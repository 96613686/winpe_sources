# AhcCdbRefresh

- ea: `0x140029954`
- end: `0x140029e04`
- name: `AhcCdbRefresh`
- size: `1200`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x14002b128`
- `0x1400438c4`
- `0x1400497bc`

## callees

- `0x1400079f0`
- `0x140024c1c`
- `0x140029954`
- `0x14002dffc`
- `0x14002e034`
- `0x1400341b0`
- `0x140034418`
- `0x14003e364`
- `0x140041d6c`
- `0x140042ad4`
- `0x140044fc8`
- `0x140045d44`
- `0x140054478`
- `0x140055038`
- `0x1400591c4`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400299bf`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400299bf`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140029cfa`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140029cfa`

## string_xrefs

- `0x140029b54`: `SdbSetEaForDb failed to set read timestamp EA for %s database [%x]`
- `0x140029bcb`: `SdbSetEaForDb failed to set read timestamp EA for stub database [%x]`
- `0x140029c18`: `AslFileSecSetEaByPath failed to set read timestamp EA for stub database [%x]`
- `0x140029c81`: `AslFileSecSetEaByPath failed to set read timestamp EA for main database [%x]`
- `0x140029d1b`: `Failed to update CDB timestamps [%x]`

## pseudocode

```c
__int64 __fastcall AhcCdbRefresh(__int64 a1)
{
  struct _ERESOURCE *v2; // rcx
  __int64 v3; // rsi
  int v4; // r15d
  int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r13
  void *v11; // r12
  int MergeStubPath; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  int EaForDb; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  char v19; // bl
  const char *v20; // rcx
  int v21; // eax
  int v22; // eax
  const char *v23; // r9
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r8
  int EaByPath; // eax
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  const char *v33; // r9
  __int64 v34; // r8
  __int64 v35; // [rsp+20h] [rbp-58h]
  char v36; // [rsp+30h] [rbp-48h]
  int v37; // [rsp+34h] [rbp-44h] BYREF
  int v38; // [rsp+38h] [rbp-40h]
  int v39; // [rsp+3Ch] [rbp-3Ch] BYREF
  __int64 v40; // [rsp+40h] [rbp-38h] BYREF
  __int128 v41; // [rsp+48h] [rbp-30h] BYREF
  __int128 v42; // [rsp+58h] [rbp-20h] BYREF

  v39 = 0;
  AslLogCallPrintf(3, "AhcCdbRefresh", 1083, "Enter.");
  v2 = *(struct _ERESOURCE **)a1;
  v3 = 0;
  *(_QWORD *)&v41 = 0x100000010LL;
  v42 = 0;
  v40 = 0;
  v4 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(v2);
  v5 = AhcStoreEnum(*(_QWORD *)(a1 + 8), AhcpStoreEnumEntryClear, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "AhcCdbRefresh", 1114, "Failed to clear cdb before load from pdb [%x]", v5);
    goto LABEL_54;
  }
  v7 = 0;
  v8 = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
      * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
  v9 = 0;
  *((_QWORD *)&v41 + 1) = v8;
  v38 = 0;
  if ( *(_DWORD *)(a1 + 320) )
  {
    while ( 1 )
    {
      v10 = (unsigned int)v9;
      v11 = (void *)SdbOpenDatabaseEx(*(_QWORD *)(a1 + 8 * v9 + 48), v8, 0);
      if ( !v11 )
      {
        AslLogCallPrintf(1, "AhcCdbRefresh", 1129, "Failed to initialize database");
        v6 = -1073741811;
        goto LABEL_52;
      }
      v36 = 0;
      MergeStubPath = SdbGetMergeStubPath(&v40, *(_QWORD *)(a1 + 8 * v10 + 48));
      v3 = v40;
      v6 = MergeStubPath;
      if ( MergeStubPath != -1073741772 )
      {
        if ( MergeStubPath < 0 )
        {
          v33 = "Unable to find merge stub database [%x]";
          v34 = 1140;
          goto LABEL_64;
        }
        if ( (unsigned int)SdbPdbIsRedirected(v11, *(_QWORD *)(a1 + 8 * v10 + 48)) )
        {
          v36 = 1;
        }
        else
        {
          v7 = (void *)SdbOpenDatabaseEx(v3, v13, 0);
          if ( !v7 )
          {
            AslLogCallPrintf(1, "AhcCdbRefresh", 1152, "Failed to initialize stub database");
            v6 = -1073741811;
            goto LABEL_65;
          }
        }
      }
      MergeStubPath = AhcpCdbLoadDb(*(PRTL_AVL_TABLE *)(a1 + 8), v11);
      v6 = MergeStubPath;
      if ( MergeStubPath < 0 )
      {
        v33 = "Failed to load database [%x]";
        v34 = 1161;
LABEL_64:
        LODWORD(v35) = MergeStubPath;
        AslLogCallPrintf(1, "AhcCdbRefresh", v34, v33, v35);
LABEL_65:
        SdbCloseDatabaseRead(v11);
        goto LABEL_52;
      }
      if ( v7 )
      {
        MergeStubPath = AhcpCdbLoadDb(*(PRTL_AVL_TABLE *)(a1 + 8), v7);
        v6 = MergeStubPath;
        if ( MergeStubPath < 0 )
        {
          v33 = "Failed to load stub database [%x]";
          v34 = 1168;
          goto LABEL_64;
        }
      }
      v37 = 16;
      EaForDb = SdbGetEaForDb(v11, v14, &v42, &v37);
      if ( EaForDb >= 0 || EaForDb == -1073741745 || EaForDb == -2147483629 )
      {
        v19 = v36;
      }
      else
      {
        v18 = SdbSetEaForDb((__int64 *)v11);
        if ( v18 >= 0 || v18 == -1073741745 )
        {
          v19 = v36;
        }
        else
        {
          v19 = v36;
          if ( v18 != -2147483629 )
          {
            v20 = "merged";
            if ( !v36 )
              v20 = "main";
            AslLogCallPrintf(
              1,
              "AhcCdbRefresh",
              1187,
              "SdbSetEaForDb failed to set read timestamp EA for %s database [%x]",
              v20,
              v18);
          }
        }
        v4 = 1;
      }
      if ( !v7 )
        break;
      v37 = 16;
      v21 = SdbGetEaForDb(v7, v16, &v42, &v37);
      if ( v21 >= 0 || v21 == -1073741745 || v21 == -2147483629 )
        goto LABEL_39;
      v22 = SdbSetEaForDb((__int64 *)v7);
      if ( v22 < 0 )
      {
        v23 = "SdbSetEaForDb failed to set read timestamp EA for stub database [%x]";
        v24 = 1201;
LABEL_37:
        LODWORD(v35) = v22;
        AslLogCallPrintf(1, "AhcCdbRefresh", v24, v23, v35);
      }
LABEL_38:
      v4 = 1;
LABEL_39:
      if ( v19 )
      {
        v37 = 16;
        EaByPath = AslFileSecGetEaByPath(&v42);
        if ( EaByPath < 0 && EaByPath != -1073741745 && EaByPath != -2147483629 )
        {
          v29 = AslFileSecSetEaByPath(v17, &v41, v28, *(_QWORD *)(a1 + 8 * v10 + 48));
          if ( v29 < 0 )
            AslLogCallPrintf(
              1,
              "AhcCdbRefresh",
              1245,
              "AslFileSecSetEaByPath failed to set read timestamp EA for main database [%x]",
              v29);
          v4 = 1;
        }
      }
      if ( v7 )
      {
        SdbCloseDatabaseRead(v7);
        v7 = 0;
      }
      if ( v3 )
      {
        AslFree(v17, v3);
        v3 = 0;
        v40 = 0;
      }
      SdbCloseDatabaseRead(v11);
      v9 = (unsigned int)(v38 + 1);
      v38 = v9;
      if ( (unsigned int)v9 >= *(_DWORD *)(a1 + 320) )
        goto LABEL_51;
    }
    if ( !v3 )
      goto LABEL_39;
    v37 = 16;
    v25 = AslFileSecGetEaByPath(&v42);
    if ( v25 >= 0 || v25 == -1073741745 || v25 == -2147483629 )
      goto LABEL_39;
    v22 = AslFileSecSetEaByPath(v17, &v41, v26, v3);
    if ( v22 >= 0 )
      goto LABEL_38;
    v23 = "AslFileSecSetEaByPath failed to set read timestamp EA for stub database [%x]";
    v24 = 1222;
    goto LABEL_37;
  }
LABEL_51:
  v6 = 0;
LABEL_52:
  if ( v7 )
    SdbCloseDatabaseRead(v7);
LABEL_54:
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a1);
  if ( v4 )
  {
    v31 = AhcCdbDetectServicing(&v39, a1);
    if ( v31 < 0 )
      AslLogCallPrintf(1, "AhcCdbRefresh", 1294, "Failed to update CDB timestamps [%x]", v31);
  }
  if ( v3 )
    AslFree(v30, v3);
  return v6;
}

```

## disassembly

```asm
0x140029954  push    rbp
0x140029956  push    rbx
0x140029957  push    rsi
0x140029958  push    rdi
0x140029959  push    r12
0x14002995b  push    r13
0x14002995d  push    r14
0x14002995f  push    r15
0x140029961  mov     rbp, rsp
0x140029964  sub     rsp, 78h
0x140029968  mov     rax, cs:__security_cookie
0x14002996f  xor     rax, rsp
0x140029972  mov     [rbp+var_10], rax
0x140029976  mov     r14, rcx
0x140029979  mov     [rbp+var_3C], 0
0x140029980  mov     ecx, 3
0x140029985  lea     r9, aEnter; "Enter."
0x14002998c  mov     r8d, 43Bh
0x140029992  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029999  call    AslLogCallPrintf
0x14002999e  mov     rcx, [r14]; Resource
0x1400299a1  xorps   xmm0, xmm0
0x1400299a4  xor     esi, esi
0x1400299a6  mov     [rbp+var_30], 10h
0x1400299ad  movups  [rbp+var_20], xmm0
0x1400299b1  mov     [rbp+var_38], rsi
0x1400299b5  xor     r15d, r15d
0x1400299b8  mov     [rbp+var_2C], 1
0x1400299bf  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400299c6  nop     dword ptr [rax+rax+00h]
0x1400299cb  mov     rcx, [r14+8]
0x1400299cf  lea     rdx, AhcpStoreEnumEntryClear
0x1400299d6  xor     r8d, r8d
0x1400299d9  call    AhcStoreEnum
0x1400299de  mov     ebx, eax
0x1400299e0  test    eax, eax
0x1400299e2  jns     short loc_140029A09
0x1400299e4  lea     r9, aFailedToClearC; "Failed to clear cdb before load from pd"...
0x1400299eb  mov     dword ptr [rsp+78h+var_58], eax
0x1400299ef  mov     r8d, 45Ah
0x1400299f5  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x1400299fc  lea     ecx, [rsi+1]
0x1400299ff  call    AslLogCallPrintf
0x140029a04  jmp     loc_140029CF7
0x140029a09  mov     rax, 0FFFFF78000000004h
0x140029a13  xor     edi, edi
0x140029a15  mov     ecx, [rax]
0x140029a17  mov     rax, 0FFFFF78000000320h
0x140029a21  shl     rcx, 20h
0x140029a25  mov     rax, [rax]
0x140029a28  shl     rax, 8
0x140029a2c  mul     rcx
0x140029a2f  xor     eax, eax
0x140029a31  mov     [rbp+var_28], rdx
0x140029a35  mov     [rbp+var_40], eax
0x140029a38  cmp     [r14+140h], eax
0x140029a3f  jbe     loc_140029CE8
0x140029a45  mov     rcx, [r14+rax*8+30h]
0x140029a4a  xor     r8d, r8d
0x140029a4d  mov     r13d, eax
0x140029a50  call    SdbOpenDatabaseEx
0x140029a55  mov     r12, rax
0x140029a58  test    rax, rax
0x140029a5b  jz      loc_140029DDC
0x140029a61  mov     rdx, [r14+r13*8+30h]
0x140029a66  lea     rcx, [rbp+var_38]
0x140029a6a  mov     [rbp+var_48], 0
0x140029a6e  call    SdbGetMergeStubPath
0x140029a73  mov     rsi, [rbp+var_38]
0x140029a77  mov     ebx, eax
0x140029a79  cmp     eax, 0C0000034h
0x140029a7e  jz      short loc_140029AB6
0x140029a80  test    eax, eax
0x140029a82  js      loc_140029D8F
0x140029a88  mov     rdx, [r14+r13*8+30h]
0x140029a8d  mov     rcx, r12
0x140029a90  call    SdbPdbIsRedirected
0x140029a95  test    eax, eax
0x140029a97  jz      short loc_140029A9F
0x140029a99  mov     [rbp+var_48], 1
0x140029a9d  jmp     short loc_140029AB6
0x140029a9f  xor     r8d, r8d
0x140029aa2  mov     rcx, rsi
0x140029aa5  call    SdbOpenDatabaseEx
0x140029aaa  mov     rdi, rax
0x140029aad  test    rax, rax
0x140029ab0  jz      loc_140029D6A
0x140029ab6  mov     rcx, [r14+8]
0x140029aba  mov     r8, rdi
0x140029abd  mov     rdx, r12
0x140029ac0  call    AhcpCdbLoadDb
0x140029ac5  mov     ebx, eax
0x140029ac7  test    eax, eax
0x140029ac9  js      loc_140029DAD
0x140029acf  test    rdi, rdi
0x140029ad2  jz      short loc_140029AED
0x140029ad4  mov     rcx, [r14+8]
0x140029ad8  xor     r8d, r8d
0x140029adb  mov     rdx, rdi
0x140029ade  call    AhcpCdbLoadDb
0x140029ae3  mov     ebx, eax
0x140029ae5  test    eax, eax
0x140029ae7  js      loc_140029D9E
0x140029aed  lea     r9, [rbp+var_44]
0x140029af1  mov     [rbp+var_44], 10h
0x140029af8  lea     r8, [rbp+var_20]
0x140029afc  mov     rcx, r12
0x140029aff  call    SdbGetEaForDb
0x140029b04  test    eax, eax
0x140029b06  jns     short loc_140029B7E
0x140029b08  mov     ebx, 0C000004Fh
0x140029b0d  cmp     eax, ebx
0x140029b0f  jz      short loc_140029B7E
0x140029b11  cmp     eax, 80000013h
0x140029b16  jz      short loc_140029B7E
0x140029b18  lea     r8, [rbp+var_30]
0x140029b1c  mov     rcx, r12
0x140029b1f  call    SdbSetEaForDb
0x140029b24  test    eax, eax
0x140029b26  jns     short loc_140029B73
0x140029b28  cmp     eax, ebx
0x140029b2a  jz      short loc_140029B73
0x140029b2c  mov     bl, [rbp+var_48]
0x140029b2f  cmp     eax, 80000013h
0x140029b34  jz      short loc_140029B76
0x140029b36  test    bl, bl
0x140029b38  mov     [rsp+78h+var_50], eax
0x140029b3c  lea     rdx, aMain; "main"
0x140029b43  mov     r8d, 4A3h
0x140029b49  lea     rcx, aMerged; "merged"
0x140029b50  cmovz   rcx, rdx
0x140029b54  lea     r9, aSdbseteafordbF; "SdbSetEaForDb failed to set read timest"...
0x140029b5b  mov     [rsp+78h+var_58], rcx
0x140029b60  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029b67  mov     ecx, 1
0x140029b6c  call    AslLogCallPrintf
0x140029b71  jmp     short loc_140029B76
0x140029b73  mov     bl, [rbp+var_48]
0x140029b76  mov     r15d, 1
0x140029b7c  jmp     short loc_140029B81
0x140029b7e  mov     bl, [rbp+var_48]
0x140029b81  test    rdi, rdi
0x140029b84  jz      short loc_140029BDA
0x140029b86  lea     r9, [rbp+var_44]
0x140029b8a  mov     [rbp+var_44], 10h
0x140029b91  lea     r8, [rbp+var_20]
0x140029b95  mov     rcx, rdi
0x140029b98  call    SdbGetEaForDb
0x140029b9d  test    eax, eax
0x140029b9f  jns     loc_140029C40
0x140029ba5  cmp     eax, 0C000004Fh
0x140029baa  jz      loc_140029C40
0x140029bb0  cmp     eax, 80000013h
0x140029bb5  jz      loc_140029C40
0x140029bbb  lea     r8, [rbp+var_30]
0x140029bbf  mov     rcx, rdi
0x140029bc2  call    SdbSetEaForDb
0x140029bc7  test    eax, eax
0x140029bc9  jns     short loc_140029C3A
0x140029bcb  lea     r9, aSdbseteafordbF_0; "SdbSetEaForDb failed to set read timest"...
0x140029bd2  mov     r8d, 4B1h
0x140029bd8  jmp     short loc_140029C25
0x140029bda  test    rsi, rsi
0x140029bdd  jz      short loc_140029C40
0x140029bdf  mov     r9, rsi
0x140029be2  mov     [rbp+var_44], 10h
0x140029be9  lea     rdx, [rbp+var_44]
0x140029bed  lea     rcx, [rbp+var_20]; void *
0x140029bf1  call    AslFileSecGetEaByPath
0x140029bf6  test    eax, eax
0x140029bf8  jns     short loc_140029C40
0x140029bfa  cmp     eax, 0C000004Fh
0x140029bff  jz      short loc_140029C40
0x140029c01  cmp     eax, 80000013h
0x140029c06  jz      short loc_140029C40
0x140029c08  mov     r9, rsi
0x140029c0b  lea     rdx, [rbp+var_30]
0x140029c0f  call    AslFileSecSetEaByPath
0x140029c14  test    eax, eax
0x140029c16  jns     short loc_140029C3A
0x140029c18  lea     r9, aAslfilesecsete; "AslFileSecSetEaByPath failed to set rea"...
0x140029c1f  mov     r8d, 4C6h
0x140029c25  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029c2c  mov     dword ptr [rsp+78h+var_58], eax
0x140029c30  mov     ecx, 1
0x140029c35  call    AslLogCallPrintf
0x140029c3a  mov     r15d, 1
0x140029c40  test    bl, bl
0x140029c42  jz      short loc_140029CA9
0x140029c44  mov     r9, [r14+r13*8+30h]
0x140029c49  lea     rdx, [rbp+var_44]
0x140029c4d  lea     rcx, [rbp+var_20]; void *
0x140029c51  mov     [rbp+var_44], 10h
0x140029c58  call    AslFileSecGetEaByPath
0x140029c5d  test    eax, eax
0x140029c5f  jns     short loc_140029CA9
0x140029c61  cmp     eax, 0C000004Fh
0x140029c66  jz      short loc_140029CA9
0x140029c68  cmp     eax, 80000013h
0x140029c6d  jz      short loc_140029CA9
0x140029c6f  mov     r9, [r14+r13*8+30h]
0x140029c74  lea     rdx, [rbp+var_30]
0x140029c78  call    AslFileSecSetEaByPath
0x140029c7d  test    eax, eax
0x140029c7f  jns     short loc_140029CA3
0x140029c81  lea     r9, aAslfilesecsete_3; "AslFileSecSetEaByPath failed to set rea"...
0x140029c88  mov     dword ptr [rsp+78h+var_58], eax
0x140029c8c  mov     r8d, 4DDh
0x140029c92  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029c99  mov     ecx, 1
0x140029c9e  call    AslLogCallPrintf
0x140029ca3  mov     r15d, 1
0x140029ca9  test    rdi, rdi
0x140029cac  jz      short loc_140029CB8
0x140029cae  mov     rcx, rdi
0x140029cb1  call    SdbCloseDatabaseRead
0x140029cb6  xor     edi, edi
0x140029cb8  test    rsi, rsi
0x140029cbb  jz      short loc_140029CCB
0x140029cbd  mov     rdx, rsi
0x140029cc0  call    AslFree
0x140029cc5  xor     esi, esi
0x140029cc7  mov     [rbp+var_38], rsi
0x140029ccb  mov     rcx, r12
0x140029cce  call    SdbCloseDatabaseRead
0x140029cd3  mov     eax, [rbp+var_40]
0x140029cd6  inc     eax
0x140029cd8  mov     [rbp+var_40], eax
0x140029cdb  cmp     eax, [r14+140h]
0x140029ce2  jb      loc_140029A45
0x140029ce8  xor     ebx, ebx
0x140029cea  test    rdi, rdi
0x140029ced  jz      short loc_140029CF7
0x140029cef  mov     rcx, rdi
0x140029cf2  call    SdbCloseDatabaseRead
0x140029cf7  mov     rcx, [r14]; Resource
0x140029cfa  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140029d01  nop     dword ptr [rax+rax+00h]
0x140029d06  test    r15d, r15d
0x140029d09  jz      short loc_140029D3D
0x140029d0b  mov     rdx, r14
0x140029d0e  lea     rcx, [rbp+var_3C]
0x140029d12  call    AhcCdbDetectServicing
0x140029d17  test    eax, eax
0x140029d19  jns     short loc_140029D3D
0x140029d1b  lea     r9, aFailedToUpdate_2; "Failed to update CDB timestamps [%x]"
0x140029d22  mov     dword ptr [rsp+78h+var_58], eax
0x140029d26  mov     r8d, 50Eh
0x140029d2c  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029d33  mov     ecx, 1
0x140029d38  call    AslLogCallPrintf
0x140029d3d  test    rsi, rsi
0x140029d40  jz      short loc_140029D4A
0x140029d42  mov     rdx, rsi
0x140029d45  call    AslFree
0x140029d4a  mov     eax, ebx
0x140029d4c  mov     rcx, [rbp+var_10]
0x140029d50  xor     rcx, rsp; StackCookie
0x140029d53  call    __security_check_cookie
0x140029d58  add     rsp, 78h
0x140029d5c  pop     r15
0x140029d5e  pop     r14
0x140029d60  pop     r13
0x140029d62  pop     r12
0x140029d64  pop     rdi
0x140029d65  pop     rsi
0x140029d66  pop     rbx
0x140029d67  pop     rbp
0x140029d68  retn
0x140029d6a  lea     r9, aFailedToInitia_14; "Failed to initialize stub database"
0x140029d71  mov     r8d, 480h
0x140029d77  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029d7e  mov     ecx, 1
0x140029d83  call    AslLogCallPrintf
0x140029d88  mov     ebx, 0C000000Dh
0x140029d8d  jmp     short loc_140029DCF
0x140029d8f  lea     r9, aUnableToFindMe_0; "Unable to find merge stub database [%x]"
0x140029d96  mov     r8d, 474h
0x140029d9c  jmp     short loc_140029DBA
0x140029d9e  lea     r9, aFailedToLoadSt_0; "Failed to load stub database [%x]"
0x140029da5  mov     r8d, 490h
0x140029dab  jmp     short loc_140029DBA
0x140029dad  lea     r9, aFailedToLoadDa; "Failed to load database [%x]"
0x140029db4  mov     r8d, 489h
0x140029dba  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029dc1  mov     dword ptr [rsp+78h+var_58], eax
0x140029dc5  mov     ecx, 1
0x140029dca  call    AslLogCallPrintf
0x140029dcf  mov     rcx, r12
0x140029dd2  call    SdbCloseDatabaseRead
0x140029dd7  jmp     loc_140029CEA
0x140029ddc  lea     r9, aFailedToInitia_12; "Failed to initialize database"
0x140029de3  mov     r8d, 469h
0x140029de9  lea     rdx, aAhccdbrefresh; "AhcCdbRefresh"
0x140029df0  mov     ecx, 1
0x140029df5  call    AslLogCallPrintf
0x140029dfa  mov     ebx, 0C000000Dh
0x140029dff  jmp     loc_140029CEA
```
