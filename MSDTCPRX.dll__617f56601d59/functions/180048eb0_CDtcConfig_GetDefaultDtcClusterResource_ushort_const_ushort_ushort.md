# CDtcConfig::GetDefaultDtcClusterResource(ushort const *,ushort * *,ushort * *)

- ea: `0x180048eb0`
- end: `0x180049009`
- name: `?GetDefaultDtcClusterResource@CDtcConfig@@UEAAJPEBGPEAPEAG1@Z`
- size: `345`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000f8d0`
- `0x180048eb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fc8`
- `MTXCLU!MtxCluGetNameFromResourceIdString` at `0x180048f8c`
- `MTXCLU!MtxCluGetNameFromResourceIdString` at `0x180048f8c`
- `MTXCLU!MtxCluGetDefaultClusterResource` at `0x180048f69`
- `MTXCLU!MtxCluGetDefaultClusterResource` at `0x180048f69`

## string_xrefs

- `0x180048edb`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180048ef0`: `CDtcConfig::GetDefaultDtcClusterResource`

## pseudocode

```c
__int64 __fastcall CDtcConfig::GetDefaultDtcClusterResource(
        CDtcConfig *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int DefaultClusterResource; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // r9
  __int64 v11; // [rsp+28h] [rbp-60h]
  LPVOID pv[9]; // [rsp+40h] [rbp-48h] BYREF
  bool v13; // [rsp+A0h] [rbp+18h] BYREF

  pv[0] = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    561,
    L"CDtcConfig::GetDefaultDtcClusterResource",
    0,
    L"In");
  if ( !a3 )
  {
    DefaultClusterResource = -2147024809;
    v8 = L"Invalid arguments";
    v9 = 566;
LABEL_9:
    LODWORD(v11) = DefaultClusterResource;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v9,
      L"CDtcConfig::GetDefaultDtcClusterResource",
      v11,
      v8);
    goto LABEL_10;
  }
  v13 = 0;
  MtxCluIsClusterPresentNonAdmin(0, &v13);
  if ( !v13 )
  {
    DefaultClusterResource = -2147019860;
    v8 = L"Not a cluster node.";
    v9 = 573;
    goto LABEL_9;
  }
  DefaultClusterResource = MtxCluGetDefaultClusterResource(a2, pv, a4);
  if ( DefaultClusterResource < 0 )
  {
    v8 = L"MtxCluGetDefaultClusterResource failed";
    v9 = 580;
    goto LABEL_9;
  }
  DefaultClusterResource = MtxCluGetNameFromResourceIdString(pv[0], a3);
  if ( DefaultClusterResource < 0 )
  {
    v8 = L"MtxCluGetNameFromResourceIdString failed";
    v9 = 587;
    goto LABEL_9;
  }
LABEL_10:
  CoTaskMemFree(pv[0]);
  LODWORD(v11) = DefaultClusterResource;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    594,
    L"CDtcConfig::GetDefaultDtcClusterResource",
    v11,
    L"Out");
  return (unsigned int)DefaultClusterResource;
}

```

## disassembly

```asm
0x180048eb0  mov     r11, rsp
0x180048eb3  push    rbx
0x180048eb4  push    rsi
0x180048eb5  push    rdi
0x180048eb6  push    r12
0x180048eb8  push    r14
0x180048eba  push    r15
0x180048ebc  sub     rsp, 58h
0x180048ec0  mov     rsi, rdx
0x180048ec3  mov     qword ptr [r11-48h], 0
0x180048ecb  mov     edx, 6
0x180048ed0  lea     rax, aIn_0; "In"
0x180048ed7  mov     [r11-58h], rax
0x180048edb  lea     r14, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048ee2  mov     rbx, r9
0x180048ee5  mov     qword ptr [r11-60h], 0
0x180048eed  mov     rdi, r8
0x180048ef0  lea     r12, aCdtcconfigGetd; "CDtcConfig::GetDefaultDtcClusterResourc"...
0x180048ef7  lea     r15d, [rdx+9]
0x180048efb  mov     [r11-68h], r12
0x180048eff  mov     ecx, r15d
0x180048f02  mov     r9d, 231h
0x180048f08  mov     r8, r14
0x180048f0b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048f10  test    rdi, rdi
0x180048f13  jnz     short loc_180048F29
0x180048f15  mov     ebx, 80070057h
0x180048f1a  lea     rax, aInvalidArgumen_9; "Invalid arguments"
0x180048f21  mov     r9d, 236h
0x180048f27  jmp     short loc_180048FA5
0x180048f29  lea     rdx, [rsp+88h+arg_10]; bool *
0x180048f31  mov     [rsp+88h+arg_10], 0
0x180048f39  xor     ecx, ecx; unsigned __int16 *
0x180048f3b  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180048f40  cmp     [rsp+88h+arg_10], 0
0x180048f48  jnz     short loc_180048F5E
0x180048f4a  mov     ebx, 800713ACh
0x180048f4f  lea     rax, aNotAClusterNod; "Not a cluster node."
0x180048f56  mov     r9d, 23Dh
0x180048f5c  jmp     short loc_180048FA5
0x180048f5e  mov     r8, rbx
0x180048f61  lea     rdx, [rsp+88h+pv]
0x180048f66  mov     rcx, rsi
0x180048f69  call    cs:__imp_MtxCluGetDefaultClusterResource
0x180048f6f  mov     ebx, eax
0x180048f71  test    eax, eax
0x180048f73  jns     short loc_180048F84
0x180048f75  lea     rax, aMtxclugetdefau_2; "MtxCluGetDefaultClusterResource failed"
0x180048f7c  mov     r9d, 244h
0x180048f82  jmp     short loc_180048FA5
0x180048f84  mov     rcx, [rsp+88h+pv]
0x180048f89  mov     rdx, rdi
0x180048f8c  call    cs:__imp_MtxCluGetNameFromResourceIdString
0x180048f92  mov     ebx, eax
0x180048f94  test    eax, eax
0x180048f96  jns     short loc_180048FC3
0x180048f98  lea     rax, aMtxclugetnamef; "MtxCluGetNameFromResourceIdString faile"...
0x180048f9f  mov     r9d, 24Bh
0x180048fa5  mov     [rsp+88h+var_58], rax
0x180048faa  mov     r8, r14
0x180048fad  mov     dword ptr [rsp+88h+var_60], ebx
0x180048fb1  mov     edx, 1
0x180048fb6  mov     ecx, r15d
0x180048fb9  mov     [rsp+88h+var_68], r12
0x180048fbe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048fc3  mov     rcx, [rsp+88h+pv]; pv
0x180048fc8  call    cs:__imp_CoTaskMemFree
0x180048fce  lea     rax, aOut; "Out"
0x180048fd5  mov     r9d, 252h
0x180048fdb  mov     [rsp+88h+var_58], rax
0x180048fe0  mov     r8, r14
0x180048fe3  mov     dword ptr [rsp+88h+var_60], ebx
0x180048fe7  mov     edx, 6
0x180048fec  mov     ecx, r15d
0x180048fef  mov     [rsp+88h+var_68], r12
0x180048ff4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048ff9  mov     eax, ebx
0x180048ffb  add     rsp, 58h
0x180048fff  pop     r15
0x180049001  pop     r14
0x180049003  pop     r12
0x180049005  pop     rdi
0x180049006  pop     rsi
0x180049007  pop     rbx
0x180049008  retn
```
