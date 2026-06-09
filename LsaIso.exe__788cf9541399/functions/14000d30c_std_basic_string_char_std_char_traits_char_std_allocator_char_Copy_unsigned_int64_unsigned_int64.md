# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000d30c`
- end: `0x14000d3e5`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d440`

## callees

- `0x140003ad6`
- `0x14000747c`
- `0x14000d30c`
- `0x14000d500`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x14000d30c  mov     [rsp+arg_10], r8
0x14000d311  mov     [rsp+arg_8], rdx
0x14000d316  mov     [rsp+arg_0], rcx
0x14000d31b  push    rbx
0x14000d31c  push    rsi
0x14000d31d  push    rdi
0x14000d31e  push    r14
0x14000d320  sub     rsp, 28h
0x14000d324  mov     rsi, r8
0x14000d327  mov     rdi, rdx
0x14000d32a  mov     rbx, rcx
0x14000d32d  or      rdx, 0Fh
0x14000d331  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000d338  cmp     rdx, r9
0x14000d33b  ja      short loc_14000D371
0x14000d33d  mov     rdi, rdx
0x14000d340  mov     r8, [rcx+18h]
0x14000d344  mov     rcx, r8
0x14000d347  shr     rcx, 1
0x14000d34a  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000d354  mul     rdx
0x14000d357  shr     rdx, 1
0x14000d35a  cmp     rcx, rdx
0x14000d35d  jbe     short loc_14000D371
0x14000d35f  mov     rax, r9
0x14000d362  sub     rax, rcx
0x14000d365  cmp     r8, rax
0x14000d368  lea     rdi, [rcx+r8]
0x14000d36c  jbe     short loc_14000D371
0x14000d36e  mov     rdi, r9
0x14000d371  lea     rcx, [rdi+1]
0x14000d375  xor     edx, edx
0x14000d377  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14000d37c  mov     r14, rax
0x14000d37f  jmp     short loc_14000D395
0x14000d381  mov     rbx, [rsp+48h+arg_0]
0x14000d386  mov     rsi, [rsp+48h+arg_10]
0x14000d38b  mov     rdi, [rsp+48h+arg_8]
0x14000d390  mov     r14, [rsp+48h+arg_18]
0x14000d395  test    rsi, rsi
0x14000d398  jz      short loc_14000D3B4
0x14000d39a  cmp     qword ptr [rbx+18h], 10h
0x14000d39f  jb      short loc_14000D3A6
0x14000d3a1  mov     rdx, [rbx]
0x14000d3a4  jmp     short loc_14000D3A9
0x14000d3a6  mov     rdx, rbx; Src
0x14000d3a9  mov     r8, rsi; Size
0x14000d3ac  mov     rcx, r14; void *
0x14000d3af  call    memcpy_0
0x14000d3b4  xor     r8d, r8d
0x14000d3b7  mov     dl, 1
0x14000d3b9  mov     rcx, rbx
0x14000d3bc  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000d3c1  mov     [rbx], r14
0x14000d3c4  mov     [rbx+18h], rdi
0x14000d3c8  mov     rax, rbx
0x14000d3cb  cmp     rdi, 10h
0x14000d3cf  cmovnb  rax, r14
0x14000d3d3  mov     [rbx+10h], rsi
0x14000d3d7  mov     byte ptr [rax+rsi], 0
0x14000d3db  add     rsp, 28h
0x14000d3df  pop     r14
0x14000d3e1  pop     rdi
0x14000d3e2  pop     rsi
0x14000d3e3  pop     rbx
0x14000d3e4  retn
```
