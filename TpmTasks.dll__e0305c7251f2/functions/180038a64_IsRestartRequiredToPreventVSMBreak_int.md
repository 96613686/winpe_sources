# IsRestartRequiredToPreventVSMBreak(int *)

- ea: `0x180038a64`
- end: `0x180038b94`
- name: `?IsRestartRequiredToPreventVSMBreak@@YAJPEAH@Z`
- size: `304`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180038784`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x180024780`
- `0x18003720c`
- `0x18003893c`
- `0x180038a64`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180038aae`
- `ntdll!NtQuerySystemInformation` at `0x180038aae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038b31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038b31`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsRestartRequiredToPreventVSMBreak(ULONG *a1)
{
  NTSTATUS v2; // eax
  __int64 result; // rax
  signed int restarted; // ebx
  int v5; // eax
  HKEY *phkResult; // rax
  LSTATUS v7; // eax
  ULONG ReturnLength; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-1Ch] BYREF
  __int128 SystemInformation; // [rsp+58h] [rbp-18h] BYREF

  *a1 = 0;
  SystemInformation = 0;
  ReturnLength = 0;
  v2 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, &ReturnLength);
  if ( v2 >= 0 )
  {
    v5 = SystemInformation & 1;
    restarted = 0;
  }
  else
  {
    result = HResultFromNtStatus(v2);
    restarted = result;
    if ( (int)result < 0 )
      return result;
    v5 = 0;
  }
  if ( v5 )
  {
    *(_QWORD *)&SystemInformation = 0;
    dwDisposition = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&SystemInformation);
    v7 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
           0,
           0,
           0,
           0xF003Fu,
           0,
           phkResult,
           &dwDisposition);
    restarted = v7;
    if ( v7 > 0 )
      restarted = (unsigned __int16)v7 | 0x80070000;
    if ( restarted >= 0 && dwDisposition == 2 )
    {
      ReturnLength = 0;
      restarted = IsRestartRequiredForVSM((int *)&ReturnLength);
      if ( restarted >= 0 )
        *a1 = ReturnLength;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&SystemInformation);
  }
  return (unsigned int)restarted;
}

```

## disassembly

```asm
0x180038a64  mov     [rsp-8+arg_8], rbx
0x180038a69  mov     [rsp-8+arg_10], rdi
0x180038a6e  push    rbp
0x180038a6f  mov     rbp, rsp
0x180038a72  sub     rsp, 70h
0x180038a76  mov     rax, cs:__security_cookie
0x180038a7d  xor     rax, rsp
0x180038a80  mov     [rbp+var_8], rax
0x180038a84  mov     rdi, rcx
0x180038a87  mov     dword ptr [rcx], 0
0x180038a8d  xorps   xmm0, xmm0
0x180038a90  movups  [rbp+SystemInformation], xmm0
0x180038a94  mov     [rbp+ReturnLength], 0
0x180038a9b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180038a9f  mov     r8d, 10h; SystemInformationLength
0x180038aa5  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180038aa9  mov     ecx, 0A5h; SystemInformationClass
0x180038aae  call    cs:__imp_NtQuerySystemInformation
0x180038ab4  test    eax, eax
0x180038ab6  jns     short loc_180038ACD
0x180038ab8  mov     ecx, eax; int
0x180038aba  call    ?HResultFromNtStatus@@YAJJ@Z; HResultFromNtStatus(long)
0x180038abf  mov     ebx, eax
0x180038ac1  test    eax, eax
0x180038ac3  js      loc_180038B76
0x180038ac9  xor     eax, eax
0x180038acb  jmp     short loc_180038AD6
0x180038acd  movzx   eax, byte ptr [rbp+SystemInformation]
0x180038ad1  and     eax, 1
0x180038ad4  xor     ebx, ebx
0x180038ad6  test    eax, eax
0x180038ad8  jz      loc_180038B74
0x180038ade  mov     qword ptr [rbp+SystemInformation], 0
0x180038ae6  mov     [rbp+dwDisposition], 0
0x180038aed  lea     rcx, [rbp+SystemInformation]
0x180038af1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180038af6  lea     rcx, [rbp+dwDisposition]
0x180038afa  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x180038aff  mov     [rsp+70h+phkResult], rax; phkResult
0x180038b04  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180038b0d  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180038b15  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180038b1d  xor     r9d, r9d; lpClass
0x180038b20  xor     r8d, r8d; Reserved
0x180038b23  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180038b2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038b31  call    cs:__imp_RegCreateKeyExW
0x180038b37  mov     ebx, eax
0x180038b39  test    eax, eax
0x180038b3b  jle     short loc_180038B46
0x180038b3d  movzx   ebx, ax
0x180038b40  or      ebx, 80070000h
0x180038b46  test    ebx, ebx
0x180038b48  js      short loc_180038B6B
0x180038b4a  cmp     [rbp+dwDisposition], 2
0x180038b4e  jnz     short loc_180038B6B
0x180038b50  mov     [rbp+ReturnLength], 0
0x180038b57  lea     rcx, [rbp+ReturnLength]; int *
0x180038b5b  call    ?IsRestartRequiredForVSM@@YAJPEAH@Z; IsRestartRequiredForVSM(int *)
0x180038b60  mov     ebx, eax
0x180038b62  test    eax, eax
0x180038b64  js      short loc_180038B6B
0x180038b66  mov     eax, [rbp+ReturnLength]
0x180038b69  mov     [rdi], eax
0x180038b6b  lea     rcx, [rbp+SystemInformation]
0x180038b6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038b74  mov     eax, ebx
0x180038b76  mov     rcx, [rbp+var_8]
0x180038b7a  xor     rcx, rsp; StackCookie
0x180038b7d  call    __security_check_cookie
0x180038b82  lea     r11, [rsp+70h+var_s0]
0x180038b87  mov     rbx, [r11+18h]
0x180038b8b  mov     rdi, [r11+20h]
0x180038b8f  mov     rsp, r11
0x180038b92  pop     rbp
0x180038b93  retn
```
