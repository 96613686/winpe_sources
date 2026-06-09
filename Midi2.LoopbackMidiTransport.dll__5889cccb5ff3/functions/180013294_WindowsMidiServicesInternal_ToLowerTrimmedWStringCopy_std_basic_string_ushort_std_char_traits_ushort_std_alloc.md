# WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180013294`
- end: `0x180013386`
- name: `?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800104a4`
- `0x180010848`
- `0x180011980`
- `0x1800172d4`
- `0x18001742c`
- `0x180017e9c`
- `0x18001d454`
- `0x180020dc4`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000f0a4`
- `0x180013294`
- `0x1800134cc`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18001332f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(unsigned __int16 *a1, void *a2)
{
  void *v4; // rax
  void *v5; // r15
  _WORD *v6; // rsi
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // rbp
  unsigned __int16 *v9; // rdi
  char v11[32]; // [rsp+38h] [rbp-80h] BYREF
  char Src[32]; // [rsp+58h] [rbp-60h] BYREF
  void *v13; // [rsp+78h] [rbp-40h]

  v13 = a2;
  v4 = (void *)std::wstring::wstring(v11, a2);
  v5 = (void *)WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v4);
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
0x180013294  mov     [rsp+arg_10], rbx
0x180013299  push    rbp
0x18001329a  push    rsi
0x18001329b  push    rdi
0x18001329c  push    r14
0x18001329e  push    r15
0x1800132a0  sub     rsp, 90h
0x1800132a7  mov     rax, cs:__security_cookie
0x1800132ae  xor     rax, rsp
0x1800132b1  mov     [rsp+0B8h+var_38], rax
0x1800132b9  mov     r14, rdx
0x1800132bc  mov     rbx, rcx
0x1800132bf  mov     [rsp+0B8h+var_88], rcx
0x1800132c4  mov     [rsp+0B8h+var_40], rdx
0x1800132c9  mov     [rsp+0B8h+var_98], 0
0x1800132d1  lea     rcx, [rsp+0B8h+var_80]
0x1800132d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800132db  mov     rdx, rax; void *
0x1800132de  lea     rcx, [rsp+0B8h+Src]; Src
0x1800132e3  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x1800132e8  mov     r15, rax
0x1800132eb  mov     [rsp+0B8h+var_90], rax
0x1800132f0  mov     rdx, rax
0x1800132f3  mov     rcx, rbx
0x1800132f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800132fb  mov     [rsp+0B8h+var_98], 2
0x180013303  cmp     qword ptr [rbx+18h], 7
0x180013308  jbe     short loc_180013312
0x18001330a  mov     rsi, [rbx]
0x18001330d  mov     rcx, rsi
0x180013310  jmp     short loc_180013318
0x180013312  mov     rsi, rbx
0x180013315  mov     rcx, rbx
0x180013318  mov     rax, [rbx+10h]
0x18001331c  lea     rbp, [rcx+rax*2]
0x180013320  jbe     short loc_180013327
0x180013322  mov     rdi, [rbx]
0x180013325  jmp     short loc_180013346
0x180013327  mov     rdi, rbx
0x18001332a  jmp     short loc_180013346
0x18001332c  movzx   ecx, word ptr [rdi]
0x18001332f  mov     rax, cs:__imp__o_towlower
0x180013336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001333b  mov     [rsi], ax
0x18001333e  lea     rsi, [rsi+2]
0x180013342  add     rdi, 2
0x180013346  cmp     rdi, rbp
0x180013349  jnz     short loc_18001332C
0x18001334b  mov     rcx, r15; void *
0x18001334e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013353  nop
0x180013354  mov     rcx, r14; void *
0x180013357  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001335c  mov     rax, rbx
0x18001335f  mov     rcx, [rsp+0B8h+var_38]
0x180013367  xor     rcx, rsp; StackCookie
0x18001336a  call    __security_check_cookie
0x18001336f  mov     rbx, [rsp+0B8h+arg_10]
0x180013377  add     rsp, 90h
0x18001337e  pop     r15
0x180013380  pop     r14
0x180013382  pop     rdi
0x180013383  pop     rsi
0x180013384  pop     rbp
0x180013385  retn
```
