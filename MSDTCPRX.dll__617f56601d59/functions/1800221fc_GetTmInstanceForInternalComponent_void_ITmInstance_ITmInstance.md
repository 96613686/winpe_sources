# GetTmInstanceForInternalComponent(void *,ITmInstance * *,ITmInstance * *)

- ea: `0x1800221fc`
- end: `0x180022458`
- name: `?GetTmInstanceForInternalComponent@@YAJPEAXPEAPEAUITmInstance@@1@Z`
- size: `604`
- prototype: `__int64 __fastcall(void *, struct ITmInstance **, struct ITmInstance **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023548`

## callees

- `0x180003cf0`
- `0x180006214`
- `0x1800221fc`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222fb`
- `RPCRT4!UuidToStringW` at `0x180022362`
- `RPCRT4!UuidToStringW` at `0x180022362`
- `RPCRT4!RpcStringFreeW` at `0x180022317`
- `RPCRT4!RpcStringFreeW` at `0x180022317`
- `MTXCLU!MtxCluGetNameFromResourceIdString` at `0x180022396`
- `MTXCLU!MtxCluGetNameFromResourceIdString` at `0x180022396`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x18002240d`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x18002240d`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x1800223cf`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x1800223cf`

## string_xrefs

- `0x180022278`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x18002242e`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x1800222aa`: `CreateLocalTmInstance failed`
- `0x180022422`: `MtxCluCreateClusterProxyTmInstance failed`
- `0x180022258`: `Invalid argument - i_pvConfigParams`
- `0x18002226c`: `GetTmInstanceForInternalComponent`
- `0x180022435`: `GetTmInstanceForInternalComponent`

## pseudocode

```c
__int64 __fastcall GetTmInstanceForInternalComponent(char *a1, struct ITmInstance **a2, struct ITmInstance **a3)
{
  __int64 v6; // r9
  int NameFromResourceIdString; // ebx
  struct ITmInstance *v8; // rcx
  __int64 v10; // [rsp+28h] [rbp-D8h]
  const wchar_t *v11; // [rsp+30h] [rbp-D0h]
  struct ITmInstance *v12; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  RPC_WSTR String[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[528]; // [rsp+70h] [rbp-90h] BYREF

  v12 = 0;
  pv = 0;
  String[0] = 0;
  if ( !a1 )
  {
    v6 = 1299;
LABEL_3:
    v11 = L"Invalid argument - i_pvConfigParams";
    NameFromResourceIdString = -2147024809;
    LODWORD(v10) = -2147024809;
    goto LABEL_4;
  }
  if ( *(_DWORD *)a1 < 2u )
  {
    v6 = 1308;
    goto LABEL_3;
  }
  NameFromResourceIdString = CreateLocalTmInstance(0, &v12);
  if ( NameFromResourceIdString >= 0 )
  {
    if ( *((_DWORD *)a1 + 2) )
    {
      if ( *((_DWORD *)a1 + 2) == 1 )
      {
        if ( UuidToStringW((const UUID *)(a1 + 12), String) )
        {
          NameFromResourceIdString = -2147024882;
          v11 = L"UuidToString failed";
          v6 = 1330;
          LODWORD(v10) = -2147024882;
          goto LABEL_4;
        }
        NameFromResourceIdString = MtxCluGetNameFromResourceIdString(String[0], &pv);
        if ( NameFromResourceIdString < 0 )
        {
          LODWORD(v10) = NameFromResourceIdString;
          TraceStringInline(
            0,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            1337,
            L"GetTmInstanceForInternalComponent",
            v10,
            L"MtxCluGetNameFromResourceIdString failed");
          goto LABEL_13;
        }
        NameFromResourceIdString = MtxCluGetDTCVirtualServerNameW(0, pv, v16, 261);
        if ( NameFromResourceIdString < 0 )
        {
          v6 = 1348;
          v11 = L"MtxCluGetDTCVirtualServerNameW failed";
          LODWORD(v10) = NameFromResourceIdString;
          goto LABEL_4;
        }
        v15 = *(_OWORD *)(a1 + 12);
        NameFromResourceIdString = MtxCluCreateClusterProxyTmInstance(v16, &v15, a2);
        if ( NameFromResourceIdString < 0 )
        {
          LODWORD(v10) = NameFromResourceIdString;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            1359,
            L"GetTmInstanceForInternalComponent",
            v10,
            L"MtxCluCreateClusterProxyTmInstance failed");
          goto LABEL_13;
        }
      }
    }
    else
    {
      v8 = v12;
      *a2 = v12;
      (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    *a3 = v12;
    v12 = 0;
    goto LABEL_13;
  }
  v6 = 1315;
  v11 = L"CreateLocalTmInstance failed";
  LODWORD(v10) = NameFromResourceIdString;
LABEL_4:
  TraceStringInline(
    0,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
    v6,
    L"GetTmInstanceForInternalComponent",
    v10,
    v11);
LABEL_13:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( String[0] )
    RpcStringFreeW(String);
  if ( v12 )
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)NameFromResourceIdString;
}

```

## disassembly

```asm
0x1800221fc  push    rbp
0x1800221fe  push    rbx
0x1800221ff  push    rsi
0x180022200  push    r14
0x180022202  push    r15
0x180022204  lea     rbp, [rsp-190h]
0x18002220c  sub     rsp, 290h
0x180022213  mov     rax, cs:__security_cookie
0x18002221a  xor     rax, rsp
0x18002221d  mov     [rbp+1B0h+var_30], rax
0x180022224  mov     [rsp+2B0h+var_270], 0
0x18002222d  mov     r15, r8
0x180022230  mov     [rsp+2B0h+pv], 0
0x180022239  mov     r14, rdx
0x18002223c  mov     [rsp+2B0h+String], 0
0x180022245  mov     rsi, rcx
0x180022248  test    rcx, rcx
0x18002224b  jnz     short loc_18002228B
0x18002224d  mov     r9d, 513h
0x180022253  mov     eax, 80070057h
0x180022258  lea     rcx, aInvalidArgumen_10; "Invalid argument - i_pvConfigParams"
0x18002225f  mov     [rsp+2B0h+var_280], rcx
0x180022264  mov     ebx, eax
0x180022266  mov     dword ptr [rsp+2B0h+var_288], eax
0x18002226a  xor     ecx, ecx
0x18002226c  lea     rax, aGettminstancef_6; "GetTmInstanceForInternalComponent"
0x180022273  mov     edx, 1
0x180022278  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18002227f  mov     [rsp+2B0h+var_290], rax
0x180022284  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022289  jmp     short loc_1800222F1
0x18002228b  cmp     dword ptr [rcx], 2
0x18002228e  jnb     short loc_180022298
0x180022290  mov     r9d, 51Ch
0x180022296  jmp     short loc_180022253
0x180022298  lea     rdx, [rsp+2B0h+var_270]; struct ITmInstance **
0x18002229d  xor     ecx, ecx; unsigned __int16 *
0x18002229f  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x1800222a4  mov     ebx, eax
0x1800222a6  test    eax, eax
0x1800222a8  jns     short loc_1800222C2
0x1800222aa  lea     rax, aCreatelocaltmi_1; "CreateLocalTmInstance failed"
0x1800222b1  mov     r9d, 523h
0x1800222b7  mov     [rsp+2B0h+var_280], rax
0x1800222bc  mov     dword ptr [rsp+2B0h+var_288], ebx
0x1800222c0  jmp     short loc_18002226A
0x1800222c2  cmp     dword ptr [rsi+8], 0
0x1800222c6  jnz     loc_180022353
0x1800222cc  mov     rcx, [rsp+2B0h+var_270]
0x1800222d1  mov     [r14], rcx
0x1800222d4  mov     rax, [rcx]
0x1800222d7  mov     rax, [rax+8]
0x1800222db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222e0  mov     rax, [rsp+2B0h+var_270]
0x1800222e5  mov     [r15], rax
0x1800222e8  mov     [rsp+2B0h+var_270], 0
0x1800222f1  mov     rcx, [rsp+2B0h+pv]; pv
0x1800222f6  test    rcx, rcx
0x1800222f9  jz      short loc_18002230A
0x1800222fb  call    cs:__imp_CoTaskMemFree
0x180022301  mov     [rsp+2B0h+pv], 0
0x18002230a  cmp     [rsp+2B0h+String], 0
0x180022310  jz      short loc_18002231D
0x180022312  lea     rcx, [rsp+2B0h+String]; String
0x180022317  call    cs:__imp_RpcStringFreeW
0x18002231d  mov     rcx, [rsp+2B0h+var_270]
0x180022322  test    rcx, rcx
0x180022325  jz      short loc_180022333
0x180022327  mov     rax, [rcx]
0x18002232a  mov     rax, [rax+10h]
0x18002232e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022333  mov     eax, ebx
0x180022335  mov     rcx, [rbp+1B0h+var_30]
0x18002233c  xor     rcx, rsp; StackCookie
0x18002233f  call    __security_check_cookie
0x180022344  add     rsp, 290h
0x18002234b  pop     r15
0x18002234d  pop     r14
0x18002234f  pop     rsi
0x180022350  pop     rbx
0x180022351  pop     rbp
0x180022352  retn
0x180022353  cmp     dword ptr [rsi+8], 1
0x180022357  jnz     short loc_1800222E0
0x180022359  lea     rdx, [rsp+2B0h+String]; StringUuid
0x18002235e  lea     rcx, [rsi+0Ch]; Uuid
0x180022362  call    cs:__imp_UuidToStringW
0x180022368  test    eax, eax
0x18002236a  jz      short loc_18002238C
0x18002236c  lea     rax, aUuidtostringFa_0; "UuidToString failed"
0x180022373  mov     ebx, 8007000Eh
0x180022378  mov     [rsp+2B0h+var_280], rax
0x18002237d  mov     r9d, 532h
0x180022383  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180022387  jmp     loc_18002226A
0x18002238c  mov     rcx, [rsp+2B0h+String]
0x180022391  lea     rdx, [rsp+2B0h+pv]
0x180022396  call    cs:__imp_MtxCluGetNameFromResourceIdString
0x18002239c  xor     ecx, ecx
0x18002239e  mov     ebx, eax
0x1800223a0  test    eax, eax
0x1800223a2  jns     short loc_1800223BF
0x1800223a4  lea     rax, aMtxclugetnamef; "MtxCluGetNameFromResourceIdString faile"...
0x1800223ab  mov     r9d, 539h
0x1800223b1  mov     [rsp+2B0h+var_280], rax
0x1800223b6  mov     dword ptr [rsp+2B0h+var_288], ebx
0x1800223ba  jmp     loc_18002226C
0x1800223bf  mov     rdx, [rsp+2B0h+pv]
0x1800223c4  lea     r8, [rsp+2B0h+var_240]
0x1800223c9  mov     r9d, 105h
0x1800223cf  call    cs:__imp_MtxCluGetDTCVirtualServerNameW
0x1800223d5  mov     ebx, eax
0x1800223d7  test    eax, eax
0x1800223d9  jns     short loc_1800223F6
0x1800223db  lea     rax, aMtxclugetdtcvi; "MtxCluGetDTCVirtualServerNameW failed"
0x1800223e2  mov     r9d, 544h
0x1800223e8  mov     [rsp+2B0h+var_280], rax
0x1800223ed  mov     dword ptr [rsp+2B0h+var_288], ebx
0x1800223f1  jmp     loc_18002226A
0x1800223f6  movups  xmm0, xmmword ptr [rsi+0Ch]
0x1800223fa  mov     r8, r14
0x1800223fd  lea     rdx, [rsp+2B0h+var_250]
0x180022402  lea     rcx, [rsp+2B0h+var_240]
0x180022407  movdqu  [rsp+2B0h+var_250], xmm0
0x18002240d  call    cs:__imp_MtxCluCreateClusterProxyTmInstance
0x180022413  mov     ebx, eax
0x180022415  test    eax, eax
0x180022417  jns     loc_1800222E0
0x18002241d  mov     edx, 1
0x180022422  lea     rax, aMtxclucreatecl_0; "MtxCluCreateClusterProxyTmInstance fail"...
0x180022429  mov     [rsp+2B0h+var_280], rax
0x18002242e  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180022435  lea     rax, aGettminstancef_6; "GetTmInstanceForInternalComponent"
0x18002243c  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180022440  mov     r9d, 54Fh
0x180022446  mov     [rsp+2B0h+var_290], rax
0x18002244b  lea     ecx, [rdx+0Eh]
0x18002244e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022453  jmp     loc_1800222F1
```
