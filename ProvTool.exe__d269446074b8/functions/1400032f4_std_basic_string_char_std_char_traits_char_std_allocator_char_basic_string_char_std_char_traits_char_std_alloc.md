# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x1400032f4`
- end: `0x1400033a1`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `173`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140009130`
- `0x140009170`
- `0x1400091c0`

## callees

- `0x1400032f4`
- `0x1400085ec`
- `0x140008c90`
- `0x14000de86`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, _BYTE *Src)
{
  size_t v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rax

  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( *Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( Src[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( v4 == -1 )
    std::wstring::_Xlen();
  if ( v4 <= 0xF )
  {
    if ( !v4 )
    {
      a1[2] = 0;
      *(_BYTE *)a1 = 0;
      return a1;
    }
  }
  else
  {
    std::string::_Copy(a1);
  }
  if ( a1[3] < 0x10u )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, v4);
  if ( a1[3] < 0x10u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  a1[2] = v4;
  *((_BYTE *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x1400032f4  mov     [rsp+arg_0], rbx
0x1400032f9  mov     [rsp+arg_8], rsi
0x1400032fe  push    rdi
0x1400032ff  sub     rsp, 20h
0x140003303  mov     qword ptr [rcx+18h], 0Fh
0x14000330b  mov     rsi, rdx
0x14000330e  mov     qword ptr [rcx+10h], 0
0x140003316  mov     rbx, rcx
0x140003319  mov     byte ptr [rcx], 0
0x14000331c  cmp     byte ptr [rdx], 0
0x14000331f  jnz     short loc_140003325
0x140003321  xor     edi, edi
0x140003323  jmp     short loc_140003332
0x140003325  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140003329  inc     rdi
0x14000332c  cmp     byte ptr [rdx+rdi], 0
0x140003330  jnz     short loc_140003329
0x140003332  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140003336  ja      short loc_14000339B
0x140003338  cmp     rdi, 0Fh
0x14000333c  jbe     short loc_140003355
0x14000333e  xor     r8d, r8d
0x140003341  mov     rdx, rdi
0x140003344  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140003349  cmp     qword ptr [rbx+18h], 10h
0x14000334e  jb      short loc_140003363
0x140003350  mov     rcx, [rbx]
0x140003353  jmp     short loc_140003366
0x140003355  test    rdi, rdi
0x140003358  jnz     short loc_140003349
0x14000335a  mov     [rcx+10h], rdi
0x14000335e  mov     [rcx], dil
0x140003361  jmp     short loc_140003388
0x140003363  mov     rcx, rbx; void *
0x140003366  mov     r8, rdi; Size
0x140003369  mov     rdx, rsi; Src
0x14000336c  call    memcpy_0
0x140003371  cmp     qword ptr [rbx+18h], 10h
0x140003376  jb      short loc_14000337D
0x140003378  mov     rax, [rbx]
0x14000337b  jmp     short loc_140003380
0x14000337d  mov     rax, rbx
0x140003380  mov     [rbx+10h], rdi
0x140003384  mov     byte ptr [rax+rdi], 0
0x140003388  mov     rsi, [rsp+28h+arg_8]
0x14000338d  mov     rax, rbx
0x140003390  mov     rbx, [rsp+28h+arg_0]
0x140003395  add     rsp, 20h
0x140003399  pop     rdi
0x14000339a  retn
0x14000339b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
