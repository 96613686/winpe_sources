# wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(Windows::Internal::StateRepository::IPackageFamily *)

- ea: `0x18006ef5c`
- end: `0x18006f019`
- name: `?IsFirstPartyPackage@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackageFamily@StateRepository@Internal@Windows@@@Z`
- size: `189`
- prototype: `bool __fastcall(wpcplugs::AppRepository::StateRepo *__hidden this, struct Windows::Internal::StateRepository::IPackageFamily *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800694cc`
- `0x18006c4d0`
- `0x18006ceb0`

## callees

- `0x18006ef5c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006efc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006eff0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006efc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006eff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006efa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006efd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006efa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006efd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(
        wpcplugs::AppRepository::StateRepo *this,
        struct Windows::Internal::StateRepository::IPackageFamily *a2)
{
  void (__fastcall *v3)(wpcplugs::AppRepository::StateRepo *, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v5; // rax
  bool v6; // bl
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  string = 0;
  v3 = *(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v3(this, &string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v6 = 1;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"8wekyb3d8bbwe", -1, 0) != 2 )
  {
    v5 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(v5, -1, L"cw5n1h2txyewy", -1, 0) != 2 )
      v6 = 0;
  }
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x18006ef5c  mov     [rsp+arg_8], rbx
0x18006ef61  push    rdi
0x18006ef62  sub     rsp, 30h
0x18006ef66  mov     rdi, rcx
0x18006ef69  mov     [rsp+38h+string], 0
0x18006ef72  mov     rax, [rcx]
0x18006ef75  mov     rbx, [rax+50h]
0x18006ef79  xor     ecx, ecx; string
0x18006ef7b  call    cs:__imp_WindowsDeleteString
0x18006ef81  mov     [rsp+38h+string], 0
0x18006ef8a  lea     rdx, [rsp+38h+string]
0x18006ef8f  mov     rcx, rdi
0x18006ef92  mov     rax, rbx
0x18006ef95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef9a  xor     edx, edx; length
0x18006ef9c  mov     rcx, [rsp+38h+string]; string
0x18006efa1  call    cs:__imp_WindowsGetStringRawBuffer
0x18006efa7  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18006efaf  or      ebx, 0FFFFFFFFh
0x18006efb2  mov     r9d, ebx; cchCount2
0x18006efb5  lea     r8, String2; "8wekyb3d8bbwe"
0x18006efbc  mov     edx, ebx; cchCount1
0x18006efbe  mov     rcx, rax; lpString1
0x18006efc1  call    cs:__imp_CompareStringOrdinal
0x18006efc7  cmp     eax, 2
0x18006efca  jz      short loc_18006EFFF
0x18006efcc  xor     edx, edx; length
0x18006efce  mov     rcx, [rsp+38h+string]; string
0x18006efd3  call    cs:__imp_WindowsGetStringRawBuffer
0x18006efd9  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18006efe1  mov     r9d, ebx; cchCount2
0x18006efe4  lea     r8, aCw5n1h2txyewy; "cw5n1h2txyewy"
0x18006efeb  mov     edx, ebx; cchCount1
0x18006efed  mov     rcx, rax; lpString1
0x18006eff0  call    cs:__imp_CompareStringOrdinal
0x18006eff6  cmp     eax, 2
0x18006eff9  jz      short loc_18006EFFF
0x18006effb  xor     bl, bl
0x18006effd  jmp     short loc_18006F001
0x18006efff  mov     bl, 1
0x18006f001  mov     rcx, [rsp+38h+string]; string
0x18006f006  call    cs:__imp_WindowsDeleteString
0x18006f00c  mov     al, bl
0x18006f00e  mov     rbx, [rsp+38h+arg_8]
0x18006f013  add     rsp, 30h
0x18006f017  pop     rdi
0x18006f018  retn
```
