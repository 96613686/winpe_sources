# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Tidy(bool,unsigned __int64)

- ea: `0x180001440`
- end: `0x180001514`
- name: `?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002c80`
- `0x180004b72`

## callees

- `0x180001440`
- `0x180001be0`
- `0x180004acc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001491`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014a9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014b9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014c9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014d6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001491`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014a9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014b9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014c9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800014d6`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, void *a3)
{
  void **v4; // rbx
  char *v5; // rdi
  unsigned __int64 v6; // rax
  char *v7; // rax
  unsigned __int64 v8; // rdi
  bool v9; // cf
  __int64 result; // rax

  v4 = a1;
  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = (char *)*a1;
    if ( a3 )
      memcpy_0(a1, *a1, 2LL * (_QWORD)a3);
    v6 = (unsigned __int64)v4[3] + 1;
    if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
      _invalid_parameter_noinfo_noreturn();
    if ( 2 * v6 >= 0x1000 )
    {
      if ( ((unsigned __int8)v5 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v7 = (char *)*((_QWORD *)v5 - 1);
      if ( v7 >= v5 )
        _invalid_parameter_noinfo_noreturn();
      v8 = v5 - v7;
      if ( v8 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v8 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v5 = v7;
    }
    operator delete(v5);
  }
  v4[3] = (void *)7;
  v9 = (unsigned __int64)v4[3] < 8;
  v4[2] = a3;
  if ( !v9 )
    v4 = (void **)*v4;
  result = 0;
  *((_WORD *)v4 + (_QWORD)a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001440  mov     [rsp+arg_0], rbx
0x180001445  mov     [rsp+arg_8], rsi
0x18000144a  push    rdi
0x18000144b  sub     rsp, 20h
0x18000144f  mov     rsi, r8
0x180001452  mov     rbx, rcx
0x180001455  test    dl, dl
0x180001457  jz      loc_1800014E8
0x18000145d  cmp     qword ptr [rcx+18h], 8
0x180001462  jb      loc_1800014E8
0x180001468  mov     rdi, [rcx]
0x18000146b  test    r8, r8
0x18000146e  jz      short loc_18000147B
0x180001470  add     r8, r8; Size
0x180001473  mov     rdx, rdi; Src
0x180001476  call    memcpy_0
0x18000147b  mov     rax, [rbx+18h]
0x18000147f  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180001489  inc     rax
0x18000148c  cmp     rax, rcx
0x18000148f  jbe     short loc_180001498
0x180001491  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001498  add     rax, rax
0x18000149b  cmp     rax, 1000h
0x1800014a1  jb      short loc_1800014E0
0x1800014a3  test    dil, 1Fh
0x1800014a7  jz      short loc_1800014B0
0x1800014a9  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800014b0  mov     rax, [rdi-8]
0x1800014b4  cmp     rax, rdi
0x1800014b7  jb      short loc_1800014C0
0x1800014b9  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800014c0  sub     rdi, rax
0x1800014c3  cmp     rdi, 8
0x1800014c7  jnb     short loc_1800014D0
0x1800014c9  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800014d0  cmp     rdi, 27h ; '''
0x1800014d4  jbe     short loc_1800014DD
0x1800014d6  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800014dd  mov     rdi, rax
0x1800014e0  mov     rcx, rdi; void *
0x1800014e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800014e8  mov     qword ptr [rbx+18h], 7
0x1800014f0  cmp     qword ptr [rbx+18h], 8
0x1800014f5  mov     [rbx+10h], rsi
0x1800014f9  jb      short loc_1800014FE
0x1800014fb  mov     rbx, [rbx]
0x1800014fe  xor     eax, eax
0x180001500  mov     [rbx+rsi*2], ax
0x180001504  mov     rbx, [rsp+28h+arg_0]
0x180001509  mov     rsi, [rsp+28h+arg_8]
0x18000150e  add     rsp, 20h
0x180001512  pop     rdi
0x180001513  retn
```
