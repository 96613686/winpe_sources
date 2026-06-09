# Validate_Parameters_KeyDerivationInterface

- ea: `0x18007da3c`
- end: `0x18007dd25`
- name: `Validate_Parameters_KeyDerivationInterface`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007dd2c`

## callees

- `0x18000ecb0`
- `0x1800102a0`
- `0x180012a80`
- `0x180063170`
- `0x18007da3c`

## string_xrefs

- `0x18007dcfa`: `onecore\ds\security\cryptoapi\ncrypt\kdf\sp800_56a.c`

## pseudocode

```c
__int64 __fastcall Validate_Parameters_KeyDerivationInterface(__int64 a1, __int64 a2)
{
  int ParameterList; // eax
  __int64 v4; // r11
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r15
  __int64 v10; // rcx
  __int64 v11; // rbp
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // r12
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r11
  __int64 v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned int v23; // ebx
  __int64 v24; // rcx
  void *v25; // rcx
  size_t v26; // r8
  const void *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  size_t v31; // r15
  unsigned int v32; // r10d
  const void *v33; // rbp
  unsigned int v34; // edi
  const void *v35; // r13
  unsigned int v36; // esi
  int v37; // r9d
  size_t v38; // r12
  int v39; // r10d
  unsigned int v40; // r9d
  void *v41; // rax
  void *v43; // [rsp+20h] [rbp-48h]
  void *v44; // [rsp+28h] [rbp-40h]
  unsigned int Size; // [rsp+80h] [rbp+18h]
  void *Src; // [rsp+88h] [rbp+20h]

  ParameterList = QueryParameterList(a1, 0, 0);
  v6 = (_QWORD *)(v5 + 8);
  if ( ParameterList >= 0 )
  {
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(*v6 + 16LL * ParameterList + 8);
    *(_DWORD *)(a2 + 24) = *(_DWORD *)(*v6 + 16LL * ParameterList);
  }
  v7 = (int)QueryParameterList(v4, 17, 0);
  v9 = (int)QueryParameterList(v8, 8, 0);
  v11 = (int)QueryParameterList(v10, 9, 0);
  v13 = (int)QueryParameterList(v12, 10, 0);
  v15 = (int)QueryParameterList(v14, 11, 0);
  v17 = (int)QueryParameterList(v16, 12, 0);
  if ( (int)v9 < 0 && (int)v11 < 0 && (int)v13 < 0 )
  {
    if ( (int)v7 >= 0 )
    {
      v19 = 2 * v7;
      v20 = *(unsigned int *)(*v6 + 8 * v19);
      *(_DWORD *)(a2 + 8) = v20;
      v21 = SafeAllocaAllocateFromHeap(v20);
      *(_QWORD *)a2 = v21;
      if ( !v21 )
      {
        v22 = 421;
LABEL_9:
        v23 = -1073741801;
        v24 = 3221225495LL;
LABEL_41:
        DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\sp800_56a.c", v22);
        return v23;
      }
      v25 = (void *)v21;
      v26 = *(unsigned int *)(a2 + 8);
      v27 = *(const void **)(*v6 + 8 * v19 + 8);
      goto LABEL_11;
    }
    goto LABEL_39;
  }
  if ( (int)v7 >= 0 )
  {
    v22 = 405;
LABEL_40:
    v24 = 3221225485LL;
    v23 = -1073741811;
    goto LABEL_41;
  }
  if ( (int)v9 < 0 || (int)v11 < 0 || (int)v13 < 0 )
  {
LABEL_39:
    v22 = 443;
    goto LABEL_40;
  }
  v28 = *(_QWORD *)(v18 + 8);
  v29 = 2 * v9;
  v30 = 2 * v11;
  v31 = *(unsigned int *)(v28 + 16 * v9);
  v32 = *(_DWORD *)(v28 + 16 * v11);
  Size = v32;
  if ( (int)v15 < 0 )
  {
    v33 = 0;
    v34 = 0;
  }
  else
  {
    v33 = *(const void **)(v28 + 16 * v15 + 8);
    v34 = *(_DWORD *)(v28 + 16 * v15);
  }
  if ( (int)v17 < 0 )
  {
    v35 = 0;
    v36 = 0;
  }
  else
  {
    v35 = *(const void **)(v28 + 16 * v17 + 8);
    v36 = *(_DWORD *)(v28 + 16 * v17);
  }
  v37 = v32 + v31;
  if ( v32 + (unsigned int)v31 < (unsigned int)v31 )
  {
    v22 = 486;
    goto LABEL_27;
  }
  v38 = *(unsigned int *)(v28 + 16 * v13);
  v39 = v38 + v37;
  if ( (int)v38 + v37 < (unsigned int)v38 )
  {
    v22 = 497;
LABEL_27:
    *(_DWORD *)(a2 + 8) = -1;
    v24 = 3221225621LL;
    v23 = -1073741675;
    goto LABEL_41;
  }
  if ( v39 + v36 < v36 )
  {
    v22 = 508;
    goto LABEL_27;
  }
  v40 = v34 + v39 + v36;
  if ( v40 < v34 )
  {
    v22 = 519;
    goto LABEL_27;
  }
  Src = *(void **)(v28 + 8 * v29 + 8);
  v43 = *(void **)(v28 + 8 * v30 + 8);
  v44 = *(void **)(v28 + 16 * v13 + 8);
  *(_DWORD *)(a2 + 8) = v40;
  v41 = (void *)SafeAllocaAllocateFromHeap(v40);
  *(_QWORD *)a2 = v41;
  if ( !v41 )
  {
    v22 = 527;
    goto LABEL_9;
  }
  memcpy_0(v41, Src, v31);
  memcpy_0((void *)(v31 + *(_QWORD *)a2), v43, Size);
  memcpy_0((void *)(*(_QWORD *)a2 + Size + v31), v44, v38);
  if ( v34 )
    memcpy_0((void *)(*(_QWORD *)a2 + v31 + v38 + Size), v33, v34);
  if ( v36 )
  {
    v27 = v35;
    v26 = v36;
    v25 = (void *)(*(_QWORD *)a2 + v31 + Size + v38 + v34);
LABEL_11:
    memcpy_0(v25, v27, v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18007da3c  mov     [rsp+arg_0], rbx
0x18007da41  push    rbp
0x18007da42  push    rsi
0x18007da43  push    rdi
0x18007da44  push    r12
0x18007da46  push    r13
0x18007da48  push    r14
0x18007da4a  push    r15
0x18007da4c  sub     rsp, 30h
0x18007da50  mov     rbx, rdx
0x18007da53  xor     r8d, r8d
0x18007da56  xor     edx, edx
0x18007da58  mov     r11, rcx
0x18007da5b  call    QueryParameterList
0x18007da60  lea     rdi, [rcx+8]
0x18007da64  test    eax, eax
0x18007da66  js      short loc_18007DA84
0x18007da68  movsxd  r8, eax
0x18007da6b  mov     rax, [rdi]
0x18007da6e  add     r8, r8
0x18007da71  mov     rcx, [rax+r8*8+8]
0x18007da76  mov     [rbx+10h], rcx
0x18007da7a  mov     rax, [rdi]
0x18007da7d  mov     ecx, [rax+r8*8]
0x18007da81  mov     [rbx+18h], ecx
0x18007da84  xor     r8d, r8d
0x18007da87  mov     rcx, r11
0x18007da8a  lea     edx, [r8+11h]
0x18007da8e  call    QueryParameterList
0x18007da93  xor     r8d, r8d
0x18007da96  movsxd  rsi, eax
0x18007da99  lea     edx, [r8+8]
0x18007da9d  call    QueryParameterList
0x18007daa2  xor     r8d, r8d
0x18007daa5  movsxd  r15, eax
0x18007daa8  lea     edx, [r8+9]
0x18007daac  call    QueryParameterList
0x18007dab1  xor     r8d, r8d
0x18007dab4  movsxd  rbp, eax
0x18007dab7  lea     edx, [r8+0Ah]
0x18007dabb  call    QueryParameterList
0x18007dac0  xor     r8d, r8d
0x18007dac3  movsxd  r14, eax
0x18007dac6  lea     edx, [r8+0Bh]
0x18007daca  call    QueryParameterList
0x18007dacf  xor     r8d, r8d
0x18007dad2  movsxd  r12, eax
0x18007dad5  lea     edx, [r8+0Ch]
0x18007dad9  call    QueryParameterList
0x18007dade  movsxd  r9, eax
0x18007dae1  test    r15d, r15d
0x18007dae4  jns     short loc_18007DB40
0x18007dae6  test    ebp, ebp
0x18007dae8  jns     short loc_18007DB40
0x18007daea  test    r14d, r14d
0x18007daed  jns     short loc_18007DB40
0x18007daef  test    esi, esi
0x18007daf1  js      loc_18007DCEA
0x18007daf7  mov     rax, [rdi]
0x18007dafa  add     rsi, rsi
0x18007dafd  mov     ecx, [rax+rsi*8]
0x18007db00  mov     [rbx+8], ecx
0x18007db03  call    SafeAllocaAllocateFromHeap
0x18007db08  mov     [rbx], rax
0x18007db0b  test    rax, rax
0x18007db0e  jnz     short loc_18007DB25
0x18007db10  mov     r9d, 1A5h
0x18007db16  mov     ebx, 0C0000017h
0x18007db1b  mov     ecx, 0C0000017h
0x18007db20  jmp     loc_18007DCFA
0x18007db25  mov     rdx, [rdi]
0x18007db28  mov     rcx, rax; void *
0x18007db2b  mov     r8d, [rbx+8]; Size
0x18007db2f  mov     rdx, [rdx+rsi*8+8]; Src
0x18007db34  call    memcpy_0
0x18007db39  xor     ebx, ebx
0x18007db3b  jmp     loc_18007DD0D
0x18007db40  test    esi, esi
0x18007db42  js      short loc_18007DB4F
0x18007db44  mov     r9d, 195h
0x18007db4a  jmp     loc_18007DCF0
0x18007db4f  test    r15d, r15d
0x18007db52  js      loc_18007DCEA
0x18007db58  test    ebp, ebp
0x18007db5a  js      loc_18007DCEA
0x18007db60  test    r14d, r14d
0x18007db63  js      loc_18007DCEA
0x18007db69  mov     rcx, [r11+8]
0x18007db6d  mov     rdx, r15
0x18007db70  add     rdx, rdx
0x18007db73  mov     r8, rbp
0x18007db76  add     r8, r8
0x18007db79  mov     r15d, [rcx+rdx*8]
0x18007db7d  mov     r10d, [rcx+r8*8]
0x18007db81  mov     dword ptr [rsp+68h+Size], r10d
0x18007db89  test    r12d, r12d
0x18007db8c  js      short loc_18007DB9E
0x18007db8e  mov     rax, r12
0x18007db91  add     rax, rax
0x18007db94  mov     rbp, [rcx+rax*8+8]
0x18007db99  mov     edi, [rcx+rax*8]
0x18007db9c  jmp     short loc_18007DBA2
0x18007db9e  xor     ebp, ebp
0x18007dba0  xor     edi, edi
0x18007dba2  test    r9d, r9d
0x18007dba5  js      short loc_18007DBB7
0x18007dba7  mov     rax, r9
0x18007dbaa  add     rax, rax
0x18007dbad  mov     r13, [rcx+rax*8+8]
0x18007dbb2  mov     esi, [rcx+rax*8]
0x18007dbb5  jmp     short loc_18007DBBC
0x18007dbb7  xor     r13d, r13d
0x18007dbba  xor     esi, esi
0x18007dbbc  lea     r9d, [r10+r15]
0x18007dbc0  cmp     r9d, r15d
0x18007dbc3  jb      loc_18007DCDF
0x18007dbc9  mov     rax, r14
0x18007dbcc  add     rax, rax
0x18007dbcf  mov     r12d, [rcx+rax*8]
0x18007dbd3  lea     r10d, [r12+r9]
0x18007dbd7  cmp     r10d, r12d
0x18007dbda  jnb     short loc_18007DBF8
0x18007dbdc  mov     r9d, 1F1h
0x18007dbe2  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18007dbe9  mov     ecx, 0C0000095h
0x18007dbee  mov     ebx, 0C0000095h
0x18007dbf3  jmp     loc_18007DCFA
0x18007dbf8  lea     r9d, [r10+rsi]
0x18007dbfc  cmp     r9d, esi
0x18007dbff  jnb     short loc_18007DC09
0x18007dc01  mov     r9d, 1FCh
0x18007dc07  jmp     short loc_18007DBE2
0x18007dc09  add     r9d, edi
0x18007dc0c  cmp     r9d, edi
0x18007dc0f  jb      loc_18007DCD4
0x18007dc15  mov     rdx, [rcx+rdx*8+8]
0x18007dc1a  mov     rax, [rcx+rax*8+8]
0x18007dc1f  mov     [rsp+68h+Src], rdx
0x18007dc27  mov     rdx, [rcx+r8*8+8]
0x18007dc2c  mov     ecx, r9d
0x18007dc2f  mov     [rsp+68h+var_48], rdx
0x18007dc34  mov     [rsp+68h+var_40], rax
0x18007dc39  mov     [rbx+8], r9d
0x18007dc3d  call    SafeAllocaAllocateFromHeap
0x18007dc42  mov     [rbx], rax
0x18007dc45  test    rax, rax
0x18007dc48  jnz     short loc_18007DC55
0x18007dc4a  mov     r9d, 20Fh
0x18007dc50  jmp     loc_18007DB16
0x18007dc55  mov     rdx, [rsp+68h+Src]; Src
0x18007dc5d  mov     r8, r15; Size
0x18007dc60  mov     rcx, rax; void *
0x18007dc63  mov     r14, r15
0x18007dc66  call    memcpy_0
0x18007dc6b  mov     rcx, [rbx]
0x18007dc6e  mov     r15d, dword ptr [rsp+68h+Size]
0x18007dc76  add     rcx, r14; void *
0x18007dc79  mov     rdx, [rsp+68h+var_48]; Src
0x18007dc7e  mov     r8d, r15d; Size
0x18007dc81  call    memcpy_0
0x18007dc86  mov     rdx, [rsp+68h+var_40]; Src
0x18007dc8b  lea     rcx, [r15+r14]
0x18007dc8f  add     rcx, [rbx]; void *
0x18007dc92  mov     r8, r12; Size
0x18007dc95  call    memcpy_0
0x18007dc9a  test    edi, edi
0x18007dc9c  jz      short loc_18007DCB3
0x18007dc9e  lea     rcx, [r12+r15]
0x18007dca2  mov     r8d, edi; Size
0x18007dca5  add     rcx, r14
0x18007dca8  mov     rdx, rbp; Src
0x18007dcab  add     rcx, [rbx]; void *
0x18007dcae  call    memcpy_0
0x18007dcb3  test    esi, esi
0x18007dcb5  jz      loc_18007DB39
0x18007dcbb  mov     ecx, edi
0x18007dcbd  mov     rdx, r13
0x18007dcc0  add     rcx, r12
0x18007dcc3  mov     r8d, esi
0x18007dcc6  add     rcx, r15
0x18007dcc9  add     rcx, r14
0x18007dccc  add     rcx, [rbx]
0x18007dccf  jmp     loc_18007DB34
0x18007dcd4  mov     r9d, 207h
0x18007dcda  jmp     loc_18007DBE2
0x18007dcdf  mov     r9d, 1E6h
0x18007dce5  jmp     loc_18007DBE2
0x18007dcea  mov     r9d, 1BBh
0x18007dcf0  mov     ecx, 0C000000Dh
0x18007dcf5  mov     ebx, 0C000000Dh
0x18007dcfa  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007dd01  lea     rdx, aStatus; "Status"
0x18007dd08  call    DebugTraceError
0x18007dd0d  mov     eax, ebx
0x18007dd0f  mov     rbx, [rsp+68h+arg_0]
0x18007dd14  add     rsp, 30h
0x18007dd18  pop     r15
0x18007dd1a  pop     r14
0x18007dd1c  pop     r13
0x18007dd1e  pop     r12
0x18007dd20  pop     rdi
0x18007dd21  pop     rsi
0x18007dd22  pop     rbp
0x18007dd23  retn
```
