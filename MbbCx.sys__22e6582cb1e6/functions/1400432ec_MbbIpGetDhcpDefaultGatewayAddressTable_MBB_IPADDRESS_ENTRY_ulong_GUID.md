# MbbIpGetDhcpDefaultGatewayAddressTable(_MBB_IPADDRESS_ENTRY * *,ulong *,_GUID *)

- ea: `0x1400432ec`
- end: `0x14004395c`
- name: `?MbbIpGetDhcpDefaultGatewayAddressTable@@YAHPEAPEAU_MBB_IPADDRESS_ENTRY@@PEAKPEAU_GUID@@@Z`
- size: `1648`
- prototype: `__int64 __fastcall(struct _MBB_IPADDRESS_ENTRY **, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x140046d80`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x1400051ac`
- `0x1400075c0`
- `0x14004253c`
- `0x1400432ec`
- `0x140046000`
- `0x1400460b8`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400434bc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400434bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400434ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400434ac`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x14004356f`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400437d1`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x14004356f`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400437d1`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400434d9`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140043558`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x1400436cc`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140043558`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x1400436cc`
- `ntoskrnl!ExAllocatePool2` at `0x140043621`
- `ntoskrnl!ExAllocatePool2` at `0x140043621`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043910`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043926`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043910`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043926`

## string_xrefs

- `0x14004346e`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall MbbIpGetDhcpDefaultGatewayAddressTable(
        struct _MBB_IPADDRESS_ENTRY **a1,
        unsigned int *a2,
        struct _GUID *a3)
{
  unsigned __int16 *v4; // r13
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  struct _MBB_IPADDRESS_ENTRY *v7; // r12
  unsigned int v8; // eax
  __int64 *v9; // rdx
  unsigned int v10; // edi
  unsigned int v11; // eax
  int v12; // edx
  unsigned int i; // edi
  PCWSTR *v14; // rax
  PVOID v15; // rbx
  PVOID SystemRoutineAddress; // rax
  int v17; // eax
  int v18; // edx
  const WCHAR *v19; // rax
  NTSTATUS v20; // eax
  __int64 v21; // rax
  int v22; // edx
  const WCHAR *v23; // rax
  char *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // r13
  __int64 v27; // r12
  char *v28; // rdi
  NTSTATUS v29; // eax
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rcx
  const WCHAR *v33; // rcx
  __int64 v34; // r13
  unsigned int v35; // edi
  PCWSTR *v36; // r14
  __int64 v37; // r12
  NTSTATUS v38; // eax
  int v39; // edx
  int v40; // r8d
  __int64 v41; // rdx
  unsigned int v42; // eax
  unsigned int *v43; // rcx
  int v45; // [rsp+20h] [rbp-E0h]
  LPCWSTR Terminator; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v49; // [rsp+58h] [rbp-A8h]
  unsigned int v50; // [rsp+5Ch] [rbp-A4h]
  unsigned int v51; // [rsp+60h] [rbp-A0h]
  __int64 Pool2; // [rsp+68h] [rbp-98h]
  PCWSTR *v53; // [rsp+70h] [rbp-90h]
  struct in_addr Addr; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+80h] [rbp-80h] BYREF
  struct _MBB_IPADDRESS_ENTRY **v56; // [rsp+88h] [rbp-78h]
  unsigned int *v57; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR S[2]; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v60[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-30h] BYREF
  int v62; // [rsp+D8h] [rbp-28h]
  const wchar_t *v63; // [rsp+E0h] [rbp-20h]
  PCWSTR *v64; // [rsp+E8h] [rbp-18h]
  int v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  int v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  int v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+118h] [rbp+18h]
  __int64 v71; // [rsp+120h] [rbp+20h]
  int v72; // [rsp+128h] [rbp+28h]
  __int64 v73; // [rsp+130h] [rbp+30h]
  int v74; // [rsp+138h] [rbp+38h]
  struct in6_addr v75; // [rsp+140h] [rbp+40h] BYREF

  v57 = a2;
  v56 = a1;
  v47 = 0;
  Terminator = 0;
  P = 0;
  v48 = 0;
  Addr = 0;
  Pool2 = 0;
  v4 = 0;
  v5 = 0;
  *(_OWORD *)S = 0;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)v60 = 0;
  v75 = 0;
  v8 = MbbIpBuildInterfaceRegistryPath(a3, 0, &v47, (unsigned __int16 **)&P);
  v9 = WPP_f53708f2277a3aabca584f524242a299_Traceguids;
  v10 = v8;
  if ( !v8 )
  {
    v11 = MbbIpBuildInterfaceRegistryPath(a3, 1, &v47, &v48);
    v10 = v11;
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          2,
          31,
          (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
          v11);
      }
LABEL_65:
      v4 = v48;
      goto LABEL_66;
    }
    v4 = v48;
    for ( i = 0; i < 2; ++i )
    {
      while ( 1 )
      {
        v47 = 0;
        v61 = 0;
        v62 = 304;
        v14 = v60;
        v65 = 117440519;
        if ( !i )
          v14 = S;
        v66 = 0;
        v53 = v14;
        v63 = L"DhcpDefaultGateway";
        v15 = v4;
        v64 = v14;
        if ( !i )
          v15 = P;
        v6 = 0;
        v67 = 0;
        v68 = 0;
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v72 = 0;
        v73 = 0;
        v74 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
        SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
        v45 = 0;
        if ( !SystemRoutineAddress )
          SystemRoutineAddress = RtlQueryRegistryValues;
        v17 = ((__int64 (__fastcall *)(_QWORD, PVOID, __int64 *, _QWORD))SystemRoutineAddress)(0, v15, &v61, 0);
        v18 = v17;
        if ( v17 >= 0 )
        {
          v19 = v53[1];
          Terminator = v19;
          while ( 1 )
          {
            v20 = i
                ? RtlIpv6StringToAddressW(v19, &Terminator, &v75)
                : RtlIpv4StringToAddressW(v19, 1u, &Terminator, &Addr);
            if ( v20 )
              break;
            ++v6;
            v19 = Terminator + 1;
            v47 = v6;
            Terminator = v19;
            if ( !*v19 )
              goto LABEL_28;
          }
          if ( !v6 && *Terminator && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dD(WPP_GLOBAL_Control->DeviceExtension, v20, 0, 33, 0, v20, i != 0 ? 6 : 4);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 3;
          WPP_RECORDER_SF_DD(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            2,
            32,
            (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
            i != 0 ? 6 : 4,
            v17);
        }
LABEL_28:
        if ( i )
          break;
        v5 = v6;
        i = 1;
      }
    }
    v21 = v5 + v6;
    v7 = 0;
    v49 = v21;
    if ( (_DWORD)v21 )
    {
      Pool2 = ExAllocatePool2(256, 24 * v21, 1682129485);
      v7 = (struct _MBB_IPADDRESS_ENTRY *)Pool2;
      if ( !Pool2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v22) = 3;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            2,
            34,
            (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids);
        }
        v10 = -1073741670;
        v5 = 0;
        v6 = 0;
        goto LABEL_66;
      }
    }
    v23 = S[1];
    v24 = (char *)v7 + 8;
    Terminator = S[1];
    v10 = 0;
    v53 = (PCWSTR *)((char *)v7 + 8);
    v25 = 0;
    v51 = 0;
    v50 = v5;
    if ( v5 )
    {
      v26 = Pool2;
      v27 = 0;
      v28 = v24;
      while ( 1 )
      {
        v29 = RtlIpv4StringToAddressW(v23, 1u, &Terminator, (struct in_addr *)&v28[24 * v27]);
        if ( v29 )
        {
          if ( !v25 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v30) = 3;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v30,
              2,
              36,
              (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
              v29);
          }
          v32 = 3 * v27;
          *(_DWORD *)&v28[24 * v27] = 0;
        }
        else
        {
          v23 = Terminator;
          if ( *Terminator )
            v23 = ++Terminator;
          v32 = 3 * v27;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_48;
          WPP_RECORDER_SF__IPV4_(WPP_GLOBAL_Control->DeviceExtension, v30, v31, 35, v45, (__int64)&v28[24 * v27]);
          v32 = 3 * v27;
        }
        v23 = Terminator;
LABEL_48:
        *(_DWORD *)(v26 + 8 * v32) &= 0xFFFFFFFC;
        ++v25;
        ++v27;
        if ( v25 >= v5 )
        {
          v6 = v47;
          v10 = v51;
          v4 = v48;
          v7 = (struct _MBB_IPADDRESS_ENTRY *)Pool2;
          goto LABEL_51;
        }
      }
    }
    v53 = (PCWSTR *)((char *)v7 + 8);
    v47 = v6;
LABEL_51:
    v33 = v60[1];
    Terminator = v60[1];
    if ( v25 >= v49 )
      goto LABEL_66;
    v34 = Pool2;
    v35 = v49;
    v36 = v53;
    v37 = v25;
    while ( 1 )
    {
      v38 = RtlIpv6StringToAddressW(v33, &Terminator, (struct in6_addr *)&v36[3 * v37]);
      if ( v38 )
      {
        if ( !v25 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v39) = 3;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v39,
            2,
            38,
            (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
            v38);
        }
        *(_OWORD *)&v36[3 * v37] = 0;
      }
      else
      {
        v33 = Terminator;
        if ( *Terminator )
          v33 = ++Terminator;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_63;
        WPP_RECORDER_SF__IPV6_(
          WPP_GLOBAL_Control->DeviceExtension,
          3 * v37,
          v40,
          37,
          (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
          (__int64)&v36[3 * v37]);
      }
      v33 = Terminator;
LABEL_63:
      ++v25;
      v41 = 3 * v37;
      v42 = *(_DWORD *)(v34 + 24 * v37++) & 0xFFFFFFFD;
      *(_DWORD *)(v34 + 8 * v41) = v42 | 1;
      if ( v25 >= v35 )
      {
        v5 = v50;
        v6 = v47;
        v10 = v51;
        v7 = (struct _MBB_IPADDRESS_ENTRY *)Pool2;
        goto LABEL_65;
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_67;
  LOBYTE(v9) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    (_DWORD)v9,
    2,
    30,
    (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
    v8);
LABEL_66:
  v9 = WPP_f53708f2277a3aabca584f524242a299_Traceguids;
LABEL_67:
  v43 = v57;
  *v56 = v7;
  *v43 = v6 + v5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      2,
      39,
      (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
      v5,
      v6);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return v10;
}

```

## disassembly

```asm
0x1400432ec  mov     [rsp-8+arg_18], rbx
0x1400432f1  push    rbp
0x1400432f2  push    rsi
0x1400432f3  push    rdi
0x1400432f4  push    r12
0x1400432f6  push    r13
0x1400432f8  push    r14
0x1400432fa  push    r15
0x1400432fc  lea     rbp, [rsp-60h]
0x140043301  sub     rsp, 160h
0x140043308  mov     rax, cs:__security_cookie
0x14004330f  xor     rax, rsp
0x140043312  mov     [rbp+90h+var_40], rax
0x140043316  xor     esi, esi
0x140043318  mov     [rbp+90h+var_100], rdx
0x14004331c  mov     rbx, r8
0x14004331f  mov     [rbp+90h+var_108], rcx
0x140043323  xorps   xmm0, xmm0
0x140043326  mov     [rsp+190h+var_148], esi
0x14004332a  xorps   xmm1, xmm1
0x14004332d  mov     [rsp+190h+Terminator], rsi
0x140043332  mov     rcx, rbx; Guid
0x140043335  mov     [rbp+90h+P], rsi
0x140043339  lea     r9, [rbp+90h+P]; unsigned __int16 **
0x14004333d  mov     [rsp+190h+var_140], rsi
0x140043342  lea     r8, [rsp+190h+var_148]; unsigned int *
0x140043347  mov     dword ptr [rsp+190h+Addr.S_un], esi
0x14004334b  xor     edx, edx; unsigned __int8
0x14004334d  mov     [rsp+190h+var_128], rsi
0x140043352  mov     r13d, esi
0x140043355  mov     r14d, esi
0x140043358  movups  xmmword ptr [rbp+90h+S], xmm0
0x14004335c  mov     r15d, esi
0x14004335f  mov     r12d, esi
0x140043362  movups  xmmword ptr [rbp+90h+var_D8], xmm1
0x140043366  movups  xmmword ptr [rbp+90h+var_50.u], xmm0
0x14004336a  call    ?MbbIpBuildInterfaceRegistryPath@@YAJPEAU_GUID@@EPEAKPEAPEAG@Z; MbbIpBuildInterfaceRegistryPath(_GUID *,uchar,ulong *,ushort * *)
0x14004336f  lea     rdx, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043376  mov     edi, eax
0x140043378  test    eax, eax
0x14004337a  jz      short loc_1400433BB
0x14004337c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140043383  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14004338a  jz      loc_1400438BD
0x140043390  mov     rcx, cs:WPP_GLOBAL_Control
0x140043397  lea     r8d, [r12+2]
0x14004339c  mov     dword ptr [rsp+190h+var_168], eax
0x1400433a0  lea     r9d, [r12+1Eh]
0x1400433a5  mov     [rsp+190h+var_170], rdx
0x1400433aa  mov     dl, r8b
0x1400433ad  mov     rcx, [rcx+40h]
0x1400433b1  call    WPP_RECORDER_SF_d
0x1400433b6  jmp     loc_1400438B6
0x1400433bb  lea     r9, [rsp+190h+var_140]; unsigned __int16 **
0x1400433c0  mov     dl, 1; unsigned __int8
0x1400433c2  lea     r8, [rsp+190h+var_148]; unsigned int *
0x1400433c7  mov     rcx, rbx; Guid
0x1400433ca  call    ?MbbIpBuildInterfaceRegistryPath@@YAJPEAU_GUID@@EPEAKPEAPEAG@Z; MbbIpBuildInterfaceRegistryPath(_GUID *,uchar,ulong *,ushort * *)
0x1400433cf  xor     r8d, r8d
0x1400433d2  mov     edi, eax
0x1400433d4  test    eax, eax
0x1400433d6  jz      short loc_14004341C
0x1400433d8  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400433df  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400433e6  jz      loc_1400438B1
0x1400433ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400433f3  lea     r9d, [r8+1Fh]
0x1400433f7  mov     dword ptr [rsp+190h+var_168], eax
0x1400433fb  lea     r8d, [r9-1Dh]
0x1400433ff  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043406  mov     dl, r8b
0x140043409  mov     [rsp+190h+var_170], rax
0x14004340e  mov     rcx, [rcx+40h]
0x140043412  call    WPP_RECORDER_SF_d
0x140043417  jmp     loc_1400438B1
0x14004341c  mov     r13, [rsp+190h+var_140]
0x140043421  lea     rsi, WPP_RECORDER_INITIALIZED
0x140043428  mov     edi, r8d
0x14004342b  lea     r12, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043432  test    edi, edi
0x140043434  mov     [rsp+190h+var_148], r8d
0x140043439  lea     rcx, [rbp+90h+S]
0x14004343d  mov     [rbp+90h+var_C0], r8
0x140043441  xorps   xmm0, xmm0
0x140043444  mov     [rbp+90h+var_B8], 130h
0x14004344b  lea     rax, [rbp+90h+var_D8]
0x14004344f  mov     [rbp+90h+var_A0], 7000007h
0x140043456  cmovz   rax, rcx
0x14004345a  mov     [rbp+90h+var_98], r8
0x14004345e  lea     rcx, aDhcpdefaultgat; "DhcpDefaultGateway"
0x140043465  mov     [rsp+190h+var_120], rax
0x14004346a  mov     [rbp+90h+var_B0], rcx
0x14004346e  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140043475  mov     rbx, r13
0x140043478  mov     [rbp+90h+var_A8], rax
0x14004347c  cmovz   rbx, [rbp+90h+P]
0x140043481  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x140043485  mov     r15d, r8d
0x140043488  mov     [rbp+90h+var_90], r8d
0x14004348c  mov     [rbp+90h+var_88], r8
0x140043490  mov     [rbp+90h+var_80], r8d
0x140043494  mov     [rbp+90h+var_78], r8
0x140043498  mov     [rbp+90h+var_70], r8
0x14004349c  mov     [rbp+90h+var_68], r8d
0x1400434a0  mov     [rbp+90h+var_60], r8
0x1400434a4  mov     [rbp+90h+var_58], r8d
0x1400434a8  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1400434ac  call    cs:__imp_RtlInitUnicodeString
0x1400434b3  nop     dword ptr [rax+rax+00h]
0x1400434b8  lea     rcx, [rbp+90h+DestinationString]; SystemRoutineName
0x1400434bc  call    cs:__imp_MmGetSystemRoutineAddress
0x1400434c3  nop     dword ptr [rax+rax+00h]
0x1400434c8  xor     ecx, ecx
0x1400434ca  lea     r8, [rbp+90h+var_C0]
0x1400434ce  test    rax, rax
0x1400434d1  mov     [rsp+190h+var_170], rcx
0x1400434d6  mov     rdx, rbx
0x1400434d9  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400434e1  xor     r9d, r9d
0x1400434e4  call    _guard_dispatch_icall
0x1400434e9  xor     r8d, r8d
0x1400434ec  mov     edx, eax
0x1400434ee  test    eax, eax
0x1400434f0  jns     short loc_140043537
0x1400434f2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400434f9  jz      loc_1400435E6
0x1400434ff  mov     [rsp+190h+var_160], edx
0x140043503  lea     r9d, [r8+20h]
0x140043507  mov     eax, edi
0x140043509  lea     r8d, [r9-1Eh]
0x14004350d  neg     eax
0x14004350f  mov     dl, 3
0x140043511  sbb     ecx, ecx
0x140043513  and     ecx, 2
0x140043516  add     ecx, 4
0x140043519  mov     dword ptr [rsp+190h+var_168], ecx
0x14004351d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043524  mov     [rsp+190h+var_170], r12
0x140043529  mov     rcx, [rcx+40h]
0x14004352d  call    WPP_RECORDER_SF_DD
0x140043532  jmp     loc_1400435E3
0x140043537  mov     rax, [rsp+190h+var_120]
0x14004353c  mov     rax, [rax+8]
0x140043540  mov     [rsp+190h+Terminator], rax
0x140043545  mov     rcx, rax; S
0x140043548  test    edi, edi
0x14004354a  jnz     short loc_140043566
0x14004354c  lea     r9, [rsp+190h+Addr]; Addr
0x140043551  mov     dl, 1; Strict
0x140043553  lea     r8, [rsp+190h+Terminator]; Terminator
0x140043558  call    cs:__imp_RtlIpv4StringToAddressW
0x14004355f  nop     dword ptr [rax+rax+00h]
0x140043564  jmp     short loc_14004357B
0x140043566  lea     r8, [rbp+90h+var_50]; Addr
0x14004356a  lea     rdx, [rsp+190h+Terminator]; Terminator
0x14004356f  call    cs:__imp_RtlIpv6StringToAddressW
0x140043576  nop     dword ptr [rax+rax+00h]
0x14004357b  xor     r8d, r8d
0x14004357e  mov     edx, eax
0x140043580  test    eax, eax
0x140043582  jnz     short loc_1400435A2
0x140043584  mov     rax, [rsp+190h+Terminator]
0x140043589  inc     r15d
0x14004358c  add     rax, 2
0x140043590  mov     [rsp+190h+var_148], r15d
0x140043595  mov     [rsp+190h+Terminator], rax
0x14004359a  cmp     [rax], r8w
0x14004359e  jnz     short loc_140043545
0x1400435a0  jmp     short loc_1400435E6
0x1400435a2  test    r15d, r15d
0x1400435a5  jnz     short loc_1400435E6
0x1400435a7  mov     rax, [rsp+190h+Terminator]
0x1400435ac  cmp     [rax], r8w
0x1400435b0  jz      short loc_1400435E6
0x1400435b2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400435b9  jz      short loc_1400435E6
0x1400435bb  mov     eax, edi
0x1400435bd  lea     r9d, [r15+21h]
0x1400435c1  neg     eax
0x1400435c3  sbb     ecx, ecx
0x1400435c5  and     ecx, 2
0x1400435c8  add     ecx, 4
0x1400435cb  mov     [rsp+190h+var_160], ecx
0x1400435cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400435d6  mov     dword ptr [rsp+190h+var_168], edx
0x1400435da  mov     rcx, [rcx+40h]
0x1400435de  call    WPP_RECORDER_SF_dD
0x1400435e3  xor     r8d, r8d
0x1400435e6  test    edi, edi
0x1400435e8  jnz     short loc_1400435F4
0x1400435ea  mov     r14d, r15d
0x1400435ed  inc     edi
0x1400435ef  jmp     loc_140043432
0x1400435f4  inc     edi
0x1400435f6  cmp     edi, 2
0x1400435f9  jb      loc_140043432
0x1400435ff  lea     eax, [r14+r15]
0x140043603  mov     r12, r8
0x140043606  mov     [rsp+190h+var_138], eax
0x14004360a  test    eax, eax
0x14004360c  jz      short loc_140043680
0x14004360e  lea     rdx, [rax+rax*2]
0x140043612  mov     ecx, 100h
0x140043617  shl     rdx, 3
0x14004361b  mov     r8d, 6443424Dh
0x140043621  call    cs:__imp_ExAllocatePool2
0x140043628  nop     dword ptr [rax+rax+00h]
0x14004362d  xor     r8d, r8d
0x140043630  mov     [rsp+190h+var_128], rax
0x140043635  mov     r12, rax
0x140043638  test    rax, rax
0x14004363b  jnz     short loc_140043680
0x14004363d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140043644  jz      short loc_140043670
0x140043646  mov     rcx, cs:WPP_GLOBAL_Control
0x14004364d  lea     r9d, [rax+22h]
0x140043651  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043658  mov     dl, 3
0x14004365a  lea     r8d, [r12+2]
0x14004365f  mov     [rsp+190h+var_170], rax
0x140043664  mov     rcx, [rcx+40h]
0x140043668  call    WPP_RECORDER_SF_
0x14004366d  xor     r8d, r8d
0x140043670  mov     edi, 0C000009Ah
0x140043675  mov     r14d, r8d
0x140043678  mov     r15d, r8d
0x14004367b  jmp     loc_1400438B6
0x140043680  mov     rax, [rbp+90h+S+8]
0x140043684  lea     rcx, [r12+8]
0x140043689  mov     [rsp+190h+Terminator], rax
0x14004368e  mov     edi, r8d
0x140043691  mov     [rsp+190h+var_120], rcx
0x140043696  mov     ebx, r8d
0x140043699  mov     [rsp+190h+var_130], r8d
0x14004369e  mov     [rsp+190h+var_134], r14d
0x1400436a3  test    r14d, r14d
0x1400436a6  jz      loc_140043793
0x1400436ac  mov     r13, [rsp+190h+var_128]
0x1400436b1  mov     r12, r8
0x1400436b4  mov     rdi, rcx
0x1400436b7  xor     r15d, r15d
0x1400436ba  lea     rcx, [r12+r12*2]
0x1400436be  mov     dl, 1; Strict
0x1400436c0  lea     r9, [rdi+rcx*8]; Addr
0x1400436c4  mov     rcx, rax; S
0x1400436c7  lea     r8, [rsp+190h+Terminator]; Terminator
0x1400436cc  call    cs:__imp_RtlIpv4StringToAddressW
0x1400436d3  nop     dword ptr [rax+rax+00h]
0x1400436d8  test    eax, eax
0x1400436da  jnz     short loc_140043722
0x1400436dc  mov     rax, [rsp+190h+Terminator]
0x1400436e1  cmp     [rax], r15w
0x1400436e5  jz      short loc_1400436F0
0x1400436e7  add     rax, 2
0x1400436eb  mov     [rsp+190h+Terminator], rax
0x1400436f0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400436f7  lea     rcx, [r12+r12*2]
0x1400436fb  jz      short loc_14004376A
0x1400436fd  lea     rax, [rdi+rcx*8]
0x140043701  mov     r9d, 23h ; '#'
0x140043707  mov     rcx, cs:WPP_GLOBAL_Control
0x14004370e  mov     [rsp+190h+var_168], rax
0x140043713  mov     rcx, [rcx+40h]
0x140043717  call    WPP_RECORDER_SF__IPV4_
0x14004371c  lea     rcx, [r12+r12*2]
0x140043720  jmp     short loc_140043765
0x140043722  test    ebx, ebx
0x140043724  jnz     short loc_140043759
0x140043726  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14004372d  jz      short loc_140043759
0x14004372f  mov     rcx, cs:WPP_GLOBAL_Control
0x140043736  lea     r9d, [rbx+24h]
0x14004373a  mov     dword ptr [rsp+190h+var_168], eax
0x14004373e  lea     r8d, [rbx+2]
0x140043742  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043749  mov     dl, 3
0x14004374b  mov     [rsp+190h+var_170], rax
0x140043750  mov     rcx, [rcx+40h]
0x140043754  call    WPP_RECORDER_SF_d
0x140043759  lea     rcx, [r12+r12*2]
0x14004375d  xor     edx, edx
0x14004375f  lea     rax, [rdi+rcx*8]
0x140043763  mov     [rax], edx
0x140043765  mov     rax, [rsp+190h+Terminator]
0x14004376a  and     dword ptr [r13+rcx*8+0], 0FFFFFFFCh
0x140043770  inc     ebx
0x140043772  inc     r12
0x140043775  cmp     ebx, r14d
0x140043778  jb      loc_1400436BA
0x14004377e  mov     r15d, [rsp+190h+var_148]
0x140043783  mov     edi, [rsp+190h+var_130]
0x140043787  mov     r13, [rsp+190h+var_140]
0x14004378c  mov     r12, [rsp+190h+var_128]
0x140043791  jmp     short loc_14004379D
0x140043793  mov     [rsp+190h+var_120], rcx
0x140043798  mov     [rsp+190h+var_148], r15d
0x14004379d  mov     rcx, [rbp+90h+var_D8+8]; S
0x1400437a1  mov     [rsp+190h+Terminator], rcx
0x1400437a6  cmp     ebx, [rsp+190h+var_138]
0x1400437aa  jnb     loc_1400438B6
  ... truncated ...
```
