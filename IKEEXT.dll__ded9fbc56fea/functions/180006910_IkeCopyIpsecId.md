# IkeCopyIpsecId

- ea: `0x180006910`
- end: `0x180006c47`
- name: `IkeCopyIpsecId`
- size: `823`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a2e0`
- `0x180044750`
- `0x18004b228`
- `0x18006c560`
- `0x18007b6c4`
- `0x1800d3658`
- `0x1800e1028`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180006910`
- `0x180008388`
- `0x180010db0`
- `0x180012230`
- `0x180012430`
- `0x180016534`
- `0x180016b20`
- `0x18004882c`
- `0x18004ce90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ad4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006b60`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006c03`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006b60`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006c03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a8d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800069ff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800069ff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006ac5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006ac5`

## string_xrefs

- `0x180006afa`: `IkeCopySid`
- `0x180006ae0`: `CopySid`
- `0x180006a62`: `IkeCopyIpsecId`
- `0x180006b86`: `WfpMidlObjectCopy`

## pseudocode

```c
__int64 __fastcall IkeCopyIpsecId(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbp
  _QWORD *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int i; // edx
  unsigned int j; // esi
  void *v12; // r15
  __int64 v13; // rax
  void *v14; // r13
  __int64 v15; // rcx
  SIZE_T LengthSid; // r12
  int v17; // eax
  __int64 v18; // rcx
  void *v19; // rbx
  __int64 v20; // rbp
  _QWORD *v22; // rax
  __int64 v23; // rcx
  DWORD LastError; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // [rsp+20h] [rbp-68h] BYREF
  unsigned int v30; // [rsp+28h] [rbp-60h] BYREF
  LPCVOID lpMem; // [rsp+30h] [rbp-58h] BYREF
  __int64 v32; // [rsp+38h] [rbp-50h]
  _QWORD *v33; // [rsp+40h] [rbp-48h]

  v33 = a2;
  v32 = a1;
  v2 = a1;
  lpMem = 0;
  v30 = 0;
  v29 = 0;
  v3 = 0;
  v4 = WfpMidlObjectEncode(&IPSEC_ID_MARSHAL_ALL_NODES_Encode, a1, &lpMem, &v30);
  v6 = lpMem;
  v7 = v4;
  if ( !v4 )
  {
    v8 = WfpMidlObjectDecode(&IPSEC_ID_MARSHAL_ALL_NODES_Decode, lpMem, v30, &v29);
    v3 = v29;
    v7 = v8;
  }
  v29 = v6;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v5);
  if ( IsEnabledDeviceUsageNoInline )
  {
    WfpMemFree25B(&v29);
  }
  else
  {
    if ( gWfpTrackHeapBytes && v6 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v6));
    HeapFree(gWfpHeap, 0, v6);
  }
  if ( !v7 )
  {
    for ( i = 0; i < *((_DWORD *)v3 + 4); *(_QWORD *)(v3[3] + 24 * v26 + 16) = 0 )
      v26 = i++;
    for ( j = 0; ; ++j )
    {
      if ( j >= *((_DWORD *)v3 + 4) )
      {
        *v33 = v3;
        return IkeReturnError(v7, "IkeCopyIpsecId");
      }
      v12 = 0;
      v13 = *(_QWORD *)(v2 + 24);
      lpMem = (LPCVOID)(24LL * j);
      v14 = *(void **)((char *)lpMem + v13 + 16);
      LengthSid = GetLengthSid(v14);
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        v17 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        v17 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v15);
      if ( v17 )
      {
        v29 = HeapAlloc(gWfpHeap, 8u, LengthSid);
        v19 = v29;
        if ( v29 )
        {
          v20 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v28 = WfpReportSysErrorAsNtStatus(v18, "HeapAlloc", 3221225495LL);
          v20 = v28;
          if ( v28 )
            WfpReportError(v28, "WfpMemAlloc25B");
        }
      }
      else
      {
        v22 = HeapAlloc(gWfpHeap, 8u, LengthSid);
        v29 = v22;
        v19 = v22;
        if ( v22 )
        {
          v20 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v22));
        }
        else
        {
          v27 = WfpReportSysErrorAsNtStatus(v23, "HeapAlloc", 3221225495LL);
          v20 = v27;
          if ( v27 )
            WfpReportError(v27, "WfpMemAlloc");
        }
      }
      if ( v20 )
        goto LABEL_28;
      if ( CopySid(LengthSid, v19, v14) )
      {
        v12 = v19;
        goto LABEL_26;
      }
      LastError = GetLastError();
      v20 = WfpReportSysErrorAsWinError(v25, "CopySid", LastError, 1);
      v12 = 0;
      if ( v20 )
LABEL_28:
        WfpMemFree(&v29);
LABEL_26:
      v7 = IkeReturnError(v20, "IkeCopySid");
      if ( v7 )
        goto LABEL_35;
      v2 = v32;
      *(_QWORD *)((char *)lpMem + v3[3] + 16) = v12;
    }
  }
  WfpReportError(v7, "WfpMidlObjectCopy");
LABEL_35:
  IkeFreeIpsecId(v3);
  return IkeReturnError(v7, "IkeCopyIpsecId");
}

```

## disassembly

```asm
0x180006910  push    rbx
0x180006912  push    rbp
0x180006913  push    rsi
0x180006914  push    rdi
0x180006915  push    r14
0x180006917  sub     rsp, 60h
0x18000691b  xor     r14d, r14d
0x18000691e  mov     [rsp+88h+var_48], rdx
0x180006923  mov     rdx, rcx
0x180006926  mov     [rsp+88h+var_50], rcx
0x18000692b  mov     rbp, rcx
0x18000692e  mov     [rsp+88h+lpMem], r14
0x180006933  lea     rcx, IPSEC_ID_MARSHAL_ALL_NODES_Encode
0x18000693a  mov     [rsp+88h+var_60], r14d
0x18000693f  lea     r9, [rsp+88h+var_60]
0x180006944  mov     [rsp+88h+var_68], r14
0x180006949  lea     r8, [rsp+88h+lpMem]
0x18000694e  mov     edi, r14d
0x180006951  call    WfpMidlObjectEncode
0x180006956  mov     rsi, [rsp+88h+lpMem]
0x18000695b  mov     rbx, rax
0x18000695e  test    rax, rax
0x180006961  jnz     short loc_180006984
0x180006963  mov     r8d, [rsp+88h+var_60]
0x180006968  lea     r9, [rsp+88h+var_68]
0x18000696d  mov     rdx, rsi
0x180006970  lea     rcx, IPSEC_ID_MARSHAL_ALL_NODES_Decode
0x180006977  call    WfpMidlObjectDecode
0x18000697c  mov     rdi, [rsp+88h+var_68]
0x180006981  mov     rbx, rax
0x180006984  mov     [rsp+88h+var_68], rsi
0x180006989  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000698f  test    al, 10h
0x180006991  jnz     loc_180006B3E
0x180006997  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000699c  test    eax, eax
0x18000699e  jz      loc_180006B46
0x1800069a4  lea     rcx, [rsp+88h+var_68]
0x1800069a9  call    WfpMemFree25B
0x1800069ae  mov     [rsp+88h+arg_10], r12
0x1800069b6  mov     [rsp+88h+var_30], r13
0x1800069bb  mov     [rsp+88h+var_38], r15
0x1800069c0  test    rbx, rbx
0x1800069c3  jnz     loc_180006B86
0x1800069c9  mov     edx, r14d
0x1800069cc  cmp     [rdi+10h], edx
0x1800069cf  ja      loc_180006BA2
0x1800069d5  mov     esi, r14d
0x1800069d8  cmp     esi, [rdi+10h]
0x1800069db  jnb     short loc_180006A5A
0x1800069dd  mov     eax, esi
0x1800069df  mov     r15, r14
0x1800069e2  lea     rcx, [rax+rax*2]
0x1800069e6  mov     rax, [rbp+18h]
0x1800069ea  lea     rcx, ds:0[rcx*8]
0x1800069f2  mov     [rsp+88h+lpMem], rcx
0x1800069f7  mov     r13, [rax+rcx+10h]
0x1800069fc  mov     rcx, r13; pSid
0x1800069ff  call    cs:__imp_GetLengthSid
0x180006a05  mov     r12d, eax
0x180006a08  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180006a0e  test    al, 10h
0x180006a10  jnz     loc_180006BBD
0x180006a16  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180006a1b  mov     rcx, cs:gWfpHeap; hHeap
0x180006a22  mov     r8, r12; dwBytes
0x180006a25  mov     edx, 8; dwFlags
0x180006a2a  test    eax, eax
0x180006a2c  jz      short loc_180006A8D
0x180006a2e  call    cs:__imp_HeapAlloc
0x180006a34  mov     [rsp+88h+var_68], rax
0x180006a39  mov     rbx, rax
0x180006a3c  test    rax, rax
0x180006a3f  jz      loc_180006C15
0x180006a45  cmp     cs:gWfpTrackHeapAllocs, 0
0x180006a4c  mov     rbp, r14
0x180006a4f  jz      short loc_180006AB4
0x180006a51  lock inc cs:gWfpNumHeapAllocs
0x180006a58  jmp     short loc_180006AB4
0x180006a5a  mov     rax, [rsp+88h+var_48]
0x180006a5f  mov     [rax], rdi
0x180006a62  lea     rdx, aIkecopyipsecid; "IkeCopyIpsecId"
0x180006a69  mov     rcx, rbx
0x180006a6c  mov     r15, [rsp+88h+var_38]
0x180006a71  mov     r13, [rsp+88h+var_30]
0x180006a76  mov     r12, [rsp+88h+arg_10]
0x180006a7e  add     rsp, 60h
0x180006a82  pop     r14
0x180006a84  pop     rdi
0x180006a85  pop     rsi
0x180006a86  pop     rbp
0x180006a87  pop     rbx
0x180006a88  jmp     IkeReturnError
0x180006a8d  call    cs:__imp_HeapAlloc
0x180006a93  mov     [rsp+88h+var_68], rax
0x180006a98  mov     rbx, rax
0x180006a9b  test    rax, rax
0x180006a9e  jz      loc_180006BC5
0x180006aa4  cmp     cs:gWfpTrackHeapBytes, 0
0x180006aab  mov     rbp, r14
0x180006aae  jnz     loc_180006BF7
0x180006ab4  mov     r14, rbx
0x180006ab7  test    rbp, rbp
0x180006aba  jnz     short loc_180006B32
0x180006abc  mov     r8, r13; pSourceSid
0x180006abf  mov     rdx, rbx; pDestinationSid
0x180006ac2  mov     ecx, r12d; nDestinationSidLength
0x180006ac5  call    cs:__imp_CopySid
0x180006acb  test    eax, eax
0x180006acd  jz      short loc_180006AD4
0x180006acf  mov     r15, rbx
0x180006ad2  jmp     short loc_180006AFA
0x180006ad4  call    cs:__imp_GetLastError
0x180006ada  mov     r9d, 1
0x180006ae0  lea     rdx, aCopysid; "CopySid"
0x180006ae7  mov     r8d, eax
0x180006aea  call    WfpReportSysErrorAsWinError
0x180006aef  mov     rbp, rax
0x180006af2  xor     r15d, r15d
0x180006af5  test    rax, rax
0x180006af8  jnz     short loc_180006B32
0x180006afa  lea     rdx, aIkecopysid; "IkeCopySid"
0x180006b01  mov     rcx, rbp
0x180006b04  call    IkeReturnError
0x180006b09  mov     rbx, rax
0x180006b0c  test    rax, rax
0x180006b0f  jnz     loc_180006B95
0x180006b15  mov     rax, [rdi+18h]
0x180006b19  inc     esi
0x180006b1b  mov     rcx, [rsp+88h+lpMem]
0x180006b20  xor     r14d, r14d
0x180006b23  mov     rbp, [rsp+88h+var_50]
0x180006b28  mov     [rax+rcx+10h], r15
0x180006b2d  jmp     loc_1800069D8
0x180006b32  lea     rcx, [rsp+88h+var_68]
0x180006b37  call    WfpMemFree
0x180006b3c  jmp     short loc_180006AFA
0x180006b3e  and     eax, 1
0x180006b41  jmp     loc_18000699C
0x180006b46  cmp     cs:gWfpTrackHeapBytes, r14d
0x180006b4d  jz      short loc_180006B6F
0x180006b4f  test    rsi, rsi
0x180006b52  jz      short loc_180006B6F
0x180006b54  mov     rcx, cs:gWfpHeap; hHeap
0x180006b5b  mov     r8, rsi; lpMem
0x180006b5e  xor     edx, edx; dwFlags
0x180006b60  call    cs:__imp_HeapSize
0x180006b66  neg     eax
0x180006b68  lock add cs:gWfpHeapBytesAllocated, eax
0x180006b6f  mov     rcx, cs:gWfpHeap; hHeap
0x180006b76  mov     r8, rsi; lpMem
0x180006b79  xor     edx, edx; dwFlags
0x180006b7b  call    cs:__imp_HeapFree
0x180006b81  jmp     loc_1800069AE
0x180006b86  lea     rdx, aWfpmidlobjectc; "WfpMidlObjectCopy"
0x180006b8d  mov     rcx, rbx
0x180006b90  call    WfpReportError
0x180006b95  mov     rcx, rdi; lpMem
0x180006b98  call    IkeFreeIpsecId
0x180006b9d  jmp     loc_180006A62
0x180006ba2  mov     eax, edx
0x180006ba4  inc     edx
0x180006ba6  lea     rcx, [rax+rax*2]
0x180006baa  mov     rax, [rdi+18h]
0x180006bae  mov     [rax+rcx*8+10h], r14
0x180006bb3  cmp     edx, [rdi+10h]
0x180006bb6  jb      short loc_180006BA2
0x180006bb8  jmp     loc_1800069D5
0x180006bbd  and     eax, 1
0x180006bc0  jmp     loc_180006A1B
0x180006bc5  mov     r8d, 0C0000017h
0x180006bcb  lea     rdx, aHeapalloc; "HeapAlloc"
0x180006bd2  call    WfpReportSysErrorAsNtStatus
0x180006bd7  mov     rbp, rax
0x180006bda  test    rax, rax
0x180006bdd  jz      loc_180006AB4
0x180006be3  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180006bea  mov     rcx, rax
0x180006bed  call    WfpReportError
0x180006bf2  jmp     loc_180006AB4
0x180006bf7  mov     rcx, cs:gWfpHeap; hHeap
0x180006bfe  mov     r8, rbx; lpMem
0x180006c01  xor     edx, edx; dwFlags
0x180006c03  call    cs:__imp_HeapSize
0x180006c09  lock add cs:gWfpHeapBytesAllocated, eax
0x180006c10  jmp     loc_180006AB4
0x180006c15  mov     r8d, 0C0000017h
0x180006c1b  lea     rdx, aHeapalloc; "HeapAlloc"
0x180006c22  call    WfpReportSysErrorAsNtStatus
0x180006c27  mov     rbp, rax
0x180006c2a  test    rax, rax
0x180006c2d  jz      loc_180006AB4
0x180006c33  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180006c3a  mov     rcx, rax
0x180006c3d  call    WfpReportError
0x180006c42  jmp     loc_180006AB4
```
