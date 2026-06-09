# FsLibGroupSubExtentsByDanglingMdl

- ea: `0x140292d60`
- end: `0x140293490`
- name: `FsLibGroupSubExtentsByDanglingMdl`
- size: `1840`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140055094`
- `0x14020f3a0`

## callees

- `0x14011afe8`
- `0x140292d60`
- `0x14029aa00`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140292e01`
- `ntoskrnl!DbgPrintEx` at `0x140292eaa`
- `ntoskrnl!DbgPrintEx` at `0x140292f16`
- `ntoskrnl!DbgPrintEx` at `0x140292fa3`
- `ntoskrnl!DbgPrintEx` at `0x14029302d`
- `ntoskrnl!DbgPrintEx` at `0x140293081`
- `ntoskrnl!DbgPrintEx` at `0x1402930d9`
- `ntoskrnl!DbgPrintEx` at `0x140293103`
- `ntoskrnl!DbgPrintEx` at `0x140293141`
- `ntoskrnl!DbgPrintEx` at `0x1402931be`
- `ntoskrnl!DbgPrintEx` at `0x140293224`
- `ntoskrnl!DbgPrintEx` at `0x14029327e`
- `ntoskrnl!DbgPrintEx` at `0x1402932b8`
- `ntoskrnl!DbgPrintEx` at `0x140293324`
- `ntoskrnl!DbgPrintEx` at `0x140293419`
- `ntoskrnl!DbgPrintEx` at `0x140292e01`
- `ntoskrnl!DbgPrintEx` at `0x140292eaa`
- `ntoskrnl!DbgPrintEx` at `0x140292f16`
- `ntoskrnl!DbgPrintEx` at `0x140292fa3`
- `ntoskrnl!DbgPrintEx` at `0x14029302d`
- `ntoskrnl!DbgPrintEx` at `0x140293081`
- `ntoskrnl!DbgPrintEx` at `0x1402930d9`
- `ntoskrnl!DbgPrintEx` at `0x140293103`
- `ntoskrnl!DbgPrintEx` at `0x140293141`
- `ntoskrnl!DbgPrintEx` at `0x1402931be`
- `ntoskrnl!DbgPrintEx` at `0x140293224`
- `ntoskrnl!DbgPrintEx` at `0x14029327e`
- `ntoskrnl!DbgPrintEx` at `0x1402932b8`
- `ntoskrnl!DbgPrintEx` at `0x140293324`
- `ntoskrnl!DbgPrintEx` at `0x140293419`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140293454`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bda49`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140293454`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bda49`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140292dd7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140292dd7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140293439`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402bda2c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140293439`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402bda2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140292e22`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140292e22`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x14029300d`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x14029300d`

## string_xrefs

- `0x140292df0`: `FsLibGroupSubExtentsByDanglingMdl: Failed to allocate ExtentsDescriptor from the lookaside list.\n`
- `0x140292e3b`: `FsLibGroupSubExtentsByDanglingMdl: Failed to allocate DsmBuffer from the non-paged lookaside list.\n`
- `0x140293075`: `Case 1: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n`
- `0x140293135`: `Case 2: Update SubExtentClusterStart: %I64x\n`
- `0x1402932ac`: `Case 4: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n`
- `0x140293272`: `Case 3: Update SubExtentClusterStart: %I64x, SubExtentPageCount: %I64x, NextStartPage: %I64x\n`

## pseudocode

```c
__int64 __fastcall FsLibGroupSubExtentsByDanglingMdl(
        int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        char *a7)
{
  unsigned __int64 v7; // r14
  unsigned int v10; // ebx
  unsigned __int64 v11; // r12
  PVOID v12; // r15
  PVOID v13; // r13
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // rcx
  int AddressRangesForSingleVolumeExtent; // eax
  __int64 i; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rax
  __int64 v23; // r15
  __int64 v24; // r12
  int appended; // eax
  const CHAR *v26; // r8
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  int v34[2]; // [rsp+28h] [rbp-C0h]
  char v35; // [rsp+40h] [rbp-A8h]
  __int64 v36; // [rsp+48h] [rbp-A0h]
  PVOID v37; // [rsp+50h] [rbp-98h]
  unsigned __int64 v38; // [rsp+58h] [rbp-90h]
  int v39; // [rsp+60h] [rbp-88h]
  unsigned __int64 v40; // [rsp+68h] [rbp-80h]
  __int64 v41; // [rsp+70h] [rbp-78h]
  unsigned __int64 IsExtentDangling; // [rsp+70h] [rbp-78h]
  __int64 v43; // [rsp+78h] [rbp-70h]
  unsigned __int64 v44; // [rsp+80h] [rbp-68h]
  char v46; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v47; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v48; // [rsp+100h] [rbp+18h]

  v7 = a4;
  if ( a3 <= 0 )
    return 3221225485LL;
  v10 = -1073741823;
  v46 = 0;
  v11 = 0;
  v12 = 0;
  v48 = 0;
  v35 = 0;
  if ( !a5 && !a6 && !a7 )
    return 3221225485LL;
  v13 = ExAllocateFromPagedLookasideList(&FsLibExtentsDescriptorLookasideList);
  v36 = (__int64)v13;
  if ( v13 )
  {
    v12 = ExAllocateFromNPagedLookasideList(&FsLibDsmBufferLookasideList);
    v37 = v12;
    if ( !v12 )
    {
      DbgPrintEx(
        0x9Au,
        2u,
        "FsLibGroupSubExtentsByDanglingMdl: Failed to allocate DsmBuffer from the non-paged lookaside list.\n");
      goto LABEL_7;
    }
    v14 = v7 >> 12;
    v15 = a2 * (v7 >> 12);
    v44 = v15;
    v16 = a3 * (v7 >> 12);
    v43 = v16;
    v17 = (_QWORD *)v36;
    while ( v16 > 0 )
    {
      *v17 = 65532;
      DbgPrintEx(
        0x9Au,
        2u,
        "FsLibGroupSubExtentsByDanglingMdl: StartingPageToQuery: 0x%llx, RemainingPagesToQuery: 0x%llx\n",
        v15,
        v16);
      AddressRangesForSingleVolumeExtent = FsLibGetAddressRangesForSingleVolumeExtent(
                                             a1,
                                             (__int64)v12,
                                             0x100000,
                                             v36,
                                             1048528);
      v10 = AddressRangesForSingleVolumeExtent;
      if ( AddressRangesForSingleVolumeExtent < 0 )
      {
        DbgPrintEx(
          0x9Au,
          2u,
          "FsLibGroupSubExtentsByDanglingMdl: FsLibGetAddressRangesForSingleVolumeExtent failed with 0x%08x\n",
          AddressRangesForSingleVolumeExtent);
        goto LABEL_59;
      }
      for ( i = 0; ; i = (unsigned int)(v39 + 1) )
      {
        v39 = i;
        v17 = (_QWORD *)v36;
        if ( (unsigned int)i >= *(_DWORD *)(v36 + 4) )
          break;
        v20 = 2 * i;
        v41 = *(_QWORD *)(v36 + 8 * v20 + 8);
        v21 = *(_QWORD *)(v36 + 8 * v20 + 16);
        v43 -= v21;
        v44 += v21;
        DbgPrintEx(0x9Au, 2u, "StartPage: %I64x, PageCount: %I64x, PagesToSkip: %I64x\n", v41, v21, v48);
        if ( v21 > v48 )
        {
          v22 = v48 + v41;
          v38 = v48 + v41;
          v23 = v21 - v48;
          v48 = 0;
          while ( 1 )
          {
            if ( !v23 )
              goto LABEL_46;
            v40 = v22;
            IsExtentDangling = FsRtlIsExtentDangling(v22, v23, 0);
            DbgPrintEx(0x9Au, 2u, "DanglingPage: %I64x\n", IsExtentDangling);
            if ( !v46 )
              goto LABEL_30;
            if ( IsExtentDangling - v38 >= v14 )
            {
              v24 = v11 / v14;
              if ( a5 )
              {
                appended = FsLibAppendExtent(a5, a2, v24);
                v10 = appended;
                if ( appended < 0 )
                {
                  v26 = "Case 2: FAILED to add to ExtentsWithDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n";
LABEL_26:
                  v34[0] = appended;
                  DbgPrintEx(0x9Au, 0, v26, a2, v24, *(_QWORD *)v34);
                  goto LABEL_27;
                }
              }
              DbgPrintEx(0x9Au, 2u, "Case 2: Found dangling MDL. StartCluster: %I64x, ClusterCount: %I64x\n", a2, v24);
              a2 += v24;
              v46 = 0;
              v11 = 0;
              DbgPrintEx(0x9Au, 2u, "Case 2: Update SubExtentClusterStart: %I64x\n", a2);
            }
            else
            {
              v11 += v14;
              v40 = v14 + v38;
              DbgPrintEx(0x9Au, 2u, "Case 1: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n", v11, v14 + v38);
            }
            if ( !v46 )
            {
LABEL_30:
              if ( IsExtentDangling >= v23 + v38 )
              {
                v11 += v23;
                v40 += v23;
                DbgPrintEx(0x9Au, 2u, "Case 4: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n", v11, v40);
              }
              else
              {
                v27 = v11 + IsExtentDangling - v38;
                v24 = v27 / v14;
                if ( !v35 )
                {
                  v35 = 1;
                  if ( !a5 && !a6 )
                  {
                    DbgPrintEx(
                      0x9Au,
                      0,
                      "Case 3: Found first dangling MDL.  Caller is not interested in sub extents that dangle or not. Dan"
                      "gling cluster: %I64x, Status: %08x\n",
                      v27 / v14 + a2,
                      v10);
                    goto LABEL_27;
                  }
                }
                v28 = v14 - v27 % v14;
                v47 = v28;
                if ( v24 > 0 )
                {
                  if ( a6 )
                  {
                    appended = FsLibAppendExtent(a6, a2, v24);
                    v10 = appended;
                    if ( appended < 0 )
                    {
                      v26 = "Case 3: FAILED to add to ExtentsWithoutDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x"
                            ", Status: %08x\n";
                      goto LABEL_26;
                    }
                  }
                  DbgPrintEx(
                    0x9Au,
                    2u,
                    "Case 3: Non-dangling range: StartCluster: %I64x, ClusterCount: %I64x\n",
                    a2,
                    v24);
                  v28 = v47;
                }
                a2 += v24;
                v46 = 1;
                v11 = v7 >> 12;
                v40 = IsExtentDangling + v28;
                DbgPrintEx(
                  0x9Au,
                  2u,
                  "Case 3: Update SubExtentClusterStart: %I64x, SubExtentPageCount: %I64x, NextStartPage: %I64x\n",
                  a2,
                  v14,
                  IsExtentDangling + v28);
              }
            }
            v29 = v38;
            if ( v40 < v23 + v38 )
            {
              v23 += v38 - v40;
              v29 = v40;
              v38 = v40;
              v30 = v48;
            }
            else
            {
              v30 = v40 - v23 - v38;
              v48 = v30;
              v23 = 0;
            }
            DbgPrintEx(
              0x9Au,
              2u,
              "End of iteration. StartPage: %I64x, PageCount: %I64x, PagesToSkip: %I64x\n",
              v29,
              v23,
              v30);
            v22 = v38;
          }
        }
        v48 -= v21;
LABEL_46:
        ;
      }
      v12 = v37;
      v16 = v43;
      v15 = v44;
    }
    if ( v46 )
    {
      if ( a5 )
      {
        v31 = FsLibAppendExtent(a5, a2, v11 / v14);
        v10 = v31;
        if ( v31 < 0 )
        {
          v34[0] = v31;
          DbgPrintEx(
            0x9Au,
            0,
            "End: FAILED to add to ExtentsWithDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n",
            a2,
            v11 / v14,
            *(_QWORD *)v34);
LABEL_27:
          v12 = v37;
LABEL_59:
          v13 = (PVOID)v36;
          goto LABEL_60;
        }
        v12 = v37;
      }
      DbgPrintEx(0x9Au, 2u, "End: Dangling range: StartCluster: %I64x, ClusterCount: %I64x\n", a2, v11 / v14);
      goto LABEL_59;
    }
    if ( a6 )
    {
      v32 = FsLibAppendExtent(a6, a2, v11 / v14);
      v10 = v32;
      if ( v32 < 0 )
      {
        v34[0] = v32;
        DbgPrintEx(
          0x9Au,
          0,
          "End: FAILED to add to ExtentsWithoutDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n",
          a2,
          v11 / v14,
          *(_QWORD *)v34);
        goto LABEL_27;
      }
      v12 = v37;
    }
    DbgPrintEx(0x9Au, 2u, "End: Non-dangling range: StartCluster: %I64x, ClusterCount: %I64x\n", a2, v11 / v14);
    goto LABEL_59;
  }
  DbgPrintEx(
    0x9Au,
    2u,
    "FsLibGroupSubExtentsByDanglingMdl: Failed to allocate ExtentsDescriptor from the lookaside list.\n");
LABEL_7:
  v10 = -1073741670;
LABEL_60:
  if ( v13 )
    ExFreeToPagedLookasideList(&FsLibExtentsDescriptorLookasideList, v13);
  if ( v12 )
    ExFreeToNPagedLookasideList(&FsLibDsmBufferLookasideList, v12);
  if ( a7 )
    *a7 = v35;
  return v10;
}

```

## disassembly

```asm
0x140292d60  mov     r11, rsp
0x140292d63  mov     [r11+8], rcx
0x140292d67  push    rbx
0x140292d68  push    rsi
0x140292d69  push    rdi
0x140292d6a  push    r12
0x140292d6c  push    r13
0x140292d6e  push    r14
0x140292d70  push    r15
0x140292d72  sub     rsp, 0B0h
0x140292d79  mov     r14d, r9d
0x140292d7c  mov     rdi, r8
0x140292d7f  mov     rsi, rdx
0x140292d82  xor     eax, eax
0x140292d84  test    r8, r8
0x140292d87  jle     loc_140293477
0x140292d8d  mov     ebx, 0C0000001h
0x140292d92  mov     [r11+10h], al
0x140292d96  mov     r12d, eax
0x140292d99  mov     [rsp+0E8h+var_A0], rax
0x140292d9e  mov     r15d, eax
0x140292da1  mov     [rsp+0E8h+var_98], rax
0x140292da6  mov     [r11+18h], rax
0x140292daa  mov     [rsp+0E8h+var_A8], al
0x140292dae  cmp     [rsp+0E8h+arg_20], rax
0x140292db6  jnz     short loc_140292DD0
0x140292db8  cmp     [rsp+0E8h+arg_28], rax
0x140292dc0  jnz     short loc_140292DD0
0x140292dc2  cmp     [rsp+0E8h+arg_30], rax
0x140292dca  jz      loc_140293477
0x140292dd0  lea     rcx, FsLibExtentsDescriptorLookasideList; Lookaside
0x140292dd7  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140292dde  nop     dword ptr [rax+rax+00h]
0x140292de3  mov     r13, rax
0x140292de6  mov     [rsp+0E8h+var_A0], rax
0x140292deb  test    rax, rax
0x140292dee  jnz     short loc_140292E1B
0x140292df0  lea     r8, aFslibgroupsube_1; "FsLibGroupSubExtentsByDanglingMdl: Fail"...
0x140292df7  mov     edx, 2; Level
0x140292dfc  mov     ecx, 9Ah; ComponentId
0x140292e01  call    cs:__imp_DbgPrintEx
0x140292e08  nop     dword ptr [rax+rax+00h]
0x140292e0d  mov     ebx, 0C000009Ah
0x140292e12  mov     [rsp+0E8h+var_A4], ebx
0x140292e16  jmp     loc_14029342A
0x140292e1b  lea     rcx, FsLibDsmBufferLookasideList; Lookaside
0x140292e22  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140292e29  nop     dword ptr [rax+rax+00h]
0x140292e2e  mov     r15, rax
0x140292e31  mov     [rsp+0E8h+var_98], rax
0x140292e36  test    rax, rax
0x140292e39  jnz     short loc_140292E44
0x140292e3b  lea     r8, aFslibgroupsube_2; "FsLibGroupSubExtentsByDanglingMdl: Fail"...
0x140292e42  jmp     short loc_140292DF7
0x140292e44  mov     r13, r14
0x140292e47  shr     r13, 0Ch
0x140292e4b  mov     rdx, r13
0x140292e4e  imul    rdx, rsi
0x140292e52  mov     [rsp+0E8h+var_68], rdx
0x140292e5a  mov     [rsp+0E8h+var_48], rdx
0x140292e62  mov     rax, r13
0x140292e65  imul    rax, rdi
0x140292e69  mov     [rsp+0E8h+var_70], rax
0x140292e6e  mov     [rsp+0E8h+var_50], rax
0x140292e76  mov     edi, 9Ah
0x140292e7b  mov     r14d, 2
0x140292e81  mov     rcx, [rsp+0E8h+var_A0]
0x140292e86  test    rax, rax
0x140292e89  jle     loc_14029335C
0x140292e8f  mov     qword ptr [rcx], 0FFFCh
0x140292e96  mov     [rsp+0E8h+var_C8], rax
0x140292e9b  mov     r9, rdx
0x140292e9e  lea     r8, aFslibgroupsube; "FsLibGroupSubExtentsByDanglingMdl: Star"...
0x140292ea5  mov     edx, r14d; Level
0x140292ea8  mov     ecx, edi; ComponentId
0x140292eaa  call    cs:__imp_DbgPrintEx
0x140292eb1  nop     dword ptr [rax+rax+00h]
0x140292eb6  mov     r8, [rsp+0E8h+var_70]
0x140292ebb  shl     r8, 0Ch
0x140292ebf  mov     rdx, [rsp+0E8h+var_68]
0x140292ec7  shl     rdx, 0Ch
0x140292ecb  mov     [rsp+0E8h+var_B0], 0FFFD0h; int
0x140292ed3  mov     rax, [rsp+0E8h+var_A0]
0x140292ed8  mov     [rsp+0E8h+var_B8], rax; __int64
0x140292edd  mov     [rsp+0E8h+var_C0], 100000h; int
0x140292ee5  mov     [rsp+0E8h+var_C8], r15; __int64
0x140292eea  mov     r9d, 10000000h
0x140292ef0  mov     rcx, qword ptr [rsp+0E8h+arg_0]; int
0x140292ef8  call    FsLibGetAddressRangesForSingleVolumeExtent
0x140292efd  mov     ebx, eax
0x140292eff  mov     [rsp+0E8h+var_A4], eax
0x140292f03  test    eax, eax
0x140292f05  jns     short loc_140292F27
0x140292f07  mov     r9d, eax
0x140292f0a  lea     r8, aFslibgroupsube_0; "FsLibGroupSubExtentsByDanglingMdl: FsLi"...
0x140292f11  mov     edx, r14d; Level
0x140292f14  mov     ecx, edi; ComponentId
0x140292f16  call    cs:__imp_DbgPrintEx
0x140292f1d  nop     dword ptr [rax+rax+00h]
0x140292f22  jmp     loc_140293425
0x140292f27  xor     eax, eax
0x140292f29  mov     [rsp+0E8h+var_88], eax
0x140292f2d  mov     rcx, [rsp+0E8h+var_A0]
0x140292f32  cmp     eax, [rcx+4]
0x140292f35  jnb     loc_140293345
0x140292f3b  add     rax, rax
0x140292f3e  mov     rdx, [rcx+rax*8+8]
0x140292f43  mov     [rsp+0E8h+var_78], rdx
0x140292f48  mov     [rsp+0E8h+var_90], rdx
0x140292f4d  mov     r15, [rcx+rax*8+10h]
0x140292f52  mov     rax, [rsp+0E8h+var_70]
0x140292f57  sub     rax, r15
0x140292f5a  mov     [rsp+0E8h+var_70], rax
0x140292f5f  mov     [rsp+0E8h+var_50], rax
0x140292f67  mov     rax, [rsp+0E8h+var_68]
0x140292f6f  add     rax, r15
0x140292f72  mov     [rsp+0E8h+var_68], rax
0x140292f7a  mov     [rsp+0E8h+var_48], rax
0x140292f82  mov     rax, [rsp+0E8h+arg_10]
0x140292f8a  mov     qword ptr [rsp+0E8h+var_C0], rax
0x140292f8f  mov     [rsp+0E8h+var_C8], r15
0x140292f94  mov     r9, rdx
0x140292f97  lea     r8, aStartpageI64xP; "StartPage: %I64x, PageCount: %I64x, Pag"...
0x140292f9e  mov     edx, r14d; Level
0x140292fa1  mov     ecx, edi; ComponentId
0x140292fa3  call    cs:__imp_DbgPrintEx
0x140292faa  nop     dword ptr [rax+rax+00h]
0x140292faf  mov     rcx, [rsp+0E8h+arg_10]
0x140292fb7  cmp     r15, rcx
0x140292fba  ja      short loc_140292FD4
0x140292fbc  sub     rcx, r15
0x140292fbf  mov     [rsp+0E8h+arg_10], rcx
0x140292fc7  mov     [rsp+0E8h+var_58], rcx
0x140292fcf  jmp     loc_14029333A
0x140292fd4  mov     rax, [rsp+0E8h+var_78]
0x140292fd9  add     rax, rcx
0x140292fdc  mov     [rsp+0E8h+var_90], rax
0x140292fe1  sub     r15, rcx
0x140292fe4  xor     ecx, ecx
0x140292fe6  mov     [rsp+0E8h+arg_10], rcx
0x140292fee  mov     [rsp+0E8h+var_58], rcx
0x140292ff6  test    r15, r15
0x140292ff9  jz      loc_14029333A
0x140292fff  mov     [rsp+0E8h+var_80], rax
0x140293004  xor     r8d, r8d
0x140293007  mov     rdx, r15
0x14029300a  mov     rcx, rax
0x14029300d  call    cs:__imp_FsRtlIsExtentDangling
0x140293014  nop     dword ptr [rax+rax+00h]
0x140293019  mov     [rsp+0E8h+var_78], rax
0x14029301e  mov     r9, rax
0x140293021  lea     r8, aDanglingpageI6; "DanglingPage: %I64x\n"
0x140293028  mov     edx, r14d; Level
0x14029302b  mov     ecx, edi; ComponentId
0x14029302d  call    cs:__imp_DbgPrintEx
0x140293034  nop     dword ptr [rax+rax+00h]
0x140293039  mov     al, byte ptr [rsp+0E8h+arg_8]
0x140293040  test    al, al
0x140293042  jz      loc_14029315C
0x140293048  mov     rcx, [rsp+0E8h+var_78]
0x14029304d  mov     rax, [rsp+0E8h+var_90]
0x140293052  sub     rcx, rax
0x140293055  cmp     rcx, r13
0x140293058  jnb     short loc_140293092
0x14029305a  add     r12, r13
0x14029305d  mov     [rsp+0E8h+var_60], r12
0x140293065  add     rax, r13
0x140293068  mov     [rsp+0E8h+var_80], rax
0x14029306d  mov     [rsp+0E8h+var_C8], rax
0x140293072  mov     r9, r12
0x140293075  lea     r8, aCase1UpdateSub; "Case 1: Update SubExtentPageCount: %I64"...
0x14029307c  mov     edx, r14d; Level
0x14029307f  mov     ecx, edi; ComponentId
0x140293081  call    cs:__imp_DbgPrintEx
0x140293088  nop     dword ptr [rax+rax+00h]
0x14029308d  jmp     loc_14029314D
0x140293092  xor     edx, edx
0x140293094  mov     rax, r12
0x140293097  div     r13
0x14029309a  mov     r12, rax
0x14029309d  mov     rax, [rsp+0E8h+arg_20]
0x1402930a5  test    rax, rax
0x1402930a8  jz      short loc_1402930EF
0x1402930aa  mov     r8, r12
0x1402930ad  mov     rdx, rsi
0x1402930b0  mov     rcx, rax
0x1402930b3  call    FsLibAppendExtent
0x1402930b8  mov     ebx, eax
0x1402930ba  mov     [rsp+0E8h+var_A4], eax
0x1402930be  test    eax, eax
0x1402930c0  jns     short loc_1402930EF
0x1402930c2  lea     r8, aCase2FailedToA; "Case 2: FAILED to add to ExtentsWithDan"...
0x1402930c9  mov     [rsp+0E8h+var_C0], eax
0x1402930cd  mov     [rsp+0E8h+var_C8], r12
0x1402930d2  mov     r9, rsi
0x1402930d5  xor     edx, edx; Level
0x1402930d7  mov     ecx, edi; ComponentId
0x1402930d9  call    cs:__imp_DbgPrintEx
0x1402930e0  nop     dword ptr [rax+rax+00h]
0x1402930e5  mov     r15, [rsp+0E8h+var_98]
0x1402930ea  jmp     loc_140293425
0x1402930ef  mov     [rsp+0E8h+var_C8], r12
0x1402930f4  mov     r9, rsi
0x1402930f7  lea     r8, aCase2FoundDang; "Case 2: Found dangling MDL. StartCluste"...
0x1402930fe  mov     edx, r14d; Level
0x140293101  mov     ecx, edi; ComponentId
0x140293103  call    cs:__imp_DbgPrintEx
0x14029310a  nop     dword ptr [rax+rax+00h]
0x14029310f  add     rsi, r12
0x140293112  mov     [rsp+0E8h+var_40], rsi
0x14029311a  xor     al, al
0x14029311c  mov     byte ptr [rsp+0E8h+arg_8], al
0x140293123  mov     [rsp+0E8h+var_A7], al
0x140293127  xor     r12d, r12d
0x14029312a  mov     [rsp+0E8h+var_60], r12
0x140293132  mov     r9, rsi
0x140293135  lea     r8, aCase2UpdateSub; "Case 2: Update SubExtentClusterStart: %"...
0x14029313c  mov     edx, r14d; Level
0x14029313f  mov     ecx, edi; ComponentId
0x140293141  call    cs:__imp_DbgPrintEx
0x140293148  nop     dword ptr [rax+rax+00h]
0x14029314d  mov     al, byte ptr [rsp+0E8h+arg_8]
0x140293154  test    al, al
0x140293156  jnz     loc_1402932C4
0x14029315c  mov     rcx, [rsp+0E8h+var_90]
0x140293161  lea     rax, [r15+rcx]
0x140293165  mov     rdx, [rsp+0E8h+var_78]
0x14029316a  cmp     rdx, rax
0x14029316d  jnb     loc_14029328C
0x140293173  mov     r8, rdx
0x140293176  sub     r8, rcx
0x140293179  add     r8, r12
0x14029317c  xor     edx, edx
0x14029317e  mov     rax, r8
0x140293181  div     r13
0x140293184  mov     r12, rax
0x140293187  mov     rcx, [rsp+0E8h+arg_28]
0x14029318f  cmp     [rsp+0E8h+var_A8], 0
0x140293194  jnz     short loc_1402931CF
0x140293196  mov     [rsp+0E8h+var_A8], 1
0x14029319b  cmp     [rsp+0E8h+arg_20], 0
0x1402931a4  jnz     short loc_1402931CF
0x1402931a6  test    rcx, rcx
0x1402931a9  jnz     short loc_1402931CF
0x1402931ab  lea     r9, [rax+rsi]
0x1402931af  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x1402931b3  lea     r8, aCase3FoundFirs; "Case 3: Found first dangling MDL.  Call"...
0x1402931ba  xor     edx, edx; Level
0x1402931bc  mov     ecx, edi; ComponentId
0x1402931be  call    cs:__imp_DbgPrintEx
0x1402931c5  nop     dword ptr [rax+rax+00h]
0x1402931ca  jmp     loc_1402930E5
0x1402931cf  xor     edx, edx
0x1402931d1  mov     rax, r8
0x1402931d4  div     r13
0x1402931d7  mov     rax, r13
0x1402931da  sub     rax, rdx
0x1402931dd  mov     [rsp+0E8h+arg_8], rax
0x1402931e5  test    r12, r12
0x1402931e8  jle     short loc_140293238
0x1402931ea  test    rcx, rcx
0x1402931ed  jz      short loc_140293210
0x1402931ef  mov     r8, r12
0x1402931f2  mov     rdx, rsi
0x1402931f5  call    FsLibAppendExtent
0x1402931fa  mov     ebx, eax
0x1402931fc  mov     [rsp+0E8h+var_A4], eax
0x140293200  test    eax, eax
0x140293202  jns     short loc_140293210
0x140293204  lea     r8, aCase3FailedToA; "Case 3: FAILED to add to ExtentsWithout"...
0x14029320b  jmp     loc_1402930C9
0x140293210  mov     [rsp+0E8h+var_C8], r12
0x140293215  mov     r9, rsi
0x140293218  lea     r8, aCase3NonDangli; "Case 3: Non-dangling range: StartCluste"...
0x14029321f  mov     edx, r14d; Level
0x140293222  mov     ecx, edi; ComponentId
0x140293224  call    cs:__imp_DbgPrintEx
0x14029322b  nop     dword ptr [rax+rax+00h]
0x140293230  mov     rax, [rsp+0E8h+arg_8]
0x140293238  add     rsi, r12
0x14029323b  mov     [rsp+0E8h+var_40], rsi
0x140293243  mov     cl, 1
0x140293245  mov     byte ptr [rsp+0E8h+arg_8], cl
0x14029324c  mov     [rsp+0E8h+var_A7], cl
0x140293250  mov     r12, r13
0x140293253  mov     [rsp+0E8h+var_60], r13
0x14029325b  add     rax, [rsp+0E8h+var_78]
0x140293260  mov     [rsp+0E8h+var_80], rax
0x140293265  mov     qword ptr [rsp+0E8h+var_C0], rax
0x14029326a  mov     [rsp+0E8h+var_C8], r13
0x14029326f  mov     r9, rsi
0x140293272  lea     r8, aCase3UpdateSub; "Case 3: Update SubExtentClusterStart: %"...
0x140293279  mov     edx, r14d; Level
0x14029327c  mov     ecx, edi; ComponentId
0x14029327e  call    cs:__imp_DbgPrintEx
0x140293285  nop     dword ptr [rax+rax+00h]
0x14029328a  jmp     short loc_1402932C4
0x14029328c  add     r12, r15
0x14029328f  mov     [rsp+0E8h+var_60], r12
0x140293297  mov     rax, [rsp+0E8h+var_80]
  ... truncated ...
```
