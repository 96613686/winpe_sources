# CRdpIdAdapter::ProcessSetMonitorConfiguration(_RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION * const,_RDPIDD_OUT_SET_MONITOR_CONFIGURATION * const)

- ea: `0x18001a860`
- end: `0x18001ade5`
- name: `?ProcessSetMonitorConfiguration@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION@@QEAU_RDPIDD_OUT_SET_MONITOR_CONFIGURATION@@@Z`
- size: `1413`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION *const, struct _RDPIDD_OUT_SET_MONITOR_CONFIGURATION *const)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800185bc`

## callees

- `0x180006f84`
- `0x18000875c`
- `0x1800089f0`
- `0x18001072c`
- `0x180011584`
- `0x180012cd8`
- `0x180012de4`
- `0x180013bb0`
- `0x18001556c`
- `0x180015850`
- `0x180015a88`
- `0x18001a860`
- `0x18001d3fc`
- `0x18001dd70`
- `0x18001ddbc`
- `0x18001de94`
- `0x18001fd78`
- `0x180021058`
- `0x180021264`
- `0x180021f78`

## string_xrefs

- `0x18001ad0c`: `Unable to cast to RDP_MONITOR_CONFIGURATION because buffer is too small`
- `0x18001ace4`: `RDP_MONITOR_CONFIGURATION structure has invalid size %d`
- `0x18001aa97`: `Monitor cannot be added because another monitor with same ID already exists`
- `0x18001aa27`: `Monitor configuration cannot be updated because it does not exist`
- `0x18001ad9f`: `RDP_MONITORCONFIG_ACTION_TYPE_UPDATE is available only for incremental updates`
- `0x18001a9a1`: `Monitor cannot be deleted because it does not exist`
- `0x18001ad41`: `RDP_MONITORCONFIG_ACTION_TYPE_DELETE is available only for incremental updates`
- `0x18001ad70`: `Invalid Action specified in RDP_MONITOR_CONFIGURATION structure`
- `0x18001adc1`: `Unable to move to next RDP_MONITOR_CONFIGURATION because buffer is too small`
- `0x18001acbb`: `Invalid Type specified in RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION structure`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CRdpIdAdapter::ProcessSetMonitorConfiguration(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION *const a2,
        struct _RDPIDD_OUT_SET_MONITOR_CONFIGURATION *const a3)
{
  unsigned int v5; // r13d
  unsigned int *v6; // r14
  unsigned int v7; // eax
  _DWORD *v8; // r12
  _DWORD *v9; // rsi
  _QWORD *v10; // rax
  char v11; // bl
  __int64 v12; // rdx
  __int128 *v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _OWORD *v16; // rax
  __int64 v17; // r10
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  char *v22; // [rsp+28h] [rbp-61h]
  __int128 v23; // [rsp+30h] [rbp-59h] BYREF
  __int64 v24; // [rsp+40h] [rbp-49h]
  _QWORD v25[2]; // [rsp+48h] [rbp-41h] BYREF
  __int128 v26; // [rsp+58h] [rbp-31h] BYREF
  __int64 v27; // [rsp+68h] [rbp-21h]
  __int128 v28; // [rsp+70h] [rbp-19h] BYREF
  __int64 v29; // [rsp+80h] [rbp-9h]
  _BYTE v30[8]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v31[80]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  char v33; // [rsp+F0h] [rbp+67h]
  char v35; // [rsp+108h] [rbp+7Fh] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xE86,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 70) == 0,
    (bool)"Encoding processor has not been started",
    (const char *)v23);
  v28 = 0;
  v29 = 0;
  v26 = 0;
  v27 = 0;
  v23 = 0;
  v24 = 0;
  if ( *(_DWORD *)a2 < 0x30u )
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0xE97,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0xC0000023LL,
      (int)"Unable to cast to RDP_MONITOR_CONFIGURATION because buffer is too small",
      v22);
  v33 = 0;
  v5 = *(_DWORD *)a2 - 24;
  v6 = (unsigned int *)((char *)a2 + 24);
  while ( 1 )
  {
    v7 = *v6;
    if ( v5 < *v6 )
      goto LABEL_53;
    if ( v7 < 0x18 )
    {
      v7 = *v6;
LABEL_53:
      LODWORD(v22) = v7;
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0xEAA,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"RDP_MONITOR_CONFIGURATION structure has invalid size %d",
        v22);
    }
    v8 = operator new(0x148u);
    *(_OWORD *)v8 = 0;
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<CMonitorConfig>::`vftable';
    CMonitorConfig::CMonitorConfig(
      (CMonitorConfig *)(v8 + 4),
      (struct _RDP_MONITOR_CONFIGURATION *const)v6,
      *((_DWORD *)this + 108));
    v25[0] = v8 + 4;
    v25[1] = v8;
    switch ( v6[1] )
    {
      case 1u:
        v9 = (_DWORD *)((char *)a2 + 12);
        if ( *((_DWORD *)a2 + 3) == 1 )
        {
          v15 = (_QWORD *)std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
                            (char *)this + 160,
                            v31,
                            v6 + 2);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xEBB,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)0x8000FFFFLL,
            *v15 != *((_QWORD *)this + 20),
            (bool)"Monitor cannot be added because another monitor with same ID already exists",
            (const char *)v23);
        }
        v11 = 1;
        v33 = 1;
        if ( *((_QWORD *)&v28 + 1) == v29 )
        {
          std::vector<std::shared_ptr<CMonitorConfig>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(
            &v28,
            *((_QWORD *)&v28 + 1),
            v25);
        }
        else
        {
          std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(*((_QWORD *)&v28 + 1), v25);
          *((_QWORD *)&v28 + 1) += 16LL;
        }
        break;
      case 2u:
        v9 = (_DWORD *)((char *)a2 + 12);
        if ( *((_DWORD *)a2 + 3) != 1 )
        {
          v21 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xED0,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)v21,
            (int)"RDP_MONITORCONFIG_ACTION_TYPE_UPDATE is available only for incremental updates",
            v22);
        }
        v14 = (_QWORD *)std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
                          (char *)this + 160,
                          v30,
                          v6 + 2);
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0xEC9,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0x80070490LL,
          *v14 == *((_QWORD *)this + 20),
          (bool)"Monitor configuration cannot be updated because it does not exist",
          (const char *)v23);
        v11 = v33;
        if ( (v8[11] & 2) != 0 )
          v11 = 1;
        v33 = v11;
        break;
      case 3u:
        v9 = (_DWORD *)((char *)a2 + 12);
        if ( *((_DWORD *)a2 + 3) != 1 )
        {
          v19 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xEEB,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)v19,
            (int)"RDP_MONITORCONFIG_ACTION_TYPE_DELETE is available only for incremental updates",
            v22);
        }
        v10 = (_QWORD *)std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
                          (char *)this + 160,
                          &v35,
                          v6 + 2);
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0xEE4,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0x80070490LL,
          *v10 == *((_QWORD *)this + 20),
          (bool)"Monitor cannot be deleted because it does not exist",
          (const char *)v23);
        v11 = 1;
        v33 = 1;
        if ( *((_QWORD *)&v26 + 1) != v27 )
        {
          std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(*((_QWORD *)&v26 + 1), v25);
          *((_QWORD *)&v26 + 1) += 16LL;
          goto LABEL_25;
        }
        v12 = *((_QWORD *)&v26 + 1);
        v13 = &v26;
        goto LABEL_24;
      default:
        v20 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xEF4,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)v20,
          (int)"Invalid Action specified in RDP_MONITOR_CONFIGURATION structure",
          v22);
    }
    if ( *((_QWORD *)&v23 + 1) != v24 )
    {
      std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(*((_QWORD *)&v23 + 1), v25);
      *((_QWORD *)&v23 + 1) += 16LL;
      goto LABEL_25;
    }
    v12 = *((_QWORD *)&v23 + 1);
    v13 = &v23;
LABEL_24:
    std::vector<std::shared_ptr<CMonitorConfig>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(
      v13,
      v12,
      v25);
LABEL_25:
    v5 -= *v6;
    if ( !v5 )
      break;
    if ( v5 < 0x18 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0xF0A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Unable to move to next RDP_MONITOR_CONFIGURATION because buffer is too small",
        v22);
    v6 = (unsigned int *)((char *)v6 + *v6);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
  }
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
  if ( *v9 )
  {
    if ( *v9 != 1 )
    {
      v18 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xF33,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)v18,
        (int)"Invalid Type specified in RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION structure",
        v22);
    }
    if ( (__int64)(*((_QWORD *)&v26 + 1) - v26) >> 4 )
      CRdpIdAdapter::DeleteMonitors(this, &v26);
  }
  else
  {
    if ( *((_QWORD *)this + 21) )
      CRdpIdAdapter::DeleteAllMonitors(this);
    if ( *((_DWORD *)a2 + 4) || *((_DWORD *)a2 + 5) )
    {
      *((_QWORD *)this + 66) = *((_QWORD *)a2 + 2);
      CRdpIdAdapter::SetPreferredRenderAdapter(this);
    }
  }
  if ( (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 4 )
    CRdpIdAdapter::AddMonitors(this, &v28);
  if ( v11 )
    CRdpIdAdapter::UpdateAllMonitors(this);
  else
    CRdpIdAdapter::UpdateMonitors(this, &v23);
  if ( a3 )
  {
    *(_DWORD *)a3 = 20;
    v16 = (_OWORD *)std::_Atomic_storage<RDP_MONITORCONFIG_2DRECTANGLE,16>::load((char *)this + 568, v25);
    *(_OWORD *)(v17 + 4) = *v16;
  }
  if ( (_QWORD)v23 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(v23, *((_QWORD *)&v23 + 1));
    std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
    v23 = 0;
    v24 = 0;
  }
  if ( (_QWORD)v26 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(v26, *((_QWORD *)&v26 + 1));
    std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF0uLL);
    v26 = 0;
    v27 = 0;
  }
  if ( (_QWORD)v28 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(v28, *((_QWORD *)&v28 + 1));
    std::_Deallocate<16>(v28, (v29 - v28) & 0xFFFFFFFFFFFFFFF0uLL);
  }
}

```

## disassembly

```asm
0x18001a860  mov     [rsp-8+arg_10], r8
0x18001a865  push    rbp
0x18001a866  push    rbx
0x18001a867  push    rsi
0x18001a868  push    rdi
0x18001a869  push    r12
0x18001a86b  push    r13
0x18001a86d  push    r14
0x18001a86f  push    r15
0x18001a871  lea     rbp, [rsp-1Fh]
0x18001a876  sub     rsp, 0A8h
0x18001a87d  mov     r15, rdx
0x18001a880  mov     rdi, rcx
0x18001a883  xor     ebx, ebx
0x18001a885  cmp     [rcx+230h], rbx
0x18001a88c  setz    al
0x18001a88f  mov     rcx, [rbp+5Fh]; this
0x18001a893  lea     rdx, aEncodingProces; "Encoding processor has not been started"
0x18001a89a  mov     [rsp+0E0h+var_B8], rdx; char *
0x18001a89f  mov     [rsp+0E0h+var_C0], al; char
0x18001a8a3  mov     r9d, 80070057h; char *
0x18001a8a9  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a8b0  mov     edx, 0E86h; void *
0x18001a8b5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001a8ba  xorps   xmm0, xmm0
0x18001a8bd  movdqu  [rbp+57h+var_70], xmm0
0x18001a8c2  mov     [rbp+57h+var_60], rbx
0x18001a8c6  movdqu  [rbp+57h+var_88], xmm0
0x18001a8cb  mov     [rbp+57h+var_78], rbx
0x18001a8cf  movdqu  [rbp+57h+var_B0], xmm0
0x18001a8d4  mov     [rbp+57h+var_A0], rbx
0x18001a8d8  mov     r13d, [r15]
0x18001a8db  cmp     r13d, 30h ; '0'
0x18001a8df  jb      loc_18001AD08
0x18001a8e5  mov     byte ptr [rbp+57h+arg_0], bl
0x18001a8e8  add     r13d, 0FFFFFFE8h
0x18001a8ec  lea     r14, [r15+18h]
0x18001a8f0  mov     eax, [r14]
0x18001a8f3  cmp     r13d, eax
0x18001a8f6  jb      loc_18001ACDC
0x18001a8fc  mov     ebx, 1
0x18001a901  cmp     eax, 18h
0x18001a904  jb      loc_18001ACD9
0x18001a90a  mov     ecx, 148h; Size
0x18001a90f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a914  mov     r12, rax
0x18001a917  mov     [rbp+57h+arg_8], rax
0x18001a91b  xorps   xmm0, xmm0
0x18001a91e  movups  xmmword ptr [rax], xmm0
0x18001a921  mov     [rax+8], ebx
0x18001a924  mov     [rax+0Ch], ebx
0x18001a927  lea     rax, ??_7?$_Ref_count_obj2@VCMonitorConfig@@@std@@6B@; const std::_Ref_count_obj2<CMonitorConfig>::`vftable'
0x18001a92e  mov     [r12], rax
0x18001a932  lea     rbx, [r12+10h]
0x18001a937  mov     r8d, [rdi+1B0h]; unsigned int
0x18001a93e  mov     rdx, r14; struct _RDP_MONITOR_CONFIGURATION *
0x18001a941  mov     rcx, rbx; this
0x18001a944  call    ??0CMonitorConfig@@QEAA@QEAU_RDP_MONITOR_CONFIGURATION@@I@Z; CMonitorConfig::CMonitorConfig(_RDP_MONITOR_CONFIGURATION * const,uint)
0x18001a949  nop
0x18001a94a  mov     [rbp+57h+var_98], rbx
0x18001a94e  mov     [rbp+57h+var_90], r12
0x18001a952  mov     ecx, [r14+4]
0x18001a956  sub     ecx, 1
0x18001a959  jz      loc_18001AA6A
0x18001a95f  sub     ecx, 1
0x18001a962  jz      loc_18001A9F6
0x18001a968  cmp     ecx, 1
0x18001a96b  jnz     loc_18001AD5F
0x18001a971  lea     rsi, [r15+0Ch]
0x18001a975  cmp     [rsi], ecx
0x18001a977  jnz     loc_18001AD30
0x18001a97d  lea     rbx, [rdi+0A0h]
0x18001a984  lea     r8, [r14+8]
0x18001a988  lea     rdx, [rbp+57h+arg_18]
0x18001a98c  mov     rcx, rbx
0x18001a98f  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x18001a994  mov     rcx, [rbx]
0x18001a997  cmp     [rax], rcx
0x18001a99a  setz    al
0x18001a99d  mov     rcx, [rbp+5Fh]; this
0x18001a9a1  lea     rdx, aMonitorCannotB_0; "Monitor cannot be deleted because it do"...
0x18001a9a8  mov     [rsp+0E0h+var_B8], rdx; bool
0x18001a9ad  mov     [rsp+0E0h+var_C0], al; char
0x18001a9b1  mov     r9d, 80070490h; char *
0x18001a9b7  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a9be  mov     edx, 0EE4h; void *
0x18001a9c3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001a9c8  mov     bl, 1
0x18001a9ca  mov     [rbp+57h+arg_0], ebx
0x18001a9cd  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x18001a9d1  cmp     rcx, [rbp+57h+var_78]
0x18001a9d5  jz      short loc_18001A9EA
0x18001a9d7  lea     rdx, [rbp+57h+var_98]
0x18001a9db  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001a9e0  add     qword ptr [rbp+57h+var_88+8], 10h
0x18001a9e5  jmp     loc_18001AB17
0x18001a9ea  mov     rdx, rcx
0x18001a9ed  lea     rcx, [rbp+57h+var_88]
0x18001a9f1  jmp     loc_18001AB0E
0x18001a9f6  lea     rsi, [r15+0Ch]
0x18001a9fa  cmp     dword ptr [rsi], 1
0x18001a9fd  jnz     loc_18001AD8E
0x18001aa03  lea     rbx, [rdi+0A0h]
0x18001aa0a  lea     r8, [r14+8]
0x18001aa0e  lea     rdx, [rbp+57h+var_58]
0x18001aa12  mov     rcx, rbx
0x18001aa15  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x18001aa1a  mov     rcx, [rbx]
0x18001aa1d  cmp     [rax], rcx
0x18001aa20  setz    al
0x18001aa23  mov     rcx, [rbp+5Fh]; this
0x18001aa27  lea     rdx, aMonitorConfigu; "Monitor configuration cannot be updated"...
0x18001aa2e  mov     [rsp+0E0h+var_B8], rdx; bool
0x18001aa33  mov     [rsp+0E0h+var_C0], al; char
0x18001aa37  mov     r9d, 80070490h; char *
0x18001aa3d  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001aa44  mov     edx, 0EC9h; void *
0x18001aa49  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001aa4e  test    byte ptr [r12+2Ch], 2
0x18001aa54  mov     ebx, [rbp+57h+arg_0]
0x18001aa57  movzx   ebx, bl
0x18001aa5a  mov     eax, 1
0x18001aa5f  cmovnz  ebx, eax
0x18001aa62  mov     [rbp+57h+arg_0], ebx
0x18001aa65  jmp     loc_18001AAED
0x18001aa6a  lea     rsi, [r15+0Ch]
0x18001aa6e  cmp     dword ptr [rsi], 1
0x18001aa71  jnz     short loc_18001AABE
0x18001aa73  lea     rbx, [rdi+0A0h]
0x18001aa7a  lea     r8, [r14+8]
0x18001aa7e  lea     rdx, [rbp+57h+var_50]
0x18001aa82  mov     rcx, rbx
0x18001aa85  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x18001aa8a  mov     rcx, [rbx]
0x18001aa8d  cmp     [rax], rcx
0x18001aa90  setnz   al
0x18001aa93  mov     rcx, [rbp+5Fh]; this
0x18001aa97  lea     rdx, aMonitorCannotB; "Monitor cannot be added because another"...
0x18001aa9e  mov     [rsp+0E0h+var_B8], rdx; char *
0x18001aaa3  mov     [rsp+0E0h+var_C0], al; char
0x18001aaa7  mov     r9d, 8000FFFFh; char *
0x18001aaad  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001aab4  mov     edx, 0EBBh; void *
0x18001aab9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001aabe  mov     bl, 1
0x18001aac0  mov     [rbp+57h+arg_0], ebx
0x18001aac3  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x18001aac7  cmp     rcx, [rbp+57h+var_60]
0x18001aacb  jz      short loc_18001AADD
0x18001aacd  lea     rdx, [rbp+57h+var_98]
0x18001aad1  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001aad6  add     qword ptr [rbp+57h+var_70+8], 10h
0x18001aadb  jmp     short loc_18001AAED
0x18001aadd  lea     r8, [rbp+57h+var_98]
0x18001aae1  mov     rdx, rcx
0x18001aae4  lea     rcx, [rbp+57h+var_70]
0x18001aae8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VCMonitorConfig@@@std@@@?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCMonitorConfig@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<CMonitorConfig>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> const &)
0x18001aaed  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x18001aaf1  cmp     rcx, [rbp+57h+var_A0]
0x18001aaf5  jz      short loc_18001AB07
0x18001aaf7  lea     rdx, [rbp+57h+var_98]
0x18001aafb  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001ab00  add     qword ptr [rbp+57h+var_B0+8], 10h
0x18001ab05  jmp     short loc_18001AB17
0x18001ab07  mov     rdx, rcx
0x18001ab0a  lea     rcx, [rbp+57h+var_B0]
0x18001ab0e  lea     r8, [rbp+57h+var_98]
0x18001ab12  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VCMonitorConfig@@@std@@@?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCMonitorConfig@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<CMonitorConfig>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> const &)
0x18001ab17  sub     r13d, [r14]
0x18001ab1a  jz      short loc_18001AB39
0x18001ab1c  cmp     r13d, 18h
0x18001ab20  jb      loc_18001ADBD
0x18001ab26  mov     eax, [r14]
0x18001ab29  add     r14, rax
0x18001ab2c  mov     rcx, r12; this
0x18001ab2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ab34  jmp     loc_18001A8F0
0x18001ab39  mov     rcx, r12; this
0x18001ab3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ab41  mov     ecx, [rsi]
0x18001ab43  xor     esi, esi
0x18001ab45  test    ecx, ecx
0x18001ab47  jz      short loc_18001AB71
0x18001ab49  cmp     ecx, 1
0x18001ab4c  jnz     loc_18001ACAA
0x18001ab52  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18001ab56  sub     rax, qword ptr [rbp+57h+var_88]
0x18001ab5a  sar     rax, 4
0x18001ab5e  test    rax, rax
0x18001ab61  jz      short loc_18001ABAE
0x18001ab63  lea     rdx, [rbp+57h+var_88]
0x18001ab67  mov     rcx, rdi
0x18001ab6a  call    ?DeleteMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z; CRdpIdAdapter::DeleteMonitors(std::vector<std::shared_ptr<CMonitorConfig>> const &)
0x18001ab6f  jmp     short loc_18001ABAE
0x18001ab71  cmp     [rdi+0A8h], rsi
0x18001ab78  jbe     short loc_18001AB82
0x18001ab7a  mov     rcx, rdi; this
0x18001ab7d  call    ?DeleteAllMonitors@CRdpIdAdapter@@AEAAXXZ; CRdpIdAdapter::DeleteAllMonitors(void)
0x18001ab82  mov     rax, qword ptr cs:stru_180046EE0.LowPart
0x18001ab89  cmp     eax, [r15+10h]
0x18001ab8d  jnz     short loc_18001AB9B
0x18001ab8f  mov     eax, cs:stru_180046EE0.HighPart
0x18001ab95  cmp     eax, [r15+14h]
0x18001ab99  jz      short loc_18001ABAE
0x18001ab9b  mov     rax, [r15+10h]
0x18001ab9f  mov     [rdi+210h], rax
0x18001aba6  mov     rcx, rdi; this
0x18001aba9  call    ?SetPreferredRenderAdapter@CRdpIdAdapter@@QEAAXXZ; CRdpIdAdapter::SetPreferredRenderAdapter(void)
0x18001abae  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18001abb2  sub     rax, qword ptr [rbp+57h+var_70]
0x18001abb6  sar     rax, 4
0x18001abba  test    rax, rax
0x18001abbd  jz      short loc_18001ABCB
0x18001abbf  lea     rdx, [rbp+57h+var_70]
0x18001abc3  mov     rcx, rdi
0x18001abc6  call    ?AddMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z; CRdpIdAdapter::AddMonitors(std::vector<std::shared_ptr<CMonitorConfig>> const &)
0x18001abcb  lea     rdx, [rbp+57h+var_B0]
0x18001abcf  mov     rcx, rdi; this
0x18001abd2  test    bl, bl
0x18001abd4  jz      short loc_18001ABDD
0x18001abd6  call    ?UpdateAllMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z; CRdpIdAdapter::UpdateAllMonitors(std::vector<std::shared_ptr<CMonitorConfig>> const &)
0x18001abdb  jmp     short loc_18001ABE2
0x18001abdd  call    ?UpdateMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z; CRdpIdAdapter::UpdateMonitors(std::vector<std::shared_ptr<CMonitorConfig>> const &)
0x18001abe2  mov     r10, [rbp+57h+arg_10]
0x18001abe6  test    r10, r10
0x18001abe9  jz      short loc_18001AC0B
0x18001abeb  mov     dword ptr [r10], 14h
0x18001abf2  lea     rcx, [rdi+238h]
0x18001abf9  lea     rdx, [rbp+57h+var_98]
0x18001abfd  call    ?load@?$_Atomic_storage@URDP_MONITORCONFIG_2DRECTANGLE@@$0BA@@std@@QEBA?AURDP_MONITORCONFIG_2DRECTANGLE@@W4memory_order@2@@Z; std::_Atomic_storage<RDP_MONITORCONFIG_2DRECTANGLE,16>::load(std::memory_order)
0x18001ac02  movups  xmm1, xmmword ptr [rax]
0x18001ac05  movdqu  xmmword ptr [r10+4], xmm1
0x18001ac0b  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18001ac0f  test    rcx, rcx
0x18001ac12  jz      short loc_18001AC3D
0x18001ac14  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x18001ac18  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> *,std::shared_ptr<CMonitorConfig> * const,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x18001ac1d  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18001ac21  mov     rdx, [rbp+57h+var_A0]
0x18001ac25  sub     rdx, rcx
0x18001ac28  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001ac2c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ac31  xorps   xmm0, xmm0
0x18001ac34  movdqu  [rbp+57h+var_B0], xmm0
0x18001ac39  mov     [rbp+57h+var_A0], rsi
0x18001ac3d  mov     rcx, qword ptr [rbp+57h+var_88]
0x18001ac41  test    rcx, rcx
0x18001ac44  jz      short loc_18001AC6F
0x18001ac46  mov     rdx, qword ptr [rbp+57h+var_88+8]
0x18001ac4a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> *,std::shared_ptr<CMonitorConfig> * const,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x18001ac4f  mov     rcx, qword ptr [rbp+57h+var_88]
0x18001ac53  mov     rdx, [rbp+57h+var_78]
0x18001ac57  sub     rdx, rcx
0x18001ac5a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001ac5e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ac63  xorps   xmm0, xmm0
0x18001ac66  movdqu  [rbp+57h+var_88], xmm0
0x18001ac6b  mov     [rbp+57h+var_78], rsi
0x18001ac6f  mov     rcx, qword ptr [rbp+57h+var_70]
0x18001ac73  test    rcx, rcx
0x18001ac76  jz      short loc_18001AC95
0x18001ac78  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x18001ac7c  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> *,std::shared_ptr<CMonitorConfig> * const,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x18001ac81  mov     rdx, [rbp+57h+var_60]
0x18001ac85  mov     rcx, qword ptr [rbp+57h+var_70]
0x18001ac89  sub     rdx, rcx
0x18001ac8c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001ac90  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ac95  add     rsp, 0A8h
0x18001ac9c  pop     r15
0x18001ac9e  pop     r14
0x18001aca0  pop     r13
0x18001aca2  pop     r12
0x18001aca4  pop     rdi
0x18001aca5  pop     rsi
0x18001aca6  pop     rbx
0x18001aca7  pop     rbp
0x18001aca8  retn
0x18001acaa  mov     ecx, 80070057h
0x18001acaf  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001acb4  mov     r9d, eax; char *
0x18001acb7  mov     rcx, [rbp+5Fh]; this
0x18001acbb  lea     rax, aInvalidTypeSpe; "Invalid Type specified in RDPIDD_OPCODE"...
0x18001acc2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001acc7  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001acce  mov     edx, 0F33h; void *
0x18001acd3  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001acd9  mov     eax, [r14]
0x18001acdc  mov     rcx, [rbp+5Fh]; this
0x18001ace0  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18001ace4  lea     rax, aRdpMonitorConf; "RDP_MONITOR_CONFIGURATION structure has"...
0x18001aceb  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001acf0  mov     r9d, 0C0000023h; char *
0x18001acf6  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001acfd  mov     edx, 0EAAh; void *
0x18001ad02  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001ad08  mov     rcx, [rbp+5Fh]; this
0x18001ad0c  lea     rax, aUnableToCastTo_11; "Unable to cast to RDP_MONITOR_CONFIGURA"...
0x18001ad13  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001ad18  mov     r9d, 0C0000023h; char *
  ... truncated ...
```
