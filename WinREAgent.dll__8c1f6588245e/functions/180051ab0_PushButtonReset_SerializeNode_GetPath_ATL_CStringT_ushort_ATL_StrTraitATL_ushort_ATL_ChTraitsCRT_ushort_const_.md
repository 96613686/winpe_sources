# PushButtonReset::SerializeNode::GetPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180051ab0`
- end: `0x18005209d`
- name: `?GetPath@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `1517`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800366f0`

## callees

- `0x180004af8`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x1800074b8`
- `0x1800089d0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002476c`
- `0x180037344`
- `0x18003d700`
- `0x180047d1c`
- `0x18004a898`
- `0x18004d35c`
- `0x180051960`
- `0x180051ab0`
- `0x180052194`
- `0x1800522e8`
- `0x180059c8c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180051b2a`: `Failed to read whether the path was set`
- `0x180051b45`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051bdd`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051c3d`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051cbf`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051d69`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051e31`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051f6c`: `PushButtonReset::SerializeNode::GetPath`
- `0x180051c22`: `Failed to read relative path from [%s]`
- `0x180051e16`: `Failed to construct full path to [%s] on volume [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PushButtonReset::SerializeNode::GetPath(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  int Property; // ebx
  struct PushButtonReset::Partition **v7; // rax
  unsigned __int64 v8; // rsi
  unsigned int v9; // edi
  PushButtonReset::Partition *v10; // rax
  int Info; // esi
  __int64 v12; // rdi
  int v13; // r15d
  __int64 v14; // rbx
  ATL::CStringData *v15; // rcx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  int *v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rax
  ATL::CStringData *v21; // r14
  int *v22; // rsi
  __int64 v23; // rbx
  int v25; // [rsp+30h] [rbp-D0h]
  int v26; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+38h] [rbp-C8h]
  _BYTE v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[96]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+F0h] [rbp-10h]

  ATL::operator+(&v35, a2, L"Set");
  ATL::operator+(&v34, a2, L"Path");
  v29[0] = 0;
  Property = PushButtonReset::SerializeNode::GetProperty(a1, &v35, v29);
  if ( Property < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Property,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      620,
      L"Failed to read whether the path was set");
    goto LABEL_36;
  }
  if ( !v29[0] )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &pszFormat, 0);
    goto LABEL_36;
  }
  if ( !(unsigned __int8)PushButtonReset::XmlNode::HasAttribute(*a1, &v34) )
  {
    Property = -2147023728;
    goto LABEL_36;
  }
  v30[0] = 0;
  v33 = 0;
  Property = PushButtonReset::SerializeNode::GetPartition(a1, a2, v30, &v33);
  if ( Property < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Property,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      636,
      L"Failed to look up disk + partition pair for [%s]",
      *a2);
    goto LABEL_36;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v32);
  Property = PushButtonReset::SerializeNode::GetProperty(a1, &v34, &v32);
  if ( Property < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Property,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      640,
      L"Failed to read relative path from [%s]",
      v34);
LABEL_11:
    ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
    goto LABEL_36;
  }
  v31[1] = 0;
  v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v7 = (struct PushButtonReset::Partition **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v31);
  v8 = v33;
  v9 = v30[0];
  Property = PushButtonReset::Partition::FindByOffset(v30[0], v33, v7);
  if ( Property < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Property,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      646,
      L"Failed to look up partition at offset [%llu] on disk [%u]",
      v8,
      v9);
    v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
    goto LABEL_11;
  }
  PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v36);
  v10 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
  Info = PushButtonReset::Partition::GetInfo(v10, (struct PushButtonReset::PartitionInfo *)v36);
  if ( Info < 0 )
  {
    v27 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31) + 16);
    v25 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31) + 104);
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      652,
      L"Failed to get info for partition [%u] on disk [%u]",
      v25,
      v27);
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v36);
    v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
    ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
    Property = Info;
    goto LABEL_36;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v30);
  if ( v37 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      v30,
      L"%c:\\",
      v37);
  }
  else
  {
    v16 = *(unsigned int *)(v38 - 16);
    if ( (int)v16 <= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        v30,
        L"\\\\?\\GLOBALROOT\\device\\harddisk%u\\partition%u\\",
        v9,
        *(unsigned int *)(v20 + 104));
      if ( !(unsigned __int8)PushButtonReset::Path::Exists(v30) )
      {
        v28 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31) + 104);
        v26 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31) + 16);
        PushButtonReset::Logging::TraceErr(
          2,
          2147942413LL,
          "PushButtonReset::SerializeNode::GetPath",
          "base\\reset\\util\\src\\serialize.cpp",
          674,
          L"Disk [%u] partition [%u] does not have an associated volume",
          v26,
          v28);
        ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v30 - 24LL));
        PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v36);
        v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
        ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
        Property = -2147024883;
        goto LABEL_36;
      }
    }
    else
    {
      v17 = (_QWORD *)(v38 - 24);
      v12 = *(_QWORD *)v30;
      v18 = (int *)(*(_QWORD *)v30 - 24LL);
      if ( v38 - 24 == *(_QWORD *)v30 - 24LL )
        goto LABEL_19;
      if ( v18[4] >= 0 && *v17 == *(_QWORD *)v18 )
      {
        v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v17);
        ATL::CStringData::Release((ATL::CStringData *)v18);
        v12 = v19 + 24;
        *(_QWORD *)v30 = v12;
        goto LABEL_19;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(v30, v38, v16);
    }
  }
  v12 = *(_QWORD *)v30;
LABEL_19:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v33);
  v13 = PushButtonReset::Path::Combine(v30, &v32, &v33);
  if ( v13 >= 0 )
  {
    v21 = (ATL::CStringData *)(v33 - 24);
    v22 = (int *)(*a3 - 24LL);
    if ( (int *)(v33 - 24) != v22 )
    {
      if ( v22[4] >= 0 && *(_QWORD *)v21 == *(_QWORD *)v22 )
      {
        v23 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v33 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v22);
        *a3 = v23 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v33, *(unsigned int *)(v33 - 16));
      }
    }
    ATL::CStringData::Release(v21);
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v36);
    v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
    v15 = (ATL::CStringData *)(v32 - 24);
  }
  else
  {
    v14 = v32;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v13,
      "PushButtonReset::SerializeNode::GetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      682,
      L"Failed to construct full path to [%s] on volume [%s]",
      v32,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v36);
    v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
    v15 = (ATL::CStringData *)(v14 - 24);
  }
  ATL::CStringData::Release(v15);
  Property = v13;
LABEL_36:
  ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180051ab0  mov     [rsp-8+arg_18], rbx
0x180051ab5  push    rbp
0x180051ab6  push    rsi
0x180051ab7  push    rdi
0x180051ab8  push    r12
0x180051aba  push    r13
0x180051abc  push    r14
0x180051abe  push    r15
0x180051ac0  lea     rbp, [rsp-10h]
0x180051ac5  sub     rsp, 110h
0x180051acc  mov     rax, cs:__security_cookie
0x180051ad3  xor     rax, rsp
0x180051ad6  mov     [rbp+40h+var_40], rax
0x180051ada  mov     r12, r8
0x180051add  mov     rsi, rdx
0x180051ae0  mov     rdi, rcx
0x180051ae3  lea     r8, aSet; "Set"
0x180051aea  lea     rcx, [rsp+140h+var_C8]
0x180051aef  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180051af4  nop
0x180051af5  lea     r8, aPath; "Path"
0x180051afc  mov     rdx, rsi
0x180051aff  lea     rcx, [rsp+140h+var_D0]
0x180051b04  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180051b09  nop
0x180051b0a  xor     r13d, r13d
0x180051b0d  mov     [rsp+140h+var_100], r13b
0x180051b12  lea     r8, [rsp+140h+var_100]
0x180051b17  lea     rdx, [rsp+140h+var_C8]
0x180051b1c  mov     rcx, rdi
0x180051b1f  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x180051b24  mov     ebx, eax
0x180051b26  test    eax, eax
0x180051b28  jns     short loc_180051B5C
0x180051b2a  lea     rax, aFailedToReadWh; "Failed to read whether the path was set"
0x180051b31  mov     [rsp+140h+var_118], rax
0x180051b36  mov     [rsp+140h+var_120], 26Ch
0x180051b3e  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051b45  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051b4c  mov     edx, ebx
0x180051b4e  lea     ecx, [r13+2]
0x180051b52  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051b57  jmp     loc_180052057
0x180051b5c  cmp     [rsp+140h+var_100], r13b
0x180051b61  jnz     short loc_180051B7A
0x180051b63  xor     r8d, r8d
0x180051b66  lea     rdx, pszFormat
0x180051b6d  mov     rcx, r12
0x180051b70  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180051b75  jmp     loc_180052057
0x180051b7a  lea     rdx, [rsp+140h+var_D0]
0x180051b7f  mov     rcx, [rdi]
0x180051b82  call    ?HasAttribute@XmlNode@PushButtonReset@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::XmlNode::HasAttribute(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180051b87  test    al, al
0x180051b89  jnz     short loc_180051B95
0x180051b8b  mov     ebx, 80070490h
0x180051b90  jmp     loc_180052057
0x180051b95  mov     [rsp+140h+var_F8], r13d
0x180051b9a  mov     [rsp+140h+var_D8], r13
0x180051b9f  lea     r9, [rsp+140h+var_D8]
0x180051ba4  lea     r8, [rsp+140h+var_F8]
0x180051ba9  mov     rdx, rsi
0x180051bac  mov     rcx, rdi
0x180051baf  call    ?GetPartition@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAKPEA_K@Z; PushButtonReset::SerializeNode::GetPartition(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *,unsigned __int64 *)
0x180051bb4  mov     ebx, eax
0x180051bb6  test    eax, eax
0x180051bb8  jns     short loc_180051BF5
0x180051bba  mov     rcx, [rsi]
0x180051bbd  mov     [rsp+140h+var_110], rcx
0x180051bc2  lea     rax, aFailedToLookUp_0; "Failed to look up disk + partition pair"...
0x180051bc9  mov     [rsp+140h+var_118], rax
0x180051bce  mov     [rsp+140h+var_120], 27Ch
0x180051bd6  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051bdd  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051be4  mov     edx, ebx
0x180051be6  mov     ecx, 2
0x180051beb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051bf0  jmp     loc_180052057
0x180051bf5  lea     rcx, [rsp+140h+var_E0]
0x180051bfa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180051bff  nop
0x180051c00  lea     r8, [rsp+140h+var_E0]
0x180051c05  lea     rdx, [rsp+140h+var_D0]
0x180051c0a  mov     rcx, rdi
0x180051c0d  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180051c12  mov     ebx, eax
0x180051c14  test    eax, eax
0x180051c16  jns     short loc_180051C64
0x180051c18  mov     rcx, [rsp+140h+var_D0]
0x180051c1d  mov     [rsp+140h+var_110], rcx
0x180051c22  lea     rax, aFailedToReadRe; "Failed to read relative path from [%s]"
0x180051c29  mov     [rsp+140h+var_118], rax
0x180051c2e  mov     [rsp+140h+var_120], 280h
0x180051c36  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051c3d  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051c44  mov     edx, ebx
0x180051c46  mov     ecx, 2
0x180051c4b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051c50  nop
0x180051c51  mov     rcx, [rsp+140h+var_E0]
0x180051c56  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180051c5a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051c5f  jmp     loc_180052057
0x180051c64  mov     [rsp+140h+var_E8], r13
0x180051c69  lea     r14, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180051c70  mov     [rsp+140h+var_F0], r14
0x180051c75  lea     rcx, [rsp+140h+var_F0]
0x180051c7a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180051c7f  mov     r8, rax; struct PushButtonReset::Partition **
0x180051c82  mov     rsi, [rsp+140h+var_D8]
0x180051c87  mov     rdx, rsi; unsigned __int64
0x180051c8a  mov     edi, [rsp+140h+var_F8]
0x180051c8e  mov     ecx, edi; unsigned int
0x180051c90  call    ?FindByOffset@Partition@PushButtonReset@@SAJK_KPEAPEAV12@@Z; PushButtonReset::Partition::FindByOffset(ulong,unsigned __int64,PushButtonReset::Partition * *)
0x180051c95  mov     ebx, eax
0x180051c97  test    eax, eax
0x180051c99  jns     short loc_180051CE7
0x180051c9b  mov     dword ptr [rsp+140h+var_108], edi
0x180051c9f  mov     [rsp+140h+var_110], rsi
0x180051ca4  lea     rax, aFailedToLookUp_7; "Failed to look up partition at offset ["...
0x180051cab  mov     [rsp+140h+var_118], rax
0x180051cb0  mov     [rsp+140h+var_120], 286h
0x180051cb8  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051cbf  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051cc6  mov     edx, ebx
0x180051cc8  mov     ecx, 2
0x180051ccd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051cd2  nop
0x180051cd3  mov     [rsp+140h+var_F0], r14
0x180051cd8  lea     rcx, [rsp+140h+var_F0]
0x180051cdd  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180051ce2  jmp     loc_180051C51
0x180051ce7  lea     rcx, [rbp+40h+var_C0]; this
0x180051ceb  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180051cf0  nop
0x180051cf1  mov     rax, [rsp+140h+var_F0]
0x180051cf6  lea     rcx, [rsp+140h+var_F0]
0x180051cfb  mov     rax, [rax+18h]
0x180051cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d04  lea     rdx, [rbp+40h+var_C0]; struct PushButtonReset::PartitionInfo *
0x180051d08  mov     rcx, rax; this
0x180051d0b  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x180051d10  mov     esi, eax
0x180051d12  test    eax, eax
0x180051d14  jns     loc_180051DAC
0x180051d1a  mov     rcx, [rsp+140h+var_F0]
0x180051d1f  mov     rax, [rcx+18h]
0x180051d23  lea     rcx, [rsp+140h+var_F0]
0x180051d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d2d  mov     ebx, [rax+10h]
0x180051d30  mov     rcx, [rsp+140h+var_F0]
0x180051d35  mov     rax, [rcx+18h]
0x180051d39  lea     rcx, [rsp+140h+var_F0]
0x180051d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d43  mov     dword ptr [rsp+140h+var_108], ebx
0x180051d47  mov     eax, [rax+68h]
0x180051d4a  mov     dword ptr [rsp+140h+var_110], eax
0x180051d4e  lea     rax, aFailedToGetInf_2; "Failed to get info for partition [%u] o"...
0x180051d55  mov     [rsp+140h+var_118], rax
0x180051d5a  mov     [rsp+140h+var_120], 28Ch
0x180051d62  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051d69  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051d70  mov     edx, esi
0x180051d72  mov     ecx, 2
0x180051d77  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051d7c  nop
0x180051d7d  lea     rcx, [rbp+40h+var_C0]; this
0x180051d81  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180051d86  nop
0x180051d87  mov     [rsp+140h+var_F0], r14
0x180051d8c  lea     rcx, [rsp+140h+var_F0]
0x180051d91  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180051d96  nop
0x180051d97  mov     rcx, [rsp+140h+var_E0]
0x180051d9c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180051da0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051da5  mov     ebx, esi
0x180051da7  jmp     loc_180052057
0x180051dac  lea     rcx, [rsp+140h+var_F8]
0x180051db1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180051db6  nop
0x180051db7  movzx   eax, [rbp+40h+var_60]
0x180051dbb  test    ax, ax
0x180051dbe  jz      loc_180051E82
0x180051dc4  mov     r8d, eax
0x180051dc7  lea     rdx, aC; "%c:\\"
0x180051dce  lea     rcx, [rsp+140h+var_F8]
0x180051dd3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180051dd8  mov     rdi, qword ptr [rsp+140h+var_F8]
0x180051ddd  lea     rcx, [rsp+140h+var_D8]
0x180051de2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180051de7  nop
0x180051de8  lea     r8, [rsp+140h+var_D8]
0x180051ded  lea     rdx, [rsp+140h+var_E0]
0x180051df2  lea     rcx, [rsp+140h+var_F8]
0x180051df7  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180051dfc  mov     r15d, eax
0x180051dff  test    eax, eax
0x180051e01  jns     loc_180051FC4
0x180051e07  mov     [rsp+140h+var_108], rdi
0x180051e0c  mov     rbx, [rsp+140h+var_E0]
0x180051e11  mov     [rsp+140h+var_110], rbx
0x180051e16  lea     rax, aFailedToConstr_16; "Failed to construct full path to [%s] o"...
0x180051e1d  mov     [rsp+140h+var_118], rax
0x180051e22  mov     [rsp+140h+var_120], 2AAh
0x180051e2a  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051e31  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051e38  mov     edx, r15d
0x180051e3b  mov     ecx, 2
0x180051e40  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051e45  nop
0x180051e46  mov     rcx, [rsp+140h+var_D8]
0x180051e4b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180051e4f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051e54  nop
0x180051e55  lea     rcx, [rdi-18h]; this
0x180051e59  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051e5e  nop
0x180051e5f  lea     rcx, [rbp+40h+var_C0]; this
0x180051e63  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180051e68  nop
0x180051e69  mov     [rsp+140h+var_F0], r14
0x180051e6e  lea     rcx, [rsp+140h+var_F0]
0x180051e73  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180051e78  nop
0x180051e79  lea     rcx, [rbx-18h]
0x180051e7d  jmp     loc_18005204F
0x180051e82  mov     rdx, [rbp+40h+var_50]
0x180051e86  mov     r8d, [rdx-10h]
0x180051e8a  test    r8d, r8d
0x180051e8d  jle     short loc_180051EE0
0x180051e8f  lea     rcx, [rdx-18h]
0x180051e93  mov     rdi, qword ptr [rsp+140h+var_F8]
0x180051e98  lea     rbx, [rdi-18h]
0x180051e9c  cmp     rcx, rbx
0x180051e9f  jz      loc_180051DDD
0x180051ea5  cmp     [rbx+10h], r13d
0x180051ea9  jl      short loc_180051ED1
0x180051eab  mov     rax, [rbx]
0x180051eae  cmp     [rcx], rax
0x180051eb1  jnz     short loc_180051ED1
0x180051eb3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180051eb8  mov     rdi, rax
0x180051ebb  mov     rcx, rbx; this
0x180051ebe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051ec3  add     rdi, 18h
0x180051ec7  mov     qword ptr [rsp+140h+var_F8], rdi
0x180051ecc  jmp     loc_180051DDD
0x180051ed1  lea     rcx, [rsp+140h+var_F8]
0x180051ed6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180051edb  jmp     loc_180051DD8
0x180051ee0  mov     rax, [rsp+140h+var_F0]
0x180051ee5  lea     rcx, [rsp+140h+var_F0]
0x180051eea  mov     rax, [rax+18h]
0x180051eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ef3  mov     r9d, [rax+68h]
0x180051ef7  mov     r8d, edi
0x180051efa  lea     rdx, aGlobalrootDevi_0; "\\\\?\\GLOBALROOT\\device\\harddisk%u\\"...
0x180051f01  lea     rcx, [rsp+140h+var_F8]
0x180051f06  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180051f0b  lea     rcx, [rsp+140h+var_F8]
0x180051f10  call    ?Exists@Path@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Path::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180051f15  test    al, al
0x180051f17  jnz     loc_180051DD8
0x180051f1d  mov     rax, [rsp+140h+var_F0]
0x180051f22  lea     rcx, [rsp+140h+var_F0]
0x180051f27  mov     rax, [rax+18h]
0x180051f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f30  mov     ebx, [rax+68h]
0x180051f33  mov     rax, [rsp+140h+var_F0]
0x180051f38  lea     rcx, [rsp+140h+var_F0]
0x180051f3d  mov     rax, [rax+18h]
0x180051f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f46  mov     dword ptr [rsp+140h+var_108], ebx
0x180051f4a  mov     eax, [rax+10h]
0x180051f4d  mov     dword ptr [rsp+140h+var_110], eax
0x180051f51  lea     rax, aDiskUPartition; "Disk [%u] partition [%u] does not have "...
0x180051f58  mov     [rsp+140h+var_118], rax
0x180051f5d  mov     [rsp+140h+var_120], 2A2h
0x180051f65  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180051f6c  lea     r8, aPushbuttonrese_5; "PushButtonReset::SerializeNode::GetPath"
0x180051f73  mov     edx, 8007000Dh
0x180051f78  mov     ecx, 2
0x180051f7d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180051f82  nop
0x180051f83  mov     rcx, qword ptr [rsp+140h+var_F8]
0x180051f88  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180051f8c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051f91  nop
0x180051f92  lea     rcx, [rbp+40h+var_C0]; this
0x180051f96  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180051f9b  nop
0x180051f9c  mov     [rsp+140h+var_F0], r14
0x180051fa1  lea     rcx, [rsp+140h+var_F0]
0x180051fa6  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180051fab  nop
0x180051fac  mov     rcx, [rsp+140h+var_E0]
0x180051fb1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180051fb5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180051fba  mov     ebx, 8007000Dh
  ... truncated ...
```
