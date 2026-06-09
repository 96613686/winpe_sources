# WindowsMidiServicesInternal::ToUpperWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001340c`
- end: `0x1800134c6`
- name: `?ToUpperWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001338c`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000f0a4`
- `0x18001340c`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001347d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall WindowsMidiServicesInternal::ToUpperWStringCopy(unsigned __int16 *a1, void *a2)
{
  _WORD *v4; // r14
  unsigned __int16 *v5; // rcx
  unsigned __int16 *v6; // rbp
  unsigned __int16 *v7; // rdi

  std::wstring::wstring(a1, a2);
  if ( *((_QWORD *)a1 + 3) <= 7u )
  {
    v4 = a1;
    v5 = a1;
  }
  else
  {
    v4 = *(_WORD **)a1;
    v5 = *(unsigned __int16 **)a1;
  }
  v6 = &v5[*((_QWORD *)a1 + 2)];
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v7 = a1;
  else
    v7 = *(unsigned __int16 **)a1;
  while ( v7 != v6 )
    *v4++ = ((__int64 (__fastcall *)(_QWORD))towupper)(*v7++);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x18001340c  mov     r11, rsp
0x18001340f  mov     [r11+18h], rbx
0x180013413  mov     [r11+20h], rbp
0x180013417  push    rsi
0x180013418  push    rdi
0x180013419  push    r14
0x18001341b  sub     rsp, 40h
0x18001341f  mov     rax, cs:__security_cookie
0x180013426  xor     rax, rsp
0x180013429  mov     [rsp+58h+var_20], rax
0x18001342e  mov     rsi, rdx
0x180013431  mov     rbx, rcx
0x180013434  mov     [r11-30h], rcx
0x180013438  mov     [r11-28h], rdx
0x18001343c  mov     [rsp+58h+var_38], 0
0x180013444  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013449  mov     [rsp+58h+var_38], 1
0x180013451  cmp     qword ptr [rbx+18h], 7
0x180013456  jbe     short loc_180013460
0x180013458  mov     r14, [rbx]
0x18001345b  mov     rcx, r14
0x18001345e  jmp     short loc_180013466
0x180013460  mov     r14, rbx
0x180013463  mov     rcx, rbx
0x180013466  mov     rax, [rbx+10h]
0x18001346a  lea     rbp, [rcx+rax*2]
0x18001346e  jbe     short loc_180013475
0x180013470  mov     rdi, [rbx]
0x180013473  jmp     short loc_180013495
0x180013475  mov     rdi, rbx
0x180013478  jmp     short loc_180013495
0x18001347a  movzx   ecx, word ptr [rdi]
0x18001347d  mov     rax, cs:__imp_towupper
0x180013484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013489  mov     [r14], ax
0x18001348d  lea     r14, [r14+2]
0x180013491  add     rdi, 2
0x180013495  cmp     rdi, rbp
0x180013498  jnz     short loc_18001347A
0x18001349a  mov     rcx, rsi; void *
0x18001349d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800134a2  mov     rax, rbx
0x1800134a5  mov     rcx, [rsp+58h+var_20]
0x1800134aa  xor     rcx, rsp; StackCookie
0x1800134ad  call    __security_check_cookie
0x1800134b2  mov     rbx, [rsp+58h+arg_10]
0x1800134b7  mov     rbp, [rsp+58h+arg_18]
0x1800134bc  add     rsp, 40h
0x1800134c0  pop     r14
0x1800134c2  pop     rdi
0x1800134c3  pop     rsi
0x1800134c4  retn
```
