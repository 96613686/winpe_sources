# Validate_Parameters_SecretAgreementInterface

- ea: `0x1800585bc`
- end: `0x18005882c`
- name: `Validate_Parameters_SecretAgreementInterface`
- size: `624`
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
- `0x1800585bc`
- `0x180063170`

## string_xrefs

- `0x180058801`: `onecore\ds\security\cryptoapi\ncrypt\kdf\sp800_56a.c`

## pseudocode

```c
__int64 __fastcall Validate_Parameters_SecretAgreementInterface(__int64 a1, __int64 a2)
{
  int ParameterList; // eax
  __int64 v4; // r11
  __int64 v5; // rcx
  __int64 *v6; // rdi
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // r14
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r15
  int v16; // eax
  __int64 v17; // r11
  __int64 v18; // rdi
  __int64 v19; // r14
  __int64 v20; // rax
  __int64 v21; // r15
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  const void *v25; // r13
  unsigned int v26; // ebp
  int v27; // eax
  __int64 v28; // rax
  const void *v29; // r12
  unsigned int v30; // esi
  unsigned int v31; // eax
  unsigned int v32; // ecx
  unsigned int v33; // eax
  const void *v34; // r14
  const void *v35; // r15
  void *v36; // rax
  unsigned int v38; // [rsp+20h] [rbp-48h]
  void *Src; // [rsp+28h] [rbp-40h]
  unsigned int Size; // [rsp+80h] [rbp+18h]
  unsigned int v41; // [rsp+88h] [rbp+20h]

  ParameterList = QueryParameterList(a1, 0, 0);
  v6 = (__int64 *)(v5 + 8);
  if ( ParameterList >= 0 )
  {
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(*v6 + 16LL * ParameterList + 8);
    *(_DWORD *)(a2 + 24) = *(_DWORD *)(*v6 + 16LL * ParameterList);
  }
  v7 = QueryParameterList(v4, 8, 0);
  if ( v7 < 0 )
  {
    v9 = 152;
LABEL_5:
    v10 = -1073741811;
    v11 = 3221225485LL;
LABEL_32:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\sp800_56a.c", v9);
    return v10;
  }
  v12 = v7;
  v13 = QueryParameterList(v8, 9, 0);
  if ( v13 < 0 )
  {
    v9 = 169;
    goto LABEL_5;
  }
  v15 = v13;
  v16 = QueryParameterList(v14, 10, 0);
  if ( v16 < 0 )
  {
    v9 = 186;
    goto LABEL_5;
  }
  v18 = *v6;
  v19 = 2 * v12;
  v20 = 2LL * v16;
  v21 = 2 * v15;
  Size = *(_DWORD *)(v18 + 8 * v19);
  v41 = *(_DWORD *)(v18 + 8 * v21);
  Src = *(void **)(v18 + 8 * v20 + 8);
  v38 = *(_DWORD *)(v18 + 8 * v20);
  v22 = QueryParameterList(v17, 11, 0);
  if ( v22 < 0 )
  {
    v25 = 0;
    v26 = 0;
  }
  else
  {
    v24 = 2LL * v22;
    v25 = *(const void **)(v18 + 8 * v24 + 8);
    v26 = *(_DWORD *)(v18 + 8 * v24);
  }
  v27 = QueryParameterList(v23, 12, 0);
  if ( v27 < 0 )
  {
    v29 = 0;
    v30 = 0;
  }
  else
  {
    v28 = 2LL * v27;
    v29 = *(const void **)(v18 + 8 * v28 + 8);
    v30 = *(_DWORD *)(v18 + 8 * v28);
  }
  v31 = Size + v41;
  if ( Size + v41 < Size )
  {
    v9 = 234;
LABEL_31:
    *(_DWORD *)(a2 + 8) = -1;
    v11 = 3221225621LL;
    v10 = -1073741675;
    goto LABEL_32;
  }
  v32 = v31 + v38;
  if ( v31 + v38 < v38 )
  {
    v9 = 245;
    goto LABEL_31;
  }
  if ( v32 + v30 < v30 )
  {
    v9 = 256;
    goto LABEL_31;
  }
  v33 = v26 + v32 + v30;
  if ( v33 < v26 )
  {
    v9 = 267;
    goto LABEL_31;
  }
  v34 = *(const void **)(v18 + 8 * v19 + 8);
  v35 = *(const void **)(v18 + 8 * v21 + 8);
  *(_DWORD *)(a2 + 8) = v33;
  v36 = (void *)SafeAllocaAllocateFromHeap(v33);
  *(_QWORD *)a2 = v36;
  if ( !v36 )
  {
    v10 = -1073741801;
    v9 = 275;
    v11 = 3221225495LL;
    goto LABEL_32;
  }
  memcpy_0(v36, v34, Size);
  memcpy_0((void *)(Size + *(_QWORD *)a2), v35, v41);
  memcpy_0((void *)(*(_QWORD *)a2 + v41 + (unsigned __int64)Size), Src, v38);
  if ( v26 )
    memcpy_0((void *)(*(_QWORD *)a2 + Size + v38 + (unsigned __int64)v41), v25, v26);
  if ( v30 )
    memcpy_0((void *)(*(_QWORD *)a2 + Size + v41 + v38 + (unsigned __int64)v26), v29, v30);
  return 0;
}

```

## disassembly

```asm
0x1800585bc  mov     [rsp+arg_0], rbx
0x1800585c1  push    rbp
0x1800585c2  push    rsi
0x1800585c3  push    rdi
0x1800585c4  push    r12
0x1800585c6  push    r13
0x1800585c8  push    r14
0x1800585ca  push    r15
0x1800585cc  sub     rsp, 30h
0x1800585d0  mov     rbx, rdx
0x1800585d3  xor     r8d, r8d
0x1800585d6  xor     edx, edx
0x1800585d8  mov     r11, rcx
0x1800585db  call    QueryParameterList
0x1800585e0  lea     rdi, [rcx+8]
0x1800585e4  test    eax, eax
0x1800585e6  js      short loc_180058604
0x1800585e8  movsxd  r8, eax
0x1800585eb  mov     rax, [rdi]
0x1800585ee  add     r8, r8
0x1800585f1  mov     rcx, [rax+r8*8+8]
0x1800585f6  mov     [rbx+10h], rcx
0x1800585fa  mov     rax, [rdi]
0x1800585fd  mov     ecx, [rax+r8*8]
0x180058601  mov     [rbx+18h], ecx
0x180058604  xor     r8d, r8d
0x180058607  mov     rcx, r11
0x18005860a  lea     edx, [r8+8]
0x18005860e  call    QueryParameterList
0x180058613  test    eax, eax
0x180058615  jns     short loc_18005862C
0x180058617  mov     r9d, 98h
0x18005861d  mov     ebx, 0C000000Dh
0x180058622  mov     ecx, 0C000000Dh
0x180058627  jmp     loc_180058801
0x18005862c  xor     r8d, r8d
0x18005862f  movsxd  r14, eax
0x180058632  lea     edx, [r8+9]
0x180058636  call    QueryParameterList
0x18005863b  test    eax, eax
0x18005863d  jns     short loc_180058647
0x18005863f  mov     r9d, 0A9h
0x180058645  jmp     short loc_18005861D
0x180058647  xor     r8d, r8d
0x18005864a  movsxd  r15, eax
0x18005864d  lea     edx, [r8+0Ah]
0x180058651  call    QueryParameterList
0x180058656  test    eax, eax
0x180058658  jns     short loc_180058662
0x18005865a  mov     r9d, 0BAh
0x180058660  jmp     short loc_18005861D
0x180058662  mov     rdi, [rdi]
0x180058665  xor     r8d, r8d
0x180058668  cdqe
0x18005866a  add     r14, r14
0x18005866d  add     rax, rax
0x180058670  add     r15, r15
0x180058673  lea     edx, [r8+0Bh]
0x180058677  mov     ecx, [rdi+r14*8]
0x18005867b  mov     dword ptr [rsp+68h+Size], ecx
0x180058682  mov     ecx, [rdi+r15*8]
0x180058686  mov     dword ptr [rsp+68h+arg_18], ecx
0x18005868d  mov     rcx, [rdi+rax*8+8]
0x180058692  mov     eax, [rdi+rax*8]
0x180058695  mov     [rsp+68h+Src], rcx
0x18005869a  mov     rcx, r11
0x18005869d  mov     dword ptr [rsp+68h+var_48], eax
0x1800586a1  call    QueryParameterList
0x1800586a6  test    eax, eax
0x1800586a8  js      short loc_1800586B9
0x1800586aa  cdqe
0x1800586ac  add     rax, rax
0x1800586af  mov     r13, [rdi+rax*8+8]
0x1800586b4  mov     ebp, [rdi+rax*8]
0x1800586b7  jmp     short loc_1800586BE
0x1800586b9  xor     r13d, r13d
0x1800586bc  xor     ebp, ebp
0x1800586be  xor     r8d, r8d
0x1800586c1  lea     edx, [r8+0Ch]
0x1800586c5  call    QueryParameterList
0x1800586ca  test    eax, eax
0x1800586cc  js      short loc_1800586DD
0x1800586ce  cdqe
0x1800586d0  add     rax, rax
0x1800586d3  mov     r12, [rdi+rax*8+8]
0x1800586d8  mov     esi, [rdi+rax*8]
0x1800586db  jmp     short loc_1800586E2
0x1800586dd  xor     r12d, r12d
0x1800586e0  xor     esi, esi
0x1800586e2  mov     eax, dword ptr [rsp+68h+arg_18]
0x1800586e9  add     eax, dword ptr [rsp+68h+Size]
0x1800586f0  cmp     eax, dword ptr [rsp+68h+Size]
0x1800586f7  jnb     short loc_180058704
0x1800586f9  mov     r9d, 0EAh
0x1800586ff  jmp     loc_1800587F0
0x180058704  mov     edx, dword ptr [rsp+68h+var_48]
0x180058708  lea     ecx, [rax+rdx]
0x18005870b  cmp     ecx, edx
0x18005870d  jnb     short loc_18005871A
0x18005870f  mov     r9d, 0F5h
0x180058715  jmp     loc_1800587F0
0x18005871a  lea     eax, [rcx+rsi]
0x18005871d  cmp     eax, esi
0x18005871f  jnb     short loc_18005872C
0x180058721  mov     r9d, 100h
0x180058727  jmp     loc_1800587F0
0x18005872c  add     eax, ebp
0x18005872e  cmp     eax, ebp
0x180058730  jb      loc_1800587EA
0x180058736  mov     r14, [rdi+r14*8+8]
0x18005873b  mov     r15, [rdi+r15*8+8]
0x180058740  mov     ecx, eax
0x180058742  mov     [rbx+8], eax
0x180058745  call    SafeAllocaAllocateFromHeap
0x18005874a  mov     [rbx], rax
0x18005874d  test    rax, rax
0x180058750  jnz     short loc_180058767
0x180058752  mov     ebx, 0C0000017h
0x180058757  mov     r9d, 113h
0x18005875d  mov     ecx, 0C0000017h
0x180058762  jmp     loc_180058801
0x180058767  mov     ecx, dword ptr [rsp+68h+Size]
0x18005876e  mov     rdx, r14; Src
0x180058771  mov     edi, ecx
0x180058773  mov     r8d, ecx; Size
0x180058776  mov     rcx, rax; void *
0x180058779  call    memcpy_0
0x18005877e  mov     rcx, [rbx]
0x180058781  mov     rdx, r15; Src
0x180058784  mov     r14d, dword ptr [rsp+68h+arg_18]
0x18005878c  add     rcx, rdi; void *
0x18005878f  mov     r8d, r14d; Size
0x180058792  call    memcpy_0
0x180058797  mov     r15d, dword ptr [rsp+68h+var_48]
0x18005879c  lea     rcx, [r14+rdi]
0x1800587a0  add     rcx, [rbx]; void *
0x1800587a3  mov     r8d, r15d; Size
0x1800587a6  mov     rdx, [rsp+68h+Src]; Src
0x1800587ab  call    memcpy_0
0x1800587b0  test    ebp, ebp
0x1800587b2  jz      short loc_1800587C9
0x1800587b4  lea     rcx, [r15+r14]
0x1800587b8  mov     r8d, ebp; Size
0x1800587bb  add     rcx, rdi
0x1800587be  mov     rdx, r13; Src
0x1800587c1  add     rcx, [rbx]; void *
0x1800587c4  call    memcpy_0
0x1800587c9  test    esi, esi
0x1800587cb  jz      short loc_1800587E6
0x1800587cd  mov     ecx, ebp
0x1800587cf  mov     rdx, r12; Src
0x1800587d2  add     rcx, r15
0x1800587d5  mov     r8d, esi; Size
0x1800587d8  add     rcx, r14
0x1800587db  add     rcx, rdi
0x1800587de  add     rcx, [rbx]; void *
0x1800587e1  call    memcpy_0
0x1800587e6  xor     ebx, ebx
0x1800587e8  jmp     short loc_180058814
0x1800587ea  mov     r9d, 10Bh
0x1800587f0  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1800587f7  mov     ecx, 0C0000095h
0x1800587fc  mov     ebx, 0C0000095h
0x180058801  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058808  lea     rdx, aStatus; "Status"
0x18005880f  call    DebugTraceError
0x180058814  mov     eax, ebx
0x180058816  mov     rbx, [rsp+68h+arg_0]
0x18005881b  add     rsp, 30h
0x18005881f  pop     r15
0x180058821  pop     r14
0x180058823  pop     r13
0x180058825  pop     r12
0x180058827  pop     rdi
0x180058828  pop     rsi
0x180058829  pop     rbp
0x18005882a  retn
```
