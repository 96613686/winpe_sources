# GetActualNameOfNetworkNameResource(_HRESOURCE *,ushort * *)

- ea: `0x18001a9b8`
- end: `0x18001ac8e`
- name: `?GetActualNameOfNetworkNameResource@@YAJPEAU_HRESOURCE@@PEAPEAG@Z`
- size: `726`
- prototype: `__int64 __fastcall(HRESOURCE hResource, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180013694`
- `0x180071a34`

## callees

- `0x180003cf0`
- `0x180006324`
- `0x180006764`
- `0x18000d5f4`
- `0x18001156c`
- `0x18001a9b8`
- `0x18001d178`
- `0x18001d184`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac5d`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001aa9c`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001ab94`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001abe6`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001aa9c`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001ab94`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001abe6`
- `CLUSAPI!ClusterResourceControl` at `0x18001aa2d`
- `CLUSAPI!ClusterResourceControl` at `0x18001ab33`
- `CLUSAPI!ClusterResourceControl` at `0x18001aa2d`
- `CLUSAPI!ClusterResourceControl` at `0x18001ab33`
- `RESUTILS!ResUtilFindSzProperty` at `0x18001abbf`
- `RESUTILS!ResUtilFindSzProperty` at `0x18001abbf`

## string_xrefs

- `0x18001aa7f`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001aac2`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001ab77`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001ac27`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001a9ea`: `GetActualNameOfNetworkNameResource (com\complus\dtc\shared\util\clusterutilbasic.cpp@1268): GetActualNameOfNetworkNameResource, hResource != NULL`
- `0x18001a9fc`: `GetActualNameOfNetworkNameResource (com\complus\dtc\shared\util\clusterutilbasic.cpp@1269): GetActualNameOfNetworkNameResource, ppwszActualName != NULL`

## pseudocode

```c
__int64 __fastcall GetActualNameOfNetworkNameResource(HRESOURCE hResource, LPVOID *a2)
{
  void *v2; // rdi
  signed int v5; // eax
  signed int v6; // ebx
  void *v7; // r14
  int StringW; // eax
  void *v9; // rsi
  __int64 v10; // r9
  const wchar_t *v11; // rax
  __int64 v12; // rcx
  signed int v13; // eax
  int v14; // eax
  void *v15; // rsi
  signed int SzProperty; // eax
  LPVOID lpOutBuffer; // [rsp+28h] [rbp-28h]
  LPWSTR pszPropertyValue; // [rsp+40h] [rbp-10h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp+30h] BYREF
  DWORD lpBytesReturned; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  pszPropertyValue = 0;
  pv = 0;
  BytesReturned = 0;
  lpBytesReturned = 0;
  if ( !hResource )
    DtcInternalErrorW(
      L"GetActualNameOfNetworkNameResource (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@1268): GetActualNameOfNe"
       "tworkNameResource, hResource != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"GetActualNameOfNetworkNameResource (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@1269): GetActualNameOfNe"
       "tworkNameResource, ppwszActualName != NULL");
  *a2 = 0;
  v5 = ClusterResourceControl(hResource, 0, 0x1000081u, 0, 0, 0, 0, &BytesReturned);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v6 = 0;
  if ( v5 != -2147024662 )
    v6 = v5;
  if ( v6 < 0 )
  {
    pv = 0;
    v7 = 0;
    StringW = MakeStringW(
                (unsigned __int16 **)&pv,
                L"hResource: %x hHostNode: NULL dwControlCode:%d",
                hResource,
                16777345);
    v9 = pv;
    if ( StringW >= 0 )
      TraceFileW(v6, (unsigned __int16 *)pv, L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp", 0x50Du);
    FailedClusterAPIToEventLog(L"ClusterResourceControl", (unsigned int)v6, v9);
    CoTaskMemFree(v9);
    v10 = 1298;
LABEL_13:
    v11 = L"GetActualNameOfNetworkNameResource, ClusterResourceControl failed";
LABEL_14:
    v12 = 7;
LABEL_15:
    LODWORD(lpOutBuffer) = v6;
    TraceStringInline(
      v12,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      v10,
      L"GetActualNameOfNetworkNameResource",
      lpOutBuffer,
      v11);
    goto LABEL_31;
  }
  v7 = operator new[](BytesReturned);
  if ( !v7 )
  {
    v6 = -2147024882;
    v11 = L"GetActualNameOfNetworkNameResource, new BYTE [cbRequired] failed";
    v10 = 1305;
    goto LABEL_14;
  }
  v13 = ClusterResourceControl(hResource, 0, 0x1000081u, 0, 0, v7, BytesReturned, &lpBytesReturned);
  v6 = v13;
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
  if ( v6 < 0 )
  {
    pv = 0;
    v14 = MakeStringW((unsigned __int16 **)&pv, L"hResource: %x hHostNode: NULL dwControlCode:%d", hResource, 16777345);
    v15 = pv;
    if ( v14 >= 0 )
      TraceFileW(v6, (unsigned __int16 *)pv, L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp", 0x52Du);
    FailedClusterAPIToEventLog(L"ClusterResourceControl", (unsigned int)v6, v15);
    CoTaskMemFree(v15);
    v10 = 1331;
    goto LABEL_13;
  }
  SzProperty = ResUtilFindSzProperty(v7, BytesReturned, L"Name", &pszPropertyValue);
  v6 = SzProperty;
  if ( SzProperty )
  {
    if ( SzProperty > 0 )
      v6 = (unsigned __int16)SzProperty | 0x80070000;
    FailedClusterAPIToEventLog(L"ResUtilFindSzProperty", (unsigned int)v6, L" ");
    v11 = L"GetActualNameOfNetworkNameResource, ResUtilFindSzProperty failed";
    v10 = 1345;
    v12 = 8;
    goto LABEL_15;
  }
  v6 = DuplicateString(pszPropertyValue, (unsigned __int16 **)&pv);
  if ( v6 >= 0 )
  {
    v2 = pv;
    *a2 = pv;
  }
  else
  {
    LODWORD(lpOutBuffer) = v6;
    TraceStringInline(
      8,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      1351,
      L"GetActualNameOfNetworkNameResource",
      lpOutBuffer,
      L"GetActualNameOfNetworkNameResource, DuplicateString failed");
    v2 = pv;
  }
LABEL_31:
  LocalFree(pszPropertyValue);
  if ( v6 < 0 )
    CoTaskMemFree(v2);
  operator delete(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a9b8  mov     [rsp-28h+arg_8], rbx
0x18001a9bd  push    rbp
0x18001a9be  push    rsi
0x18001a9bf  push    rdi
0x18001a9c0  push    r14
0x18001a9c2  push    r15
0x18001a9c4  mov     rbp, rsp
0x18001a9c7  sub     rsp, 50h
0x18001a9cb  xor     edi, edi
0x18001a9cd  mov     [rbp+pszPropertyValue], 0
0x18001a9d5  mov     [rbp+pv], rdi
0x18001a9d9  mov     r15, rdx
0x18001a9dc  mov     [rbp+BytesReturned], edi
0x18001a9df  mov     rsi, rcx
0x18001a9e2  mov     [rbp+arg_10], edi
0x18001a9e5  test    rcx, rcx
0x18001a9e8  jnz     short loc_18001A9F7
0x18001a9ea  lea     rcx, aGetactualnameo_1; "GetActualNameOfNetworkNameResource (com"...
0x18001a9f1  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001a9f7  test    r15, r15
0x18001a9fa  jnz     short loc_18001AA09
0x18001a9fc  lea     rcx, aGetactualnameo_5; "GetActualNameOfNetworkNameResource (com"...
0x18001aa03  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001aa09  lea     rax, [rbp+BytesReturned]
0x18001aa0d  mov     [rdx], rdi
0x18001aa10  mov     [rsp+50h+lpBytesReturned], rax; lpBytesReturned
0x18001aa15  xor     r9d, r9d; lpInBuffer
0x18001aa18  mov     [rsp+50h+cbOutBufferSize], edi; cbOutBufferSize
0x18001aa1c  xor     edx, edx; hHostNode
0x18001aa1e  mov     [rsp+50h+lpOutBuffer], rdi; lpOutBuffer
0x18001aa23  mov     r8d, 1000081h; dwControlCode
0x18001aa29  mov     [rsp+50h+cbInBufferSize], edi; cbInBufferSize
0x18001aa2d  call    cs:__imp_ClusterResourceControl
0x18001aa33  test    eax, eax
0x18001aa35  jle     short loc_18001AA3F
0x18001aa37  movzx   eax, ax
0x18001aa3a  or      eax, 80070000h
0x18001aa3f  xor     ebx, ebx
0x18001aa41  cmp     eax, 800700EAh
0x18001aa46  cmovnz  ebx, eax
0x18001aa49  test    ebx, ebx
0x18001aa4b  jns     loc_18001AAE8
0x18001aa51  mov     r9d, 1000081h
0x18001aa57  mov     [rbp+pv], rdi
0x18001aa5b  mov     r8, rsi
0x18001aa5e  lea     rdx, aHresourceXHhos; "hResource: %x hHostNode: NULL dwControl"...
0x18001aa65  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18001aa69  xor     r14d, r14d
0x18001aa6c  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001aa71  mov     rsi, [rbp+pv]
0x18001aa75  test    eax, eax
0x18001aa77  js      short loc_18001AA90
0x18001aa79  mov     r9d, 50Dh; unsigned int
0x18001aa7f  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001aa86  mov     rdx, rsi; unsigned __int16 *
0x18001aa89  mov     ecx, ebx; int
0x18001aa8b  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001aa90  mov     r8, rsi
0x18001aa93  lea     rcx, aClusterresourc_3; "ClusterResourceControl"
0x18001aa9a  mov     edx, ebx
0x18001aa9c  call    cs:__imp_FailedClusterAPIToEventLog
0x18001aaa2  mov     rcx, rsi; pv
0x18001aaa5  call    cs:__imp_CoTaskMemFree
0x18001aaab  mov     r9d, 512h
0x18001aab1  lea     rax, aGetactualnameo_4; "GetActualNameOfNetworkNameResource, Clu"...
0x18001aab8  mov     ecx, 7
0x18001aabd  mov     qword ptr [rsp+50h+cbOutBufferSize], rax
0x18001aac2  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001aac9  lea     rax, aGetactualnameo; "GetActualNameOfNetworkNameResource"
0x18001aad0  mov     dword ptr [rsp+50h+lpOutBuffer], ebx
0x18001aad4  mov     edx, 1
0x18001aad9  mov     qword ptr [rsp+50h+cbInBufferSize], rax
0x18001aade  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001aae3  jmp     loc_18001AC59
0x18001aae8  mov     ecx, [rbp+BytesReturned]; unsigned __int64
0x18001aaeb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001aaf0  mov     r14, rax
0x18001aaf3  test    rax, rax
0x18001aaf6  jnz     short loc_18001AB0C
0x18001aaf8  mov     ebx, 8007000Eh
0x18001aafd  lea     rax, aGetactualnameo_0; "GetActualNameOfNetworkNameResource, new"...
0x18001ab04  mov     r9d, 519h
0x18001ab0a  jmp     short loc_18001AAB8
0x18001ab0c  lea     rax, [rbp+arg_10]
0x18001ab10  xor     r9d, r9d; lpInBuffer
0x18001ab13  mov     [rsp+50h+lpBytesReturned], rax; lpBytesReturned
0x18001ab18  xor     edx, edx; hHostNode
0x18001ab1a  mov     eax, [rbp+BytesReturned]
0x18001ab1d  mov     r8d, 1000081h; dwControlCode
0x18001ab23  mov     [rsp+50h+cbOutBufferSize], eax; cbOutBufferSize
0x18001ab27  mov     rcx, rsi; hResource
0x18001ab2a  mov     [rsp+50h+lpOutBuffer], r14; lpOutBuffer
0x18001ab2f  mov     [rsp+50h+cbInBufferSize], edi; cbInBufferSize
0x18001ab33  call    cs:__imp_ClusterResourceControl
0x18001ab39  mov     ebx, eax
0x18001ab3b  test    eax, eax
0x18001ab3d  jle     short loc_18001AB48
0x18001ab3f  movzx   ebx, ax
0x18001ab42  or      ebx, 80070000h
0x18001ab48  test    ebx, ebx
0x18001ab4a  jns     short loc_18001ABAE
0x18001ab4c  mov     r9d, 1000081h
0x18001ab52  mov     [rbp+pv], rdi
0x18001ab56  mov     r8, rsi
0x18001ab59  lea     rdx, aHresourceXHhos; "hResource: %x hHostNode: NULL dwControl"...
0x18001ab60  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18001ab64  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001ab69  mov     rsi, [rbp+pv]
0x18001ab6d  test    eax, eax
0x18001ab6f  js      short loc_18001AB88
0x18001ab71  mov     r9d, 52Dh; unsigned int
0x18001ab77  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001ab7e  mov     rdx, rsi; unsigned __int16 *
0x18001ab81  mov     ecx, ebx; int
0x18001ab83  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001ab88  mov     r8, rsi
0x18001ab8b  lea     rcx, aClusterresourc_3; "ClusterResourceControl"
0x18001ab92  mov     edx, ebx
0x18001ab94  call    cs:__imp_FailedClusterAPIToEventLog
0x18001ab9a  mov     rcx, rsi; pv
0x18001ab9d  call    cs:__imp_CoTaskMemFree
0x18001aba3  mov     r9d, 533h
0x18001aba9  jmp     loc_18001AAB1
0x18001abae  mov     edx, [rbp+BytesReturned]; cbPropertyListSize
0x18001abb1  lea     r9, [rbp+pszPropertyValue]; pszPropertyValue
0x18001abb5  lea     r8, pszPropertyName; "Name"
0x18001abbc  mov     rcx, r14; pPropertyList
0x18001abbf  call    cs:__imp_ResUtilFindSzProperty
0x18001abc5  mov     ebx, eax
0x18001abc7  test    eax, eax
0x18001abc9  jz      short loc_18001AC03
0x18001abcb  jle     short loc_18001ABD6
0x18001abcd  movzx   ebx, ax
0x18001abd0  or      ebx, 80070000h
0x18001abd6  lea     r8, asc_180093980; " "
0x18001abdd  mov     edx, ebx
0x18001abdf  lea     rcx, aResutilfindszp; "ResUtilFindSzProperty"
0x18001abe6  call    cs:__imp_FailedClusterAPIToEventLog
0x18001abec  lea     rax, aGetactualnameo_2; "GetActualNameOfNetworkNameResource, Res"...
0x18001abf3  mov     r9d, 541h
0x18001abf9  mov     ecx, 8
0x18001abfe  jmp     loc_18001AABD
0x18001ac03  mov     rcx, [rbp+pszPropertyValue]; unsigned __int16 *
0x18001ac07  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18001ac0b  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18001ac10  mov     ebx, eax
0x18001ac12  test    eax, eax
0x18001ac14  jns     short loc_18001AC52
0x18001ac16  mov     edx, 1
0x18001ac1b  lea     rax, aGetactualnameo_3; "GetActualNameOfNetworkNameResource, Dup"...
0x18001ac22  mov     qword ptr [rsp+50h+cbOutBufferSize], rax
0x18001ac27  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001ac2e  lea     rax, aGetactualnameo; "GetActualNameOfNetworkNameResource"
0x18001ac35  mov     dword ptr [rsp+50h+lpOutBuffer], ebx
0x18001ac39  mov     r9d, 547h
0x18001ac3f  mov     qword ptr [rsp+50h+cbInBufferSize], rax
0x18001ac44  lea     ecx, [rdx+7]
0x18001ac47  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ac4c  mov     rdi, [rbp+pv]
0x18001ac50  jmp     short loc_18001AC59
0x18001ac52  mov     rdi, [rbp+pv]
0x18001ac56  mov     [r15], rdi
0x18001ac59  mov     rcx, [rbp+pszPropertyValue]; hMem
0x18001ac5d  call    cs:__imp_LocalFree
0x18001ac63  test    ebx, ebx
0x18001ac65  jns     short loc_18001AC70
0x18001ac67  mov     rcx, rdi; pv
0x18001ac6a  call    cs:__imp_CoTaskMemFree
0x18001ac70  mov     rcx, r14; Block
0x18001ac73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac78  mov     eax, ebx
0x18001ac7a  mov     rbx, [rsp+50h+arg_8]
0x18001ac82  add     rsp, 50h
0x18001ac86  pop     r15
0x18001ac88  pop     r14
0x18001ac8a  pop     rdi
0x18001ac8b  pop     rsi
0x18001ac8c  pop     rbp
0x18001ac8d  retn
```
