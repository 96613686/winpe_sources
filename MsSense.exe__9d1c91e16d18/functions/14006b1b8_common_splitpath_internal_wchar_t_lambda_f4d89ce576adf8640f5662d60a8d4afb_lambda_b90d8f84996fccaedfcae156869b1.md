# common_splitpath_internal<wchar_t,_lambda_f4d89ce576adf8640f5662d60a8d4afb_,_lambda_b90d8f84996fccaedfcae156869b1630_>(wchar_t const * const,`anonymous namespace'::component_buffers<wchar_t> * const,_lambda_f4d89ce576adf8640f5662d60a8d4afb_,_lambda_b90d8f84996fccaedfcae156869b1630_)

- ea: `0x14006b1b8`
- end: `0x14006b403`
- name: `??$common_splitpath_internal@_WV_lambda_f4d89ce576adf8640f5662d60a8d4afb_@@V_lambda_b90d8f84996fccaedfcae156869b1630_@@@@YAHQEB_WQEAU?$component_buffers@_W@?A0x95109fda@@V_lambda_f4d89ce576adf8640f5662d60a8d4afb_@@V_lambda_b90d8f84996fccaedfcae156869b1630_@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14006b438`

## callees

- `0x140061534`
- `0x1400616b4`
- `0x140066da0`
- `0x14006b1b8`
- `0x14006b404`

## pseudocode

```c
__int64 __fastcall common_splitpath_internal<wchar_t,_lambda_f4d89ce576adf8640f5662d60a8d4afb_,_lambda_b90d8f84996fccaedfcae156869b1630_>(
        _WORD *a1,
        unsigned __int64 a2,
        char a3)
{
  _QWORD *v4; // rdi
  _WORD *v5; // r8
  _WORD *v6; // r10
  __int64 v7; // rax
  _WORD *v8; // rsi
  __int16 v10; // ax
  _WORD *v11; // rsi
  _WORD *v12; // r14
  _WORD *v13; // rbp
  __int64 v14; // rcx
  unsigned __int64 v15; // r9
  _WORD *v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // r9
  __int64 v19; // rcx
  unsigned __int64 v20; // rsi
  __int64 v21; // rcx
  unsigned __int64 v22; // rsi
  _WORD *v23; // rax

  v4 = (_QWORD *)a2;
  v5 = a1;
  if ( a1
    && a2
    && (v6 = *(_WORD **)a2, a2 = *(_QWORD *)(a2 + 8), (*v4 == 0) == (a2 == 0))
    && (v4[2] == 0) == (v4[3] == 0)
    && (v4[4] == 0) == (v4[5] == 0)
    && (v4[6] == 0) == (v4[7] == 0) )
  {
    v7 = 1;
    v8 = a1;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    if ( *v8 == 58 )
    {
      if ( v6 )
      {
        if ( a2 < 3 )
        {
LABEL_13:
          LOBYTE(a2) = a3;
          unknown_libname_89(v4, a2, v5);
          *(_DWORD *)sub_1400616B4() = 34;
          return 34;
        }
        sub_140066DA0(*v4, a2, a1, 2);
      }
      v5 = v8 + 1;
    }
    else if ( v6 )
    {
      *v6 = 0;
    }
    v10 = *v5;
    v11 = v5;
    v12 = 0;
    v13 = 0;
    if ( !*v5 )
      goto LABEL_30;
    do
    {
      if ( v10 == 47 || v10 == 92 )
      {
        v12 = v11 + 1;
      }
      else if ( v10 == 46 )
      {
        v13 = v11;
      }
      v10 = *++v11;
    }
    while ( *v11 );
    if ( v12 )
    {
      v14 = v4[2];
      if ( v14 )
      {
        a2 = v4[3];
        v15 = v12 - v5;
        if ( a2 <= v15 )
          goto LABEL_13;
        sub_140066DA0(v14, a2, v5, v15);
      }
      v5 = v12;
    }
    else
    {
LABEL_30:
      v16 = (_WORD *)v4[2];
      if ( v16 )
        *v16 = 0;
    }
    if ( v13 && v13 >= v5 )
    {
      v17 = v4[4];
      if ( v17 )
      {
        a2 = v4[5];
        v18 = v13 - v5;
        if ( a2 <= v18 )
          goto LABEL_13;
        sub_140066DA0(v17, a2, v5, v18);
      }
      v19 = v4[6];
      if ( v19 )
      {
        a2 = v4[7];
        v20 = v11 - v13;
        if ( a2 <= v20 )
          goto LABEL_13;
        sub_140066DA0(v19, a2, v13, v20);
      }
    }
    else
    {
      v21 = v4[4];
      if ( v21 )
      {
        a2 = v4[5];
        v22 = v11 - v5;
        if ( a2 <= v22 )
          goto LABEL_13;
        sub_140066DA0(v21, a2, v5, v22);
      }
      v23 = (_WORD *)v4[6];
      if ( v23 )
        *v23 = 0;
    }
    return 0;
  }
  else
  {
    LOBYTE(a2) = a3;
    unknown_libname_89(v4, a2, a1);
    *(_DWORD *)sub_1400616B4() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x14006b1b8  mov     [rsp+arg_0], rbx
0x14006b1bd  mov     [rsp+arg_8], rbp
0x14006b1c2  mov     [rsp+arg_10], rsi
0x14006b1c7  push    rdi
0x14006b1c8  push    r12
0x14006b1ca  push    r13
0x14006b1cc  push    r14
0x14006b1ce  push    r15
0x14006b1d0  sub     rsp, 20h
0x14006b1d4  xor     r13d, r13d
0x14006b1d7  mov     bl, r8b
0x14006b1da  mov     rdi, rdx
0x14006b1dd  mov     r8, rcx
0x14006b1e0  test    rcx, rcx
0x14006b1e3  jz      loc_14006B3C9
0x14006b1e9  test    rdx, rdx
0x14006b1ec  jz      loc_14006B3C9
0x14006b1f2  mov     r10, [rdi]
0x14006b1f5  mov     ecx, r13d
0x14006b1f8  mov     rdx, [rdx+8]
0x14006b1fc  test    r10, r10
0x14006b1ff  mov     eax, r13d
0x14006b202  setz    cl
0x14006b205  test    rdx, rdx
0x14006b208  setz    al
0x14006b20b  cmp     ecx, eax
0x14006b20d  jnz     loc_14006B3C9
0x14006b213  cmp     [rdi+10h], r13
0x14006b217  mov     ecx, r13d
0x14006b21a  mov     eax, r13d
0x14006b21d  setz    cl
0x14006b220  cmp     [rdi+18h], r13
0x14006b224  setz    al
0x14006b227  cmp     ecx, eax
0x14006b229  jnz     loc_14006B3C9
0x14006b22f  cmp     [rdi+20h], r13
0x14006b233  mov     ecx, r13d
0x14006b236  mov     eax, r13d
0x14006b239  setz    cl
0x14006b23c  cmp     [rdi+28h], r13
0x14006b240  setz    al
0x14006b243  cmp     ecx, eax
0x14006b245  jnz     loc_14006B3C9
0x14006b24b  cmp     [rdi+30h], r13
0x14006b24f  mov     ecx, r13d
0x14006b252  mov     eax, r13d
0x14006b255  setz    cl
0x14006b258  cmp     [rdi+38h], r13
0x14006b25c  setz    al
0x14006b25f  cmp     ecx, eax
0x14006b261  jnz     loc_14006B3C9
0x14006b267  lea     eax, [r13+1]
0x14006b26b  mov     rsi, r8
0x14006b26e  cmp     [rsi], r13w
0x14006b272  jz      short loc_14006B27E
0x14006b274  add     rsi, 2
0x14006b278  sub     rax, 1
0x14006b27c  jnz     short loc_14006B26E
0x14006b27e  cmp     word ptr [rsi], 3Ah ; ':'
0x14006b282  jnz     short loc_14006B2C0
0x14006b284  test    r10, r10
0x14006b287  jz      short loc_14006B2BA
0x14006b289  cmp     rdx, 3
0x14006b28d  jnb     short loc_14006B2AC
0x14006b28f  mov     dl, bl
0x14006b291  mov     rcx, rdi
0x14006b294  call    unknown_libname_89; Microsoft VisualC 64bit universal runtime
0x14006b299  call    sub_1400616B4
0x14006b29e  mov     ecx, 22h ; '"'
0x14006b2a3  mov     [rax], ecx
0x14006b2a5  mov     eax, ecx
0x14006b2a7  jmp     loc_14006B3E6
0x14006b2ac  mov     r9d, 2
0x14006b2b2  mov     rcx, r10
0x14006b2b5  call    sub_140066DA0
0x14006b2ba  lea     r8, [rsi+2]
0x14006b2be  jmp     short loc_14006B2C9
0x14006b2c0  test    r10, r10
0x14006b2c3  jz      short loc_14006B2C9
0x14006b2c5  mov     [r10], r13w
0x14006b2c9  movzx   eax, word ptr [r8]
0x14006b2cd  mov     rsi, r8
0x14006b2d0  mov     r14, r13
0x14006b2d3  mov     rbp, r13
0x14006b2d6  test    ax, ax
0x14006b2d9  jz      short loc_14006B330
0x14006b2db  cmp     ax, 2Fh ; '/'
0x14006b2df  jz      short loc_14006B2F2
0x14006b2e1  cmp     ax, 5Ch ; '\'
0x14006b2e5  jz      short loc_14006B2F2
0x14006b2e7  cmp     ax, 2Eh ; '.'
0x14006b2eb  jnz     short loc_14006B2F6
0x14006b2ed  mov     rbp, rsi
0x14006b2f0  jmp     short loc_14006B2F6
0x14006b2f2  lea     r14, [rsi+2]
0x14006b2f6  add     rsi, 2
0x14006b2fa  movzx   eax, word ptr [rsi]
0x14006b2fd  test    ax, ax
0x14006b300  jnz     short loc_14006B2DB
0x14006b302  test    r14, r14
0x14006b305  jz      short loc_14006B330
0x14006b307  mov     rcx, [rdi+10h]
0x14006b30b  test    rcx, rcx
0x14006b30e  jz      short loc_14006B32B
0x14006b310  mov     rdx, [rdi+18h]
0x14006b314  mov     r9, r14
0x14006b317  sub     r9, r8
0x14006b31a  sar     r9, 1
0x14006b31d  cmp     rdx, r9
0x14006b320  jbe     loc_14006B28F
0x14006b326  call    sub_140066DA0
0x14006b32b  mov     r8, r14
0x14006b32e  jmp     short loc_14006B33D
0x14006b330  mov     rax, [rdi+10h]
0x14006b334  test    rax, rax
0x14006b337  jz      short loc_14006B33D
0x14006b339  mov     [rax], r13w
0x14006b33d  test    rbp, rbp
0x14006b340  jz      short loc_14006B394
0x14006b342  cmp     rbp, r8
0x14006b345  jb      short loc_14006B394
0x14006b347  mov     rcx, [rdi+20h]
0x14006b34b  test    rcx, rcx
0x14006b34e  jz      short loc_14006B36B
0x14006b350  mov     rdx, [rdi+28h]
0x14006b354  mov     r9, rbp
0x14006b357  sub     r9, r8
0x14006b35a  sar     r9, 1
0x14006b35d  cmp     rdx, r9
0x14006b360  jbe     loc_14006B28F
0x14006b366  call    sub_140066DA0
0x14006b36b  mov     rcx, [rdi+30h]
0x14006b36f  test    rcx, rcx
0x14006b372  jz      short loc_14006B3C5
0x14006b374  mov     rdx, [rdi+38h]
0x14006b378  sub     rsi, rbp
0x14006b37b  sar     rsi, 1
0x14006b37e  cmp     rdx, rsi
0x14006b381  jbe     loc_14006B28F
0x14006b387  mov     r9, rsi
0x14006b38a  mov     r8, rbp
0x14006b38d  call    sub_140066DA0
0x14006b392  jmp     short loc_14006B3C5
0x14006b394  mov     rcx, [rdi+20h]
0x14006b398  test    rcx, rcx
0x14006b39b  jz      short loc_14006B3B8
0x14006b39d  mov     rdx, [rdi+28h]
0x14006b3a1  sub     rsi, r8
0x14006b3a4  sar     rsi, 1
0x14006b3a7  cmp     rdx, rsi
0x14006b3aa  jbe     loc_14006B28F
0x14006b3b0  mov     r9, rsi
0x14006b3b3  call    sub_140066DA0
0x14006b3b8  mov     rax, [rdi+30h]
0x14006b3bc  test    rax, rax
0x14006b3bf  jz      short loc_14006B3C5
0x14006b3c1  mov     [rax], r13w
0x14006b3c5  xor     eax, eax
0x14006b3c7  jmp     short loc_14006B3E6
0x14006b3c9  mov     dl, bl
0x14006b3cb  mov     rcx, rdi
0x14006b3ce  call    unknown_libname_89; Microsoft VisualC 64bit universal runtime
0x14006b3d3  call    sub_1400616B4
0x14006b3d8  mov     ebx, 16h
0x14006b3dd  mov     [rax], ebx
0x14006b3df  call    _invalid_parameter_noinfo
0x14006b3e4  mov     eax, ebx
0x14006b3e6  mov     rbx, [rsp+48h+arg_0]
0x14006b3eb  mov     rbp, [rsp+48h+arg_8]
0x14006b3f0  mov     rsi, [rsp+48h+arg_10]
0x14006b3f5  add     rsp, 20h
0x14006b3f9  pop     r15
0x14006b3fb  pop     r14
0x14006b3fd  pop     r13
0x14006b3ff  pop     r12
0x14006b401  pop     rdi
0x14006b402  retn
```
