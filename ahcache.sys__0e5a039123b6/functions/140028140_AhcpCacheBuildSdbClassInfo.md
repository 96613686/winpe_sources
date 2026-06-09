# AhcpCacheBuildSdbClassInfo

- ea: `0x140028140`
- end: `0x140028848`
- name: `AhcpCacheBuildSdbClassInfo`
- size: `1800`
- prototype: `__int64 __fastcall(int *, _DWORD *, int, _QWORD *, wchar_t *Str1, __int64, int, unsigned __int16 *, __int64, __int16, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14004c3a0`

## callees

- `0x1400079c8`
- `0x140007b40`
- `0x140007e40`
- `0x140028140`
- `0x14002ae24`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`
- `0x140054b90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028473`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002859d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002877e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028473`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002859d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002877e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400283e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028503`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400286cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028718`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400283e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028503`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400286cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028718`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028404`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028431`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002852a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002855b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400286ed`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002873e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028404`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028431`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002852a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002855b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400286ed`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002873e`
- `ntoskrnl!_wcsnicmp` at `0x14002832b`
- `ntoskrnl!_wcsnicmp` at `0x14002832b`

## string_xrefs

- `0x140028201`: `AhcpCacheBuildSdbClassInfo`
- `0x1400282af`: `AhcpCacheBuildSdbClassInfo`
- `0x1400287e8`: `Failed to write query result to stream [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheBuildSdbClassInfo(
        int *a1,
        _DWORD *a2,
        int a3,
        _QWORD *a4,
        wchar_t *Str1,
        __int64 a6,
        int a7,
        unsigned __int16 *a8,
        __int64 a9,
        __int16 a10,
        int a11,
        int a12)
{
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // r10
  int v19; // ebx
  __int64 v20; // r15
  int v21; // r14d
  const wchar_t **v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // rcx
  wchar_t *v25; // rbp
  int LookupClass; // eax
  __int64 v27; // rdx
  _DWORD *v28; // rcx
  size_t v29; // r8
  __int64 v30; // rcx
  int HasData; // eax
  unsigned __int64 v32; // rbp
  _OWORD *v33; // rsi
  int v34; // r12d
  unsigned __int64 v35; // rcx
  POOL_TYPE v36; // r15d
  __int64 v37; // rbx
  void *v38; // r13
  SIZE_T v39; // rbx
  KIRQL CurrentIrql; // al
  POOL_TYPE v41; // ecx
  PVOID v42; // rax
  void *v43; // r14
  PVOID PoolWithTag; // rax
  size_t v45; // r8
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // rcx
  SIZE_T v48; // r14
  unsigned __int64 v49; // rdx
  __int64 v50; // rbx
  void *v51; // r12
  SIZE_T v52; // rbx
  KIRQL v53; // al
  POOL_TYPE v54; // ecx
  PVOID v55; // rax
  void *v56; // rbp
  PVOID v57; // rax
  size_t v58; // r8
  __int64 v59; // rax
  _OWORD *v60; // rdx
  __int128 v61; // xmm1
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // rax
  size_t v65; // rax
  size_t v66; // rcx
  size_t v67; // r13
  unsigned __int64 v68; // rcx
  __int64 v69; // rbx
  void *v70; // rbp
  SIZE_T v71; // rbx
  PVOID v72; // rax
  void *v73; // rsi
  SIZE_T v74; // r14
  PVOID v75; // rax
  size_t v76; // r8
  size_t v77; // rax
  size_t v78; // rcx
  size_t v79; // rax
  __int64 v81; // [rsp+20h] [rbp-98h]
  int v82; // [rsp+60h] [rbp-58h] BYREF
  int Src; // [rsp+64h] [rbp-54h] BYREF
  __int64 v84; // [rsp+68h] [rbp-50h]
  __int64 v85; // [rsp+70h] [rbp-48h]
  int v88; // [rsp+D8h] [rbp+20h] BYREF

  a4[4] = 0;
  v14 = 0;
  v88 = 0;
  v82 = 0;
  while ( 1 )
  {
    v15 = a4[1];
    if ( v14 > v15 )
      break;
    v16 = v14 + 8;
    if ( v14 + 8 < v14 )
      break;
    if ( v16 > v15 )
      break;
    v17 = *(_QWORD *)(v14 + a4[5]);
    a4[4] = v16;
    v18 = v16 + HIDWORD(v17);
    if ( v18 < v16 )
      break;
    if ( v18 + 3 < v18 )
      break;
    v14 = (v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v14 > v15 )
      break;
    if ( (_DWORD)v17 == a12 )
      return 0;
    a4[4] = v14;
  }
  v85 = AslAlloc(a1, 456, 1);
  v20 = v85;
  if ( v85 )
  {
    v21 = a7;
    v22 = (const wchar_t **)a8;
    if ( a7 )
    {
      v23 = *((_QWORD *)a8 + 1);
      v24 = 0;
    }
    else
    {
      v24 = *((_QWORD *)a8 + 1);
      v23 = 0;
    }
    v25 = Str1;
    LookupClass = AhcSdbQueryLookupClass(
                    a3,
                    v85,
                    (unsigned int)&v88,
                    (unsigned int)&v82,
                    (__int64)Str1,
                    a6,
                    v24,
                    v23,
                    a9,
                    a10);
    v19 = LookupClass;
    if ( LookupClass < 0 )
    {
      LODWORD(v81) = LookupClass;
      AslLogCallPrintf(1, "AhcpCacheBuildSdbClassInfo", 2429, "Failed to lookup SDB [%x]", v81);
LABEL_100:
      AslFree(v28, v85);
      return (unsigned int)v19;
    }
    if ( !v88 && !v21 && !a11 )
    {
      if ( wcsncmp_0(v25, L"\\??\\", 4u) )
        goto LABEL_29;
      v29 = (unsigned __int64)*(unsigned __int16 *)v22 >> 1;
      v30 = -1;
      do
        ++v30;
      while ( v25[v30] );
      if ( v30 == v29 + 4 && !_wcsnicmp(v25 + 4, v22[1], v29) )
        v88 = 0;
      else
LABEL_29:
        v88 = 1;
    }
    HasData = AhcSdbQueryHasData(v20, v27);
    v32 = a4[1];
    a4[4] = v32;
    LODWORD(v84) = 4096;
    Src = 0;
    v33 = (_OWORD *)(v20 & -(__int64)(HasData != 0));
    v34 = HasData;
    HIDWORD(v84) = HasData != 0 ? 0x1C8 : 0;
    if ( (v32 & 3) != 0 )
      goto LABEL_28;
    v35 = v32 + 8;
    if ( v32 + 8 >= v32 )
    {
      v36 = 512;
      if ( v35 > a4[2] )
      {
        v37 = a4[3] - 1LL;
        if ( v35 + v37 < v35 )
          goto LABEL_74;
        v38 = (void *)a4[5];
        v39 = (v35 + v37) & ~v37;
        CurrentIrql = KeGetCurrentIrql();
        v41 = 512;
        if ( v38 )
        {
          if ( CurrentIrql != 2 )
            v41 = PagedPool;
          PoolWithTag = ExAllocatePoolWithTag(v41, v39, 0x7274534Du);
          v43 = PoolWithTag;
          if ( !PoolWithTag )
            goto LABEL_73;
          memset(PoolWithTag, 0, v39);
          v45 = v39;
          if ( v32 < v39 )
            v45 = v32;
          memmove(v43, v38, v45);
          ExFreePoolWithTag(v38, 0x7274534Du);
        }
        else
        {
          if ( CurrentIrql != 2 )
            v41 = PagedPool;
          v42 = ExAllocatePoolWithTag(v41, v39, 0x7274534Du);
          v43 = v42;
          if ( !v42 )
            goto LABEL_73;
          memset(v42, 0, v39);
        }
        a4[5] = v43;
        a4[2] = v39;
      }
      *(_QWORD *)(a4[4] + a4[5]) = v84;
      v46 = a4[4];
      v47 = v46 + 8;
      if ( v46 + 8 < v46 )
      {
LABEL_95:
        v19 = -1073741675;
        a4[4] = -1;
        goto LABEL_97;
      }
      a4[4] = v47;
      v48 = a4[1];
      if ( v48 <= v47 )
        v48 = v46 + 8;
      a4[1] = v48;
      if ( v34 )
      {
        v49 = v46 + 464;
        if ( v46 + 464 < v46 + 8 )
        {
LABEL_28:
          v19 = -1073741811;
LABEL_98:
          LODWORD(v81) = v19;
          AslLogCallPrintf(1, "AhcpCacheBuildSdbClassInfo", 2465, "Failed to write query result to stream [%x]", v81);
          goto LABEL_100;
        }
        if ( v49 > a4[2] )
        {
          v50 = a4[3] - 1LL;
          if ( v49 + v50 < v49 )
            goto LABEL_74;
          v51 = (void *)a4[5];
          v52 = (v49 + v50) & ~v50;
          v53 = KeGetCurrentIrql();
          v54 = 512;
          if ( v51 )
          {
            if ( v53 != 2 )
              v54 = PagedPool;
            v57 = ExAllocatePoolWithTag(v54, v52, 0x7274534Du);
            v56 = v57;
            if ( !v57 )
              goto LABEL_73;
            memset(v57, 0, v52);
            v58 = v52;
            if ( v48 < v52 )
              v58 = v48;
            memmove(v56, v51, v58);
            ExFreePoolWithTag(v51, 0x7274534Du);
          }
          else
          {
            if ( v53 != 2 )
              v54 = PagedPool;
            v55 = ExAllocatePoolWithTag(v54, v52, 0x7274534Du);
            v56 = v55;
            if ( !v55 )
              goto LABEL_73;
            memset(v55, 0, v52);
          }
          a4[5] = v56;
          a4[2] = v52;
        }
        v59 = 3;
        v60 = (_OWORD *)(a4[5] + a4[4]);
        do
        {
          *v60 = *v33;
          v60[1] = v33[1];
          v60[2] = v33[2];
          v60[3] = v33[3];
          v60[4] = v33[4];
          v60[5] = v33[5];
          v60[6] = v33[6];
          v61 = v33[7];
          v33 += 8;
          v60[7] = v61;
          v60 += 8;
          --v59;
        }
        while ( v59 );
        *v60 = *v33;
        v60[1] = v33[1];
        v60[2] = v33[2];
        v60[3] = v33[3];
        *((_QWORD *)v60 + 8) = *((_QWORD *)v33 + 8);
        v62 = a4[4];
        v63 = v62 + 456;
        if ( v62 + 456 < v62 )
        {
          a4[4] = -1;
          v19 = -1073741675;
          goto LABEL_98;
        }
        a4[4] = v63;
        v64 = a4[1];
        if ( v64 <= v63 )
          v64 = v63;
        a4[1] = v64;
      }
      v65 = a4[4];
      v66 = v65 & 3;
      if ( (v65 & 3) == 0 )
        goto LABEL_99;
      v67 = 4 - v66;
      if ( 4 == v66 )
        goto LABEL_72;
      v68 = v65 + v67;
      if ( v65 + v67 >= v65 )
      {
        if ( v68 <= a4[2] )
          goto LABEL_91;
        v69 = a4[3] - 1LL;
        if ( v69 + v68 >= v68 )
        {
          v70 = (void *)a4[5];
          v71 = (v69 + v68) & ~v69;
          if ( v70 )
          {
            v74 = a4[1];
            if ( KeGetCurrentIrql() != 2 )
              v36 = PagedPool;
            v75 = ExAllocatePoolWithTag(v36, v71, 0x7274534Du);
            v73 = v75;
            if ( v75 )
            {
              memset(v75, 0, v71);
              v76 = v71;
              if ( v74 < v71 )
                v76 = v74;
              memmove(v73, v70, v76);
              ExFreePoolWithTag(v70, 0x7274534Du);
              goto LABEL_90;
            }
          }
          else
          {
            if ( KeGetCurrentIrql() != 2 )
              v36 = PagedPool;
            v72 = ExAllocatePoolWithTag(v36, v71, 0x7274534Du);
            v73 = v72;
            if ( v72 )
            {
              memset(v72, 0, v71);
LABEL_90:
              a4[5] = v73;
              a4[2] = v71;
LABEL_91:
              memmove((void *)(a4[5] + a4[4]), &Src, v67);
              v77 = a4[4];
              v78 = v77 + v67;
              if ( v77 + v67 >= v77 )
              {
                a4[4] = v78;
                v79 = a4[1];
                if ( v79 <= v78 )
                  v79 = v78;
                a4[1] = v79;
LABEL_72:
                v19 = 0;
                goto LABEL_97;
              }
              goto LABEL_95;
            }
          }
LABEL_73:
          v19 = -1073741801;
          goto LABEL_97;
        }
LABEL_74:
        v19 = -1073741675;
        goto LABEL_97;
      }
    }
    v19 = -1073741811;
LABEL_97:
    if ( v19 < 0 )
      goto LABEL_98;
LABEL_99:
    v19 = 0;
    *a1 = v88;
    v28 = a2;
    *a2 = v82;
    goto LABEL_100;
  }
  v19 = -1073741801;
  AslLogCallPrintf(1, "AhcpCacheBuildSdbClassInfo", 2411, "Out of memory");
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140028140  mov     rax, rsp
0x140028143  mov     [rax+18h], rbx
0x140028147  mov     [rax+10h], rdx
0x14002814b  mov     [rax+8], rcx
0x14002814f  push    rbp
0x140028150  push    rsi
0x140028151  push    rdi
0x140028152  push    r12
0x140028154  push    r13
0x140028156  push    r14
0x140028158  push    r15
0x14002815a  sub     rsp, 80h
0x140028161  xor     r12d, r12d
0x140028164  mov     rdi, r9
0x140028167  mov     [r9+20h], r12
0x14002816b  mov     rbx, r8
0x14002816e  mov     r9d, r12d
0x140028171  mov     [rax+20h], r12d
0x140028175  mov     [rax-58h], r12d
0x140028179  mov     r8, [rdi+8]
0x14002817d  cmp     r9, r8
0x140028180  ja      short loc_1400281D4
0x140028182  lea     rdx, [r9+8]
0x140028186  cmp     rdx, r9
0x140028189  jb      short loc_1400281D4
0x14002818b  cmp     rdx, r8
0x14002818e  ja      short loc_1400281D4
0x140028190  mov     rax, [rdi+28h]
0x140028194  mov     rax, [r9+rax]
0x140028198  mov     [rdi+20h], rdx
0x14002819c  mov     r10, rax
0x14002819f  shr     r10, 20h
0x1400281a3  add     r10, rdx
0x1400281a6  cmp     r10, rdx
0x1400281a9  jb      short loc_1400281D4
0x1400281ab  lea     r9, [r10+3]
0x1400281af  cmp     r9, r10
0x1400281b2  jb      short loc_1400281D4
0x1400281b4  and     r9, 0FFFFFFFFFFFFFFFCh
0x1400281b8  cmp     r9, r8
0x1400281bb  ja      short loc_1400281D4
0x1400281bd  cmp     eax, [rsp+0B8h+arg_58]
0x1400281c4  jz      short loc_1400281CC
0x1400281c6  mov     [rdi+20h], r9
0x1400281ca  jmp     short loc_140028179
0x1400281cc  mov     ebx, r12d
0x1400281cf  jmp     loc_14002882A
0x1400281d4  mov     r13d, 1
0x1400281da  mov     edx, 1C8h
0x1400281df  mov     r8d, r13d
0x1400281e2  call    AslAlloc
0x1400281e7  mov     [rsp+0B8h+var_48], rax
0x1400281ec  mov     r15, rax
0x1400281ef  test    rax, rax
0x1400281f2  jnz     short loc_14002821A
0x1400281f4  lea     r9, aOutOfMemory; "Out of memory"
0x1400281fb  mov     r8d, 96Bh
0x140028201  lea     rdx, aAhcpcachebuild_1; "AhcpCacheBuildSdbClassInfo"
0x140028208  mov     ecx, r13d
0x14002820b  mov     ebx, 0C0000017h
0x140028210  call    AslLogCallPrintf
0x140028215  jmp     loc_14002882A
0x14002821a  mov     r14d, [rsp+0B8h+arg_30]
0x140028222  mov     rsi, [rsp+0B8h+arg_38]
0x14002822a  test    r14d, r14d
0x14002822d  jz      short loc_140028238
0x14002822f  mov     rdx, [rsi+8]
0x140028233  mov     rcx, r12
0x140028236  jmp     short loc_14002823F
0x140028238  mov     rcx, [rsi+8]
0x14002823c  mov     rdx, r12
0x14002823f  movzx   eax, [rsp+0B8h+arg_48]
0x140028247  lea     r9, [rsp+0B8h+var_58]
0x14002824c  mov     rbp, [rsp+0B8h+Str1]
0x140028254  lea     r8, [rsp+0B8h+arg_18]
0x14002825c  mov     [rsp+0B8h+var_70], ax
0x140028261  mov     rax, [rsp+0B8h+arg_40]
0x140028269  mov     [rsp+0B8h+var_78], rax
0x14002826e  mov     rax, [rsp+0B8h+arg_28]
0x140028276  mov     [rsp+0B8h+var_80], rdx
0x14002827b  mov     rdx, r15
0x14002827e  mov     [rsp+0B8h+var_88], rcx
0x140028283  mov     rcx, rbx
0x140028286  mov     [rsp+0B8h+var_90], rax
0x14002828b  mov     [rsp+0B8h+var_98], rbp
0x140028290  call    AhcSdbQueryLookupClass
0x140028295  mov     ebx, eax
0x140028297  test    eax, eax
0x140028299  jns     short loc_1400282C0
0x14002829b  mov     dword ptr [rsp+0B8h+var_98], eax
0x14002829f  lea     r9, aFailedToLookup; "Failed to lookup SDB [%x]"
0x1400282a6  mov     r8d, 97Dh
0x1400282ac  mov     ecx, r13d
0x1400282af  lea     rdx, aAhcpcachebuild_1; "AhcpCacheBuildSdbClassInfo"
0x1400282b6  call    AslLogCallPrintf
0x1400282bb  jmp     loc_140028820
0x1400282c0  mov     r8d, [rsp+0B8h+arg_18]
0x1400282c8  mov     r13d, 4
0x1400282ce  mov     [rsp+0B8h+arg_18], r8d
0x1400282d6  test    r8d, r8d
0x1400282d9  jnz     short loc_140028343
0x1400282db  test    r14d, r14d
0x1400282de  jnz     short loc_140028343
0x1400282e0  cmp     [rsp+0B8h+arg_50], r12d
0x1400282e8  jnz     short loc_140028343
0x1400282ea  mov     r8d, r13d; MaxCount
0x1400282ed  lea     rdx, asc_14000EAD8; "\\??\\"
0x1400282f4  mov     rcx, rbp; Str1
0x1400282f7  call    wcsncmp_0
0x1400282fc  test    eax, eax
0x1400282fe  jnz     loc_140028396
0x140028304  movzx   r8d, word ptr [rsi]
0x140028308  shr     r8, 1; MaxCount
0x14002830b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002830f  inc     rcx
0x140028312  cmp     [rbp+rcx*2+0], r12w
0x140028318  jnz     short loc_14002830F
0x14002831a  lea     rax, [r8+4]
0x14002831e  cmp     rcx, rax
0x140028321  jnz     short loc_140028396
0x140028323  mov     rdx, [rsi+8]; Str2
0x140028327  lea     rcx, [rbp+8]; Str1
0x14002832b  call    cs:__imp__wcsnicmp
0x140028332  nop     dword ptr [rax+rax+00h]
0x140028337  test    eax, eax
0x140028339  jnz     short loc_140028396
0x14002833b  mov     [rsp+0B8h+arg_18], r12d
0x140028343  mov     r14d, 1
0x140028349  mov     rcx, r15
0x14002834c  call    AhcSdbQueryHasData
0x140028351  mov     rbp, [rdi+8]
0x140028355  mov     ecx, eax
0x140028357  neg     ecx
0x140028359  mov     [rdi+20h], rbp
0x14002835d  mov     ecx, eax
0x14002835f  mov     dword ptr [rsp+0B8h+var_50], 1000h
0x140028367  sbb     rsi, rsi
0x14002836a  mov     [rsp+0B8h+Src], 0
0x140028372  and     rsi, r15
0x140028375  mov     r12d, eax
0x140028378  neg     ecx
0x14002837a  sbb     edx, edx
0x14002837c  and     edx, 1C8h
0x140028382  mov     dword ptr [rsp+0B8h+var_50+4], edx
0x140028386  test    bpl, 3
0x14002838a  jz      short loc_1400283A6
0x14002838c  mov     ebx, 0C000000Dh
0x140028391  jmp     loc_1400287E4
0x140028396  mov     r14d, 1
0x14002839c  mov     [rsp+0B8h+arg_18], r14d
0x1400283a4  jmp     short loc_140028349
0x1400283a6  lea     rcx, [rbp+8]
0x1400283aa  cmp     rcx, rbp
0x1400283ad  jb      loc_1400287DB
0x1400283b3  mov     r15d, 200h
0x1400283b9  cmp     rcx, [rdi+10h]
0x1400283bd  jbe     loc_14002848D
0x1400283c3  mov     rbx, [rdi+18h]
0x1400283c7  dec     rbx
0x1400283ca  lea     rax, [rcx+rbx]
0x1400283ce  cmp     rax, rcx
0x1400283d1  jb      loc_14002867A
0x1400283d7  mov     r13, [rdi+28h]
0x1400283db  not     rbx
0x1400283de  and     rbx, rax
0x1400283e1  call    cs:__imp_KeGetCurrentIrql
0x1400283e8  nop     dword ptr [rax+rax+00h]
0x1400283ed  mov     ecx, r15d
0x1400283f0  mov     r8d, 7274534Dh; Tag
0x1400283f6  mov     rdx, rbx; NumberOfBytes
0x1400283f9  test    r13, r13
0x1400283fc  jnz     short loc_14002842B
0x1400283fe  cmp     al, 2
0x140028400  cmovnz  ecx, r14d; PoolType
0x140028404  call    cs:__imp_ExAllocatePoolWithTag
0x14002840b  nop     dword ptr [rax+rax+00h]
0x140028410  mov     r14, rax
0x140028413  test    rax, rax
0x140028416  jz      loc_140028670
0x14002841c  mov     r8, rbx; Size
0x14002841f  xor     edx, edx; Val
0x140028421  mov     rcx, rax; void *
0x140028424  call    memset
0x140028429  jmp     short loc_14002847F
0x14002842b  cmp     al, 2
0x14002842d  cmovnz  ecx, r14d; PoolType
0x140028431  call    cs:__imp_ExAllocatePoolWithTag
0x140028438  nop     dword ptr [rax+rax+00h]
0x14002843d  mov     r14, rax
0x140028440  test    rax, rax
0x140028443  jz      loc_140028670
0x140028449  mov     r8, rbx; Size
0x14002844c  xor     edx, edx; Val
0x14002844e  mov     rcx, rax; void *
0x140028451  call    memset
0x140028456  cmp     rbp, rbx
0x140028459  mov     r8, rbx
0x14002845c  mov     rdx, r13; Src
0x14002845f  mov     rcx, r14; void *
0x140028462  cmovb   r8, rbp; Size
0x140028466  call    memmove
0x14002846b  mov     edx, 7274534Dh; Tag
0x140028470  mov     rcx, r13; P
0x140028473  call    cs:__imp_ExFreePoolWithTag
0x14002847a  nop     dword ptr [rax+rax+00h]
0x14002847f  mov     [rdi+28h], r14
0x140028483  mov     r13d, 4
0x140028489  mov     [rdi+10h], rbx
0x14002848d  mov     rcx, [rdi+28h]
0x140028491  mov     rax, [rsp+0B8h+var_50]
0x140028496  mov     rdx, [rdi+20h]
0x14002849a  mov     [rdx+rcx], rax
0x14002849e  mov     rax, [rdi+20h]
0x1400284a2  lea     rcx, [rax+8]
0x1400284a6  cmp     rcx, rax
0x1400284a9  jb      loc_1400287CC
0x1400284af  mov     [rdi+20h], rcx
0x1400284b3  mov     r14, [rdi+8]
0x1400284b7  cmp     r14, rcx
0x1400284ba  cmovbe  r14, rcx
0x1400284be  mov     [rdi+8], r14
0x1400284c2  test    r12d, r12d
0x1400284c5  jz      loc_140028654
0x1400284cb  lea     rdx, [rcx+1C8h]
0x1400284d2  cmp     rdx, rcx
0x1400284d5  jb      loc_14002838C
0x1400284db  cmp     rdx, [rdi+10h]
0x1400284df  jbe     loc_1400285B1
0x1400284e5  mov     rbx, [rdi+18h]
0x1400284e9  dec     rbx
0x1400284ec  lea     rax, [rdx+rbx]
0x1400284f0  cmp     rax, rdx
0x1400284f3  jb      loc_14002867A
0x1400284f9  mov     r12, [rdi+28h]
0x1400284fd  not     rbx
0x140028500  and     rbx, rax
0x140028503  call    cs:__imp_KeGetCurrentIrql
0x14002850a  nop     dword ptr [rax+rax+00h]
0x14002850f  mov     ecx, r15d
0x140028512  mov     r8d, 7274534Dh; Tag
0x140028518  mov     rdx, rbx; NumberOfBytes
0x14002851b  test    r12, r12
0x14002851e  jnz     short loc_140028551
0x140028520  cmp     al, 2
0x140028522  lea     eax, [r12+1]
0x140028527  cmovnz  ecx, eax; PoolType
0x14002852a  call    cs:__imp_ExAllocatePoolWithTag
0x140028531  nop     dword ptr [rax+rax+00h]
0x140028536  mov     rbp, rax
0x140028539  test    rax, rax
0x14002853c  jz      loc_140028670
0x140028542  mov     r8, rbx; Size
0x140028545  xor     edx, edx; Val
0x140028547  mov     rcx, rax; void *
0x14002854a  call    memset
0x14002854f  jmp     short loc_1400285A9
0x140028551  cmp     al, 2
0x140028553  mov     eax, 1
0x140028558  cmovnz  ecx, eax; PoolType
0x14002855b  call    cs:__imp_ExAllocatePoolWithTag
0x140028562  nop     dword ptr [rax+rax+00h]
0x140028567  mov     rbp, rax
0x14002856a  test    rax, rax
0x14002856d  jz      loc_140028670
0x140028573  mov     r8, rbx; Size
0x140028576  xor     edx, edx; Val
0x140028578  mov     rcx, rax; void *
0x14002857b  call    memset
0x140028580  cmp     r14, rbx
0x140028583  mov     r8, rbx
0x140028586  mov     rdx, r12; Src
0x140028589  mov     rcx, rbp; void *
0x14002858c  cmovb   r8, r14; Size
0x140028590  call    memmove
0x140028595  mov     edx, 7274534Dh; Tag
0x14002859a  mov     rcx, r12; P
0x14002859d  call    cs:__imp_ExFreePoolWithTag
0x1400285a4  nop     dword ptr [rax+rax+00h]
0x1400285a9  mov     [rdi+28h], rbp
0x1400285ad  mov     [rdi+10h], rbx
0x1400285b1  mov     rdx, [rdi+20h]
0x1400285b5  mov     eax, 3
0x1400285ba  add     rdx, [rdi+28h]
0x1400285be  lea     ecx, [rax+7Dh]
0x1400285c1  movups  xmm0, xmmword ptr [rsi]
0x1400285c4  movups  xmmword ptr [rdx], xmm0
0x1400285c7  movups  xmm1, xmmword ptr [rsi+10h]
0x1400285cb  movups  xmmword ptr [rdx+10h], xmm1
0x1400285cf  movups  xmm0, xmmword ptr [rsi+20h]
0x1400285d3  movups  xmmword ptr [rdx+20h], xmm0
0x1400285d7  movups  xmm1, xmmword ptr [rsi+30h]
0x1400285db  movups  xmmword ptr [rdx+30h], xmm1
0x1400285df  movups  xmm0, xmmword ptr [rsi+40h]
0x1400285e3  movups  xmmword ptr [rdx+40h], xmm0
0x1400285e7  movups  xmm1, xmmword ptr [rsi+50h]
0x1400285eb  movups  xmmword ptr [rdx+50h], xmm1
0x1400285ef  movups  xmm0, xmmword ptr [rsi+60h]
0x1400285f3  movups  xmmword ptr [rdx+60h], xmm0
0x1400285f7  movups  xmm1, xmmword ptr [rsi+70h]
0x1400285fb  add     rsi, rcx
  ... truncated ...
```
