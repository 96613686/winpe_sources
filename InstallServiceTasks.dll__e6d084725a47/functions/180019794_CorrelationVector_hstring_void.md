# CorrelationVector::hstring(void)

- ea: `0x180019794`
- end: `0x18001984a`
- name: `?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ`
- size: `182`
- prototype: `HSTRING __fastcall(CorrelationVector *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180016044`
- `0x180020a1c`
- `0x180030434`

## callees

- `0x180003450`
- `0x180010150`
- `0x180019794`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800197d3`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800197d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800197ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800197ff`

## string_xrefs

- `0x180019811`: `onecoreuap\enduser\winstore\installservice\lib\CorrelationVector.h`

## pseudocode

```c
HSTRING __fastcall CorrelationVector::hstring(CorrelationVector *this)
{
  HSTRING *v1; // rbx
  HSTRING result; // rax
  __int64 v3; // rdx
  HRESULT String; // eax
  WCHAR sourceString[136]; // [rsp+20h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v1 = (HSTRING *)((char *)this + 144);
  result = (HSTRING)*((_QWORD *)this + 18);
  if ( !result )
  {
    _o_mbstowcs(sourceString, (char *)this + 8, 129);
    WindowsDeleteString(*v1);
    *v1 = 0;
    v3 = -1;
    do
      ++v3;
    while ( sourceString[v3] );
    String = WindowsCreateString(sourceString, v3, v1);
    if ( String < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\CorrelationVector.h",
        (const char *)(unsigned int)String,
        *(int *)sourceString);
    return *v1;
  }
  return result;
}

```

## disassembly

```asm
0x180019794  mov     [rsp+arg_8], rbx
0x180019799  push    rdi
0x18001979a  sub     rsp, 140h
0x1800197a1  mov     rax, cs:__security_cookie
0x1800197a8  xor     rax, rsp
0x1800197ab  mov     [rsp+148h+var_18], rax
0x1800197b3  lea     rbx, [rcx+90h]
0x1800197ba  xor     edi, edi
0x1800197bc  mov     rax, [rbx]
0x1800197bf  test    rax, rax
0x1800197c2  jnz     short loc_180019829
0x1800197c4  lea     rdx, [rcx+8]
0x1800197c8  mov     r8d, 81h
0x1800197ce  lea     rcx, [rsp+148h+sourceString]
0x1800197d3  call    cs:__imp__o_mbstowcs
0x1800197d9  mov     rcx, [rbx]; string
0x1800197dc  call    cs:__imp_WindowsDeleteString
0x1800197e2  lea     rax, [rsp+148h+sourceString]
0x1800197e7  mov     [rbx], rdi
0x1800197ea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800197ee  inc     rdx; length
0x1800197f1  cmp     [rax+rdx*2], di
0x1800197f5  jnz     short loc_1800197EE
0x1800197f7  mov     r8, rbx; string
0x1800197fa  lea     rcx, [rsp+148h+sourceString]; sourceString
0x1800197ff  call    cs:__imp_WindowsCreateString
0x180019805  test    eax, eax
0x180019807  jns     short loc_180019826
0x180019809  mov     rcx, [rsp+148h]; this
0x180019811  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\installs"...
0x180019818  mov     r9d, eax; char *
0x18001981b  mov     edx, 5Ah ; 'Z'; void *
0x180019820  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019826  mov     rax, [rbx]
0x180019829  mov     rcx, [rsp+148h+var_18]
0x180019831  xor     rcx, rsp; StackCookie
0x180019834  call    __security_check_cookie
0x180019839  mov     rbx, [rsp+148h+arg_8]
0x180019841  add     rsp, 140h
0x180019848  pop     rdi
0x180019849  retn
```
