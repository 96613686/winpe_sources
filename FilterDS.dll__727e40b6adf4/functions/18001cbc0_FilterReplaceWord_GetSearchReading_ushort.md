# FilterReplaceWord::GetSearchReading(ushort * *)

- ea: `0x18001cbc0`
- end: `0x18001cc83`
- name: `?GetSearchReading@FilterReplaceWord@@UEAAJPEAPEAG@Z`
- size: `195`
- prototype: `__int64 __fastcall(FilterReplaceWord *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000cde4`
- `0x18001c62c`
- `0x18001cbc0`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc5f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001cc4b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001cc4b`

## pseudocode

```c
__int64 __fastcall FilterReplaceWord::GetSearchReading(FilterReplaceWord *this, unsigned __int16 **a2)
{
  void **v2; // rdi
  __int64 v4; // rax
  const OLECHAR *v6; // rcx
  unsigned __int16 *v7; // rax
  bool v8; // cf
  __int16 v9; // [rsp+20h] [rbp-30h] BYREF
  OLECHAR *strIn[2]; // [rsp+28h] [rbp-28h] BYREF
  UINT ui[2]; // [rsp+38h] [rbp-18h]
  unsigned __int64 v12; // [rsp+40h] [rbp-10h]

  v2 = (void **)((char *)this + 8);
  *a2 = 0;
  v9 = -2;
  v4 = std::wstring::find((char *)this + 8, &v9);
  if ( v4 == -1 )
    return 1;
  v12 = 7;
  *(_QWORD *)ui = 0;
  LOWORD(strIn[0]) = 0;
  std::wstring::assign((void **)strIn, v2, v4 + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v6 = (const OLECHAR *)strIn;
  if ( v12 >= 8 )
    v6 = strIn[0];
  v7 = SysAllocStringLen(v6, ui[0]);
  v8 = v12 < 8;
  *a2 = v7;
  if ( !v8 )
    operator delete(strIn[0]);
  return 0;
}

```

## disassembly

```asm
0x18001cbc0  mov     [rsp-8+arg_10], rbx
0x18001cbc5  mov     [rsp-8+arg_18], rdi
0x18001cbca  push    rbp
0x18001cbcb  mov     rbp, rsp
0x18001cbce  sub     rsp, 50h
0x18001cbd2  mov     rax, cs:__security_cookie
0x18001cbd9  xor     rax, rsp
0x18001cbdc  mov     [rbp+var_8], rax
0x18001cbe0  lea     rdi, [rcx+8]
0x18001cbe4  mov     qword ptr [rdx], 0
0x18001cbeb  mov     rbx, rdx
0x18001cbee  mov     eax, 0FFFEh
0x18001cbf3  mov     rcx, rdi
0x18001cbf6  mov     [rbp+var_30], ax
0x18001cbfa  lea     rdx, [rbp+var_30]
0x18001cbfe  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18001cc03  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cc07  mov     r8, rax
0x18001cc0a  cmp     rax, r9
0x18001cc0d  jnz     short loc_18001CC15
0x18001cc0f  lea     eax, [r9+2]
0x18001cc13  jmp     short loc_18001CC67
0x18001cc15  xor     eax, eax
0x18001cc17  mov     [rbp+var_10], 7
0x18001cc1f  inc     r8
0x18001cc22  mov     qword ptr [rbp+ui], 0
0x18001cc2a  mov     rdx, rdi
0x18001cc2d  mov     word ptr [rbp+strIn], ax
0x18001cc31  lea     rcx, [rbp+strIn]; void *
0x18001cc35  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001cc3a  cmp     [rbp+var_10], 8
0x18001cc3f  lea     rcx, [rbp+strIn]
0x18001cc43  mov     edx, [rbp+ui]; ui
0x18001cc46  cmovnb  rcx, [rbp+strIn]; strIn
0x18001cc4b  call    cs:__imp_SysAllocStringLen
0x18001cc51  cmp     [rbp+var_10], 8
0x18001cc56  mov     [rbx], rax
0x18001cc59  jb      short loc_18001CC65
0x18001cc5b  mov     rcx, [rbp+strIn]
0x18001cc5f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cc65  xor     eax, eax
0x18001cc67  mov     rcx, [rbp+var_8]
0x18001cc6b  xor     rcx, rsp; StackCookie
0x18001cc6e  call    __security_check_cookie
0x18001cc73  mov     rbx, [rsp+50h+arg_10]
0x18001cc78  mov     rdi, [rsp+50h+arg_18]
0x18001cc7d  add     rsp, 50h
0x18001cc81  pop     rbp
0x18001cc82  retn
```
