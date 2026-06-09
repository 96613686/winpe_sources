# wil::str_printf<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(ushort const *,...)

- ea: `0x180026f3c`
- end: `0x180027105`
- name: `??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c454`

## callees

- `0x180002590`
- `0x180002fb0`
- `0x180003004`
- `0x18000ab14`
- `0x180013890`
- `0x18002065c`
- `0x180026f3c`
- `0x18002845c`
- `0x18002ecb8`

## string_xrefs

- `0x1800270ae`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800270f3`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 wil::str_printf<std::wstring>(__int64 a1, const wchar_t *a2, ...)
{
  size_t v4; // rsi
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  wchar_t *v10; // rdi
  unsigned __int64 v11; // r14
  int v12; // eax
  int v14; // [rsp+20h] [rbp-60h]
  wchar_t *Buffer[2]; // [rsp+38h] [rbp-48h] BYREF
  __m128i si128; // [rsp+48h] [rbp-38h]
  _OWORD v17[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  va_list ArgList; // [rsp+D0h] [rbp+50h] BYREF

  va_start(ArgList, a2);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v14 = 1;
  v4 = vscwprintf(a2, ArgList);
  *(_OWORD *)Buffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Buffer[0]) = 0;
  v6 = wil::details::string_maker<std::wstring>::make(Buffer, v5, v4);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 1997;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)v8,
      1);
    goto LABEL_19;
  }
  v10 = (wchar_t *)Buffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = Buffer[0];
  v11 = v4 + 1;
  if ( v4 == -1 )
  {
    v7 = -2147024809;
    goto LABEL_17;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v7 = -2147024809;
LABEL_16:
    *v10 = 0;
    goto LABEL_17;
  }
  v12 = vsnwprintf(v10, v4, a2, ArgList);
  if ( v12 < 0 || v12 > v4 )
  {
    v10[v4] = 0;
    v7 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_16;
LABEL_17:
    v8 = (unsigned int)v7;
    v9 = 2001;
    goto LABEL_18;
  }
  if ( v12 == v4 )
    v10[v4] = 0;
  v17[0] = *(_OWORD *)Buffer;
  v17[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Buffer[0]) = 0;
  std::wstring::operator=(a1, v17);
  std::wstring::~wstring(v17);
  v7 = 0;
LABEL_19:
  std::wstring::~wstring(Buffer);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7F0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v7,
      v14);
  return a1;
}

```

## disassembly

```asm
0x180026f3c  mov     [rsp-38h+arg_8], rdx
0x180026f41  mov     qword ptr [rsp-38h+ArgList], r8
0x180026f46  mov     [rsp-38h+arg_18], r9
0x180026f4b  push    rbp
0x180026f4c  push    rbx
0x180026f4d  push    rsi
0x180026f4e  push    rdi
0x180026f4f  push    r12
0x180026f51  push    r14
0x180026f53  push    r15
0x180026f55  mov     rbp, rsp
0x180026f58  sub     rsp, 80h
0x180026f5f  mov     rax, cs:__security_cookie
0x180026f66  xor     rax, rsp
0x180026f69  mov     [rbp+var_8], rax
0x180026f6d  mov     r12, rdx
0x180026f70  mov     r15, rcx
0x180026f73  mov     [rbp+var_58], rcx
0x180026f77  mov     [rbp+var_60], 0
0x180026f7e  xorps   xmm0, xmm0
0x180026f81  movups  xmmword ptr [rcx], xmm0
0x180026f84  mov     qword ptr [rcx+10h], 0
0x180026f8c  mov     qword ptr [rcx+18h], 7
0x180026f94  xor     eax, eax
0x180026f96  mov     [rcx], ax
0x180026f99  mov     [rbp+var_60], 1
0x180026fa0  mov     [rbp+var_50], rax
0x180026fa4  lea     rdx, [rbp+ArgList]; ArgList
0x180026fa8  mov     rcx, r12; Format
0x180026fab  call    _vscwprintf
0x180026fb0  movsxd  rsi, eax
0x180026fb3  xorps   xmm0, xmm0
0x180026fb6  movups  xmmword ptr [rbp+Buffer], xmm0
0x180026fba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026fc2  movdqu  [rbp+var_38], xmm1
0x180026fc7  xor     eax, eax
0x180026fc9  mov     word ptr [rbp+Buffer], ax
0x180026fcd  mov     r8, rsi
0x180026fd0  lea     rcx, [rbp+Buffer]
0x180026fd4  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x180026fd9  mov     ebx, eax
0x180026fdb  test    eax, eax
0x180026fdd  jns     short loc_180026FEC
0x180026fdf  mov     r9d, eax
0x180026fe2  mov     edx, 7CDh
0x180026fe7  jmp     loc_1800270AE
0x180026fec  lea     rdi, [rbp+Buffer]
0x180026ff0  cmp     qword ptr [rbp+var_38+8], 7
0x180026ff5  cmova   rdi, [rbp+Buffer]
0x180026ffa  lea     r14, [rsi+1]
0x180026ffe  test    r14, r14
0x180027001  jz      loc_180027097
0x180027007  cmp     r14, 7FFFFFFFh
0x18002700e  jbe     short loc_18002701A
0x180027010  mov     ebx, 80070057h
0x180027015  jmp     loc_1800270A1
0x18002701a  lea     r9, [rbp+ArgList]; Args
0x18002701e  mov     r8, r12; Format
0x180027021  mov     rdx, rsi; BufferCount
0x180027024  mov     rcx, rdi; Buffer
0x180027027  call    _vsnwprintf
0x18002702c  test    eax, eax
0x18002702e  js      short loc_18002707B
0x180027030  cdqe
0x180027032  cmp     rax, rsi
0x180027035  ja      short loc_18002707B
0x180027037  jnz     short loc_18002703F
0x180027039  xor     eax, eax
0x18002703b  mov     [rdi+rsi*2], ax
0x18002703f  movups  xmm0, xmmword ptr [rbp+Buffer]
0x180027043  movups  [rbp+var_28], xmm0
0x180027047  movups  xmm1, [rbp+var_38]
0x18002704b  movups  [rbp+var_18], xmm1
0x18002704f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180027057  movdqu  [rbp+var_38], xmm0
0x18002705c  xor     eax, eax
0x18002705e  mov     word ptr [rbp+Buffer], ax
0x180027062  lea     rdx, [rbp+var_28]
0x180027066  mov     rcx, r15
0x180027069  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002706e  lea     rcx, [rbp+var_28]
0x180027072  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027077  xor     ebx, ebx
0x180027079  jmp     short loc_1800270BE
0x18002707b  xor     eax, eax
0x18002707d  mov     [rdi+rsi*2], ax
0x180027081  mov     ebx, 8007007Ah
0x180027086  mov     rax, 7FFFFFFFFFFFFFFFh
0x180027090  test    rax, r14
0x180027093  jbe     short loc_1800270A6
0x180027095  jmp     short loc_1800270A1
0x180027097  mov     ebx, 80070057h
0x18002709c  test    r14, r14
0x18002709f  jz      short loc_1800270A6
0x1800270a1  xor     eax, eax
0x1800270a3  mov     [rdi], ax
0x1800270a6  mov     r9d, ebx; char *
0x1800270a9  mov     edx, 7D1h; void *
0x1800270ae  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800270b5  mov     rcx, [rbp+38h]; this
0x1800270b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270be  lea     rcx, [rbp+Buffer]
0x1800270c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800270c7  test    ebx, ebx
0x1800270c9  js      short loc_1800270EC
0x1800270cb  mov     rax, r15
0x1800270ce  mov     rcx, [rbp+var_8]
0x1800270d2  xor     rcx, rsp; StackCookie
0x1800270d5  call    __security_check_cookie
0x1800270da  add     rsp, 80h
0x1800270e1  pop     r15
0x1800270e3  pop     r14
0x1800270e5  pop     r12
0x1800270e7  pop     rdi
0x1800270e8  pop     rsi
0x1800270e9  pop     rbx
0x1800270ea  pop     rbp
0x1800270eb  retn
0x1800270ec  mov     rcx, [rbp+38h]; this
0x1800270f0  mov     r9d, ebx; char *
0x1800270f3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800270fa  mov     edx, 7F0h; void *
0x1800270ff  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
