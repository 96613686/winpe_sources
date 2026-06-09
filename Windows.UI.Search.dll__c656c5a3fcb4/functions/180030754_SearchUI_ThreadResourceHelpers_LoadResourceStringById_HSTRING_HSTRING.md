# SearchUI::ThreadResourceHelpers::LoadResourceStringById(HSTRING__ *,HSTRING__ * *)

- ea: `0x180030754`
- end: `0x180030803`
- name: `?LoadResourceStringById@ThreadResourceHelpers@SearchUI@@YAJPEAUHSTRING__@@PEAPEAU3@@Z`
- size: `175`
- prototype: `int(SearchUI::ThreadResourceHelpers *__hidden this, HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800766e0`
- `0x1800767ac`

## callees

- `0x1800120dc`
- `0x180015ab8`
- `0x180030754`
- `0x18003080c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800307dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800307dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SearchUI::ThreadResourceHelpers::LoadResourceStringById(
        SearchUI::ThreadResourceHelpers *this,
        HSTRING *a2,
        HSTRING *a3)
{
  SearchUI::ThreadResourceHelpers *StringRawBuffer; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int16 **v6; // r8
  HRESULT ResourceStringById; // ebx
  const WCHAR *v8; // r9
  unsigned __int16 v10[4]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  UINT32 length; // [rsp+68h] [rbp+28h] BYREF

  *a2 = 0;
  StringRawBuffer = (SearchUI::ThreadResourceHelpers *)WindowsGetStringRawBuffer((HSTRING)this, 0);
  *(_QWORD *)v10 = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v10);
  v5 = -1;
  v11 = -1;
  v12 = -1;
  ResourceStringById = SearchUI::ThreadResourceHelpers::LoadResourceStringById(StringRawBuffer, v10, v6);
  if ( ResourceStringById >= 0 )
  {
    length = 0;
    do
      ++v5;
    while ( *(_WORD *)(*(_QWORD *)v10 + 2 * v5) );
    ResourceStringById = ULongLongToULong(v5, &length);
    if ( ResourceStringById >= 0 )
      ResourceStringById = WindowsCreateString(v8, length, a2);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v10);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x180030754  mov     [rsp-18h+arg_0], rbx
0x180030759  mov     [rsp-18h+arg_10], rsi
0x18003075e  push    rbp
0x18003075f  push    rdi
0x180030760  push    r14
0x180030762  mov     rbp, rsp
0x180030765  sub     rsp, 40h
0x180030769  mov     rsi, rdx
0x18003076c  xor     r14d, r14d
0x18003076f  mov     [rdx], r14
0x180030772  xor     edx, edx; length
0x180030774  call    cs:__imp_WindowsGetStringRawBuffer
0x18003077a  mov     rbx, rax
0x18003077d  mov     qword ptr [rbp+var_20], r14
0x180030781  mov     [rbp+var_18], r14
0x180030785  mov     [rbp+var_10], r14
0x180030789  lea     rcx, [rbp+var_20]
0x18003078d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030792  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180030796  mov     [rbp+var_18], rdi
0x18003079a  mov     [rbp+var_10], rdi
0x18003079e  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x1800307a2  mov     rcx, rbx; this
0x1800307a5  call    ?LoadResourceStringById@ThreadResourceHelpers@SearchUI@@YAJPEBGPEAPEAG@Z; SearchUI::ThreadResourceHelpers::LoadResourceStringById(ushort const *,ushort * *)
0x1800307aa  mov     ebx, eax
0x1800307ac  test    eax, eax
0x1800307ae  js      short loc_1800307E5
0x1800307b0  mov     [rbp+length], r14d
0x1800307b4  mov     r9, qword ptr [rbp+var_20]
0x1800307b8  inc     rdi
0x1800307bb  cmp     [r9+rdi*2], r14w
0x1800307c0  jnz     short loc_1800307B8
0x1800307c2  lea     rdx, [rbp+length]; unsigned int *
0x1800307c6  mov     rcx, rdi; unsigned __int64
0x1800307c9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800307ce  mov     ebx, eax
0x1800307d0  test    eax, eax
0x1800307d2  js      short loc_1800307E5
0x1800307d4  mov     r8, rsi; string
0x1800307d7  mov     edx, [rbp+length]; length
0x1800307da  mov     rcx, r9; sourceString
0x1800307dd  call    cs:__imp_WindowsCreateString
0x1800307e3  mov     ebx, eax
0x1800307e5  lea     rcx, [rbp+var_20]
0x1800307e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800307ee  mov     eax, ebx
0x1800307f0  mov     rbx, [rsp+40h+arg_0]
0x1800307f5  mov     rsi, [rsp+40h+arg_10]
0x1800307fa  add     rsp, 40h
0x1800307fe  pop     r14
0x180030800  pop     rdi
0x180030801  pop     rbp
0x180030802  retn
```
