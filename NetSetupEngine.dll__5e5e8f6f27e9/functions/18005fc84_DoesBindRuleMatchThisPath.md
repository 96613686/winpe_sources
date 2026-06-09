# DoesBindRuleMatchThisPath

- ea: `0x18005fc84`
- end: `0x18005fefa`
- name: `DoesBindRuleMatchThisPath`
- size: `630`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x18001a7d8`
- `0x180071898`

## callees

- `0x180009570`
- `0x18000a430`
- `0x18000c620`
- `0x18001ac44`
- `0x18003c06c`
- `0x18005097c`
- `0x18005b034`
- `0x18005fc84`
- `0x18005ff00`
- `0x180064704`
- `0x180065035`
- `0x180071310`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18005fd67`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18005fd67`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall DoesBindRuleMatchThisPath(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  handle_t v9; // rbx
  unsigned int v10; // edi
  int v11; // ebx
  int v12; // ebx
  int v13; // eax
  char v14; // bl
  __int64 v15; // rcx
  _BYTE v16[8]; // [rsp+30h] [rbp-D0h] BYREF
  handle_t *p_pHandle; // [rsp+38h] [rbp-C8h]
  __int128 *v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  _BYTE pExceptionObject[208]; // [rsp+50h] [rbp-B0h] BYREF
  handle_t pHandle; // [rsp+120h] [rbp+20h] BYREF
  __int128 v22; // [rsp+128h] [rbp+28h] BYREF
  void *Block[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v24; // [rsp+148h] [rbp+48h]
  handle_t v25; // [rsp+150h] [rbp+50h] BYREF
  __int128 v26; // [rsp+158h] [rbp+58h] BYREF
  __int64 v27; // [rsp+168h] [rbp+68h]

  v19 = -2;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)Block = 0;
  v24 = 0;
  std::vector<_NETSETUPPROPKEY>::push_back(&v26, NETSETUPPKEY_BindRule_RulePredicate);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2);
  (*(void (__fastcall **)(__int64, __int64, __int128 *, void **))(*(_QWORD *)v6 + 8LL))(v6, a1, &v26, Block);
  if ( *((_DWORD *)Block[0] + 5) )
  {
    pHandle = 0;
    v9 = 0;
    v25 = 0;
    v10 = MesDecodeBufferHandleCreate(
            *((char **)Block[0] + 3),
            *((_DWORD *)Block[0] + 8) - *((_QWORD *)Block[0] + 3),
            &pHandle);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f5b31fed6253328cade6c55e84009aaa_Traceguids, v10);
      HResultException::HResultException((HResultException *)pExceptionObject, v10 | 0x80010000);
      throw (HResultException *)pExceptionObject;
    }
    if ( pHandle )
      v9 = pHandle;
    v25 = v9;
    v22 = 0;
    v11 = DecodeBindRuleFilter(pHandle, &v22);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_f5b31fed6253328cade6c55e84009aaa_Traceguids,
          (unsigned int)v11);
      HResultException::HResultException((HResultException *)pExceptionObject, v11);
      throw (HResultException *)pExceptionObject;
    }
    v16[0] = 0;
    p_pHandle = &pHandle;
    v18 = &v22;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 40LL))(a3);
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 32LL))(a3);
    v14 = NetSetupApplyFilter(a1, v13, v12, 0, v22, *((__int64 *)&v22 + 1));
    ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_bfe961ded6037c4a55c9afc5a6b30130_____(v16);
    NdrSerializationHandle::~NdrSerializationHandle((NdrSerializationHandle *)&v25);
    if ( Block[0] )
    {
      std::vector<NetSetup2::Property>::_Destroy(v15, Block[0], Block[1]);
      operator delete(Block[0]);
      *(_OWORD *)Block = 0;
      v24 = 0;
    }
    std::vector<_NETSETUPPROPKEY>::_Tidy(&v26);
    return v14;
  }
  else
  {
    std::vector<NetSetup2::Property>::_Destroy(v7, Block[0], Block[1]);
    operator delete(Block[0]);
    *(_OWORD *)Block = 0;
    v24 = 0;
    std::vector<_NETSETUPPROPKEY>::_Tidy(&v26);
    return 0;
  }
}

```

## disassembly

```asm
0x18005fc84  push    rbp
0x18005fc86  push    rbx
0x18005fc87  push    rsi
0x18005fc88  push    rdi
0x18005fc89  push    r14
0x18005fc8b  lea     rbp, [rsp-80h]
0x18005fc90  sub     rsp, 180h
0x18005fc97  mov     [rsp+1A0h+var_158], 0FFFFFFFFFFFFFFFEh
0x18005fca0  mov     rax, cs:__security_cookie
0x18005fca7  xor     rax, rsp
0x18005fcaa  mov     [rbp+0A0h+var_30], rax
0x18005fcae  mov     rsi, r8
0x18005fcb1  mov     rbx, rdx
0x18005fcb4  mov     r14, rcx
0x18005fcb7  xorps   xmm0, xmm0
0x18005fcba  movdqu  [rbp+0A0h+var_48], xmm0
0x18005fcbf  mov     [rbp+0A0h+var_38], 0
0x18005fcc7  movdqu  xmmword ptr [rbp+0A0h+Block], xmm0
0x18005fccc  mov     [rbp+0A0h+var_58], 0
0x18005fcd4  lea     rdx, NETSETUPPKEY_BindRule_RulePredicate
0x18005fcdb  lea     rcx, [rbp+0A0h+var_48]
0x18005fcdf  call    ?push_back@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@QEAAXAEBU_NETSETUPPROPKEY@@@Z; std::vector<_NETSETUPPROPKEY>::push_back(_NETSETUPPROPKEY const &)
0x18005fce4  mov     rax, [rbx]
0x18005fce7  mov     rcx, rbx
0x18005fcea  mov     rax, [rax+20h]
0x18005fcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcf3  mov     r10, rax
0x18005fcf6  mov     rcx, [rax]
0x18005fcf9  mov     rax, [rcx+8]
0x18005fcfd  lea     r9, [rbp+0A0h+Block]
0x18005fd01  lea     r8, [rbp+0A0h+var_48]
0x18005fd05  mov     rdx, r14
0x18005fd08  mov     rcx, r10
0x18005fd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd10  mov     rdx, [rbp+0A0h+Block]
0x18005fd14  cmp     dword ptr [rdx+14h], 0
0x18005fd18  jnz     short loc_18005FD4C
0x18005fd1a  mov     r8, [rbp+0A0h+Block+8]
0x18005fd1e  call    ?_Destroy@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAXPEAVProperty@NetSetup2@@0@Z; std::vector<NetSetup2::Property>::_Destroy(NetSetup2::Property *,NetSetup2::Property *)
0x18005fd23  mov     rcx, [rbp+0A0h+Block]; Block
0x18005fd27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005fd2c  xorps   xmm0, xmm0
0x18005fd2f  movdqu  xmmword ptr [rbp+0A0h+Block], xmm0
0x18005fd34  mov     [rbp+0A0h+var_58], 0
0x18005fd3c  lea     rcx, [rbp+0A0h+var_48]
0x18005fd40  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18005fd45  xor     al, al
0x18005fd47  jmp     loc_18005FEE0
0x18005fd4c  mov     [rbp+0A0h+pHandle], 0
0x18005fd54  xor     ebx, ebx
0x18005fd56  mov     [rbp+0A0h+var_50], rbx
0x18005fd5a  mov     rcx, [rdx+18h]; Buffer
0x18005fd5e  mov     edx, [rdx+20h]
0x18005fd61  sub     edx, ecx; BufferSize
0x18005fd63  lea     r8, [rbp+0A0h+pHandle]; pHandle
0x18005fd67  call    cs:__imp_MesDecodeBufferHandleCreate
0x18005fd6d  mov     edi, eax
0x18005fd6f  test    eax, eax
0x18005fd71  jz      short loc_18005FDC6
0x18005fd73  lea     rax, WPP_GLOBAL_Control
0x18005fd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fd81  cmp     rcx, rax
0x18005fd84  jz      short loc_18005FDA2
0x18005fd86  cmp     byte ptr [rcx+19h], 2
0x18005fd8a  jb      short loc_18005FDA2
0x18005fd8c  lea     edx, [rbx+0Fh]
0x18005fd8f  mov     r9d, edi
0x18005fd92  lea     r8, WPP_f5b31fed6253328cade6c55e84009aaa_Traceguids
0x18005fd99  mov     rcx, [rcx+10h]
0x18005fd9d  call    WPP_SF_d
0x18005fda2  or      edi, 80010000h
0x18005fda8  mov     edx, edi; int
0x18005fdaa  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18005fdaf  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18005fdb4  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18005fdbb  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18005fdc0  call    _CxxThrowException_0
0x18005fdc6  mov     rcx, [rbp+0A0h+pHandle]
0x18005fdca  test    rcx, rcx
0x18005fdcd  cmovnz  rbx, rcx
0x18005fdd1  mov     [rbp+0A0h+var_50], rbx
0x18005fdd5  xorps   xmm0, xmm0
0x18005fdd8  movups  [rbp+0A0h+var_78], xmm0
0x18005fddc  lea     rdx, [rbp+0A0h+var_78]
0x18005fde0  call    DecodeBindRuleFilter
0x18005fde5  mov     ebx, eax
0x18005fde7  test    eax, eax
0x18005fde9  jns     short loc_18005FE3A
0x18005fdeb  lea     rax, WPP_GLOBAL_Control
0x18005fdf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fdf9  cmp     rcx, rax
0x18005fdfc  jz      short loc_18005FE1C
0x18005fdfe  cmp     byte ptr [rcx+19h], 2
0x18005fe02  jb      short loc_18005FE1C
0x18005fe04  mov     edx, 10h
0x18005fe09  mov     r9d, ebx
0x18005fe0c  lea     r8, WPP_f5b31fed6253328cade6c55e84009aaa_Traceguids
0x18005fe13  mov     rcx, [rcx+10h]
0x18005fe17  call    WPP_SF_d
0x18005fe1c  mov     edx, ebx; int
0x18005fe1e  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18005fe23  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18005fe28  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18005fe2f  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18005fe34  call    _CxxThrowException_0
0x18005fe3a  mov     [rsp+1A0h+var_170], 0
0x18005fe3f  lea     rax, [rbp+0A0h+pHandle]
0x18005fe43  mov     [rsp+1A0h+var_168], rax
0x18005fe48  lea     rax, [rbp+0A0h+var_78]
0x18005fe4c  mov     [rsp+1A0h+var_160], rax
0x18005fe51  mov     rax, [rsi]
0x18005fe54  mov     rcx, rsi
0x18005fe57  mov     rax, [rax+28h]
0x18005fe5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe60  mov     rbx, rax
0x18005fe63  mov     rdx, [rsi]
0x18005fe66  mov     rcx, rsi
0x18005fe69  mov     rax, [rdx+20h]
0x18005fe6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe72  mov     rdx, qword ptr [rbp+0A0h+var_78+8]
0x18005fe76  mov     [rsp+1A0h+var_178], rdx
0x18005fe7b  mov     edx, dword ptr [rbp+0A0h+var_78]
0x18005fe7e  mov     [rsp+1A0h+var_180], edx
0x18005fe82  xor     r9d, r9d
0x18005fe85  mov     r8, rbx
0x18005fe88  mov     rdx, rax
0x18005fe8b  mov     rcx, r14
0x18005fe8e  call    ?NetSetupApplyFilter@@YA_NAEBVNetSetupTransaction@@PEBVINetSetupPropertyProvider@@PEBVINetSetupObjectRelationsProvider@@PEBV?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetupApplyFilter(NetSetupTransaction const &,INetSetupPropertyProvider const *,INetSetupObjectRelationsProvider const *,std::vector<_NETSETUPPROPKEY> const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18005fe93  mov     bl, al
0x18005fe95  lea     rcx, [rsp+1A0h+var_170]
0x18005fe9a  call    ScopeGuardImplBase__SafeExecute_ScopeGuardImpl0__lambda_bfe961ded6037c4a55c9afc5a6b30130_____
0x18005fe9f  nop
0x18005fea0  lea     rcx, [rbp+0A0h+var_50]; this
0x18005fea4  call    ??1NdrSerializationHandle@@QEAA@XZ; NdrSerializationHandle::~NdrSerializationHandle(void)
0x18005fea9  nop
0x18005feaa  mov     rdx, [rbp+0A0h+Block]
0x18005feae  test    rdx, rdx
0x18005feb1  jz      short loc_18005FED5
0x18005feb3  mov     r8, [rbp+0A0h+Block+8]
0x18005feb7  call    ?_Destroy@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAXPEAVProperty@NetSetup2@@0@Z; std::vector<NetSetup2::Property>::_Destroy(NetSetup2::Property *,NetSetup2::Property *)
0x18005febc  mov     rcx, [rbp+0A0h+Block]; Block
0x18005fec0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005fec5  xorps   xmm0, xmm0
0x18005fec8  movdqu  xmmword ptr [rbp+0A0h+Block], xmm0
0x18005fecd  mov     [rbp+0A0h+var_58], 0
0x18005fed5  lea     rcx, [rbp+0A0h+var_48]
0x18005fed9  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18005fede  mov     al, bl
0x18005fee0  mov     rcx, [rbp+0A0h+var_30]
0x18005fee4  xor     rcx, rsp; StackCookie
0x18005fee7  call    __security_check_cookie
0x18005feec  add     rsp, 180h
0x18005fef3  pop     r14
0x18005fef5  pop     rdi
0x18005fef6  pop     rsi
0x18005fef7  pop     rbx
0x18005fef8  pop     rbp
0x18005fef9  retn
```
