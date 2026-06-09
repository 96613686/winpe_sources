# Smb2InvalidateSessionInFreePendingTable

- ea: `0x14002ff54`
- end: `0x14003011c`
- name: `Smb2InvalidateSessionInFreePendingTable`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037c24`

## callees

- `0x140015960`
- `0x14002019c`
- `0x14002ff54`
- `0x140030244`
- `0x140038490`
- `0x140077600`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140030011`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140030011`
- `ntoskrnl!RtlEqualSid` at `0x14002fff2`
- `ntoskrnl!RtlEqualSid` at `0x14002fff2`
- `srvnet!SrvLibGetSelfSid` at `0x14002ffbd`
- `srvnet!SrvLibGetSelfSid` at `0x14002ffbd`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateSessionInFreePendingTable(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  SECURITY_STATUS SelfSid; // edi
  __int64 v6; // r8
  __int64 v7; // r8
  _BYTE Sid1[816]; // [rsp+20h] [rbp-348h] BYREF

  v4 = *(_QWORD *)(a2 + 32);
  if ( !v4 || !a1 || !*(_QWORD *)a1 || !*(_QWORD *)(a1 + 8) )
    return 3221225485LL;
  SelfSid = Smb2ImpersonateSecurityContext(v4);
  if ( SelfSid < 0 )
    return (unsigned int)SelfSid;
  SelfSid = SrvLibGetSelfSid(Sid1);
  Smb2Revert();
  if ( SelfSid < 0 )
    return (unsigned int)SelfSid;
  if ( *(_QWORD *)(a2 + 200) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 25, v6, **(_QWORD **)a1);
    }
    SelfSid = -2147483622;
    goto LABEL_26;
  }
  if ( !RtlEqualSid(Sid1, (PSID)(*(_QWORD *)a1 + 16LL)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 24, v7, **(_QWORD **)a1);
    }
    SelfSid = -1073741790;
    *(_DWORD *)(*(_QWORD *)a1 + 12LL) = -1073741790;
    return (unsigned int)SelfSid;
  }
  *(_QWORD *)(a2 + 200) = *(_QWORD *)(a1 + 8);
  if ( ExAcquireRundownProtection(*(PEX_RUNDOWN_REF *)(a1 + 8)) )
  {
    *(_BYTE *)(a2 + 284) = 1;
LABEL_26:
    *(_DWORD *)(*(_QWORD *)a1 + 12LL) = 0;
    return (unsigned int)SelfSid;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x14002ff54  mov     [rsp+arg_10], rbx
0x14002ff59  mov     [rsp+arg_18], rsi
0x14002ff5e  push    rdi
0x14002ff5f  sub     rsp, 360h
0x14002ff66  mov     rax, cs:__security_cookie
0x14002ff6d  xor     rax, rsp
0x14002ff70  mov     [rsp+368h+var_18], rax
0x14002ff78  mov     rbx, rcx
0x14002ff7b  mov     rsi, rdx
0x14002ff7e  mov     rcx, [rdx+20h]
0x14002ff82  test    rcx, rcx
0x14002ff85  jz      loc_1400300F1
0x14002ff8b  test    rbx, rbx
0x14002ff8e  jz      loc_1400300F1
0x14002ff94  cmp     qword ptr [rbx], 0
0x14002ff98  jz      loc_1400300F1
0x14002ff9e  cmp     qword ptr [rbx+8], 0
0x14002ffa3  jz      loc_1400300F1
0x14002ffa9  call    Smb2ImpersonateSecurityContext
0x14002ffae  mov     edi, eax
0x14002ffb0  test    eax, eax
0x14002ffb2  js      loc_1400300ED
0x14002ffb8  lea     rcx, [rsp+368h+Sid1]
0x14002ffbd  call    cs:__imp_SrvLibGetSelfSid
0x14002ffc4  nop     dword ptr [rax+rax+00h]
0x14002ffc9  mov     edi, eax
0x14002ffcb  call    Smb2Revert
0x14002ffd0  test    edi, edi
0x14002ffd2  js      loc_1400300ED
0x14002ffd8  cmp     qword ptr [rsi+0C8h], 0
0x14002ffe0  jnz     loc_1400300AA
0x14002ffe6  mov     rdx, [rbx]
0x14002ffe9  lea     rcx, [rsp+368h+Sid1]; Sid1
0x14002ffee  add     rdx, 10h; Sid2
0x14002fff2  call    cs:__imp_RtlEqualSid
0x14002fff9  nop     dword ptr [rax+rax+00h]
0x14002fffe  test    al, al
0x140030000  jz      short loc_140030069
0x140030002  mov     rax, [rbx+8]
0x140030006  mov     [rsi+0C8h], rax
0x14003000d  mov     rcx, [rbx+8]; RunRef
0x140030011  call    cs:__imp_ExAcquireRundownProtection
0x140030018  nop     dword ptr [rax+rax+00h]
0x14003001d  test    al, al
0x14003001f  jnz     short loc_140030060
0x140030021  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030028  lea     rax, WPP_GLOBAL_Control
0x14003002f  cmp     rcx, rax
0x140030032  jz      short loc_140030056
0x140030034  mov     eax, [rcx+2Ch]
0x140030037  test    al, 1
0x140030039  jz      short loc_140030056
0x14003003b  cmp     byte ptr [rcx+29h], 2
0x14003003f  jb      short loc_140030056
0x140030041  mov     rcx, [rcx+18h]
0x140030045  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x14003004c  mov     edx, 17h
0x140030051  call    WPP_SF_
0x140030056  mov     eax, 0C00000E5h
0x14003005b  jmp     loc_1400300F6
0x140030060  mov     byte ptr [rsi+11Ch], 1
0x140030067  jmp     short loc_1400300E3
0x140030069  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030070  lea     rax, WPP_GLOBAL_Control
0x140030077  cmp     rcx, rax
0x14003007a  jz      short loc_14003009D
0x14003007c  mov     eax, [rcx+2Ch]
0x14003007f  test    al, 1
0x140030081  jz      short loc_14003009D
0x140030083  cmp     byte ptr [rcx+29h], 2
0x140030087  jb      short loc_14003009D
0x140030089  mov     r9, [rbx]
0x14003008c  mov     edx, 18h
0x140030091  mov     rcx, [rcx+18h]
0x140030095  mov     r9, [r9]
0x140030098  call    WPP_SF_i
0x14003009d  mov     rax, [rbx]
0x1400300a0  mov     edi, 0C0000022h
0x1400300a5  mov     [rax+0Ch], edi
0x1400300a8  jmp     short loc_1400300ED
0x1400300aa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400300b1  lea     rax, WPP_GLOBAL_Control
0x1400300b8  cmp     rcx, rax
0x1400300bb  jz      short loc_1400300DE
0x1400300bd  mov     eax, [rcx+2Ch]
0x1400300c0  test    al, 1
0x1400300c2  jz      short loc_1400300DE
0x1400300c4  cmp     byte ptr [rcx+29h], 2
0x1400300c8  jb      short loc_1400300DE
0x1400300ca  mov     r9, [rbx]
0x1400300cd  mov     edx, 19h
0x1400300d2  mov     rcx, [rcx+18h]
0x1400300d6  mov     r9, [r9]
0x1400300d9  call    WPP_SF_i
0x1400300de  mov     edi, 8000001Ah
0x1400300e3  mov     rax, [rbx]
0x1400300e6  mov     dword ptr [rax+0Ch], 0
0x1400300ed  mov     eax, edi
0x1400300ef  jmp     short loc_1400300F6
0x1400300f1  mov     eax, 0C000000Dh
0x1400300f6  mov     rcx, [rsp+368h+var_18]
0x1400300fe  xor     rcx, rsp; StackCookie
0x140030101  call    __security_check_cookie
0x140030106  lea     r11, [rsp+368h+var_8]
0x14003010e  mov     rbx, [r11+20h]
0x140030112  mov     rsi, [r11+28h]
0x140030116  mov     rsp, r11
0x140030119  pop     rdi
0x14003011a  retn
```
