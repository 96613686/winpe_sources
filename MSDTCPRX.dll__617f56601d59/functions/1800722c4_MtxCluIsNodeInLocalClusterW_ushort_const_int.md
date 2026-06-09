# MtxCluIsNodeInLocalClusterW(ushort const *,int *)

- ea: `0x1800722c4`
- end: `0x18007241c`
- name: `?MtxCluIsNodeInLocalClusterW@@YAJPEBGPEAH@Z`
- size: `344`
- prototype: `__int64 __fastcall(wchar_t *String2, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072174`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180018188`
- `0x1800722c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800723eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800723eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072402`
- `msvcrt!_wcsicmp` at `0x1800723c7`
- `msvcrt!_wcsicmp` at `0x1800723c7`

## string_xrefs

- `0x180072347`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18007238d`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800722f0`: `MtxCluIsNodeInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@723): MtxCluIsNodeInLocalClusterW, pwszNodeName != NULL`
- `0x180072302`: `MtxCluIsNodeInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@724): MtxCluIsNodeInLocalClusterW, pbNodeInLocalCluster != NULL`

## pseudocode

```c
__int64 __fastcall MtxCluIsNodeInLocalClusterW(wchar_t *String2, int *a2)
{
  int NodesW; // eax
  const wchar_t **v5; // rsi
  unsigned int v6; // r14d
  unsigned int v7; // edi
  __int64 v8; // r15
  __int64 i; // rbp
  __int64 v11; // [rsp+28h] [rbp-40h]
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+18h] BYREF

  v12 = 0;
  pv = 0;
  if ( !String2 )
    DtcInternalErrorW(
      L"MtxCluIsNodeInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@723): MtxCluIsNodeInLocalCluste"
       "rW, pwszNodeName != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluIsNodeInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@724): MtxCluIsNodeInLocalCluste"
       "rW, pbNodeInLocalCluster != NULL");
  *a2 = 0;
  NodesW = MtxCluGetNodesW((unsigned __int16 ***)&pv, &v12);
  v5 = (const wchar_t **)pv;
  v6 = NodesW;
  if ( NodesW >= 0 )
  {
    v7 = v12;
    if ( v12 )
    {
      while ( 1 )
      {
        v8 = v7 - 1;
        if ( !_wcsicmp(v5[v8], String2) )
          break;
        --v7;
        if ( !(_DWORD)v8 )
          goto LABEL_13;
      }
      *a2 = 1;
    }
    else
    {
      v6 = -2147467259;
      LODWORD(v11) = -2147467259;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        737,
        L"MtxCluIsNodeInLocalClusterW",
        v11,
        L"MtxCluIsNodeInLocalClusterW, MtxCluGetNodesW returned 0 number of nodes");
    }
  }
  else
  {
    LODWORD(v11) = NodesW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      731,
      L"MtxCluIsNodeInLocalClusterW",
      v11,
      L"MtxCluIsNodeInLocalClusterW, MtxCluGetNodesW failed");
    v7 = v12;
  }
LABEL_13:
  if ( v5 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree((LPVOID)v5[i]);
      v5[i] = 0;
    }
  }
  CoTaskMemFree(v5);
  return v6;
}

```

## disassembly

```asm
0x1800722c4  mov     rax, rsp
0x1800722c7  mov     [rax+10h], rbx
0x1800722cb  push    rbp
0x1800722cc  push    rsi
0x1800722cd  push    rdi
0x1800722ce  push    r14
0x1800722d0  push    r15
0x1800722d2  sub     rsp, 40h
0x1800722d6  mov     dword ptr [rax+8], 0
0x1800722dd  mov     rbx, rdx
0x1800722e0  mov     qword ptr [rax+18h], 0
0x1800722e8  mov     rbp, rcx
0x1800722eb  test    rcx, rcx
0x1800722ee  jnz     short loc_1800722FD
0x1800722f0  lea     rcx, aMtxcluisnodein_2; "MtxCluIsNodeInLocalClusterW (com\\compl"...
0x1800722f7  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800722fd  test    rbx, rbx
0x180072300  jnz     short loc_18007230F
0x180072302  lea     rcx, aMtxcluisnodein; "MtxCluIsNodeInLocalClusterW (com\\compl"...
0x180072309  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007230f  mov     dword ptr [rdx], 0
0x180072315  lea     rcx, [rsp+68h+pv]; unsigned __int16 ***
0x18007231d  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x180072322  call    ?MtxCluGetNodesW@@YAJPEAPEAPEAGPEAK@Z; MtxCluGetNodesW(ushort * * *,ulong *)
0x180072327  mov     rsi, [rsp+68h+pv]
0x18007232f  mov     r14d, eax
0x180072332  test    eax, eax
0x180072334  jns     short loc_180072373
0x180072336  mov     edx, 1
0x18007233b  lea     rax, aMtxcluisnodein_3; "MtxCluIsNodeInLocalClusterW, MtxCluGetN"...
0x180072342  mov     [rsp+68h+var_38], rax
0x180072347  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18007234e  lea     rax, aMtxcluisnodein_1; "MtxCluIsNodeInLocalClusterW"
0x180072355  mov     dword ptr [rsp+68h+var_40], r14d
0x18007235a  mov     r9d, 2DBh
0x180072360  mov     [rsp+68h+var_48], rax
0x180072365  lea     ecx, [rdx+6]
0x180072368  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007236d  mov     edi, [rsp+68h+arg_0]
0x180072371  jmp     short loc_1800723DC
0x180072373  mov     edi, [rsp+68h+arg_0]
0x180072377  test    edi, edi
0x180072379  jnz     short loc_1800723BC
0x18007237b  lea     rax, aMtxcluisnodein_0; "MtxCluIsNodeInLocalClusterW, MtxCluGetN"...
0x180072382  mov     r14d, 80004005h
0x180072388  mov     [rsp+68h+var_38], rax
0x18007238d  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180072394  lea     rax, aMtxcluisnodein_1; "MtxCluIsNodeInLocalClusterW"
0x18007239b  mov     dword ptr [rsp+68h+var_40], r14d
0x1800723a0  mov     r9d, 2E1h
0x1800723a6  mov     [rsp+68h+var_48], rax
0x1800723ab  lea     edx, [rdi+1]
0x1800723ae  lea     ecx, [rdi+7]
0x1800723b1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800723b6  jmp     short loc_1800723DC
0x1800723b8  test    edi, edi
0x1800723ba  jz      short loc_1800723DC
0x1800723bc  lea     r15d, [rdi-1]
0x1800723c0  mov     rdx, rbp; String2
0x1800723c3  mov     rcx, [rsi+r15*8]; String1
0x1800723c7  call    cs:__imp__wcsicmp
0x1800723cd  test    eax, eax
0x1800723cf  jz      short loc_1800723D6
0x1800723d1  mov     edi, r15d
0x1800723d4  jmp     short loc_1800723B8
0x1800723d6  mov     dword ptr [rbx], 1
0x1800723dc  test    rsi, rsi
0x1800723df  jz      short loc_1800723FF
0x1800723e1  xor     ebp, ebp
0x1800723e3  test    edi, edi
0x1800723e5  jz      short loc_1800723FF
0x1800723e7  mov     rcx, [rsi+rbp*8]; pv
0x1800723eb  call    cs:__imp_CoTaskMemFree
0x1800723f1  mov     qword ptr [rsi+rbp*8], 0
0x1800723f9  inc     ebp
0x1800723fb  cmp     ebp, edi
0x1800723fd  jb      short loc_1800723E7
0x1800723ff  mov     rcx, rsi; pv
0x180072402  call    cs:__imp_CoTaskMemFree
0x180072408  mov     rbx, [rsp+68h+arg_8]
0x18007240d  mov     eax, r14d
0x180072410  add     rsp, 40h
0x180072414  pop     r15
0x180072416  pop     r14
0x180072418  pop     rdi
0x180072419  pop     rsi
0x18007241a  pop     rbp
0x18007241b  retn
```
