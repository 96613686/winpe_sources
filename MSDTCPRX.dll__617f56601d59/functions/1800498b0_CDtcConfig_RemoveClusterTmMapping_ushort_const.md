# CDtcConfig::RemoveClusterTmMapping(ushort const *)

- ea: `0x1800498b0`
- end: `0x180049a01`
- name: `?RemoveClusterTmMapping@CDtcConfig@@UEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000f8d0`
- `0x1800498b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499ba`
- `MTXCLU!MtxCluRemoveClusterTmMappingByName` at `0x18004997e`
- `MTXCLU!MtxCluRemoveClusterTmMappingByName` at `0x18004997e`

## string_xrefs

- `0x1800498df`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x1800498f1`: `CDtcConfig::RemoveClusterTmMapping`
- `0x18004998a`: `MtxCluRemoveClusterTmMappingByName failed`

## pseudocode

```c
__int64 __fastcall CDtcConfig::RemoveClusterTmMapping(CDtcConfig *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  __int64 v8; // [rsp+28h] [rbp-30h]
  bool v9; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    265,
    L"CDtcConfig::RemoveClusterTmMapping",
    0,
    L"In");
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2), &pv);
    if ( v4 >= 0 )
    {
      v9 = 0;
      MtxCluIsClusterPresentNonAdmin(0, &v9);
      if ( v9 )
      {
        v4 = MtxCluRemoveClusterTmMappingByName(pv, a2);
        if ( v4 >= 0 )
          goto LABEL_10;
        v5 = L"MtxCluRemoveClusterTmMappingByName failed";
        v6 = 289;
      }
      else
      {
        v4 = -2147019860;
        v5 = L"Not a cluster node.";
        v6 = 282;
      }
    }
    else
    {
      v5 = L"ITmnstance::GetHostName failed";
      v6 = 275;
    }
    LODWORD(v8) = v4;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v6,
      L"CDtcConfig::RemoveClusterTmMapping",
      v8,
      v5);
    goto LABEL_10;
  }
  v4 = -2147024809;
LABEL_10:
  CoTaskMemFree(pv);
  LODWORD(v8) = v4;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    295,
    L"CDtcConfig::RemoveClusterTmMapping",
    v8,
    L"Out");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800498b0  mov     r11, rsp
0x1800498b3  mov     [r11+8], rbx
0x1800498b7  mov     [r11+20h], rbp
0x1800498bb  push    rdi
0x1800498bc  push    r14
0x1800498be  push    r15
0x1800498c0  sub     rsp, 40h
0x1800498c4  mov     rdi, rdx
0x1800498c7  mov     qword ptr [r11+18h], 0
0x1800498cf  mov     edx, 6
0x1800498d4  lea     rax, aIn_0; "In"
0x1800498db  mov     [r11-28h], rax
0x1800498df  lea     rbp, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800498e6  mov     rbx, rcx
0x1800498e9  mov     qword ptr [r11-30h], 0
0x1800498f1  lea     r15, aCdtcconfigRemo; "CDtcConfig::RemoveClusterTmMapping"
0x1800498f8  mov     r9d, 109h
0x1800498fe  lea     r14d, [rdx+9]
0x180049902  mov     [r11-38h], r15
0x180049906  mov     ecx, r14d
0x180049909  mov     r8, rbp
0x18004990c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049911  test    rdi, rdi
0x180049914  jnz     short loc_180049920
0x180049916  mov     ebx, 80070057h
0x18004991b  jmp     loc_1800499B5
0x180049920  mov     rcx, [rbx+10h]
0x180049924  lea     rdx, [rsp+58h+pv]
0x180049929  mov     rax, [rcx]
0x18004992c  mov     rax, [rax+28h]
0x180049930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049935  mov     ebx, eax
0x180049937  test    eax, eax
0x180049939  jns     short loc_18004994A
0x18004993b  lea     rax, aItmnstanceGeth; "ITmnstance::GetHostName failed"
0x180049942  mov     r9d, 113h
0x180049948  jmp     short loc_180049997
0x18004994a  lea     rdx, [rsp+58h+arg_8]; bool *
0x18004994f  mov     [rsp+58h+arg_8], 0
0x180049954  xor     ecx, ecx; unsigned __int16 *
0x180049956  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18004995b  cmp     [rsp+58h+arg_8], 0
0x180049960  jnz     short loc_180049976
0x180049962  mov     ebx, 800713ACh
0x180049967  lea     rax, aNotAClusterNod; "Not a cluster node."
0x18004996e  mov     r9d, 11Ah
0x180049974  jmp     short loc_180049997
0x180049976  mov     rcx, [rsp+58h+pv]
0x18004997b  mov     rdx, rdi
0x18004997e  call    cs:__imp_MtxCluRemoveClusterTmMappingByName
0x180049984  mov     ebx, eax
0x180049986  test    eax, eax
0x180049988  jns     short loc_1800499B5
0x18004998a  lea     rax, aMtxcluremovecl; "MtxCluRemoveClusterTmMappingByName fail"...
0x180049991  mov     r9d, 121h
0x180049997  mov     [rsp+58h+var_28], rax
0x18004999c  mov     r8, rbp
0x18004999f  mov     dword ptr [rsp+58h+var_30], ebx
0x1800499a3  mov     edx, 1
0x1800499a8  mov     ecx, r14d
0x1800499ab  mov     [rsp+58h+var_38], r15
0x1800499b0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800499b5  mov     rcx, [rsp+58h+pv]; pv
0x1800499ba  call    cs:__imp_CoTaskMemFree
0x1800499c0  lea     rax, aOut; "Out"
0x1800499c7  mov     r9d, 127h
0x1800499cd  mov     [rsp+58h+var_28], rax
0x1800499d2  mov     r8, rbp
0x1800499d5  mov     dword ptr [rsp+58h+var_30], ebx
0x1800499d9  mov     edx, 6
0x1800499de  mov     ecx, r14d
0x1800499e1  mov     [rsp+58h+var_38], r15
0x1800499e6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800499eb  mov     rbp, [rsp+58h+arg_18]
0x1800499f0  mov     eax, ebx
0x1800499f2  mov     rbx, [rsp+58h+arg_0]
0x1800499f7  add     rsp, 40h
0x1800499fb  pop     r15
0x1800499fd  pop     r14
0x1800499ff  pop     rdi
0x180049a00  retn
```
