# CRDPCoreConnection::InitializeInstance(IRDPENCNetStream *,IRDPCoreConnectionChannelBinder *,ulong)

- ea: `0x180063fb0`
- end: `0x18006450c`
- name: `?InitializeInstance@CRDPCoreConnection@@UEAAJPEAUIRDPENCNetStream@@PEAUIRDPCoreConnectionChannelBinder@@K@Z`
- size: `1372`
- prototype: `__int64 __fastcall(CRDPCoreConnection *__hidden this, struct IRDPENCNetStream *, struct IRDPCoreConnectionChannelBinder *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002170`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000ec70`
- `0x1800439a0`
- `0x180063fb0`
- `0x180065300`
- `0x180076090`
- `0x180079724`
- `0x180079770`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006445b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006445b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006443a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006443a`

## string_xrefs

- `0x1800643a7`: `MaxCompressionLevel`
- `0x18006416a`: `CRDPCollectionMT::CreateInstance failed`
- `0x1800643e0`: `Failed to disable compression as requested`
- `0x180064387`: `RDPWDUMX::DisableCompression`
- `0x180064488`: `Failed to create the StackCreated event.  GetLastError[0x%x]`

## pseudocode

```c
__int64 __fastcall CRDPCoreConnection::InitializeInstance(
        CRDPCoreConnection *this,
        struct IRDPENCNetStream *a2,
        struct IRDPCoreConnectionChannelBinder *a3,
        int a4)
{
  bool v4; // zf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int Instance; // ebx
  __int64 v11; // rbx
  __int64 *v12; // rbx
  const struct _GUID *v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // eax
  _QWORD *v16; // r15
  unsigned int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  char v22; // bl
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  char v28; // bl
  unsigned int v29; // eax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  signed int v35; // eax
  int v37; // [rsp+50h] [rbp-49h] BYREF
  DWORD v38; // [rsp+54h] [rbp-45h] BYREF
  int v39; // [rsp+58h] [rbp-41h] BYREF
  int v40; // [rsp+5Ch] [rbp-3Dh] BYREF
  const char *v41; // [rsp+60h] [rbp-39h] BYREF
  const char *v42; // [rsp+68h] [rbp-31h] BYREF
  const char *v43; // [rsp+70h] [rbp-29h] BYREF
  __int128 v44; // [rsp+78h] [rbp-21h] BYREF
  __int64 v45; // [rsp+88h] [rbp-11h]
  __int128 v46; // [rsp+90h] [rbp-9h] BYREF
  __int64 v47; // [rsp+A0h] [rbp+7h]
  int v48; // [rsp+100h] [rbp+67h] BYREF

  v4 = (*((_BYTE *)this + 44) & 2) == 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v44 = 0;
  v46 = 0;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    Instance = -2147418113;
    goto LABEL_64;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 144LL))(*((_QWORD *)this + 11));
  if ( v11 != *((_QWORD *)this + 18) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 144);
    *((_QWORD *)this + 18) = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  *((_DWORD *)this + 11) |= 2u;
  v12 = (__int64 *)((char *)this + 136);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 152LL))(*((_QWORD *)this + 11));
  if ( v14 != *((_QWORD *)this + 17) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 136);
    *v12 = v14;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 136);
  }
  if ( !*v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        v15,
        -2147467263);
    }
    Instance = -2147467263;
    goto LABEL_64;
  }
  v16 = (_QWORD *)((char *)this + 128);
  Instance = CRDPCollectionMT::CreateInstance(v13, (void **)this + 16);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_64;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 19;
    v19 = "CRDPCollectionMT::CreateInstance failed";
LABEL_23:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      (unsigned int)WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
      v17,
      (__int64)v19,
      Instance);
LABEL_64:
    CRDPCoreConnection::TerminateInstance(this);
    return (unsigned int)Instance;
  }
  Instance = RDPWDUMX_CreateLegacyContext();
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_64;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 20;
    v19 = "Failed to init the legacy stack context";
    goto LABEL_23;
  }
  *((_DWORD *)this + 45) = 1;
  *((_DWORD *)this + 44) = a4;
  if ( a2 != *((struct IRDPENCNetStream **)this + 15) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 120);
    *((_QWORD *)this + 15) = a2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 120);
  }
  v20 = *v16;
  DWORD2(v44) = a4;
  LOWORD(v44) = 23;
  Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v20 + 56LL))(
               v20,
               L"ConnectionID",
               &v44);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_64;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 21;
    v19 = "Failed to set the property connection ID";
    goto LABEL_23;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 11) + 32LL))(
          *((_QWORD *)this + 11),
          L"GfxPipeline::ForceLyncProfile",
          &v48);
  v22 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        v23,
        (__int64)"Failed to get GFX_PIPELINE_FORCELYNCPROFILE property",
        v22);
    }
    goto LABEL_41;
  }
  if ( !v48 )
  {
LABEL_41:
    v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 176LL))(*((_QWORD *)this + 11));
    goto LABEL_42;
  }
  v24 = -1;
LABEL_42:
  v25 = *v16;
  DWORD2(v46) = v24;
  LOWORD(v46) = 23;
  Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v25 + 56LL))(
               v25,
               L"SessionID",
               &v46);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_64;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 23;
    v19 = "Failed to set the unique session ID";
    goto LABEL_23;
  }
  v26 = *((_QWORD *)this + 11);
  v37 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v26 + 32LL))(
         v26,
         L"RDPWDUMX::DisableCompression",
         &v37) >= 0 )
  {
    if ( v37 )
    {
      v27 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(*(_QWORD *)*v16 + 72LL))(
              *v16,
              L"MaxCompressionLevel",
              0);
      v28 = v27;
      if ( v27 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
          v29,
          (__int64)"Failed to disable compression as requested",
          v28);
      }
    }
  }
  Instance = 0;
  if ( a3 != *((struct IRDPCoreConnectionChannelBinder **)this + 14) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 112);
    *((_QWORD *)this + 14) = a3;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 112);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 24) = EventW;
  if ( !EventW )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LastError = GetLastError();
      v39 = 203;
      v38 = LastError;
      v41 = "InitializeInstance";
      v42 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\coreconnection.cpp";
      v43 = "Failed to create the StackCreated event.  GetLastError[0x%x]";
      v40 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v32,
        (unsigned int)&dword_180287664,
        v33,
        v34,
        (__int64)&v43,
        (__int64)&v40,
        (__int64)&v42,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v38);
    }
    v35 = GetLastError();
    Instance = v35;
    if ( v35 > 0 )
      Instance = (unsigned __int16)v35 | 0x80070000;
    if ( Instance < 0 )
      goto LABEL_64;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180063fb0  push    rbp
0x180063fb2  push    rbx
0x180063fb3  push    rsi
0x180063fb4  push    rdi
0x180063fb5  push    r12
0x180063fb7  push    r13
0x180063fb9  push    r14
0x180063fbb  push    r15
0x180063fbd  lea     rbp, [rsp-1Fh]
0x180063fc2  sub     rsp, 0B8h
0x180063fc9  xor     eax, eax
0x180063fcb  xorps   xmm0, xmm0
0x180063fce  test    byte ptr [rcx+2Ch], 2
0x180063fd2  xorps   xmm1, xmm1
0x180063fd5  mov     r12d, r9d
0x180063fd8  mov     [rbp+57h+var_68], rax
0x180063fdc  mov     r13, r8
0x180063fdf  mov     [rbp+57h+var_50], rax
0x180063fe3  mov     r14, rdx
0x180063fe6  mov     [rbp+57h+arg_0], eax
0x180063fe9  mov     rsi, rcx
0x180063fec  movups  [rbp+57h+var_78], xmm0
0x180063ff0  movups  [rbp+57h+var_60], xmm1
0x180063ff4  jz      short loc_18006404B
0x180063ff6  mov     rax, cs:WPP_GLOBAL_Control
0x180063ffd  lea     rdi, WPP_GLOBAL_Control
0x180064004  cmp     rax, rdi
0x180064007  jz      short loc_180064041
0x180064009  test    byte ptr [rax+1Ch], 8
0x18006400d  jz      short loc_180064041
0x18006400f  cmp     byte ptr [rax+19h], 2
0x180064013  jb      short loc_180064041
0x180064015  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006401a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064021  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x180064028  mov     edx, 10h
0x18006402d  mov     dword ptr [rsp+0F0h+var_D0], 8000FFFFh
0x180064035  mov     r9d, eax
0x180064038  mov     rcx, [rcx+10h]
0x18006403c  call    WPP_SF_Dd
0x180064041  mov     ebx, 8000FFFFh
0x180064046  jmp     loc_1800644EE
0x18006404b  mov     rcx, [rcx+58h]
0x18006404f  mov     rax, [rcx]
0x180064052  mov     rax, [rax+90h]
0x180064059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006405e  lea     rdi, [rsi+90h]
0x180064065  mov     rbx, rax
0x180064068  cmp     rax, [rdi]
0x18006406b  jz      short loc_18006408C
0x18006406d  mov     rcx, rdi
0x180064070  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180064075  mov     [rdi], rbx
0x180064078  test    rbx, rbx
0x18006407b  jz      short loc_18006408C
0x18006407d  mov     rcx, [rbx]
0x180064080  mov     rax, [rcx+8]
0x180064084  mov     rcx, rbx
0x180064087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006408c  or      dword ptr [rsi+2Ch], 2
0x180064090  mov     rcx, [rsi+58h]
0x180064094  mov     rax, [rcx]
0x180064097  mov     rax, [rax+98h]
0x18006409e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640a3  lea     rbx, [rsi+88h]
0x1800640aa  mov     rdi, rax
0x1800640ad  cmp     rax, [rbx]
0x1800640b0  jz      short loc_1800640C5
0x1800640b2  mov     rcx, rbx
0x1800640b5  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800640ba  mov     rcx, rbx
0x1800640bd  mov     [rbx], rdi
0x1800640c0  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800640c5  cmp     qword ptr [rbx], 0
0x1800640c9  jnz     short loc_180064120
0x1800640cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800640d2  lea     rdi, WPP_GLOBAL_Control
0x1800640d9  cmp     rax, rdi
0x1800640dc  jz      short loc_180064116
0x1800640de  test    byte ptr [rax+1Ch], 8
0x1800640e2  jz      short loc_180064116
0x1800640e4  cmp     byte ptr [rax+19h], 2
0x1800640e8  jb      short loc_180064116
0x1800640ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800640ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640f6  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x1800640fd  mov     edx, 12h
0x180064102  mov     dword ptr [rsp+0F0h+var_D0], 80004001h
0x18006410a  mov     r9d, eax
0x18006410d  mov     rcx, [rcx+10h]
0x180064111  call    WPP_SF_Dd
0x180064116  mov     ebx, 80004001h
0x18006411b  jmp     loc_1800644EE
0x180064120  lea     r15, [rsi+80h]
0x180064127  mov     rdx, r15; void **
0x18006412a  call    ?CreateInstance@CRDPCollectionMT@@SAJAEBU_GUID@@PEAPEAX@Z; CRDPCollectionMT::CreateInstance(_GUID const &,void * *)
0x18006412f  mov     ebx, eax
0x180064131  test    eax, eax
0x180064133  jns     short loc_180064199
0x180064135  mov     rax, cs:WPP_GLOBAL_Control
0x18006413c  lea     rdi, WPP_GLOBAL_Control
0x180064143  cmp     rax, rdi
0x180064146  jz      loc_1800644EE
0x18006414c  test    byte ptr [rax+1Ch], 8
0x180064150  jz      loc_1800644EE
0x180064156  cmp     byte ptr [rax+19h], 2
0x18006415a  jb      loc_1800644EE
0x180064160  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064165  mov     edx, 13h
0x18006416a  lea     rcx, aCrdpcollection_0; "CRDPCollectionMT::CreateInstance failed"
0x180064171  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180064175  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x18006417c  mov     [rsp+0F0h+var_D0], rcx
0x180064181  mov     r9d, eax
0x180064184  mov     rcx, cs:WPP_GLOBAL_Control
0x18006418b  mov     rcx, [rcx+10h]
0x18006418f  call    WPP_SF_DsD
0x180064194  jmp     loc_1800644EE
0x180064199  call    RDPWDUMX_CreateLegacyContext
0x18006419e  mov     ebx, eax
0x1800641a0  test    eax, eax
0x1800641a2  jns     short loc_1800641E2
0x1800641a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800641ab  lea     rdi, WPP_GLOBAL_Control
0x1800641b2  cmp     rax, rdi
0x1800641b5  jz      loc_1800644EE
0x1800641bb  test    byte ptr [rax+1Ch], 8
0x1800641bf  jz      loc_1800644EE
0x1800641c5  cmp     byte ptr [rax+19h], 2
0x1800641c9  jb      loc_1800644EE
0x1800641cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800641d4  mov     edx, 14h
0x1800641d9  lea     rcx, aFailedToInitTh; "Failed to init the legacy stack context"
0x1800641e0  jmp     short loc_180064171
0x1800641e2  lea     rbx, [rsi+78h]
0x1800641e6  mov     dword ptr [rsi+0B4h], 1
0x1800641f0  mov     [rsi+0B0h], r12d
0x1800641f7  cmp     r14, [rbx]
0x1800641fa  jz      short loc_18006420F
0x1800641fc  mov     rcx, rbx
0x1800641ff  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180064204  mov     rcx, rbx
0x180064207  mov     [rbx], r14
0x18006420a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18006420f  mov     rcx, [r15]
0x180064212  lea     r8, [rbp+57h+var_78]
0x180064216  mov     eax, 17h
0x18006421b  mov     dword ptr [rbp+57h+var_78+8], r12d
0x18006421f  mov     word ptr [rbp+57h+var_78], ax
0x180064223  lea     rdx, aConnectionid; "ConnectionID"
0x18006422a  mov     rax, [rcx]
0x18006422d  mov     rax, [rax+38h]
0x180064231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064236  xor     r14d, r14d
0x180064239  mov     ebx, eax
0x18006423b  test    eax, eax
0x18006423d  jns     short loc_18006427F
0x18006423f  mov     rax, cs:WPP_GLOBAL_Control
0x180064246  lea     rdi, WPP_GLOBAL_Control
0x18006424d  cmp     rax, rdi
0x180064250  jz      loc_1800644EE
0x180064256  test    byte ptr [rax+1Ch], 8
0x18006425a  jz      loc_1800644EE
0x180064260  cmp     byte ptr [rax+19h], 2
0x180064264  jb      loc_1800644EE
0x18006426a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006426f  lea     edx, [r14+15h]
0x180064273  lea     rcx, aFailedToSetThe_7; "Failed to set the property connection I"...
0x18006427a  jmp     loc_180064171
0x18006427f  mov     rcx, [rsi+58h]
0x180064283  lea     r8, [rbp+57h+arg_0]
0x180064287  lea     rdx, aGfxpipelineFor; "GfxPipeline::ForceLyncProfile"
0x18006428e  mov     rax, [rcx]
0x180064291  mov     rax, [rax+20h]
0x180064295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006429a  lea     rdi, WPP_GLOBAL_Control
0x1800642a1  mov     ebx, eax
0x1800642a3  test    eax, eax
0x1800642a5  jns     loc_180064370
0x1800642ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800642b2  cmp     rcx, rdi
0x1800642b5  jz      short loc_1800642F7
0x1800642b7  test    byte ptr [rcx+1Ch], 8
0x1800642bb  jz      short loc_1800642F7
0x1800642bd  cmp     byte ptr [rcx+19h], 2
0x1800642c1  jb      short loc_1800642F7
0x1800642c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800642c8  lea     rcx, aFailedToGetGfx; "Failed to get GFX_PIPELINE_FORCELYNCPRO"...
0x1800642cf  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x1800642d3  mov     [rsp+0F0h+var_D0], rcx
0x1800642d8  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x1800642df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800642e6  mov     edx, 16h
0x1800642eb  mov     r9d, eax
0x1800642ee  mov     rcx, [rcx+10h]
0x1800642f2  call    WPP_SF_DsD
0x1800642f7  mov     rcx, [rsi+58h]
0x1800642fb  mov     rax, [rcx]
0x1800642fe  mov     rax, [rax+0B0h]
0x180064305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006430a  mov     rcx, [r15]
0x18006430d  lea     r8, [rbp+57h+var_60]
0x180064311  mov     dword ptr [rbp+57h+var_60+8], eax
0x180064314  lea     rdx, aSessionid; "SessionID"
0x18006431b  mov     r12d, 17h
0x180064321  mov     word ptr [rbp+57h+var_60], r12w
0x180064326  mov     rax, [rcx]
0x180064329  mov     rax, [rax+38h]
0x18006432d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064332  mov     ebx, eax
0x180064334  test    eax, eax
0x180064336  jns     short loc_18006437B
0x180064338  mov     rax, cs:WPP_GLOBAL_Control
0x18006433f  cmp     rax, rdi
0x180064342  jz      loc_1800644EE
0x180064348  test    byte ptr [rax+1Ch], 8
0x18006434c  jz      loc_1800644EE
0x180064352  cmp     byte ptr [rax+19h], 2
0x180064356  jb      loc_1800644EE
0x18006435c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064361  mov     edx, r12d
0x180064364  lea     rcx, aFailedToSetThe_19; "Failed to set the unique session ID"
0x18006436b  jmp     loc_180064171
0x180064370  cmp     [rbp+57h+arg_0], r14d
0x180064374  jz      short loc_1800642F7
0x180064376  or      eax, 0FFFFFFFFh
0x180064379  jmp     short loc_18006430A
0x18006437b  mov     rcx, [rsi+58h]
0x18006437f  lea     r8, [rbp+57h+var_A0]
0x180064383  mov     [rbp+57h+var_A0], r14d
0x180064387  lea     rdx, aRdpwdumxDisabl; "RDPWDUMX::DisableCompression"
0x18006438e  mov     rax, [rcx]
0x180064391  mov     rax, [rax+20h]
0x180064395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006439a  test    eax, eax
0x18006439c  js      short loc_18006440F
0x18006439e  cmp     [rbp+57h+var_A0], r14d
0x1800643a2  jz      short loc_18006440F
0x1800643a4  mov     rcx, [r15]
0x1800643a7  lea     rdx, aMaxcompression_0; "MaxCompressionLevel"
0x1800643ae  xor     r8d, r8d
0x1800643b1  mov     rax, [rcx]
0x1800643b4  mov     rax, [rax+48h]
0x1800643b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643bd  mov     ebx, eax
0x1800643bf  test    eax, eax
0x1800643c1  jns     short loc_18006440F
0x1800643c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800643ca  cmp     rcx, rdi
0x1800643cd  jz      short loc_18006440F
0x1800643cf  test    byte ptr [rcx+1Ch], 8
0x1800643d3  jz      short loc_18006440F
0x1800643d5  cmp     byte ptr [rcx+19h], 2
0x1800643d9  jb      short loc_18006440F
0x1800643db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800643e0  lea     rcx, aFailedToDisabl; "Failed to disable compression as reques"...
0x1800643e7  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x1800643eb  mov     [rsp+0F0h+var_D0], rcx
0x1800643f0  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x1800643f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800643fe  mov     edx, 18h
0x180064403  mov     r9d, eax
0x180064406  mov     rcx, [rcx+10h]
0x18006440a  call    WPP_SF_DsD
0x18006440f  lea     rdi, [rsi+70h]
0x180064413  mov     ebx, r14d
0x180064416  cmp     r13, [rdi]
0x180064419  jz      short loc_18006442E
0x18006441b  mov     rcx, rdi
0x18006441e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180064423  mov     rcx, rdi
0x180064426  mov     [rdi], r13
0x180064429  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18006442e  xor     r9d, r9d; lpName
0x180064431  xor     r8d, r8d; bInitialState
0x180064434  xor     ecx, ecx; lpEventAttributes
0x180064436  lea     edx, [r9+1]; bManualReset
0x18006443a  call    cs:__imp_CreateEventW
0x180064440  mov     [rsi+0C0h], rax
0x180064447  test    rax, rax
0x18006444a  jnz     loc_1800644F6
0x180064450  mov     eax, cs:CallbackContext
0x180064456  cmp     eax, 2
0x180064459  jbe     short loc_1800644D5
0x18006445b  call    cs:__imp_GetLastError
0x180064461  lea     rdx, dword_180287664
0x180064468  mov     [rbp+57h+var_98], 0CBh
0x18006446f  mov     [rbp+57h+var_9C], eax
0x180064472  lea     rax, aInitializeinst_0; "InitializeInstance"
0x180064479  mov     [rbp+57h+var_90], rax
0x18006447d  lea     rax, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064484  mov     [rbp+57h+var_88], rax
0x180064488  lea     rax, aFailedToCreate_133; "Failed to create the StackCreated event"...
0x18006448f  mov     [rbp+57h+var_80], rax
0x180064493  lea     rax, [rbp+57h+var_9C]
0x180064497  mov     [rsp+0F0h+var_A8], rax
0x18006449c  lea     rax, [rbp+57h+var_90]
0x1800644a0  mov     [rsp+0F0h+var_B0], rax
0x1800644a5  lea     rax, [rbp+57h+var_98]
0x1800644a9  mov     [rsp+0F0h+var_B8], rax
  ... truncated ...
```
