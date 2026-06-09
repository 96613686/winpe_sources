# EnvironmentDefaultImpl::get_MsaBinaryVersion(HSTRING__ * *)

- ea: `0x18003d260`
- end: `0x18003d2a6`
- name: `?get_MsaBinaryVersion@EnvironmentDefaultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `70`
- prototype: `int(EnvironmentDefaultImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800153f8`
- `0x18003d260`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d275`

## string_xrefs

- `0x18003d286`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_MsaBinaryVersion(EnvironmentDefaultImpl *this, HSTRING *a2)
{
  HRESULT String; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  String = WindowsCreateString(L"60", 2u, a2);
  v3 = String;
  if ( String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC4,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
    (const char *)(unsigned int)String,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18003d260  push    rbx; int
0x18003d262  sub     rsp, 20h
0x18003d266  mov     r8, rdx; string
0x18003d269  lea     rcx, a60; "60"
0x18003d270  mov     edx, 2; length
0x18003d275  call    cs:__imp_WindowsCreateString
0x18003d27b  mov     ebx, eax
0x18003d27d  test    eax, eax
0x18003d27f  jns     short loc_18003D29E
0x18003d281  mov     rcx, [rsp+28h]; this
0x18003d286  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d28d  mov     r9d, eax; char *
0x18003d290  mov     edx, 0C4h; void *
0x18003d295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d29a  mov     eax, ebx
0x18003d29c  jmp     short loc_18003D2A0
0x18003d29e  xor     eax, eax
0x18003d2a0  add     rsp, 20h
0x18003d2a4  pop     rbx
0x18003d2a5  retn
```
