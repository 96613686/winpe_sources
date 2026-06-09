# CEventLogChannelsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x1800089b0`
- end: `0x180008bff`
- name: `?CreateNodeInstance@CEventLogChannelsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008840`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x1800089b0`
- `0x18000f9fc`
- `0x18000fd38`
- `0x180039010`

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
    _InterlockedIncrement(&dword_18004B4E0);
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v18 = v12;
    if ( a3 )
      v16 = *((_DWORD *)a3 + 3);
    else
      v16 = -1;
    LODWORD(v19[0]) = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned __int8 *)&dword_180040BA4,
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
0x1800089b0  push    rbp
0x1800089b2  push    rbx
0x1800089b3  push    rsi
0x1800089b4  push    rdi
0x1800089b5  push    r12
0x1800089b7  push    r13
0x1800089b9  push    r14
0x1800089bb  push    r15
0x1800089bd  mov     rbp, rsp
0x1800089c0  sub     rsp, 48h
0x1800089c4  xor     edi, edi
0x1800089c6  mov     [rbp+arg_0], 0
0x1800089cd  mov     rsi, r8
0x1800089d0  mov     r15, rdx
0x1800089d3  mov     r13, rcx
0x1800089d6  test    rcx, rcx
0x1800089d9  jz      loc_180008B96
0x1800089df  test    rdx, rdx
0x1800089e2  jz      loc_180008B96
0x1800089e8  test    r8, r8
0x1800089eb  jz      loc_180008B96
0x1800089f1  mov     r12, [rbp+arg_20]
0x1800089f5  test    r12, r12
0x1800089f8  jz      loc_180008B96
0x1800089fe  mov     r14, [rbp+arg_28]
0x180008a02  test    r14, r14
0x180008a05  jz      loc_180008B96
0x180008a0b  mov     [r12], rdi
0x180008a0f  mov     [r14], edi
0x180008a12  test    r9d, r9d
0x180008a15  jz      short loc_180008A6D
0x180008a17  test    byte ptr [r8+14h], 4
0x180008a1c  jnz     short loc_180008A28
0x180008a1e  mov     ebx, 86000011h
0x180008a23  jmp     loc_180008B9B
0x180008a28  mov     rax, [rdx]
0x180008a2b  lea     r8, [rbp+var_10]
0x180008a2f  mov     edx, 3
0x180008a34  mov     [rbp+var_10], rdi
0x180008a38  mov     rcx, r15
0x180008a3b  mov     rax, [rax+58h]
0x180008a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a44  mov     ebx, eax
0x180008a46  test    eax, eax
0x180008a48  js      loc_180008B9B
0x180008a4e  cmp     dword ptr [rsi+0Ch], 0Eh
0x180008a52  jnz     loc_180008AFA
0x180008a58  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180008a5c  call    ?RegisterChannel@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::RegisterChannel(ushort const *)
0x180008a61  mov     ebx, eax
0x180008a63  test    eax, eax
0x180008a65  js      loc_180008B9B
0x180008a6b  jmp     short loc_180008AD0
0x180008a6d  cmp     [r8+18h], edi
0x180008a71  jnz     short loc_180008AD0
0x180008a73  mov     rax, [rdx]
0x180008a76  lea     r8, [rbp+var_10]
0x180008a7a  mov     edx, 3
0x180008a7f  mov     [rbp+var_10], rdi
0x180008a83  mov     rcx, r15
0x180008a86  mov     rax, [rax+58h]
0x180008a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8f  mov     ebx, eax
0x180008a91  test    eax, eax
0x180008a93  js      loc_180008B9B
0x180008a99  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180008a9d  call    ?IsChannelRegistered@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::IsChannelRegistered(ushort const *)
0x180008aa2  test    eax, eax
0x180008aa4  jns     short loc_180008AB0
0x180008aa6  mov     ebx, 86000002h
0x180008aab  jmp     loc_180008B9B
0x180008ab0  mov     ecx, [rsi+0Ch]
0x180008ab3  sub     ecx, 0Eh
0x180008ab6  jz      short loc_180008AD0
0x180008ab8  sub     ecx, 1
0x180008abb  jz      short loc_180008AC9
0x180008abd  sub     ecx, 1
0x180008ac0  jz      short loc_180008AD0
0x180008ac2  cmp     ecx, 1
0x180008ac5  jz      short loc_180008AD0
0x180008ac7  jmp     short loc_180008AA6
0x180008ac9  mov     dword ptr [r14], 2
0x180008ad0  mov     rax, [r15]
0x180008ad3  lea     rdx, [rbp+arg_0]
0x180008ad7  mov     rcx, r15
0x180008ada  mov     rax, [rax+88h]
0x180008ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae6  mov     ebx, eax
0x180008ae8  test    eax, eax
0x180008aea  js      loc_180008B9B
0x180008af0  mov     eax, [rsi+8]
0x180008af3  inc     eax
0x180008af5  cmp     eax, [rbp+arg_0]
0x180008af8  jz      short loc_180008B04
0x180008afa  mov     ebx, 8000FFFFh
0x180008aff  jmp     loc_180008B9B
0x180008b04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008b0b  mov     ecx, 48h ; 'H'; unsigned __int64
0x180008b10  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008b15  mov     [rbp+var_10], rax
0x180008b19  mov     rdi, rax
0x180008b1c  test    rax, rax
0x180008b1f  jz      short loc_180008B8D
0x180008b21  mov     qword ptr [rax+10h], 0
0x180008b29  xorps   xmm0, xmm0
0x180008b2c  mov     qword ptr [rax+18h], 0
0x180008b34  mov     dword ptr [rax+40h], 1
0x180008b3b  movups  xmmword ptr [rax+20h], xmm0
0x180008b3f  movups  xmmword ptr [rax+30h], xmm0
0x180008b43  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNode@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNode'}
0x180008b4a  mov     [rdi], rax
0x180008b4d  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180008b54  mov     [rdi+8], rax
0x180008b58  lock inc cs:dword_18004B4E0
0x180008b5f  test    rdi, rdi
0x180008b62  jz      short loc_180008B8F
0x180008b64  mov     rax, [rdi]
0x180008b67  mov     r9, rsi
0x180008b6a  mov     r8, r15
0x180008b6d  mov     rdx, r13
0x180008b70  mov     rcx, rdi
0x180008b73  mov     rax, [rax+88h]
0x180008b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7f  mov     ebx, eax
0x180008b81  test    eax, eax
0x180008b83  js      short loc_180008B9B
0x180008b85  mov     [r12], rdi
0x180008b89  xor     edi, edi
0x180008b8b  jmp     short loc_180008B9B
0x180008b8d  xor     edi, edi
0x180008b8f  mov     ebx, 8007000Eh
0x180008b94  jmp     short loc_180008B9B
0x180008b96  mov     ebx, 80070057h
0x180008b9b  mov     eax, cs:dword_18004AE90
0x180008ba1  cmp     eax, 5
0x180008ba4  jbe     short loc_180008BD7
0x180008ba6  mov     [rbp+var_18], ebx
0x180008ba9  test    rsi, rsi
0x180008bac  jz      short loc_180008BB3
0x180008bae  mov     eax, [rsi+0Ch]
0x180008bb1  jmp     short loc_180008BB6
0x180008bb3  or      eax, 0FFFFFFFFh
0x180008bb6  mov     dword ptr [rbp+var_10], eax
0x180008bb9  lea     rdx, dword_180040BA4
0x180008bc0  lea     rax, [rbp+var_18]
0x180008bc4  mov     [rsp+48h+var_20], rax
0x180008bc9  lea     rax, [rbp+var_10]
0x180008bcd  mov     [rsp+48h+var_28], rax
0x180008bd2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008bd7  test    rdi, rdi
0x180008bda  jz      short loc_180008BEB
0x180008bdc  mov     rax, [rdi]
0x180008bdf  mov     rcx, rdi
0x180008be2  mov     rax, [rax+10h]
0x180008be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008beb  mov     eax, ebx
0x180008bed  add     rsp, 48h
0x180008bf1  pop     r15
0x180008bf3  pop     r14
0x180008bf5  pop     r13
0x180008bf7  pop     r12
0x180008bf9  pop     rdi
0x180008bfa  pop     rsi
0x180008bfb  pop     rbx
0x180008bfc  pop     rbp
0x180008bfd  retn
```
