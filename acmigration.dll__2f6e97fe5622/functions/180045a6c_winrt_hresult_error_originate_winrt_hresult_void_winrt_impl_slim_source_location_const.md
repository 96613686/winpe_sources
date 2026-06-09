# winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)

- ea: `0x180045a6c`
- end: `0x180045bae`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z`
- size: `322`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003db8c`
- `0x18003dc48`
- `0x18003df8c`
- `0x18006872b`
- `0x18006881b`
- `0x18006890b`

## callees

- `0x180002aaf`
- `0x180002fa7`
- `0x18000a110`
- `0x180045a6c`
- `0x18006a010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180045ab0`
- `KERNEL32!LoadLibraryExW` at `0x180045ab0`

## string_xrefs

- `0x180045aa9`: `combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall winrt::hresult_error::originate(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  __int64 *v10; // rbx
  __int64 v11; // rdi
  __int64 *result; // rax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+38h] [rbp-18h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  IErrorInfo *pperrinfo; // [rsp+70h] [rbp+20h] BYREF

  v14[1] = -2;
  ProcAddress = (FARPROC)`winrt::impl::downlevel::runtime_RoOriginateLanguageException'::`2'::handler;
  if ( !`winrt::impl::downlevel::runtime_RoOriginateLanguageException'::`2'::handler )
  {
    Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "RoOriginateLanguageException");
    `winrt::impl::downlevel::runtime_RoOriginateLanguageException'::`2'::handler = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)winrt::impl::downlevel::fallback_RoOriginateLanguageException;
      `winrt::impl::downlevel::runtime_RoOriginateLanguageException'::`2'::handler = (__int64)winrt::impl::downlevel::fallback_RoOriginateLanguageException;
    }
  }
  ((void (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(a2, a3, 0);
  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(*a4, *((_QWORD *)a4 + 1), *((_QWORD *)a4 + 2), retaddr, a2);
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v10 = (__int64 *)(a1 + 16);
  if ( pperrinfo )
  {
    v14[0] = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, _QWORD *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      &winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      v14);
    v11 = v14[0];
    v13 = v14[0];
  }
  else
  {
    v13 = 0;
    v11 = 0;
  }
  result = &v13;
  if ( v10 == &v13 )
  {
    if ( v11 )
      result = (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  }
  else
  {
    if ( *v10 )
      result = (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 16);
    *v10 = v11;
  }
  if ( pperrinfo )
    return (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return result;
}

```

## disassembly

```asm
0x180045a6c  mov     rax, rsp
0x180045a6f  push    rbp
0x180045a70  push    rdi
0x180045a71  push    r14
0x180045a73  mov     rbp, rsp
0x180045a76  sub     rsp, 50h
0x180045a7a  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180045a82  mov     [rax+10h], rbx
0x180045a86  mov     [rax+18h], rsi
0x180045a8a  mov     rdi, r9
0x180045a8d  mov     r14, r8
0x180045a90  mov     ebx, edx
0x180045a92  mov     rsi, rcx
0x180045a95  mov     rax, cs:?handler@?1??runtime_RoOriginateLanguageException@downlevel@impl@winrt@@YAHHPEAX0@Z@4P6AHH00@_EEA
0x180045a9c  test    rax, rax
0x180045a9f  jnz     short loc_180045ADF
0x180045aa1  xor     edx, edx; hFile
0x180045aa3  mov     r8d, 800h; dwFlags
0x180045aa9  lea     rcx, LibFileName; "combase.dll"
0x180045ab0  call    cs:__imp_LoadLibraryExW
0x180045ab6  mov     rcx, rax; hModule
0x180045ab9  lea     rdx, aRooriginatelan; "RoOriginateLanguageException"
0x180045ac0  call    WINRT_IMPL_GetProcAddress
0x180045ac5  mov     cs:?handler@?1??runtime_RoOriginateLanguageException@downlevel@impl@winrt@@YAHHPEAX0@Z@4P6AHH00@_EEA, rax
0x180045acc  test    rax, rax
0x180045acf  jnz     short loc_180045ADF
0x180045ad1  lea     rax, ?fallback_RoOriginateLanguageException@downlevel@impl@winrt@@YAHHPEAX0@Z; winrt::impl::downlevel::fallback_RoOriginateLanguageException(int,void *,void *)
0x180045ad8  mov     cs:?handler@?1??runtime_RoOriginateLanguageException@downlevel@impl@winrt@@YAHHPEAX0@Z@4P6AHH00@_EEA, rax
0x180045adf  xor     r8d, r8d
0x180045ae2  mov     rdx, r14
0x180045ae5  mov     ecx, ebx
0x180045ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aec  nop
0x180045aed  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180045af4  test    rax, rax
0x180045af7  jz      short loc_180045B10
0x180045af9  mov     r9, [rbp+18h]
0x180045afd  mov     [rsp+50h+var_30], ebx
0x180045b01  mov     r8, [rdi+10h]
0x180045b05  mov     rdx, [rdi+8]
0x180045b09  mov     ecx, [rdi]
0x180045b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b10  mov     [rbp+pperrinfo], 0
0x180045b18  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180045b1c  xor     ecx, ecx; dwReserved
0x180045b1e  call    GetErrorInfo_0
0x180045b23  lea     rbx, [rsi+10h]
0x180045b27  mov     rcx, [rbp+pperrinfo]
0x180045b2b  test    rcx, rcx
0x180045b2e  jnz     short loc_180045B38
0x180045b30  mov     [rbp+var_20], rcx
0x180045b34  xor     edi, edi
0x180045b36  jmp     short loc_180045B5E
0x180045b38  mov     [rbp+var_18], 0
0x180045b40  mov     rax, [rcx]
0x180045b43  lea     r8, [rbp+var_18]
0x180045b47  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180045b4e  mov     rax, [rax]
0x180045b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b56  mov     rdi, [rbp+var_18]
0x180045b5a  mov     [rbp+var_20], rdi
0x180045b5e  lea     rax, [rbp+var_20]
0x180045b62  cmp     rbx, rax
0x180045b65  jz      short loc_180045B7A
0x180045b67  cmp     qword ptr [rbx], 0
0x180045b6b  jz      short loc_180045B75
0x180045b6d  mov     rcx, rbx
0x180045b70  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180045b75  mov     [rbx], rdi
0x180045b78  jmp     short loc_180045B88
0x180045b7a  test    rdi, rdi
0x180045b7d  jz      short loc_180045B88
0x180045b7f  lea     rcx, [rbp+var_20]
0x180045b83  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180045b88  cmp     [rbp+pperrinfo], 0
0x180045b8d  jz      short loc_180045B99
0x180045b8f  lea     rcx, [rbp+pperrinfo]
0x180045b93  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180045b98  nop
0x180045b99  lea     r11, [rsp+50h+var_s0]
0x180045b9e  mov     rbx, [r11+28h]
0x180045ba2  mov     rsi, [r11+30h]
0x180045ba6  mov     rsp, r11
0x180045ba9  pop     r14
0x180045bab  pop     rdi
0x180045bac  pop     rbp
0x180045bad  retn
```
