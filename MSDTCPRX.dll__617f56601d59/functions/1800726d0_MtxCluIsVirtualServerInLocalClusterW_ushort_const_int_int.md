# MtxCluIsVirtualServerInLocalClusterW(ushort const *,int,int *)

- ea: `0x1800726d0`
- end: `0x1800727fe`
- name: `?MtxCluIsVirtualServerInLocalClusterW@@YAJPEBGHPEAH@Z`
- size: `302`
- prototype: `__int64 __fastcall(wchar_t *String2, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072174`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180013694`
- `0x1800726d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800727c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800727e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800727c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800727e1`
- `msvcrt!_wcsicmp` at `0x1800727a3`
- `msvcrt!_wcsicmp` at `0x1800727a3`

## string_xrefs

- `0x180072754`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180072701`: `MtxCluIsVirtualServerInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@927): MtxCluIsVirtualServerInLocalClusterW, pwszVirtualServerName != NULL`
- `0x180072713`: `MtxCluIsVirtualServerInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@928): MtxCluIsVirtualServerInLocalClusterW, pbVirtualServerInLocalCluster != NULL`

## pseudocode

```c
__int64 __fastcall MtxCluIsVirtualServerInLocalClusterW(wchar_t *String2, __int64 a2, int *a3)
{
  int VirtualServersW; // eax
  const wchar_t **v6; // rdi
  unsigned int v7; // r14d
  const wchar_t *v8; // rax
  __int64 v9; // r9
  __int64 i; // rbx
  __int64 j; // rsi
  __int64 v13; // [rsp+28h] [rbp-30h]
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  pv = 0;
  if ( !String2 )
    DtcInternalErrorW(
      L"MtxCluIsVirtualServerInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@927): MtxCluIsVirtualS"
       "erverInLocalClusterW, pwszVirtualServerName != NULL");
  if ( !a3 )
    DtcInternalErrorW(
      L"MtxCluIsVirtualServerInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@928): MtxCluIsVirtualS"
       "erverInLocalClusterW, pbVirtualServerInLocalCluster != NULL");
  *a3 = 0;
  VirtualServersW = MtxCluGetVirtualServersW((unsigned int)String2, (unsigned __int16 ***)&pv, &v15);
  v6 = (const wchar_t **)pv;
  v7 = VirtualServersW;
  if ( VirtualServersW < 0 )
  {
    v8 = L"MtxCluIsVirtualServerInLocalClusterW, MtxCluGetVirtualServersW failed";
    v9 = 935;
LABEL_7:
    LODWORD(v13) = v7;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      v9,
      L"MtxCluIsVirtualServerInLocalClusterW",
      v13,
      v8);
    goto LABEL_15;
  }
  if ( !v15 )
  {
    v7 = 0;
    v8 = L"MtxCluIsVirtualServerInLocalClusterW, MtxCluGetVirtualServersW returned 0 number of nodes";
    v9 = 945;
    goto LABEL_7;
  }
  for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
  {
    if ( !_wcsicmp(v6[i], String2) )
    {
      *a3 = 1;
      break;
    }
  }
LABEL_15:
  if ( v6 )
  {
    for ( j = 0; (unsigned int)j < v15; j = (unsigned int)(j + 1) )
    {
      CoTaskMemFree((LPVOID)v6[j]);
      v6[j] = 0;
    }
  }
  CoTaskMemFree(v6);
  return v7;
}

```

## disassembly

```asm
0x1800726d0  mov     rax, rsp
0x1800726d3  mov     [rax+18h], rbx
0x1800726d7  mov     [rax+20h], rsi
0x1800726db  mov     [rax+10h], edx
0x1800726de  push    rdi
0x1800726df  push    r14
0x1800726e1  push    r15
0x1800726e3  sub     rsp, 40h
0x1800726e7  mov     dword ptr [rax+10h], 0
0x1800726ee  mov     rsi, r8
0x1800726f1  mov     qword ptr [rax+8], 0
0x1800726f9  mov     r15, rcx
0x1800726fc  test    rcx, rcx
0x1800726ff  jnz     short loc_18007270E
0x180072701  lea     rcx, aMtxcluisvirtua_0; "MtxCluIsVirtualServerInLocalClusterW (c"...
0x180072708  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007270e  test    rsi, rsi
0x180072711  jnz     short loc_180072720
0x180072713  lea     rcx, aMtxcluisvirtua_1; "MtxCluIsVirtualServerInLocalClusterW (c"...
0x18007271a  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180072720  mov     dword ptr [r8], 0
0x180072727  lea     rdx, [rsp+58h+pv]; unsigned __int16 ***
0x18007272c  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x180072731  call    ?MtxCluGetVirtualServersW@@YAJHPEAPEAPEAGPEAK@Z; MtxCluGetVirtualServersW(int,ushort * * *,ulong *)
0x180072736  mov     rdi, [rsp+58h+pv]
0x18007273b  mov     r14d, eax
0x18007273e  test    eax, eax
0x180072740  jns     short loc_18007277B
0x180072742  lea     rax, aMtxcluisvirtua; "MtxCluIsVirtualServerInLocalClusterW, M"...
0x180072749  mov     r9d, 3A7h
0x18007274f  mov     [rsp+58h+var_28], rax
0x180072754  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18007275b  mov     edx, 1
0x180072760  mov     dword ptr [rsp+58h+var_30], r14d
0x180072765  lea     rax, aMtxcluisvirtua_3; "MtxCluIsVirtualServerInLocalClusterW"
0x18007276c  mov     [rsp+58h+var_38], rax
0x180072771  lea     ecx, [rdx+6]
0x180072774  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180072779  jmp     short loc_1800727B7
0x18007277b  cmp     [rsp+58h+arg_8], 0
0x180072780  jnz     short loc_180072794
0x180072782  xor     r14d, r14d
0x180072785  lea     rax, aMtxcluisvirtua_2; "MtxCluIsVirtualServerInLocalClusterW, M"...
0x18007278c  mov     r9d, 3B1h
0x180072792  jmp     short loc_18007274F
0x180072794  xor     ebx, ebx
0x180072796  cmp     ebx, [rsp+58h+arg_8]
0x18007279a  jnb     short loc_1800727B7
0x18007279c  mov     rcx, [rdi+rbx*8]; String1
0x1800727a0  mov     rdx, r15; String2
0x1800727a3  call    cs:__imp__wcsicmp
0x1800727a9  test    eax, eax
0x1800727ab  jz      short loc_1800727B1
0x1800727ad  inc     ebx
0x1800727af  jmp     short loc_180072796
0x1800727b1  mov     dword ptr [rsi], 1
0x1800727b7  test    rdi, rdi
0x1800727ba  jz      short loc_1800727DE
0x1800727bc  xor     esi, esi
0x1800727be  cmp     [rsp+58h+arg_8], esi
0x1800727c2  jbe     short loc_1800727DE
0x1800727c4  mov     rcx, [rdi+rsi*8]; pv
0x1800727c8  call    cs:__imp_CoTaskMemFree
0x1800727ce  mov     qword ptr [rdi+rsi*8], 0
0x1800727d6  inc     esi
0x1800727d8  cmp     esi, [rsp+58h+arg_8]
0x1800727dc  jb      short loc_1800727C4
0x1800727de  mov     rcx, rdi; pv
0x1800727e1  call    cs:__imp_CoTaskMemFree
0x1800727e7  mov     rbx, [rsp+58h+arg_10]
0x1800727ec  mov     eax, r14d
0x1800727ef  mov     rsi, [rsp+58h+arg_18]
0x1800727f4  add     rsp, 40h
0x1800727f8  pop     r15
0x1800727fa  pop     r14
0x1800727fc  pop     rdi
0x1800727fd  retn
```
