# RtlWriteDataIntoSmartLBlobWritingContext

- ea: `0x140072350`
- end: `0x1400726d1`
- name: `RtlWriteDataIntoSmartLBlobWritingContext`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x14006db20`

## callees

- `0x140071010`
- `0x140071c20`
- `0x140071cbc`
- `0x140072350`
- `0x140072764`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400725c1`
- `msvcrt!memcpy_s` at `0x14007265d`
- `msvcrt!memcpy_s` at `0x1400725c1`
- `msvcrt!memcpy_s` at `0x14007265d`
- `ntdll!RtlRaiseStatus` at `0x140072687`
- `ntdll!RtlRaiseStatus` at `0x140072687`

## string_xrefs

- `0x140072395`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x1400723e0`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x14007240c`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x140072479`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x1400724c4`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x140072525`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x1400725f2`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x14007248a`: `BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)`

## pseudocode

```c
__int64 __fastcall RtlWriteDataIntoSmartLBlobWritingContext(__int64 a1, char **a2)
{
  const char *v4; // rax
  __int64 result; // rax
  rsize_t *v6; // rcx
  char *v7; // rsi
  char *v8; // rdi
  rsize_t v9; // r14
  unsigned __int64 *v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r8
  char *v14; // rax
  unsigned __int64 v15; // rdx
  char *v16; // rcx
  char *v17; // rax
  __int64 v18; // rdx
  char *v19; // rcx
  char *v20; // rax
  char *v21; // rdx
  __int128 v22; // [rsp+20h] [rbp-30h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h]
  const char *v24; // [rsp+38h] [rbp-18h]
  unsigned __int64 v25; // [rsp+40h] [rbp-10h] BYREF

  if ( !a1 )
  {
    v23 = 1774;
    *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Data";
LABEL_3:
    v24 = v4;
    RtlReportErrorOrigination(&v22, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !(unsigned __int8)RtlIsLBlobValid(a1) )
  {
    v23 = 1775;
    *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "::RtlIsLBlobValid(Data)";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v23 = 1776;
    *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Context";
    goto LABEL_3;
  }
  v7 = a2[1];
  v8 = *a2;
  v9 = *v6;
  if ( *v6 <= v7 - *a2 )
    goto LABEL_35;
  if ( !a2[6] )
    return 3221225507LL;
  v10 = (unsigned __int64 *)a2[4];
  v22 = 0;
  v11 = *v10;
  v25 = 0;
  v12 = v11 + v9;
  if ( v11 + v9 < v9 )
  {
    v23 = 1794;
    *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v24 = "BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)";
    RtlReportErrorOrigination(&v22, a2, 3221225621LL);
    return 3221225621LL;
  }
  v13 = (unsigned __int64)a2[3];
  if ( v12 > v13 )
  {
    v23 = 1797;
    *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
    v24 = 0;
    *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    RtlReportErrorOrigination(&v22, a2, 3221226539LL);
    return 3221226539LL;
  }
  v14 = a2[8];
  v15 = v11 + v9;
  if ( v14 )
    result = ((__int64 (__fastcall *)(char **, unsigned __int64, unsigned __int64 *))v14)(a2, v15, &v25);
  else
    result = RtlpSmartLBlobWritingContextResizePolicy(v11, v15, v13, &v25);
  if ( (int)result >= 0 )
  {
    if ( v25 < v12 )
    {
      v23 = 1813;
      *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
      v24 = 0;
      *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
      RtlReportErrorOrigination(&v22, v25, 3221225507LL);
      return 3221225507LL;
    }
    v16 = a2[6];
    v17 = a2[4];
    if ( v17 == v16 )
    {
      if ( *((_QWORD *)v17 + 1) < v25 )
      {
        result = RtlReallocateLBlob(v16, v25, a2[6]);
        if ( (int)result < 0 )
          return result;
      }
    }
    else
    {
      if ( v17 != a2[5] )
        RtlRaiseStatus(-1073741595);
      if ( *((_QWORD *)v16 + 1) < v25 )
      {
        result = RtlReallocateLBlob(v16, v25, a2[6]);
        if ( (int)result < 0 )
          return result;
        v16 = a2[6];
      }
      if ( memcpy_s(
             *((void *const *)v16 + 2),
             *((_QWORD *)v16 + 1),
             *((const void *const *)a2[4] + 2),
             *(_QWORD *)a2[4] != 0) )
      {
        v23 = 1839;
        v24 = 0;
LABEL_31:
        *(_QWORD *)&v22 = "onecore\\base\\lstring\\lblob.cpp";
        *((_QWORD *)&v22 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
        RtlReportErrorOrigination(&v22, v18, 3221684490LL);
        return 3221684490LL;
      }
      *(_QWORD *)a2[6] = *(_QWORD *)a2[4];
      v19 = a2[7];
      v20 = a2[6];
      a2[4] = v20;
      if ( v19 )
        *(_QWORD *)v19 = v20;
    }
    v21 = a2[4];
    v8 = (char *)(*(_QWORD *)v21 + *((_QWORD *)v21 + 2));
    *a2 = v8;
    v7 = (char *)(*((_QWORD *)v21 + 2) + *((_QWORD *)v21 + 1));
    a2[1] = v7;
LABEL_35:
    if ( v9 )
    {
      if ( memcpy_s(v8, v7 - v8, *(const void *const *)(a1 + 16), v9) )
      {
        v23 = 1871;
        v24 = 0;
        goto LABEL_31;
      }
      *(_QWORD *)a2[4] = &v8[v9 - *((_QWORD *)a2[4] + 2)];
      *a2 = &v8[v9];
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140072350  mov     [rsp-28h+arg_10], rbx
0x140072355  mov     [rsp-28h+arg_18], rsi
0x14007235a  push    rbp
0x14007235b  push    rdi
0x14007235c  push    r13
0x14007235e  push    r14
0x140072360  push    r15
0x140072362  mov     rbp, rsp
0x140072365  sub     rsp, 50h
0x140072369  mov     rax, cs:__security_cookie
0x140072370  xor     rax, rsp
0x140072373  mov     [rbp+var_8], rax
0x140072377  mov     rbx, rdx
0x14007237a  mov     r15, rcx
0x14007237d  test    rcx, rcx
0x140072380  jnz     short loc_1400723C4
0x140072382  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140072389  mov     [rbp+var_20], 6EEh
0x140072391  mov     qword ptr [rbp+var_30], rax
0x140072395  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x14007239c  mov     qword ptr [rbp+var_30+8], rax
0x1400723a0  lea     rax, aNotNullCheckFa_4; "Not-null check failed: Data"
0x1400723a7  mov     r8d, 0C000000Dh
0x1400723ad  mov     [rbp+var_18], rax
0x1400723b1  lea     rcx, [rbp+var_30]
0x1400723b5  call    RtlReportErrorOrigination
0x1400723ba  mov     eax, 0C000000Dh
0x1400723bf  jmp     loc_1400726AB
0x1400723c4  call    RtlIsLBlobValid
0x1400723c9  test    al, al
0x1400723cb  jnz     short loc_1400723F4
0x1400723cd  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1400723d4  mov     [rbp+var_20], 6EFh
0x1400723dc  mov     qword ptr [rbp+var_30], rax
0x1400723e0  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x1400723e7  mov     qword ptr [rbp+var_30+8], rax
0x1400723eb  lea     rax, aRtlislblobvali_0; "::RtlIsLBlobValid(Data)"
0x1400723f2  jmp     short loc_1400723A7
0x1400723f4  test    rbx, rbx
0x1400723f7  jnz     short loc_140072420
0x1400723f9  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140072400  mov     [rbp+var_20], 6F0h
0x140072408  mov     qword ptr [rbp+var_30], rax
0x14007240c  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x140072413  mov     qword ptr [rbp+var_30+8], rax
0x140072417  lea     rax, aNotNullCheckFa_1; "Not-null check failed: Context"
0x14007241e  jmp     short loc_1400723A7
0x140072420  mov     rsi, [rdx+8]
0x140072424  mov     rdi, [rdx]
0x140072427  mov     rax, rsi
0x14007242a  mov     r14, [rcx]
0x14007242d  sub     rax, rdi
0x140072430  cmp     r14, rax
0x140072433  jbe     loc_140072648
0x140072439  cmp     qword ptr [rdx+30h], 0
0x14007243e  jz      loc_14007253F
0x140072444  mov     rax, [rdx+20h]
0x140072448  xor     r13d, r13d
0x14007244b  xorps   xmm0, xmm0
0x14007244e  movups  [rbp+var_30], xmm0
0x140072452  mov     rcx, [rax]; unsigned __int64
0x140072455  mov     [rbp+var_10], r13
0x140072459  lea     rdi, [rcx+r14]
0x14007245d  cmp     rdi, r14
0x140072460  jnb     short loc_1400724A4
0x140072462  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140072469  mov     [rbp+var_20], 702h
0x140072471  mov     qword ptr [rbp+var_30], rax
0x140072475  lea     rcx, [rbp+var_30]
0x140072479  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x140072480  mov     r8d, 0C0000095h
0x140072486  mov     qword ptr [rbp+var_30+8], rax
0x14007248a  lea     rax, aBuclRtlAddSize_0; "BUCL::Rtl::Add<SIZE_T>(DataLength, OldL"...
0x140072491  mov     [rbp+var_18], rax
0x140072495  call    RtlReportErrorOrigination
0x14007249a  mov     eax, 0C0000095h
0x14007249f  jmp     loc_1400726AB
0x1400724a4  mov     r8, [rdx+18h]; unsigned __int64
0x1400724a8  cmp     rdi, r8
0x1400724ab  jbe     short loc_1400724E8
0x1400724ad  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1400724b4  mov     [rbp+var_20], 705h
0x1400724bc  mov     qword ptr [rbp+var_30], rax
0x1400724c0  lea     rcx, [rbp+var_30]
0x1400724c4  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x1400724cb  mov     [rbp+var_18], r13
0x1400724cf  mov     r8d, 0C000042Bh
0x1400724d5  mov     qword ptr [rbp+var_30+8], rax
0x1400724d9  call    RtlReportErrorOrigination
0x1400724de  mov     eax, 0C000042Bh
0x1400724e3  jmp     loc_1400726AB
0x1400724e8  mov     rax, [rdx+40h]
0x1400724ec  mov     rdx, rdi; unsigned __int64
0x1400724ef  test    rax, rax
0x1400724f2  jnz     short loc_140072549
0x1400724f4  lea     r9, [rbp+var_10]; unsigned __int64 *
0x1400724f8  call    ?RtlpSmartLBlobWritingContextResizePolicy@@YAJ_K00PEA_K@Z; RtlpSmartLBlobWritingContextResizePolicy(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1400724fd  test    eax, eax
0x1400724ff  js      loc_1400726AB
0x140072505  mov     rdx, [rbp+var_10]
0x140072509  cmp     rdx, rdi
0x14007250c  jnb     short loc_140072557
0x14007250e  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140072515  mov     [rbp+var_20], 715h
0x14007251d  mov     qword ptr [rbp+var_30], rax
0x140072521  lea     rcx, [rbp+var_30]
0x140072525  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x14007252c  mov     [rbp+var_18], r13
0x140072530  mov     r8d, 0C0000023h
0x140072536  mov     qword ptr [rbp+var_30+8], rax
0x14007253a  call    RtlReportErrorOrigination
0x14007253f  mov     eax, 0C0000023h
0x140072544  jmp     loc_1400726AB
0x140072549  lea     r8, [rbp+var_10]
0x14007254d  mov     rcx, rbx
0x140072550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072555  jmp     short loc_1400724FD
0x140072557  mov     rcx, [rbx+30h]
0x14007255b  mov     rax, [rbx+20h]
0x14007255f  cmp     rax, rcx
0x140072562  jnz     short loc_140072583
0x140072564  cmp     [rax+8], rdx
0x140072568  jnb     loc_14007262E
0x14007256e  mov     r8, rcx
0x140072571  call    RtlReallocateLBlob
0x140072576  test    eax, eax
0x140072578  jns     loc_14007262E
0x14007257e  jmp     loc_1400726AB
0x140072583  cmp     rax, [rbx+28h]
0x140072587  jnz     loc_140072682
0x14007258d  cmp     [rcx+8], rdx
0x140072591  jnb     short loc_1400725A7
0x140072593  mov     r8, rcx
0x140072596  call    RtlReallocateLBlob
0x14007259b  test    eax, eax
0x14007259d  js      loc_1400726AB
0x1400725a3  mov     rcx, [rbx+30h]
0x1400725a7  mov     r8, [rbx+20h]
0x1400725ab  xor     r9d, r9d
0x1400725ae  mov     rdx, [rcx+8]; DestinationSize
0x1400725b2  mov     rcx, [rcx+10h]; Destination
0x1400725b6  cmp     [r8], r9
0x1400725b9  mov     r8, [r8+10h]; Source
0x1400725bd  setnz   r9b; SourceSize
0x1400725c1  call    cs:__imp_memcpy_s
0x1400725c8  nop     dword ptr [rax+rax+00h]
0x1400725cd  test    eax, eax
0x1400725cf  jz      short loc_14007260C
0x1400725d1  mov     [rbp+var_20], 72Fh
0x1400725d9  mov     [rbp+var_18], r13
0x1400725dd  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1400725e4  mov     r8d, 0C007010Ah
0x1400725ea  mov     qword ptr [rbp+var_30], rax
0x1400725ee  lea     rcx, [rbp+var_30]
0x1400725f2  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x1400725f9  mov     qword ptr [rbp+var_30+8], rax
0x1400725fd  call    RtlReportErrorOrigination
0x140072602  mov     eax, 0C007010Ah
0x140072607  jmp     loc_1400726AB
0x14007260c  mov     rax, [rbx+20h]
0x140072610  mov     rcx, [rbx+30h]
0x140072614  mov     rax, [rax]
0x140072617  mov     [rcx], rax
0x14007261a  mov     rcx, [rbx+38h]
0x14007261e  mov     rax, [rbx+30h]
0x140072622  mov     [rbx+20h], rax
0x140072626  test    rcx, rcx
0x140072629  jz      short loc_14007262E
0x14007262b  mov     [rcx], rax
0x14007262e  mov     rdx, [rbx+20h]
0x140072632  mov     rdi, [rdx+10h]
0x140072636  add     rdi, [rdx]
0x140072639  mov     [rbx], rdi
0x14007263c  mov     rsi, [rdx+8]
0x140072640  add     rsi, [rdx+10h]
0x140072644  mov     [rbx+8], rsi
0x140072648  test    r14, r14
0x14007264b  jz      short loc_1400726A9
0x14007264d  mov     r8, [r15+10h]; Source
0x140072651  sub     rsi, rdi
0x140072654  mov     rdx, rsi; DestinationSize
0x140072657  mov     r9, r14; SourceSize
0x14007265a  mov     rcx, rdi; Destination
0x14007265d  call    cs:__imp_memcpy_s
0x140072664  nop     dword ptr [rax+rax+00h]
0x140072669  test    eax, eax
0x14007266b  jz      short loc_140072694
0x14007266d  mov     [rbp+var_20], 74Fh
0x140072675  mov     [rbp+var_18], 0
0x14007267d  jmp     loc_1400725DD
0x140072682  mov     ecx, 0C00000E5h; Status
0x140072687  call    cs:__imp_RtlRaiseStatus
0x14007268e  nop     dword ptr [rax+rax+00h]
0x140072693  int     3; Trap to Debugger
0x140072694  mov     rcx, [rbx+20h]
0x140072698  lea     rdx, [r14+rdi]
0x14007269c  mov     rax, rdx
0x14007269f  sub     rax, [rcx+10h]
0x1400726a3  mov     [rcx], rax
0x1400726a6  mov     [rbx], rdx
0x1400726a9  xor     eax, eax
0x1400726ab  mov     rcx, [rbp+var_8]
0x1400726af  xor     rcx, rsp; StackCookie
0x1400726b2  call    __security_check_cookie
0x1400726b7  lea     r11, [rsp+50h+var_s0]
0x1400726bc  mov     rbx, [r11+40h]
0x1400726c0  mov     rsi, [r11+48h]
0x1400726c4  mov     rsp, r11
0x1400726c7  pop     r15
0x1400726c9  pop     r14
0x1400726cb  pop     r13
0x1400726cd  pop     rdi
0x1400726ce  pop     rbp
0x1400726cf  retn
```
