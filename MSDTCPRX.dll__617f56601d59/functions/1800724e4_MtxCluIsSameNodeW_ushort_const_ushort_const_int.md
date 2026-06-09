# MtxCluIsSameNodeW(ushort const *,ushort const *,int *)

- ea: `0x1800724e4`
- end: `0x1800726c8`
- name: `?MtxCluIsSameNodeW@@YAJPEBG0PEAH@Z`
- size: `484`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004fe10`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x18001c410`
- `0x18007198c`
- `0x1800724e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007269e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800726a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007269e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800726a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007266d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007266d`
- `msvcrt!_wcsicmp` at `0x18007255a`
- `msvcrt!_wcsicmp` at `0x18007255a`
- `CLUSAPI!CloseClusterResource` at `0x180072686`
- `CLUSAPI!CloseClusterResource` at `0x180072695`
- `CLUSAPI!CloseClusterResource` at `0x180072686`
- `CLUSAPI!CloseClusterResource` at `0x180072695`

## string_xrefs

- `0x18007258a`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800725e0`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180072633`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180072524`: `MtxCluIsSameNodeW (com\complus\dtc\shared\util\clusterutilbasic.cpp@595): MtxCluIsSameNodeW, pwszName1 != NULL`
- `0x180072536`: `MtxCluIsSameNodeW (com\complus\dtc\shared\util\clusterutilbasic.cpp@596): MtxCluIsSameNodeW, pwszName2 != NULL`
- `0x180072548`: `MtxCluIsSameNodeW (com\complus\dtc\shared\util\clusterutilbasic.cpp@597): MtxCluIsSameNodeW, pIsSameNode != NULL`

## pseudocode

```c
__int64 __fastcall MtxCluIsSameNodeW(const unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  WCHAR *v3; // r15
  WCHAR *v4; // rsi
  unsigned int v8; // ebx
  int NetworkNameResourceW; // eax
  int v10; // eax
  __int64 v12; // [rsp+28h] [rbp-28h]
  HRESOURCE hResource; // [rsp+40h] [rbp-10h] BYREF
  HRESOURCE v14; // [rsp+48h] [rbp-8h] BYREF
  LPCWSTR lpString2; // [rsp+80h] [rbp+30h] BYREF
  LPCWSTR lpString1; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hResource = 0;
  v4 = 0;
  lpString1 = 0;
  v14 = 0;
  lpString2 = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"MtxCluIsSameNodeW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@595): MtxCluIsSameNodeW, pwszName1 != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluIsSameNodeW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@596): MtxCluIsSameNodeW, pwszName2 != NULL");
  if ( !a3 )
    DtcInternalErrorW(
      L"MtxCluIsSameNodeW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@597): MtxCluIsSameNodeW, pIsSameNode != NULL");
  v8 = 0;
  *a3 = 0;
  if ( _wcsicmp(a1, a2) )
  {
    if ( GetLocalClusterHandle() )
    {
      NetworkNameResourceW = MtxCluGetNetworkNameResourceW(a1, &hResource, (unsigned __int16 **)&lpString1);
      v3 = (WCHAR *)lpString1;
      v8 = NetworkNameResourceW;
      if ( NetworkNameResourceW >= 0 )
      {
        v10 = MtxCluGetNetworkNameResourceW(a2, &v14, (unsigned __int16 **)&lpString2);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v4 = (WCHAR *)lpString2;
          if ( !lstrcmpiW(v3, lpString2) )
            *a3 = 1;
        }
        else
        {
          LODWORD(v12) = v10;
          TraceStringInline(
            7,
            1,
            L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
            637,
            L"MtxCluIsSameNodeW",
            v12,
            L"MtxCluGetNetworkNameResourceW failed for %s",
            a2);
          v4 = (WCHAR *)lpString2;
        }
      }
      else
      {
        LODWORD(v12) = NetworkNameResourceW;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          629,
          L"MtxCluIsSameNodeW",
          v12,
          L"MtxCluGetNetworkNameResourceW failed for %s",
          a1);
      }
      if ( hResource )
        CloseClusterResource(hResource);
      if ( v14 )
        CloseClusterResource(v14);
    }
    else
    {
      TraceStringInline(
        7,
        4,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        618,
        L"MtxCluIsSameNodeW",
        0,
        L"Can't get the cluster handle, assuming the two names are NOT the same node");
    }
  }
  else
  {
    *a3 = 1;
  }
  CoTaskMemFree(v3);
  CoTaskMemFree(v4);
  return v8;
}

```

## disassembly

```asm
0x1800724e4  mov     [rsp-28h+arg_8], rbx
0x1800724e9  mov     [rsp-28h+arg_10], rsi
0x1800724ee  push    rbp
0x1800724ef  push    rdi
0x1800724f0  push    r12
0x1800724f2  push    r14
0x1800724f4  push    r15
0x1800724f6  mov     rbp, rsp
0x1800724f9  sub     rsp, 50h
0x1800724fd  xor     r15d, r15d
0x180072500  mov     [rbp+hResource], 0
0x180072508  xor     esi, esi
0x18007250a  mov     [rbp+lpString1], r15
0x18007250e  mov     [rbp+var_8], r15
0x180072512  mov     rdi, r8
0x180072515  mov     [rbp+lpString2], rsi
0x180072519  mov     r14, rdx
0x18007251c  mov     r12, rcx
0x18007251f  test    rcx, rcx
0x180072522  jnz     short loc_180072531
0x180072524  lea     rcx, aMtxcluissameno; "MtxCluIsSameNodeW (com\\complus\\dtc\\s"...
0x18007252b  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180072531  test    r14, r14
0x180072534  jnz     short loc_180072543
0x180072536  lea     rcx, aMtxcluissameno_1; "MtxCluIsSameNodeW (com\\complus\\dtc\\s"...
0x18007253d  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180072543  test    rdi, rdi
0x180072546  jnz     short loc_180072555
0x180072548  lea     rcx, aMtxcluissameno_2; "MtxCluIsSameNodeW (com\\complus\\dtc\\s"...
0x18007254f  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180072555  xor     ebx, ebx
0x180072557  mov     [r8], ebx
0x18007255a  call    cs:__imp__wcsicmp
0x180072560  test    eax, eax
0x180072562  jnz     short loc_18007256F
0x180072564  mov     dword ptr [rdi], 1
0x18007256a  jmp     loc_18007269B
0x18007256f  call    ?GetLocalClusterHandle@@YAPEAU_HCLUSTER@@XZ; GetLocalClusterHandle(void)
0x180072574  test    rax, rax
0x180072577  jnz     short loc_1800725B5
0x180072579  mov     edx, 4
0x18007257e  lea     rax, aCanTGetTheClus; "Can't get the cluster handle, assuming "...
0x180072585  mov     [rsp+50h+var_20], rax
0x18007258a  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180072591  lea     rax, aMtxcluissameno_0; "MtxCluIsSameNodeW"
0x180072598  mov     [rsp+50h+var_28], rbx
0x18007259d  mov     r9d, 26Ah
0x1800725a3  mov     [rsp+50h+var_30], rax
0x1800725a8  lea     ecx, [rdx+3]
0x1800725ab  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800725b0  jmp     loc_18007269B
0x1800725b5  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1800725b9  mov     rcx, r12; unsigned __int16 *
0x1800725bc  lea     rdx, [rbp+hResource]; struct _HRESOURCE **
0x1800725c0  call    ?MtxCluGetNetworkNameResourceW@@YAJPEBGPEAPEAU_HRESOURCE@@PEAPEAG@Z; MtxCluGetNetworkNameResourceW(ushort const *,_HRESOURCE * *,ushort * *)
0x1800725c5  mov     r15, [rbp+lpString1]
0x1800725c9  mov     ebx, eax
0x1800725cb  test    eax, eax
0x1800725cd  jns     short loc_18007260C
0x1800725cf  mov     [rsp+50h+var_18], r12
0x1800725d4  lea     rax, aMtxclugetnetwo_1; "MtxCluGetNetworkNameResourceW failed fo"...
0x1800725db  mov     [rsp+50h+var_20], rax
0x1800725e0  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800725e7  mov     edx, 1
0x1800725ec  mov     dword ptr [rsp+50h+var_28], ebx
0x1800725f0  lea     rax, aMtxcluissameno_0; "MtxCluIsSameNodeW"
0x1800725f7  mov     r9d, 275h
0x1800725fd  mov     [rsp+50h+var_30], rax
0x180072602  lea     ecx, [rdx+6]
0x180072605  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007260a  jmp     short loc_18007267D
0x18007260c  lea     r8, [rbp+lpString2]; unsigned __int16 **
0x180072610  mov     rcx, r14; unsigned __int16 *
0x180072613  lea     rdx, [rbp+var_8]; struct _HRESOURCE **
0x180072617  call    ?MtxCluGetNetworkNameResourceW@@YAJPEBGPEAPEAU_HRESOURCE@@PEAPEAG@Z; MtxCluGetNetworkNameResourceW(ushort const *,_HRESOURCE * *,ushort * *)
0x18007261c  mov     ebx, eax
0x18007261e  test    eax, eax
0x180072620  jns     short loc_180072663
0x180072622  mov     [rsp+50h+var_18], r14
0x180072627  lea     rax, aMtxclugetnetwo_1; "MtxCluGetNetworkNameResourceW failed fo"...
0x18007262e  mov     [rsp+50h+var_20], rax
0x180072633  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18007263a  mov     edx, 1
0x18007263f  mov     dword ptr [rsp+50h+var_28], ebx
0x180072643  lea     rax, aMtxcluissameno_0; "MtxCluIsSameNodeW"
0x18007264a  mov     r9d, 27Dh
0x180072650  mov     [rsp+50h+var_30], rax
0x180072655  lea     ecx, [rdx+6]
0x180072658  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007265d  mov     rsi, [rbp+lpString2]
0x180072661  jmp     short loc_18007267D
0x180072663  mov     rsi, [rbp+lpString2]
0x180072667  mov     rcx, r15; lpString1
0x18007266a  mov     rdx, rsi; lpString2
0x18007266d  call    cs:__imp_lstrcmpiW
0x180072673  test    eax, eax
0x180072675  jnz     short loc_18007267D
0x180072677  mov     dword ptr [rdi], 1
0x18007267d  mov     rcx, [rbp+hResource]; hResource
0x180072681  test    rcx, rcx
0x180072684  jz      short loc_18007268C
0x180072686  call    cs:__imp_CloseClusterResource
0x18007268c  mov     rcx, [rbp+var_8]; hResource
0x180072690  test    rcx, rcx
0x180072693  jz      short loc_18007269B
0x180072695  call    cs:__imp_CloseClusterResource
0x18007269b  mov     rcx, r15; pv
0x18007269e  call    cs:__imp_CoTaskMemFree
0x1800726a4  mov     rcx, rsi; pv
0x1800726a7  call    cs:__imp_CoTaskMemFree
0x1800726ad  lea     r11, [rsp+50h+var_s0]
0x1800726b2  mov     eax, ebx
0x1800726b4  mov     rbx, [r11+38h]
0x1800726b8  mov     rsi, [r11+40h]
0x1800726bc  mov     rsp, r11
0x1800726bf  pop     r15
0x1800726c1  pop     r14
0x1800726c3  pop     r12
0x1800726c5  pop     rdi
0x1800726c6  pop     rbp
0x1800726c7  retn
```
