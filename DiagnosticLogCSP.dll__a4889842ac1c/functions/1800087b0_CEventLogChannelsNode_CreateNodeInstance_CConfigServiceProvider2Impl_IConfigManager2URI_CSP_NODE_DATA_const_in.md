# CEventLogChannelsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x1800087b0`
- end: `0x1800089fe`
- name: `?CreateNodeInstance@CEventLogChannelsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `590`
- prototype: `__int64 __fastcall(__int64, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008640`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x1800087b0`
- `0x18000f280`
- `0x18000f580`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CEventLogChannelsNode::CreateNodeInstance(
        __int64 a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v6; // rdi
  __int64 v9; // r13
  struct ICSPNode **v10; // r12
  unsigned int *v11; // r14
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  int v16; // eax
  int v18; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v19[2]; // [rsp+38h] [rbp-10h] BYREF
  int v20; // [rsp+90h] [rbp+48h] BYREF

  v6 = 0;
  v20 = 0;
  v9 = a1;
  if ( !a1 || !a2 || !a3 || (v10 = a5) == 0 || (v11 = a6) == 0 )
  {
    v12 = -2147024809;
    goto LABEL_30;
  }
  *a5 = 0;
  *v11 = 0;
  if ( (_DWORD)a4 )
  {
    if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
    {
      v12 = -2046820335;
      goto LABEL_30;
    }
    v13 = *(_QWORD *)a2;
    v19[0] = 0;
    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v13 + 88))(a2, 3, v19);
    if ( v12 < 0 )
      goto LABEL_30;
    if ( *((_DWORD *)a3 + 3) != 14 )
    {
LABEL_24:
      v12 = -2147418113;
      goto LABEL_30;
    }
    v12 = CEventLogChannel::RegisterChannel(v19[0]);
    if ( v12 < 0 )
      goto LABEL_30;
  }
  else if ( !*((_DWORD *)a3 + 6) )
  {
    v14 = *(_QWORD *)a2;
    v19[0] = 0;
    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v14 + 88))(a2, 3, v19);
    if ( v12 < 0 )
      goto LABEL_30;
    if ( (int)CEventLogChannel::IsChannelRegistered(v19[0]) < 0 )
      goto LABEL_16;
    if ( *((_DWORD *)a3 + 3) != 14 )
    {
      if ( *((_DWORD *)a3 + 3) == 15 )
      {
        *v11 = 2;
        goto LABEL_22;
      }
      a1 = (unsigned int)(*((_DWORD *)a3 + 3) - 16);
      if ( (unsigned int)a1 >= 2 )
      {
LABEL_16:
        v12 = -2046820350;
        goto LABEL_30;
      }
    }
  }
LABEL_22:
  v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v20);
  if ( v12 < 0 )
    goto LABEL_30;
  if ( *((_DWORD *)a3 + 2) + 1 != v20 )
    goto LABEL_24;
  v15 = (unsigned __int16 *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v19[0] = v15;
  v6 = (struct ICSPNode *)v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 2) = 0;
    *((_QWORD *)v15 + 3) = 0;
    *((_DWORD *)v15 + 16) = 1;
    *((_OWORD *)v15 + 2) = 0;
    *((_OWORD *)v15 + 3) = 0;
    *(_QWORD *)v15 = &CEventLogChannelsNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v15 + 1) = &CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_1800494E0);
    v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v15 + 136LL))(
            v15,
            v9,
            a2,
            a3);
    if ( v12 >= 0 )
    {
      *v10 = v6;
      v6 = 0;
    }
  }
  else
  {
    v6 = 0;
    v12 = -2147024882;
  }
LABEL_30:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v18 = v12;
    if ( a3 )
      v16 = *((_DWORD *)a3 + 3);
    else
      v16 = -1;
    LODWORD(v19[0]) = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)&dword_18003EBA4,
      (__int64)a3,
      a4,
      (__int64)v19,
      (__int64)&v18);
  }
  if ( v6 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800087b0  push    rbp
0x1800087b2  push    rbx
0x1800087b3  push    rsi
0x1800087b4  push    rdi
0x1800087b5  push    r12
0x1800087b7  push    r13
0x1800087b9  push    r14
0x1800087bb  push    r15
0x1800087bd  mov     rbp, rsp
0x1800087c0  sub     rsp, 48h
0x1800087c4  xor     edi, edi
0x1800087c6  mov     [rbp+arg_0], 0
0x1800087cd  mov     rsi, r8
0x1800087d0  mov     r15, rdx
0x1800087d3  mov     r13, rcx
0x1800087d6  test    rcx, rcx
0x1800087d9  jz      loc_180008996
0x1800087df  test    rdx, rdx
0x1800087e2  jz      loc_180008996
0x1800087e8  test    r8, r8
0x1800087eb  jz      loc_180008996
0x1800087f1  mov     r12, [rbp+arg_20]
0x1800087f5  test    r12, r12
0x1800087f8  jz      loc_180008996
0x1800087fe  mov     r14, [rbp+arg_28]
0x180008802  test    r14, r14
0x180008805  jz      loc_180008996
0x18000880b  mov     [r12], rdi
0x18000880f  mov     [r14], edi
0x180008812  test    r9d, r9d
0x180008815  jz      short loc_18000886D
0x180008817  test    byte ptr [r8+14h], 4
0x18000881c  jnz     short loc_180008828
0x18000881e  mov     ebx, 86000011h
0x180008823  jmp     loc_18000899B
0x180008828  mov     rax, [rdx]
0x18000882b  lea     r8, [rbp+var_10]
0x18000882f  mov     edx, 3
0x180008834  mov     [rbp+var_10], rdi
0x180008838  mov     rcx, r15
0x18000883b  mov     rax, [rax+58h]
0x18000883f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008844  mov     ebx, eax
0x180008846  test    eax, eax
0x180008848  js      loc_18000899B
0x18000884e  cmp     dword ptr [rsi+0Ch], 0Eh
0x180008852  jnz     loc_1800088FA
0x180008858  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000885c  call    ?RegisterChannel@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::RegisterChannel(ushort const *)
0x180008861  mov     ebx, eax
0x180008863  test    eax, eax
0x180008865  js      loc_18000899B
0x18000886b  jmp     short loc_1800088D0
0x18000886d  cmp     [r8+18h], edi
0x180008871  jnz     short loc_1800088D0
0x180008873  mov     rax, [rdx]
0x180008876  lea     r8, [rbp+var_10]
0x18000887a  mov     edx, 3
0x18000887f  mov     [rbp+var_10], rdi
0x180008883  mov     rcx, r15
0x180008886  mov     rax, [rax+58h]
0x18000888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888f  mov     ebx, eax
0x180008891  test    eax, eax
0x180008893  js      loc_18000899B
0x180008899  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000889d  call    ?IsChannelRegistered@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::IsChannelRegistered(ushort const *)
0x1800088a2  test    eax, eax
0x1800088a4  jns     short loc_1800088B0
0x1800088a6  mov     ebx, 86000002h
0x1800088ab  jmp     loc_18000899B
0x1800088b0  mov     ecx, [rsi+0Ch]
0x1800088b3  sub     ecx, 0Eh
0x1800088b6  jz      short loc_1800088D0
0x1800088b8  sub     ecx, 1
0x1800088bb  jz      short loc_1800088C9
0x1800088bd  sub     ecx, 1
0x1800088c0  jz      short loc_1800088D0
0x1800088c2  cmp     ecx, 1
0x1800088c5  jz      short loc_1800088D0
0x1800088c7  jmp     short loc_1800088A6
0x1800088c9  mov     dword ptr [r14], 2
0x1800088d0  mov     rax, [r15]
0x1800088d3  lea     rdx, [rbp+arg_0]
0x1800088d7  mov     rcx, r15
0x1800088da  mov     rax, [rax+88h]
0x1800088e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e6  mov     ebx, eax
0x1800088e8  test    eax, eax
0x1800088ea  js      loc_18000899B
0x1800088f0  mov     eax, [rsi+8]
0x1800088f3  inc     eax
0x1800088f5  cmp     eax, [rbp+arg_0]
0x1800088f8  jz      short loc_180008904
0x1800088fa  mov     ebx, 8000FFFFh
0x1800088ff  jmp     loc_18000899B
0x180008904  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000890b  mov     ecx, 48h ; 'H'; unsigned __int64
0x180008910  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008915  mov     [rbp+var_10], rax
0x180008919  mov     rdi, rax
0x18000891c  test    rax, rax
0x18000891f  jz      short loc_18000898D
0x180008921  mov     qword ptr [rax+10h], 0
0x180008929  xorps   xmm0, xmm0
0x18000892c  mov     qword ptr [rax+18h], 0
0x180008934  mov     dword ptr [rax+40h], 1
0x18000893b  movups  xmmword ptr [rax+20h], xmm0
0x18000893f  movups  xmmword ptr [rax+30h], xmm0
0x180008943  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNode@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNode'}
0x18000894a  mov     [rdi], rax
0x18000894d  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180008954  mov     [rdi+8], rax
0x180008958  lock inc cs:dword_1800494E0
0x18000895f  test    rdi, rdi
0x180008962  jz      short loc_18000898F
0x180008964  mov     rax, [rdi]
0x180008967  mov     r9, rsi
0x18000896a  mov     r8, r15
0x18000896d  mov     rdx, r13
0x180008970  mov     rcx, rdi
0x180008973  mov     rax, [rax+88h]
0x18000897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897f  mov     ebx, eax
0x180008981  test    eax, eax
0x180008983  js      short loc_18000899B
0x180008985  mov     [r12], rdi
0x180008989  xor     edi, edi
0x18000898b  jmp     short loc_18000899B
0x18000898d  xor     edi, edi
0x18000898f  mov     ebx, 8007000Eh
0x180008994  jmp     short loc_18000899B
0x180008996  mov     ebx, 80070057h
0x18000899b  mov     eax, cs:dword_180048E90
0x1800089a1  cmp     eax, 5
0x1800089a4  jbe     short loc_1800089D7
0x1800089a6  mov     [rbp+var_18], ebx
0x1800089a9  test    rsi, rsi
0x1800089ac  jz      short loc_1800089B3
0x1800089ae  mov     eax, [rsi+0Ch]
0x1800089b1  jmp     short loc_1800089B6
0x1800089b3  or      eax, 0FFFFFFFFh
0x1800089b6  mov     dword ptr [rbp+var_10], eax
0x1800089b9  lea     rdx, dword_18003EBA4
0x1800089c0  lea     rax, [rbp+var_18]
0x1800089c4  mov     [rsp+48h+var_20], rax
0x1800089c9  lea     rax, [rbp+var_10]
0x1800089cd  mov     [rsp+48h+var_28], rax
0x1800089d2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800089d7  test    rdi, rdi
0x1800089da  jz      short loc_1800089EB
0x1800089dc  mov     rax, [rdi]
0x1800089df  mov     rcx, rdi
0x1800089e2  mov     rax, [rax+10h]
0x1800089e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089eb  mov     eax, ebx
0x1800089ed  add     rsp, 48h
0x1800089f1  pop     r15
0x1800089f3  pop     r14
0x1800089f5  pop     r13
0x1800089f7  pop     r12
0x1800089f9  pop     rdi
0x1800089fa  pop     rsi
0x1800089fb  pop     rbx
0x1800089fc  pop     rbp
0x1800089fd  retn
```
