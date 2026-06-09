# UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)

- ea: `0x140007a4c`
- end: `0x140007b8c`
- name: `?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(void *, enum _PS_PROTECTED_TYPE *, enum _PS_PROTECTED_SIGNER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005590`
- `0x140007634`
- `0x140007b94`

## callees

- `0x140007a4c`
- `0x140007c34`
- `0x140007cd4`
- `0x14000e598`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140007ad7`
- `ntdll!NtQueryInformationProcess` at `0x140007ad7`

## pseudocode

```c
__int64 __fastcall UtilGetProtectedProcessInfo(void *a1, enum _PS_PROTECTED_TYPE *a2, enum _PS_PROTECTED_SIGNER *a3)
{
  _QWORD *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  NTSTATUS v9; // ebx
  unsigned __int8 v10; // al
  unsigned __int8 ProcessInformation; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -2147024809;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v6;
    v7 = 10;
LABEL_5:
    WPP_SF_d(v5[2], v7, &WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids, v6);
    return v6;
  }
  if ( a2 )
    *(_DWORD *)a2 = 3;
  if ( a3 )
    *(_DWORD *)a3 = 9;
  ProcessInformation = 0;
  v9 = NtQueryInformationProcess(a1, ProcessAffinityUpdateMode|ProcessUserModeIOPL, &ProcessInformation, 1u, 0);
  if ( v9 < 0 )
  {
    v6 = v9 | 0x10000000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return v6;
    v7 = 11;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids,
      ProcessInformation & 7,
      ProcessInformation >> 4);
  v10 = ProcessInformation;
  if ( (ProcessInformation & 7u) >= 3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = ProcessInformation;
  }
  if ( a2 )
    *(_DWORD *)a2 = v10 & 7;
  if ( a3 )
    *(_DWORD *)a3 = v10 >> 4;
  return 0;
}

```

## disassembly

```asm
0x140007a4c  mov     [rsp+arg_8], rbx
0x140007a51  mov     [rsp+arg_10], rsi
0x140007a56  push    rdi
0x140007a57  sub     rsp, 30h
0x140007a5b  mov     rdi, r8
0x140007a5e  mov     rsi, rdx
0x140007a61  test    rcx, rcx
0x140007a64  jnz     short loc_140007AA3
0x140007a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a6d  lea     rax, WPP_GLOBAL_Control
0x140007a74  mov     ebx, 80070057h
0x140007a79  cmp     rcx, rax
0x140007a7c  jz      short loc_140007A9C
0x140007a7e  test    byte ptr [rcx+1Ch], 1
0x140007a82  jz      short loc_140007A9C
0x140007a84  mov     edx, 0Ah
0x140007a89  mov     rcx, [rcx+10h]
0x140007a8d  lea     r8, WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids
0x140007a94  mov     r9d, ebx
0x140007a97  call    WPP_SF_d
0x140007a9c  mov     eax, ebx
0x140007a9e  jmp     loc_140007B7C
0x140007aa3  test    rsi, rsi
0x140007aa6  jz      short loc_140007AAE
0x140007aa8  mov     dword ptr [rdx], 3
0x140007aae  test    rdi, rdi
0x140007ab1  jz      short loc_140007ABA
0x140007ab3  mov     dword ptr [r8], 9
0x140007aba  mov     r9d, 1; ProcessInformationLength
0x140007ac0  mov     [rsp+38h+ProcessInformation], 0
0x140007ac5  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x140007aca  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x140007ad3  lea     edx, [r9+3Ch]; ProcessInformationClass
0x140007ad7  call    cs:__imp_NtQueryInformationProcess
0x140007add  mov     ebx, eax
0x140007adf  test    eax, eax
0x140007ae1  jns     short loc_140007B07
0x140007ae3  bts     ebx, 1Ch
0x140007ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x140007aee  lea     rax, WPP_GLOBAL_Control
0x140007af5  cmp     rcx, rax
0x140007af8  jz      short loc_140007A9C
0x140007afa  test    byte ptr [rcx+1Ch], 2
0x140007afe  jz      short loc_140007A9C
0x140007b00  mov     edx, 0Bh
0x140007b05  jmp     short loc_140007A89
0x140007b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b0e  lea     rax, WPP_GLOBAL_Control
0x140007b15  cmp     rcx, rax
0x140007b18  jz      short loc_140007B49
0x140007b1a  test    byte ptr [rcx+1Ch], 8
0x140007b1e  jz      short loc_140007B49
0x140007b20  movzx   r9d, [rsp+38h+ProcessInformation]
0x140007b26  lea     r8, WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids
0x140007b2d  mov     rcx, [rcx+10h]
0x140007b31  mov     eax, r9d
0x140007b34  shr     eax, 4
0x140007b37  and     r9d, 7
0x140007b3b  mov     edx, 0Ch
0x140007b40  mov     dword ptr [rsp+38h+ReturnLength], eax
0x140007b44  call    WPP_SF_DD
0x140007b49  mov     al, [rsp+38h+ProcessInformation]
0x140007b4d  mov     cl, al
0x140007b4f  and     cl, 7
0x140007b52  cmp     cl, 3
0x140007b55  jb      short loc_140007B60
0x140007b57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140007b5c  mov     al, [rsp+38h+ProcessInformation]
0x140007b60  test    rsi, rsi
0x140007b63  jz      short loc_140007B6D
0x140007b65  movzx   ecx, al
0x140007b68  and     ecx, 7
0x140007b6b  mov     [rsi], ecx
0x140007b6d  test    rdi, rdi
0x140007b70  jz      short loc_140007B7A
0x140007b72  movzx   ecx, al
0x140007b75  shr     ecx, 4
0x140007b78  mov     [rdi], ecx
0x140007b7a  xor     eax, eax
0x140007b7c  mov     rbx, [rsp+38h+arg_8]
0x140007b81  mov     rsi, [rsp+38h+arg_10]
0x140007b86  add     rsp, 30h
0x140007b8a  pop     rdi
0x140007b8b  retn
```
