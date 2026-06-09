# SdbOpenDatabaseEx

- ea: `0x140037870`
- end: `0x140037bdd`
- name: `SdbOpenDatabaseEx`
- size: `877`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400346cc`
- `0x140034d80`

## callees

- `0x140037448`
- `0x140037870`
- `0x140039144`
- `0x1400393a4`
- `0x14003bd8c`
- `0x14003bf18`
- `0x14003c368`
- `0x14003cb70`
- `0x14003ce04`
- `0x14003cf38`
- `0x14003d3c8`
- `0x14003dec0`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400378fb`
- `ntdll!RtlAllocateHeap` at `0x1400378fb`

## string_xrefs

- `0x14003789a`: `Flags:%d; DatabasePath:%ws`
- `0x1400378b5`: `SdbOpenDatabaseEx`
- `0x14003791a`: `SdbOpenDatabaseEx`
- `0x1400379af`: `SdbOpenDatabaseEx`
- `0x1400379ef`: `SdbOpenDatabaseEx`
- `0x140037a1b`: `SdbOpenDatabaseEx`
- `0x140037a75`: `SdbOpenDatabaseEx`
- `0x140037b47`: `SdbOpenDatabaseEx`
- `0x140037b86`: `SdbOpenDatabaseEx`
- `0x140037a09`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x1400379de`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x140037b79`: `Failed to open SDB - File size too large or small.`
- `0x140037a68`: `Failed to create file mapping [%x]`
- `0x140037ae9`: `Failed to read database header`
- `0x140037b3a`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const wchar_t *a1, __int64 a2, unsigned int a3)
{
  const unsigned __int16 *v5; // rax
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  int MergeRedirectPath; // eax
  int v9; // r14d
  int v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v19; // [rsp+20h] [rbp-40h]
  int v20; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v21; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h]

  v23 = 0;
  v24 = 0;
  v20 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &qword_14004E980;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", a3, v5);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v22 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v21 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_47;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v21, &v20, (a3 & 0x20) == 0, a1);
    v9 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v10 = v9;
    }
    else if ( v21 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v20 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v20 )
      {
        FileNamePart = AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v12 = AslFileMappingCreate(v7, v21, 0);
      v10 = v12;
      if ( v12 < 0 )
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2558,
          "Failed to create file mapping for redirected SDB file [%x]",
          v12);
    }
    else
    {
      v10 = -1073741772;
    }
    if ( v21 )
      AslFree(NtCurrentPeb()->ProcessHeap, v21);
    if ( v10 < 0 || !*v7 )
    {
LABEL_47:
      v13 = AslFileMappingCreate(v7, a1, 0);
      if ( v13 < 0 )
      {
        v14 = "Failed to create file mapping [%x]";
        v15 = 2580;
LABEL_25:
        LODWORD(v19) = v13;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v15, v14, v19);
        goto LABEL_42;
      }
    }
    v16 = *(_QWORD *)(*v7 + 24LL);
    if ( (unsigned __int64)(v16 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
      goto LABEL_42;
    }
    v13 = AslFileMappingEnsureMappedAsEx();
    if ( v13 < 0 )
    {
      v14 = "Failed to map SDB [%x]";
      v15 = 2595;
      goto LABEL_25;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v16;
    v7[1] = AslFileMappingGetViewBase(*v7);
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v23, 12) )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
      goto LABEL_42;
    }
    v13 = v24;
    if ( v24 != 1717724275 )
    {
      if ( v24 == 1717724282 )
      {
        if ( (unsigned int)SdbpOpenCompressedDatabase(&v22, v17, a3) )
          return v22;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2627, "SdbpOpenCompressedDatabase failed to open compressed database.");
        v7 = v22;
LABEL_42:
        if ( v7 )
        {
          AslFileMappingDelete((_QWORD *)*v7);
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        }
        return 0;
      }
      if ( (a3 & 2) == 0 )
      {
        v14 = "Magic does not match a valid value: 0x%lx";
        v15 = 2621;
        goto LABEL_25;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v23, a3) )
      return v7;
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x140037870  mov     r11, rsp
0x140037873  mov     [r11+10h], rbx
0x140037877  mov     [r11+20h], rsi
0x14003787b  push    rbp
0x14003787c  push    rdi
0x14003787d  push    r12
0x14003787f  push    r13
0x140037881  push    r14
0x140037883  mov     rbp, rsp
0x140037886  sub     rsp, 60h
0x14003788a  mov     rax, cs:__security_cookie
0x140037891  xor     rax, rsp
0x140037894  mov     [rbp+var_8], rax
0x140037898  xor     eax, eax
0x14003789a  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x1400378a1  mov     r13, rcx
0x1400378a4  mov     [rbp+var_18], rax
0x1400378a8  mov     [rbp+var_10], eax
0x1400378ab  lea     rcx, qword_14004E980
0x1400378b2  mov     [rbp+var_30], eax
0x1400378b5  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400378bc  mov     r12d, r8d
0x1400378bf  test    r13, r13
0x1400378c2  mov     rax, r13
0x1400378c5  cmovz   rax, rcx
0x1400378c9  mov     ecx, 3
0x1400378ce  mov     [r11-60h], rax
0x1400378d2  mov     [r11-68h], r8d
0x1400378d6  mov     r8d, 9C5h
0x1400378dc  call    AslLogCallPrintf
0x1400378e1  mov     rcx, gs:60h
0x1400378ea  mov     edi, 0A80h
0x1400378ef  mov     r8d, edi; Size
0x1400378f2  mov     edx, 8; Flags
0x1400378f7  mov     rcx, [rcx+30h]; HeapHandle
0x1400378fb  call    cs:__imp_RtlAllocateHeap
0x140037901  mov     [rbp+var_20], rax
0x140037905  mov     rbx, rax
0x140037908  test    rax, rax
0x14003790b  jnz     short loc_14003792E
0x14003790d  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x140037914  mov     r8d, 9CDh
0x14003791a  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140037921  lea     ecx, [rax+1]
0x140037924  call    AslLogCallPrintf
0x140037929  jmp     loc_140037BB6
0x14003792e  mov     r8, rdi; Size
0x140037931  xor     edx, edx; Val
0x140037933  mov     rcx, rbx; void *
0x140037936  call    memset_0
0x14003793b  mov     [rbp+var_28], 0
0x140037943  mov     edi, 1
0x140037948  test    r12b, 10h
0x14003794c  jnz     loc_140037A56
0x140037952  lea     r8d, [rdi-1]
0x140037956  mov     esi, r12d
0x140037959  and     esi, 20h
0x14003795c  lea     rdx, [rbp+var_30]
0x140037960  mov     r9, r13
0x140037963  lea     rcx, [rbp+var_28]
0x140037967  setz    r8b
0x14003796b  call    SdbGetMergeRedirectPath
0x140037970  mov     r14d, eax
0x140037973  test    eax, eax
0x140037975  js      loc_1400379FF
0x14003797b  cmp     [rbp+var_28], 0
0x140037980  jnz     short loc_14003798C
0x140037982  mov     esi, 0C0000034h
0x140037987  jmp     loc_140037A2F
0x14003798c  test    esi, esi
0x14003798e  jnz     short loc_1400379BF
0x140037990  cmp     [rbp+var_30], esi
0x140037993  jz      short loc_1400379C9
0x140037995  mov     rcx, r13
0x140037998  call    AslPathGetFileNamePart
0x14003799d  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x1400379a4  mov     [rsp+60h+var_40], rax
0x1400379a9  mov     r8d, 9EBh
0x1400379af  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400379b6  mov     ecx, edi
0x1400379b8  call    AslLogCallPrintf
0x1400379bd  jmp     short loc_1400379C9
0x1400379bf  cmp     [rbp+var_30], 0
0x1400379c3  jnz     short loc_1400379C9
0x1400379c5  or      dword ptr [rbx+18h], 20h
0x1400379c9  mov     rdx, [rbp+var_28]
0x1400379cd  xor     r8d, r8d
0x1400379d0  mov     rcx, rbx
0x1400379d3  call    AslFileMappingCreate
0x1400379d8  mov     esi, eax
0x1400379da  test    eax, eax
0x1400379dc  jns     short loc_140037A2F
0x1400379de  lea     r9, aFailedToCreate_3; "Failed to create file mapping for redir"...
0x1400379e5  mov     dword ptr [rsp+60h+var_40], eax
0x1400379e9  mov     r8d, 9FEh
0x1400379ef  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400379f6  mov     ecx, edi
0x1400379f8  call    AslLogCallPrintf
0x1400379fd  jmp     short loc_140037A2F
0x1400379ff  mov     esi, 0C0000034h
0x140037a04  cmp     r14d, esi
0x140037a07  jz      short loc_140037A2C
0x140037a09  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x140037a10  mov     dword ptr [rsp+60h+var_40], r14d
0x140037a15  mov     r8d, 9DFh
0x140037a1b  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140037a22  mov     ecx, 3
0x140037a27  call    AslLogCallPrintf
0x140037a2c  mov     esi, r14d
0x140037a2f  cmp     [rbp+var_28], 0
0x140037a34  jz      short loc_140037A4C
0x140037a36  mov     rcx, gs:60h
0x140037a3f  mov     rdx, [rbp+var_28]
0x140037a43  mov     rcx, [rcx+30h]
0x140037a47  call    AslFree
0x140037a4c  test    esi, esi
0x140037a4e  js      short loc_140037A56
0x140037a50  cmp     qword ptr [rbx], 0
0x140037a54  jnz     short loc_140037A8C
0x140037a56  xor     r8d, r8d
0x140037a59  mov     rdx, r13
0x140037a5c  mov     rcx, rbx
0x140037a5f  call    AslFileMappingCreate
0x140037a64  test    eax, eax
0x140037a66  jns     short loc_140037A8C
0x140037a68  lea     r9, aFailedToCreate_1; "Failed to create file mapping [%x]"
0x140037a6f  mov     r8d, 0A14h
0x140037a75  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140037a7c  mov     dword ptr [rsp+60h+var_40], eax
0x140037a80  mov     ecx, edi
0x140037a82  call    AslLogCallPrintf
0x140037a87  jmp     loc_140037B94
0x140037a8c  mov     rcx, [rbx]
0x140037a8f  mov     rsi, [rcx+18h]
0x140037a93  lea     rax, [rsi-2Ah]
0x140037a97  cmp     rax, 0FFFFFD5h
0x140037a9d  ja      loc_140037B79
0x140037aa3  call    AslFileMappingEnsureMappedAsEx
0x140037aa8  test    eax, eax
0x140037aaa  jns     short loc_140037ABB
0x140037aac  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x140037ab3  mov     r8d, 0A23h
0x140037ab9  jmp     short loc_140037A75
0x140037abb  mov     dword ptr [rbx+10h], 0
0x140037ac2  mov     [rbx+14h], esi
0x140037ac5  mov     rcx, [rbx]
0x140037ac8  call    AslFileMappingGetViewBase
0x140037acd  mov     r9d, 0Ch
0x140037ad3  mov     [rbx+8], rax
0x140037ad7  lea     r8, [rbp+var_18]
0x140037adb  xor     edx, edx
0x140037add  mov     rcx, rbx
0x140037ae0  call    SdbpReadMappedData
0x140037ae5  test    eax, eax
0x140037ae7  jnz     short loc_140037AFB
0x140037ae9  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x140037af0  mov     r8d, 0A30h
0x140037af6  jmp     loc_140037B86
0x140037afb  mov     eax, [rbp+var_10]
0x140037afe  mov     ecx, 6662647Ah
0x140037b03  cmp     eax, 66626473h
0x140037b08  jz      short loc_140037B26
0x140037b0a  cmp     eax, ecx
0x140037b0c  jz      short loc_140037B2A
0x140037b0e  test    r12b, 2
0x140037b12  jnz     short loc_140037B26
0x140037b14  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x140037b1b  mov     r8d, 0A3Dh
0x140037b21  jmp     loc_140037A75
0x140037b26  cmp     eax, ecx
0x140037b28  jnz     short loc_140037B61
0x140037b2a  mov     r8d, r12d
0x140037b2d  lea     rcx, [rbp+var_20]
0x140037b31  call    SdbpOpenCompressedDatabase
0x140037b36  test    eax, eax
0x140037b38  jnz     short loc_140037B5B
0x140037b3a  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x140037b41  mov     r8d, 0A43h
0x140037b47  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140037b4e  mov     ecx, edi
0x140037b50  call    AslLogCallPrintf
0x140037b55  mov     rbx, [rbp+var_20]
0x140037b59  jmp     short loc_140037B94
0x140037b5b  mov     rbx, [rbp+var_20]
0x140037b5f  jmp     short loc_140037B74
0x140037b61  mov     r8d, r12d
0x140037b64  lea     rdx, [rbp+var_18]
0x140037b68  mov     rcx, rbx
0x140037b6b  call    SdbpValidateAndApplyCompatFlags
0x140037b70  test    eax, eax
0x140037b72  jz      short loc_140037B94
0x140037b74  mov     rax, rbx
0x140037b77  jmp     short loc_140037BB8
0x140037b79  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x140037b80  mov     r8d, 0A1Dh
0x140037b86  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140037b8d  mov     ecx, edi
0x140037b8f  call    AslLogCallPrintf
0x140037b94  test    rbx, rbx
0x140037b97  jz      short loc_140037BB6
0x140037b99  mov     rcx, [rbx]
0x140037b9c  call    AslFileMappingDelete
0x140037ba1  mov     rcx, gs:60h
0x140037baa  mov     rdx, rbx
0x140037bad  mov     rcx, [rcx+30h]
0x140037bb1  call    AslFree
0x140037bb6  xor     eax, eax
0x140037bb8  mov     rcx, [rbp+var_8]
0x140037bbc  xor     rcx, rsp; StackCookie
0x140037bbf  call    __security_check_cookie
0x140037bc4  lea     r11, [rsp+60h+var_s0]
0x140037bc9  mov     rbx, [r11+38h]
0x140037bcd  mov     rsi, [r11+48h]
0x140037bd1  mov     rsp, r11
0x140037bd4  pop     r14
0x140037bd6  pop     r13
0x140037bd8  pop     r12
0x140037bda  pop     rdi
0x140037bdb  pop     rbp
0x140037bdc  retn
```
