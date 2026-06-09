# WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001b160`
- end: `0x18001b252`
- name: `?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `242`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001ab10`
- `0x180023320`
- `0x180036d5c`
- `0x180043eb4`
- `0x1800456dc`
- `0x180055984`

## callees

- `0x180005020`
- `0x18000d430`
- `0x180014194`
- `0x18001b160`
- `0x18001b258`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18001b1fb`

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
0x18001b160  mov     [rsp+arg_10], rbx
0x18001b165  push    rbp
0x18001b166  push    rsi
0x18001b167  push    rdi
0x18001b168  push    r14
0x18001b16a  push    r15
0x18001b16c  sub     rsp, 90h
0x18001b173  mov     rax, cs:__security_cookie
0x18001b17a  xor     rax, rsp
0x18001b17d  mov     [rsp+0B8h+var_38], rax
0x18001b185  mov     r14, rdx
0x18001b188  mov     rbx, rcx
0x18001b18b  mov     [rsp+0B8h+var_88], rcx
0x18001b190  mov     [rsp+0B8h+var_40], rdx
0x18001b195  mov     [rsp+0B8h+var_98], 0
0x18001b19d  lea     rcx, [rsp+0B8h+var_80]
0x18001b1a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b1a7  mov     rdx, rax; void *
0x18001b1aa  lea     rcx, [rsp+0B8h+Src]; Src
0x18001b1af  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001b1b4  mov     r15, rax
0x18001b1b7  mov     [rsp+0B8h+var_90], rax
0x18001b1bc  mov     rdx, rax
0x18001b1bf  mov     rcx, rbx
0x18001b1c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b1c7  mov     [rsp+0B8h+var_98], 2
0x18001b1cf  cmp     qword ptr [rbx+18h], 7
0x18001b1d4  jbe     short loc_18001B1DE
0x18001b1d6  mov     rsi, [rbx]
0x18001b1d9  mov     rcx, rsi
0x18001b1dc  jmp     short loc_18001B1E4
0x18001b1de  mov     rsi, rbx
0x18001b1e1  mov     rcx, rbx
0x18001b1e4  mov     rax, [rbx+10h]
0x18001b1e8  lea     rbp, [rcx+rax*2]
0x18001b1ec  jbe     short loc_18001B1F3
0x18001b1ee  mov     rdi, [rbx]
0x18001b1f1  jmp     short loc_18001B212
0x18001b1f3  mov     rdi, rbx
0x18001b1f6  jmp     short loc_18001B212
0x18001b1f8  movzx   ecx, word ptr [rdi]
0x18001b1fb  mov     rax, cs:__imp__o_towlower
0x18001b202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b207  mov     [rsi], ax
0x18001b20a  lea     rsi, [rsi+2]
0x18001b20e  add     rdi, 2
0x18001b212  cmp     rdi, rbp
0x18001b215  jnz     short loc_18001B1F8
0x18001b217  mov     rcx, r15; void *
0x18001b21a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b21f  nop
0x18001b220  mov     rcx, r14; void *
0x18001b223  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b228  mov     rax, rbx
0x18001b22b  mov     rcx, [rsp+0B8h+var_38]
0x18001b233  xor     rcx, rsp; StackCookie
0x18001b236  call    __security_check_cookie
0x18001b23b  mov     rbx, [rsp+0B8h+arg_10]
0x18001b243  add     rsp, 90h
0x18001b24a  pop     r15
0x18001b24c  pop     r14
0x18001b24e  pop     rdi
0x18001b24f  pop     rsi
0x18001b250  pop     rbp
0x18001b251  retn
```
