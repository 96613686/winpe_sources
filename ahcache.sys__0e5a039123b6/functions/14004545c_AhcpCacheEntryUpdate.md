# AhcpCacheEntryUpdate

- ea: `0x14004545c`
- end: `0x1400459f8`
- name: `AhcpCacheEntryUpdate`
- size: `1436`
- prototype: `__int64 __fastcall(__int64, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140043fc4`

## callees

- `0x140001b78`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x14004545c`
- `0x140045c38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400455b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400458f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004594d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400459a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400458f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004594d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400459a4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004575c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400457d2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004584c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004575c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400457d2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004584c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045783`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400457f9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045875`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400458b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004590b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045964`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045783`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400457f9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045875`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400458b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004590b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045964`

## string_xrefs

- `0x140045496`: `AhcpCacheEntryUpdate`
- `0x14004571c`: `AhcpCacheEntryUpdate`
- `0x1400459d9`: `AhcpCacheEntryUpdate`
- `0x14004570b`: `WriteParam failed [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntryUpdate(__int64 a1, unsigned int a2, const void *a3, unsigned int a4)
{
  __int64 v7; // r15
  void *v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  char *v11; // rsi
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  int v20; // ebx
  unsigned __int64 v22; // r14
  SIZE_T v23; // rdi
  size_t v24; // rax
  char *v25; // r15
  unsigned __int64 v26; // rax
  size_t v27; // r13
  char *v28; // r15
  unsigned __int64 v29; // rax
  KIRQL CurrentIrql; // al
  POOL_TYPE v31; // ecx
  char *v32; // rax
  char *v33; // r15
  unsigned __int64 v34; // rax
  KIRQL v35; // al
  POOL_TYPE v36; // ecx
  char *v37; // rax
  char *v38; // r13
  unsigned __int64 v39; // rax
  SIZE_T v40; // rdi
  KIRQL v41; // al
  POOL_TYPE v42; // ecx
  PVOID v43; // rax
  char *PoolWithTag; // rax
  size_t v45; // r8
  char *v46; // rax
  size_t v47; // r8
  PVOID v48; // rax
  size_t v49; // r8
  const char *v50; // r9
  __int64 v51; // r8
  __int64 v52; // [rsp+20h] [rbp-50h]
  int v53; // [rsp+30h] [rbp-40h] BYREF
  void *v54; // [rsp+38h] [rbp-38h]
  __int64 v55; // [rsp+40h] [rbp-30h] BYREF
  __int128 v56; // [rsp+48h] [rbp-28h]
  __int64 v57; // [rsp+58h] [rbp-18h]
  PVOID P[2]; // [rsp+60h] [rbp-10h]

  v55 = 0;
  v7 = 4096;
  v57 = 4096;
  v56 = 0;
  *(_OWORD *)P = 0;
  AslLogCallPrintf(3, "AhcpCacheEntryUpdate", 702, "InfoClass: %d", a2);
  v8 = *(void **)(a1 + 24);
  if ( v8 )
  {
    v19 = RtlMemoryStream::InitializeFromBuffer((RtlMemoryStream *)&v55, v8, *(unsigned int *)(a1 + 16));
    v20 = v19;
    if ( v19 < 0 )
    {
      v50 = "InitializeFromBuffer failed [%x]";
      v51 = 711;
      goto LABEL_94;
    }
    v7 = v57;
  }
  v9 = v56;
  v10 = 0;
  v11 = (char *)P[1];
  while ( 1 )
  {
    P[0] = (PVOID)v10;
    if ( v10 > (unsigned __int64)v56 )
      break;
    v12 = v10 + 8;
    if ( v10 + 8 < v10 )
      break;
    if ( v12 > (unsigned __int64)v56 )
      break;
    v13 = *(_QWORD *)((char *)P[1] + v10);
    P[0] = (PVOID)(v10 + 8);
    v14 = v12 + HIDWORD(v13);
    if ( v14 < v12 )
      break;
    if ( v14 + 3 < v14 )
      break;
    v10 = (v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v10 > (unsigned __int64)v56 )
      break;
    if ( (_DWORD)v13 == a2 )
    {
      if ( v12 >= 8 )
      {
        v15 = HIDWORD(v13);
        v16 = v12 + v15;
        if ( v12 + v15 >= v12 && v16 + 3 >= v16 )
        {
          v17 = (v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v17 <= (unsigned __int64)v56 )
          {
            v18 = v56 - v17;
            memmove((char *)P[1] + v12 - 8, (char *)P[1] + v17, v56 - v17);
            P[0] = 0;
            v9 = v12 + v18 - 8;
            *(_QWORD *)&v56 = v9;
          }
        }
      }
      break;
    }
  }
  if ( !a3 )
  {
LABEL_16:
    v19 = AhcpCacheEntrySetDataFromStream(a1, &v55);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v20 = 0;
LABEL_18:
      v11 = (char *)P[1];
      goto LABEL_19;
    }
    v50 = "Failed to set data in entry [%x]";
    v51 = 732;
LABEL_94:
    LODWORD(v52) = v19;
    AslLogCallPrintf(1, "AhcpCacheEntryUpdate", v51, v50, v52);
    goto LABEL_18;
  }
  P[0] = (PVOID)v9;
  v54 = (void *)__PAIR64__(a4, a2);
  v53 = 0;
  if ( (v9 & 3) != 0 )
    goto LABEL_48;
  v22 = v9 + 8;
  if ( v9 + 8 < v9 )
  {
LABEL_26:
    v20 = -1073741811;
    goto LABEL_27;
  }
  v23 = *((_QWORD *)&v56 + 1);
  if ( v22 > *((_QWORD *)&v56 + 1) )
  {
    v29 = v7 - 1 + v22;
    if ( v29 < v22 )
      goto LABEL_52;
    v23 = v29 & ~(v7 - 1);
    CurrentIrql = KeGetCurrentIrql();
    v31 = 512;
    if ( v11 )
    {
      if ( CurrentIrql != 2 )
        v31 = PagedPool;
      PoolWithTag = (char *)ExAllocatePoolWithTag(v31, v23, 0x7274534Du);
      v33 = PoolWithTag;
      if ( !PoolWithTag )
        goto LABEL_95;
      memset(PoolWithTag, 0, v23);
      v45 = v9;
      if ( v9 >= v23 )
        v45 = v23;
      memmove(v33, v11, v45);
      ExFreePoolWithTag(v11, 0x7274534Du);
    }
    else
    {
      if ( CurrentIrql != 2 )
        v31 = PagedPool;
      v32 = (char *)ExAllocatePoolWithTag(v31, v23, 0x7274534Du);
      v33 = v32;
      if ( !v32 )
        goto LABEL_95;
      memset(v32, 0, v23);
    }
    v11 = v33;
    P[1] = v33;
    *((_QWORD *)&v56 + 1) = v23;
  }
  *(_QWORD *)&v11[v9] = v54;
  v24 = a4;
  if ( v9 <= v22 )
    v9 += 8LL;
  P[0] = (PVOID)v22;
  *(_QWORD *)&v56 = v9;
  if ( a4 )
  {
    v25 = (char *)(a4 + v22);
    v54 = (void *)a4;
    if ( (unsigned __int64)v25 >= v22 )
    {
      if ( (unsigned __int64)v25 > v23 )
      {
        v34 = (unsigned __int64)&v25[v57 - 1];
        if ( v34 < (unsigned __int64)v25 )
          goto LABEL_52;
        v23 = v34 & ~(v57 - 1);
        v35 = KeGetCurrentIrql();
        v36 = 512;
        if ( v11 )
        {
          if ( v35 != 2 )
            v36 = PagedPool;
          v46 = (char *)ExAllocatePoolWithTag(v36, v23, 0x7274534Du);
          v38 = v46;
          if ( !v46 )
            goto LABEL_95;
          memset(v46, 0, v23);
          v47 = v9;
          if ( v9 >= v23 )
            v47 = v23;
          memmove(v38, v11, v47);
          ExFreePoolWithTag(v11, 0x7274534Du);
        }
        else
        {
          if ( v35 != 2 )
            v36 = PagedPool;
          v37 = (char *)ExAllocatePoolWithTag(v36, v23, 0x7274534Du);
          v38 = v37;
          if ( !v37 )
            goto LABEL_95;
          memset(v37, 0, v23);
        }
        v24 = (size_t)v54;
        v11 = v38;
        P[1] = v38;
        *((_QWORD *)&v56 + 1) = v23;
      }
      memmove(&v11[v22], a3, v24);
      if ( (unsigned __int64)v25 < v22 )
      {
        v20 = -1073741675;
        goto LABEL_49;
      }
      P[0] = (PVOID)(a4 + v22);
      v22 = (unsigned __int64)P[0];
      if ( v9 <= (unsigned __int64)v25 )
        v9 = (unsigned __int64)v25;
      *(_QWORD *)&v56 = v9;
      goto LABEL_39;
    }
LABEL_48:
    v20 = -1073741811;
    goto LABEL_49;
  }
LABEL_39:
  v26 = v22 & 3;
  if ( (v22 & 3) == 0 )
    goto LABEL_16;
  v27 = 4 - v26;
  if ( v26 == 4 )
    goto LABEL_47;
  v28 = (char *)(v22 + v27);
  if ( v22 + v27 < v22 )
    goto LABEL_26;
  if ( (unsigned __int64)v28 <= v23 )
  {
LABEL_43:
    memmove(&v11[v22], &v53, v27);
    if ( (unsigned __int64)v28 >= v22 )
    {
      P[0] = (PVOID)(v22 + v27);
      if ( v9 <= (unsigned __int64)v28 )
        v9 = v22 + v27;
      *(_QWORD *)&v56 = v9;
LABEL_47:
      v20 = 0;
      goto LABEL_27;
    }
    P[0] = (PVOID)-1LL;
    goto LABEL_52;
  }
  v39 = (unsigned __int64)&v28[v57 - 1];
  if ( v39 < (unsigned __int64)v28 )
  {
LABEL_52:
    v20 = -1073741675;
    goto LABEL_27;
  }
  v40 = v39 & ~(v57 - 1);
  v41 = KeGetCurrentIrql();
  v42 = 512;
  if ( v11 )
  {
    if ( v41 != 2 )
      v42 = PagedPool;
    v48 = ExAllocatePoolWithTag(v42, v40, 0x7274534Du);
    v54 = v48;
    if ( v48 )
    {
      memset(v48, 0, v40);
      v49 = v9;
      if ( v9 >= v40 )
        v49 = v40;
      memmove(v54, v11, v49);
      ExFreePoolWithTag(v11, 0x7274534Du);
      goto LABEL_73;
    }
  }
  else
  {
    if ( v41 != 2 )
      v42 = PagedPool;
    v43 = ExAllocatePoolWithTag(v42, v40, 0x7274534Du);
    v54 = v43;
    if ( v43 )
    {
      memset(v43, 0, v40);
LABEL_73:
      v11 = (char *)v54;
      P[1] = v54;
      *((_QWORD *)&v56 + 1) = v40;
      goto LABEL_43;
    }
  }
LABEL_95:
  v20 = -1073741801;
LABEL_27:
  if ( v20 >= 0 )
    goto LABEL_16;
LABEL_49:
  AslLogCallPrintf(1, "AhcpCacheEntryUpdate", 721, "WriteParam failed [%x]", v20);
LABEL_19:
  if ( v11 )
    ExFreePoolWithTag(v11, 0x7274534Du);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14004545c  mov     rax, rsp
0x14004545f  mov     [rax+10h], rbx
0x140045463  mov     [rax+20h], r9d
0x140045467  mov     [rax+18h], r8
0x14004546b  mov     [rax+8], rcx
0x14004546f  push    rbp
0x140045470  push    rsi
0x140045471  push    rdi
0x140045472  push    r12
0x140045474  push    r13
0x140045476  push    r14
0x140045478  push    r15
0x14004547a  mov     rbp, rsp
0x14004547d  sub     rsp, 70h
0x140045481  mov     r13, r8
0x140045484  mov     [rsp+70h+var_50], edx
0x140045488  mov     r14d, edx
0x14004548b  mov     [rbp+var_30], 0
0x140045493  mov     rbx, rcx
0x140045496  lea     rdx, aAhcpcacheentry_4; "AhcpCacheEntryUpdate"
0x14004549d  xorps   xmm0, xmm0
0x1400454a0  lea     r9, aInfoclassD; "InfoClass: %d"
0x1400454a7  xorps   xmm1, xmm1
0x1400454aa  mov     r15d, 1000h
0x1400454b0  mov     r8d, 2BEh
0x1400454b6  mov     [rbp+var_18], r15
0x1400454ba  mov     ecx, 3
0x1400454bf  movdqu  [rbp+var_28], xmm0
0x1400454c4  movdqu  xmmword ptr [rbp+P], xmm1
0x1400454c9  call    AslLogCallPrintf
0x1400454ce  mov     rdx, [rbx+18h]; void *
0x1400454d2  test    rdx, rdx
0x1400454d5  jnz     loc_1400455DC
0x1400454db  mov     rbx, qword ptr [rbp+var_28]
0x1400454df  xor     ecx, ecx
0x1400454e1  mov     rsi, [rbp+P+8]
0x1400454e5  mov     [rbp+P], rcx
0x1400454e9  cmp     rcx, rbx
0x1400454ec  ja      loc_140045580
0x1400454f2  lea     rdi, [rcx+8]
0x1400454f6  cmp     rdi, rcx
0x1400454f9  jb      loc_140045580
0x1400454ff  cmp     rdi, rbx
0x140045502  ja      short loc_140045580
0x140045504  mov     rax, [rsi+rcx]
0x140045508  mov     [rbp+P], rdi
0x14004550c  mov     rdx, rax
0x14004550f  shr     rdx, 20h
0x140045513  add     rdx, rdi
0x140045516  cmp     rdx, rdi
0x140045519  jb      short loc_140045580
0x14004551b  lea     rcx, [rdx+3]
0x14004551f  cmp     rcx, rdx
0x140045522  jb      short loc_140045580
0x140045524  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140045528  cmp     rcx, rbx
0x14004552b  ja      short loc_140045580
0x14004552d  cmp     eax, r14d
0x140045530  jnz     short loc_1400454E5
0x140045532  cmp     rdi, 8
0x140045536  jb      short loc_140045580
0x140045538  shr     rax, 20h
0x14004553c  lea     rdx, [rdi+rax]
0x140045540  cmp     rdx, rdi
0x140045543  jb      short loc_140045580
0x140045545  lea     rax, [rdx+3]
0x140045549  cmp     rax, rdx
0x14004554c  jb      short loc_140045580
0x14004554e  and     rax, 0FFFFFFFFFFFFFFFCh
0x140045552  cmp     rax, rbx
0x140045555  ja      short loc_140045580
0x140045557  sub     rbx, rax
0x14004555a  lea     rcx, [rsi-8]
0x14004555e  add     rcx, rdi; void *
0x140045561  lea     rdx, [rsi+rax]; Src
0x140045565  mov     r8, rbx; Size
0x140045568  call    memmove
0x14004556d  add     rbx, 0FFFFFFFFFFFFFFF8h
0x140045571  mov     [rbp+P], 0
0x140045579  add     rbx, rdi
0x14004557c  mov     qword ptr [rbp+var_28], rbx
0x140045580  mov     r12d, 1
0x140045586  test    r13, r13
0x140045589  jnz     short loc_1400455FC
0x14004558b  mov     rcx, [rbp+arg_0]
0x14004558f  lea     rdx, [rbp+var_30]
0x140045593  call    AhcpCacheEntrySetDataFromStream
0x140045598  mov     ebx, eax
0x14004559a  test    eax, eax
0x14004559c  js      loc_1400459C9
0x1400455a2  xor     ebx, ebx
0x1400455a4  mov     rsi, [rbp+P+8]
0x1400455a8  test    rsi, rsi
0x1400455ab  jz      short loc_1400455C1
0x1400455ad  mov     edx, 7274534Dh; Tag
0x1400455b2  mov     rcx, rsi; P
0x1400455b5  call    cs:__imp_ExFreePoolWithTag
0x1400455bc  nop     dword ptr [rax+rax+00h]
0x1400455c1  mov     eax, ebx
0x1400455c3  mov     rbx, [rsp+70h+arg_8]
0x1400455cb  add     rsp, 70h
0x1400455cf  pop     r15
0x1400455d1  pop     r14
0x1400455d3  pop     r13
0x1400455d5  pop     r12
0x1400455d7  pop     rdi
0x1400455d8  pop     rsi
0x1400455d9  pop     rbp
0x1400455da  retn
0x1400455dc  mov     r8d, [rbx+10h]; unsigned __int64
0x1400455e0  lea     rcx, [rbp+var_30]; this
0x1400455e4  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x1400455e9  mov     ebx, eax
0x1400455eb  test    eax, eax
0x1400455ed  js      loc_1400459B5
0x1400455f3  mov     r15, [rbp+var_18]
0x1400455f7  jmp     loc_1400454DB
0x1400455fc  mov     eax, dword ptr [rbp+Size]
0x1400455ff  mov     dword ptr [rbp+var_38+4], eax
0x140045602  mov     [rbp+P], rbx
0x140045606  mov     dword ptr [rbp+var_38], r14d
0x14004560a  mov     [rbp+var_40], 0
0x140045611  test    bl, 3
0x140045614  jnz     loc_140045706
0x14004561a  lea     r14, [rbx+8]
0x14004561e  cmp     r14, rbx
0x140045621  jnb     short loc_140045635
0x140045623  mov     ebx, 0C000000Dh
0x140045628  test    ebx, ebx
0x14004562a  jns     loc_14004558B
0x140045630  jmp     loc_14004570B
0x140045635  mov     rdi, qword ptr [rbp+var_28+8]
0x140045639  mov     r13d, 200h
0x14004563f  cmp     r14, rdi
0x140045642  ja      loc_140045749
0x140045648  mov     rcx, rdi
0x14004564b  mov     rax, [rbp+var_38]
0x14004564f  cmp     rbx, r14
0x140045652  mov     [rbx+rsi], rax
0x140045656  mov     eax, dword ptr [rbp+Size]
0x140045659  cmovbe  rbx, r14
0x14004565d  mov     [rbp+P], r14
0x140045661  mov     qword ptr [rbp+var_28], rbx
0x140045665  test    eax, eax
0x140045667  jz      short loc_1400456AE
0x140045669  lea     r15, [rax+r14]
0x14004566d  mov     [rbp+var_38], rax
0x140045671  cmp     r15, r14
0x140045674  jb      loc_140045706
0x14004567a  cmp     r15, rcx
0x14004567d  ja      loc_1400457B8
0x140045683  mov     rdx, [rbp+Src]; Src
0x140045687  lea     rcx, [r14+rsi]; void *
0x14004568b  mov     r8, rax; Size
0x14004568e  call    memmove
0x140045693  cmp     r15, r14
0x140045696  jb      loc_140045730
0x14004569c  cmp     rbx, r15
0x14004569f  mov     [rbp+P], r15
0x1400456a3  mov     r14, r15
0x1400456a6  cmovbe  rbx, r15
0x1400456aa  mov     qword ptr [rbp+var_28], rbx
0x1400456ae  mov     rax, r14
0x1400456b1  and     eax, 3
0x1400456b4  jz      loc_14004558B
0x1400456ba  mov     r13d, 4
0x1400456c0  sub     r13, rax
0x1400456c3  jz      short loc_1400456FF
0x1400456c5  lea     r15, [r14+r13]
0x1400456c9  cmp     r15, r14
0x1400456cc  jb      loc_140045623
0x1400456d2  cmp     r15, rdi
0x1400456d5  ja      loc_140045832
0x1400456db  lea     rcx, [r14+rsi]; void *
0x1400456df  mov     r8, r13; Size
0x1400456e2  lea     rdx, [rbp+var_40]; Src
0x1400456e6  call    memmove
0x1400456eb  cmp     r15, r14
0x1400456ee  jb      short loc_140045737
0x1400456f0  cmp     rbx, r15
0x1400456f3  mov     [rbp+P], r15
0x1400456f7  cmovbe  rbx, r15
0x1400456fb  mov     qword ptr [rbp+var_28], rbx
0x1400456ff  xor     ebx, ebx
0x140045701  jmp     loc_140045628
0x140045706  mov     ebx, 0C000000Dh
0x14004570b  lea     r9, aWriteparamFail; "WriteParam failed [%x]"
0x140045712  mov     [rsp+70h+var_50], ebx
0x140045716  mov     r8d, 2D1h
0x14004571c  lea     rdx, aAhcpcacheentry_4; "AhcpCacheEntryUpdate"
0x140045723  mov     ecx, r12d
0x140045726  call    AslLogCallPrintf
0x14004572b  jmp     loc_1400455A8
0x140045730  mov     ebx, 0C0000095h
0x140045735  jmp     short loc_14004570B
0x140045737  mov     [rbp+P], 0FFFFFFFFFFFFFFFFh
0x14004573f  mov     ebx, 0C0000095h
0x140045744  jmp     loc_140045628
0x140045749  lea     rdi, [r15-1]
0x14004574d  lea     rax, [rdi+r14]
0x140045751  cmp     rax, r14
0x140045754  jb      short loc_14004573F
0x140045756  not     rdi
0x140045759  and     rdi, rax
0x14004575c  call    cs:__imp_KeGetCurrentIrql
0x140045763  nop     dword ptr [rax+rax+00h]
0x140045768  mov     ecx, r13d
0x14004576b  mov     r8d, 7274534Dh; Tag
0x140045771  mov     rdx, rdi; NumberOfBytes
0x140045774  test    rsi, rsi
0x140045777  jnz     loc_1400458AC
0x14004577d  cmp     al, 2
0x14004577f  cmovnz  ecx, r12d; PoolType
0x140045783  call    cs:__imp_ExAllocatePoolWithTag
0x14004578a  nop     dword ptr [rax+rax+00h]
0x14004578f  mov     r15, rax
0x140045792  test    rax, rax
0x140045795  jz      loc_1400459EE
0x14004579b  mov     r8, rdi; Size
0x14004579e  xor     edx, edx; Val
0x1400457a0  mov     rcx, rax; void *
0x1400457a3  call    memset
0x1400457a8  mov     rsi, r15
0x1400457ab  mov     [rbp+P+8], r15
0x1400457af  mov     qword ptr [rbp+var_28+8], rdi
0x1400457b3  jmp     loc_140045648
0x1400457b8  mov     rdi, [rbp+var_18]
0x1400457bc  dec     rdi
0x1400457bf  lea     rax, [r15+rdi]
0x1400457c3  cmp     rax, r15
0x1400457c6  jb      loc_14004573F
0x1400457cc  not     rdi
0x1400457cf  and     rdi, rax
0x1400457d2  call    cs:__imp_KeGetCurrentIrql
0x1400457d9  nop     dword ptr [rax+rax+00h]
0x1400457de  mov     ecx, r13d
0x1400457e1  mov     r8d, 7274534Dh; Tag
0x1400457e7  mov     rdx, rdi; NumberOfBytes
0x1400457ea  test    rsi, rsi
0x1400457ed  jnz     loc_140045905
0x1400457f3  cmp     al, 2
0x1400457f5  cmovnz  ecx, r12d; PoolType
0x1400457f9  call    cs:__imp_ExAllocatePoolWithTag
0x140045800  nop     dword ptr [rax+rax+00h]
0x140045805  mov     r13, rax
0x140045808  test    rax, rax
0x14004580b  jz      loc_1400459EE
0x140045811  mov     r8, rdi; Size
0x140045814  xor     edx, edx; Val
0x140045816  mov     rcx, rax; void *
0x140045819  call    memset
0x14004581e  mov     rax, [rbp+var_38]
0x140045822  mov     rsi, r13
0x140045825  mov     [rbp+P+8], r13
0x140045829  mov     qword ptr [rbp+var_28+8], rdi
0x14004582d  jmp     loc_140045683
0x140045832  mov     rdi, [rbp+var_18]
0x140045836  dec     rdi
0x140045839  lea     rax, [r15+rdi]
0x14004583d  cmp     rax, r15
0x140045840  jb      loc_14004573F
0x140045846  not     rdi
0x140045849  and     rdi, rax
0x14004584c  call    cs:__imp_KeGetCurrentIrql
0x140045853  nop     dword ptr [rax+rax+00h]
0x140045858  mov     ecx, 200h
0x14004585d  mov     r8d, 7274534Dh; Tag
0x140045863  mov     rdx, rdi; NumberOfBytes
0x140045866  test    rsi, rsi
0x140045869  jnz     loc_14004595E
0x14004586f  cmp     al, 2
0x140045871  cmovnz  ecx, r12d; PoolType
0x140045875  call    cs:__imp_ExAllocatePoolWithTag
0x14004587c  nop     dword ptr [rax+rax+00h]
0x140045881  mov     [rbp+var_38], rax
0x140045885  test    rax, rax
0x140045888  jz      loc_1400459EE
0x14004588e  mov     r8, rdi; Size
0x140045891  xor     edx, edx; Val
0x140045893  mov     rcx, rax; void *
0x140045896  call    memset
0x14004589b  mov     rsi, [rbp+var_38]
0x14004589f  mov     [rbp+P+8], rsi
0x1400458a3  mov     qword ptr [rbp+var_28+8], rdi
0x1400458a7  jmp     loc_1400456DB
0x1400458ac  cmp     al, 2
0x1400458ae  cmovnz  ecx, r12d; PoolType
0x1400458b2  call    cs:__imp_ExAllocatePoolWithTag
0x1400458b9  nop     dword ptr [rax+rax+00h]
0x1400458be  mov     r15, rax
0x1400458c1  test    rax, rax
0x1400458c4  jz      loc_1400459EE
0x1400458ca  mov     r8, rdi; Size
0x1400458cd  xor     edx, edx; Val
0x1400458cf  mov     rcx, rax; void *
0x1400458d2  call    memset
0x1400458d7  cmp     rbx, rdi
0x1400458da  mov     r8, rbx
0x1400458dd  mov     rdx, rsi; Src
0x1400458e0  mov     rcx, r15; void *
  ... truncated ...
```
