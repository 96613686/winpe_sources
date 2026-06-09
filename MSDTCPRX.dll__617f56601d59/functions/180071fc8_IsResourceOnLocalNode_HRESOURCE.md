# IsResourceOnLocalNode(_HRESOURCE *)

- ea: `0x180071fc8`
- end: `0x18007216e`
- name: `?IsResourceOnLocalNode@@YAHPEAU_HRESOURCE@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(HRESOURCE hResource)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013694`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x1800092f4`
- `0x18000d5f4`
- `0x18001156c`
- `0x180071fc8`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007210b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007214b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007210b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007214b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007209b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007209b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180072136`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180072136`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180072102`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180072102`
- `CLUSAPI!GetClusterResourceState` at `0x18007208c`
- `CLUSAPI!GetClusterResourceState` at `0x18007208c`

## string_xrefs

- `0x18007205e`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800720e5`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18007201f`: `IsResourceOnLocalNode (com\complus\dtc\shared\util\clusterutilbasic.cpp@1212): IsResourceOnLocalNode, hResource != NULL`

## pseudocode

```c
_BOOL8 __fastcall IsResourceOnLocalNode(HRESOURCE hResource)
{
  BOOL v2; // edi
  int PhysicalNodeNameW; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StringW; // eax
  void *v7; // rsi
  LPDWORD lpcchGroupName; // [rsp+20h] [rbp-E0h]
  __int64 v10; // [rsp+28h] [rbp-D8h]
  DWORD cchNodeName; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpString2; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szNodeName; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[526]; // [rsp+62h] [rbp-9Eh] BYREF

  szNodeName = 0;
  memset_0(v15, 0, 0x200u);
  cchNodeName = 257;
  lpString2 = 0;
  if ( !hResource )
    DtcInternalErrorW(
      L"IsResourceOnLocalNode (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@1212): IsResourceOnLocalNode, hResource != NULL");
  v2 = 0;
  PhysicalNodeNameW = GetPhysicalNodeNameW((BYTE **)&lpString2);
  if ( PhysicalNodeNameW >= 0 )
  {
    if ( GetClusterResourceState(hResource, &szNodeName, &cchNodeName, 0, 0) == ClusterResourceStateUnknown )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(lpcchGroupName) = cchNodeName;
      pv = 0;
      StringW = MakeStringW(
                  (unsigned __int16 **)&pv,
                  L"hResource: %x lpszNodeName: %s lpcchNodeName: %d",
                  hResource,
                  &szNodeName,
                  lpcchGroupName);
      v7 = pv;
      if ( StringW >= 0 )
        TraceFileW(v5, (unsigned __int16 *)pv, L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp", 0x4D4u);
      FailedClusterAPIToEventLog(L"GetClusterResourceState", v5, v7);
      CoTaskMemFree(v7);
      LODWORD(v10) = v5;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        1242,
        L"IsResourceOnLocalNode",
        v10,
        L"GetClusterResourceState failed");
    }
    else
    {
      v2 = lstrcmpiW(&szNodeName, lpString2) == 0;
    }
  }
  else
  {
    LODWORD(v10) = PhysicalNodeNameW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      1217,
      L"IsResourceOnLocalNode",
      v10,
      L"GetPhysicalNodeNameW failed");
  }
  CoTaskMemFree((LPVOID)lpString2);
  return v2;
}

```

## disassembly

```asm
0x180071fc8  push    rbp
0x180071fca  push    rbx
0x180071fcb  push    rsi
0x180071fcc  push    rdi
0x180071fcd  lea     rbp, [rsp-188h]
0x180071fd5  sub     rsp, 288h
0x180071fdc  mov     rax, cs:__security_cookie
0x180071fe3  xor     rax, rsp
0x180071fe6  mov     [rbp+1A0h+var_30], rax
0x180071fed  mov     rsi, rcx
0x180071ff0  xor     eax, eax
0x180071ff2  lea     rcx, [rsp+2A0h+var_23E]; void *
0x180071ff7  mov     [rsp+2A0h+szNodeName], ax
0x180071ffc  xor     edx, edx; Val
0x180071ffe  mov     r8d, 200h; Size
0x180072004  call    memset_0
0x180072009  mov     [rsp+2A0h+cchNodeName], 101h
0x180072011  mov     [rsp+2A0h+lpString2], 0
0x18007201a  test    rsi, rsi
0x18007201d  jnz     short loc_18007202C
0x18007201f  lea     rcx, aIsresourceonlo_0; "IsResourceOnLocalNode (com\\complus\\dt"...
0x180072026  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007202c  lea     rcx, [rsp+2A0h+lpString2]; unsigned __int16 **
0x180072031  xor     edi, edi
0x180072033  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x180072038  test    eax, eax
0x18007203a  jns     short loc_180072077
0x18007203c  lea     rcx, aGetphysicalnod; "GetPhysicalNodeNameW failed"
0x180072043  mov     r9d, 4C1h
0x180072049  mov     [rsp+2A0h+var_270], rcx
0x18007204e  mov     dword ptr [rsp+2A0h+var_278], eax
0x180072052  mov     edx, 1
0x180072057  lea     rax, aIsresourceonlo; "IsResourceOnLocalNode"
0x18007205e  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180072065  mov     [rsp+2A0h+lpcchGroupName], rax
0x18007206a  lea     ecx, [rdx+6]
0x18007206d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180072072  jmp     loc_180072146
0x180072077  xor     r9d, r9d; lpszGroupName
0x18007207a  mov     [rsp+2A0h+lpcchGroupName], rdi; lpcchGroupName
0x18007207f  lea     r8, [rsp+2A0h+cchNodeName]; lpcchNodeName
0x180072084  mov     rcx, rsi; hResource
0x180072087  lea     rdx, [rsp+2A0h+szNodeName]; lpszNodeName
0x18007208c  call    cs:__imp_GetClusterResourceState
0x180072092  cmp     eax, 0FFFFFFFFh
0x180072095  jnz     loc_18007212C
0x18007209b  call    cs:__imp_GetLastError
0x1800720a1  mov     ebx, eax
0x1800720a3  test    eax, eax
0x1800720a5  jle     short loc_1800720B0
0x1800720a7  movzx   ebx, ax
0x1800720aa  or      ebx, 80070000h
0x1800720b0  mov     eax, [rsp+2A0h+cchNodeName]
0x1800720b4  lea     r9, [rsp+2A0h+szNodeName]
0x1800720b9  mov     r8, rsi
0x1800720bc  mov     dword ptr [rsp+2A0h+lpcchGroupName], eax
0x1800720c0  lea     rdx, aHresourceXLpsz; "hResource: %x lpszNodeName: %s lpcchNod"...
0x1800720c7  mov     [rsp+2A0h+pv], rdi
0x1800720cc  lea     rcx, [rsp+2A0h+pv]; unsigned __int16 **
0x1800720d1  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800720d6  mov     rsi, [rsp+2A0h+pv]
0x1800720db  test    eax, eax
0x1800720dd  js      short loc_1800720F6
0x1800720df  mov     r9d, 4D4h; unsigned int
0x1800720e5  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800720ec  mov     rdx, rsi; unsigned __int16 *
0x1800720ef  mov     ecx, ebx; int
0x1800720f1  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800720f6  mov     r8, rsi
0x1800720f9  lea     rcx, aGetclusterreso_0; "GetClusterResourceState"
0x180072100  mov     edx, ebx
0x180072102  call    cs:__imp_FailedClusterAPIToEventLog
0x180072108  mov     rcx, rsi; pv
0x18007210b  call    cs:__imp_CoTaskMemFree
0x180072111  lea     rax, aGetclusterreso_1; "GetClusterResourceState failed"
0x180072118  mov     r9d, 4DAh
0x18007211e  mov     [rsp+2A0h+var_270], rax
0x180072123  mov     dword ptr [rsp+2A0h+var_278], ebx
0x180072127  jmp     loc_180072052
0x18007212c  mov     rdx, [rsp+2A0h+lpString2]; lpString2
0x180072131  lea     rcx, [rsp+2A0h+szNodeName]; lpString1
0x180072136  call    cs:__imp_lstrcmpiW
0x18007213c  test    eax, eax
0x18007213e  mov     ecx, 1
0x180072143  cmovz   edi, ecx
0x180072146  mov     rcx, [rsp+2A0h+lpString2]; pv
0x18007214b  call    cs:__imp_CoTaskMemFree
0x180072151  mov     eax, edi
0x180072153  mov     rcx, [rbp+1A0h+var_30]
0x18007215a  xor     rcx, rsp; StackCookie
0x18007215d  call    __security_check_cookie
0x180072162  add     rsp, 288h
0x180072169  pop     rdi
0x18007216a  pop     rsi
0x18007216b  pop     rbx
0x18007216c  pop     rbp
0x18007216d  retn
```
