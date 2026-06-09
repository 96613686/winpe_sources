# EvtOpenChannelConfig

- ea: `0x18001a750`
- end: `0x18001a986`
- name: `EvtOpenChannelConfig`
- size: `566`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, LPCWSTR ChannelPath, DWORD Flags)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18001a750`
- `0x18001a98c`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a7ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a7ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
EVT_HANDLE __stdcall EvtOpenChannelConfig(EVT_HANDLE Session, LPCWSTR ChannelPath, DWORD Flags)
{
  __int64 v5; // rsi
  int v6; // ecx
  __int64 v7; // rcx
  DWORD v8; // r14d
  void *v9; // r14
  __int64 v11; // [rsp+30h] [rbp-88h] BYREF
  wmi::RefBase *v12; // [rsp+38h] [rbp-80h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-78h] BYREF
  __int64 v14; // [rsp+50h] [rbp-68h]
  int v15; // [rsp+58h] [rbp-60h]
  int v16; // [rsp+5Ch] [rbp-5Ch]
  int v17; // [rsp+60h] [rbp-58h]
  __int128 v18; // [rsp+68h] [rbp-50h] BYREF
  __int64 v19; // [rsp+78h] [rbp-40h]
  int v20; // [rsp+80h] [rbp-38h]
  int v21; // [rsp+84h] [rbp-34h]
  int v22; // [rsp+88h] [rbp-30h]
  LPCWSTR v23; // [rsp+C8h] [rbp+10h] BYREF
  DWORD v24; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+20h] BYREF

  v24 = Flags;
  v23 = ChannelPath;
  v5 = 0;
  v25 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  if ( Flags )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v14 = 0;
    v15 = 87;
    v16 = -1;
    v17 = 1440;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !ChannelPath )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    v18 = 0;
    v19 = 0;
    v20 = 87;
    v21 = -1;
    v22 = 1445;
    throw (EvtException *)&v18;
  }
  GetSession(&v12);
  v11 = 0;
  v7 = HandleTable::Emplace<ChannelConfigObject,wmi::AutoRef<Session> &,wchar_t const * &,unsigned long &>(
         v6,
         (unsigned int)&v11,
         (unsigned int)&v12,
         (unsigned int)&v23,
         (__int64)&v24);
  if ( v7 )
  {
    *(_QWORD *)(v7 + 16) = v11;
    _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
    _InterlockedAdd((volatile signed __int32 *)(v7 + 24), 1u);
    v5 = v7;
    v25 = v7;
    v11 = 0;
    EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v11);
    v8 = 0;
  }
  else
  {
    v8 = 14;
  }
  if ( v12 )
    wmi::RefBase::Release(v12);
  SetLastError(v8);
  if ( v5 )
  {
    v9 = *(void **)(v5 + 16);
    v25 = 0;
    *(_BYTE *)(v5 + 29) = 1;
  }
  else
  {
    v9 = 0;
  }
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v25);
  return v9;
}

```

## disassembly

```asm
0x18001a750  mov     rax, rsp
0x18001a753  mov     [rax+8], rsi
0x18001a757  mov     [rax+18h], r8d
0x18001a75b  mov     [rax+10h], rdx
0x18001a75f  push    rdi
0x18001a760  push    r14
0x18001a762  push    r15
0x18001a764  sub     rsp, 0A0h
0x18001a76b  mov     r14d, r8d
0x18001a76e  mov     rdi, rdx
0x18001a771  mov     r15, rcx
0x18001a774  xor     esi, esi
0x18001a776  mov     [rax+20h], rsi
0x18001a77a  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001a77f  test    r14d, r14d
0x18001a782  jnz     loc_18001A836
0x18001a788  test    rdi, rdi
0x18001a78b  jz      loc_18001A8AC
0x18001a791  mov     rdx, r15
0x18001a794  lea     rcx, [rsp+0B8h+var_80]; void *
0x18001a799  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001a79e  nop
0x18001a79f  mov     [rsp+0B8h+var_88], rsi
0x18001a7a4  lea     rax, [rsp+0B8h+arg_10]
0x18001a7ac  mov     [rsp+0B8h+var_98], rax
0x18001a7b1  lea     r9, [rsp+0B8h+arg_8]
0x18001a7b9  lea     r8, [rsp+0B8h+var_80]
0x18001a7be  lea     rdx, [rsp+0B8h+var_88]
0x18001a7c3  call    ??$Emplace@VChannelConfigObject@@AEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAK@HandleTable@@QEAAPEAVChannelConfigObject@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAK@Z; HandleTable::Emplace<ChannelConfigObject,wmi::AutoRef<Session> &,wchar_t const * &,ulong &>(void * &,wmi::AutoRef<Session> &,wchar_t const * &,ulong &)
0x18001a7c8  mov     rcx, rax
0x18001a7cb  lea     edi, [rsi+1]
0x18001a7ce  test    rax, rax
0x18001a7d1  jnz     loc_18001A92C
0x18001a7d7  lea     r14d, [rsi+0Eh]
0x18001a7db  mov     rcx, [rsp+0B8h+var_80]; this
0x18001a7e0  test    rcx, rcx
0x18001a7e3  jz      short loc_18001A7EB
0x18001a7e5  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001a7ea  nop
0x18001a7eb  mov     ecx, r14d; dwErrCode
0x18001a7ee  call    cs:__imp_SetLastError
0x18001a7f4  test    rsi, rsi
0x18001a7f7  jz      loc_18001A97D
0x18001a7fd  mov     r14, [rsi+10h]
0x18001a801  mov     [rsp+0B8h+arg_18], 0
0x18001a80d  xchg    dil, [rsi+1Dh]
0x18001a811  lea     rcx, [rsp+0B8h+arg_18]; this
0x18001a819  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001a81e  mov     rax, r14
0x18001a821  mov     rsi, [rsp+0B8h+arg_0]
0x18001a829  add     rsp, 0A0h
0x18001a830  pop     r15
0x18001a832  pop     r14
0x18001a834  pop     rdi
0x18001a835  retn
0x18001a836  lea     rax, WPP_GLOBAL_Control
0x18001a83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a844  cmp     rcx, rax
0x18001a847  jz      short loc_18001A871
0x18001a849  mov     edi, 1
0x18001a84e  test    [rcx+1Ch], dil
0x18001a852  jz      short loc_18001A871
0x18001a854  cmp     byte ptr [rcx+19h], 2
0x18001a858  jb      short loc_18001A871
0x18001a85a  lea     edx, [rdi+2Bh]
0x18001a85d  lea     r9d, [rdi+56h]
0x18001a861  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001a868  mov     rcx, [rcx+10h]
0x18001a86c  call    WPP_SF_D
0x18001a871  xorps   xmm0, xmm0
0x18001a874  movdqu  [rsp+0B8h+pExceptionObject], xmm0
0x18001a87a  mov     [rsp+0B8h+var_68], 0
0x18001a883  mov     [rsp+0B8h+var_60], 57h ; 'W'
0x18001a88b  mov     [rsp+0B8h+var_5C], 0FFFFFFFFh
0x18001a893  mov     [rsp+0B8h+var_58], 5A0h
0x18001a89b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001a8a2  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18001a8a7  call    _CxxThrowException_0
0x18001a8ac  lea     rax, WPP_GLOBAL_Control
0x18001a8b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8ba  cmp     rcx, rax
0x18001a8bd  jz      short loc_18001A8E7
0x18001a8bf  mov     edi, 1
0x18001a8c4  test    [rcx+1Ch], dil
0x18001a8c8  jz      short loc_18001A8E7
0x18001a8ca  cmp     byte ptr [rcx+19h], 2
0x18001a8ce  jb      short loc_18001A8E7
0x18001a8d0  lea     edx, [rdi+2Ch]
0x18001a8d3  lea     r9d, [rdi+56h]
0x18001a8d7  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001a8de  mov     rcx, [rcx+10h]
0x18001a8e2  call    WPP_SF_D
0x18001a8e7  xorps   xmm0, xmm0
0x18001a8ea  movdqu  [rsp+0B8h+var_50], xmm0
0x18001a8f0  mov     [rsp+0B8h+var_40], 0
0x18001a8f9  mov     [rsp+0B8h+var_38], 57h ; 'W'
0x18001a904  mov     [rsp+0B8h+var_34], 0FFFFFFFFh
0x18001a90f  mov     [rsp+0B8h+var_30], 5A5h
0x18001a91a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001a921  lea     rcx, [rsp+0B8h+var_50]; pExceptionObject
0x18001a926  call    _CxxThrowException_0
0x18001a92c  mov     rax, [rsp+0B8h+var_88]
0x18001a931  mov     [rcx+10h], rax
0x18001a935  lock add [rcx+8], edi
0x18001a939  lock add [rcx+18h], edi
0x18001a93d  mov     rsi, rcx
0x18001a940  mov     [rsp+0B8h+arg_18], rcx
0x18001a948  mov     [rsp+0B8h+var_88], 0
0x18001a951  lea     rcx, [rsp+0B8h+var_88]; this
0x18001a956  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001a95b  xor     r14d, r14d
0x18001a95e  jmp     loc_18001A7DB
0x18001a963  mov     edi, 1
0x18001a968  mov     r14d, [rsp+0B8h+arg_10]
0x18001a970  mov     rsi, [rsp+0B8h+arg_18]
0x18001a978  jmp     loc_18001A7EB
0x18001a97d  xor     r14d, r14d
0x18001a980  jmp     loc_18001A811
```
