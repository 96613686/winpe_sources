# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000878c`
- end: `0x140008882`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `246`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008888`

## callees

- `0x140001530`
- `0x14000878c`
- `0x1400088e8`
- `0x140013ab7`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000880c`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000880c`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  const void **result; // rax
  void *v12; // rax
  __int64 v13; // [rsp+0h] [rbp-48h] BYREF
  void *v14; // [rsp+20h] [rbp-28h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v9 = 0;
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
    v14 = v9;
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)&v13;
    v12 = 0;
    if ( a2 == -1 || (v12 = operator new(a2 + 1)) != 0 )
    {
      v14 = v12;
      goto LABEL_9;
    }
    std::_Xbad_alloc();
LABEL_9:
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v14;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  LOBYTE(v6) = 1;
  std::string::_Tidy(v5, v6, 0);
  *v5 = v9;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v9;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x14000878c  mov     rax, rsp
0x14000878f  mov     [rax+20h], rbx
0x140008793  mov     [rax+18h], r8
0x140008797  mov     [rax+10h], rdx
0x14000879b  mov     [rax+8], rcx
0x14000879f  push    rsi
0x1400087a0  push    rdi
0x1400087a1  push    r14
0x1400087a3  sub     rsp, 30h
0x1400087a7  mov     r14, r8
0x1400087aa  mov     rbx, rdx
0x1400087ad  mov     rdi, rcx
0x1400087b0  or      rdx, 0Fh
0x1400087b4  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400087bb  cmp     rdx, r9
0x1400087be  ja      short loc_1400087F4
0x1400087c0  mov     rbx, rdx
0x1400087c3  mov     r8, [rcx+18h]
0x1400087c7  mov     rcx, r8
0x1400087ca  shr     rcx, 1
0x1400087cd  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400087d7  mul     rdx
0x1400087da  shr     rdx, 1
0x1400087dd  cmp     rcx, rdx
0x1400087e0  jbe     short loc_1400087F4
0x1400087e2  mov     rax, r9
0x1400087e5  sub     rax, rcx
0x1400087e8  cmp     r8, rax
0x1400087eb  lea     rbx, [rcx+r8]
0x1400087ef  jbe     short loc_1400087F4
0x1400087f1  mov     rbx, r9
0x1400087f4  lea     rcx, [rbx+1]; Size
0x1400087f8  xor     esi, esi
0x1400087fa  test    rcx, rcx
0x1400087fd  jz      short loc_140008812
0x1400087ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008804  mov     rsi, rax
0x140008807  test    rax, rax
0x14000880a  jnz     short loc_140008812
0x14000880c  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140008812  mov     [rsp+48h+var_28], rsi
0x140008817  jmp     short loc_14000882D
0x140008819  mov     rdi, [rsp+48h+arg_0]
0x14000881e  mov     r14, [rsp+48h+arg_10]
0x140008823  mov     rbx, [rsp+48h+arg_8]
0x140008828  mov     rsi, [rsp+48h+var_28]
0x14000882d  test    r14, r14
0x140008830  jz      short loc_14000884C
0x140008832  cmp     qword ptr [rdi+18h], 10h
0x140008837  jb      short loc_14000883E
0x140008839  mov     rdx, [rdi]
0x14000883c  jmp     short loc_140008841
0x14000883e  mov     rdx, rdi; Src
0x140008841  mov     r8, r14; Size
0x140008844  mov     rcx, rsi; void *
0x140008847  call    memcpy_0
0x14000884c  xor     r8d, r8d
0x14000884f  mov     dl, 1
0x140008851  mov     rcx, rdi
0x140008854  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140008859  mov     [rdi], rsi
0x14000885c  mov     [rdi+18h], rbx
0x140008860  mov     rax, rdi
0x140008863  cmp     rbx, 10h
0x140008867  cmovnb  rax, rsi
0x14000886b  mov     [rdi+10h], r14
0x14000886f  mov     byte ptr [rax+r14], 0
0x140008874  mov     rbx, [rsp+48h+arg_18]
0x140008879  add     rsp, 30h
0x14000887d  pop     r14
0x14000887f  pop     rdi
0x140008880  pop     rsi
0x140008881  retn
```
