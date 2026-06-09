# CDtcConfig::Init(ushort const *,ushort const *)

- ea: `0x180015414`
- end: `0x1800158d2`
- name: `?Init@CDtcConfig@@AEAAJPEBG0@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CDtcConfig *this, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048690`

## callees

- `0x180003cf0`
- `0x1800092f4`
- `0x18000f8d0`
- `0x180015414`
- `0x180017934`
- `0x180018d24`
- `0x18004de14`
- `0x180053720`
- `0x1800537f0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001582f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001582f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001552a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001552a`
- `msvcrt!_wcsicmp` at `0x1800157cd`
- `msvcrt!_wcsicmp` at `0x1800157cd`
- `MTXCLU!MtxCluCreateClusterTmInstance` at `0x1800155bb`
- `MTXCLU!MtxCluCreateClusterTmInstance` at `0x1800155bb`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x18001556f`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x18001556f`
- `MTXCLU!MtxCluGetResourceIdStringFromName` at `0x180015594`
- `MTXCLU!MtxCluGetResourceIdStringFromName` at `0x180015594`

## string_xrefs

- `0x180015470`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x1800154c3`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180015552`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x1800155e0`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180015600`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001569b`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001571c`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001589e`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001544d`: `CDtcConfig::Init`
- `0x1800154b7`: `CDtcConfig::Init`
- `0x18001554b`: `CDtcConfig::Init`
- `0x1800155d9`: `CDtcConfig::Init`
- `0x180015607`: `CDtcConfig::Init`
- `0x180015654`: `CDtcConfig::Init`
- `0x180015692`: `CDtcConfig::Init`
- `0x1800156e6`: `CDtcConfig::Init`
- `0x1800157b5`: `CDtcConfig::Init`
- `0x180015803`: `CDtcConfig::Init`
- `0x1800154fd`: `CreateLegacyTmInstance failed`
- `0x18001553e`: `CoTaskMemAlloc failed`
- `0x1800155cc`: `MtxCluCreateClusterTmInstance failed`
- `0x1800155ee`: `A cluster Tm instance was created.`
- `0x1800156c8`: `An admin user access is required for this operation`
- `0x1800156f8`: `CreateTmInstanceForRemoteAdmin failed`
- `0x18001570a`: `A non clustered TM instance is created.`
- `0x18001574c`: `IsLocalDtcServiceEnabled failed`

## pseudocode

```c
__int64 __fastcall CDtcConfig::Init(CDtcConfig *this, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  struct INameObject *v6; // rsi
  int v7; // r13d
  int v8; // eax
  int DTCVirtualServerNameW; // ebx
  const wchar_t *v10; // rax
  __int64 v11; // r9
  wchar_t *v12; // r12
  int v13; // edi
  void *v14; // rax
  __int64 v15; // r9
  int v16; // eax
  CDtcConfig *v17; // rcx
  WINBOOL v18; // eax
  __int64 v20; // [rsp+28h] [rbp-41h]
  WINBOOL IsMember; // [rsp+40h] [rbp-29h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-21h] BYREF
  struct ITmInstance *v23; // [rsp+50h] [rbp-19h] BYREF
  struct INameObject *v24; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1h]
  LPVOID v27[10]; // [rsp+70h] [rbp+7h] BYREF
  int v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v23 = 0;
  v25 = 0;
  v24 = 0;
  pv = 0;
  String2 = 0;
  v27[0] = 0;
  v6 = 0;
  IsMember = 0;
  v7 = 0;
  v28 = 0;
  TraceStringInline(15, 6, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp", 347, L"CDtcConfig::Init", 0, L"In");
  v8 = IsUserAdmin(&IsMember);
  DTCVirtualServerNameW = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      DTCVirtualServerNameW = (unsigned __int16)v8 | 0x80070000;
    v10 = L"IsUserAdmin failed";
    v11 = 352;
    goto LABEL_5;
  }
  DTCVirtualServerNameW = CreateLegacyTmInstance(a2, &v25);
  if ( DTCVirtualServerNameW < 0 )
  {
    v10 = L"CreateLegacyTmInstance failed";
    v11 = 359;
LABEL_5:
    LODWORD(v20) = DTCVirtualServerNameW;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v11,
      L"CDtcConfig::Init",
      v20,
      v10);
LABEL_6:
    v12 = String2;
    goto LABEL_42;
  }
  v13 = 1;
  if ( a3 )
  {
    if ( !IsMember )
    {
      LOBYTE(v28) = 0;
      MtxCluIsClusterPresentNonAdmin(0, (bool *)&v28);
      if ( (_BYTE)v28 )
      {
        DTCVirtualServerNameW = -2147024891;
        v10 = L"An admin user access is required for this operation";
        v11 = 409;
      }
      else
      {
        DTCVirtualServerNameW = -2147483646;
        v10 = L"Not a cluster node.";
        v11 = 403;
      }
      goto LABEL_5;
    }
    v14 = CoTaskMemAlloc(0x20Au);
    pv = v14;
    if ( !v14 )
    {
      DTCVirtualServerNameW = -2147024882;
      v10 = L"CoTaskMemAlloc failed";
      v11 = 371;
      goto LABEL_5;
    }
    DTCVirtualServerNameW = MtxCluGetDTCVirtualServerNameW(a2, a3, v14, 261);
    if ( DTCVirtualServerNameW < 0 )
    {
      v10 = L"MtxCluGetDTCVirtualServerNameW failed";
      v11 = 378;
      goto LABEL_5;
    }
    DTCVirtualServerNameW = MtxCluGetResourceIdStringFromName(a2, a3, v27);
    if ( DTCVirtualServerNameW < 0 )
    {
      v10 = L"MtxCluGetResourceIdStringFromName failed";
      v11 = 385;
      goto LABEL_5;
    }
    DTCVirtualServerNameW = MtxCluCreateClusterTmInstance(pv, v27[0], &v23);
    if ( DTCVirtualServerNameW < 0 )
    {
      v10 = L"MtxCluCreateClusterTmInstance failed";
      v11 = 394;
      goto LABEL_5;
    }
    TraceStringInline(
      15,
      3,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      397,
      L"CDtcConfig::Init",
      0,
      L"A cluster Tm instance was created.");
    DTCVirtualServerNameW = GetTmNameObjectForDescription(v23, L"MSDTC", &v24);
    if ( DTCVirtualServerNameW < 0 )
    {
      v15 = 416;
LABEL_21:
      LODWORD(v20) = DTCVirtualServerNameW;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        v15,
        L"CDtcConfig::Init",
        v20,
        L"GetTmNameObjectForDescription failed");
      v6 = v24;
      goto LABEL_6;
    }
    v6 = v24;
    v16 = 0;
  }
  else
  {
    DTCVirtualServerNameW = CreateTmInstanceForRemoteAdmin(a2, &v23);
    if ( DTCVirtualServerNameW < 0 )
    {
      v10 = L"CreateTmInstanceForRemoteAdmin failed";
      v11 = 426;
      goto LABEL_5;
    }
    TraceStringInline(
      15,
      3,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      429,
      L"CDtcConfig::Init",
      0,
      L"A non clustered TM instance is created.");
    DTCVirtualServerNameW = CDtcConfig::IsLocalDtcServiceEnabled(v17, a2, &v28);
    if ( DTCVirtualServerNameW < 0 )
    {
      v10 = L"IsLocalDtcServiceEnabled failed";
      v11 = 434;
      goto LABEL_5;
    }
    v7 = v28;
    if ( v28 )
    {
      DTCVirtualServerNameW = GetTmNameObjectForDescription(v23, L"MSDTC", &v24);
      if ( DTCVirtualServerNameW < 0 )
      {
        v15 = 443;
        goto LABEL_21;
      }
      v6 = v24;
    }
    v16 = 1;
  }
  *((_DWORD *)this + 9) = v16;
  DTCVirtualServerNameW = GetPhysicalNodeNameW(&String2);
  if ( DTCVirtualServerNameW < 0 )
  {
    v10 = L"GetPhysicalNodeNameW failed";
    v11 = 454;
    goto LABEL_5;
  }
  v12 = String2;
  if ( a2 && _wcsicmp(a2, String2) )
    v13 = 0;
  else
    *((_DWORD *)this + 26) = 6;
  *((_QWORD *)this + 2) = v25;
  *((_QWORD *)this + 1) = v23;
  v18 = IsMember;
  *((_QWORD *)this + 22) = v6;
  v6 = 0;
  *((_DWORD *)this + 8) = v7;
  *((_DWORD *)this + 6) = v18;
  v25 = 0;
  v23 = 0;
  *((_DWORD *)this + 7) = v13;
LABEL_42:
  CoTaskMemFree(v12);
  CoTaskMemFree(pv);
  CoTaskMemFree(v27[0]);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v6 + 16LL))(v6);
  LODWORD(v20) = DTCVirtualServerNameW;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    488,
    L"CDtcConfig::Init",
    v20,
    L"Out");
  return (unsigned int)DTCVirtualServerNameW;
}

```

## disassembly

```asm
0x180015414  push    rbp
0x180015416  push    rbx
0x180015417  push    rsi
0x180015418  push    rdi
0x180015419  push    r12
0x18001541b  push    r13
0x18001541d  push    r14
0x18001541f  push    r15
0x180015421  lea     rbp, [rsp-1Fh]
0x180015426  sub     rsp, 88h
0x18001542d  xor     edi, edi
0x18001542f  lea     rax, aIn_0; "In"
0x180015436  mov     [rsp+0C0h+var_90], rax
0x18001543b  mov     r12, r8
0x18001543e  mov     r15, rdx
0x180015441  mov     [rsp+0C0h+var_98], rdi
0x180015446  mov     r14, rcx
0x180015449  mov     [rbp+57h+var_70], rdi
0x18001544d  lea     rax, aCdtcconfigInit; "CDtcConfig::Init"
0x180015454  mov     [rbp+57h+var_60], rdi
0x180015458  lea     edx, [rdi+6]
0x18001545b  mov     [rbp+57h+var_68], rdi
0x18001545f  lea     ecx, [rdi+0Fh]
0x180015462  mov     [rbp+57h+pv], rdi
0x180015466  mov     r9d, 15Bh
0x18001546c  mov     [rbp+57h+String2], rdi
0x180015470  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180015477  mov     [rbp+57h+var_50], rdi
0x18001547b  mov     esi, edi
0x18001547d  mov     [rbp+57h+IsMember], edi
0x180015480  mov     r13d, edi
0x180015483  mov     [rbp+57h+arg_18], edi
0x180015486  mov     [rsp+0C0h+var_A0], rax
0x18001548b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015490  lea     rcx, [rbp+57h+IsMember]; IsMember
0x180015494  call    ?IsUserAdmin@@YAKAEAH@Z; IsUserAdmin(int &)
0x180015499  mov     ebx, eax
0x18001549b  test    eax, eax
0x18001549d  jz      short loc_1800154EB
0x18001549f  jle     short loc_1800154AA
0x1800154a1  movzx   ebx, ax
0x1800154a4  or      ebx, 80070000h
0x1800154aa  lea     rax, aIsuseradminFai; "IsUserAdmin failed"
0x1800154b1  mov     r9d, 160h
0x1800154b7  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x1800154be  mov     edx, 1
0x1800154c3  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800154ca  mov     ecx, 0Fh
0x1800154cf  mov     [rsp+0C0h+var_90], rax
0x1800154d4  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1800154d8  mov     [rsp+0C0h+var_A0], r13
0x1800154dd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800154e2  mov     r12, [rbp+57h+String2]
0x1800154e6  jmp     loc_180015822
0x1800154eb  lea     rdx, [rbp+57h+var_60]
0x1800154ef  mov     rcx, r15; unsigned __int16 *
0x1800154f2  call    CreateLegacyTmInstance
0x1800154f7  mov     ebx, eax
0x1800154f9  test    eax, eax
0x1800154fb  jns     short loc_18001550C
0x1800154fd  lea     rax, aCreatelegacytm_0; "CreateLegacyTmInstance failed"
0x180015504  mov     r9d, 167h
0x18001550a  jmp     short loc_1800154B7
0x18001550c  xor     ebx, ebx
0x18001550e  mov     edi, 1
0x180015513  test    r12, r12
0x180015516  jz      loc_1800156DA
0x18001551c  cmp     [rbp+57h+IsMember], ebx
0x18001551f  jz      loc_180015684
0x180015525  mov     ecx, 20Ah; cb
0x18001552a  call    cs:__imp_CoTaskMemAlloc
0x180015530  mov     [rbp+57h+pv], rax
0x180015534  test    rax, rax
0x180015537  jnz     short loc_180015560
0x180015539  mov     ebx, 8007000Eh
0x18001553e  lea     rax, aCotaskmemalloc_2; "CoTaskMemAlloc failed"
0x180015545  mov     r9d, 173h
0x18001554b  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x180015552  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180015559  mov     edx, edi
0x18001555b  jmp     loc_1800154CA
0x180015560  mov     r9d, 105h
0x180015566  mov     r8, rax
0x180015569  mov     rdx, r12
0x18001556c  mov     rcx, r15
0x18001556f  call    cs:__imp_MtxCluGetDTCVirtualServerNameW
0x180015575  mov     ebx, eax
0x180015577  test    eax, eax
0x180015579  jns     short loc_18001558A
0x18001557b  lea     rax, aMtxclugetdtcvi; "MtxCluGetDTCVirtualServerNameW failed"
0x180015582  mov     r9d, 17Ah
0x180015588  jmp     short loc_18001554B
0x18001558a  lea     r8, [rbp+57h+var_50]
0x18001558e  mov     rdx, r12
0x180015591  mov     rcx, r15
0x180015594  call    cs:__imp_MtxCluGetResourceIdStringFromName
0x18001559a  mov     ebx, eax
0x18001559c  test    eax, eax
0x18001559e  jns     short loc_1800155AF
0x1800155a0  lea     rax, aMtxclugetresou; "MtxCluGetResourceIdStringFromName faile"...
0x1800155a7  mov     r9d, 181h
0x1800155ad  jmp     short loc_18001554B
0x1800155af  mov     rdx, [rbp+57h+var_50]
0x1800155b3  lea     r8, [rbp+57h+var_70]
0x1800155b7  mov     rcx, [rbp+57h+pv]
0x1800155bb  call    cs:__imp_MtxCluCreateClusterTmInstance
0x1800155c1  mov     ebx, eax
0x1800155c3  mov     ecx, 0Fh
0x1800155c8  test    eax, eax
0x1800155ca  jns     short loc_1800155EE
0x1800155cc  lea     rax, aMtxclucreatecl; "MtxCluCreateClusterTmInstance failed"
0x1800155d3  mov     r9d, 18Ah
0x1800155d9  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x1800155e0  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800155e7  mov     edx, edi
0x1800155e9  jmp     loc_1800154CF
0x1800155ee  lea     rax, aAClusterTmInst; "A cluster Tm instance was created."
0x1800155f5  mov     r9d, 18Dh
0x1800155fb  mov     [rsp+0C0h+var_90], rax
0x180015600  lea     r12, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180015607  lea     rax, aCdtcconfigInit; "CDtcConfig::Init"
0x18001560e  mov     [rsp+0C0h+var_98], rsi
0x180015613  mov     r8, r12
0x180015616  mov     [rsp+0C0h+var_A0], rax
0x18001561b  mov     edx, 3
0x180015620  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015625  mov     rcx, [rbp+57h+var_70]; struct ITmInstance *
0x180015629  lea     r8, [rbp+57h+var_68]; struct INameObject **
0x18001562d  lea     rdx, aMsdtc; "MSDTC"
0x180015634  call    ?GetTmNameObjectForDescription@@YAJPEAUITmInstance@@PEBGPEAPEAUINameObject@@@Z; GetTmNameObjectForDescription(ITmInstance *,ushort const *,INameObject * *)
0x180015639  mov     ebx, eax
0x18001563b  test    eax, eax
0x18001563d  jns     short loc_180015679
0x18001563f  mov     r9d, 1A0h
0x180015645  lea     rax, aGettmnameobjec_0; "GetTmNameObjectForDescription failed"
0x18001564c  mov     r8, r12
0x18001564f  mov     [rsp+0C0h+var_90], rax
0x180015654  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x18001565b  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18001565f  mov     edx, edi
0x180015661  mov     ecx, 0Fh
0x180015666  mov     [rsp+0C0h+var_A0], r13
0x18001566b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015670  mov     rsi, [rbp+57h+var_68]
0x180015674  jmp     loc_1800154E2
0x180015679  mov     rsi, [rbp+57h+var_68]
0x18001567d  xor     eax, eax
0x18001567f  jmp     loc_180015795
0x180015684  lea     rdx, [rbp+57h+arg_18]; bool *
0x180015688  mov     byte ptr [rbp+57h+arg_18], bl
0x18001568b  xor     ecx, ecx; unsigned __int16 *
0x18001568d  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180015692  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x180015699  mov     edx, edi
0x18001569b  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800156a2  mov     ecx, 0Fh
0x1800156a7  cmp     byte ptr [rbp+57h+arg_18], bl
0x1800156aa  jnz     short loc_1800156C3
0x1800156ac  mov     ebx, 80000002h
0x1800156b1  lea     rax, aNotAClusterNod; "Not a cluster node."
0x1800156b8  mov     r9d, 193h
0x1800156be  jmp     loc_1800154CF
0x1800156c3  mov     ebx, 80070005h
0x1800156c8  lea     rax, aAnAdminUserAcc; "An admin user access is required for th"...
0x1800156cf  mov     r9d, 199h
0x1800156d5  jmp     loc_1800154CF
0x1800156da  lea     rdx, [rbp+57h+var_70]; struct ITmInstance **
0x1800156de  mov     rcx, r15; unsigned __int16 *
0x1800156e1  call    CreateTmInstanceForRemoteAdmin
0x1800156e6  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x1800156ed  mov     ebx, eax
0x1800156ef  mov     ecx, 0Fh
0x1800156f4  test    eax, eax
0x1800156f6  jns     short loc_18001570A
0x1800156f8  lea     rax, aCreatetminstan_0; "CreateTmInstanceForRemoteAdmin failed"
0x1800156ff  mov     r9d, 1AAh
0x180015705  jmp     loc_1800155E0
0x18001570a  lea     rax, aANonClusteredT; "A non clustered TM instance is created."
0x180015711  mov     r9d, 1ADh
0x180015717  mov     [rsp+0C0h+var_90], rax
0x18001571c  lea     r12, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180015723  mov     [rsp+0C0h+var_98], rsi
0x180015728  mov     r8, r12
0x18001572b  mov     edx, 3
0x180015730  mov     [rsp+0C0h+var_A0], r13
0x180015735  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001573a  lea     r8, [rbp+57h+arg_18]; int *
0x18001573e  mov     rdx, r15; unsigned __int16 *
0x180015741  call    ?IsLocalDtcServiceEnabled@CDtcConfig@@AEAAJPEBGPEAH@Z; CDtcConfig::IsLocalDtcServiceEnabled(ushort const *,int *)
0x180015746  mov     ebx, eax
0x180015748  test    eax, eax
0x18001574a  jns     short loc_180015761
0x18001574c  lea     rax, aIslocaldtcserv; "IsLocalDtcServiceEnabled failed"
0x180015753  mov     r9d, 1B2h
0x180015759  mov     r8, r12
0x18001575c  jmp     loc_180015559
0x180015761  mov     r13d, [rbp+57h+arg_18]
0x180015765  test    r13d, r13d
0x180015768  jz      short loc_180015793
0x18001576a  mov     rcx, [rbp+57h+var_70]; struct ITmInstance *
0x18001576e  lea     r8, [rbp+57h+var_68]; struct INameObject **
0x180015772  lea     rdx, aMsdtc; "MSDTC"
0x180015779  call    ?GetTmNameObjectForDescription@@YAJPEAUITmInstance@@PEBGPEAPEAUINameObject@@@Z; GetTmNameObjectForDescription(ITmInstance *,ushort const *,INameObject * *)
0x18001577e  mov     ebx, eax
0x180015780  test    eax, eax
0x180015782  jns     short loc_18001578F
0x180015784  mov     r9d, 1BBh
0x18001578a  jmp     loc_180015645
0x18001578f  mov     rsi, [rbp+57h+var_68]
0x180015793  mov     eax, edi
0x180015795  lea     rcx, [rbp+57h+String2]; unsigned __int16 **
0x180015799  mov     [r14+24h], eax
0x18001579d  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x1800157a2  mov     ebx, eax
0x1800157a4  test    eax, eax
0x1800157a6  jns     short loc_1800157BE
0x1800157a8  lea     rax, aGetphysicalnod; "GetPhysicalNodeNameW failed"
0x1800157af  mov     r9d, 1C6h
0x1800157b5  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x1800157bc  jmp     short loc_180015759
0x1800157be  mov     r12, [rbp+57h+String2]
0x1800157c2  test    r15, r15
0x1800157c5  jz      short loc_1800157DB
0x1800157c7  mov     rdx, r12; String2
0x1800157ca  mov     rcx, r15; String1
0x1800157cd  call    cs:__imp__wcsicmp
0x1800157d3  test    eax, eax
0x1800157d5  jz      short loc_1800157DB
0x1800157d7  xor     edi, edi
0x1800157d9  jmp     short loc_1800157E3
0x1800157db  mov     dword ptr [r14+68h], 6
0x1800157e3  mov     rax, [rbp+57h+var_60]
0x1800157e7  mov     [r14+10h], rax
0x1800157eb  mov     rax, [rbp+57h+var_70]
0x1800157ef  mov     [r14+8], rax
0x1800157f3  mov     eax, [rbp+57h+IsMember]
0x1800157f6  mov     [r14+0B0h], rsi
0x1800157fd  xor     esi, esi
0x1800157ff  mov     [r14+20h], r13d
0x180015803  lea     r13, aCdtcconfigInit; "CDtcConfig::Init"
0x18001580a  mov     [r14+18h], eax
0x18001580e  mov     [rbp+57h+var_60], 0
0x180015816  mov     [rbp+57h+var_70], 0
0x18001581e  mov     [r14+1Ch], edi
0x180015822  mov     rcx, r12; pv
0x180015825  call    cs:__imp_CoTaskMemFree
0x18001582b  mov     rcx, [rbp+57h+pv]; pv
0x18001582f  call    cs:__imp_CoTaskMemFree
0x180015835  mov     rcx, [rbp+57h+var_50]; pv
0x180015839  call    cs:__imp_CoTaskMemFree
0x18001583f  mov     rcx, [rbp+57h+var_60]
0x180015843  test    rcx, rcx
0x180015846  jz      short loc_18001585C
0x180015848  mov     rax, [rcx]
0x18001584b  mov     rax, [rax+10h]
0x18001584f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015854  mov     [rbp+57h+var_60], 0
0x18001585c  mov     rcx, [rbp+57h+var_70]
0x180015860  test    rcx, rcx
0x180015863  jz      short loc_180015879
0x180015865  mov     rax, [rcx]
0x180015868  mov     rax, [rax+10h]
0x18001586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015871  mov     [rbp+57h+var_70], 0
0x180015879  test    rsi, rsi
0x18001587c  jz      short loc_18001588D
0x18001587e  mov     rax, [rsi]
0x180015881  mov     rcx, rsi
0x180015884  mov     rax, [rax+10h]
0x180015888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001588d  mov     edx, 6
0x180015892  lea     rax, aOut; "Out"
0x180015899  mov     [rsp+0C0h+var_90], rax
0x18001589e  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800158a5  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1800158a9  mov     r9d, 1E8h
0x1800158af  mov     [rsp+0C0h+var_A0], r13
0x1800158b4  lea     ecx, [rdx+9]
0x1800158b7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800158bc  mov     eax, ebx
0x1800158be  add     rsp, 88h
0x1800158c5  pop     r15
0x1800158c7  pop     r14
0x1800158c9  pop     r13
0x1800158cb  pop     r12
0x1800158cd  pop     rdi
0x1800158ce  pop     rsi
0x1800158cf  pop     rbx
0x1800158d0  pop     rbp
0x1800158d1  retn
```
