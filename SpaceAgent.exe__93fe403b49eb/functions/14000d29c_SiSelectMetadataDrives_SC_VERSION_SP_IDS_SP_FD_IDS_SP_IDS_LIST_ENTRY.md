# SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)

- ea: `0x14000d29c`
- end: `0x14000d703`
- name: `?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z`
- size: `1127`
- prototype: `__int64 __fastcall(unsigned int, __int64, int *, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b02c`
- `0x14000e860`
- `0x140012fb0`

## callees

- `0x140001caf`
- `0x14000ca04`
- `0x14000d29c`
- `0x1400140ac`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000d650`
- `KERNEL32!LocalFree` at `0x14000d650`
- `KERNEL32!SetLastError` at `0x14000d3a7`
- `KERNEL32!SetLastError` at `0x14000d5dd`
- `KERNEL32!SetLastError` at `0x14000d3a7`
- `KERNEL32!SetLastError` at `0x14000d5dd`
- `KERNEL32!LocalAlloc` at `0x14000d397`
- `KERNEL32!LocalAlloc` at `0x14000d397`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000d59c`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000d642`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000d59c`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000d642`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x14000d53a`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x14000d53a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000d5be`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000d62d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000d5be`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000d62d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x14000d4ae`
- `ntdll!RtlInitializeGenericTableAvl` at `0x14000d4ae`
- `bcrypt!BCryptGenRandom` at `0x14000d521`
- `bcrypt!BCryptGenRandom` at `0x14000d521`

## pseudocode

```c
__int64 __fastcall SiSelectMetadataDrives(unsigned int a1, __int64 a2, int *a3, __int64 a4, __int64 *a5)
{
  unsigned int v8; // edx
  __int64 v9; // rcx
  int v10; // r13d
  __int64 *i; // rax
  _DWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // rax
  int v16; // r15d
  int v17; // ebx
  _QWORD **v18; // rsi
  _QWORD *v19; // rcx
  unsigned int v20; // edx
  __int64 v21; // rax
  unsigned int v22; // r14d
  struct _RTL_AVL_TABLE *v23; // r12
  struct _RTL_AVL_TABLE *Parent; // rsi
  _QWORD *v25; // rax
  _QWORD *v26; // r15
  _QWORD *v27; // rdx
  int LeftChild; // eax
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  DWORD v31; // ecx
  signed int v32; // esi
  struct _RTL_AVL_TABLE *j; // rbx
  _QWORD *v34; // rax
  BOOLEAN v35; // al
  _QWORD **v36; // rbx
  _QWORD *v37; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rdx
  _QWORD *v40; // r14
  struct _RTL_AVL_TABLE *v41; // rsi
  PVOID v42; // rax
  __int64 *v43; // rcx
  __int64 *v44; // rax
  __int64 v45; // rax
  PVOID TableContext; // [rsp+20h] [rbp-A1h]
  __int64 *v48; // [rsp+28h] [rbp-99h]
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v50; // [rsp+38h] [rbp-89h] BYREF
  __int64 *v51; // [rsp+40h] [rbp-81h]
  PVOID v52; // [rsp+48h] [rbp-79h] BYREF
  _QWORD *Buffer; // [rsp+50h] [rbp-71h] BYREF
  PVOID RestartKey; // [rsp+58h] [rbp-69h] BYREF
  __int64 v55; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v56[11]; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v57[2]; // [rsp+C0h] [rbp-1h] BYREF

  v55 = 0;
  memset_0(v56, 0, 0x68u);
  Buffer = 0;
  v51 = &v50;
  v8 = 0;
  RestartKey = 0;
  v50 = (__int64)&v50;
  *(_DWORD *)NewElement = 1;
  do
  {
    v9 = 2LL * (int)v8++;
    v56[v9] = &v56[v9 - 1];
    v56[v9 - 1] = &v56[v9 - 1];
  }
  while ( v8 < 7 );
  v10 = 6;
  if ( a1 <= 8 )
  {
    for ( i = (__int64 *)*a5; i != a5; i = (__int64 *)*i )
      *((_DWORD *)i + 5) |= 4u;
    goto LABEL_50;
  }
  v48 = &v50;
  TableContext = a5;
  *(_DWORD *)NewElement = SiIncludeDrivesForMetadata(a1, a2, a3);
  if ( !*(_DWORD *)NewElement || (__int64 *)v50 == &v50 )
    goto LABEL_50;
  v12 = LocalAlloc(0x40u, 0xD8u);
  if ( !v12 )
  {
    SetLastError(0x5AAu);
    *(_DWORD *)NewElement = 0;
    goto LABEL_50;
  }
  *v12 = 6;
  v14 = v57[0];
  if ( *(_QWORD **)(v57[0] + 8LL) != v57 )
    goto LABEL_66;
  v15 = v12 + 50;
  v16 = 6;
  *v15 = v57[0];
  v15[1] = v57;
  *(_QWORD *)(v14 + 8) = v15;
  v57[0] = v15;
  if ( !a3 || (v17 = *a3, v17 <= 1) )
    v17 = 5;
  while ( v17 > 0 )
  {
    v18 = (_QWORD **)&v56[2 * v17 - 1];
    *(_DWORD *)NewElement = SiGetFaultDomains(&v50, (unsigned int)v17, v13, v18);
    if ( !*(_DWORD *)NewElement )
      goto LABEL_50;
    if ( v17 == 1 )
      break;
    v19 = *v18;
    v20 = 0;
    while ( v19 != v18 )
    {
      v21 = *(_QWORD *)((char *)v19 - 196) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v21 )
        v21 = *(_QWORD *)((char *)v19 - 188) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v21 )
        goto LABEL_27;
      v19 = (_QWORD *)*v19;
      ++v20;
    }
    if ( v20 >= 5 )
      break;
    v16 = v17;
LABEL_27:
    --v17;
  }
  v22 = 0;
  v23 = (struct _RTL_AVL_TABLE *)&v56[2 * v16 - 1];
  Parent = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent;
LABEL_29:
  if ( Parent != v23 )
  {
    RtlInitializeGenericTableAvl(
      Parent - 1,
      (PRTL_AVL_COMPARE_ROUTINE)SiFdTableCompareRoutine,
      SiTableAllocateRoutine,
      SiTableFreeRoutine,
      0);
    v25 = &v56[2 * v17 - 1];
    v52 = v25;
    v26 = (_QWORD *)*v25;
    while ( 1 )
    {
      if ( v26 == v25 )
      {
        Parent = (struct _RTL_AVL_TABLE *)Parent->BalancedRoot.Parent;
        ++v22;
        goto LABEL_29;
      }
      v27 = v26 - 25;
      Buffer = v26 - 25;
      LeftChild = (int)Parent[-2].BalancedRoot.LeftChild;
      if ( LeftChild == 6 )
        goto LABEL_69;
      v29 = 2LL * (unsigned int)(LeftChild - 2);
      v30 = *(_QWORD *)((char *)&v27[2 * (unsigned int)(LeftChild - 2) + 2] + 4)
          - *(unsigned __int64 *)((char *)&Parent[-2].BalancedRoot.LeftChild + 4);
      if ( !v30 )
        v30 = *(_QWORD *)((char *)&v27[v29 + 3] + 4)
            - *(unsigned __int64 *)((char *)&Parent[-2].BalancedRoot.RightChild + 4);
      if ( !v30 )
      {
LABEL_69:
        BCryptGenRandom(0, (PUCHAR)(v27[11] + 16LL), 4u, 2u);
        RtlInsertElementGenericTableAvl(Parent - 1, &Buffer, 8u, NewElement);
        if ( !*(_DWORD *)NewElement )
          break;
      }
      v26 = (_QWORD *)*v26;
      v25 = v52;
    }
    v31 = 5010;
LABEL_49:
    SetLastError(v31);
    goto LABEL_50;
  }
  v32 = 0;
LABEL_41:
  if ( v32 < (int)((v22 + 4 - (v22 + 4) % v22) / v22) )
  {
    for ( j = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent; ; j = (struct _RTL_AVL_TABLE *)j->BalancedRoot.Parent )
    {
      if ( j == v23 )
      {
        ++v32;
        goto LABEL_41;
      }
      RestartKey = 0;
      v34 = RtlEnumerateGenericTableWithoutSplayingAvl(j - 1, &RestartKey);
      if ( v34 )
      {
        Buffer = (_QWORD *)*v34;
        *(_DWORD *)(Buffer[11] + 20LL) |= 4u;
        v35 = RtlDeleteElementGenericTableAvl(j - 1, v34);
        *(_DWORD *)NewElement = v35;
        if ( !v35 )
          break;
      }
    }
    v31 = 1168;
    goto LABEL_49;
  }
  do
  {
LABEL_50:
    v36 = (_QWORD **)&v56[2 * v10 - 1];
    while ( 1 )
    {
      v37 = *v36;
      if ( *v36 == v36 )
        break;
      v38 = *v37;
      if ( *(_QWORD **)(*v37 + 8LL) != v37 )
        goto LABEL_66;
      v39 = (_QWORD *)v37[1];
      if ( (_QWORD *)*v39 != v37 )
        goto LABEL_66;
      v40 = v37 - 25;
      *v39 = v38;
      v41 = (struct _RTL_AVL_TABLE *)(v37 - 13);
      *(_QWORD *)(v38 + 8) = v39;
      while ( 1 )
      {
        v52 = 0;
        v42 = RtlEnumerateGenericTableWithoutSplayingAvl(v41, &v52);
        if ( !v42 )
          break;
        RtlDeleteElementGenericTableAvl(v41, v42);
      }
      LocalFree(v40);
    }
    --v10;
  }
  while ( v10 >= 0 );
  if ( *(__int64 **)(*a5 + 8) != a5
    || (v43 = (__int64 *)a5[1], (__int64 *)*v43 != a5)
    || *(__int64 **)(v50 + 8) != &v50
    || (__int64 *)*v51 != &v50
    || (*v43 = (__int64)&v50,
        v44 = v51,
        a5[1] = (__int64)v51,
        *v44 = (__int64)a5,
        v45 = v50,
        v51 = v43,
        *(__int64 **)(v50 + 8) != &v50)
    || (__int64 *)*v43 != &v50 )
  {
LABEL_66:
    __fastfail(3u);
  }
  *v43 = v50;
  *(_QWORD *)(v45 + 8) = v43;
  return *(unsigned int *)NewElement;
}

```

## disassembly

```asm
0x14000d29c  mov     [rsp-8+arg_18], rbx
0x14000d2a1  push    rbp
0x14000d2a2  push    rsi
0x14000d2a3  push    rdi
0x14000d2a4  push    r12
0x14000d2a6  push    r13
0x14000d2a8  push    r14
0x14000d2aa  push    r15
0x14000d2ac  lea     rbp, [rsp-1Fh]
0x14000d2b1  sub     rsp, 0E0h
0x14000d2b8  mov     rax, cs:__security_cookie
0x14000d2bf  xor     rax, rsp
0x14000d2c2  mov     [rbp+4Fh+var_40], rax
0x14000d2c6  mov     rdi, [rbp+4Fh+arg_20]
0x14000d2ca  mov     r14, rdx
0x14000d2cd  xor     edx, edx; Val
0x14000d2cf  mov     [rbp+4Fh+var_B0], 0
0x14000d2d7  mov     rbx, r8
0x14000d2da  mov     esi, ecx
0x14000d2dc  lea     rcx, [rbp+4Fh+var_A8]; void *
0x14000d2e0  lea     r8d, [rdx+68h]; Size
0x14000d2e4  call    memset_0
0x14000d2e9  lea     rax, [rsp+110h+var_D8]
0x14000d2ee  mov     [rbp+4Fh+Buffer], 0
0x14000d2f6  mov     [rsp+110h+var_D0], rax
0x14000d2fb  xor     edx, edx
0x14000d2fd  lea     rax, [rsp+110h+var_D8]
0x14000d302  mov     [rbp+4Fh+RestartKey], 0
0x14000d30a  mov     [rsp+110h+var_D8], rax
0x14000d30f  mov     dword ptr [rsp+110h+NewElement], 1
0x14000d317  movsxd  rcx, edx
0x14000d31a  lea     rax, [rbp+4Fh+var_B0]
0x14000d31e  shl     rcx, 4
0x14000d322  inc     edx
0x14000d324  add     rax, rcx
0x14000d327  mov     [rbp+rcx+4Fh+var_A8], rax
0x14000d32c  mov     [rax], rax
0x14000d32f  cmp     edx, 7
0x14000d332  jb      short loc_14000D317
0x14000d334  mov     r13d, 6
0x14000d33a  cmp     esi, 8
0x14000d33d  ja      short loc_14000D355
0x14000d33f  mov     rax, [rdi]
0x14000d342  jmp     short loc_14000D34B
0x14000d344  or      dword ptr [rax+14h], 4
0x14000d348  mov     rax, [rax]
0x14000d34b  cmp     rax, rdi
0x14000d34e  jnz     short loc_14000D344
0x14000d350  jmp     loc_14000D5E3
0x14000d355  lea     rax, [rsp+110h+var_D8]
0x14000d35a  mov     r8, rbx
0x14000d35d  mov     [rsp+110h+var_E8], rax
0x14000d362  mov     rdx, r14
0x14000d365  mov     ecx, esi
0x14000d367  mov     [rsp+110h+TableContext], rdi
0x14000d36c  call    ?SiIncludeDrivesForMetadata@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@3@Z; SiIncludeDrivesForMetadata(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *,_LIST_ENTRY *)
0x14000d371  mov     dword ptr [rsp+110h+NewElement], eax
0x14000d375  test    eax, eax
0x14000d377  jz      loc_14000D5E3
0x14000d37d  lea     rax, [rsp+110h+var_D8]
0x14000d382  cmp     [rsp+110h+var_D8], rax
0x14000d387  jz      loc_14000D5E3
0x14000d38d  mov     edx, 0D8h; uBytes
0x14000d392  mov     ecx, 40h ; '@'; uFlags
0x14000d397  call    cs:__imp_LocalAlloc
0x14000d39d  test    rax, rax
0x14000d3a0  jnz     short loc_14000D3BA
0x14000d3a2  mov     ecx, 5AAh; dwErrCode
0x14000d3a7  call    cs:__imp_SetLastError
0x14000d3ad  mov     dword ptr [rsp+110h+NewElement], 0
0x14000d3b5  jmp     loc_14000D5E3
0x14000d3ba  mov     [rax], r13d
0x14000d3bd  lea     rdx, [rbp+4Fh+var_50]
0x14000d3c1  mov     rcx, [rbp+4Fh+var_50]
0x14000d3c5  cmp     [rcx+8], rdx
0x14000d3c9  jnz     loc_14000D6FC
0x14000d3cf  add     rax, 0C8h
0x14000d3d5  lea     rdx, [rbp+4Fh+var_50]
0x14000d3d9  mov     r15d, r13d
0x14000d3dc  mov     [rax], rcx
0x14000d3df  mov     [rax+8], rdx
0x14000d3e3  mov     [rcx+8], rax
0x14000d3e7  mov     [rbp+4Fh+var_50], rax
0x14000d3eb  test    rbx, rbx
0x14000d3ee  jz      short loc_14000D3F7
0x14000d3f0  mov     ebx, [rbx]
0x14000d3f2  cmp     ebx, 1
0x14000d3f5  jg      short loc_14000D3FC
0x14000d3f7  mov     ebx, 5
0x14000d3fc  test    ebx, ebx
0x14000d3fe  jle     short loc_14000D46E
0x14000d400  movsxd  rax, ebx
0x14000d403  lea     rsi, [rbp+4Fh+var_B0]
0x14000d407  shl     rax, 4
0x14000d40b  lea     rcx, [rsp+110h+var_D8]
0x14000d410  add     rsi, rax
0x14000d413  mov     edx, ebx
0x14000d415  mov     r9, rsi
0x14000d418  call    ?SiGetFaultDomains@@YAHPEAU_LIST_ENTRY@@W4_SC_FD_TYPE@@H0@Z; SiGetFaultDomains(_LIST_ENTRY *,_SC_FD_TYPE,int,_LIST_ENTRY *)
0x14000d41d  mov     dword ptr [rsp+110h+NewElement], eax
0x14000d421  test    eax, eax
0x14000d423  jz      loc_14000D5E3
0x14000d429  cmp     ebx, 1
0x14000d42c  jz      short loc_14000D46E
0x14000d42e  mov     rcx, [rsi]
0x14000d431  xor     edx, edx
0x14000d433  cmp     rcx, rsi
0x14000d436  jz      short loc_14000D462
0x14000d438  mov     rax, [rcx-0C4h]
0x14000d43f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14000d446  jnz     short loc_14000D456
0x14000d448  mov     rax, [rcx-0BCh]
0x14000d44f  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14000d456  test    rax, rax
0x14000d459  jz      short loc_14000D46A
0x14000d45b  mov     rcx, [rcx]
0x14000d45e  inc     edx
0x14000d460  jmp     short loc_14000D433
0x14000d462  cmp     edx, 5
0x14000d465  jnb     short loc_14000D46E
0x14000d467  mov     r15d, ebx
0x14000d46a  dec     ebx
0x14000d46c  jmp     short loc_14000D3FC
0x14000d46e  movsxd  rax, r15d
0x14000d471  lea     r12, [rbp+4Fh+var_B0]
0x14000d475  shl     rax, 4
0x14000d479  xor     r14d, r14d
0x14000d47c  add     r12, rax
0x14000d47f  mov     rsi, [r12]
0x14000d483  cmp     rsi, r12
0x14000d486  jz      loc_14000D565
0x14000d48c  lea     rcx, [rsi-68h]; Table
0x14000d490  mov     [rsp+110h+TableContext], 0; TableContext
0x14000d499  lea     r9, ?SiTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x14000d4a0  lea     r8, ?SiTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x14000d4a7  lea     rdx, ?SiFdTableCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x14000d4ae  call    cs:__imp_RtlInitializeGenericTableAvl
0x14000d4b4  lea     r15, [rbp+4Fh+var_B0]
0x14000d4b8  movsxd  rax, ebx
0x14000d4bb  shl     rax, 4
0x14000d4bf  add     rax, r15
0x14000d4c2  mov     [rbp+4Fh+var_C8], rax
0x14000d4c6  mov     r15, [rax]
0x14000d4c9  cmp     r15, rax
0x14000d4cc  jz      loc_14000D553
0x14000d4d2  lea     rdx, [r15-0C8h]
0x14000d4d9  mov     [rbp+4Fh+Buffer], rdx
0x14000d4dd  mov     eax, [rsi-0C8h]
0x14000d4e3  cmp     eax, r13d
0x14000d4e6  jz      short loc_14000D50F
0x14000d4e8  add     eax, 0FFFFFFFEh
0x14000d4eb  mov     ecx, eax
0x14000d4ed  add     rcx, rcx
0x14000d4f0  mov     rax, [rdx+rcx*8+14h]
0x14000d4f5  sub     rax, [rsi-0C4h]
0x14000d4fc  jnz     short loc_14000D50A
0x14000d4fe  mov     rax, [rdx+rcx*8+1Ch]
0x14000d503  sub     rax, [rsi-0BCh]
0x14000d50a  test    rax, rax
0x14000d50d  jnz     short loc_14000D547
0x14000d50f  mov     rdx, [rdx+58h]
0x14000d513  xor     ecx, ecx; hAlgorithm
0x14000d515  add     rdx, 10h; pbBuffer
0x14000d519  lea     r9d, [rcx+2]; dwFlags
0x14000d51d  lea     r8d, [rcx+4]; cbBuffer
0x14000d521  call    cs:__imp_BCryptGenRandom
0x14000d527  lea     r9, [rsp+110h+NewElement]; NewElement
0x14000d52c  mov     r8d, 8; BufferSize
0x14000d532  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x14000d536  lea     rcx, [rsi-68h]; Table
0x14000d53a  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14000d540  cmp     dword ptr [rsp+110h+NewElement], 0
0x14000d545  jz      short loc_14000D55E
0x14000d547  mov     r15, [r15]
0x14000d54a  mov     rax, [rbp+4Fh+var_C8]
0x14000d54e  jmp     loc_14000D4C9
0x14000d553  mov     rsi, [rsi]
0x14000d556  inc     r14d
0x14000d559  jmp     loc_14000D483
0x14000d55e  mov     ecx, 1392h
0x14000d563  jmp     short loc_14000D5DD
0x14000d565  xor     edx, edx
0x14000d567  lea     ecx, [r14+4]
0x14000d56b  mov     eax, ecx
0x14000d56d  div     r14d
0x14000d570  sub     ecx, edx
0x14000d572  xor     edx, edx
0x14000d574  mov     eax, ecx
0x14000d576  div     r14d
0x14000d579  xor     esi, esi
0x14000d57b  mov     r15d, eax
0x14000d57e  cmp     esi, r15d
0x14000d581  jge     short loc_14000D5E3
0x14000d583  mov     rbx, [r12]
0x14000d587  cmp     rbx, r12
0x14000d58a  jz      short loc_14000D5D4
0x14000d58c  lea     rdx, [rbp+4Fh+RestartKey]; RestartKey
0x14000d590  mov     [rbp+4Fh+RestartKey], 0
0x14000d598  lea     rcx, [rbx-68h]; Table
0x14000d59c  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14000d5a2  test    rax, rax
0x14000d5a5  jz      short loc_14000D5CF
0x14000d5a7  mov     rdx, [rax]
0x14000d5aa  lea     rcx, [rbx-68h]; Table
0x14000d5ae  mov     [rbp+4Fh+Buffer], rdx
0x14000d5b2  mov     r8, [rdx+58h]
0x14000d5b6  mov     rdx, rax; Buffer
0x14000d5b9  or      dword ptr [r8+14h], 4
0x14000d5be  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000d5c4  movzx   eax, al
0x14000d5c7  mov     dword ptr [rsp+110h+NewElement], eax
0x14000d5cb  test    eax, eax
0x14000d5cd  jz      short loc_14000D5D8
0x14000d5cf  mov     rbx, [rbx]
0x14000d5d2  jmp     short loc_14000D587
0x14000d5d4  inc     esi
0x14000d5d6  jmp     short loc_14000D57E
0x14000d5d8  mov     ecx, 490h; dwErrCode
0x14000d5dd  call    cs:__imp_SetLastError
0x14000d5e3  movsxd  rax, r13d
0x14000d5e6  lea     rbx, [rbp+4Fh+var_B0]
0x14000d5ea  shl     rax, 4
0x14000d5ee  add     rbx, rax
0x14000d5f1  mov     rax, [rbx]
0x14000d5f4  cmp     rax, rbx
0x14000d5f7  jz      short loc_14000D658
0x14000d5f9  mov     rcx, [rax]
0x14000d5fc  cmp     [rcx+8], rax
0x14000d600  jnz     loc_14000D6FC
0x14000d606  mov     rdx, [rax+8]
0x14000d60a  cmp     [rdx], rax
0x14000d60d  jnz     loc_14000D6FC
0x14000d613  lea     r14, [rax-0C8h]
0x14000d61a  mov     [rdx], rcx
0x14000d61d  lea     rsi, [r14+60h]
0x14000d621  mov     [rcx+8], rdx
0x14000d625  jmp     short loc_14000D633
0x14000d627  mov     rdx, rax; Buffer
0x14000d62a  mov     rcx, rsi; Table
0x14000d62d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000d633  lea     rdx, [rbp+4Fh+var_C8]; RestartKey
0x14000d637  mov     [rbp+4Fh+var_C8], 0
0x14000d63f  mov     rcx, rsi; Table
0x14000d642  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14000d648  test    rax, rax
0x14000d64b  jnz     short loc_14000D627
0x14000d64d  mov     rcx, r14; hMem
0x14000d650  call    cs:__imp_LocalFree
0x14000d656  jmp     short loc_14000D5F1
0x14000d658  sub     r13d, 1
0x14000d65c  jns     short loc_14000D5E3
0x14000d65e  mov     rax, [rdi]
0x14000d661  cmp     [rax+8], rdi
0x14000d665  jnz     loc_14000D6FC
0x14000d66b  mov     rcx, [rdi+8]
0x14000d66f  cmp     [rcx], rdi
0x14000d672  jnz     loc_14000D6FC
0x14000d678  mov     rax, [rsp+110h+var_D8]
0x14000d67d  lea     rdx, [rsp+110h+var_D8]
0x14000d682  cmp     [rax+8], rdx
0x14000d686  jnz     short loc_14000D6FC
0x14000d688  mov     rax, [rsp+110h+var_D0]
0x14000d68d  lea     rdx, [rsp+110h+var_D8]
0x14000d692  cmp     [rax], rdx
0x14000d695  jnz     short loc_14000D6FC
0x14000d697  lea     rax, [rsp+110h+var_D8]
0x14000d69c  mov     [rcx], rax
0x14000d69f  lea     rdx, [rsp+110h+var_D8]
0x14000d6a4  mov     rax, [rsp+110h+var_D0]
0x14000d6a9  mov     [rdi+8], rax
0x14000d6ad  mov     [rax], rdi
0x14000d6b0  mov     rax, [rsp+110h+var_D8]
0x14000d6b5  mov     [rsp+110h+var_D0], rcx
0x14000d6ba  cmp     [rax+8], rdx
0x14000d6be  jnz     short loc_14000D6FC
0x14000d6c0  lea     rdx, [rsp+110h+var_D8]
0x14000d6c5  cmp     [rcx], rdx
0x14000d6c8  jnz     short loc_14000D6FC
0x14000d6ca  mov     [rcx], rax
0x14000d6cd  mov     [rax+8], rcx
0x14000d6d1  mov     eax, dword ptr [rsp+110h+NewElement]
0x14000d6d5  mov     rcx, [rbp+4Fh+var_40]
0x14000d6d9  xor     rcx, rsp; StackCookie
0x14000d6dc  call    __security_check_cookie
0x14000d6e1  mov     rbx, [rsp+110h+arg_18]
0x14000d6e9  add     rsp, 0E0h
0x14000d6f0  pop     r15
0x14000d6f2  pop     r14
0x14000d6f4  pop     r13
0x14000d6f6  pop     r12
0x14000d6f8  pop     rdi
0x14000d6f9  pop     rsi
0x14000d6fa  pop     rbp
0x14000d6fb  retn
0x14000d6fc  mov     ecx, 3
0x14000d701  int     29h; Win8: RtlFailFast(ecx)
```
