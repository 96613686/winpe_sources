# AreTmInstancesEqual

- ea: `0x180021c30`
- end: `0x180021dc3`
- name: `AreTmInstancesEqual`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002369c`

## callees

- `0x180021c30`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021dae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021dae`

## pseudocode

```c
__int64 __fastcall AreTmInstancesEqual(__int64 a1, __int64 *a2, int *a3)
{
  __int64 v3; // rax
  unsigned int v4; // edi
  __int64 (__fastcall *v7)(__int64 *); // rax
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  unsigned __int16 *v14; // rax
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // eax
  unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // edx
  LPVOID pv; // [rsp+60h] [rbp+38h] BYREF
  LPVOID v24; // [rsp+68h] [rbp+40h] BYREF
  LPVOID v25; // [rsp+70h] [rbp+48h] BYREF
  LPVOID v26; // [rsp+78h] [rbp+50h] BYREF

  v3 = *a2;
  v4 = 0;
  pv = 0;
  v24 = 0;
  v25 = 0;
  v7 = *(__int64 (__fastcall **)(__int64 *))(v3 + 24);
  v26 = 0;
  v9 = v7(a2);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1) == v9
    && (v10 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 32))(a2),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1) == v10) )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, &pv);
    v12 = 0;
    v4 = v11;
    if ( v11 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(*a2 + 40))(a2, &v24);
      v12 = 0;
      v4 = v13;
      if ( v13 >= 0 )
      {
        v14 = (unsigned __int16 *)pv;
        do
        {
          v15 = *(unsigned __int16 *)((char *)v14 + (_BYTE *)v24 - (_BYTE *)pv);
          v16 = *v14 - v15;
          if ( v16 )
            break;
          ++v14;
        }
        while ( v15 );
        v12 = 0;
        if ( !v16 )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1) )
            goto LABEL_16;
          v17 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 64LL))(a1, &v25);
          v12 = 0;
          v4 = v17;
          if ( v17 >= 0 )
          {
            v18 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(*a2 + 64))(a2, &v26);
            v12 = 0;
            v4 = v18;
            if ( v18 >= 0 )
            {
              v19 = (unsigned __int16 *)v25;
              do
              {
                v20 = *(unsigned __int16 *)((char *)v19 + (_BYTE *)v26 - (_BYTE *)v25);
                v21 = *v19 - v20;
                if ( v21 )
                  break;
                ++v19;
              }
              while ( v20 );
              v12 = 0;
              if ( !v21 )
LABEL_16:
                v12 = 1;
            }
          }
        }
      }
    }
  }
  else
  {
    v12 = 0;
  }
  *a3 = v12;
  CoTaskMemFree(pv);
  CoTaskMemFree(v24);
  CoTaskMemFree(v25);
  CoTaskMemFree(v26);
  return v4;
}

```

## disassembly

```asm
0x180021c30  push    rbp
0x180021c32  push    rbx
0x180021c33  push    rsi
0x180021c34  push    rdi
0x180021c35  push    r14
0x180021c37  push    r15
0x180021c39  mov     rbp, rsp
0x180021c3c  sub     rsp, 28h
0x180021c40  mov     rax, [rdx]
0x180021c43  xor     edi, edi
0x180021c45  mov     rsi, rcx
0x180021c48  mov     [rbp+pv], rdi
0x180021c4c  mov     rcx, rdx
0x180021c4f  mov     [rbp+arg_8], rdi
0x180021c53  mov     r15, r8
0x180021c56  mov     [rbp+arg_10], rdi
0x180021c5a  mov     rax, [rax+18h]
0x180021c5e  mov     r14, rdx
0x180021c61  mov     [rbp+arg_18], rdi
0x180021c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c6a  mov     ebx, eax
0x180021c6c  mov     rcx, rsi
0x180021c6f  mov     rax, [rsi]
0x180021c72  mov     rax, [rax+18h]
0x180021c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c7b  cmp     eax, ebx
0x180021c7d  jnz     loc_180021D87
0x180021c83  mov     rax, [r14]
0x180021c86  mov     rcx, r14
0x180021c89  mov     rax, [rax+20h]
0x180021c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c92  mov     ebx, eax
0x180021c94  mov     rcx, rsi
0x180021c97  mov     rax, [rsi]
0x180021c9a  mov     rax, [rax+20h]
0x180021c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ca3  cmp     eax, ebx
0x180021ca5  jnz     loc_180021D87
0x180021cab  mov     rax, [rsi]
0x180021cae  lea     rdx, [rbp+pv]
0x180021cb2  mov     rcx, rsi
0x180021cb5  mov     rax, [rax+28h]
0x180021cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cbe  xor     ecx, ecx
0x180021cc0  mov     edi, eax
0x180021cc2  test    eax, eax
0x180021cc4  js      loc_180021D89
0x180021cca  mov     rax, [r14]
0x180021ccd  lea     rdx, [rbp+arg_8]
0x180021cd1  mov     rcx, r14
0x180021cd4  mov     rax, [rax+28h]
0x180021cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cdd  xor     ecx, ecx
0x180021cdf  mov     edi, eax
0x180021ce1  test    eax, eax
0x180021ce3  js      loc_180021D89
0x180021ce9  mov     rax, [rbp+pv]
0x180021ced  mov     rcx, [rbp+arg_8]
0x180021cf1  sub     rcx, rax
0x180021cf4  movzx   r8d, word ptr [rax]
0x180021cf8  movzx   edx, word ptr [rax+rcx]
0x180021cfc  sub     r8d, edx
0x180021cff  jnz     short loc_180021D09
0x180021d01  add     rax, 2
0x180021d05  test    edx, edx
0x180021d07  jnz     short loc_180021CF4
0x180021d09  xor     ecx, ecx
0x180021d0b  test    r8d, r8d
0x180021d0e  jnz     short loc_180021D89
0x180021d10  mov     rax, [rsi]
0x180021d13  mov     rcx, rsi
0x180021d16  mov     rax, [rax+18h]
0x180021d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d1f  test    eax, eax
0x180021d21  jz      short loc_180021D80
0x180021d23  mov     rax, [rsi]
0x180021d26  lea     rdx, [rbp+arg_10]
0x180021d2a  mov     rcx, rsi
0x180021d2d  mov     rax, [rax+40h]
0x180021d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d36  xor     ecx, ecx
0x180021d38  mov     edi, eax
0x180021d3a  test    eax, eax
0x180021d3c  js      short loc_180021D89
0x180021d3e  mov     rax, [r14]
0x180021d41  lea     rdx, [rbp+arg_18]
0x180021d45  mov     rcx, r14
0x180021d48  mov     rax, [rax+40h]
0x180021d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d51  xor     ecx, ecx
0x180021d53  mov     edi, eax
0x180021d55  test    eax, eax
0x180021d57  js      short loc_180021D89
0x180021d59  mov     rax, [rbp+arg_10]
0x180021d5d  mov     rcx, [rbp+arg_18]
0x180021d61  sub     rcx, rax
0x180021d64  movzx   edx, word ptr [rax]
0x180021d67  movzx   r8d, word ptr [rax+rcx]
0x180021d6c  sub     edx, r8d
0x180021d6f  jnz     short loc_180021D7A
0x180021d71  add     rax, 2
0x180021d75  test    r8d, r8d
0x180021d78  jnz     short loc_180021D64
0x180021d7a  xor     ecx, ecx
0x180021d7c  test    edx, edx
0x180021d7e  jnz     short loc_180021D89
0x180021d80  mov     ecx, 1
0x180021d85  jmp     short loc_180021D89
0x180021d87  xor     ecx, ecx
0x180021d89  mov     [r15], ecx
0x180021d8c  mov     rcx, [rbp+pv]; pv
0x180021d90  call    cs:__imp_CoTaskMemFree
0x180021d96  mov     rcx, [rbp+arg_8]; pv
0x180021d9a  call    cs:__imp_CoTaskMemFree
0x180021da0  mov     rcx, [rbp+arg_10]; pv
0x180021da4  call    cs:__imp_CoTaskMemFree
0x180021daa  mov     rcx, [rbp+arg_18]; pv
0x180021dae  call    cs:__imp_CoTaskMemFree
0x180021db4  mov     eax, edi
0x180021db6  add     rsp, 28h
0x180021dba  pop     r15
0x180021dbc  pop     r14
0x180021dbe  pop     rdi
0x180021dbf  pop     rsi
0x180021dc0  pop     rbx
0x180021dc1  pop     rbp
0x180021dc2  retn
```
