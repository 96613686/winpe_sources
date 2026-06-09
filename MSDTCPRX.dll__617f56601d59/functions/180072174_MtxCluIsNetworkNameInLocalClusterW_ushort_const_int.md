# MtxCluIsNetworkNameInLocalClusterW(ushort const *,int *)

- ea: `0x180072174`
- end: `0x1800722bb`
- name: `?MtxCluIsNetworkNameInLocalClusterW@@YAJPEBGPEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(wchar_t *String1, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006709c`
- `0x180072424`

## callees

- `0x180003cf0`
- `0x1800092f4`
- `0x18000d5f4`
- `0x18000f8d0`
- `0x180072174`
- `0x1800722c4`
- `0x1800726d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800722a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800722a6`
- `msvcrt!_wcsicmp` at `0x180072226`
- `msvcrt!_wcsicmp` at `0x180072226`

## string_xrefs

- `0x1800721ec`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18007227f`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180072192`: `MtxCluIsNetworkNameInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@252): MtxCluIsNodeInLocalClusterW, pwszName != NULL`
- `0x1800721a4`: `MtxCluIsNetworkNameInLocalClusterW (com\complus\dtc\shared\util\clusterutilbasic.cpp@253): MtxCluIsNodeInLocalClusterW, pInLocalCluster != NULL`

## pseudocode

```c
__int64 __fastcall MtxCluIsNetworkNameInLocalClusterW(wchar_t *String1, int *a2)
{
  wchar_t *v2; // rsi
  __int64 v5; // rdx
  int IsVirtualServerInLocalClusterW; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  __int64 v10; // [rsp+28h] [rbp-30h]
  bool v11; // [rsp+60h] [rbp+8h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  String2 = 0;
  if ( !String1 )
    DtcInternalErrorW(
      L"MtxCluIsNetworkNameInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@252): MtxCluIsNodeInLoca"
       "lClusterW, pwszName != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluIsNetworkNameInLocalClusterW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@253): MtxCluIsNodeInLoca"
       "lClusterW, pInLocalCluster != NULL");
  *a2 = 0;
  v11 = 0;
  MtxCluIsClusterPresentNonAdmin(0, &v11);
  if ( v11 )
  {
    IsVirtualServerInLocalClusterW = MtxCluIsVirtualServerInLocalClusterW(String1, v5, a2);
    if ( IsVirtualServerInLocalClusterW >= 0 )
    {
      if ( *a2 )
        goto LABEL_16;
      IsVirtualServerInLocalClusterW = MtxCluIsNodeInLocalClusterW(String1, a2);
      if ( IsVirtualServerInLocalClusterW >= 0 )
        goto LABEL_16;
      v7 = L"MtxCluIsNetworkNameInLocalClusterW, MtxCluIsNodeInLocalClusterW failed";
      v8 = 286;
    }
    else
    {
      v7 = L"MtxCluIsNetworkNameInLocalClusterW, MtxCluIsVirtualServerInLocalClusterW failed";
      v8 = 275;
    }
    LODWORD(v10) = IsVirtualServerInLocalClusterW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      v8,
      L"MtxCluIsNetworkNameInLocalClusterW",
      v10,
      v7);
    goto LABEL_16;
  }
  IsVirtualServerInLocalClusterW = GetPhysicalNodeNameW((BYTE **)&String2);
  if ( IsVirtualServerInLocalClusterW >= 0 )
  {
    v2 = String2;
    if ( !_wcsicmp(String1, String2) )
      *a2 = 1;
  }
  else
  {
    LODWORD(v10) = IsVirtualServerInLocalClusterW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      262,
      L"MtxCluIsNetworkNameInLocalClusterW",
      v10,
      L"MtxCluIsNetworkNameInLocalClusterW, GetPhysicalNodeNameW failed");
    v2 = String2;
  }
LABEL_16:
  CoTaskMemFree(v2);
  return (unsigned int)IsVirtualServerInLocalClusterW;
}

```

## disassembly

```asm
0x180072174  mov     [rsp+arg_8], rbx
0x180072179  push    rbp
0x18007217a  push    rsi
0x18007217b  push    rdi
0x18007217c  sub     rsp, 40h
0x180072180  xor     esi, esi
0x180072182  mov     rdi, rdx
0x180072185  mov     [rsp+58h+String2], rsi
0x18007218a  mov     rbp, rcx
0x18007218d  test    rcx, rcx
0x180072190  jnz     short loc_18007219F
0x180072192  lea     rcx, aMtxcluisnetwor_0; "MtxCluIsNetworkNameInLocalClusterW (com"...
0x180072199  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007219f  test    rdi, rdi
0x1800721a2  jnz     short loc_1800721B1
0x1800721a4  lea     rcx, aMtxcluisnetwor; "MtxCluIsNetworkNameInLocalClusterW (com"...
0x1800721ab  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800721b1  mov     [rdx], esi
0x1800721b3  xor     ecx, ecx; unsigned __int16 *
0x1800721b5  lea     rdx, [rsp+58h+arg_0]; bool *
0x1800721ba  mov     [rsp+58h+arg_0], sil
0x1800721bf  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x1800721c4  cmp     [rsp+58h+arg_0], sil
0x1800721c9  jnz     short loc_180072238
0x1800721cb  lea     rcx, [rsp+58h+String2]; unsigned __int16 **
0x1800721d0  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x1800721d5  mov     ebx, eax
0x1800721d7  test    eax, eax
0x1800721d9  jns     short loc_18007221B
0x1800721db  mov     edx, 1
0x1800721e0  lea     rax, aMtxcluisnetwor_2; "MtxCluIsNetworkNameInLocalClusterW, Get"...
0x1800721e7  mov     [rsp+58h+var_28], rax
0x1800721ec  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800721f3  lea     rax, aMtxcluisnetwor_1; "MtxCluIsNetworkNameInLocalClusterW"
0x1800721fa  mov     dword ptr [rsp+58h+var_30], ebx
0x1800721fe  mov     r9d, 106h
0x180072204  mov     [rsp+58h+var_38], rax
0x180072209  lea     ecx, [rdx+6]
0x18007220c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180072211  mov     rsi, [rsp+58h+String2]
0x180072216  jmp     loc_1800722A3
0x18007221b  mov     rsi, [rsp+58h+String2]
0x180072220  mov     rcx, rbp; String1
0x180072223  mov     rdx, rsi; String2
0x180072226  call    cs:__imp__wcsicmp
0x18007222c  test    eax, eax
0x18007222e  jnz     short loc_1800722A3
0x180072230  mov     dword ptr [rdi], 1
0x180072236  jmp     short loc_1800722A3
0x180072238  mov     r8, rdi; int *
0x18007223b  mov     rcx, rbp; String2
0x18007223e  call    ?MtxCluIsVirtualServerInLocalClusterW@@YAJPEBGHPEAH@Z; MtxCluIsVirtualServerInLocalClusterW(ushort const *,int,int *)
0x180072243  mov     ebx, eax
0x180072245  test    eax, eax
0x180072247  jns     short loc_180072258
0x180072249  lea     rax, aMtxcluisnetwor_4; "MtxCluIsNetworkNameInLocalClusterW, Mtx"...
0x180072250  mov     r9d, 113h
0x180072256  jmp     short loc_18007227A
0x180072258  cmp     [rdi], esi
0x18007225a  jnz     short loc_1800722A3
0x18007225c  mov     rdx, rdi; int *
0x18007225f  mov     rcx, rbp; String2
0x180072262  call    ?MtxCluIsNodeInLocalClusterW@@YAJPEBGPEAH@Z; MtxCluIsNodeInLocalClusterW(ushort const *,int *)
0x180072267  mov     ebx, eax
0x180072269  test    eax, eax
0x18007226b  jns     short loc_1800722A3
0x18007226d  lea     rax, aMtxcluisnetwor_3; "MtxCluIsNetworkNameInLocalClusterW, Mtx"...
0x180072274  mov     r9d, 11Eh
0x18007227a  mov     [rsp+58h+var_28], rax
0x18007227f  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180072286  mov     edx, 1
0x18007228b  mov     dword ptr [rsp+58h+var_30], ebx
0x18007228f  lea     rax, aMtxcluisnetwor_1; "MtxCluIsNetworkNameInLocalClusterW"
0x180072296  mov     [rsp+58h+var_38], rax
0x18007229b  lea     ecx, [rdx+6]
0x18007229e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800722a3  mov     rcx, rsi; pv
0x1800722a6  call    cs:__imp_CoTaskMemFree
0x1800722ac  mov     eax, ebx
0x1800722ae  mov     rbx, [rsp+58h+arg_8]
0x1800722b3  add     rsp, 40h
0x1800722b7  pop     rdi
0x1800722b8  pop     rsi
0x1800722b9  pop     rbp
0x1800722ba  retn
```
