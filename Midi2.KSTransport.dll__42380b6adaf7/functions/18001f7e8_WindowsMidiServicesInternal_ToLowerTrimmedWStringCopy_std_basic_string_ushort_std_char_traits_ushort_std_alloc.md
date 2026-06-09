# WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001f7e8`
- end: `0x18001f8da`
- name: `?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001b7a0`

## callees

- `0x180004410`
- `0x18000c250`
- `0x180017c18`
- `0x18001f7e8`
- `0x18001f8e0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18001f883`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(unsigned __int16 *a1, void *a2)
{
  void *v4; // rax
  _QWORD *v5; // r15
  _WORD *v6; // rsi
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // rbp
  unsigned __int16 *v9; // rdi
  char v11[32]; // [rsp+38h] [rbp-80h] BYREF
  _QWORD Src[5]; // [rsp+58h] [rbp-60h] BYREF

  Src[4] = a2;
  v4 = (void *)std::wstring::wstring(v11, a2);
  v5 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v4);
  std::wstring::wstring(a1, v5);
  if ( *((_QWORD *)a1 + 3) <= 7u )
  {
    v6 = a1;
    v7 = a1;
  }
  else
  {
    v6 = *(_WORD **)a1;
    v7 = *(unsigned __int16 **)a1;
  }
  v8 = &v7[*((_QWORD *)a1 + 2)];
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v9 = a1;
  else
    v9 = *(unsigned __int16 **)a1;
  while ( v9 != v8 )
    *v6++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v9++);
  std::wstring::~wstring(v5);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x18001f7e8  mov     [rsp+arg_10], rbx
0x18001f7ed  push    rbp
0x18001f7ee  push    rsi
0x18001f7ef  push    rdi
0x18001f7f0  push    r14
0x18001f7f2  push    r15
0x18001f7f4  sub     rsp, 90h
0x18001f7fb  mov     rax, cs:__security_cookie
0x18001f802  xor     rax, rsp
0x18001f805  mov     [rsp+0B8h+var_38], rax
0x18001f80d  mov     r14, rdx
0x18001f810  mov     rbx, rcx
0x18001f813  mov     [rsp+0B8h+var_88], rcx
0x18001f818  mov     [rsp+0B8h+var_40], rdx
0x18001f81d  mov     [rsp+0B8h+var_98], 0
0x18001f825  lea     rcx, [rsp+0B8h+var_80]
0x18001f82a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f82f  mov     rdx, rax; void *
0x18001f832  lea     rcx, [rsp+0B8h+Src]; Src
0x18001f837  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001f83c  mov     r15, rax
0x18001f83f  mov     [rsp+0B8h+var_90], rax
0x18001f844  mov     rdx, rax
0x18001f847  mov     rcx, rbx
0x18001f84a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f84f  mov     [rsp+0B8h+var_98], 2
0x18001f857  cmp     qword ptr [rbx+18h], 7
0x18001f85c  jbe     short loc_18001F866
0x18001f85e  mov     rsi, [rbx]
0x18001f861  mov     rcx, rsi
0x18001f864  jmp     short loc_18001F86C
0x18001f866  mov     rsi, rbx
0x18001f869  mov     rcx, rbx
0x18001f86c  mov     rax, [rbx+10h]
0x18001f870  lea     rbp, [rcx+rax*2]
0x18001f874  jbe     short loc_18001F87B
0x18001f876  mov     rdi, [rbx]
0x18001f879  jmp     short loc_18001F89A
0x18001f87b  mov     rdi, rbx
0x18001f87e  jmp     short loc_18001F89A
0x18001f880  movzx   ecx, word ptr [rdi]
0x18001f883  mov     rax, cs:__imp__o_towlower
0x18001f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f88f  mov     [rsi], ax
0x18001f892  lea     rsi, [rsi+2]
0x18001f896  add     rdi, 2
0x18001f89a  cmp     rdi, rbp
0x18001f89d  jnz     short loc_18001F880
0x18001f89f  mov     rcx, r15; void *
0x18001f8a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f8a7  nop
0x18001f8a8  mov     rcx, r14; void *
0x18001f8ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f8b0  mov     rax, rbx
0x18001f8b3  mov     rcx, [rsp+0B8h+var_38]
0x18001f8bb  xor     rcx, rsp; StackCookie
0x18001f8be  call    __security_check_cookie
0x18001f8c3  mov     rbx, [rsp+0B8h+arg_10]
0x18001f8cb  add     rsp, 90h
0x18001f8d2  pop     r15
0x18001f8d4  pop     r14
0x18001f8d6  pop     rdi
0x18001f8d7  pop     rsi
0x18001f8d8  pop     rbp
0x18001f8d9  retn
```
