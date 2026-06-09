# wil::make_bstr(wchar_t const *)

- ea: `0x18002f478`
- end: `0x18002f4cb`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800140d4`
- `0x1800142a4`
- `0x1800143e8`

## callees

- `0x18002f454`
- `0x18002f478`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002f495`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f495`

## string_xrefs

- `0x18002f4b9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall wil::make_bstr(BSTR *a1, const OLECHAR *a2)
{
  BSTR v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v3 = SysAllocString(a2);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  return a1;
}

```

## disassembly

```asm
0x18002f478  mov     [rsp+arg_0], rcx
0x18002f47d  push    rbx
0x18002f47e  sub     rsp, 30h
0x18002f482  mov     rbx, rcx
0x18002f485  mov     [rsp+38h+var_18], 0
0x18002f48d  xor     eax, eax
0x18002f48f  mov     [rcx], rax
0x18002f492  mov     rcx, rdx; psz
0x18002f495  call    cs:__imp_SysAllocString
0x18002f49b  mov     [rbx], rax
0x18002f49e  mov     [rsp+38h+var_18], 1
0x18002f4a6  test    rax, rax
0x18002f4a9  jz      short loc_18002F4B4
0x18002f4ab  mov     rax, rbx
0x18002f4ae  add     rsp, 30h
0x18002f4b2  pop     rbx
0x18002f4b3  retn
0x18002f4b4  mov     rcx, [rsp+38h]; this
0x18002f4b9  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002f4c0  mov     edx, 138Dh; void *
0x18002f4c5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
