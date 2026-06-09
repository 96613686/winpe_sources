# IPxlatInterfaceMgr::Enable464xlat(unsigned __int64,ulong,_IPV6_PREFIX *,_IPV6_PREFIX *,_IPXLAT_TRIGGER_SOURCE)

- ea: `0x18000f9f0`
- end: `0x18000fde7`
- name: `?Enable464xlat@IPxlatInterfaceMgr@@QEAAK_KKPEAU_IPV6_PREFIX@@1W4_IPXLAT_TRIGGER_SOURCE@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, __int64, void *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c590`
- `0x18000c7d0`

## callees

- `0x180002110`
- `0x18000214c`
- `0x18000b12c`
- `0x18000e91c`
- `0x18000f9f0`
- `0x180011dc0`
- `0x180011fdc`
- `0x180012388`
- `0x1800128d0`
- `0x1800132ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fafb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fda0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fdb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fafb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fda0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fdb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa48`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000fd96`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000fd96`

## string_xrefs

- `0x18000fb1a`: `Enable464xlat: 464xlat is already enabled on this interface`

## pseudocode

```c
__int64 __fastcall IPxlatInterfaceMgr::Enable464xlat(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        void *a5,
        int a6)
{
  const char *v8; // r8
  struct _RTL_CRITICAL_SECTION *v9; // r12
  __int64 result; // rax
  __int64 *v11; // rdx
  __int64 *v12; // rax
  __int64 *v13; // rcx
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rax
  int v17; // ebx
  IPxlatInterface *v18; // rax
  IPxlatInterface *v19; // rbx
  _DWORD *v20; // r13
  IPxlatInterface *v21; // rax
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  __int64 v26; // r9
  std::error_code *v27; // rax
  int v28; // ebx
  __int64 v29; // r8
  int v30; // eax
  int v31; // edx
  __int64 v32; // r9
  bool v33; // [rsp+50h] [rbp-88h]
  int v34; // [rsp+54h] [rbp-84h] BYREF
  void *v35; // [rsp+58h] [rbp-80h]
  void *v36; // [rsp+60h] [rbp-78h] BYREF
  IPxlatInterface *v37; // [rsp+68h] [rbp-70h]
  int v38; // [rsp+70h] [rbp-68h]
  int v39; // [rsp+74h] [rbp-64h]
  _BYTE v40[12]; // [rsp+78h] [rbp-60h] BYREF
  int v41; // [rsp+84h] [rbp-54h]
  const std::system_error *v42; // [rsp+90h] [rbp-48h] BYREF
  int v44; // [rsp+E8h] [rbp+10h]

  v44 = (int)a2;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0) )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v8 = "Enable464xlat: Interface manager is cleaning up";
LABEL_7:
      McTemplateU0sqx_EventWriteTransfer(a1, (_DWORD)a2, (_DWORD)v8, 1722, (char)a2);
      return 1722;
    }
    return 1722;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( *(_BYTE *)a1 )
  {
    LeaveCriticalSection(v9);
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v8 = "Enable464xlat: RPC is blocked";
      goto LABEL_7;
    }
    return 1722;
  }
  LOBYTE(v34) = 0;
  *(_WORD *)((char *)&v34 + 1) = 0;
  HIBYTE(v34) = 0;
  v33 = 0;
  v11 = *(__int64 **)(a1 + 128);
  v12 = (__int64 *)v11[1];
  v41 = 0;
  v13 = v11;
  while ( !*((_BYTE *)v12 + 25) )
  {
    if ( v12[4] >= (unsigned __int64)a2 )
    {
      v13 = v12;
      v12 = (__int64 *)*v12;
    }
    else
    {
      v12 = (__int64 *)v12[2];
    }
  }
  if ( *((_BYTE *)v13 + 25) || (unsigned __int64)a2 < v13[4] || v11 == v13 )
  {
    v16 = *(_QWORD *)(a1 + 104);
    try
    {
      while ( v16 != *(_QWORD *)(a1 + 112) )
      {
        if ( *(_BYTE *)(v16 + 4) )
        {
          v17 = *(_DWORD *)v16;
          v34 = *(_DWORD *)v16;
          *(_BYTE *)(v16 + 4) = 0;
          v33 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetImpl'::`2'::impl) != 0;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl) )
          {
            v35 = operator new(0xE8u);
            v18 = (IPxlatInterface *)IPxlatInterface::IPxlatInterface(
                                       (__int64)v35,
                                       (__int64)a2,
                                       a3,
                                       *(_DWORD *)(a1 + 96),
                                       v17,
                                       *(_BYTE *)(a1 + 100),
                                       a4,
                                       a5,
                                       a6);
            v36 = a2;
            v35 = 0;
            v37 = v18;
            std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(
              (__int64 *)(a1 + 128),
              (__int64)v40,
              (__int64 *)&v36);
            goto LABEL_27;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl'::`2'::impl) )
          {
            v20 = operator new(0xE8u);
            v36 = v20;
            LODWORD(v35) = *(_DWORD *)(a1 + 156);
            v39 = *(_DWORD *)(a1 + 152);
            v38 = *(_DWORD *)(a1 + 148);
            IPxlatInterface::IPxlatInterface(
              (__int64)v20,
              (__int64)a2,
              a3,
              *(_DWORD *)(a1 + 96),
              v17,
              *(_BYTE *)(a1 + 100),
              a4,
              a5,
              a6);
            v20[48] = v38;
            v20[49] = v39;
            v20[50] = (_DWORD)v35;
            v36 = a2;
            v35 = 0;
            v37 = (IPxlatInterface *)v20;
            std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(
              (__int64 *)(a1 + 128),
              (__int64)v40,
              (__int64 *)&v36);
LABEL_27:
            v19 = v37;
LABEL_31:
            if ( v19 )
            {
              IPxlatInterface::~IPxlatInterface(v19);
              operator delete(v19);
            }
          }
          else
          {
            v36 = operator new(0xE8u);
            v21 = (IPxlatInterface *)IPxlatInterface::IPxlatInterface(
                                       (__int64)v36,
                                       (__int64)a2,
                                       a3,
                                       *(_DWORD *)(a1 + 96),
                                       v17,
                                       *(_BYTE *)(a1 + 100),
                                       a4,
                                       a5,
                                       a6);
            v36 = a2;
            v35 = 0;
            v37 = v21;
            std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(
              (__int64 *)(a1 + 128),
              (__int64)v40,
              (__int64 *)&v36);
            v19 = v37;
            if ( v37 )
              goto LABEL_31;
          }
          if ( *(_QWORD *)(a1 + 136) == 1 )
            CancelWaitableTimer(*(HANDLE *)(a1 + 48));
          LeaveCriticalSection(v9);
          result = 0;
          goto LABEL_53;
        }
        v16 += 8;
      }
      LeaveCriticalSection(v9);
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        McTemplateU0sqx_EventWriteTransfer(
          v23,
          v22,
          (unsigned int)"Enable464xlat: No more IPv4 addresses available from the synthetic IPv4 address pool",
          259,
          (char)a2);
      result = 259;
    }
    catch ( const std::system_error *v42 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetImpl'::`2'::impl) )
        goto LABEL_44;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      {
        v27 = std::system_error::code(v42);
        v28 = std::error_code::value(v27);
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        McTemplateU0sqx_EventWriteTransfer(v44, v31, v30, v28, v44);
      }
      if ( v33 )
        IPxlatInterfaceMgr::UnblockSyntheticIPv4AddressFromPool((IPxlatInterfaceMgr *)a1, (struct in_addr *)&v34);
      else
LABEL_44:
        v32 = a1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 56));
      throw;
    }
    catch ( ... )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetImpl'::`2'::impl) )
        goto LABEL_51;
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        McTemplateU0sqx_EventWriteTransfer(
          v25,
          v24,
          (unsigned int)"Internal error occured while creating the interface object",
          1359,
          v44);
      if ( v33 )
        IPxlatInterfaceMgr::UnblockSyntheticIPv4AddressFromPool((IPxlatInterfaceMgr *)a1, (struct in_addr *)&v34);
      else
LABEL_51:
        v26 = a1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 56));
      throw;
    }
LABEL_53:
    ;
  }
  else
  {
    LeaveCriticalSection(v9);
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      McTemplateU0sqx_EventWriteTransfer(
        v15,
        v14,
        (unsigned int)"Enable464xlat: 464xlat is already enabled on this interface",
        183,
        (char)a2);
    return 183;
  }
  return result;
}

```

## disassembly

```asm
0x18000f9f0  mov     rax, rsp
0x18000f9f3  mov     [rax+20h], r9
0x18000f9f7  mov     [rax+18h], r8d
0x18000f9fb  mov     [rax+10h], rdx
0x18000f9ff  mov     [rax+8], rcx
0x18000fa03  push    rbx
0x18000fa04  push    rsi
0x18000fa05  push    rdi
0x18000fa06  push    r12
0x18000fa08  push    r13
0x18000fa0a  push    r14
0x18000fa0c  push    r15
0x18000fa0e  sub     rsp, 0A0h
0x18000fa15  mov     r14, rdx
0x18000fa18  mov     rsi, rcx
0x18000fa1b  xor     r15d, r15d
0x18000fa1e  mov     r10d, r15d
0x18000fa21  xor     eax, eax
0x18000fa23  lock cmpxchg [rcx+4], r10d
0x18000fa29  jnz     short loc_18000FA41
0x18000fa2b  lea     edi, [r15+1]
0x18000fa2f  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000fa36  jz      short loc_18000FA81
0x18000fa38  lea     r8, aEnable464xlatI_0; "Enable464xlat: Interface manager is cle"...
0x18000fa3f  jmp     short loc_18000FA71
0x18000fa41  lea     r12, [rcx+38h]
0x18000fa45  mov     rcx, r12; lpCriticalSection
0x18000fa48  call    cs:__imp_EnterCriticalSection
0x18000fa4e  cmp     [rsi], r15b
0x18000fa51  jz      short loc_18000FA99
0x18000fa53  mov     rcx, r12; lpCriticalSection
0x18000fa56  call    cs:__imp_LeaveCriticalSection
0x18000fa5c  mov     edi, 1
0x18000fa61  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000fa68  jz      short loc_18000FA81
0x18000fa6a  lea     r8, aEnable464xlatR; "Enable464xlat: RPC is blocked"
0x18000fa71  mov     [rsp+0D8h+var_B8], r14
0x18000fa76  mov     r9d, 6BAh
0x18000fa7c  call    McTemplateU0sqx_EventWriteTransfer
0x18000fa81  mov     eax, 6BAh
0x18000fa86  add     rsp, 0A0h
0x18000fa8d  pop     r15
0x18000fa8f  pop     r14
0x18000fa91  pop     r13
0x18000fa93  pop     r12
0x18000fa95  pop     rdi
0x18000fa96  pop     rsi
0x18000fa97  pop     rbx
0x18000fa98  retn
0x18000fa99  mov     byte ptr [rsp+0D8h+var_84], r15b
0x18000fa9e  xor     eax, eax
0x18000faa0  mov     word ptr [rsp+0D8h+var_84+1], ax
0x18000faa5  mov     byte ptr [rsp+0D8h+var_84+3], al
0x18000faa9  movzx   edi, r15b
0x18000faad  mov     [rsp+0D8h+var_88], dil
0x18000fab2  lea     r13, [rsi+80h]
0x18000fab9  mov     rdx, [r13+0]
0x18000fabd  mov     rax, [rdx+8]
0x18000fac1  xor     ecx, ecx
0x18000fac3  mov     [rsp+0D8h+var_54], ecx
0x18000faca  mov     rcx, rdx
0x18000facd  jmp     short loc_18000FAE1
0x18000facf  cmp     [rax+20h], r14
0x18000fad3  jnb     short loc_18000FADB
0x18000fad5  mov     rax, [rax+10h]
0x18000fad9  jmp     short loc_18000FAE1
0x18000fadb  mov     rcx, rax
0x18000fade  mov     rax, [rax]
0x18000fae1  cmp     [rax+19h], r15b
0x18000fae5  jz      short loc_18000FACF
0x18000fae7  cmp     [rcx+19h], r15b
0x18000faeb  jnz     short loc_18000FB30
0x18000faed  cmp     r14, [rcx+20h]
0x18000faf1  jb      short loc_18000FB30
0x18000faf3  cmp     rdx, rcx
0x18000faf6  jz      short loc_18000FB30
0x18000faf8  mov     rcx, r12; lpCriticalSection
0x18000fafb  call    cs:__imp_LeaveCriticalSection
0x18000fb01  mov     edi, 1
0x18000fb06  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000fb0d  jz      short loc_18000FB26
0x18000fb0f  mov     [rsp+0D8h+var_B8], r14
0x18000fb14  mov     r9d, 0B7h
0x18000fb1a  lea     r8, aEnable464xlat4; "Enable464xlat: 464xlat is already enabl"...
0x18000fb21  call    McTemplateU0sqx_EventWriteTransfer
0x18000fb26  mov     eax, 0B7h
0x18000fb2b  jmp     loc_18000FA86
0x18000fb30  mov     rax, [rsi+68h]
0x18000fb34  cmp     rax, [rsi+70h]
0x18000fb38  jz      loc_18000FDAD
0x18000fb3e  cmp     [rax+4], r15b
0x18000fb42  jnz     short loc_18000FB4A
0x18000fb44  add     rax, 8
0x18000fb48  jmp     short loc_18000FB34
0x18000fb4a  mov     ebx, [rax]
0x18000fb4c  mov     [rsp+0D8h+var_84], ebx
0x18000fb50  mov     [rax+4], r15b
0x18000fb54  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetImpl(void)'::`2'::impl
0x18000fb5b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::__private_IsEnabled(void)
0x18000fb60  mov     ecx, edi
0x18000fb62  mov     edi, 1
0x18000fb67  test    al, al
0x18000fb69  cmovnz  ecx, edi
0x18000fb6c  mov     [rsp+0D8h+var_88], cl
0x18000fb70  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x18000fb77  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)
0x18000fb7c  test    al, al
0x18000fb7e  jz      loc_18000FC0F
0x18000fb84  mov     r15d, 0E8h
0x18000fb8a  mov     ecx, r15d; Size
0x18000fb8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb92  mov     [rsp+0D8h+var_80], rax
0x18000fb97  mov     ecx, [rsp+0D8h+arg_28]
0x18000fb9e  mov     [rsp+0D8h+var_98], ecx
0x18000fba2  mov     rcx, [rsp+0D8h+arg_20]
0x18000fbaa  mov     [rsp+0D8h+var_A0], rcx
0x18000fbaf  mov     rcx, [rsp+0D8h+arg_18]
0x18000fbb7  mov     [rsp+0D8h+var_A8], rcx
0x18000fbbc  mov     cl, [rsi+64h]
0x18000fbbf  mov     [rsp+0D8h+var_B0], cl
0x18000fbc3  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000fbc7  mov     r9d, [rsi+60h]
0x18000fbcb  mov     r8d, [rsp+0D8h+arg_10]
0x18000fbd3  mov     rdx, r14
0x18000fbd6  mov     rcx, rax
0x18000fbd9  call    ??0IPxlatInterface@@QEAA@_KKUin_addr@@1EPEAU_IPV6_PREFIX@@2W4_IPXLAT_TRIGGER_SOURCE@@@Z; IPxlatInterface::IPxlatInterface(unsigned __int64,ulong,in_addr,in_addr,uchar,_IPV6_PREFIX *,_IPV6_PREFIX *,_IPXLAT_TRIGGER_SOURCE)
0x18000fbde  nop
0x18000fbdf  mov     [rsp+0D8h+var_78], r14
0x18000fbe4  mov     [rsp+0D8h+var_80], 0
0x18000fbed  mov     [rsp+0D8h+var_70], rax
0x18000fbf2  lea     r8, [rsp+0D8h+var_78]
0x18000fbf7  lea     rdx, [rsp+0D8h+var_60]
0x18000fbfc  mov     rcx, r13
0x18000fbff  call    ??$insert@U?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@$0A@@?$map@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@1@@Z; std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>> &&)
0x18000fc04  nop
0x18000fc05  mov     rbx, [rsp+0D8h+var_70]
0x18000fc0a  jmp     loc_18000FD70
0x18000fc0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl(void)'::`2'::impl
0x18000fc16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(void)
0x18000fc1b  mov     r15d, 0E8h
0x18000fc21  mov     ecx, r15d; Size
0x18000fc24  test    al, al
0x18000fc26  jz      loc_18000FCEE
0x18000fc2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fc31  mov     r13, rax
0x18000fc34  mov     [rsp+0D8h+var_78], rax
0x18000fc39  mov     eax, [rsi+9Ch]
0x18000fc3f  mov     dword ptr [rsp+0D8h+var_80], eax
0x18000fc43  mov     eax, [rsi+98h]
0x18000fc49  mov     [rsp+0D8h+var_64], eax
0x18000fc4d  mov     eax, [rsi+94h]
0x18000fc53  mov     [rsp+0D8h+var_68], eax
0x18000fc57  mov     ecx, [rsp+0D8h+arg_28]
0x18000fc5e  mov     [rsp+0D8h+var_98], ecx
0x18000fc62  mov     rcx, [rsp+0D8h+arg_20]
0x18000fc6a  mov     [rsp+0D8h+var_A0], rcx
0x18000fc6f  mov     rcx, [rsp+0D8h+arg_18]
0x18000fc77  mov     [rsp+0D8h+var_A8], rcx
0x18000fc7c  mov     al, [rsi+64h]
0x18000fc7f  mov     [rsp+0D8h+var_B0], al
0x18000fc83  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000fc87  mov     r9d, [rsi+60h]
0x18000fc8b  mov     r8d, [rsp+0D8h+arg_10]
0x18000fc93  mov     rdx, r14
0x18000fc96  mov     rcx, r13
0x18000fc99  call    ??0IPxlatInterface@@QEAA@_KKUin_addr@@1EPEAU_IPV6_PREFIX@@2W4_IPXLAT_TRIGGER_SOURCE@@@Z; IPxlatInterface::IPxlatInterface(unsigned __int64,ulong,in_addr,in_addr,uchar,_IPV6_PREFIX *,_IPV6_PREFIX *,_IPXLAT_TRIGGER_SOURCE)
0x18000fc9e  mov     eax, [rsp+0D8h+var_68]
0x18000fca2  mov     [r13+0C0h], eax
0x18000fca9  mov     eax, [rsp+0D8h+var_64]
0x18000fcad  mov     [r13+0C4h], eax
0x18000fcb4  mov     eax, dword ptr [rsp+0D8h+var_80]
0x18000fcb8  mov     [r13+0C8h], eax
0x18000fcbf  mov     [rsp+0D8h+var_78], r14
0x18000fcc4  mov     [rsp+0D8h+var_80], 0
0x18000fccd  mov     [rsp+0D8h+var_70], r13
0x18000fcd2  lea     r8, [rsp+0D8h+var_78]
0x18000fcd7  lea     rdx, [rsp+0D8h+var_60]
0x18000fcdc  lea     rcx, [rsi+80h]
0x18000fce3  call    ??$insert@U?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@$0A@@?$map@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@1@@Z; std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>> &&)
0x18000fce8  nop
0x18000fce9  jmp     loc_18000FC05
0x18000fcee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fcf3  mov     [rsp+0D8h+var_78], rax
0x18000fcf8  mov     ecx, [rsp+0D8h+arg_28]
0x18000fcff  mov     [rsp+0D8h+var_98], ecx
0x18000fd03  mov     rcx, [rsp+0D8h+arg_20]
0x18000fd0b  mov     [rsp+0D8h+var_A0], rcx
0x18000fd10  mov     rcx, [rsp+0D8h+arg_18]
0x18000fd18  mov     [rsp+0D8h+var_A8], rcx
0x18000fd1d  mov     cl, [rsi+64h]
0x18000fd20  mov     [rsp+0D8h+var_B0], cl
0x18000fd24  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000fd28  mov     r9d, [rsi+60h]
0x18000fd2c  mov     r8d, [rsp+0D8h+arg_10]
0x18000fd34  mov     rdx, r14
0x18000fd37  mov     rcx, rax
0x18000fd3a  call    ??0IPxlatInterface@@QEAA@_KKUin_addr@@1EPEAU_IPV6_PREFIX@@2W4_IPXLAT_TRIGGER_SOURCE@@@Z; IPxlatInterface::IPxlatInterface(unsigned __int64,ulong,in_addr,in_addr,uchar,_IPV6_PREFIX *,_IPV6_PREFIX *,_IPXLAT_TRIGGER_SOURCE)
0x18000fd3f  nop
0x18000fd40  mov     [rsp+0D8h+var_78], r14
0x18000fd45  mov     [rsp+0D8h+var_80], 0
0x18000fd4e  mov     [rsp+0D8h+var_70], rax
0x18000fd53  lea     r8, [rsp+0D8h+var_78]
0x18000fd58  lea     rdx, [rsp+0D8h+var_60]
0x18000fd5d  mov     rcx, r13
0x18000fd60  call    ??$insert@U?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@$0A@@?$map@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@1@@Z; std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>> &&)
0x18000fd65  nop
0x18000fd66  mov     rbx, [rsp+0D8h+var_70]
0x18000fd6b  test    rbx, rbx
0x18000fd6e  jz      short loc_18000FD89
0x18000fd70  test    rbx, rbx
0x18000fd73  jz      short loc_18000FD89
0x18000fd75  mov     rcx, rbx; this
0x18000fd78  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000fd7d  mov     rdx, r15; unsigned __int64
0x18000fd80  mov     rcx, rbx; void *
0x18000fd83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fd88  nop
0x18000fd89  cmp     [rsi+88h], rdi
0x18000fd90  jnz     short loc_18000FD9D
0x18000fd92  mov     rcx, [rsi+30h]; hTimer
0x18000fd96  call    cs:__imp_CancelWaitableTimer
0x18000fd9c  nop
0x18000fd9d  mov     rcx, r12; lpCriticalSection
0x18000fda0  call    cs:__imp_LeaveCriticalSection
0x18000fda6  xor     eax, eax
0x18000fda8  jmp     loc_18000FA86
0x18000fdad  mov     rcx, r12; lpCriticalSection
0x18000fdb0  call    cs:__imp_LeaveCriticalSection
0x18000fdb6  mov     edi, 1
0x18000fdbb  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18000fdc2  jz      short loc_18000FDDB
0x18000fdc4  mov     [rsp+0D8h+var_B8], r14
0x18000fdc9  mov     r9d, 103h
0x18000fdcf  lea     r8, aEnable464xlatN; "Enable464xlat: No more IPv4 addresses a"...
0x18000fdd6  call    McTemplateU0sqx_EventWriteTransfer
0x18000fddb  mov     eax, 103h
0x18000fde0  jmp     loc_18000FA86
```
