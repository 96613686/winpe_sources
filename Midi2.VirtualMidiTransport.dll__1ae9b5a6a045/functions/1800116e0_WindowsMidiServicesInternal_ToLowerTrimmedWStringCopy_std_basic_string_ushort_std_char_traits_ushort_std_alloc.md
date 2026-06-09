# WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800116e0`
- end: `0x1800117d2`
- name: `?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000d9b4`
- `0x18000e0a4`
- `0x1800159c8`
- `0x180016348`
- `0x180016740`
- `0x18001b094`
- `0x18001b1b0`
- `0x18001d680`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x1800116e0`
- `0x180011918`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18001177b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(unsigned __int16 *a1, __int64 a2)
{
  __int64 v4; // r15
  _WORD *v5; // rsi
  unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // rbp
  unsigned __int16 *v8; // rdi
  char v10[32]; // [rsp+38h] [rbp-80h] BYREF
  char Src[32]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v12; // [rsp+78h] [rbp-40h]

  v12 = a2;
  std::wstring::wstring(v10, a2);
  v4 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src);
  std::wstring::wstring(a1, v4);
  if ( *((_QWORD *)a1 + 3) <= 7u )
  {
    v5 = a1;
    v6 = a1;
  }
  else
  {
    v5 = *(_WORD **)a1;
    v6 = *(unsigned __int16 **)a1;
  }
  v7 = &v6[*((_QWORD *)a1 + 2)];
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v8 = a1;
  else
    v8 = *(unsigned __int16 **)a1;
  while ( v8 != v7 )
    *v5++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v8++);
  std::wstring::~wstring(v4);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x1800116e0  mov     [rsp+arg_10], rbx
0x1800116e5  push    rbp
0x1800116e6  push    rsi
0x1800116e7  push    rdi
0x1800116e8  push    r14
0x1800116ea  push    r15
0x1800116ec  sub     rsp, 90h
0x1800116f3  mov     rax, cs:__security_cookie
0x1800116fa  xor     rax, rsp
0x1800116fd  mov     [rsp+0B8h+var_38], rax
0x180011705  mov     r14, rdx
0x180011708  mov     rbx, rcx
0x18001170b  mov     [rsp+0B8h+var_88], rcx
0x180011710  mov     [rsp+0B8h+var_40], rdx
0x180011715  mov     [rsp+0B8h+var_98], 0
0x18001171d  lea     rcx, [rsp+0B8h+var_80]
0x180011722  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011727  mov     rdx, rax
0x18001172a  lea     rcx, [rsp+0B8h+Src]; Src
0x18001172f  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180011734  mov     r15, rax
0x180011737  mov     [rsp+0B8h+var_90], rax
0x18001173c  mov     rdx, rax
0x18001173f  mov     rcx, rbx
0x180011742  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011747  mov     [rsp+0B8h+var_98], 2
0x18001174f  cmp     qword ptr [rbx+18h], 7
0x180011754  jbe     short loc_18001175E
0x180011756  mov     rsi, [rbx]
0x180011759  mov     rcx, rsi
0x18001175c  jmp     short loc_180011764
0x18001175e  mov     rsi, rbx
0x180011761  mov     rcx, rbx
0x180011764  mov     rax, [rbx+10h]
0x180011768  lea     rbp, [rcx+rax*2]
0x18001176c  jbe     short loc_180011773
0x18001176e  mov     rdi, [rbx]
0x180011771  jmp     short loc_180011792
0x180011773  mov     rdi, rbx
0x180011776  jmp     short loc_180011792
0x180011778  movzx   ecx, word ptr [rdi]
0x18001177b  mov     rax, cs:__imp__o_towlower
0x180011782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011787  mov     [rsi], ax
0x18001178a  lea     rsi, [rsi+2]
0x18001178e  add     rdi, 2
0x180011792  cmp     rdi, rbp
0x180011795  jnz     short loc_180011778
0x180011797  mov     rcx, r15
0x18001179a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001179f  nop
0x1800117a0  mov     rcx, r14
0x1800117a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800117a8  mov     rax, rbx
0x1800117ab  mov     rcx, [rsp+0B8h+var_38]
0x1800117b3  xor     rcx, rsp; StackCookie
0x1800117b6  call    __security_check_cookie
0x1800117bb  mov     rbx, [rsp+0B8h+arg_10]
0x1800117c3  add     rsp, 90h
0x1800117ca  pop     r15
0x1800117cc  pop     r14
0x1800117ce  pop     rdi
0x1800117cf  pop     rsi
0x1800117d0  pop     rbp
0x1800117d1  retn
```
