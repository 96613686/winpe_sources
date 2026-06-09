# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x1800037f0`
- end: `0x18000389e`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004ddf`

## callees

- `0x180001be0`
- `0x1800037f0`
- `0x180004acc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003835`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003845`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003855`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003862`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003835`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003845`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003855`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003862`

## pseudocode

```c
void __fastcall std::string::_Tidy(void **a1, char a2, size_t a3)
{
  void **v4; // rbx
  char *v5; // rdi
  char *v6; // rax
  unsigned __int64 v7; // rdi
  bool v8; // cf

  v4 = a1;
  if ( a2 && (unsigned __int64)a1[3] >= 0x10 )
  {
    v5 = (char *)*a1;
    if ( a3 )
      memcpy_0(a1, *a1, a3);
    if ( (unsigned __int64)v4[3] + 1 >= 0x1000 )
    {
      if ( ((unsigned __int8)v5 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v6 = (char *)*((_QWORD *)v5 - 1);
      if ( v6 >= v5 )
        _invalid_parameter_noinfo_noreturn();
      v7 = v5 - v6;
      if ( v7 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v7 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v5 = v6;
    }
    operator delete(v5);
  }
  v4[3] = (void *)15;
  v8 = (unsigned __int64)v4[3] < 0x10;
  v4[2] = (void *)a3;
  if ( !v8 )
    v4 = (void **)*v4;
  *((_BYTE *)v4 + a3) = 0;
}

```

## disassembly

```asm
0x1800037f0  mov     [rsp+arg_0], rbx
0x1800037f5  mov     [rsp+arg_8], rsi
0x1800037fa  push    rdi
0x1800037fb  sub     rsp, 20h
0x1800037ff  mov     rsi, r8
0x180003802  mov     rbx, rcx
0x180003805  test    dl, dl
0x180003807  jz      short loc_180003874
0x180003809  cmp     qword ptr [rcx+18h], 10h
0x18000380e  jb      short loc_180003874
0x180003810  mov     rdi, [rcx]
0x180003813  test    r8, r8
0x180003816  jz      short loc_180003820
0x180003818  mov     rdx, rdi; Src
0x18000381b  call    memcpy_0
0x180003820  mov     rax, [rbx+18h]
0x180003824  inc     rax
0x180003827  cmp     rax, 1000h
0x18000382d  jb      short loc_18000386C
0x18000382f  test    dil, 1Fh
0x180003833  jz      short loc_18000383C
0x180003835  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000383c  mov     rax, [rdi-8]
0x180003840  cmp     rax, rdi
0x180003843  jb      short loc_18000384C
0x180003845  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000384c  sub     rdi, rax
0x18000384f  cmp     rdi, 8
0x180003853  jnb     short loc_18000385C
0x180003855  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000385c  cmp     rdi, 27h ; '''
0x180003860  jbe     short loc_180003869
0x180003862  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003869  mov     rdi, rax
0x18000386c  mov     rcx, rdi; void *
0x18000386f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003874  mov     qword ptr [rbx+18h], 0Fh
0x18000387c  cmp     qword ptr [rbx+18h], 10h
0x180003881  mov     [rbx+10h], rsi
0x180003885  jb      short loc_18000388A
0x180003887  mov     rbx, [rbx]
0x18000388a  mov     byte ptr [rbx+rsi], 0
0x18000388e  mov     rbx, [rsp+28h+arg_0]
0x180003893  mov     rsi, [rsp+28h+arg_8]
0x180003898  add     rsp, 20h
0x18000389c  pop     rdi
0x18000389d  retn
```
