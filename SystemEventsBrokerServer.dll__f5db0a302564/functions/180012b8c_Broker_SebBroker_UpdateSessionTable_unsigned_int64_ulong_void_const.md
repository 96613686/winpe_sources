# Broker::SebBroker::UpdateSessionTable(unsigned __int64,ulong,void * const)

- ea: `0x180012b8c`
- end: `0x180013056`
- name: `?UpdateSessionTable@SebBroker@Broker@@AEAA_N_KKQEAX@Z`
- size: `1226`
- prototype: `bool(Broker::SebBroker *__hidden this, unsigned __int64, unsigned int, void *const)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180016590`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x180012b8c`
- `0x18001305c`
- `0x1800133c0`
- `0x180016150`
- `0x180018ba8`
- `0x180018e54`
- `0x180019618`
- `0x18001964c`
- `0x18001cf74`
- `0x18001d9ac`
- `0x18001e5b4`
- `0x18001e774`
- `0x18001f63c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180012fee`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180012fee`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180012eea`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180012f8d`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180012eea`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180012f8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char __fastcall Broker::SebBroker::UpdateSessionTable(
        Broker::SebBroker *this,
        unsigned __int64 a2,
        __int64 a3,
        char *pSid)
{
  char *v4; // r13
  unsigned int v5; // ebx
  unsigned __int64 v6; // rsi
  _QWORD *v8; // rcx
  char v9; // di
  char *v10; // rdi
  __int64 *v11; // rax
  __int64 *v12; // rcx
  char **v13; // rax
  const char *v14; // rdx
  __int64 *v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rax
  __int64 *v18; // r14
  std::_Ref_count_base *v19; // r12
  __int64 v20; // rcx
  __int64 v21; // rax
  const char *v22; // rdx
  char v23; // r14
  GUID *v24; // r14
  _QWORD *v25; // r15
  GUID *v26; // r14
  char v28; // [rsp+30h] [rbp-D8h]
  unsigned __int64 v29; // [rsp+38h] [rbp-D0h] BYREF
  char *v30; // [rsp+40h] [rbp-C8h] BYREF
  std::_Ref_count_base *v31; // [rsp+48h] [rbp-C0h]
  __int128 v32; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v34[16]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v35; // [rsp+80h] [rbp-88h]
  __int64 v36; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v37; // [rsp+98h] [rbp-70h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v39[80]; // [rsp+B8h] [rbp-50h] BYREF
  int v40; // [rsp+118h] [rbp+10h]
  unsigned int v41; // [rsp+120h] [rbp+18h] BYREF
  char *v42; // [rsp+128h] [rbp+20h]

  v42 = pSid;
  v41 = a3;
  v40 = a2;
  v4 = pSid;
  v5 = a3;
  v6 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x31u, a3, a2, a3, pSid);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v5 <= 0x400 )
  {
    v32 = 0;
    v35 = 0;
    v10 = (char *)operator new(0x68u);
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<Broker::_SessionInfo>::`vftable';
    Broker::_SessionInfo::_SessionInfo((Broker::_SessionInfo *)(v10 + 16), v4, 1, v6, v5);
    v33[0] = v10 + 16;
    v33[1] = v10;
    v12 = (__int64 *)*((_QWORD *)this + 2);
    v11 = (__int64 *)v12[1];
    HIDWORD(v30) = 0;
    while ( !*((_BYTE *)v11 + 25) )
    {
      if ( v11[4] >= v6 )
      {
        v12 = v11;
        v11 = (__int64 *)*v11;
      }
      else
      {
        v11 = (__int64 *)v11[2];
      }
    }
    if ( *((_BYTE *)v12 + 25) || v6 < v12[4] )
    {
      v13 = (char **)std::make_shared<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>,>(&v36);
      v29 = v6;
      v30 = *v13;
      v31 = (std::_Ref_count_base *)v13[1];
      *v13 = 0;
      v13[1] = 0;
      std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Emplace<std::pair<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>(
        (__int64 *)this + 2,
        (__int64)v34,
        &v29);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      if ( v37 )
        std::_Ref_count_base::_Decref(v37);
      if ( !v34[8] )
      {
        std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, v14);
        throw (std::out_of_range *)pExceptionObject;
      }
    }
    v15 = (__int64 *)*((_QWORD *)this + 2);
    v16 = (__int64 *)v15[1];
    HIDWORD(v30) = 0;
    while ( !*((_BYTE *)v16 + 25) )
    {
      if ( v16[4] >= v6 )
      {
        v15 = v16;
        v16 = (__int64 *)*v16;
      }
      else
      {
        v16 = (__int64 *)v16[2];
      }
    }
    if ( *((_BYTE *)v15 + 25) || v6 < v15[4] )
    {
      std::_Xout_of_range("invalid map<K, T> key");
      v9 = v28;
      LODWORD(v6) = v40;
      LOBYTE(v5) = v41;
      v4 = v42;
    }
    else
    {
      v17 = v15[6];
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      v18 = (__int64 *)v15[5];
      v19 = (std::_Ref_count_base *)v15[6];
      *(_QWORD *)&v35 = v18;
      *((_QWORD *)&v35 + 1) = v19;
      v20 = *v18;
      v21 = *(_QWORD *)(*v18 + 8);
      HIDWORD(v30) = 0;
      while ( !*(_BYTE *)(v21 + 25) )
      {
        if ( *(_DWORD *)(v21 + 32) >= v5 )
        {
          v20 = v21;
          v21 = *(_QWORD *)v21;
        }
        else
        {
          v21 = *(_QWORD *)(v21 + 16);
        }
      }
      if ( *(_BYTE *)(v20 + 25) || v5 < *(_DWORD *)(v20 + 32) )
      {
        LODWORD(v29) = v5;
        if ( v10 )
          _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
        v30 = v10 + 16;
        v31 = (std::_Ref_count_base *)v10;
        std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Emplace<std::pair<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>(
          v18,
          (__int64)v34,
          &v29);
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
      }
      else
      {
        std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::erase(
          v18,
          &v41);
        LODWORD(v29) = v5;
        std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(&v30, v33);
        v23 = *(_BYTE *)(std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>::insert<std::pair<unsigned long,std::shared_ptr<Broker::_SessionInfo>>,0>(
                           v18,
                           (__int64)v34,
                           &v29)
                       + 8);
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
        if ( !v23 )
        {
          std::out_of_range::out_of_range((std::out_of_range *)v39, v22);
          throw (std::out_of_range *)v39;
        }
      }
      v24 = &GUID_SESSION_DISPLAY_STATUS;
      if ( !v5 )
        v24 = &GUID_MONITOR_POWER_ON;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      *(_QWORD *)&v32 = Broker::SystemEventsBrokerDisplayNotificationCallback;
      *((_QWORD *)&v32 + 1) = v10 + 16;
      v25 = v10 + 40;
      if ( (unsigned int)PowerSettingRegisterNotificationEx(v24, v5, 2, &v32, v10 + 40) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
        *v25 = 0;
      }
      v26 = &GUID_SESSION_USER_PRESENCE;
      if ( !v5 )
        v26 = &GUID_GLOBAL_USER_PRESENCE;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      *(_QWORD *)&v32 = Broker::SystemEventsBrokerUserPresenceNotificationCallback;
      *((_QWORD *)&v32 + 1) = v10 + 16;
      if ( (unsigned int)PowerSettingRegisterNotificationEx(v26, v5, 2, &v32, v10 + 48) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
        *v25 = 0;
      }
      if ( v10 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v10);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      v9 = 1;
    }
    v8 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_dd(v8[2], 50, a3, v5, 1024);
      v8 = WPP_GLOBAL_Control;
    }
    v9 = 0;
  }
  if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_dd_sid_(v8[2], 0x39u, a3, v6, v5, v4);
  return v9;
}

```

## disassembly

```asm
0x180012b8c  mov     [rsp+arg_18], r9
0x180012b91  mov     [rsp+arg_10], r8d
0x180012b96  mov     [rsp+arg_8], rdx
0x180012b9b  push    rbx
0x180012b9c  push    rsi
0x180012b9d  push    rdi
0x180012b9e  push    r12
0x180012ba0  push    r13
0x180012ba2  push    r14
0x180012ba4  push    r15
0x180012ba6  sub     rsp, 0D0h
0x180012bad  mov     r13, r9
0x180012bb0  mov     ebx, r8d
0x180012bb3  mov     rsi, rdx
0x180012bb6  mov     r14, rcx
0x180012bb9  xor     r12d, r12d
0x180012bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bc3  test    byte ptr [rcx+1Ch], 1
0x180012bc7  jz      short loc_180012BF0
0x180012bc9  cmp     byte ptr [rcx+19h], 4
0x180012bcd  jb      short loc_180012BF0
0x180012bcf  mov     r9d, esi
0x180012bd2  lea     edx, [r12+31h]
0x180012bd7  mov     [rsp+108h+pSid], r13; pSid
0x180012bdc  mov     dword ptr [rsp+108h+var_E8], ebx; char
0x180012be0  mov     rcx, [rcx+10h]; LoggerHandle
0x180012be4  call    WPP_SF_dd_sid_
0x180012be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bf0  mov     eax, 400h
0x180012bf5  cmp     ebx, eax
0x180012bf7  jbe     short loc_180012C29
0x180012bf9  test    byte ptr [rcx+1Ch], 1
0x180012bfd  jz      short loc_180012C21
0x180012bff  cmp     byte ptr [rcx+19h], 2
0x180012c03  jb      short loc_180012C21
0x180012c05  mov     edx, 32h ; '2'
0x180012c0a  mov     dword ptr [rsp+108h+var_E8], eax
0x180012c0e  mov     r9d, ebx
0x180012c11  mov     rcx, [rcx+10h]
0x180012c15  call    WPP_SF_dd
0x180012c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c21  mov     dil, r12b
0x180012c24  jmp     loc_18001301A
0x180012c29  xorps   xmm0, xmm0
0x180012c2c  movups  [rsp+108h+var_B8], xmm0
0x180012c31  xorps   xmm1, xmm1
0x180012c34  movdqu  [rsp+108h+var_88], xmm1
0x180012c3d  mov     ecx, 68h ; 'h'; Size
0x180012c42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012c47  mov     rdi, rax
0x180012c4a  mov     [rsp+108h+var_A8], rax
0x180012c4f  mov     dword ptr [rax+8], 1
0x180012c56  mov     dword ptr [rax+0Ch], 1
0x180012c5d  lea     rax, ??_7?$_Ref_count_obj2@U_SessionInfo@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::_SessionInfo>::`vftable'
0x180012c64  mov     [rdi], rax
0x180012c67  lea     r15, [rdi+10h]
0x180012c6b  mov     dword ptr [rsp+108h+var_E8], ebx; unsigned int
0x180012c6f  mov     r9, rsi; unsigned __int64
0x180012c72  mov     r8b, 1; bool
0x180012c75  mov     rdx, r13; void *
0x180012c78  mov     rcx, r15; this
0x180012c7b  call    ??0_SessionInfo@Broker@@QEAA@PEAX_N_KK@Z; Broker::_SessionInfo::_SessionInfo(void *,bool,unsigned __int64,ulong)
0x180012c80  nop
0x180012c81  mov     [rsp+108h+var_A8], r15
0x180012c86  mov     [rsp+108h+var_A0], rdi
0x180012c8b  mov     rcx, [r14+10h]
0x180012c8f  mov     rax, [rcx+8]
0x180012c93  xor     edx, edx
0x180012c95  mov     dword ptr [rsp+108h+var_C8+4], edx
0x180012c99  jmp     short loc_180012CAD
0x180012c9b  cmp     [rax+20h], rsi
0x180012c9f  jnb     short loc_180012CA7
0x180012ca1  mov     rax, [rax+10h]
0x180012ca5  jmp     short loc_180012CAD
0x180012ca7  mov     rcx, rax
0x180012caa  mov     rax, [rax]
0x180012cad  cmp     [rax+19h], r12b
0x180012cb1  jz      short loc_180012C9B
0x180012cb3  cmp     [rcx+19h], r12b
0x180012cb7  jnz     short loc_180012CC3
0x180012cb9  cmp     rsi, [rcx+20h]
0x180012cbd  jnb     loc_180012D4E
0x180012cc3  lea     rcx, [rsp+108h+var_78]
0x180012ccb  call    ??$make_shared@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@$$V@std@@YA?AV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@0@XZ; std::make_shared<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>,>(void)
0x180012cd0  mov     rcx, rax
0x180012cd3  mov     [rsp+108h+var_D0], rsi
0x180012cd8  mov     rax, [rax]
0x180012cdb  mov     [rsp+40h], rax
0x180012ce0  mov     rax, [rcx+8]
0x180012ce4  mov     [rsp+108h+var_C0], rax
0x180012ce9  mov     [rcx], r12
0x180012cec  mov     [rcx+8], r12
0x180012cf0  lea     r8, [rsp+108h+var_D0]
0x180012cf5  lea     rdx, [rsp+108h+var_98]
0x180012cfa  lea     rcx, [r14+10h]
0x180012cfe  call    ??$_Emplace@U?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Emplace<std::pair<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>(std::pair<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>> &&)
0x180012d03  nop
0x180012d04  mov     rcx, [rsp+108h+var_C0]; this
0x180012d09  test    rcx, rcx
0x180012d0c  jz      short loc_180012D14
0x180012d0e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012d13  nop
0x180012d14  mov     rcx, [rsp+108h+var_70]; this
0x180012d1c  test    rcx, rcx
0x180012d1f  jz      short loc_180012D26
0x180012d21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012d26  cmp     [rsp+108h+var_90], r12b
0x180012d2b  jnz     short loc_180012D4E
0x180012d2d  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180012d35  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x180012d3a  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180012d41  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180012d49  call    _CxxThrowException_0
0x180012d4e  mov     rcx, [r14+10h]
0x180012d52  mov     rax, [rcx+8]
0x180012d56  xor     edx, edx
0x180012d58  mov     dword ptr [rsp+108h+var_C8+4], edx
0x180012d5c  jmp     short loc_180012D70
0x180012d5e  cmp     [rax+20h], rsi
0x180012d62  jnb     short loc_180012D6A
0x180012d64  mov     rax, [rax+10h]
0x180012d68  jmp     short loc_180012D70
0x180012d6a  mov     rcx, rax
0x180012d6d  mov     rax, [rax]
0x180012d70  cmp     [rax+19h], r12b
0x180012d74  jz      short loc_180012D5E
0x180012d76  cmp     [rcx+19h], r12b
0x180012d7a  jnz     loc_180012FE7
0x180012d80  cmp     rsi, [rcx+20h]
0x180012d84  jb      loc_180012FE7
0x180012d8a  mov     rax, [rcx+30h]
0x180012d8e  test    rax, rax
0x180012d91  jz      short loc_180012D97
0x180012d93  lock inc dword ptr [rax+8]
0x180012d97  mov     r14, [rcx+28h]
0x180012d9b  mov     r12, [rcx+30h]
0x180012d9f  mov     qword ptr [rsp+108h+var_88], r14
0x180012da7  mov     qword ptr [rsp+108h+var_88+8], r12
0x180012daf  mov     rcx, [r14]
0x180012db2  mov     rax, [rcx+8]
0x180012db6  mov     dword ptr [rsp+108h+var_C8+4], edx
0x180012dba  jmp     short loc_180012DCD
0x180012dbc  cmp     [rax+20h], ebx
0x180012dbf  jnb     short loc_180012DC7
0x180012dc1  mov     rax, [rax+10h]
0x180012dc5  jmp     short loc_180012DCD
0x180012dc7  mov     rcx, rax
0x180012dca  mov     rax, [rax]
0x180012dcd  cmp     [rax+19h], dl
0x180012dd0  jz      short loc_180012DBC
0x180012dd2  cmp     [rcx+19h], dl
0x180012dd5  jnz     short loc_180012E4B
0x180012dd7  cmp     ebx, [rcx+20h]
0x180012dda  jb      short loc_180012E4B
0x180012ddc  lea     rdx, [rsp+108h+arg_10]
0x180012de4  mov     rcx, r14
0x180012de7  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::erase(ulong const &)
0x180012dec  mov     dword ptr [rsp+108h+var_D0], ebx
0x180012df0  lea     rdx, [rsp+108h+var_A8]
0x180012df5  lea     rcx, [rsp+108h+var_C8]
0x180012dfa  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x180012dff  nop
0x180012e00  lea     r8, [rsp+108h+var_D0]
0x180012e05  lea     rdx, [rsp+108h+var_98]
0x180012e0a  mov     rcx, r14
0x180012e0d  call    ??$insert@U?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@$0A@@?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@1@@Z; std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>::insert<std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>>,0>(std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>> &&)
0x180012e12  mov     r14b, [rax+8]
0x180012e16  mov     rcx, [rsp+108h+var_C0]; this
0x180012e1b  test    rcx, rcx
0x180012e1e  jz      short loc_180012E25
0x180012e20  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012e25  test    r14b, r14b
0x180012e28  jnz     short loc_180012E84
0x180012e2a  lea     rcx, [rsp+108h+var_50]; this
0x180012e32  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x180012e37  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180012e3e  lea     rcx, [rsp+108h+var_50]; pExceptionObject
0x180012e46  call    _CxxThrowException_0
0x180012e4b  mov     dword ptr [rsp+108h+var_D0], ebx
0x180012e4f  test    rdi, rdi
0x180012e52  jz      short loc_180012E58
0x180012e54  lock inc dword ptr [rdi+8]
0x180012e58  mov     [rsp+108h+var_C8], r15
0x180012e5d  mov     [rsp+108h+var_C0], rdi
0x180012e62  lea     r8, [rsp+108h+var_D0]
0x180012e67  lea     rdx, [rsp+108h+var_98]
0x180012e6c  mov     rcx, r14
0x180012e6f  call    ??$_Emplace@U?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Emplace<std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>>>(std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>> &&)
0x180012e74  nop
0x180012e75  mov     rcx, [rsp+108h+var_C0]; this
0x180012e7a  test    rcx, rcx
0x180012e7d  jz      short loc_180012E84
0x180012e7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012e84  lea     r14, GUID_SESSION_DISPLAY_STATUS
0x180012e8b  lea     rax, GUID_MONITOR_POWER_ON
0x180012e92  test    ebx, ebx
0x180012e94  cmovz   r14, rax
0x180012e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e9f  test    byte ptr [rcx+1Ch], 1
0x180012ea3  jz      short loc_180012EC0
0x180012ea5  cmp     byte ptr [rcx+19h], 4
0x180012ea9  jb      short loc_180012EC0
0x180012eab  mov     edx, 33h ; '3'
0x180012eb0  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180012eb7  mov     rcx, [rcx+10h]
0x180012ebb  call    WPP_SF_
0x180012ec0  lea     rax, ?SystemEventsBrokerDisplayNotificationCallback@Broker@@YAKPEAXK0@Z; Broker::SystemEventsBrokerDisplayNotificationCallback(void *,ulong,void *)
0x180012ec7  mov     qword ptr [rsp+108h+var_B8], rax
0x180012ecc  mov     qword ptr [rsp+108h+var_B8+8], r15
0x180012ed1  add     r15, 18h
0x180012ed5  mov     qword ptr [rsp+108h+var_E8], r15
0x180012eda  lea     r9, [rsp+108h+var_B8]
0x180012edf  mov     r8d, 2
0x180012ee5  mov     edx, ebx
0x180012ee7  mov     rcx, r14
0x180012eea  call    cs:__imp_PowerSettingRegisterNotificationEx
0x180012ef0  test    eax, eax
0x180012ef2  jz      short loc_180012F23
0x180012ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012efb  test    byte ptr [rcx+1Ch], 1
0x180012eff  jz      short loc_180012F1C
0x180012f01  cmp     byte ptr [rcx+19h], 2
0x180012f05  jb      short loc_180012F1C
0x180012f07  mov     edx, 34h ; '4'
0x180012f0c  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180012f13  mov     rcx, [rcx+10h]
0x180012f17  call    WPP_SF_
0x180012f1c  mov     qword ptr [r15], 0
0x180012f23  lea     r14, GUID_SESSION_USER_PRESENCE
0x180012f2a  lea     rax, GUID_GLOBAL_USER_PRESENCE
0x180012f31  test    ebx, ebx
0x180012f33  cmovz   r14, rax
0x180012f37  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f3e  test    byte ptr [rcx+1Ch], 1
0x180012f42  jz      short loc_180012F5F
0x180012f44  cmp     byte ptr [rcx+19h], 4
0x180012f48  jb      short loc_180012F5F
0x180012f4a  mov     edx, 35h ; '5'
0x180012f4f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180012f56  mov     rcx, [rcx+10h]
0x180012f5a  call    WPP_SF_
0x180012f5f  lea     rax, ?SystemEventsBrokerUserPresenceNotificationCallback@Broker@@YAKPEAXK0@Z; Broker::SystemEventsBrokerUserPresenceNotificationCallback(void *,ulong,void *)
0x180012f66  mov     qword ptr [rsp+108h+var_B8], rax
0x180012f6b  lea     rax, [rdi+10h]
0x180012f6f  mov     qword ptr [rsp+108h+var_B8+8], rax
0x180012f74  add     rax, 20h ; ' '
0x180012f78  mov     qword ptr [rsp+108h+var_E8], rax
0x180012f7d  lea     r9, [rsp+108h+var_B8]
0x180012f82  mov     r8d, 2
0x180012f88  mov     edx, ebx
0x180012f8a  mov     rcx, r14
0x180012f8d  call    cs:__imp_PowerSettingRegisterNotificationEx
0x180012f93  test    eax, eax
0x180012f95  jz      short loc_180012FC6
0x180012f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f9e  test    byte ptr [rcx+1Ch], 1
0x180012fa2  jz      short loc_180012FBF
0x180012fa4  cmp     byte ptr [rcx+19h], 2
0x180012fa8  jb      short loc_180012FBF
0x180012faa  mov     edx, 36h ; '6'
0x180012faf  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180012fb6  mov     rcx, [rcx+10h]
0x180012fba  call    WPP_SF_
0x180012fbf  mov     qword ptr [r15], 0
0x180012fc6  test    rdi, rdi
0x180012fc9  jz      short loc_180012FD4
0x180012fcb  mov     rcx, rdi; this
0x180012fce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012fd3  nop
0x180012fd4  test    r12, r12
0x180012fd7  jz      short loc_180012FE2
0x180012fd9  mov     rcx, r12; this
0x180012fdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012fe1  nop
0x180012fe2  mov     dil, 1
0x180012fe5  jmp     short loc_180013013
0x180012fe7  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180012fee  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180012ff4  nop
0x180012ff5  jmp     short $+2
0x180012ff7  mov     dil, [rsp+108h+var_D8]
0x180012ffc  mov     rsi, [rsp+108h+arg_8]
0x180013004  mov     ebx, [rsp+108h+arg_10]
0x18001300b  mov     r13, [rsp+108h+arg_18]
0x180013013  mov     rcx, cs:WPP_GLOBAL_Control
0x18001301a  test    byte ptr [rcx+1Ch], 1
0x18001301e  jz      short loc_180013040
0x180013020  cmp     byte ptr [rcx+19h], 4
0x180013024  jb      short loc_180013040
0x180013026  mov     r9d, esi
0x180013029  mov     edx, 39h ; '9'
0x18001302e  mov     [rsp+108h+pSid], r13; pSid
0x180013033  mov     dword ptr [rsp+108h+var_E8], ebx; char
0x180013037  mov     rcx, [rcx+10h]; LoggerHandle
0x18001303b  call    WPP_SF_dd_sid_
0x180013040  mov     al, dil
0x180013043  add     rsp, 0D0h
0x18001304a  pop     r15
0x18001304c  pop     r14
0x18001304e  pop     r13
  ... truncated ...
```
