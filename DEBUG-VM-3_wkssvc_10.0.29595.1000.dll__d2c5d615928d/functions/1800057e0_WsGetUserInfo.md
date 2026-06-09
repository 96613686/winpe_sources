# WsGetUserInfo

- ea: `0x1800057e0`
- end: `0x180005a52`
- name: `WsGetUserInfo`
- size: `626`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca10`

## callees

- `0x1800051c0`
- `0x1800057e0`
- `0x180005a60`
- `0x18001e420`
- `0x18001ed46`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180005856`
- `ntdll!RtlCopyLuid` at `0x180005948`
- `ntdll!RtlCopyLuid` at `0x180005856`
- `ntdll!RtlCopyLuid` at `0x180005948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a35`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18000588d`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18000588d`

## pseudocode

```c
__int64 __fastcall WsGetUserInfo(PLUID SourceLuid, int a2, PVOID *a3, HLOCAL *a4, unsigned int *a5, unsigned int *a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebp
  __int64 result; // rax
  unsigned __int16 *v13; // rdx
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int i; // edx
  unsigned int v18; // ecx
  int ProtocolStatus; // [rsp+50h] [rbp-C8h] BYREF
  ULONG ReturnBufferLength; // [rsp+54h] [rbp-C4h] BYREF
  int ProtocolSubmitBuffer; // [rsp+58h] [rbp-C0h] BYREF
  struct _LUID DestinationLuid; // [rsp+5Ch] [rbp-BCh] BYREF
  _DWORD v23[2]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v24[4]; // [rsp+78h] [rbp-A0h] BYREF
  struct _LUID v25; // [rsp+7Ch] [rbp-9Ch] BYREF
  unsigned int v26; // [rsp+A8h] [rbp-70h]
  __int64 v27; // [rsp+B0h] [rbp-68h]

  ReturnBufferLength = 0;
  if ( a2 != 1 && a2 != 1101 )
    goto LABEL_3;
  memset_0(v24, 0, 0x58u);
  if ( !WsDgReceiverDeviceHandle )
  {
    if ( a6 )
      *a6 += 2;
    *a5 = 0;
    *a4 = 0;
LABEL_23:
    if ( a2 == 1101 )
    {
      v18 = *a6 + 8;
      if ( v18 < *a6 )
      {
LABEL_11:
        *a6 = -1;
        return 2140;
      }
      *a6 = v18;
      return 0;
    }
LABEL_3:
    ProtocolStatus = 0;
    DestinationLuid = 0;
    ProtocolSubmitBuffer = 3;
    RtlCopyLuid(&DestinationLuid, SourceLuid);
    v10 = LsaCallAuthenticationPackage(
            LsaHandle,
            AuthenticationPackage,
            &ProtocolSubmitBuffer,
            0xCu,
            a3,
            &ReturnBufferLength,
            &ProtocolStatus);
    if ( v10 || (v10 = ProtocolStatus) != 0 )
    {
      v11 = WsMapStatus(v10);
      if ( v11 )
      {
        LocalFree(*a4);
        *a4 = 0;
        result = v11;
        *a5 = 0;
        return result;
      }
    }
    if ( a6 )
    {
      v13 = (unsigned __int16 *)*a3;
      if ( a2 )
        v14 = v13[16] + v13[24] + v13[8] + 38;
      else
        v14 = v13[8] + 10;
      v15 = *a6 + v14;
      if ( v15 < *a6 )
        goto LABEL_11;
      *a6 = v15;
    }
    return 0;
  }
  v23[1] = 6;
  v23[0] = 0;
  RtlCopyLuid(&v25, SourceLuid);
  v27 = 0;
  result = WsDeviceControlGetInfo(1, WsDgReceiverDeviceHandle, 1245207, v23, 96, a4, -1, 0);
  if ( !(_DWORD)result )
  {
    if ( a6 )
      *a6 += 2;
    v16 = v26;
    *a5 = v26;
    if ( !v16 && *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( a6 )
    {
      for ( i = 0; i < *a5; ++i )
      {
        if ( *((_DWORD *)*a4 + 6 * i + 4) == 4 )
          *a6 += *((unsigned __int16 *)*a4 + 12 * i) + 2;
      }
    }
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x1800057e0  push    rbx
0x1800057e2  push    rbp
0x1800057e3  push    rsi
0x1800057e4  push    rdi
0x1800057e5  push    r12
0x1800057e7  push    r14
0x1800057e9  push    r15
0x1800057eb  sub     rsp, 0E0h
0x1800057f2  mov     rax, cs:__security_cookie
0x1800057f9  xor     rax, rsp
0x1800057fc  mov     [rsp+118h+var_48], rax
0x180005804  mov     r15, [rsp+118h+arg_20]
0x18000580c  xor     r12d, r12d
0x18000580f  mov     rbx, [rsp+118h+arg_28]
0x180005817  mov     r14, r9
0x18000581a  mov     [rsp+118h+var_C4], r12d
0x18000581f  mov     rsi, r8
0x180005822  mov     edi, edx
0x180005824  mov     rbp, rcx
0x180005827  cmp     edx, 1
0x18000582a  jz      loc_180005914
0x180005830  cmp     edx, 44Dh
0x180005836  jz      loc_180005914
0x18000583c  mov     rdx, rbp; SourceLuid
0x18000583f  mov     [rsp+118h+var_C8], r12d
0x180005844  lea     rcx, [rsp+118h+DestinationLuid]; DestinationLuid
0x180005849  mov     qword ptr [rsp+118h+DestinationLuid.LowPart], r12
0x18000584e  mov     [rsp+118h+ProtocolSubmitBuffer], 3
0x180005856  call    cs:__imp_RtlCopyLuid
0x18000585c  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x180005862  lea     rax, [rsp+118h+var_C8]
0x180005867  mov     rcx, cs:LsaHandle; LsaHandle
0x18000586e  lea     r8, [rsp+118h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x180005873  mov     [rsp+118h+ProtocolStatus], rax; ProtocolStatus
0x180005878  mov     r9d, 0Ch; SubmitBufferLength
0x18000587e  lea     rax, [rsp+118h+var_C4]
0x180005883  mov     [rsp+118h+ReturnBufferLength], rax; ReturnBufferLength
0x180005888  mov     [rsp+118h+ProtocolReturnBuffer], rsi; ProtocolReturnBuffer
0x18000588d  call    cs:__imp_LsaCallAuthenticationPackage
0x180005893  test    eax, eax
0x180005895  jz      short loc_1800058B7
0x180005897  mov     ecx, eax
0x180005899  call    WsMapStatus
0x18000589e  mov     ebp, eax
0x1800058a0  test    eax, eax
0x1800058a2  jz      short loc_1800058BF
0x1800058a4  mov     rcx, [r14]; hMem
0x1800058a7  call    cs:__imp_LocalFree
0x1800058ad  mov     [r14], r12
0x1800058b0  mov     eax, ebp
0x1800058b2  mov     [r15], r12d
0x1800058b5  jmp     short loc_1800058F2
0x1800058b7  mov     eax, [rsp+118h+var_C8]
0x1800058bb  test    eax, eax
0x1800058bd  jnz     short loc_180005897
0x1800058bf  test    rbx, rbx
0x1800058c2  jz      loc_1800059F2
0x1800058c8  mov     rdx, [rsi]
0x1800058cb  test    edi, edi
0x1800058cd  jnz     loc_1800059F9
0x1800058d3  movzx   eax, word ptr [rdx+10h]
0x1800058d7  add     eax, 0Ah
0x1800058da  mov     ecx, [rbx]
0x1800058dc  lea     edx, [rcx+rax]
0x1800058df  cmp     edx, ecx
0x1800058e1  jnb     loc_180005A4E
0x1800058e7  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800058ed  mov     eax, 85Ch
0x1800058f2  mov     rcx, [rsp+118h+var_48]
0x1800058fa  xor     rcx, rsp; StackCookie
0x1800058fd  call    __security_check_cookie
0x180005902  add     rsp, 0E0h
0x180005909  pop     r15
0x18000590b  pop     r14
0x18000590d  pop     r12
0x18000590f  pop     rdi
0x180005910  pop     rsi
0x180005911  pop     rbp
0x180005912  pop     rbx
0x180005913  retn
0x180005914  xor     edx, edx; Val
0x180005916  lea     rcx, [rsp+118h+var_A0]; void *
0x18000591b  mov     r8d, 58h ; 'X'; Size
0x180005921  call    memset_0
0x180005926  cmp     cs:WsDgReceiverDeviceHandle, r12
0x18000592d  jz      loc_180005A11
0x180005933  mov     rdx, rbp; SourceLuid
0x180005936  mov     [rsp+118h+var_A4], 6
0x18000593e  lea     rcx, [rsp+118h+var_9C]; DestinationLuid
0x180005943  mov     [rsp+118h+var_A8], r12d
0x180005948  call    cs:__imp_RtlCopyLuid
0x18000594e  mov     rdx, cs:WsDgReceiverDeviceHandle
0x180005955  lea     r9, [rsp+118h+var_A8]
0x18000595a  mov     [rsp+118h+var_E0], r12d
0x18000595f  mov     r8d, 130017h
0x180005965  mov     dword ptr [rsp+118h+ProtocolStatus], 0FFFFFFFFh
0x18000596d  mov     ecx, 1
0x180005972  mov     [rsp+118h+ReturnBufferLength], r14
0x180005977  mov     dword ptr [rsp+118h+ProtocolReturnBuffer], 60h ; '`'
0x18000597f  mov     [rsp+118h+var_68], r12
0x180005987  call    WsDeviceControlGetInfo
0x18000598c  test    eax, eax
0x18000598e  jnz     loc_1800058F2
0x180005994  test    rbx, rbx
0x180005997  jnz     loc_180005A21
0x18000599d  mov     eax, [rsp+118h+var_70]
0x1800059a4  mov     [r15], eax
0x1800059a7  test    eax, eax
0x1800059a9  jz      loc_180005A29
0x1800059af  test    rbx, rbx
0x1800059b2  jz      short loc_1800059D7
0x1800059b4  mov     edx, r12d
0x1800059b7  cmp     [r15], r12d
0x1800059ba  jbe     short loc_1800059D7
0x1800059bc  nop     dword ptr [rax+00h]
0x1800059c0  mov     eax, edx
0x1800059c2  lea     rcx, [rax+rax*2]
0x1800059c6  mov     rax, [r14]
0x1800059c9  cmp     dword ptr [rax+rcx*8+10h], 4
0x1800059ce  jz      short loc_180005A43
0x1800059d0  inc     edx
0x1800059d2  cmp     edx, [r15]
0x1800059d5  jb      short loc_1800059C0
0x1800059d7  cmp     edi, 44Dh
0x1800059dd  jnz     loc_18000583C
0x1800059e3  mov     eax, [rbx]
0x1800059e5  lea     ecx, [rax+8]
0x1800059e8  cmp     ecx, eax
0x1800059ea  jb      loc_1800058E7
0x1800059f0  mov     [rbx], ecx
0x1800059f2  xor     eax, eax
0x1800059f4  jmp     loc_1800058F2
0x1800059f9  movzx   eax, word ptr [rdx+20h]
0x1800059fd  movzx   ecx, word ptr [rdx+30h]
0x180005a01  add     ecx, eax
0x180005a03  movzx   eax, word ptr [rdx+10h]
0x180005a07  add     eax, 26h ; '&'
0x180005a0a  add     eax, ecx
0x180005a0c  jmp     loc_1800058DA
0x180005a11  test    rbx, rbx
0x180005a14  jz      short loc_180005A19
0x180005a16  add     dword ptr [rbx], 2
0x180005a19  mov     [r15], r12d
0x180005a1c  mov     [r14], r12
0x180005a1f  jmp     short loc_1800059D7
0x180005a21  add     dword ptr [rbx], 2
0x180005a24  jmp     loc_18000599D
0x180005a29  mov     rcx, [r14]; hMem
0x180005a2c  test    rcx, rcx
0x180005a2f  jz      loc_1800059AF
0x180005a35  call    cs:__imp_LocalFree
0x180005a3b  mov     [r14], r12
0x180005a3e  jmp     loc_1800059AF
0x180005a43  movzx   eax, word ptr [rax+rcx*8]
0x180005a47  add     eax, 2
0x180005a4a  add     [rbx], eax
0x180005a4c  jmp     short loc_1800059D0
0x180005a4e  mov     [rbx], edx
0x180005a50  jmp     short loc_1800059F2
```
