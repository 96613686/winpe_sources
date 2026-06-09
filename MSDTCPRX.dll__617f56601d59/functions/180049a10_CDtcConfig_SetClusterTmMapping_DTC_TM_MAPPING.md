# CDtcConfig::SetClusterTmMapping(_DTC_TM_MAPPING)

- ea: `0x180049a10`
- end: `0x180049c9b`
- name: `?SetClusterTmMapping@CDtcConfig@@UEAAJU_DTC_TM_MAPPING@@@Z`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000f8d0`
- `0x180049a10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c4b`
- `MTXCLU!MtxCluSetClusterTmMapping` at `0x180049b88`
- `MTXCLU!MtxCluSetClusterTmMapping` at `0x180049b88`

## string_xrefs

- `0x180049a61`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049b19`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049be6`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049c17`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049c62`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049a42`: `CDtcConfig::SetClusterTmMapping`
- `0x180049b0d`: `CDtcConfig::SetClusterTmMapping`
- `0x180049b8e`: `CDtcConfig::SetClusterTmMapping`
- `0x180049bda`: `CDtcConfig::SetClusterTmMapping`
- `0x180049c3c`: `CDtcConfig::SetClusterTmMapping`
- `0x180049aaa`: `Service`
- `0x180049abc`: `ComplusApp`

## pseudocode

```c
__int64 __fastcall CDtcConfig::SetClusterTmMapping(__int64 a1, __int64 a2)
{
  __int64 v4; // r15
  __int64 v5; // r12
  int v6; // ecx
  const wchar_t *v7; // rbp
  int v8; // ecx
  const wchar_t *v9; // r14
  int v10; // ebx
  const wchar_t *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r9
  const wchar_t *v14; // rcx
  __int64 v16; // [rsp+28h] [rbp-40h]
  int v17; // [rsp+38h] [rbp-30h]
  bool v18; // [rsp+78h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+18h] BYREF

  pv = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    182,
    L"CDtcConfig::SetClusterTmMapping",
    0,
    L"In");
  if ( !*(_QWORD *)a2 || (v4 = *(_QWORD *)(a2 + 24)) == 0 || (v5 = *(_QWORD *)(a2 + 32)) == 0 )
  {
    LODWORD(v16) = -2147024809;
    v10 = -2147024809;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      189,
      L"CDtcConfig::SetClusterTmMapping",
      v16,
      L"Invalid arguments.");
    goto LABEL_25;
  }
  v6 = *(_DWORD *)(a2 + 8);
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v7 = L"Service";
    }
    else
    {
      if ( v6 != 2 )
      {
        v17 = *(_DWORD *)(a2 + 8);
        v13 = 208;
        v14 = L"Invalid argument: tmMapping.MappingType %d";
        goto LABEL_23;
      }
      v7 = L"ComplusApp";
    }
  }
  else
  {
    v7 = L"Exe";
  }
  v8 = *(_DWORD *)(a2 + 16);
  if ( !v8 )
  {
    v9 = L"AppId";
    goto LABEL_14;
  }
  if ( v8 != 1 )
  {
    v17 = *(_DWORD *)(a2 + 16);
    v13 = 223;
    v14 = L"Invalid argument: tmMapping.dwIdType %d";
LABEL_23:
    LODWORD(v16) = -2147024809;
    v10 = -2147024809;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v13,
      L"CDtcConfig::SetClusterTmMapping",
      v16,
      v14,
      v17);
    goto LABEL_25;
  }
  v9 = L"Name";
LABEL_14:
  v10 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(a1 + 16) + 40LL))(*(_QWORD *)(a1 + 16), &pv);
  if ( v10 >= 0 )
  {
    v18 = 0;
    MtxCluIsClusterPresentNonAdmin(0, &v18);
    if ( v18 )
    {
      v10 = MtxCluSetClusterTmMapping(pv, v7, *(_QWORD *)a2, v9, v4, *(_DWORD *)(a2 + 12), v5);
      if ( v10 >= 0 )
        goto LABEL_25;
      v11 = L"MtxCluSetClusterTmMapping failed";
      v12 = 250;
    }
    else
    {
      v10 = -2147019860;
      v11 = L"Not a cluster node.";
      v12 = 237;
    }
  }
  else
  {
    v11 = L"GetHostName failed";
    v12 = 230;
  }
  LODWORD(v16) = v10;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    v12,
    L"CDtcConfig::SetClusterTmMapping",
    v16,
    v11);
LABEL_25:
  CoTaskMemFree(pv);
  LODWORD(v16) = v10;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    256,
    L"CDtcConfig::SetClusterTmMapping",
    v16,
    L"Out");
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180049a10  mov     r11, rsp
0x180049a13  mov     [r11+8], rbx
0x180049a17  mov     [r11+20h], rbp
0x180049a1b  push    rsi
0x180049a1c  push    rdi
0x180049a1d  push    r12
0x180049a1f  push    r14
0x180049a21  push    r15
0x180049a23  sub     rsp, 40h
0x180049a27  mov     rsi, rdx
0x180049a2a  mov     qword ptr [r11+18h], 0
0x180049a32  mov     edx, 6
0x180049a37  lea     rax, aIn_0; "In"
0x180049a3e  mov     [r11-38h], rax
0x180049a42  lea     rdi, aCdtcconfigSetc; "CDtcConfig::SetClusterTmMapping"
0x180049a49  mov     rbx, rcx
0x180049a4c  mov     qword ptr [r11-40h], 0
0x180049a54  mov     r9d, 0B6h
0x180049a5a  mov     [r11-48h], rdi
0x180049a5e  lea     ecx, [rdx+9]
0x180049a61  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049a68  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049a6d  cmp     qword ptr [rsi], 0
0x180049a71  jz      loc_180049C06
0x180049a77  mov     r15, [rsi+18h]
0x180049a7b  test    r15, r15
0x180049a7e  jz      loc_180049C06
0x180049a84  mov     r12, [rsi+20h]
0x180049a88  test    r12, r12
0x180049a8b  jz      loc_180049C06
0x180049a91  mov     ecx, [rsi+8]
0x180049a94  mov     edi, 1
0x180049a99  test    ecx, ecx
0x180049a9b  jnz     short loc_180049AA6
0x180049a9d  lea     rbp, aExe; "Exe"
0x180049aa4  jmp     short loc_180049AC3
0x180049aa6  cmp     ecx, edi
0x180049aa8  jnz     short loc_180049AB3
0x180049aaa  lea     rbp, aService; "Service"
0x180049ab1  jmp     short loc_180049AC3
0x180049ab3  cmp     ecx, 2
0x180049ab6  jnz     loc_180049BC4
0x180049abc  lea     rbp, aComplusapp; "ComplusApp"
0x180049ac3  mov     ecx, [rsi+10h]
0x180049ac6  test    ecx, ecx
0x180049ac8  jnz     short loc_180049AD3
0x180049aca  lea     r14, aAppid; "AppId"
0x180049ad1  jmp     short loc_180049AE2
0x180049ad3  cmp     ecx, edi
0x180049ad5  jnz     loc_180049BB1
0x180049adb  lea     r14, pszPropertyName; "Name"
0x180049ae2  mov     rcx, [rbx+10h]
0x180049ae6  lea     rdx, [rsp+68h+pv]
0x180049aee  mov     rax, [rcx]
0x180049af1  mov     rax, [rax+28h]
0x180049af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049afa  mov     ebx, eax
0x180049afc  test    eax, eax
0x180049afe  jns     short loc_180049B3A
0x180049b00  lea     rax, aGethostnameFai; "GetHostName failed"
0x180049b07  mov     r9d, 0E6h
0x180049b0d  lea     rsi, aCdtcconfigSetc; "CDtcConfig::SetClusterTmMapping"
0x180049b14  mov     [rsp+68h+var_38], rax
0x180049b19  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049b20  mov     dword ptr [rsp+68h+var_40], ebx
0x180049b24  mov     edx, edi
0x180049b26  mov     ecx, 0Fh
0x180049b2b  mov     [rsp+68h+var_48], rsi
0x180049b30  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049b35  jmp     loc_180049C43
0x180049b3a  lea     rdx, [rsp+68h+arg_8]; bool *
0x180049b3f  mov     [rsp+68h+arg_8], 0
0x180049b44  xor     ecx, ecx; unsigned __int16 *
0x180049b46  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180049b4b  cmp     [rsp+68h+arg_8], 0
0x180049b50  jnz     short loc_180049B66
0x180049b52  mov     ebx, 800713ACh
0x180049b57  lea     rax, aNotAClusterNod; "Not a cluster node."
0x180049b5e  mov     r9d, 0EDh
0x180049b64  jmp     short loc_180049B0D
0x180049b66  mov     eax, [rsi+0Ch]
0x180049b69  mov     r9, r14
0x180049b6c  mov     r8, [rsi]
0x180049b6f  mov     rdx, rbp
0x180049b72  mov     rcx, [rsp+68h+pv]
0x180049b7a  mov     [rsp+68h+var_38], r12
0x180049b7f  mov     dword ptr [rsp+68h+var_40], eax
0x180049b83  mov     [rsp+68h+var_48], r15
0x180049b88  call    cs:__imp_MtxCluSetClusterTmMapping
0x180049b8e  lea     rsi, aCdtcconfigSetc; "CDtcConfig::SetClusterTmMapping"
0x180049b95  mov     ebx, eax
0x180049b97  test    eax, eax
0x180049b99  jns     loc_180049C43
0x180049b9f  lea     rax, aMtxclusetclust; "MtxCluSetClusterTmMapping failed"
0x180049ba6  mov     r9d, 0FAh
0x180049bac  jmp     loc_180049B14
0x180049bb1  mov     [rsp+68h+var_30], ecx
0x180049bb5  mov     r9d, 0DFh
0x180049bbb  lea     rcx, aInvalidArgumen_1; "Invalid argument: tmMapping.dwIdType %d"
0x180049bc2  jmp     short loc_180049BD5
0x180049bc4  mov     [rsp+68h+var_30], ecx
0x180049bc8  mov     r9d, 0D0h
0x180049bce  lea     rcx, aInvalidArgumen_2; "Invalid argument: tmMapping.MappingType"...
0x180049bd5  mov     [rsp+68h+var_38], rcx
0x180049bda  lea     rsi, aCdtcconfigSetc; "CDtcConfig::SetClusterTmMapping"
0x180049be1  mov     eax, 80070057h
0x180049be6  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049bed  mov     dword ptr [rsp+68h+var_40], eax
0x180049bf1  mov     edx, edi
0x180049bf3  mov     ecx, 0Fh
0x180049bf8  mov     [rsp+68h+var_48], rsi
0x180049bfd  mov     ebx, eax
0x180049bff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049c04  jmp     short loc_180049C43
0x180049c06  lea     rcx, aInvalidArgumen_4; "Invalid arguments."
0x180049c0d  mov     eax, 80070057h
0x180049c12  mov     [rsp+68h+var_38], rcx
0x180049c17  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049c1e  mov     edx, 1
0x180049c23  mov     dword ptr [rsp+68h+var_40], eax
0x180049c27  mov     r9d, 0BDh
0x180049c2d  mov     [rsp+68h+var_48], rdi
0x180049c32  mov     ebx, eax
0x180049c34  lea     ecx, [rdx+0Eh]
0x180049c37  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049c3c  lea     rsi, aCdtcconfigSetc; "CDtcConfig::SetClusterTmMapping"
0x180049c43  mov     rcx, [rsp+68h+pv]; pv
0x180049c4b  call    cs:__imp_CoTaskMemFree
0x180049c51  mov     edx, 6
0x180049c56  lea     rax, aOut; "Out"
0x180049c5d  mov     [rsp+68h+var_38], rax
0x180049c62  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049c69  mov     dword ptr [rsp+68h+var_40], ebx
0x180049c6d  mov     r9d, 100h
0x180049c73  mov     [rsp+68h+var_48], rsi
0x180049c78  lea     ecx, [rdx+9]
0x180049c7b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049c80  lea     r11, [rsp+68h+var_28]
0x180049c85  mov     eax, ebx
0x180049c87  mov     rbx, [r11+30h]
0x180049c8b  mov     rbp, [r11+48h]
0x180049c8f  mov     rsp, r11
0x180049c92  pop     r15
0x180049c94  pop     r14
0x180049c96  pop     r12
0x180049c98  pop     rdi
0x180049c99  pop     rsi
0x180049c9a  retn
```
