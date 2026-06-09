# SdbOpenDatabaseEx

- ea: `0x18005ec7c`
- end: `0x18005efa6`
- name: `SdbOpenDatabaseEx`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005e5f0`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800543c0`
- `0x180054fd4`
- `0x1800552d4`
- `0x180055470`
- `0x18005a3d4`
- `0x18005e998`
- `0x18005ec7c`
- `0x180060330`
- `0x180060674`
- `0x180061e78`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18005ed02`
- `ntdll!RtlAllocateHeap` at `0x18005ed02`
- `ntdll!RtlFreeHeap` at `0x18005ee1d`
- `ntdll!RtlFreeHeap` at `0x18005ef85`
- `ntdll!RtlFreeHeap` at `0x18005ee1d`
- `ntdll!RtlFreeHeap` at `0x18005ef85`

## string_xrefs

- `0x18005ec9c`: `SdbOpenDatabaseEx`
- `0x18005edc3`: `SdbOpenDatabaseEx`
- `0x18005edef`: `SdbOpenDatabaseEx`
- `0x18005ee49`: `SdbOpenDatabaseEx`
- `0x18005ef17`: `SdbOpenDatabaseEx`
- `0x18005ef53`: `SdbOpenDatabaseEx`
- `0x18005ecb7`: `Flags:%d; DatabasePath:%ws`
- `0x18005eddd`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x18005edb2`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x18005ef46`: `Failed to open SDB - File size too large or small.`
- `0x18005ee3c`: `Failed to create file mapping [%x]`
- `0x18005eec1`: `Failed to read database header`
- `0x18005ef0a`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const WCHAR *a1)
{
  const OLECHAR *v2; // rax
  _QWORD *Heap; // rax
  _QWORD *v4; // rbx
  int MergeRedirectPath; // eax
  int v6; // r15d
  int v7; // esi
  const wchar_t *FileNamePart; // rax
  int v9; // eax
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v16; // [rsp+20h] [rbp-48h]
  PVOID P; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h] BYREF
  int v21; // [rsp+50h] [rbp-18h]

  v20 = 0;
  v21 = 0;
  v18 = 0;
  v2 = a1;
  if ( !a1 )
    v2 = &psz;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", 0, v2);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v19 = Heap;
  v4 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    P = 0;
    MergeRedirectPath = SdbGetMergeRedirectPath(&P, &v18, 1, a1);
    v6 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v7 = v6;
    }
    else if ( P )
    {
      if ( v18 )
      {
        FileNamePart = (const wchar_t *)AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v9 = AslFileMappingCreate(v4, (const WCHAR *)P);
      v7 = v9;
      if ( v9 < 0 )
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2558, "Failed to create file mapping for redirected SDB file [%x]", v9);
    }
    else
    {
      v7 = -1073741772;
    }
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( v7 < 0 || !*v4 )
    {
      v10 = AslFileMappingCreate(v4, a1);
      if ( v10 < 0 )
      {
        v11 = "Failed to create file mapping [%x]";
        v12 = 2580;
LABEL_21:
        LODWORD(v16) = v10;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v12, v11, v16);
        goto LABEL_39;
      }
    }
    v13 = *(_QWORD *)(*v4 + 24LL);
    if ( (unsigned __int64)(v13 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
    }
    else
    {
      v10 = AslFileMappingEnsureMappedAsEx();
      if ( v10 < 0 )
      {
        v11 = "Failed to map SDB [%x]";
        v12 = 2595;
        goto LABEL_21;
      }
      *((_DWORD *)v4 + 4) = 0;
      *((_DWORD *)v4 + 5) = v13;
      v14 = *v4;
      if ( *v4 )
        v14 = *(_QWORD *)(v14 + 32);
      v4[1] = v14;
      if ( !(unsigned int)SdbpReadMappedData(v4, 0, &v20, 12) )
      {
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
        goto LABEL_39;
      }
      v10 = v21;
      if ( v21 != 1717724275 )
      {
        if ( v21 != 1717724282 )
        {
          v11 = "Magic does not match a valid value: 0x%lx";
          v12 = 2621;
          goto LABEL_21;
        }
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v19) )
        {
          AslLogCallPrintf(
            1,
            "SdbOpenDatabaseEx",
            2627,
            "SdbpOpenCompressedDatabase failed to open compressed database.");
          v4 = v19;
          goto LABEL_39;
        }
        return v19;
      }
      if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v4, &v20) )
        return v4;
    }
LABEL_39:
    if ( v4 )
    {
      AslFileMappingDelete((PVOID)*v4);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    return 0;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x18005ec7c  push    rbp
0x18005ec7e  push    rbx
0x18005ec7f  push    rsi
0x18005ec80  push    rdi
0x18005ec81  push    r12
0x18005ec83  push    r15
0x18005ec85  mov     rbp, rsp
0x18005ec88  sub     rsp, 68h
0x18005ec8c  mov     rax, cs:__security_cookie
0x18005ec93  xor     rax, rsp
0x18005ec96  mov     [rbp+var_10], rax
0x18005ec9a  xor     eax, eax
0x18005ec9c  lea     rsi, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005eca3  mov     r12, rcx
0x18005eca6  mov     [rbp+var_20], rax
0x18005ecaa  mov     [rbp+var_18], eax
0x18005ecad  lea     rcx, psz
0x18005ecb4  mov     [rbp+var_30], eax
0x18005ecb7  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x18005ecbe  test    r12, r12
0x18005ecc1  mov     rax, r12
0x18005ecc4  mov     r8d, 9C5h
0x18005ecca  mov     rdx, rsi
0x18005eccd  cmovz   rax, rcx
0x18005ecd1  mov     ecx, 3
0x18005ecd6  mov     [rsp+68h+var_40], rax
0x18005ecdb  mov     dword ptr [rsp+68h+var_48], 0
0x18005ece3  call    AslLogCallPrintf
0x18005ece8  mov     rcx, gs:60h
0x18005ecf1  mov     edi, 0A80h
0x18005ecf6  mov     r8d, edi; Size
0x18005ecf9  mov     edx, 8; Flags
0x18005ecfe  mov     rcx, [rcx+30h]; HeapHandle
0x18005ed02  call    cs:__imp_RtlAllocateHeap
0x18005ed08  mov     [rbp+var_28], rax
0x18005ed0c  mov     rbx, rax
0x18005ed0f  test    rax, rax
0x18005ed12  jnz     short loc_18005ED31
0x18005ed14  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x18005ed1b  mov     r8d, 9CDh
0x18005ed21  mov     rdx, rsi
0x18005ed24  lea     ecx, [rax+1]
0x18005ed27  call    AslLogCallPrintf
0x18005ed2c  jmp     loc_18005EF8B
0x18005ed31  mov     r8, rdi; Size
0x18005ed34  xor     edx, edx; Val
0x18005ed36  mov     rcx, rbx; void *
0x18005ed39  call    memset_0
0x18005ed3e  mov     edi, 1
0x18005ed43  mov     [rbp+P], 0
0x18005ed4b  mov     r8d, edi
0x18005ed4e  lea     rdx, [rbp+var_30]
0x18005ed52  mov     r9, r12
0x18005ed55  lea     rcx, [rbp+P]
0x18005ed59  call    SdbGetMergeRedirectPath
0x18005ed5e  mov     r15d, eax
0x18005ed61  test    eax, eax
0x18005ed63  js      short loc_18005EDD3
0x18005ed65  cmp     [rbp+P], 0
0x18005ed6a  jnz     short loc_18005ED76
0x18005ed6c  mov     esi, 0C0000034h
0x18005ed71  jmp     loc_18005EE03
0x18005ed76  cmp     [rbp+var_30], 0
0x18005ed7a  jz      short loc_18005EDA0
0x18005ed7c  mov     rcx, r12
0x18005ed7f  call    AslPathGetFileNamePart
0x18005ed84  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x18005ed8b  mov     [rsp+68h+var_48], rax
0x18005ed90  mov     r8d, 9EBh
0x18005ed96  mov     rdx, rsi
0x18005ed99  mov     ecx, edi
0x18005ed9b  call    AslLogCallPrintf
0x18005eda0  mov     rdx, [rbp+P]
0x18005eda4  mov     rcx, rbx
0x18005eda7  call    AslFileMappingCreate
0x18005edac  mov     esi, eax
0x18005edae  test    eax, eax
0x18005edb0  jns     short loc_18005EE03
0x18005edb2  lea     r9, aFailedToCreate_1; "Failed to create file mapping for redir"...
0x18005edb9  mov     dword ptr [rsp+68h+var_48], eax
0x18005edbd  mov     r8d, 9FEh
0x18005edc3  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005edca  mov     ecx, edi
0x18005edcc  call    AslLogCallPrintf
0x18005edd1  jmp     short loc_18005EE03
0x18005edd3  mov     esi, 0C0000034h
0x18005edd8  cmp     r15d, esi
0x18005eddb  jz      short loc_18005EE00
0x18005eddd  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x18005ede4  mov     dword ptr [rsp+68h+var_48], r15d
0x18005ede9  mov     r8d, 9DFh
0x18005edef  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005edf6  mov     ecx, 3
0x18005edfb  call    AslLogCallPrintf
0x18005ee00  mov     esi, r15d
0x18005ee03  cmp     [rbp+P], 0
0x18005ee08  jz      short loc_18005EE23
0x18005ee0a  mov     rcx, gs:60h
0x18005ee13  xor     edx, edx; Flags
0x18005ee15  mov     r8, [rbp+P]; P
0x18005ee19  mov     rcx, [rcx+30h]; HeapHandle
0x18005ee1d  call    cs:__imp_RtlFreeHeap
0x18005ee23  test    esi, esi
0x18005ee25  js      short loc_18005EE2D
0x18005ee27  cmp     qword ptr [rbx], 0
0x18005ee2b  jnz     short loc_18005EE60
0x18005ee2d  mov     rdx, r12
0x18005ee30  mov     rcx, rbx
0x18005ee33  call    AslFileMappingCreate
0x18005ee38  test    eax, eax
0x18005ee3a  jns     short loc_18005EE60
0x18005ee3c  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x18005ee43  mov     r8d, 0A14h
0x18005ee49  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005ee50  mov     dword ptr [rsp+68h+var_48], eax
0x18005ee54  mov     ecx, edi
0x18005ee56  call    AslLogCallPrintf
0x18005ee5b  jmp     loc_18005EF61
0x18005ee60  mov     rcx, [rbx]
0x18005ee63  mov     rsi, [rcx+18h]
0x18005ee67  lea     rax, [rsi-2Ah]
0x18005ee6b  cmp     rax, 0FFFFFD5h
0x18005ee71  ja      loc_18005EF46
0x18005ee77  call    AslFileMappingEnsureMappedAsEx
0x18005ee7c  test    eax, eax
0x18005ee7e  jns     short loc_18005EE8F
0x18005ee80  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x18005ee87  mov     r8d, 0A23h
0x18005ee8d  jmp     short loc_18005EE49
0x18005ee8f  mov     dword ptr [rbx+10h], 0
0x18005ee96  mov     [rbx+14h], esi
0x18005ee99  mov     rax, [rbx]
0x18005ee9c  test    rax, rax
0x18005ee9f  jz      short loc_18005EEA5
0x18005eea1  mov     rax, [rax+20h]
0x18005eea5  mov     r9d, 0Ch
0x18005eeab  mov     [rbx+8], rax
0x18005eeaf  lea     r8, [rbp+var_20]
0x18005eeb3  xor     edx, edx
0x18005eeb5  mov     rcx, rbx
0x18005eeb8  call    SdbpReadMappedData
0x18005eebd  test    eax, eax
0x18005eebf  jnz     short loc_18005EED3
0x18005eec1  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x18005eec8  mov     r8d, 0A30h
0x18005eece  jmp     loc_18005EF53
0x18005eed3  mov     eax, [rbp+var_18]
0x18005eed6  cmp     eax, 66626473h
0x18005eedb  jz      short loc_18005EEF6
0x18005eedd  cmp     eax, 6662647Ah
0x18005eee2  jz      short loc_18005EEFD
0x18005eee4  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x18005eeeb  mov     r8d, 0A3Dh
0x18005eef1  jmp     loc_18005EE49
0x18005eef6  cmp     eax, 6662647Ah
0x18005eefb  jnz     short loc_18005EF31
0x18005eefd  lea     rcx, [rbp+var_28]
0x18005ef01  call    SdbpOpenCompressedDatabase
0x18005ef06  test    eax, eax
0x18005ef08  jnz     short loc_18005EF2B
0x18005ef0a  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x18005ef11  mov     r8d, 0A43h
0x18005ef17  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005ef1e  mov     ecx, edi
0x18005ef20  call    AslLogCallPrintf
0x18005ef25  mov     rbx, [rbp+var_28]
0x18005ef29  jmp     short loc_18005EF61
0x18005ef2b  mov     rbx, [rbp+var_28]
0x18005ef2f  jmp     short loc_18005EF41
0x18005ef31  lea     rdx, [rbp+var_20]
0x18005ef35  mov     rcx, rbx
0x18005ef38  call    SdbpValidateAndApplyCompatFlags
0x18005ef3d  test    eax, eax
0x18005ef3f  jz      short loc_18005EF61
0x18005ef41  mov     rax, rbx
0x18005ef44  jmp     short loc_18005EF8D
0x18005ef46  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x18005ef4d  mov     r8d, 0A1Dh
0x18005ef53  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18005ef5a  mov     ecx, edi
0x18005ef5c  call    AslLogCallPrintf
0x18005ef61  test    rbx, rbx
0x18005ef64  jz      short loc_18005EF8B
0x18005ef66  mov     rcx, [rbx]; P
0x18005ef69  call    AslFileMappingDelete
0x18005ef6e  test    rbx, rbx
0x18005ef71  jz      short loc_18005EF8B
0x18005ef73  mov     rcx, gs:60h
0x18005ef7c  mov     r8, rbx; P
0x18005ef7f  xor     edx, edx; Flags
0x18005ef81  mov     rcx, [rcx+30h]; HeapHandle
0x18005ef85  call    cs:__imp_RtlFreeHeap
0x18005ef8b  xor     eax, eax
0x18005ef8d  mov     rcx, [rbp+var_10]
0x18005ef91  xor     rcx, rsp; StackCookie
0x18005ef94  call    __security_check_cookie
0x18005ef99  add     rsp, 68h
0x18005ef9d  pop     r15
0x18005ef9f  pop     r12
0x18005efa1  pop     rdi
0x18005efa2  pop     rsi
0x18005efa3  pop     rbx
0x18005efa4  pop     rbp
0x18005efa5  retn
```
