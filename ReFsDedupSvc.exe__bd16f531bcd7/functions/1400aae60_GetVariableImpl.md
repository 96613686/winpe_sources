# GetVariableImpl

- ea: `0x1400aae60`
- end: `0x1400aafe0`
- name: `GetVariableImpl`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140050288`
- `0x1400830cc`
- `0x1400a3230`
- `0x1400aac70`
- `0x1400aae60`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1400aae94`
- `ntdll!RtlAdjustPrivilege` at `0x1400aaf9d`
- `ntdll!RtlAdjustPrivilege` at `0x1400aae94`
- `ntdll!RtlAdjustPrivilege` at `0x1400aaf9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aaf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aaf50`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableExW` at `0x1400aaf26`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableExW` at `0x1400aaf26`

## pseudocode

```c
__int64 __fastcall GetVariableImpl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, int a6)
{
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  int v12; // eax
  unsigned int v13; // edi
  unsigned int FirmwareEnvironmentVariable; // eax
  const char *v15; // r9
  signed int LastError; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // ebx
  int v19; // [rsp+20h] [rbp-40h]
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v21[2]; // [rsp+38h] [rbp-28h] BYREF
  _WORD v22[12]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  OldValue[0] = 0;
  v9 = RtlAdjustPrivilege(0x16u, 1u, NtCurrentTeb()->IsImpersonating != 0, OldValue);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v21[0] = v22;
    v21[1] = v22;
    v22[0] = 0;
    v12 = GUIDToWstring(a2, v21);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v13 = 0;
      FirmwareEnvironmentVariable = GetFirmwareEnvironmentVariableExW(a3, v21[0], a4, *(unsigned int *)a5);
      *a5 = FirmwareEnvironmentVariable;
      if ( !FirmwareEnvironmentVariable )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0x70D,
          (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
          v15);
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError == 1168 || LastError == 203 )
        {
          v13 = -1073741275;
        }
        else if ( LastError > 0 )
        {
          v13 = (unsigned __int16)LastError | 0xC0070000;
        }
      }
      if ( !OldValue[0] )
      {
        v17 = RtlAdjustPrivilege(0x16u, 0, NtCurrentTeb()->IsImpersonating != 0, OldValue);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x71D,
            (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
            (const char *)(unsigned int)v17,
            a6);
          v13 = v18;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_NtStatus(
        retaddr,
        (void *)0x702,
        (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
        (const char *)(unsigned int)v12,
        v19);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
    return v13;
  }
  else
  {
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)0x6FF,
      (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
      (const char *)(unsigned int)v9,
      v19);
    return v10;
  }
}

```

## disassembly

```asm
0x1400aae60  push    rbp
0x1400aae62  push    rbx
0x1400aae63  push    rsi
0x1400aae64  push    rdi
0x1400aae65  push    r14
0x1400aae67  mov     rbp, rsp
0x1400aae6a  sub     rsp, 60h
0x1400aae6e  mov     [rbp+OldValue], 0
0x1400aae72  mov     rsi, r9
0x1400aae75  mov     eax, gs:179Ch
0x1400aae7d  lea     r9, [rbp+OldValue]; OldValue
0x1400aae81  test    eax, eax
0x1400aae83  mov     r14, r8
0x1400aae86  mov     rdi, rdx
0x1400aae89  mov     ecx, 16h; Privilege
0x1400aae8e  setnz   r8b; ForThread
0x1400aae92  mov     dl, 1; NewValue
0x1400aae94  call    cs:__imp_RtlAdjustPrivilege
0x1400aae9b  nop     dword ptr [rax+rax+00h]
0x1400aaea0  mov     ebx, eax
0x1400aaea2  test    eax, eax
0x1400aaea4  jns     short loc_1400AAEC5
0x1400aaea6  mov     rcx, [rbp+28h]; this
0x1400aaeaa  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400aaeb1  mov     r9d, eax; char *
0x1400aaeb4  mov     edx, 6FFh; void *
0x1400aaeb9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400aaebe  mov     eax, ebx
0x1400aaec0  jmp     loc_1400AAFD4
0x1400aaec5  lea     rax, [rbp+var_18]
0x1400aaec9  mov     rcx, rdi
0x1400aaecc  mov     [rbp+var_28], rax
0x1400aaed0  lea     rdx, [rbp+var_28]
0x1400aaed4  lea     rax, [rbp+var_18]
0x1400aaed8  mov     [rbp+var_20], rax
0x1400aaedc  xor     eax, eax
0x1400aaede  mov     [rbp+var_18], ax
0x1400aaee2  call    ?GUIDToWstring@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GUIDToWstring(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1400aaee7  mov     edi, eax
0x1400aaee9  test    eax, eax
0x1400aaeeb  jns     short loc_1400AAF0A
0x1400aaeed  mov     rcx, [rbp+28h]; this
0x1400aaef1  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400aaef8  mov     r9d, eax; char *
0x1400aaefb  mov     edx, 702h; void *
0x1400aaf00  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400aaf05  jmp     loc_1400AAFC9
0x1400aaf0a  mov     rax, qword ptr [rbp+arg_28]
0x1400aaf0e  mov     r8, rsi
0x1400aaf11  mov     rbx, [rbp+arg_20]
0x1400aaf15  mov     rcx, r14
0x1400aaf18  mov     rdx, [rbp+var_28]
0x1400aaf1c  xor     edi, edi
0x1400aaf1e  mov     qword ptr [rsp+60h+var_40], rax; int
0x1400aaf23  mov     r9d, [rbx]
0x1400aaf26  call    cs:__imp_GetFirmwareEnvironmentVariableExW
0x1400aaf2d  nop     dword ptr [rax+rax+00h]
0x1400aaf32  mov     ecx, eax
0x1400aaf34  mov     [rbx], rcx
0x1400aaf37  test    eax, eax
0x1400aaf39  jnz     short loc_1400AAF80
0x1400aaf3b  mov     rcx, [rbp+28h]; this
0x1400aaf3f  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400aaf46  mov     edx, 70Dh; void *
0x1400aaf4b  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1400aaf50  call    cs:__imp_GetLastError
0x1400aaf57  nop     dword ptr [rax+rax+00h]
0x1400aaf5c  mov     edi, eax
0x1400aaf5e  cmp     eax, 490h
0x1400aaf63  jz      short loc_1400AAF7B
0x1400aaf65  cmp     eax, 0CBh
0x1400aaf6a  jz      short loc_1400AAF7B
0x1400aaf6c  test    eax, eax
0x1400aaf6e  jle     short loc_1400AAF80
0x1400aaf70  movzx   edi, ax
0x1400aaf73  or      edi, 0C0070000h
0x1400aaf79  jmp     short loc_1400AAF80
0x1400aaf7b  mov     edi, 0C0000225h
0x1400aaf80  cmp     [rbp+OldValue], 0
0x1400aaf84  jnz     short loc_1400AAFC9
0x1400aaf86  mov     eax, gs:179Ch
0x1400aaf8e  lea     r9, [rbp+OldValue]; OldValue
0x1400aaf92  test    eax, eax
0x1400aaf94  setnz   r8b; ForThread
0x1400aaf98  xor     edx, edx; NewValue
0x1400aaf9a  lea     ecx, [rdx+16h]; Privilege
0x1400aaf9d  call    cs:__imp_RtlAdjustPrivilege
0x1400aafa4  nop     dword ptr [rax+rax+00h]
0x1400aafa9  mov     ebx, eax
0x1400aafab  test    eax, eax
0x1400aafad  jns     short loc_1400AAFC9
0x1400aafaf  mov     rcx, [rbp+28h]; this
0x1400aafb3  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400aafba  mov     r9d, eax; char *
0x1400aafbd  mov     edx, 71Dh; void *
0x1400aafc2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400aafc7  mov     edi, ebx
0x1400aafc9  lea     rcx, [rbp+var_28]
0x1400aafcd  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1400aafd2  mov     eax, edi
0x1400aafd4  add     rsp, 60h
0x1400aafd8  pop     r14
0x1400aafda  pop     rdi
0x1400aafdb  pop     rsi
0x1400aafdc  pop     rbx
0x1400aafdd  pop     rbp
0x1400aafde  retn
```
