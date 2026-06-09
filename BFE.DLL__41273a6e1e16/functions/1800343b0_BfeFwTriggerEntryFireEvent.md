# BfeFwTriggerEntryFireEvent

- ea: `0x1800343b0`
- end: `0x180034532`
- name: `BfeFwTriggerEntryFireEvent`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cea0`
- `0x18004cc00`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x1800343b0`
- `0x18005aa60`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180034409`
- `ntdll!EtwEventWrite` at `0x18003445b`
- `ntdll!EtwEventWrite` at `0x180034409`
- `ntdll!EtwEventWrite` at `0x18003445b`

## string_xrefs

- `0x18003446e`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall BfeFwTriggerEntryFireEvent(__int64 a1, int a2)
{
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rcx
  int v7; // r8d
  int v8; // [rsp+30h] [rbp-58h] BYREF
  __int64 v9; // [rsp+38h] [rbp-50h] BYREF
  int v10; // [rsp+40h] [rbp-48h]
  int v11; // [rsp+44h] [rbp-44h]
  _BYTE v12[16]; // [rsp+48h] [rbp-40h] BYREF
  const char *v13; // [rsp+58h] [rbp-30h]
  __int64 v14; // [rsp+60h] [rbp-28h]
  int *v15; // [rsp+68h] [rbp-20h]
  __int64 v16; // [rsp+70h] [rbp-18h]

  v9 = *(_QWORD *)(a1 + 32);
  v2 = 0;
  v3 = *(_DWORD *)(a1 + 48) + 74;
  v11 = 0;
  v10 = v3;
  if ( a2 )
  {
    if ( a2 != 1 )
      return v2;
    if ( *(_DWORD *)(a1 + 28) != 1 )
      return v2;
    v4 = EtwEventWrite(gBfeFwPortEvent, Symbol_FirewallPortCloseEvent, 1, &v9);
    if ( !v4 )
      return v2;
  }
  else
  {
    if ( *(_DWORD *)(a1 + 28) )
      return v2;
    v4 = EtwEventWrite(gBfeFwPortEvent, Symbol_FirewallPortOpenEvent, 1, &v9);
    if ( !v4 )
      return v2;
  }
  v2 = WfpReportSysErrorAsWinError(v5, "EtwEventWrite", v4);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v7, 0, (__int64)"BfeFwTriggerEntryFireEvent", v2);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v8 = v2;
      v15 = &v8;
      v13 = "BfeFwTriggerEntryFireEvent";
      v14 = 27;
      v16 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v7,
        3,
        (__int64)v12);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800343b0  mov     [rsp+arg_8], rbx
0x1800343b5  push    rsi
0x1800343b6  sub     rsp, 80h
0x1800343bd  mov     rax, cs:__security_cookie
0x1800343c4  xor     rax, rsp
0x1800343c7  mov     [rsp+88h+var_10], rax
0x1800343cc  mov     rax, [rcx+20h]
0x1800343d0  xor     esi, esi
0x1800343d2  mov     [rsp+88h+var_50], rax
0x1800343d7  mov     ebx, esi
0x1800343d9  mov     eax, [rcx+30h]
0x1800343dc  add     eax, 4Ah ; 'J'
0x1800343df  mov     [rsp+88h+var_44], esi
0x1800343e3  mov     [rsp+88h+var_48], eax
0x1800343e7  test    edx, edx
0x1800343e9  jnz     short loc_18003443B
0x1800343eb  cmp     [rcx+1Ch], ebx
0x1800343ee  jnz     short loc_180034419
0x1800343f0  mov     rcx, cs:gBfeFwPortEvent
0x1800343f7  lea     r9, [rsp+88h+var_50]
0x1800343fc  mov     r8d, 1
0x180034402  lea     rdx, Symbol_FirewallPortOpenEvent
0x180034409  call    cs:__imp_EtwEventWrite
0x180034410  nop     dword ptr [rax+rax+00h]
0x180034415  test    eax, eax
0x180034417  jnz     short loc_18003446B
0x180034419  mov     rax, rbx
0x18003441c  mov     rcx, [rsp+88h+var_10]
0x180034421  xor     rcx, rsp; StackCookie
0x180034424  call    __security_check_cookie
0x180034429  mov     rbx, [rsp+88h+arg_8]
0x180034431  add     rsp, 80h
0x180034438  pop     rsi
0x180034439  retn
0x18003443b  cmp     edx, 1
0x18003443e  jnz     short loc_180034419
0x180034440  cmp     [rcx+1Ch], edx
0x180034443  jnz     short loc_180034419
0x180034445  mov     rcx, cs:gBfeFwPortEvent
0x18003444c  lea     r9, [rsp+88h+var_50]
0x180034451  mov     r8d, edx
0x180034454  lea     rdx, Symbol_FirewallPortCloseEvent
0x18003445b  call    cs:__imp_EtwEventWrite
0x180034462  nop     dword ptr [rax+rax+00h]
0x180034467  test    eax, eax
0x180034469  jz      short loc_180034419
0x18003446b  mov     r8d, eax
0x18003446e  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x180034475  call    WfpReportSysErrorAsWinError
0x18003447a  mov     rbx, rax
0x18003447d  test    rax, rax
0x180034480  jz      short loc_180034419
0x180034482  mov     [rsp+88h+arg_0], rdi
0x18003448a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034491  lea     rax, WPP_GLOBAL_Control
0x180034498  lea     rdi, aBfefwtriggeren; "BfeFwTriggerEntryFireEvent"
0x18003449f  cmp     rcx, rax
0x1800344a2  jz      short loc_1800344CA
0x1800344a4  cmp     byte ptr [rcx+19h], 2
0x1800344a8  jb      short loc_1800344CA
0x1800344aa  test    byte ptr [rcx+1Ch], 1
0x1800344ae  jz      short loc_1800344CA
0x1800344b0  mov     rcx, [rcx+10h]
0x1800344b4  mov     edx, 1Ah
0x1800344b9  mov     [rsp+88h+var_60], ebx
0x1800344bd  xor     r9d, r9d
0x1800344c0  mov     [rsp+88h+var_68], rdi
0x1800344c5  call    WPP_SF_Ssd
0x1800344ca  cmp     cs:gWfpLogUserModeErrors, esi
0x1800344d0  jnz     short loc_1800344DF
0x1800344d2  mov     rdi, [rsp+88h+arg_0]
0x1800344da  jmp     loc_180034419
0x1800344df  test    cs:byte_1800F6115, 1
0x1800344e6  jz      short loc_1800344D2
0x1800344e8  lea     rax, [rsp+88h+var_58]
0x1800344ed  mov     [rsp+88h+var_58], ebx
0x1800344f1  mov     [rsp+88h+var_20], rax
0x1800344f6  lea     rdx, WFP_USERMODE_ERROR
0x1800344fd  lea     rax, [rsp+88h+var_40]
0x180034502  mov     [rsp+88h+var_30], rdi
0x180034507  mov     r9d, 3
0x18003450d  mov     [rsp+88h+var_68], rax
0x180034512  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180034519  mov     [rsp+88h+var_28], 1Bh
0x180034522  mov     [rsp+88h+var_18], 4
0x18003452b  call    McGenEventWrite_EtwEventWriteTransfer
0x180034530  jmp     short loc_1800344D2
```
