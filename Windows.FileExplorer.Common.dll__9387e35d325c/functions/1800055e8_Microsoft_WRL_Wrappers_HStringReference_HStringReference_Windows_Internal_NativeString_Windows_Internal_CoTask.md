# Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800055e8`
- end: `0x180005670`
- name: `??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z`
- size: `136`
- prototype: `__int64 __fastcall(HSTRING_HEADER *hstringHeader)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d188`

## callees

- `0x1800055e8`
- `0x180006c54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005656`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005669`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005656`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000562f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000562f`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const WCHAR **a2)
{
  unsigned __int64 v3; // rbx
  const WCHAR *v4; // rsi
  unsigned int v5; // eax
  UINT32 v6; // edx
  HRESULT StringReference; // eax

  hstringHeader[1].Reserved.Reserved1 = 0;
  v3 = -1;
  v4 = *a2;
  do
    ++v3;
  while ( v4[v3] );
  if ( v3 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v5 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v3);
  v6 = v5 - 1;
  if ( (unsigned int)v3 < v5 )
    v6 = v3;
  StringReference = WindowsCreateStringReference(v4, v6, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x18000566FLL);
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x1800055e8  push    rbx
0x1800055ea  push    rbp
0x1800055eb  push    rsi
0x1800055ec  push    rdi
0x1800055ed  push    r14
0x1800055ef  sub     rsp, 20h
0x1800055f3  xor     ebp, ebp
0x1800055f5  mov     rdi, rcx
0x1800055f8  mov     [rcx+18h], rbp
0x1800055fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005600  mov     rsi, [rdx]
0x180005603  inc     rbx
0x180005606  cmp     [rsi+rbx*2], bp
0x18000560a  jnz     short loc_180005603
0x18000560c  mov     eax, 0FFFFFFFFh
0x180005611  cmp     rbx, rax
0x180005614  ja      short loc_180005647
0x180005616  mov     ecx, ebx; unsigned int
0x180005618  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000561d  cmp     ebx, eax
0x18000561f  lea     r9, [rdi+18h]; string
0x180005623  mov     r8, rdi; hstringHeader
0x180005626  mov     rcx, rsi; sourceString
0x180005629  lea     edx, [rax-1]
0x18000562c  cmovb   edx, ebx; length
0x18000562f  call    cs:__imp_WindowsCreateStringReference
0x180005635  test    eax, eax
0x180005637  js      short loc_18000565D
0x180005639  mov     rax, rdi
0x18000563c  add     rsp, 20h
0x180005640  pop     r14
0x180005642  pop     rdi
0x180005643  pop     rsi
0x180005644  pop     rbp
0x180005645  pop     rbx
0x180005646  retn
0x180005647  xor     r9d, r9d; lpArguments
0x18000564a  xor     r8d, r8d; nNumberOfArguments
0x18000564d  mov     ecx, 80070216h; dwExceptionCode
0x180005652  lea     edx, [r9+1]; dwExceptionFlags
0x180005656  call    cs:__imp_RaiseException
0x18000565c  int     3; Trap to Debugger
0x18000565d  xor     r9d, r9d; lpArguments
0x180005660  xor     r8d, r8d; nNumberOfArguments
0x180005663  mov     ecx, eax; dwExceptionCode
0x180005665  lea     edx, [r9+1]; dwExceptionFlags
0x180005669  call    cs:__imp_RaiseException
```
