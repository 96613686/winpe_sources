# winrt::hresult_error::originate(winrt::hresult,void *)

- ea: `0x1800356d0`
- end: `0x1800357f5`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z`
- size: `293`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034bc4`
- `0x1800357fc`
- `0x18004737c`
- `0x1800476a4`
- `0x18005f037`
- `0x18005f10d`
- `0x18005f1e3`

## callees

- `0x18002d1a4`
- `0x1800356d0`
- `0x180056161`
- `0x180056500`
- `0x18005c49e`
- `0x18005c4aa`
- `0x18005c5e0`

## string_xrefs

- `0x180035701`: `combase.dll`

## pseudocode

```c
IErrorInfo *__fastcall winrt::hresult_error::originate(__int64 a1, unsigned int a2, __int64 a3)
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW_0; // rax
  __int64 *v8; // rbx
  IErrorInfo *result; // rax
  __int64 v10; // rdi
  __int64 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp-10h] BYREF

  ProcAddress = (FARPROC)`winrt::hresult_error::originate'::`2'::handler;
  if ( !`winrt::hresult_error::originate'::`2'::handler )
  {
    LibraryW_0 = LoadLibraryW_0(L"combase.dll");
    ProcAddress = WINRT_IMPL_GetProcAddress(LibraryW_0, "RoOriginateLanguageException");
    `winrt::hresult_error::originate'::`2'::handler = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)winrt::hresult_error::fallback_RoOriginateLanguageException;
      `winrt::hresult_error::originate'::`2'::handler = (__int64)winrt::hresult_error::fallback_RoOriginateLanguageException;
    }
  }
  ((void (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(a2, a3, 0);
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v8 = (__int64 *)(a1 + 16);
  result = pperrinfo;
  if ( pperrinfo )
  {
    v12 = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      &winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &v12);
    v10 = v12;
    v11 = v12;
    result = pperrinfo;
  }
  else
  {
    v11 = 0;
    v10 = 0;
  }
  if ( v8 == &v11 )
  {
    if ( v10 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
      result = pperrinfo;
    }
  }
  else
  {
    if ( *v8 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
      result = pperrinfo;
    }
    *v8 = v10;
  }
  if ( result )
    return (IErrorInfo *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return result;
}

```

## disassembly

```asm
0x1800356d0  mov     [rsp-18h+arg_8], rbx
0x1800356d5  push    rbp
0x1800356d6  push    rsi
0x1800356d7  push    rdi
0x1800356d8  mov     rbp, rsp
0x1800356db  sub     rsp, 40h
0x1800356df  mov     rax, cs:__security_cookie
0x1800356e6  xor     rax, rsp
0x1800356e9  mov     [rbp+var_8], rax
0x1800356ed  mov     rsi, r8
0x1800356f0  mov     ebx, edx
0x1800356f2  mov     rdi, rcx
0x1800356f5  mov     rax, cs:?handler@?1??originate@hresult_error@winrt@@AEAAXUhresult@3@PEAX@Z@4P6AHH11@_EEA
0x1800356fc  test    rax, rax
0x1800356ff  jnz     short loc_180035736
0x180035701  lea     rcx, LibFileName; "combase.dll"
0x180035708  call    LoadLibraryW_0
0x18003570d  mov     rcx, rax; hModule
0x180035710  lea     rdx, aRooriginatelan; "RoOriginateLanguageException"
0x180035717  call    WINRT_IMPL_GetProcAddress
0x18003571c  mov     cs:?handler@?1??originate@hresult_error@winrt@@AEAAXUhresult@3@PEAX@Z@4P6AHH11@_EEA, rax
0x180035723  test    rax, rax
0x180035726  jnz     short loc_180035736
0x180035728  lea     rax, ?fallback_RoOriginateLanguageException@hresult_error@winrt@@CAHHPEAX0@Z; winrt::hresult_error::fallback_RoOriginateLanguageException(int,void *,void *)
0x18003572f  mov     cs:?handler@?1??originate@hresult_error@winrt@@AEAAXUhresult@3@PEAX@Z@4P6AHH11@_EEA, rax
0x180035736  xor     r8d, r8d
0x180035739  mov     rdx, rsi
0x18003573c  mov     ecx, ebx
0x18003573e  call    _guard_dispatch_icall
0x180035743  mov     [rbp+pperrinfo], 0
0x18003574b  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18003574f  xor     ecx, ecx; dwReserved
0x180035751  call    GetErrorInfo_0
0x180035756  lea     rbx, [rdi+10h]
0x18003575a  mov     rax, [rbp+pperrinfo]
0x18003575e  test    rax, rax
0x180035761  jnz     short loc_18003576B
0x180035763  mov     [rbp+var_20], rax
0x180035767  xor     edi, edi
0x180035769  jmp     short loc_18003579B
0x18003576b  mov     [rbp+var_18], 0
0x180035773  mov     rcx, [rax]
0x180035776  mov     r9, [rcx]
0x180035779  lea     r8, [rbp+var_18]
0x18003577d  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180035784  mov     rcx, rax
0x180035787  mov     rax, r9
0x18003578a  call    _guard_dispatch_icall
0x18003578f  mov     rdi, [rbp+var_18]
0x180035793  mov     [rbp+var_20], rdi
0x180035797  mov     rax, [rbp+pperrinfo]
0x18003579b  lea     rcx, [rbp+var_20]
0x18003579f  cmp     rbx, rcx
0x1800357a2  jz      short loc_1800357BB
0x1800357a4  cmp     qword ptr [rbx], 0
0x1800357a8  jz      short loc_1800357B6
0x1800357aa  mov     rcx, rbx
0x1800357ad  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800357b2  mov     rax, [rbp+pperrinfo]
0x1800357b6  mov     [rbx], rdi
0x1800357b9  jmp     short loc_1800357CD
0x1800357bb  test    rdi, rdi
0x1800357be  jz      short loc_1800357CD
0x1800357c0  lea     rcx, [rbp+var_20]
0x1800357c4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800357c9  mov     rax, [rbp+pperrinfo]
0x1800357cd  test    rax, rax
0x1800357d0  jz      short loc_1800357DC
0x1800357d2  lea     rcx, [rbp+pperrinfo]
0x1800357d6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800357db  nop
0x1800357dc  mov     rcx, [rbp+var_8]
0x1800357e0  xor     rcx, rsp; StackCookie
0x1800357e3  call    __security_check_cookie
0x1800357e8  mov     rbx, [rsp+40h+arg_8]
0x1800357ed  add     rsp, 40h
0x1800357f1  pop     rdi
0x1800357f2  pop     rsi
0x1800357f3  pop     rbp
0x1800357f4  retn
```
