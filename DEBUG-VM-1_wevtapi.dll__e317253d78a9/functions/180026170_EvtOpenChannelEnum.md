# EvtOpenChannelEnum

- ea: `0x180026170`
- end: `0x18002635a`
- name: `EvtOpenChannelEnum`
- size: `490`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, DWORD Flags)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x180007aa0`
- `0x18001a71c`
- `0x180023548`
- `0x180023ac8`
- `0x1800258ac`
- `0x180026170`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026323`
- `RPCRT4!NdrClientCall3` at `0x180026272`
- `RPCRT4!NdrClientCall3` at `0x180026272`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EVT_HANDLE __stdcall EvtOpenChannelEnum(EVT_HANDLE Session, DWORD Flags)
{
  DWORD Pointer; // ebx
  __int64 v4; // rcx
  void *v5; // rbx
  __int64 v7; // [rsp+40h] [rbp-68h] BYREF
  __int64 v8; // [rsp+48h] [rbp-60h] BYREF
  int v9; // [rsp+54h] [rbp-54h]
  __int64 v10; // [rsp+58h] [rbp-50h] BYREF
  DWORD v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+64h] [rbp-44h]
  char v13; // [rsp+68h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+70h] [rbp-38h] BYREF
  __int64 v15; // [rsp+80h] [rbp-28h]
  int v16; // [rsp+88h] [rbp-20h]
  int v17; // [rsp+8Ch] [rbp-1Ch]
  int v18; // [rsp+90h] [rbp-18h]
  EvtException *v19; // [rsp+98h] [rbp-10h] BYREF
  DWORD v20; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+20h] BYREF

  v22 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 87;
      v17 = -1;
      v18 = 1345;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v8);
    v21 = 0;
    v20 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x13u,
                              0,
                              *(_QWORD *)(v8 + 72),
                              0,
                              &v20,
                              &v21).Pointer;
    v10 = v21;
    v11 = v20;
    v12 = v9;
    v13 = 1;
    if ( !Pointer )
    {
      v7 = 0;
      v4 = HandleTable::Emplace<ChannelEnumObject,wchar_t * * &,unsigned long &>(v20, &v7, &v21, &v20);
      if ( v4 )
      {
        *(_QWORD *)(v4 + 16) = v7;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 24));
        v22 = v4;
        v7 = 0;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v7);
        Pointer = 0;
      }
      else
      {
        Pointer = 14;
      }
    }
    tlx::_UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___::__UndoSolo__ChannelConfigObject::GetProperty_::_8_::_lambda_1___(&v10);
    wmi::AutoRef<Object>::Release(&v8);
  }
  catch ( EvtException *v19 )
  {
    v20 = *((_DWORD *)v19 + 6);
    Pointer = v20;
  }
  SetLastError(Pointer);
  v5 = EvtHandleRef::Detach((EvtHandleRef *)&v22);
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v22);
  return v5;
}

```

## disassembly

```asm
0x180026170  mov     rax, rsp
0x180026173  mov     [rax+8], rbx
0x180026177  push    rdi
0x180026178  sub     rsp, 0A0h
0x18002617f  mov     ebx, edx
0x180026181  mov     rdi, rcx
0x180026184  mov     qword ptr [rax+20h], 0
0x18002618c  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180026191  test    ebx, ebx
0x180026193  jz      short loc_180026214
0x180026195  lea     rax, WPP_GLOBAL_Control
0x18002619c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261a3  cmp     rcx, rax
0x1800261a6  jz      short loc_1800261CD
0x1800261a8  test    byte ptr [rcx+1Ch], 1
0x1800261ac  jz      short loc_1800261CD
0x1800261ae  cmp     byte ptr [rcx+19h], 2
0x1800261b2  jb      short loc_1800261CD
0x1800261b4  mov     edx, 2Bh ; '+'
0x1800261b9  lea     r9d, [rdx+2Ch]
0x1800261bd  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800261c4  mov     rcx, [rcx+10h]
0x1800261c8  call    WPP_SF_D
0x1800261cd  xorps   xmm0, xmm0
0x1800261d0  movdqu  [rsp+0A8h+pExceptionObject], xmm0
0x1800261d6  mov     [rsp+0A8h+var_28], 0
0x1800261e2  mov     [rsp+0A8h+var_20], 57h ; 'W'
0x1800261ed  mov     [rsp+0A8h+var_1C], 0FFFFFFFFh
0x1800261f8  mov     [rsp+0A8h+var_18], 541h
0x180026203  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002620a  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002620f  call    _CxxThrowException_0
0x180026214  mov     rdx, rdi
0x180026217  lea     rcx, [rsp+0A8h+var_60]; void *
0x18002621c  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180026221  nop
0x180026222  mov     [rsp+0A8h+arg_10], 0
0x18002622e  mov     [rsp+0A8h+arg_8], 0
0x180026239  lea     rax, [rsp+0A8h+arg_10]
0x180026241  mov     [rsp+0A8h+var_78], rax
0x180026246  lea     rax, [rsp+0A8h+arg_8]
0x18002624e  mov     [rsp+0A8h+var_80], rax
0x180026253  mov     [rsp+0A8h+var_88], 0
0x18002625b  mov     r9, [rsp+0A8h+var_60]
0x180026260  mov     r9, [r9+48h]
0x180026264  xor     r8d, r8d; pReturnValue
0x180026267  lea     edx, [r8+13h]; nProcNum
0x18002626b  lea     rcx, pProxyInfo; pProxyInfo
0x180026272  call    cs:__imp_NdrClientCall3
0x180026278  mov     rbx, rax
0x18002627b  mov     rax, [rsp+0A8h+arg_10]
0x180026283  mov     ecx, [rsp+0A8h+arg_8]
0x18002628a  mov     [rsp+0A8h+var_50], rax
0x18002628f  mov     [rsp+0A8h+var_48], ecx
0x180026293  mov     eax, [rsp+0A8h+var_54]
0x180026297  mov     [rsp+0A8h+var_44], eax
0x18002629b  mov     [rsp+0A8h+var_40], 1
0x1800262a0  test    ebx, ebx
0x1800262a2  jnz     short loc_180026302
0x1800262a4  mov     [rsp+0A8h+var_68], 0
0x1800262ad  lea     r9, [rsp+0A8h+arg_8]
0x1800262b5  lea     r8, [rsp+0A8h+arg_10]
0x1800262bd  lea     rdx, [rsp+0A8h+var_68]
0x1800262c2  call    ??$Emplace@VChannelEnumObject@@AEAPEAPEA_WAEAK@HandleTable@@QEAAPEAVChannelEnumObject@@AEAPEAXAEAPEAPEA_WAEAK@Z; HandleTable::Emplace<ChannelEnumObject,wchar_t * * &,ulong &>(void * &,wchar_t * * &,ulong &)
0x1800262c7  mov     rcx, rax
0x1800262ca  test    rax, rax
0x1800262cd  jnz     short loc_1800262D4
0x1800262cf  lea     ebx, [rax+0Eh]
0x1800262d2  jmp     short loc_180026302
0x1800262d4  mov     rax, [rsp+0A8h+var_68]
0x1800262d9  mov     [rcx+10h], rax
0x1800262dd  lock inc dword ptr [rcx+8]
0x1800262e1  lock inc dword ptr [rcx+18h]
0x1800262e5  mov     [rsp+0A8h+arg_18], rcx
0x1800262ed  mov     [rsp+0A8h+var_68], 0
0x1800262f6  lea     rcx, [rsp+0A8h+var_68]; this
0x1800262fb  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180026300  xor     ebx, ebx
0x180026302  lea     rcx, [rsp+0A8h+var_50]
0x180026307  call    tlx___UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1_______UndoSolo__ChannelConfigObject__GetProperty____8____lambda_1___
0x18002630c  nop
0x18002630d  lea     rcx, [rsp+0A8h+var_60]; void *
0x180026312  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180026317  nop
0x180026318  jmp     short loc_180026321
0x18002631a  mov     ebx, [rsp+0A8h+arg_8]
0x180026321  mov     ecx, ebx; dwErrCode
0x180026323  call    cs:__imp_SetLastError
0x180026329  lea     rcx, [rsp+0A8h+arg_18]; this
0x180026331  call    ?Detach@EvtHandleRef@@QEAAPEAXXZ; EvtHandleRef::Detach(void)
0x180026336  mov     rbx, rax
0x180026339  lea     rcx, [rsp+0A8h+arg_18]; this
0x180026341  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180026346  mov     rax, rbx
0x180026349  mov     rbx, [rsp+0A8h+arg_0]
0x180026351  add     rsp, 0A0h
0x180026358  pop     rdi
0x180026359  retn
```
