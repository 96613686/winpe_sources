# common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630_

- ea: `0x180023e3c`
- end: `0x18002407c`
- name: `common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630___`
- size: `576`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800240b0`

## callees

- `0x18000bb9c`
- `0x18000be9c`
- `0x18000bfbc`
- `0x180023e3c`
- `0x18002407c`

## pseudocode

```c
__int64 __fastcall common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630_(
        wchar_t *Source,
        wchar_t *a2,
        char a3)
{
  wchar_t **v4; // rdi
  wchar_t *v5; // r8
  wchar_t *v6; // r10
  __int64 v7; // rax
  wchar_t *v8; // rsi
  wchar_t v10; // ax
  wchar_t *v11; // rsi
  wchar_t *v12; // r14
  const wchar_t *v13; // rbp
  wchar_t *v14; // rcx
  rsize_t v15; // r9
  wchar_t *v16; // rax
  wchar_t *v17; // rcx
  rsize_t v18; // r9
  wchar_t *v19; // rcx
  rsize_t v20; // rsi
  wchar_t *v21; // rcx
  rsize_t v22; // rsi
  wchar_t *v23; // rax

  v4 = (wchar_t **)a2;
  v5 = Source;
  if ( Source
    && a2
    && (v6 = *(wchar_t **)a2, a2 = (wchar_t *)*((_QWORD *)a2 + 1), (*v4 == 0) == (a2 == 0))
    && (v4[2] == 0) == (v4[3] == 0)
    && (v4[4] == 0) == (v4[5] == 0)
    && (v4[6] == 0) == (v4[7] == 0) )
  {
    v7 = 1;
    v8 = Source;
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
        if ( (unsigned __int64)a2 < 3 )
        {
LABEL_13:
          LOBYTE(a2) = a3;
          reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb_(v4, a2, v5);
          *errno() = 34;
          return 34;
        }
        wcsncpy_s(*v4, (rsize_t)a2, Source, 2u);
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
    while ( v10 )
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
    if ( v12 )
    {
      v14 = v4[2];
      if ( v14 )
      {
        a2 = v4[3];
        v15 = v12 - v5;
        if ( (unsigned __int64)a2 <= v15 )
          goto LABEL_13;
        wcsncpy_s(v14, (rsize_t)a2, v5, v15);
      }
      v5 = v12;
    }
    else
    {
      v16 = v4[2];
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
        if ( (unsigned __int64)a2 <= v18 )
          goto LABEL_13;
        wcsncpy_s(v17, (rsize_t)a2, v5, v18);
      }
      v19 = v4[6];
      if ( v19 )
      {
        a2 = v4[7];
        v20 = v11 - v13;
        if ( (unsigned __int64)a2 <= v20 )
          goto LABEL_13;
        wcsncpy_s(v19, (rsize_t)a2, v13, v20);
      }
    }
    else
    {
      v21 = v4[4];
      if ( v21 )
      {
        a2 = v4[5];
        v22 = v11 - v5;
        if ( (unsigned __int64)a2 <= v22 )
          goto LABEL_13;
        wcsncpy_s(v21, (rsize_t)a2, v5, v22);
      }
      v23 = v4[6];
      if ( v23 )
        *v23 = 0;
    }
    return 0;
  }
  else
  {
    LOBYTE(a2) = a3;
    reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb_(v4, a2, Source);
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x180023e3c  mov     [rsp+arg_0], rbx
0x180023e41  mov     [rsp+arg_8], rbp
0x180023e46  mov     [rsp+arg_10], rsi
0x180023e4b  push    rdi
0x180023e4c  push    r14
0x180023e4e  push    r15
0x180023e50  sub     rsp, 20h
0x180023e54  xor     r15d, r15d
0x180023e57  mov     bl, r8b
0x180023e5a  mov     rdi, rdx
0x180023e5d  mov     r8, rcx; Source
0x180023e60  test    rcx, rcx
0x180023e63  jz      loc_180024046
0x180023e69  test    rdx, rdx
0x180023e6c  jz      loc_180024046
0x180023e72  mov     r10, [rdi]
0x180023e75  mov     ecx, r15d
0x180023e78  mov     rdx, [rdx+8]; SizeInWords
0x180023e7c  test    r10, r10
0x180023e7f  mov     eax, r15d
0x180023e82  setz    cl
0x180023e85  test    rdx, rdx
0x180023e88  setz    al
0x180023e8b  cmp     ecx, eax
0x180023e8d  jnz     loc_180024046
0x180023e93  cmp     [rdi+10h], r15
0x180023e97  mov     ecx, r15d
0x180023e9a  mov     eax, r15d
0x180023e9d  setz    cl
0x180023ea0  cmp     [rdi+18h], r15
0x180023ea4  setz    al
0x180023ea7  cmp     ecx, eax
0x180023ea9  jnz     loc_180024046
0x180023eaf  cmp     [rdi+20h], r15
0x180023eb3  mov     ecx, r15d
0x180023eb6  mov     eax, r15d
0x180023eb9  setz    cl
0x180023ebc  cmp     [rdi+28h], r15
0x180023ec0  setz    al
0x180023ec3  cmp     ecx, eax
0x180023ec5  jnz     loc_180024046
0x180023ecb  cmp     [rdi+30h], r15
0x180023ecf  mov     ecx, r15d
0x180023ed2  mov     eax, r15d
0x180023ed5  setz    cl
0x180023ed8  cmp     [rdi+38h], r15
0x180023edc  setz    al
0x180023edf  cmp     ecx, eax
0x180023ee1  jnz     loc_180024046
0x180023ee7  lea     eax, [r15+1]
0x180023eeb  mov     rsi, r8
0x180023eee  cmp     [rsi], r15w
0x180023ef2  jz      short loc_180023EFE
0x180023ef4  add     rsi, 2
0x180023ef8  sub     rax, 1
0x180023efc  jnz     short loc_180023EEE
0x180023efe  cmp     word ptr [rsi], 3Ah ; ':'
0x180023f02  jnz     short loc_180023F40
0x180023f04  test    r10, r10
0x180023f07  jz      short loc_180023F3A
0x180023f09  cmp     rdx, 3
0x180023f0d  jnb     short loc_180023F2C
0x180023f0f  mov     dl, bl
0x180023f11  mov     rcx, rdi
0x180023f14  call    reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___; reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb_
0x180023f19  call    _errno
0x180023f1e  mov     ecx, 22h ; '"'
0x180023f23  mov     [rax], ecx
0x180023f25  mov     eax, ecx
0x180023f27  jmp     loc_180024063
0x180023f2c  mov     r9d, 2; MaxCount
0x180023f32  mov     rcx, r10; Destination
0x180023f35  call    wcsncpy_s
0x180023f3a  lea     r8, [rsi+2]; Source
0x180023f3e  jmp     short loc_180023F49
0x180023f40  test    r10, r10
0x180023f43  jz      short loc_180023F49
0x180023f45  mov     [r10], r15w
0x180023f49  movzx   eax, word ptr [r8]
0x180023f4d  mov     rsi, r8
0x180023f50  mov     r14, r15
0x180023f53  mov     rbp, r15
0x180023f56  jmp     short loc_180023F7A
0x180023f58  cmp     ax, 2Fh ; '/'
0x180023f5c  jz      short loc_180023F6F
0x180023f5e  cmp     ax, 5Ch ; '\'
0x180023f62  jz      short loc_180023F6F
0x180023f64  cmp     ax, 2Eh ; '.'
0x180023f68  jnz     short loc_180023F73
0x180023f6a  mov     rbp, rsi
0x180023f6d  jmp     short loc_180023F73
0x180023f6f  lea     r14, [rsi+2]
0x180023f73  add     rsi, 2
0x180023f77  movzx   eax, word ptr [rsi]
0x180023f7a  test    ax, ax
0x180023f7d  jnz     short loc_180023F58
0x180023f7f  test    r14, r14
0x180023f82  jz      short loc_180023FAD
0x180023f84  mov     rcx, [rdi+10h]; Destination
0x180023f88  test    rcx, rcx
0x180023f8b  jz      short loc_180023FA8
0x180023f8d  mov     rdx, [rdi+18h]; SizeInWords
0x180023f91  mov     r9, r14
0x180023f94  sub     r9, r8
0x180023f97  sar     r9, 1; MaxCount
0x180023f9a  cmp     rdx, r9
0x180023f9d  jbe     loc_180023F0F
0x180023fa3  call    wcsncpy_s
0x180023fa8  mov     r8, r14; Source
0x180023fab  jmp     short loc_180023FBA
0x180023fad  mov     rax, [rdi+10h]
0x180023fb1  test    rax, rax
0x180023fb4  jz      short loc_180023FBA
0x180023fb6  mov     [rax], r15w
0x180023fba  test    rbp, rbp
0x180023fbd  jz      short loc_180024011
0x180023fbf  cmp     rbp, r8
0x180023fc2  jb      short loc_180024011
0x180023fc4  mov     rcx, [rdi+20h]; Destination
0x180023fc8  test    rcx, rcx
0x180023fcb  jz      short loc_180023FE8
0x180023fcd  mov     rdx, [rdi+28h]; SizeInWords
0x180023fd1  mov     r9, rbp
0x180023fd4  sub     r9, r8
0x180023fd7  sar     r9, 1; MaxCount
0x180023fda  cmp     rdx, r9
0x180023fdd  jbe     loc_180023F0F
0x180023fe3  call    wcsncpy_s
0x180023fe8  mov     rcx, [rdi+30h]; Destination
0x180023fec  test    rcx, rcx
0x180023fef  jz      short loc_180024042
0x180023ff1  mov     rdx, [rdi+38h]; SizeInWords
0x180023ff5  sub     rsi, rbp
0x180023ff8  sar     rsi, 1
0x180023ffb  cmp     rdx, rsi
0x180023ffe  jbe     loc_180023F0F
0x180024004  mov     r9, rsi; MaxCount
0x180024007  mov     r8, rbp; Source
0x18002400a  call    wcsncpy_s
0x18002400f  jmp     short loc_180024042
0x180024011  mov     rcx, [rdi+20h]; Destination
0x180024015  test    rcx, rcx
0x180024018  jz      short loc_180024035
0x18002401a  mov     rdx, [rdi+28h]; SizeInWords
0x18002401e  sub     rsi, r8
0x180024021  sar     rsi, 1
0x180024024  cmp     rdx, rsi
0x180024027  jbe     loc_180023F0F
0x18002402d  mov     r9, rsi; MaxCount
0x180024030  call    wcsncpy_s
0x180024035  mov     rax, [rdi+30h]
0x180024039  test    rax, rax
0x18002403c  jz      short loc_180024042
0x18002403e  mov     [rax], r15w
0x180024042  xor     eax, eax
0x180024044  jmp     short loc_180024063
0x180024046  mov     dl, bl
0x180024048  mov     rcx, rdi
0x18002404b  call    reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___; reset_buffers_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb_
0x180024050  call    _errno
0x180024055  mov     ebx, 16h
0x18002405a  mov     [rax], ebx
0x18002405c  call    _invalid_parameter_noinfo
0x180024061  mov     eax, ebx
0x180024063  mov     rbx, [rsp+38h+arg_0]
0x180024068  mov     rbp, [rsp+38h+arg_8]
0x18002406d  mov     rsi, [rsp+38h+arg_10]
0x180024072  add     rsp, 20h
0x180024076  pop     r15
0x180024078  pop     r14
0x18002407a  pop     rdi
0x18002407b  retn
```
