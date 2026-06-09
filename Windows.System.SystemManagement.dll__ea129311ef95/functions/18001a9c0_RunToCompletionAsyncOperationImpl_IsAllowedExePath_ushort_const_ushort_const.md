# RunToCompletionAsyncOperationImpl::IsAllowedExePath(ushort const *,ushort const *)

- ea: `0x18001a9c0`
- end: `0x18001aab8`
- name: `?IsAllowedExePath@RunToCompletionAsyncOperationImpl@@AEAAHPEBG0@Z`
- size: `248`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001bad0`

## callees

- `0x1800032b0`
- `0x180016080`
- `0x18001a580`
- `0x18001a9c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001aa3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001aa3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001aaa4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001aaa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aa05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aa05`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RunToCompletionAsyncOperationImpl::IsAllowedExePath(
        RunToCompletionAsyncOperationImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // esi
  LSTATUS v6; // eax
  RunToCompletionAsyncOperationImpl *v7; // rcx
  bool v8; // sf
  unsigned __int16 **RegMultiSz; // rax
  unsigned __int16 **v10; // rdi
  unsigned __int16 **i; // rbx
  void *v12; // rcx
  int LastError; // eax
  void **v15; // [rsp+30h] [rbp-38h] BYREF
  HKEY v16; // [rsp+38h] [rbp-30h] BYREF

  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  v16 = 0;
  v5 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EmbeddedMode\\ProcessLauncher",
         0,
         1u,
         &v16);
  v8 = v6 < 0;
  if ( v6 > 0 )
    v8 = 1;
  if ( !v8 )
  {
    RegMultiSz = RunToCompletionAsyncOperationImpl::GetRegMultiSz(v7, v16, a3);
    v10 = RegMultiSz;
    if ( RegMultiSz )
    {
      for ( i = RegMultiSz; *i; ++i )
      {
        if ( !(unsigned int)_o__wcsicmp(*i, a2) )
        {
          v5 = 1;
          break;
        }
      }
      v12 = *(v10 - 1);
      if ( v12 )
        operator delete(v12);
      operator delete(v10 - 1);
    }
  }
  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  if ( v16
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(&v15) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return v5;
}

```

## disassembly

```asm
0x18001a9c0  mov     r11, rsp
0x18001a9c3  push    rbx
0x18001a9c4  push    rbp
0x18001a9c5  push    rsi
0x18001a9c6  push    rdi
0x18001a9c7  push    r12
0x18001a9c9  sub     rsp, 40h
0x18001a9cd  mov     rbx, r8
0x18001a9d0  mov     rbp, rdx
0x18001a9d3  lea     r12, ??_7?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable'
0x18001a9da  mov     [r11-38h], r12
0x18001a9de  mov     qword ptr [r11-30h], 0
0x18001a9e6  xor     esi, esi
0x18001a9e8  lea     rax, [r11-30h]
0x18001a9ec  mov     [r11-48h], rax
0x18001a9f0  lea     r9d, [rsi+1]; samDesired
0x18001a9f4  xor     r8d, r8d; ulOptions
0x18001a9f7  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a9fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001aa05  call    cs:__imp_RegOpenKeyExW
0x18001aa0b  test    eax, eax
0x18001aa0d  jle     short loc_18001AA19
0x18001aa0f  movzx   eax, ax
0x18001aa12  or      eax, 80070000h
0x18001aa17  test    eax, eax
0x18001aa19  js      short loc_18001AA6B
0x18001aa1b  mov     r8, rbx; unsigned __int16 *
0x18001aa1e  mov     rdx, [rsp+68h+var_30]; HKEY
0x18001aa23  call    ?GetRegMultiSz@RunToCompletionAsyncOperationImpl@@AEAAPEAPEAGPEAUHKEY__@@PEBG@Z; RunToCompletionAsyncOperationImpl::GetRegMultiSz(HKEY__ *,ushort const *)
0x18001aa28  mov     rdi, rax
0x18001aa2b  test    rax, rax
0x18001aa2e  jz      short loc_18001AA6B
0x18001aa30  mov     rbx, rax
0x18001aa33  mov     rcx, [rbx]
0x18001aa36  test    rcx, rcx
0x18001aa39  jz      short loc_18001AA53
0x18001aa3b  mov     rdx, rbp
0x18001aa3e  call    cs:__imp__o__wcsicmp
0x18001aa44  test    eax, eax
0x18001aa46  jz      short loc_18001AA4E
0x18001aa48  add     rbx, 8
0x18001aa4c  jmp     short loc_18001AA33
0x18001aa4e  mov     esi, 1
0x18001aa53  mov     rcx, [rdi-8]; Block
0x18001aa57  test    rcx, rcx
0x18001aa5a  jz      short loc_18001AA61
0x18001aa5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa61  lea     rcx, [rdi-8]; Block
0x18001aa65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa6a  nop
0x18001aa6b  mov     [rsp+68h+var_38], r12
0x18001aa70  cmp     [rsp+68h+var_30], 0
0x18001aa76  jz      short loc_18001AAAB
0x18001aa78  lea     rcx, [rsp+68h+var_38]
0x18001aa7d  call    ?InternalClose@?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(void)
0x18001aa82  test    al, al
0x18001aa84  jnz     short loc_18001AAAB
0x18001aa86  call    cs:__imp_GetLastError
0x18001aa8c  test    eax, eax
0x18001aa8e  jle     short loc_18001AA98
0x18001aa90  movzx   eax, ax
0x18001aa93  or      eax, 80070000h
0x18001aa98  xor     r9d, r9d; lpArguments
0x18001aa9b  xor     r8d, r8d; nNumberOfArguments
0x18001aa9e  lea     edx, [r9+1]; dwExceptionFlags
0x18001aaa2  mov     ecx, eax; dwExceptionCode
0x18001aaa4  call    cs:__imp_RaiseException
0x18001aaaa  int     3; Trap to Debugger
0x18001aaab  mov     eax, esi
0x18001aaad  add     rsp, 40h
0x18001aab1  pop     r12
0x18001aab3  pop     rdi
0x18001aab4  pop     rsi
0x18001aab5  pop     rbp
0x18001aab6  pop     rbx
0x18001aab7  retn
```
