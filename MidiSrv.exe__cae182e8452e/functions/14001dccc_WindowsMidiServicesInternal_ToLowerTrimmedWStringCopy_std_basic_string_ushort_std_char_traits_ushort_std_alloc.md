# WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x14001dccc`
- end: `0x14001ddbe`
- name: `?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140017838`
- `0x140018f54`
- `0x1400193c4`
- `0x14001b8c0`
- `0x140028430`
- `0x14002b1a0`
- `0x14002ce1c`
- `0x14002d640`
- `0x14002ddf0`
- `0x14002e720`
- `0x140030250`
- `0x1400324c0`
- `0x140032ff4`
- `0x140034960`
- `0x140036a90`
- `0x140037b20`
- `0x140037dd0`
- `0x1400399d0`
- `0x14003b820`
- `0x140041a40`

## callees

- `0x1400054c0`
- `0x140007c20`
- `0x140013a38`
- `0x14001dccc`
- `0x14001ddc4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14001dd67`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(_QWORD *a1, char **a2)
{
  void *v4; // rax
  char **v5; // r15
  _WORD *v6; // rsi
  _QWORD *v7; // rcx
  unsigned __int16 *v8; // rbp
  unsigned __int16 *v9; // rdi
  _BYTE v11[32]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE Src[32]; // [rsp+58h] [rbp-60h] BYREF
  char **v13; // [rsp+78h] [rbp-40h]

  v13 = a2;
  v4 = (void *)std::wstring::wstring((__int64)v11, (__int64)a2);
  v5 = (char **)WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v4);
  std::wstring::wstring((__int64)a1, (__int64)v5);
  if ( a1[3] <= 7u )
  {
    v6 = a1;
    v7 = a1;
  }
  else
  {
    v6 = (_WORD *)*a1;
    v7 = (_QWORD *)*a1;
  }
  v8 = (unsigned __int16 *)v7 + a1[2];
  if ( a1[3] <= 7u )
    v9 = (unsigned __int16 *)a1;
  else
    v9 = (unsigned __int16 *)*a1;
  while ( v9 != v8 )
    *v6++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v9++);
  std::wstring::~wstring(v5);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x14001dccc  mov     [rsp+arg_10], rbx
0x14001dcd1  push    rbp
0x14001dcd2  push    rsi
0x14001dcd3  push    rdi
0x14001dcd4  push    r14
0x14001dcd6  push    r15
0x14001dcd8  sub     rsp, 90h
0x14001dcdf  mov     rax, cs:__security_cookie
0x14001dce6  xor     rax, rsp
0x14001dce9  mov     [rsp+0B8h+var_38], rax
0x14001dcf1  mov     r14, rdx
0x14001dcf4  mov     rbx, rcx
0x14001dcf7  mov     [rsp+0B8h+var_88], rcx
0x14001dcfc  mov     [rsp+0B8h+var_40], rdx
0x14001dd01  mov     [rsp+0B8h+var_98], 0
0x14001dd09  lea     rcx, [rsp+0B8h+var_80]
0x14001dd0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001dd13  mov     rdx, rax; void *
0x14001dd16  lea     rcx, [rsp+0B8h+Src]; Src
0x14001dd1b  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x14001dd20  mov     r15, rax
0x14001dd23  mov     [rsp+0B8h+var_90], rax
0x14001dd28  mov     rdx, rax
0x14001dd2b  mov     rcx, rbx
0x14001dd2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001dd33  mov     [rsp+0B8h+var_98], 2
0x14001dd3b  cmp     qword ptr [rbx+18h], 7
0x14001dd40  jbe     short loc_14001DD4A
0x14001dd42  mov     rsi, [rbx]
0x14001dd45  mov     rcx, rsi
0x14001dd48  jmp     short loc_14001DD50
0x14001dd4a  mov     rsi, rbx
0x14001dd4d  mov     rcx, rbx
0x14001dd50  mov     rax, [rbx+10h]
0x14001dd54  lea     rbp, [rcx+rax*2]
0x14001dd58  jbe     short loc_14001DD5F
0x14001dd5a  mov     rdi, [rbx]
0x14001dd5d  jmp     short loc_14001DD7E
0x14001dd5f  mov     rdi, rbx
0x14001dd62  jmp     short loc_14001DD7E
0x14001dd64  movzx   ecx, word ptr [rdi]
0x14001dd67  mov     rax, cs:__imp__o_towlower
0x14001dd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dd73  mov     [rsi], ax
0x14001dd76  lea     rsi, [rsi+2]
0x14001dd7a  add     rdi, 2
0x14001dd7e  cmp     rdi, rbp
0x14001dd81  jnz     short loc_14001DD64
0x14001dd83  mov     rcx, r15; void *
0x14001dd86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dd8b  nop
0x14001dd8c  mov     rcx, r14; void *
0x14001dd8f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dd94  mov     rax, rbx
0x14001dd97  mov     rcx, [rsp+0B8h+var_38]
0x14001dd9f  xor     rcx, rsp; StackCookie
0x14001dda2  call    __security_check_cookie
0x14001dda7  mov     rbx, [rsp+0B8h+arg_10]
0x14001ddaf  add     rsp, 90h
0x14001ddb6  pop     r15
0x14001ddb8  pop     r14
0x14001ddba  pop     rdi
0x14001ddbb  pop     rsi
0x14001ddbc  pop     rbp
0x14001ddbd  retn
```
