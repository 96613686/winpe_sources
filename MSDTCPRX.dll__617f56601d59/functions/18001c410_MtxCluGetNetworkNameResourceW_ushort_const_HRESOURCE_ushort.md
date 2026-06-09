# MtxCluGetNetworkNameResourceW(ushort const *,_HRESOURCE * *,ushort * *)

- ea: `0x18001c410`
- end: `0x18001c7ae`
- name: `?MtxCluGetNetworkNameResourceW@@YAJPEBGPEAPEAU_HRESOURCE@@PEAPEAG@Z`
- size: `926`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _HRESOURCE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800724e4`

## callees

- `0x180003cf0`
- `0x180006324`
- `0x180006764`
- `0x18000d5f4`
- `0x18001156c`
- `0x18001c410`
- `0x18007198c`
- `0x180071a34`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c66b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5fb`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001c662`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001c662`
- `CLUSAPI!GetClusterResourceState` at `0x18001c5ec`
- `CLUSAPI!GetClusterResourceState` at `0x18001c5ec`
- `CLUSAPI!CloseClusterResource` at `0x18001c74c`
- `CLUSAPI!CloseClusterResource` at `0x18001c74c`

## string_xrefs

- `0x18001c49a`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001c46a`: `MtxCluGetNetworkNameResourceW (com\complus\dtc\shared\util\clusterutilbasic.cpp@478): MtxCluGetNetworkNameResourceW, pwszResourceName != NULL`
- `0x18001c47c`: `MtxCluGetNetworkNameResourceW (com\complus\dtc\shared\util\clusterutilbasic.cpp@479): MtxCluGetNetworkNameResourceW, phResource != NULL`

## pseudocode

```c
__int64 __fastcall MtxCluGetNetworkNameResourceW(WCHAR *a1, struct _HRESOURCE **a2, unsigned __int16 **a3)
{
  struct _HCLUSTER *LocalClusterHandle; // rbx
  signed int LastError; // eax
  signed int NetworkNameResource; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  signed int v11; // eax
  struct _HRESOURCE *v12; // r8
  int StringW; // eax
  void *v14; // rsi
  LPDWORD lpcchGroupName; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  WCHAR *p_szNodeName; // [rsp+38h] [rbp-C8h]
  DWORD cchNodeName; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szNodeName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[526]; // [rsp+52h] [rbp-AEh] BYREF

  szNodeName = 0;
  memset_0(v23, 0, 0x200u);
  cchNodeName = 257;
  if ( !a1 )
    DtcInternalErrorW(
      L"MtxCluGetNetworkNameResourceW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@478): MtxCluGetNetworkNameRes"
       "ourceW, pwszResourceName != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluGetNetworkNameResourceW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@479): MtxCluGetNetworkNameRes"
       "ourceW, phResource != NULL");
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    481,
    L"MtxCluGetNetworkNameResourceW",
    0,
    L"In");
  *a2 = 0;
  LocalClusterHandle = GetLocalClusterHandle();
  if ( !LocalClusterHandle )
  {
    LastError = GetLastError();
    NetworkNameResource = LastError;
    if ( LastError > 0 )
      NetworkNameResource = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v17) = NetworkNameResource;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      490,
      L"MtxCluGetNetworkNameResourceW",
      v17,
      L"GetLocalClusterHandle failed");
    goto LABEL_21;
  }
  TraceStringInline(
    7,
    4,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    494,
    L"MtxCluGetNetworkNameResourceW",
    0,
    L"Provided Resource Name: %s",
    a1);
  NetworkNameResource = GetNetworkNameResource(LocalClusterHandle, a1, a2);
  if ( NetworkNameResource >= 0 )
  {
    if ( !a3 )
      goto LABEL_28;
    *a3 = 0;
    if ( *a2 )
    {
      if ( GetClusterResourceState(*a2, &szNodeName, &cchNodeName, 0, 0) == ClusterResourceStateUnknown )
      {
        v11 = GetLastError();
        NetworkNameResource = v11;
        if ( v11 > 0 )
          NetworkNameResource = (unsigned __int16)v11 | 0x80070000;
        v12 = *a2;
        LODWORD(lpcchGroupName) = cchNodeName;
        pv = 0;
        StringW = MakeStringW(
                    (unsigned __int16 **)&pv,
                    L"hResource: %x lpszNodeName: %s lpcchNodeName: %d",
                    v12,
                    &szNodeName,
                    lpcchGroupName);
        v14 = pv;
        if ( StringW >= 0 )
          TraceFileW(
            NetworkNameResource,
            (unsigned __int16 *)pv,
            L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
            0x21Cu);
        FailedClusterAPIToEventLog(L"GetClusterResourceState", (unsigned int)NetworkNameResource, v14);
        CoTaskMemFree(v14);
        LODWORD(v18) = NetworkNameResource;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          546,
          L"MtxCluGetNetworkNameResourceW",
          v18,
          L"GetClusterResourceState failed for %s",
          a1);
LABEL_21:
        if ( NetworkNameResource >= 0 )
          goto LABEL_28;
        goto LABEL_26;
      }
      NetworkNameResource = DuplicateString(&szNodeName, a3);
      if ( NetworkNameResource >= 0 )
        goto LABEL_28;
      v10 = 553;
      p_szNodeName = &szNodeName;
      v9 = L"DuplicateString failed for physical name %s";
    }
    else
    {
      NetworkNameResource = DuplicateString(a1, a3);
      if ( NetworkNameResource >= 0 )
        goto LABEL_28;
      p_szNodeName = a1;
      v9 = L"DuplicateString failed for %s";
      v10 = 516;
    }
  }
  else
  {
    p_szNodeName = a1;
    v9 = L"GetNetworkNameResource failed for %s";
    v10 = 500;
  }
  LODWORD(v18) = NetworkNameResource;
  TraceStringInline(
    7,
    1,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    v10,
    L"MtxCluGetNetworkNameResourceW",
    v18,
    v9,
    p_szNodeName);
LABEL_26:
  if ( *a2 )
  {
    TraceStringInline(
      7,
      240,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      563,
      L"MtxCluGetNetworkNameResourceW",
      0,
      L"Closing resource (error case) = 0x%x",
      *a2);
    CloseClusterResource(*a2);
    *a2 = 0;
  }
LABEL_28:
  LODWORD(v18) = NetworkNameResource;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    571,
    L"MtxCluGetNetworkNameResourceW",
    v18,
    L"Out");
  return (unsigned int)NetworkNameResource;
}

```

## disassembly

```asm
0x18001c410  push    rbp
0x18001c412  push    rbx
0x18001c413  push    rsi
0x18001c414  push    rdi
0x18001c415  push    r12
0x18001c417  push    r13
0x18001c419  push    r14
0x18001c41b  lea     rbp, [rsp-170h]
0x18001c423  sub     rsp, 270h
0x18001c42a  mov     rax, cs:__security_cookie
0x18001c431  xor     rax, rsp
0x18001c434  mov     [rbp+1A0h+var_40], rax
0x18001c43b  mov     rsi, r8
0x18001c43e  mov     rdi, rdx
0x18001c441  mov     r14, rcx
0x18001c444  xor     eax, eax
0x18001c446  xor     edx, edx; Val
0x18001c448  mov     [rsp+2A0h+szNodeName], ax
0x18001c44d  mov     r8d, 200h; Size
0x18001c453  lea     rcx, [rsp+2A0h+var_24E]; void *
0x18001c458  call    memset_0
0x18001c45d  mov     [rsp+2A0h+cchNodeName], 101h
0x18001c465  test    r14, r14
0x18001c468  jnz     short loc_18001C477
0x18001c46a  lea     rcx, aMtxclugetnetwo; "MtxCluGetNetworkNameResourceW (com\\com"...
0x18001c471  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001c477  test    rdi, rdi
0x18001c47a  jnz     short loc_18001C489
0x18001c47c  lea     rcx, aMtxclugetnetwo_2; "MtxCluGetNetworkNameResourceW (com\\com"...
0x18001c483  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001c489  mov     edx, 6
0x18001c48e  lea     rax, aIn_0; "In"
0x18001c495  mov     [rsp+2A0h+var_270], rax
0x18001c49a  lea     r12, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001c4a1  lea     rax, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c4a8  mov     [rsp+2A0h+var_278], 0
0x18001c4b1  mov     r9d, 1E1h
0x18001c4b7  mov     [rsp+2A0h+lpcchGroupName], rax
0x18001c4bc  lea     r13d, [rdx+1]
0x18001c4c0  mov     r8, r12
0x18001c4c3  mov     ecx, r13d
0x18001c4c6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c4cb  mov     qword ptr [rdi], 0
0x18001c4d2  call    ?GetLocalClusterHandle@@YAPEAU_HCLUSTER@@XZ; GetLocalClusterHandle(void)
0x18001c4d7  mov     rbx, rax
0x18001c4da  test    rax, rax
0x18001c4dd  jnz     short loc_18001C52B
0x18001c4df  call    cs:__imp_GetLastError
0x18001c4e5  mov     ebx, eax
0x18001c4e7  test    eax, eax
0x18001c4e9  jle     short loc_18001C4F4
0x18001c4eb  movzx   ebx, ax
0x18001c4ee  or      ebx, 80070000h
0x18001c4f4  lea     rax, aGetlocalcluste; "GetLocalClusterHandle failed"
0x18001c4fb  mov     r9d, 1EAh
0x18001c501  mov     [rsp+2A0h+var_270], rax
0x18001c506  mov     r8, r12
0x18001c509  lea     rax, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c510  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18001c514  mov     edx, 1
0x18001c519  mov     [rsp+2A0h+lpcchGroupName], rax
0x18001c51e  mov     ecx, r13d
0x18001c521  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c526  jmp     loc_18001C6A8
0x18001c52b  mov     [rsp+2A0h+var_268], r14
0x18001c530  lea     rax, aProvidedResour; "Provided Resource Name: %s"
0x18001c537  mov     [rsp+2A0h+var_270], rax
0x18001c53c  mov     r9d, 1EEh
0x18001c542  lea     rax, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c549  mov     [rsp+2A0h+var_278], 0
0x18001c552  mov     r8, r12
0x18001c555  mov     [rsp+2A0h+lpcchGroupName], rax
0x18001c55a  mov     edx, 4
0x18001c55f  mov     ecx, r13d
0x18001c562  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c567  mov     r8, rdi; struct _HRESOURCE **
0x18001c56a  mov     rdx, r14; lpString2
0x18001c56d  mov     rcx, rbx; hCluster
0x18001c570  call    ?GetNetworkNameResource@@YAJPEAU_HCLUSTER@@PEBGPEAPEAU_HRESOURCE@@@Z; GetNetworkNameResource(_HCLUSTER *,ushort const *,_HRESOURCE * *)
0x18001c575  mov     ebx, eax
0x18001c577  test    eax, eax
0x18001c579  jns     short loc_18001C592
0x18001c57b  mov     [rsp+2A0h+var_268], r14
0x18001c580  lea     rax, aGetnetworkname_1; "GetNetworkNameResource failed for %s"
0x18001c587  mov     r9d, 1F4h
0x18001c58d  jmp     loc_18001C6E7
0x18001c592  test    rsi, rsi
0x18001c595  jz      loc_18001C759
0x18001c59b  mov     qword ptr [rsi], 0
0x18001c5a2  mov     rcx, [rdi]; hResource
0x18001c5a5  test    rcx, rcx
0x18001c5a8  jnz     short loc_18001C5D6
0x18001c5aa  mov     rdx, rsi; unsigned __int16 **
0x18001c5ad  mov     rcx, r14; unsigned __int16 *
0x18001c5b0  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18001c5b5  mov     ebx, eax
0x18001c5b7  test    eax, eax
0x18001c5b9  jns     loc_18001C759
0x18001c5bf  mov     [rsp+2A0h+var_268], r14
0x18001c5c4  lea     rax, aDuplicatestrin_7; "DuplicateString failed for %s"
0x18001c5cb  mov     r9d, 204h
0x18001c5d1  jmp     loc_18001C6E7
0x18001c5d6  xor     r9d, r9d; lpszGroupName
0x18001c5d9  mov     [rsp+2A0h+lpcchGroupName], 0; lpcchGroupName
0x18001c5e2  lea     r8, [rsp+2A0h+cchNodeName]; lpcchNodeName
0x18001c5e7  lea     rdx, [rsp+2A0h+szNodeName]; lpszNodeName
0x18001c5ec  call    cs:__imp_GetClusterResourceState
0x18001c5f2  cmp     eax, 0FFFFFFFFh
0x18001c5f5  jnz     loc_18001C6B9
0x18001c5fb  call    cs:__imp_GetLastError
0x18001c601  mov     ebx, eax
0x18001c603  test    eax, eax
0x18001c605  jle     short loc_18001C610
0x18001c607  movzx   ebx, ax
0x18001c60a  or      ebx, 80070000h
0x18001c610  mov     eax, [rsp+2A0h+cchNodeName]
0x18001c614  lea     r9, [rsp+2A0h+szNodeName]
0x18001c619  mov     r8, [rdi]
0x18001c61c  lea     rdx, aHresourceXLpsz; "hResource: %x lpszNodeName: %s lpcchNod"...
0x18001c623  lea     rcx, [rsp+2A0h+pv]; unsigned __int16 **
0x18001c628  mov     dword ptr [rsp+2A0h+lpcchGroupName], eax
0x18001c62c  mov     [rsp+2A0h+pv], 0
0x18001c635  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001c63a  mov     rsi, [rsp+2A0h+pv]
0x18001c63f  test    eax, eax
0x18001c641  js      short loc_18001C656
0x18001c643  mov     r9d, 21Ch; unsigned int
0x18001c649  mov     r8, r12; unsigned __int16 *
0x18001c64c  mov     rdx, rsi; unsigned __int16 *
0x18001c64f  mov     ecx, ebx; int
0x18001c651  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001c656  mov     r8, rsi
0x18001c659  lea     rcx, aGetclusterreso_0; "GetClusterResourceState"
0x18001c660  mov     edx, ebx
0x18001c662  call    cs:__imp_FailedClusterAPIToEventLog
0x18001c668  mov     rcx, rsi; pv
0x18001c66b  call    cs:__imp_CoTaskMemFree
0x18001c671  mov     [rsp+2A0h+var_268], r14
0x18001c676  lea     rax, aGetclusterreso; "GetClusterResourceState failed for %s"
0x18001c67d  mov     [rsp+2A0h+var_270], rax
0x18001c682  mov     r9d, 222h
0x18001c688  lea     rax, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c68f  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18001c693  mov     r8, r12
0x18001c696  mov     [rsp+2A0h+lpcchGroupName], rax
0x18001c69b  mov     edx, 1
0x18001c6a0  mov     ecx, r13d
0x18001c6a3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c6a8  test    ebx, ebx
0x18001c6aa  jns     loc_18001C759
0x18001c6b0  lea     rsi, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c6b7  jmp     short loc_18001C70C
0x18001c6b9  mov     rdx, rsi; unsigned __int16 **
0x18001c6bc  lea     rcx, [rsp+2A0h+szNodeName]; unsigned __int16 *
0x18001c6c1  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18001c6c6  mov     ebx, eax
0x18001c6c8  test    eax, eax
0x18001c6ca  jns     loc_18001C759
0x18001c6d0  lea     rax, [rsp+2A0h+szNodeName]
0x18001c6d5  mov     r9d, 229h
0x18001c6db  mov     [rsp+2A0h+var_268], rax
0x18001c6e0  lea     rax, aDuplicatestrin_1; "DuplicateString failed for physical nam"...
0x18001c6e7  mov     [rsp+2A0h+var_270], rax
0x18001c6ec  lea     rsi, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c6f3  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18001c6f7  mov     r8, r12
0x18001c6fa  mov     edx, 1
0x18001c6ff  mov     [rsp+2A0h+lpcchGroupName], rsi
0x18001c704  mov     ecx, r13d
0x18001c707  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c70c  mov     rax, [rdi]
0x18001c70f  test    rax, rax
0x18001c712  jz      short loc_18001C759
0x18001c714  mov     [rsp+2A0h+var_268], rax
0x18001c719  mov     r9d, 233h
0x18001c71f  lea     rax, aClosingResourc; "Closing resource (error case) = 0x%x"
0x18001c726  mov     r8, r12
0x18001c729  mov     [rsp+2A0h+var_270], rax
0x18001c72e  mov     edx, 0F0h
0x18001c733  mov     [rsp+2A0h+var_278], 0
0x18001c73c  mov     ecx, r13d
0x18001c73f  mov     [rsp+2A0h+lpcchGroupName], rsi
0x18001c744  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c749  mov     rcx, [rdi]; hResource
0x18001c74c  call    cs:__imp_CloseClusterResource
0x18001c752  mov     qword ptr [rdi], 0
0x18001c759  lea     rax, aOut; "Out"
0x18001c760  mov     r9d, 23Bh
0x18001c766  mov     [rsp+2A0h+var_270], rax
0x18001c76b  mov     r8, r12
0x18001c76e  lea     rax, aMtxclugetnetwo_0; "MtxCluGetNetworkNameResourceW"
0x18001c775  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18001c779  mov     edx, 6
0x18001c77e  mov     [rsp+2A0h+lpcchGroupName], rax
0x18001c783  mov     ecx, r13d
0x18001c786  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c78b  mov     eax, ebx
0x18001c78d  mov     rcx, [rbp+1A0h+var_40]
0x18001c794  xor     rcx, rsp; StackCookie
0x18001c797  call    __security_check_cookie
0x18001c79c  add     rsp, 270h
0x18001c7a3  pop     r14
0x18001c7a5  pop     r13
0x18001c7a7  pop     r12
0x18001c7a9  pop     rdi
0x18001c7aa  pop     rsi
0x18001c7ab  pop     rbx
0x18001c7ac  pop     rbp
0x18001c7ad  retn
```
