# RebootSystem(void)

- ea: `0x140009918`
- end: `0x140009ab7`
- name: `?RebootSystem@@YAJXZ`
- size: `415`
- prototype: `int __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140006b04`

## callees

- `0x140007734`
- `0x140009340`
- `0x140009918`
- `0x140009ac0`
- `0x140009ae4`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099ad`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000999f`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000999f`
- `ntdll!RtlAdjustPrivilege` at `0x140009966`
- `ntdll!RtlAdjustPrivilege` at `0x140009a2f`
- `ntdll!RtlAdjustPrivilege` at `0x140009a5e`
- `ntdll!RtlAdjustPrivilege` at `0x140009966`
- `ntdll!RtlAdjustPrivilege` at `0x140009a2f`
- `ntdll!RtlAdjustPrivilege` at `0x140009a5e`

## pseudocode

```c
int __fastcall RebootSystem(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int result; // eax
  __int64 v7; // r9
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // r8
  signed int LastError; // eax
  signed int v11; // ebx
  NTSTATUS v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  NTSTATUS v15; // eax
  void *v16; // rdx
  int bRebootAfterShutdown; // [rsp+20h] [rbp-58h]
  int bRebootAfterShutdowna; // [rsp+20h] [rbp-58h]
  int bRebootAfterShutdownb; // [rsp+20h] [rbp-58h]
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-48h] BYREF
  signed int v21; // [rsp+38h] [rbp-40h] BYREF
  int v22[4]; // [rsp+40h] [rbp-38h] BYREF
  signed int *v23; // [rsp+50h] [rbp-28h]
  __int64 v24; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, TimeloopStartRebootSystem, a3, 1, v22);
  OldValue[0] = 0;
  v3 = RtlAdjustPrivilege(0x13u, 1u, 0, OldValue);
  if ( v3 >= 0 )
  {
    if ( InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0x20001u) )
      goto LABEL_30;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v7 = 2;
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v21 = v11;
      v23 = &v21;
      v24 = 4;
      McGenEventWrite_EventWriteTransfer(v8, ProvToolInitiateSystemShutdownExFailed, v9, 2, v22);
    }
    if ( v11 >= 0 )
    {
LABEL_30:
      if ( OldValue[0] )
      {
        v15 = RtlAdjustPrivilege(0x13u, 0, 0, OldValue);
        v8 = retaddr;
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_NtStatus(
            retaddr,
            v16,
            v9,
            (const char *)(unsigned int)v15,
            bRebootAfterShutdowna);
      }
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v8, ProvToolInitiateSystemShutdownExSucceeded, v9, 1, v22);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
        (const char *)(unsigned int)v11,
        bRebootAfterShutdowna);
      if ( OldValue[0] )
      {
        v12 = RtlAdjustPrivilege(0x13u, 0, 0, OldValue);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_NtStatus(
            retaddr,
            v13,
            v14,
            (const char *)(unsigned int)v12,
            bRebootAfterShutdownb);
      }
      result = v11;
    }
  }
  else
  {
    result = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               v4,
               v5,
               (const char *)(unsigned int)v3,
               bRebootAfterShutdown);
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v21 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x8E,
              (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
              (const char *)v7);
      result = v21;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x140009918  push    rbx
0x14000991a  sub     rsp, 70h
0x14000991e  mov     rax, cs:__security_cookie
0x140009925  xor     rax, rsp
0x140009928  mov     [rsp+78h+var_18], rax
0x14000992d  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x140009934  jz      short loc_140009953
0x140009936  lea     rax, [rsp+78h+var_38]
0x14000993b  mov     qword ptr [rsp+78h+bRebootAfterShutdown], rax; int
0x140009940  mov     r9d, 1
0x140009946  lea     rdx, TimeloopStartRebootSystem
0x14000994d  call    McGenEventWrite_EventWriteTransfer
0x140009952  nop
0x140009953  mov     [rsp+78h+OldValue], 0
0x140009958  lea     r9, [rsp+78h+OldValue]; OldValue
0x14000995d  xor     r8d, r8d; ForThread
0x140009960  mov     dl, 1; NewValue
0x140009962  lea     ecx, [r8+13h]; Privilege
0x140009966  call    cs:__imp_RtlAdjustPrivilege
0x14000996c  test    eax, eax
0x14000996e  jns     short loc_140009982
0x140009970  mov     rcx, [rsp+78h]; this
0x140009975  mov     r9d, eax; char *
0x140009978  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14000997d  jmp     loc_140009AA3
0x140009982  mov     [rsp+78h+dwReason], 20001h; dwReason
0x14000998a  mov     [rsp+78h+bRebootAfterShutdown], 1; int
0x140009992  mov     r9d, 1; bForceAppsClosed
0x140009998  xor     r8d, r8d; dwTimeout
0x14000999b  xor     edx, edx; lpMessage
0x14000999d  xor     ecx, ecx; lpMachineName
0x14000999f  call    cs:__imp_InitiateSystemShutdownExW
0x1400099a5  test    eax, eax
0x1400099a7  jnz     loc_140009A4A
0x1400099ad  call    cs:__imp_GetLastError
0x1400099b3  mov     ebx, eax
0x1400099b5  test    eax, eax
0x1400099b7  jle     short loc_1400099C2
0x1400099b9  movzx   ebx, ax
0x1400099bc  or      ebx, 80070000h
0x1400099c2  mov     r9d, 2
0x1400099c8  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, r9b
0x1400099cf  jz      short loc_1400099FE
0x1400099d1  mov     [rsp+78h+var_40], ebx
0x1400099d5  lea     rax, [rsp+78h+var_40]
0x1400099da  mov     [rsp+78h+var_28], rax
0x1400099df  mov     [rsp+78h+var_20], 4
0x1400099e8  lea     rax, [rsp+78h+var_38]
0x1400099ed  mov     qword ptr [rsp+78h+bRebootAfterShutdown], rax; int
0x1400099f2  lea     rdx, ProvToolInitiateSystemShutdownExFailed
0x1400099f9  call    McGenEventWrite_EventWriteTransfer
0x1400099fe  test    ebx, ebx
0x140009a00  jns     short loc_140009A4A
0x140009a02  mov     rcx, [rsp+78h]; this
0x140009a07  mov     r9d, ebx; char *
0x140009a0a  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x140009a11  mov     edx, 8Bh; void *
0x140009a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009a1b  cmp     [rsp+78h+OldValue], 0
0x140009a20  jz      short loc_140009A46
0x140009a22  lea     r9, [rsp+78h+OldValue]; OldValue
0x140009a27  xor     r8d, r8d; ForThread
0x140009a2a  xor     edx, edx; NewValue
0x140009a2c  lea     ecx, [rdx+13h]; Privilege
0x140009a2f  call    cs:__imp_RtlAdjustPrivilege
0x140009a35  mov     rcx, [rsp+78h]; this
0x140009a3a  test    eax, eax
0x140009a3c  jns     short loc_140009A46
0x140009a3e  mov     r9d, eax; char *
0x140009a41  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x140009a46  mov     eax, ebx
0x140009a48  jmp     short loc_140009AA3
0x140009a4a  cmp     [rsp+78h+OldValue], 0
0x140009a4f  jz      short loc_140009A76
0x140009a51  lea     r9, [rsp+78h+OldValue]; OldValue
0x140009a56  xor     r8d, r8d; ForThread
0x140009a59  xor     edx, edx; NewValue
0x140009a5b  lea     ecx, [rdx+13h]; Privilege
0x140009a5e  call    cs:__imp_RtlAdjustPrivilege
0x140009a64  mov     rcx, [rsp+78h]; this
0x140009a69  test    eax, eax
0x140009a6b  jns     short loc_140009A76
0x140009a6d  mov     r9d, eax; char *
0x140009a70  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x140009a75  nop
0x140009a76  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x140009a7d  jz      short loc_140009A9B
0x140009a7f  lea     rax, [rsp+78h+var_38]
0x140009a84  mov     qword ptr [rsp+78h+bRebootAfterShutdown], rax
0x140009a89  mov     r9d, 1
0x140009a8f  lea     rdx, ProvToolInitiateSystemShutdownExSucceeded
0x140009a96  call    McGenEventWrite_EventWriteTransfer
0x140009a9b  xor     eax, eax
0x140009a9d  jmp     short loc_140009AA3
0x140009a9f  mov     eax, [rsp+78h+var_40]
0x140009aa3  mov     rcx, [rsp+78h+var_18]
0x140009aa8  xor     rcx, rsp; StackCookie
0x140009aab  call    __security_check_cookie
0x140009ab0  add     rsp, 70h
0x140009ab4  pop     rbx
0x140009ab5  retn
```
