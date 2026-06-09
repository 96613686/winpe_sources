# __scrt_initialize_onexit_tables

- ea: `0x180003d20`
- end: `0x180003de9`
- name: `__scrt_initialize_onexit_tables`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003bd4`

## callees

- `0x180003d20`
- `0x180004670`
- `0x18000467c`
- `0x18000498a`

## pseudocode

```c
bool __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  bool result; // al
  _PVFV *v3; // r8
  __int128 v4; // [rsp+20h] [rbp-20h]

  if ( a1 > 1 )
  {
    _scrt_fastfail(5u);
    JUMPOUT(0x180003DE8LL);
  }
  if ( !_scrt_is_ucrt_dll_in_use() || a1 )
  {
    result = 1;
    v3 = (_PVFV *)(_security_cookie ^ __ROR8__(-1, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
    *(_QWORD *)&v4 = v3;
    *((_QWORD *)&v4 + 1) = v3;
    *(_OWORD *)&Table._first = v4;
    *(_QWORD *)&v4 = v3;
    *((_QWORD *)&v4 + 1) = v3;
    Table._end = v3;
    *(_OWORD *)&stru_180008188._first = v4;
    stru_180008188._end = v3;
  }
  else
  {
    return !initialize_onexit_table_0(&Table) && initialize_onexit_table_0(&stru_180008188) == 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003d20  mov     [rsp-8+arg_0], rbx
0x180003d25  push    rbp
0x180003d26  mov     rbp, rsp
0x180003d29  sub     rsp, 40h
0x180003d2d  mov     ebx, ecx
0x180003d2f  cmp     ecx, 1
0x180003d32  ja      loc_180003DDE
0x180003d38  call    __scrt_is_ucrt_dll_in_use
0x180003d3d  test    eax, eax
0x180003d3f  jz      short loc_180003D6C
0x180003d41  test    ebx, ebx
0x180003d43  jnz     short loc_180003D6C
0x180003d45  lea     rcx, Table; Table
0x180003d4c  call    _initialize_onexit_table_0
0x180003d51  test    eax, eax
0x180003d53  jz      short loc_180003D59
0x180003d55  xor     al, al
0x180003d57  jmp     short loc_180003DD3
0x180003d59  lea     rcx, stru_180008188; Table
0x180003d60  call    _initialize_onexit_table_0
0x180003d65  test    eax, eax
0x180003d67  setz    al
0x180003d6a  jmp     short loc_180003DD3
0x180003d6c  mov     rdx, cs:__security_cookie
0x180003d73  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003d77  mov     eax, edx
0x180003d79  mov     ecx, 40h ; '@'
0x180003d7e  and     eax, 3Fh
0x180003d81  sub     ecx, eax
0x180003d83  mov     al, 1
0x180003d85  ror     r8, cl
0x180003d88  xor     r8, rdx
0x180003d8b  mov     qword ptr [rbp+var_20], r8
0x180003d8f  mov     qword ptr [rbp+var_20+8], r8
0x180003d93  movups  xmm0, [rbp+var_20]
0x180003d97  mov     [rbp+var_10], r8
0x180003d9b  movsd   xmm1, [rbp+var_10]
0x180003da0  movups  xmmword ptr cs:Table._first, xmm0
0x180003da7  mov     qword ptr [rbp+var_20], r8
0x180003dab  mov     qword ptr [rbp+var_20+8], r8
0x180003daf  movups  xmm0, [rbp+var_20]
0x180003db3  mov     [rbp+var_10], r8
0x180003db7  movsd   cs:Table._end, xmm1
0x180003dbf  movsd   xmm1, [rbp+var_10]
0x180003dc4  movups  xmmword ptr cs:stru_180008188._first, xmm0
0x180003dcb  movsd   cs:stru_180008188._end, xmm1
0x180003dd3  mov     rbx, [rsp+40h+arg_0]
0x180003dd8  add     rsp, 40h
0x180003ddc  pop     rbp
0x180003ddd  retn
0x180003dde  mov     ecx, 5
0x180003de3  call    __scrt_fastfail
```
