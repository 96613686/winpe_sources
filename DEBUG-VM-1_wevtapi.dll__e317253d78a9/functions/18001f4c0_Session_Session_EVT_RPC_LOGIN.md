# Session::Session(_EVT_RPC_LOGIN *)

- ea: `0x18001f4c0`
- end: `0x18001fade`
- name: `??0Session@@QEAA@PEAU_EVT_RPC_LOGIN@@@Z`
- size: `1566`
- prototype: `Session *__fastcall(Session *__hidden this, struct _EVT_RPC_LOGIN *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180007940`
- `0x180021d1c`

## callees

- `0x18000a724`
- `0x18000bf84`
- `0x18000c9b4`
- `0x18000f624`
- `0x18001e488`
- `0x18001e4bc`
- `0x18001ea28`
- `0x18001f4c0`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `RPCRT4!RpcBindingSetOption` at `0x18001f783`
- `RPCRT4!RpcBindingSetOption` at `0x18001f783`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001f5ab`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001f5ab`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f558`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f589`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f558`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f589`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001f767`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001f767`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
Session *__fastcall Session::Session(Session *this, struct _EVT_RPC_LOGIN *a2)
{
  _QWORD *v4; // rdx
  RPC_BINDING_HANDLE *v5; // r12
  RPC_WSTR *StringBinding; // rax
  unsigned int v7; // eax
  LPWSTR Server; // r14
  RPC_WSTR *v9; // rax
  unsigned int v10; // esi
  RPC_BINDING_HANDLE *v11; // rax
  unsigned int v12; // esi
  __int128 *v13; // r15
  LPWSTR User; // rcx
  __int64 v15; // rax
  LPWSTR Domain; // rcx
  __int64 v17; // rax
  LPWSTR Password; // rcx
  __int64 v19; // rax
  DWORD Flags; // ecx
  DWORD v21; // ecx
  DWORD v22; // ecx
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  __int128 pExceptionObject; // [rsp+40h] [rbp-99h] BYREF
  __int64 v30; // [rsp+50h] [rbp-89h]
  int v31; // [rsp+58h] [rbp-81h]
  int v32; // [rsp+5Ch] [rbp-7Dh]
  int v33; // [rsp+60h] [rbp-79h]
  char v34; // [rsp+64h] [rbp-75h]
  RPC_WSTR v35; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int16 *v37; // [rsp+78h] [rbp-61h]
  _WORD v38[8]; // [rsp+80h] [rbp-59h] BYREF
  __int128 v39; // [rsp+90h] [rbp-49h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-39h]
  __int128 v41; // [rsp+B0h] [rbp-29h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v43; // [rsp+D0h] [rbp-9h]
  __int128 v44; // [rsp+E0h] [rbp+7h]
  Session *v45; // [rsp+F0h] [rbp+17h]

  v45 = this;
  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_WORD *)this + 14) = 0;
  *((_BYTE *)this + 30) = 1;
  *(_QWORD *)this = &Session::`vftable';
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>((char *)this + 32);
  *((_QWORD *)this + 8) = 0;
  v5 = (RPC_BINDING_HANDLE *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  v35 = 0;
  if ( v4 && *v4 )
  {
    StringBinding = (RPC_WSTR *)tlx::replace<tlx::handle_traits<wchar_t *,long (wchar_t *),&long MyRpcStringFree(wchar_t *),0>>(&v35);
    v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", a2->Server, 0, 0, StringBinding);
    Server = a2->Server;
  }
  else
  {
    v9 = (RPC_WSTR *)tlx::replace<tlx::handle_traits<wchar_t *,long (wchar_t *),&long MyRpcStringFree(wchar_t *),0>>(&v35);
    v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"eventlog", 0, v9);
    Server = 0;
  }
  v10 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, v7);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v30 = 0;
    v31 = v10;
    v32 = -1;
    v33 = -1;
    v34 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v11 = (RPC_BINDING_HANDLE *)tlx::replace<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>((char *)this + 72);
  v12 = RpcBindingFromStringBindingW(v35, v11);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, v12);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v30 = 0;
    v31 = v12;
    v32 = -1;
    v33 = -1;
    v34 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v13 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( !a2 )
    goto LABEL_24;
  User = a2->User;
  if ( User )
  {
    *(_QWORD *)&v39 = a2->User;
    v15 = -1;
    do
      ++v15;
    while ( User[v15] );
    DWORD2(v39) = v15;
    v13 = &v39;
  }
  Domain = a2->Domain;
  if ( Domain )
  {
    *(_QWORD *)&v40 = a2->Domain;
    v17 = -1;
    do
      ++v17;
    while ( Domain[v17] );
    DWORD2(v40) = v17;
    v13 = &v39;
  }
  Password = a2->Password;
  if ( Password )
  {
    *(_QWORD *)&v41 = a2->Password;
    v19 = -1;
    do
      ++v19;
    while ( Password[v19] );
    DWORD2(v41) = v19;
    v13 = &v39;
  }
  HIDWORD(v41) = 2;
  Flags = a2->Flags;
  if ( Flags )
  {
    v21 = Flags - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 != 1 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, 87);
          }
          pExceptionObject = 0;
          v30 = 0;
          v31 = 87;
          v32 = -1;
          v33 = 130;
          throw (EvtException *)&pExceptionObject;
        }
LABEL_24:
        v23 = 10;
        goto LABEL_25;
      }
      if ( !Server )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, 87);
        }
        pExceptionObject = 0;
        v30 = 0;
        v31 = 87;
        v32 = -1;
        v33 = 119;
        throw (EvtException *)&pExceptionObject;
      }
      v23 = 16;
    }
    else
    {
      if ( !Server )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, 87);
        }
        pExceptionObject = 0;
        v30 = 0;
        v31 = 87;
        v32 = -1;
        v33 = 110;
        throw (EvtException *)&pExceptionObject;
      }
      v23 = 9;
    }
  }
  else
  {
    v23 = 10 - (Server != 0);
  }
LABEL_25:
  v43 = 0;
  v44 = 0;
  SecurityQOS.Version = 4;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 3;
  v24 = v38;
  v36 = v38;
  v25 = v38;
  v37 = v38;
  v38[0] = 0;
  if ( Server )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v36,
                             L"host/",
                             5)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &v36,
                             Server) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, 14);
      }
      pExceptionObject = 0;
      v30 = 0;
      v31 = 14;
      v32 = -1;
      v33 = 154;
      throw (EvtException *)&pExceptionObject;
    }
    v25 = v37;
    v24 = v36;
  }
  else
  {
    *(_QWORD *)&v44 = &unk_1800419B8;
    SecurityQOS.Capabilities = 17;
  }
  if ( v24 == v25 )
    v24 = 0;
  v26 = RpcBindingSetAuthInfoExW(*v5, v24, 6u, v23, v13, 0xFFFFFFFF, &SecurityQOS);
  v27 = v26;
  if ( v26 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ee73b2d0816435d812843a965169dfc4_Traceguids, v26);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v30 = 0;
    v31 = v27;
    v32 = -1;
    v33 = -1;
    v34 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !Server )
    RpcBindingSetOption(*v5, 9u, 1u);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v36);
  tlx::unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&long MyRpcStringFree(wchar_t *),0>>::~unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&long MyRpcStringFree(wchar_t *),0>>(&v35);
  return this;
}

```

## disassembly

```asm
0x18001f4c0  mov     [rsp-8+arg_10], rbx
0x18001f4c5  push    rbp
0x18001f4c6  push    rsi
0x18001f4c7  push    rdi
0x18001f4c8  push    r12
0x18001f4ca  push    r13
0x18001f4cc  push    r14
0x18001f4ce  push    r15
0x18001f4d0  lea     rbp, [rsp-27h]
0x18001f4d5  sub     rsp, 100h
0x18001f4dc  mov     rbx, rdx
0x18001f4df  mov     rdi, rcx
0x18001f4e2  mov     [rbp+57h+var_40], rcx
0x18001f4e6  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18001f4ed  mov     [rcx], rax
0x18001f4f0  xor     r13d, r13d
0x18001f4f3  mov     [rcx+8], r13d
0x18001f4f7  mov     [rcx+10h], r13
0x18001f4fb  mov     [rcx+18h], r13d
0x18001f4ff  mov     [rcx+1Ch], r13w
0x18001f504  mov     byte ptr [rcx+1Eh], 1
0x18001f508  lea     rax, ??_7Session@@6B@; const Session::`vftable'
0x18001f50f  mov     [rcx], rax
0x18001f512  add     rcx, 20h ; ' '
0x18001f516  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x18001f51b  nop
0x18001f51c  mov     [rdi+40h], r13
0x18001f520  lea     r12, [rdi+48h]
0x18001f524  mov     [r12], r13
0x18001f528  mov     [rbp+57h+var_C8], r13
0x18001f52c  test    rdx, rdx
0x18001f52f  jz      short loc_18001F563
0x18001f531  cmp     [rdx], r13
0x18001f534  jz      short loc_18001F563
0x18001f536  lea     rcx, [rbp+57h+var_C8]
0x18001f53a  call    ??$replace@U?$handle_traits@PEA_W$$A6AJPEA_W@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEA_WAEAV?$unique_any@U?$handle_traits@PEA_W$$A6AJPEA_W@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>>(tlx::unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>> &)
0x18001f53f  mov     [rsp+130h+StringBinding], rax; StringBinding
0x18001f544  mov     [rsp+130h+Options], r13; Options
0x18001f549  xor     r9d, r9d; Endpoint
0x18001f54c  mov     r8, [rbx]; NetworkAddr
0x18001f54f  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18001f556  xor     ecx, ecx; ObjUuid
0x18001f558  call    cs:__imp_RpcStringBindingComposeW
0x18001f55e  mov     r14, [rbx]
0x18001f561  jmp     short loc_18001F592
0x18001f563  lea     rcx, [rbp+57h+var_C8]
0x18001f567  call    ??$replace@U?$handle_traits@PEA_W$$A6AJPEA_W@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEA_WAEAV?$unique_any@U?$handle_traits@PEA_W$$A6AJPEA_W@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>>(tlx::unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>> &)
0x18001f56c  mov     [rsp+130h+StringBinding], rax; StringBinding
0x18001f571  mov     [rsp+130h+Options], r13; Options
0x18001f576  lea     r9, Endpoint; "eventlog"
0x18001f57d  xor     r8d, r8d; NetworkAddr
0x18001f580  lea     rdx, aNcalrpc; "ncalrpc"
0x18001f587  xor     ecx, ecx; ObjUuid
0x18001f589  call    cs:__imp_RpcStringBindingComposeW
0x18001f58f  mov     r14, r13
0x18001f592  mov     esi, eax
0x18001f594  test    eax, eax
0x18001f596  jnz     loc_18001F830
0x18001f59c  mov     rcx, r12
0x18001f59f  call    ??$replace@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>> &)
0x18001f5a4  mov     rdx, rax; Binding
0x18001f5a7  mov     rcx, [rbp+57h+var_C8]; StringBinding
0x18001f5ab  call    cs:__imp_RpcBindingFromStringBindingW
0x18001f5b1  mov     esi, eax
0x18001f5b3  test    eax, eax
0x18001f5b5  jnz     loc_18001F8A8
0x18001f5bb  mov     r15, r13
0x18001f5be  xorps   xmm0, xmm0
0x18001f5c1  movups  [rbp+57h+var_A0], xmm0
0x18001f5c5  movups  [rbp+57h+var_90], xmm0
0x18001f5c9  movups  [rbp+57h+var_80], xmm0
0x18001f5cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f5d1  test    rbx, rbx
0x18001f5d4  jz      loc_18001F66A
0x18001f5da  mov     rcx, [rbx+8]
0x18001f5de  test    rcx, rcx
0x18001f5e1  jz      short loc_18001F5FB
0x18001f5e3  mov     qword ptr [rbp+57h+var_A0], rcx
0x18001f5e7  mov     rax, rsi
0x18001f5ea  inc     rax
0x18001f5ed  cmp     [rcx+rax*2], r13w
0x18001f5f2  jnz     short loc_18001F5EA
0x18001f5f4  mov     dword ptr [rbp+57h+var_A0+8], eax
0x18001f5f7  lea     r15, [rbp+57h+var_A0]
0x18001f5fb  mov     rcx, [rbx+10h]
0x18001f5ff  test    rcx, rcx
0x18001f602  jz      short loc_18001F61C
0x18001f604  mov     qword ptr [rbp+57h+var_90], rcx
0x18001f608  mov     rax, rsi
0x18001f60b  inc     rax
0x18001f60e  cmp     [rcx+rax*2], r13w
0x18001f613  jnz     short loc_18001F60B
0x18001f615  mov     dword ptr [rbp+57h+var_90+8], eax
0x18001f618  lea     r15, [rbp+57h+var_A0]
0x18001f61c  mov     rcx, [rbx+18h]
0x18001f620  test    rcx, rcx
0x18001f623  jz      short loc_18001F63D
0x18001f625  mov     qword ptr [rbp+57h+var_80], rcx
0x18001f629  mov     rax, rsi
0x18001f62c  inc     rax
0x18001f62f  cmp     [rcx+rax*2], r13w
0x18001f634  jnz     short loc_18001F62C
0x18001f636  mov     dword ptr [rbp+57h+var_80+8], eax
0x18001f639  lea     r15, [rbp+57h+var_A0]
0x18001f63d  mov     dword ptr [rbp+57h+var_80+0Ch], 2
0x18001f644  mov     ecx, [rbx+20h]
0x18001f647  test    ecx, ecx
0x18001f649  jz      loc_18001F717
0x18001f64f  sub     ecx, 1
0x18001f652  jz      loc_18001F704
0x18001f658  sub     ecx, 1
0x18001f65b  jz      loc_18001F6F1
0x18001f661  cmp     ecx, 1
0x18001f664  jnz     loc_18001F920
0x18001f66a  mov     ebx, 0Ah
0x18001f66f  xorps   xmm0, xmm0
0x18001f672  movdqu  [rbp+57h+var_60], xmm0
0x18001f677  xorps   xmm1, xmm1
0x18001f67a  movdqu  [rbp+57h+var_50], xmm1
0x18001f67f  mov     [rbp+57h+var_70.Version], 4
0x18001f686  mov     [rbp+57h+var_70.Capabilities], 1
0x18001f68d  mov     [rbp+57h+var_70.IdentityTracking], 1
0x18001f694  mov     [rbp+57h+var_70.ImpersonationType], 3
0x18001f69b  lea     rdx, [rbp+57h+var_B0]
0x18001f69f  mov     [rbp+57h+var_C0], rdx
0x18001f6a3  lea     rcx, [rbp+57h+var_B0]
0x18001f6a7  mov     [rbp+57h+var_B8], rcx
0x18001f6ab  mov     [rbp+57h+var_B0], r13w
0x18001f6b0  test    r14, r14
0x18001f6b3  jz      short loc_18001F72B
0x18001f6b5  mov     r8d, 5
0x18001f6bb  lea     rdx, aHost; "host/"
0x18001f6c2  lea     rcx, [rbp+57h+var_C0]
0x18001f6c6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001f6cb  test    al, al
0x18001f6cd  jz      loc_18001FA6D
0x18001f6d3  mov     rdx, r14
0x18001f6d6  lea     rcx, [rbp+57h+var_C0]
0x18001f6da  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x18001f6df  test    al, al
0x18001f6e1  jz      loc_18001FA6D
0x18001f6e7  mov     rcx, [rbp+57h+var_B8]
0x18001f6eb  mov     rdx, [rbp+57h+var_C0]
0x18001f6ef  jmp     short loc_18001F73D
0x18001f6f1  test    r14, r14
0x18001f6f4  jz      loc_18001F98F
0x18001f6fa  mov     ebx, 10h
0x18001f6ff  jmp     loc_18001F66F
0x18001f704  test    r14, r14
0x18001f707  jz      loc_18001F9FE
0x18001f70d  mov     ebx, 9
0x18001f712  jmp     loc_18001F66F
0x18001f717  mov     rax, r14
0x18001f71a  neg     rax
0x18001f71d  sbb     ecx, ecx
0x18001f71f  mov     ebx, 0Ah
0x18001f724  add     ebx, ecx
0x18001f726  jmp     loc_18001F66F
0x18001f72b  lea     rax, unk_1800419B8
0x18001f732  mov     qword ptr [rbp+57h+var_50], rax
0x18001f736  mov     [rbp+57h+var_70.Capabilities], 11h
0x18001f73d  cmp     rdx, rcx
0x18001f740  cmovz   rdx, r13; ServerPrincName
0x18001f744  lea     rax, [rbp+57h+var_70]
0x18001f748  mov     [rsp+130h+SecurityQOS], rax; SecurityQOS
0x18001f74d  mov     dword ptr [rsp+130h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18001f755  mov     [rsp+130h+Options], r15; AuthIdentity
0x18001f75a  mov     r9d, ebx; AuthnSvc
0x18001f75d  mov     r8d, 6; AuthnLevel
0x18001f763  mov     rcx, [r12]; Binding
0x18001f767  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18001f76d  mov     ebx, eax
0x18001f76f  test    eax, eax
0x18001f771  jnz     short loc_18001F7BC
0x18001f773  test    r14, r14
0x18001f776  jnz     short loc_18001F78A
0x18001f778  lea     edx, [rax+9]; option
0x18001f77b  lea     r8d, [rax+1]; optionValue
0x18001f77f  mov     rcx, [r12]; hBinding
0x18001f783  call    cs:__imp_RpcBindingSetOption
0x18001f789  nop
0x18001f78a  lea     rcx, [rbp+57h+var_C0]
0x18001f78e  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18001f793  nop
0x18001f794  lea     rcx, [rbp+57h+var_C8]
0x18001f798  call    ??1?$unique_any@U?$handle_traits@PEA_W$$A6AJPEA_W@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>>::~unique_any<tlx::handle_traits<wchar_t *,long (wchar_t *),&MyRpcStringFree(wchar_t *),0>>(void)
0x18001f79d  nop
0x18001f79e  mov     rax, rdi
0x18001f7a1  mov     rbx, [rsp+130h+arg_10]
0x18001f7a9  add     rsp, 100h
0x18001f7b0  pop     r15
0x18001f7b2  pop     r14
0x18001f7b4  pop     r13
0x18001f7b6  pop     r12
0x18001f7b8  pop     rdi
0x18001f7b9  pop     rsi
0x18001f7ba  pop     rbp
0x18001f7bb  retn
0x18001f7bc  lea     rax, WPP_GLOBAL_Control
0x18001f7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7ca  cmp     rcx, rax
0x18001f7cd  jz      short loc_18001F7F6
0x18001f7cf  test    dword ptr [rcx+1Ch], 40000h
0x18001f7d6  jz      short loc_18001F7F6
0x18001f7d8  cmp     byte ptr [rcx+19h], 2
0x18001f7dc  jb      short loc_18001F7F6
0x18001f7de  mov     edx, 10h
0x18001f7e3  mov     r9d, ebx
0x18001f7e6  lea     r8, WPP_ee73b2d0816435d812843a965169dfc4_Traceguids
0x18001f7ed  mov     rcx, [rcx+10h]
0x18001f7f1  call    WPP_SF_D
0x18001f7f6  lea     rax, word_18004024A
0x18001f7fd  mov     qword ptr [rsp+130h+pExceptionObject], rax
0x18001f802  mov     qword ptr [rsp+130h+pExceptionObject+8], r13
0x18001f807  mov     [rsp+130h+var_E0], r13
0x18001f80c  mov     [rsp+130h+var_D8], ebx
0x18001f810  mov     [rbp+57h+var_D4], 0FFFFFFFFh
0x18001f817  mov     [rbp+57h+var_D0], esi
0x18001f81a  mov     [rbp+57h+var_CC], r13b
0x18001f81e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f825  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001f82a  call    _CxxThrowException_0
0x18001f830  lea     rax, WPP_GLOBAL_Control
0x18001f837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f83e  cmp     rcx, rax
0x18001f841  jz      short loc_18001F86A
0x18001f843  test    dword ptr [rcx+1Ch], 40000h
0x18001f84a  jz      short loc_18001F86A
0x18001f84c  cmp     byte ptr [rcx+19h], 2
0x18001f850  jb      short loc_18001F86A
0x18001f852  mov     edx, 0Ah
0x18001f857  mov     r9d, esi
0x18001f85a  lea     r8, WPP_ee73b2d0816435d812843a965169dfc4_Traceguids
0x18001f861  mov     rcx, [rcx+10h]
0x18001f865  call    WPP_SF_D
0x18001f86a  lea     rax, word_18004024A
0x18001f871  mov     qword ptr [rsp+130h+pExceptionObject], rax
0x18001f876  mov     qword ptr [rsp+130h+pExceptionObject+8], r13
0x18001f87b  mov     [rsp+130h+var_E0], r13
0x18001f880  mov     [rsp+130h+var_D8], esi
0x18001f884  mov     [rbp+57h+var_D4], 0FFFFFFFFh
0x18001f88b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f88f  mov     [rbp+57h+var_D0], esi
0x18001f892  mov     [rbp+57h+var_CC], r13b
0x18001f896  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f89d  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001f8a2  call    _CxxThrowException_0
0x18001f8a8  lea     rax, WPP_GLOBAL_Control
0x18001f8af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8b6  cmp     rcx, rax
0x18001f8b9  jz      short loc_18001F8E2
0x18001f8bb  test    dword ptr [rcx+1Ch], 40000h
0x18001f8c2  jz      short loc_18001F8E2
0x18001f8c4  cmp     byte ptr [rcx+19h], 2
0x18001f8c8  jb      short loc_18001F8E2
0x18001f8ca  mov     edx, 0Bh
0x18001f8cf  mov     r9d, esi
0x18001f8d2  lea     r8, WPP_ee73b2d0816435d812843a965169dfc4_Traceguids
0x18001f8d9  mov     rcx, [rcx+10h]
0x18001f8dd  call    WPP_SF_D
0x18001f8e2  lea     rax, word_18004024A
0x18001f8e9  mov     qword ptr [rsp+130h+pExceptionObject], rax
0x18001f8ee  mov     qword ptr [rsp+130h+pExceptionObject+8], r13
0x18001f8f3  mov     [rsp+130h+var_E0], r13
0x18001f8f8  mov     [rsp+130h+var_D8], esi
0x18001f8fc  mov     [rbp+57h+var_D4], 0FFFFFFFFh
0x18001f903  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f907  mov     [rbp+57h+var_D0], esi
0x18001f90a  mov     [rbp+57h+var_CC], r13b
0x18001f90e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f915  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001f91a  call    _CxxThrowException_0
0x18001f920  lea     rax, WPP_GLOBAL_Control
0x18001f927  mov     ebx, 57h ; 'W'
0x18001f92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f933  cmp     rcx, rax
0x18001f936  jz      short loc_18001F95D
0x18001f938  test    dword ptr [rcx+1Ch], 40000h
0x18001f93f  jz      short loc_18001F95D
0x18001f941  cmp     byte ptr [rcx+19h], 2
0x18001f945  jb      short loc_18001F95D
0x18001f947  lea     edx, [rbx-49h]
0x18001f94a  mov     r9d, ebx
0x18001f94d  lea     r8, WPP_ee73b2d0816435d812843a965169dfc4_Traceguids
0x18001f954  mov     rcx, [rcx+10h]
0x18001f958  call    WPP_SF_D
0x18001f95d  xorps   xmm0, xmm0
0x18001f960  movdqu  [rsp+130h+pExceptionObject], xmm0
0x18001f966  mov     [rsp+130h+var_E0], r13
0x18001f96b  mov     [rsp+130h+var_D8], ebx
0x18001f96f  mov     [rbp+57h+var_D4], 0FFFFFFFFh
0x18001f976  mov     [rbp+57h+var_D0], 82h
0x18001f97d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f984  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001f989  call    _CxxThrowException_0
0x18001f98f  lea     rax, WPP_GLOBAL_Control
0x18001f996  mov     ebx, 57h ; 'W'
0x18001f99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9a2  cmp     rcx, rax
0x18001f9a5  jz      short loc_18001F9CC
  ... truncated ...
```
