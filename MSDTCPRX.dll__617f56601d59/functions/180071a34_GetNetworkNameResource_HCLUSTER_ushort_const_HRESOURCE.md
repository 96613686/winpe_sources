# GetNetworkNameResource(_HCLUSTER *,ushort const *,_HRESOURCE * *)

- ea: `0x180071a34`
- end: `0x180071fc2`
- name: `?GetNetworkNameResource@@YAJPEAU_HCLUSTER@@PEBGPEAPEAU_HRESOURCE@@@Z`
- size: `1422`
- prototype: `__int64 __fastcall(HCLUSTER hCluster, PCNZWCH lpString2, struct _HRESOURCE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c410`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x18000d5f4`
- `0x18001156c`
- `0x18001a9b8`
- `0x180071a34`
- `0x18007975c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f7a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071d74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071e15`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180071b95`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180071e74`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180071b95`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180071e74`
- `CLUSAPI!ClusterResourceTypeGetEnumCount` at `0x180071be2`
- `CLUSAPI!ClusterResourceTypeGetEnumCount` at `0x180071be2`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x180071b19`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x180071b19`
- `CLUSAPI!OpenClusterResourceEx` at `0x180071caa`
- `CLUSAPI!OpenClusterResourceEx` at `0x180071caa`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x180071f09`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x180071f09`
- `CLUSAPI!CloseClusterResource` at `0x180071c70`
- `CLUSAPI!CloseClusterResource` at `0x180071f56`
- `CLUSAPI!CloseClusterResource` at `0x180071c70`
- `CLUSAPI!CloseClusterResource` at `0x180071f56`

## string_xrefs

- `0x180071aa0`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071ada`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071b78`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071bc0`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071c3c`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071cc1`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071d0a`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071daa`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071e57`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071ea0`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071ed8`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071f29`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071f91`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180071a70`: `GetNetworkNameResource (com\complus\dtc\shared\util\clusterutilbasic.cpp@322): GetNetworkNameResource, pwszResourceName != NULL`
- `0x180071a82`: `GetNetworkNameResource (com\complus\dtc\shared\util\clusterutilbasic.cpp@323): GetNetworkNameResource, phResource != NULL`
- `0x180071b8c`: `ClusterResourceTypeOpenEnum`
- `0x180071ba9`: `ClusterResourceTypeOpenEnum failed`
- `0x180071e6b`: `OpenClusterResourceEx`
- `0x180071e83`: `OpenClusterResourceEx failed`
- `0x180071cc8`: `After OpenClusterResourceEx, hResource = 0x%x`

## pseudocode

```c
__int64 __fastcall GetNetworkNameResource(HCLUSTER hCluster, PCNZWCH lpString2, struct _HRESOURCE **a3)
{
  struct _HRESOURCE **v3; // r12
  WCHAR *v6; // rsi
  WCHAR *v7; // rdi
  struct _HRESOURCE *v8; // r14
  struct _HRESTYPEENUM *v9; // rax
  struct _HRESTYPEENUM *v10; // rbx
  signed int v11; // eax
  signed int ActualNameOfNetworkNameResource; // ebx
  int v13; // eax
  void *v14; // r15
  DWORD EnumCount; // eax
  DWORD v16; // r12d
  HRESOURCE v17; // rax
  signed int LastError; // eax
  int StringW; // eax
  void *v20; // r12
  PCNZWCH lpString2a; // [rsp+20h] [rbp-58h]
  int cchCount2[2]; // [rsp+28h] [rbp-50h]
  int cchCount2a[2]; // [rsp+28h] [rbp-50h]
  PCNZWCH lpString1; // [rsp+50h] [rbp-28h] BYREF
  LPCWSTR lpszResourceName; // [rsp+58h] [rbp-20h] BYREF
  HRESTYPEENUM hResTypeEnum; // [rsp+60h] [rbp-18h]
  DWORD dwType; // [rsp+C8h] [rbp+50h] BYREF
  struct _HRESOURCE **v30; // [rsp+D0h] [rbp+58h]
  LPVOID pv; // [rsp+D8h] [rbp+60h] BYREF

  v30 = a3;
  v3 = a3;
  lpszResourceName = 0;
  lpString1 = 0;
  dwType = 0;
  v6 = 0;
  v7 = 0;
  if ( !lpString2 )
    DtcInternalErrorW(
      L"GetNetworkNameResource (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@322): GetNetworkNameResource, pwszRe"
       "sourceName != NULL");
  if ( !a3 )
    DtcInternalErrorW(
      L"GetNetworkNameResource (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@323): GetNetworkNameResource, phResource != NULL");
  v8 = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    325,
    L"GetNetworkNameResource",
    0,
    L"In");
  *v3 = 0;
  TraceStringInline(
    7,
    4,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    330,
    L"GetNetworkNameResource",
    0,
    L"Provided Network Name: %s",
    lpString2);
  v9 = ClusterResourceTypeOpenEnum(hCluster, L"Network Name", 2u);
  hResTypeEnum = v9;
  v10 = v9;
  if ( v9 )
  {
    EnumCount = ClusterResourceTypeGetEnumCount(v9);
    v16 = 0;
    LODWORD(pv) = EnumCount;
    while ( 1 )
    {
      if ( v16 >= EnumCount )
      {
        ActualNameOfNetworkNameResource = 1;
        goto LABEL_33;
      }
      if ( v6 )
      {
        CoTaskMemFree(v6);
        lpszResourceName = 0;
      }
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v7 = 0;
        lpString1 = 0;
      }
      if ( v8 )
      {
        TraceStringInline(
          7,
          240,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          374,
          L"GetNetworkNameResource",
          0,
          L"Closing hResource = 0x%x",
          v8);
        CloseClusterResource(v8);
        v8 = 0;
      }
      ActualNameOfNetworkNameResource = ClusterResourceTypeEnumHelper(
                                          v10,
                                          v16,
                                          &dwType,
                                          (unsigned __int16 **)&lpszResourceName);
      if ( ActualNameOfNetworkNameResource < 0 )
      {
        cchCount2[0] = ActualNameOfNetworkNameResource;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          382,
          L"GetNetworkNameResource",
          *(_QWORD *)cchCount2,
          L"Error enumerating cluster");
        v6 = (WCHAR *)lpszResourceName;
        goto LABEL_33;
      }
      v6 = (WCHAR *)lpszResourceName;
      v17 = OpenClusterResourceEx(hCluster, lpszResourceName, 0x2000000u, 0);
      v8 = v17;
      if ( !v17 )
        break;
      TraceStringInline(
        7,
        240,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        408,
        L"GetNetworkNameResource",
        0,
        L"After OpenClusterResourceEx, hResource = 0x%x",
        v17);
      ActualNameOfNetworkNameResource = GetActualNameOfNetworkNameResource(v8, (unsigned __int16 **)&lpString1);
      if ( ActualNameOfNetworkNameResource < 0 )
      {
        cchCount2a[0] = ActualNameOfNetworkNameResource;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          413,
          L"GetNetworkNameResource",
          *(_QWORD *)cchCount2a,
          L"GetActualNameOfNetworkNameResource failed");
        v7 = (WCHAR *)lpString1;
        goto LABEL_33;
      }
      v7 = (WCHAR *)lpString1;
      TraceStringInline(
        7,
        240,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        417,
        L"GetNetworkNameResource",
        0,
        L"Actual resource name = %s",
        lpString1);
      if ( CompareStringW(0x7Fu, 1u, v7, -1, lpString2, -1) == 2 )
      {
        v3 = v30;
        *v30 = v8;
        TraceStringInline(
          7,
          240,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          424,
          L"GetNetworkNameResource",
          0,
          L"Found it - actual resource name = %s, resource handle = 0x%x",
          v7,
          v8);
        goto LABEL_34;
      }
      v10 = hResTypeEnum;
      ++v16;
      EnumCount = (unsigned int)pv;
    }
    LastError = GetLastError();
    ActualNameOfNetworkNameResource = LastError;
    if ( LastError > 0 )
      ActualNameOfNetworkNameResource = (unsigned __int16)LastError | 0x80070000;
    pv = 0;
    StringW = MakeStringW((unsigned __int16 **)&pv, L"hCluster: %x lpszResourceName: %s", hCluster, v6);
    v20 = pv;
    if ( StringW >= 0 )
      TraceFileW(
        ActualNameOfNetworkNameResource,
        (unsigned __int16 *)pv,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        0x18Eu);
    FailedClusterAPIToEventLog(L"OpenClusterResourceEx", (unsigned int)ActualNameOfNetworkNameResource, v20);
    CoTaskMemFree(v20);
    cchCount2[0] = ActualNameOfNetworkNameResource;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      404,
      L"GetNetworkNameResource",
      *(_QWORD *)cchCount2,
      L"OpenClusterResourceEx failed");
LABEL_33:
    v3 = v30;
LABEL_34:
    ClusterResourceTypeCloseEnum(hResTypeEnum);
  }
  else
  {
    v11 = GetLastError();
    ActualNameOfNetworkNameResource = v11;
    if ( v11 > 0 )
      ActualNameOfNetworkNameResource = (unsigned __int16)v11 | 0x80070000;
    pv = 0;
    LODWORD(lpString2a) = 2;
    v13 = MakeStringW(
            (unsigned __int16 **)&pv,
            L"hCluster: %x lpszResourceTypeName: %s dwType: %d",
            hCluster,
            L"Network Name",
            lpString2a);
    v14 = pv;
    if ( v13 >= 0 )
      TraceFileW(
        ActualNameOfNetworkNameResource,
        (unsigned __int16 *)pv,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        0x158u);
    FailedClusterAPIToEventLog(L"ClusterResourceTypeOpenEnum", (unsigned int)ActualNameOfNetworkNameResource, v14);
    CoTaskMemFree(v14);
    cchCount2[0] = ActualNameOfNetworkNameResource;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      350,
      L"GetNetworkNameResource",
      *(_QWORD *)cchCount2,
      L"ClusterResourceTypeOpenEnum failed");
  }
  if ( ActualNameOfNetworkNameResource && v8 )
  {
    TraceStringInline(
      7,
      240,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      441,
      L"GetNetworkNameResource",
      0,
      L"Closing resource (error case) = 0x%x",
      v8);
    CloseClusterResource(v8);
    *v3 = 0;
  }
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
    CoTaskMemFree(v7);
  cchCount2[0] = ActualNameOfNetworkNameResource;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    460,
    L"GetNetworkNameResource",
    *(_QWORD *)cchCount2,
    L"Out");
  return (unsigned int)ActualNameOfNetworkNameResource;
}

```

## disassembly

```asm
0x180071a34  mov     [rsp-40h+arg_10], r8
0x180071a39  mov     [rsp-40h+hCluster], rcx
0x180071a3e  push    rbp
0x180071a3f  push    rbx
0x180071a40  push    rsi
0x180071a41  push    rdi
0x180071a42  push    r12
0x180071a44  push    r13
0x180071a46  push    r14
0x180071a48  push    r15
0x180071a4a  mov     rbp, rsp
0x180071a4d  sub     rsp, 78h
0x180071a51  xor     ebx, ebx
0x180071a53  mov     r12, r8
0x180071a56  mov     [rbp+lpszResourceName], rbx
0x180071a5a  mov     r13, rdx
0x180071a5d  mov     [rbp+lpString1], rbx
0x180071a61  mov     r15, rcx
0x180071a64  mov     [rbp+dwType], ebx
0x180071a67  mov     esi, ebx
0x180071a69  mov     edi, ebx
0x180071a6b  test    rdx, rdx
0x180071a6e  jnz     short loc_180071A7D
0x180071a70  lea     rcx, aGetnetworkname; "GetNetworkNameResource (com\\complus\\d"...
0x180071a77  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180071a7d  test    r12, r12
0x180071a80  jnz     short loc_180071A8F
0x180071a82  lea     rcx, aGetnetworkname_0; "GetNetworkNameResource (com\\complus\\d"...
0x180071a89  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180071a8f  mov     edx, 6
0x180071a94  lea     rax, aIn_0; "In"
0x180071a9b  mov     [rsp+78h+var_48], rax
0x180071aa0  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071aa7  lea     rax, aGetnetworkname_2; "GetNetworkNameResource"
0x180071aae  mov     qword ptr [rsp+78h+cchCount2], rbx
0x180071ab3  mov     r9d, 145h
0x180071ab9  mov     [rsp+78h+lpString2], rax
0x180071abe  lea     ecx, [rdx+1]
0x180071ac1  mov     r14, rbx
0x180071ac4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071ac9  mov     [rsp+78h+var_40], r13
0x180071ace  lea     rax, aProvidedNetwor; "Provided Network Name: %s"
0x180071ad5  mov     [rsp+78h+var_48], rax
0x180071ada  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071ae1  mov     edx, 4
0x180071ae6  mov     qword ptr [rsp+78h+cchCount2], rbx
0x180071aeb  lea     rax, aGetnetworkname_2; "GetNetworkNameResource"
0x180071af2  mov     [r12], rbx
0x180071af6  mov     r9d, 14Ah
0x180071afc  mov     [rsp+78h+lpString2], rax
0x180071b01  lea     ecx, [rdx+3]
0x180071b04  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071b09  mov     r8d, 2; dwType
0x180071b0f  lea     rdx, szResourceTypeName; "Network Name"
0x180071b16  mov     rcx, r15; hCluster
0x180071b19  call    cs:__imp_ClusterResourceTypeOpenEnum
0x180071b1f  mov     [rbp+hResTypeEnum], rax
0x180071b23  mov     rbx, rax
0x180071b26  test    rax, rax
0x180071b29  jnz     loc_180071BDF
0x180071b2f  call    cs:__imp_GetLastError
0x180071b35  mov     ebx, eax
0x180071b37  test    eax, eax
0x180071b39  jle     short loc_180071B44
0x180071b3b  movzx   ebx, ax
0x180071b3e  or      ebx, 80070000h
0x180071b44  lea     r9, szResourceTypeName; "Network Name"
0x180071b4b  mov     [rbp+pv], rsi
0x180071b4f  mov     r8, r15
0x180071b52  mov     dword ptr [rsp+78h+lpString2], 2
0x180071b5a  lea     rdx, aHclusterXLpszr_1; "hCluster: %x lpszResourceTypeName: %s d"...
0x180071b61  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180071b65  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180071b6a  mov     r15, [rbp+pv]
0x180071b6e  test    eax, eax
0x180071b70  js      short loc_180071B89
0x180071b72  mov     r9d, 158h; unsigned int
0x180071b78  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071b7f  mov     rdx, r15; unsigned __int16 *
0x180071b82  mov     ecx, ebx; int
0x180071b84  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180071b89  mov     r8, r15
0x180071b8c  lea     rcx, aClusterresourc_1; "ClusterResourceTypeOpenEnum"
0x180071b93  mov     edx, ebx
0x180071b95  call    cs:__imp_FailedClusterAPIToEventLog
0x180071b9b  mov     rcx, r15; pv
0x180071b9e  call    cs:__imp_CoTaskMemFree
0x180071ba4  mov     edx, 1
0x180071ba9  lea     rax, aClusterresourc_2; "ClusterResourceTypeOpenEnum failed"
0x180071bb0  mov     [rsp+78h+var_48], rax
0x180071bb5  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071bbc  mov     [rsp+78h+cchCount2], ebx
0x180071bc0  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071bc7  mov     r9d, 15Eh
0x180071bcd  mov     [rsp+78h+lpString2], r13
0x180071bd2  lea     ecx, [rdx+6]
0x180071bd5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071bda  jmp     loc_180071F0F
0x180071bdf  mov     rcx, rax; hResTypeEnum
0x180071be2  call    cs:__imp_ClusterResourceTypeGetEnumCount
0x180071be8  xor     r12d, r12d
0x180071beb  mov     dword ptr [rbp+pv], eax
0x180071bee  lea     r15d, [r12+1]
0x180071bf3  cmp     r12d, eax
0x180071bf6  jnb     loc_180071EF7
0x180071bfc  test    rsi, rsi
0x180071bff  jz      short loc_180071C12
0x180071c01  mov     rcx, rsi; pv
0x180071c04  call    cs:__imp_CoTaskMemFree
0x180071c0a  mov     [rbp+lpszResourceName], 0
0x180071c12  test    rdi, rdi
0x180071c15  jz      short loc_180071C26
0x180071c17  mov     rcx, rdi; pv
0x180071c1a  call    cs:__imp_CoTaskMemFree
0x180071c20  xor     edi, edi
0x180071c22  mov     [rbp+lpString1], rdi
0x180071c26  test    r14, r14
0x180071c29  jz      short loc_180071C79
0x180071c2b  mov     [rsp+78h+var_40], r14
0x180071c30  lea     rax, aClosingHresour; "Closing hResource = 0x%x"
0x180071c37  mov     [rsp+78h+var_48], rax
0x180071c3c  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071c43  lea     rax, aGetnetworkname_2; "GetNetworkNameResource"
0x180071c4a  mov     qword ptr [rsp+78h+cchCount2], 0
0x180071c53  mov     r9d, 176h
0x180071c59  mov     [rsp+78h+lpString2], rax
0x180071c5e  mov     edx, 0F0h
0x180071c63  mov     ecx, 7
0x180071c68  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071c6d  mov     rcx, r14; hResource
0x180071c70  call    cs:__imp_CloseClusterResource
0x180071c76  xor     r14d, r14d
0x180071c79  lea     r9, [rbp+lpszResourceName]; unsigned __int16 **
0x180071c7d  mov     edx, r12d; dwIndex
0x180071c80  lea     r8, [rbp+dwType]; lpdwType
0x180071c84  mov     rcx, rbx; hResTypeEnum
0x180071c87  call    ?ClusterResourceTypeEnumHelper@@YAJPEAU_HRESTYPEENUM@@KPEAKPEAPEAG@Z; ClusterResourceTypeEnumHelper(_HRESTYPEENUM *,ulong,ulong *,ushort * *)
0x180071c8c  mov     ebx, eax
0x180071c8e  test    eax, eax
0x180071c90  js      loc_180071EBB
0x180071c96  mov     rsi, [rbp+lpszResourceName]
0x180071c9a  xor     r9d, r9d; lpdwGrantedAccess
0x180071c9d  mov     rcx, [rbp+hCluster]; hCluster
0x180071ca1  mov     rdx, rsi; lpszResourceName
0x180071ca4  mov     r8d, 2000000h; dwDesiredAccess
0x180071caa  call    cs:__imp_OpenClusterResourceEx
0x180071cb0  mov     r14, rax
0x180071cb3  test    rax, rax
0x180071cb6  jz      loc_180071E15
0x180071cbc  mov     [rsp+78h+var_40], rax
0x180071cc1  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071cc8  lea     rax, aAfterOpenclust; "After OpenClusterResourceEx, hResource "...
0x180071ccf  mov     r9d, 198h
0x180071cd5  mov     [rsp+78h+var_48], rax
0x180071cda  mov     edx, 0F0h
0x180071cdf  lea     rax, aGetnetworkname_2; "GetNetworkNameResource"
0x180071ce6  mov     qword ptr [rsp+78h+cchCount2], 0
0x180071cef  mov     ecx, 7
0x180071cf4  mov     [rsp+78h+lpString2], rax
0x180071cf9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071cfe  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180071d02  mov     rcx, r14; hResource
0x180071d05  call    ?GetActualNameOfNetworkNameResource@@YAJPEAU_HRESOURCE@@PEAPEAG@Z; GetActualNameOfNetworkNameResource(_HRESOURCE *,ushort * *)
0x180071d0a  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071d11  mov     ebx, eax
0x180071d13  mov     ecx, 7
0x180071d18  test    eax, eax
0x180071d1a  js      loc_180071DE2
0x180071d20  mov     rdi, [rbp+lpString1]
0x180071d24  lea     rax, aActualResource; "Actual resource name = %s"
0x180071d2b  mov     [rsp+78h+var_40], rdi
0x180071d30  mov     r9d, 1A1h
0x180071d36  mov     [rsp+78h+var_48], rax
0x180071d3b  mov     edx, 0F0h
0x180071d40  lea     rax, aGetnetworkname_2; "GetNetworkNameResource"
0x180071d47  mov     qword ptr [rsp+78h+cchCount2], 0
0x180071d50  mov     [rsp+78h+lpString2], rax
0x180071d55  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071d5a  or      eax, 0FFFFFFFFh
0x180071d5d  mov     r8, rdi; lpString1
0x180071d60  mov     [rsp+78h+cchCount2], eax; cchCount2
0x180071d64  mov     r9d, eax; cchCount1
0x180071d67  mov     edx, r15d; dwCmpFlags
0x180071d6a  mov     [rsp+78h+lpString2], r13; lpString2
0x180071d6f  mov     ecx, 7Fh; Locale
0x180071d74  call    cs:__imp_CompareStringW
0x180071d7a  cmp     eax, 2
0x180071d7d  jz      short loc_180071D8E
0x180071d7f  mov     rbx, [rbp+hResTypeEnum]
0x180071d83  add     r12d, r15d
0x180071d86  mov     eax, dword ptr [rbp+pv]
0x180071d89  jmp     loc_180071BF3
0x180071d8e  mov     r12, [rbp+arg_10]
0x180071d92  lea     rax, aFoundItActualR; "Found it - actual resource name = %s, r"...
0x180071d99  mov     [rsp+78h+var_38], r14
0x180071d9e  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071da5  mov     [rsp+78h+var_40], rdi
0x180071daa  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071db1  mov     [rsp+78h+var_48], rax
0x180071db6  mov     r9d, 1A8h
0x180071dbc  mov     qword ptr [rsp+78h+cchCount2], 0
0x180071dc5  mov     edx, 0F0h
0x180071dca  mov     ecx, 7
0x180071dcf  mov     [r12], r14
0x180071dd3  mov     [rsp+78h+lpString2], r13
0x180071dd8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071ddd  jmp     loc_180071F05
0x180071de2  lea     rax, aGetactualnameo_6; "GetActualNameOfNetworkNameResource fail"...
0x180071de9  mov     r9d, 19Dh
0x180071def  mov     [rsp+78h+var_48], rax
0x180071df4  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071dfb  mov     [rsp+78h+cchCount2], ebx
0x180071dff  mov     edx, r15d
0x180071e02  mov     [rsp+78h+lpString2], r13
0x180071e07  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071e0c  mov     rdi, [rbp+lpString1]
0x180071e10  jmp     loc_180071F01
0x180071e15  call    cs:__imp_GetLastError
0x180071e1b  mov     ebx, eax
0x180071e1d  test    eax, eax
0x180071e1f  jle     short loc_180071E2A
0x180071e21  movzx   ebx, ax
0x180071e24  or      ebx, 80070000h
0x180071e2a  mov     r8, [rbp+hCluster]
0x180071e2e  lea     rdx, aHclusterXLpszr_0; "hCluster: %x lpszResourceName: %s"
0x180071e35  mov     r9, rsi
0x180071e38  mov     [rbp+pv], 0
0x180071e40  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180071e44  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180071e49  mov     r12, [rbp+pv]
0x180071e4d  test    eax, eax
0x180071e4f  js      short loc_180071E68
0x180071e51  mov     r9d, 18Eh; unsigned int
0x180071e57  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071e5e  mov     rdx, r12; unsigned __int16 *
0x180071e61  mov     ecx, ebx; int
0x180071e63  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180071e68  mov     r8, r12
0x180071e6b  lea     rcx, aOpenclusterres; "OpenClusterResourceEx"
0x180071e72  mov     edx, ebx
0x180071e74  call    cs:__imp_FailedClusterAPIToEventLog
0x180071e7a  mov     rcx, r12; pv
0x180071e7d  call    cs:__imp_CoTaskMemFree
0x180071e83  lea     rax, aOpenclusterres_0; "OpenClusterResourceEx failed"
0x180071e8a  mov     r9d, 194h
0x180071e90  mov     [rsp+78h+var_48], rax
0x180071e95  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071e9c  mov     [rsp+78h+cchCount2], ebx
0x180071ea0  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071ea7  mov     edx, r15d
0x180071eaa  mov     [rsp+78h+lpString2], r13
0x180071eaf  mov     ecx, 7
0x180071eb4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071eb9  jmp     short loc_180071F01
0x180071ebb  lea     rax, aErrorEnumerati; "Error enumerating cluster"
0x180071ec2  mov     r9d, 17Eh
0x180071ec8  mov     [rsp+78h+var_48], rax
0x180071ecd  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071ed4  mov     [rsp+78h+cchCount2], ebx
0x180071ed8  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071edf  mov     edx, r15d
0x180071ee2  mov     [rsp+78h+lpString2], r13
0x180071ee7  mov     ecx, 7
0x180071eec  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071ef1  mov     rsi, [rbp+lpszResourceName]
0x180071ef5  jmp     short loc_180071F01
0x180071ef7  mov     ebx, r15d
0x180071efa  lea     r13, aGetnetworkname_2; "GetNetworkNameResource"
0x180071f01  mov     r12, [rbp+arg_10]
0x180071f05  mov     rcx, [rbp+hResTypeEnum]; hResTypeEnum
0x180071f09  call    cs:__imp_ClusterResourceTypeCloseEnum
0x180071f0f  test    ebx, ebx
0x180071f11  jz      short loc_180071F64
0x180071f13  test    r14, r14
0x180071f16  jz      short loc_180071F64
0x180071f18  mov     [rsp+78h+var_40], r14
0x180071f1d  lea     rax, aClosingResourc; "Closing resource (error case) = 0x%x"
0x180071f24  mov     [rsp+78h+var_48], rax
0x180071f29  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180071f30  mov     qword ptr [rsp+78h+cchCount2], 0
0x180071f39  mov     r9d, 1B9h
0x180071f3f  mov     edx, 0F0h
0x180071f44  mov     [rsp+78h+lpString2], r13
0x180071f49  mov     ecx, 7
0x180071f4e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180071f53  mov     rcx, r14; hResource
0x180071f56  call    cs:__imp_CloseClusterResource
0x180071f5c  mov     qword ptr [r12], 0
0x180071f64  test    rsi, rsi
0x180071f67  jz      short loc_180071F72
0x180071f69  mov     rcx, rsi; pv
0x180071f6c  call    cs:__imp_CoTaskMemFree
0x180071f72  test    rdi, rdi
0x180071f75  jz      short loc_180071F80
0x180071f77  mov     rcx, rdi; pv
0x180071f7a  call    cs:__imp_CoTaskMemFree
0x180071f80  mov     edx, 6
0x180071f85  lea     rax, aOut; "Out"
0x180071f8c  mov     [rsp+78h+var_48], rax
0x180071f91  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
  ... truncated ...
```
