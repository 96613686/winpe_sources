# Broker::SebBroker::OnUserLogonStart(_BROKER *,ulong,unsigned __int64,void * const)

- ea: `0x180016590`
- end: `0x1800167e7`
- name: `?OnUserLogonStart@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z`
- size: `599`
- prototype: `static unsigned int(struct _BROKER *, unsigned int, unsigned __int64, void *const)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180006c50`
- `0x1800076a0`
- `0x18000b168`
- `0x18000f370`
- `0x180012b8c`
- `0x180013820`
- `0x180013920`
- `0x180016150`
- `0x180016590`
- `0x18001ab34`
- `0x18001cf50`
- `0x18001d9ac`
- `0x18001f588`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Broker::SebBroker::OnUserLogonStart(
        struct _BROKER *a1,
        unsigned int a2,
        unsigned __int64 a3,
        char *a4)
{
  char *pSid; // rdi
  unsigned __int64 v5; // r15
  unsigned int v6; // esi
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int128 v10; // xmm0
  unsigned int v11; // ebx
  unsigned int SessionID; // eax
  unsigned int v13; // r12d
  __int64 v14; // rdx
  __int64 v15; // r8
  char v17; // [rsp+38h] [rbp-100h]
  int v18; // [rsp+40h] [rbp-F8h]
  _BYTE v20[16]; // [rsp+60h] [rbp-D8h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-C8h] BYREF
  __int128 v22; // [rsp+78h] [rbp-C0h]
  int v23; // [rsp+88h] [rbp-B0h]
  int v24; // [rsp+90h] [rbp-A8h]
  _QWORD v25[3]; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-80h] BYREF
  _BYTE v27[40]; // [rsp+D8h] [rbp-60h] BYREF

  pSid = a4;
  v5 = a3;
  v6 = a2;
  v17 = a2;
  v18 = a3;
  std::vector<_GUID>::vector<_GUID>(v25);
  std::wstring::wstring(v26);
  std::wstring::wstring(v27);
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Au, v8, v5, v6, pSid);
    v9 = WPP_GLOBAL_Control;
  }
  if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
  {
    if ( *(&Broker::SebBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v9 = WPP_GLOBAL_Control;
    }
    v10 = *(_OWORD *)&Broker::SebBroker::Instance;
  }
  else
  {
    v10 = 0;
  }
  if ( (_QWORD)v10 )
  {
    v11 = 0;
    if ( *(struct _BROKER **)(v10 + 136) == a1 )
    {
      Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v20, (struct _RTL_SRWLOCK *)(v10 + 8), 1);
      SessionID = Broker::SebBroker::GetSessionID((Broker::SebBroker *)v10, pSid);
      try
      {
        v13 = SessionID;
        if ( !Broker::SebBroker::UpdateSessionTable((Broker::SebBroker *)v10, v5, v6, pSid) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v6, pSid);
          v22 = 0;
          v23 = 6;
          pExceptionObject = &Broker::BILayer::Failure::`vftable';
          v24 = -1073741801;
          throw (Broker::BILayer::Failure *)&pExceptionObject;
        }
        if ( v13 != -1 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v13);
        Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v20);
      }
      catch ( ... )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
        v11 = 1359;
        LODWORD(v5) = v18;
        LOBYTE(v6) = v17;
        pSid = a4;
      }
      v9 = WPP_GLOBAL_Control;
    }
    else
    {
      v11 = 5;
    }
  }
  else
  {
    v11 = 21;
  }
  if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_dd_sid_(v9[2], 0x3Eu, v8, v5, v6, pSid);
  if ( *((_QWORD *)&v10 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v10 + 1));
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v25);
  return v11;
}

```

## disassembly

```asm
0x180016590  mov     [rsp+arg_0], rbx
0x180016595  push    rsi
0x180016596  push    rdi
0x180016597  push    r12
0x180016599  push    r14
0x18001659b  push    r15
0x18001659d  sub     rsp, 110h
0x1800165a4  mov     rax, cs:__security_cookie
0x1800165ab  xor     rax, rsp
0x1800165ae  mov     [rsp+138h+var_38], rax
0x1800165b6  mov     rdi, r9
0x1800165b9  mov     r15, r8
0x1800165bc  mov     esi, edx
0x1800165be  mov     r12, rcx
0x1800165c1  mov     dword ptr [rsp+138h+var_100], edx
0x1800165c5  mov     [rsp+138h+var_F8], r8
0x1800165ca  mov     [rsp+138h+var_F0], r9
0x1800165cf  lea     rcx, [rsp+138h+var_98]
0x1800165d7  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800165dc  lea     rcx, [rsp+138h+var_80]
0x1800165e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800165e9  lea     rcx, [rsp+138h+var_60]
0x1800165f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800165f6  nop
0x1800165f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165fe  test    byte ptr [rcx+1Ch], 1
0x180016602  jz      short loc_18001662B
0x180016604  cmp     byte ptr [rcx+19h], 4
0x180016608  jb      short loc_18001662B
0x18001660a  mov     r9d, r15d
0x18001660d  mov     edx, 3Ah ; ':'
0x180016612  mov     [rsp+138h+pSid], rdi; pSid
0x180016617  mov     dword ptr [rsp+138h+var_118], esi; char
0x18001661b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001661f  call    WPP_SF_dd_sid_
0x180016624  mov     rcx, cs:WPP_GLOBAL_Control
0x18001662b  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180016632  test    rax, rax
0x180016635  jz      short loc_18001665C
0x180016637  cmp     byte ptr [rax], 0
0x18001663a  jz      short loc_18001665C
0x18001663c  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180016643  test    rax, rax
0x180016646  jz      short loc_180016653
0x180016648  lock inc dword ptr [rax+8]
0x18001664c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016653  movups  xmm0, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18001665a  jmp     short loc_18001665F
0x18001665c  xorps   xmm0, xmm0
0x18001665f  movdqu  xmmword ptr [rsp+138h+var_E8], xmm0
0x180016665  movq    r14, xmm0
0x18001666a  test    r14, r14
0x18001666d  jnz     short loc_180016678
0x18001666f  lea     ebx, [r14+15h]
0x180016673  jmp     loc_180016779
0x180016678  xor     ebx, ebx
0x18001667a  cmp     [r14+88h], r12
0x180016681  jz      short loc_18001668D
0x180016683  mov     ebx, 5
0x180016688  jmp     loc_180016779
0x18001668d  lea     rdx, [r14+8]; struct _RTL_SRWLOCK *
0x180016691  mov     r8b, 1; bool
0x180016694  lea     rcx, [rsp+138h+var_D8]; this
0x180016699  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001669e  nop
0x18001669f  mov     rdx, rdi; void *
0x1800166a2  mov     rcx, r14; this
0x1800166a5  call    ?GetSessionID@SebBroker@Broker@@AEAAKQEAX@Z; Broker::SebBroker::GetSessionID(void * const)
0x1800166aa  mov     r12d, eax
0x1800166ad  mov     r9, rdi; void *
0x1800166b0  mov     r8d, esi; unsigned int
0x1800166b3  mov     rdx, r15; unsigned __int64
0x1800166b6  mov     rcx, r14; this
0x1800166b9  call    ?UpdateSessionTable@SebBroker@Broker@@AEAA_N_KKQEAX@Z; Broker::SebBroker::UpdateSessionTable(unsigned __int64,ulong,void * const)
0x1800166be  test    al, al
0x1800166c0  jnz     short loc_180016721
0x1800166c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166c9  test    byte ptr [rcx+1Ch], 1
0x1800166cd  jz      short loc_1800166E6
0x1800166cf  cmp     byte ptr [rcx+19h], 2
0x1800166d3  jb      short loc_1800166E6
0x1800166d5  mov     [rsp+138h+var_118], rdi; pSid
0x1800166da  mov     r9d, esi
0x1800166dd  mov     rcx, [rcx+10h]; LoggerHandle
0x1800166e1  call    WPP_SF_d_sid_
0x1800166e6  xorps   xmm0, xmm0
0x1800166e9  movups  [rsp+138h+var_C0], xmm0
0x1800166ee  mov     [rsp+138h+var_B0], 6
0x1800166f9  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180016700  mov     [rsp+138h+pExceptionObject], rax
0x180016705  mov     [rsp+138h+var_A8], 0C0000017h
0x180016710  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180016717  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18001671c  call    _CxxThrowException_0
0x180016721  cmp     r12d, 0FFFFFFFFh
0x180016725  jz      short loc_180016753
0x180016727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001672e  test    byte ptr [rcx+1Ch], 1
0x180016732  jz      short loc_180016753
0x180016734  cmp     byte ptr [rcx+19h], 4
0x180016738  jb      short loc_180016753
0x18001673a  mov     edx, 3Ch ; '<'
0x18001673f  mov     r9d, r12d
0x180016742  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180016749  mov     rcx, [rcx+10h]
0x18001674d  call    WPP_SF_d
0x180016752  nop
0x180016753  lea     rcx, [rsp+138h+var_D8]; this
0x180016758  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001675d  nop
0x18001675e  jmp     short loc_180016772
0x180016760  mov     ebx, [rsp+138h+var_108]
0x180016764  mov     r15, [rsp+138h+var_F8]
0x180016769  mov     esi, dword ptr [rsp+138h+var_100]
0x18001676d  mov     rdi, [rsp+138h+var_F0]
0x180016772  mov     rcx, cs:WPP_GLOBAL_Control
0x180016779  test    byte ptr [rcx+1Ch], 1
0x18001677d  jz      short loc_1800167A0
0x18001677f  cmp     byte ptr [rcx+19h], 4
0x180016783  jb      short loc_1800167A0
0x180016785  mov     r9d, r15d
0x180016788  mov     edx, 3Eh ; '>'
0x18001678d  mov     [rsp+138h+pSid], rdi; pSid
0x180016792  mov     dword ptr [rsp+138h+var_118], esi; char
0x180016796  mov     rcx, [rcx+10h]; LoggerHandle
0x18001679a  call    WPP_SF_dd_sid_
0x18001679f  nop
0x1800167a0  mov     rcx, [rsp+138h+var_E8+8]; this
0x1800167a5  test    rcx, rcx
0x1800167a8  jz      short loc_1800167B0
0x1800167aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800167af  nop
0x1800167b0  lea     rcx, [rsp+138h+var_98]; this
0x1800167b8  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x1800167bd  mov     eax, ebx
0x1800167bf  mov     rcx, [rsp+138h+var_38]
0x1800167c7  xor     rcx, rsp; StackCookie
0x1800167ca  call    __security_check_cookie
0x1800167cf  mov     rbx, [rsp+138h+arg_0]
0x1800167d7  add     rsp, 110h
0x1800167de  pop     r15
0x1800167e0  pop     r14
0x1800167e2  pop     r12
0x1800167e4  pop     rdi
0x1800167e5  pop     rsi
0x1800167e6  retn
```
