# WindowsMidiServicesInternal::ToUpperWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011858`
- end: `0x180011912`
- name: `?ToUpperWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800117d8`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x180011858`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800118c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall WindowsMidiServicesInternal::ToUpperWStringCopy(unsigned __int16 *a1, __int64 a2)
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
0x180011858  mov     r11, rsp
0x18001185b  mov     [r11+18h], rbx
0x18001185f  mov     [r11+20h], rbp
0x180011863  push    rsi
0x180011864  push    rdi
0x180011865  push    r14
0x180011867  sub     rsp, 40h
0x18001186b  mov     rax, cs:__security_cookie
0x180011872  xor     rax, rsp
0x180011875  mov     [rsp+58h+var_20], rax
0x18001187a  mov     rsi, rdx
0x18001187d  mov     rbx, rcx
0x180011880  mov     [r11-30h], rcx
0x180011884  mov     [r11-28h], rdx
0x180011888  mov     [rsp+58h+var_38], 0
0x180011890  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011895  mov     [rsp+58h+var_38], 1
0x18001189d  cmp     qword ptr [rbx+18h], 7
0x1800118a2  jbe     short loc_1800118AC
0x1800118a4  mov     r14, [rbx]
0x1800118a7  mov     rcx, r14
0x1800118aa  jmp     short loc_1800118B2
0x1800118ac  mov     r14, rbx
0x1800118af  mov     rcx, rbx
0x1800118b2  mov     rax, [rbx+10h]
0x1800118b6  lea     rbp, [rcx+rax*2]
0x1800118ba  jbe     short loc_1800118C1
0x1800118bc  mov     rdi, [rbx]
0x1800118bf  jmp     short loc_1800118E1
0x1800118c1  mov     rdi, rbx
0x1800118c4  jmp     short loc_1800118E1
0x1800118c6  movzx   ecx, word ptr [rdi]
0x1800118c9  mov     rax, cs:__imp_towupper
0x1800118d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118d5  mov     [r14], ax
0x1800118d9  lea     r14, [r14+2]
0x1800118dd  add     rdi, 2
0x1800118e1  cmp     rdi, rbp
0x1800118e4  jnz     short loc_1800118C6
0x1800118e6  mov     rcx, rsi
0x1800118e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800118ee  mov     rax, rbx
0x1800118f1  mov     rcx, [rsp+58h+var_20]
0x1800118f6  xor     rcx, rsp; StackCookie
0x1800118f9  call    __security_check_cookie
0x1800118fe  mov     rbx, [rsp+58h+arg_10]
0x180011903  mov     rbp, [rsp+58h+arg_18]
0x180011908  add     rsp, 40h
0x18001190c  pop     r14
0x18001190e  pop     rdi
0x18001190f  pop     rsi
0x180011910  retn
```
