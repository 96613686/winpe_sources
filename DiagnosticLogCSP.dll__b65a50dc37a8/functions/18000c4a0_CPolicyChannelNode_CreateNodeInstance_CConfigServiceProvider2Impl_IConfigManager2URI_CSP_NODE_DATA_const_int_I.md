# CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000c4a0`
- end: `0x18000c7aa`
- name: `?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c210`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x18000c4a0`
- `0x18000d194`
- `0x18000d344`
- `0x18000d6e4`
- `0x180013ab4`
- `0x180039010`

## string_xrefs

- `0x18000c64b`: `ChannelAccess`

## pseudocode

```c
__int64 __fastcall CPolicyChannelNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v10; // rdi
  unsigned int v11; // ecx
  unsigned __int16 *v12; // r8
  int v13; // r9d
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  const WCHAR *v18; // rcx
  char v19; // al
  unsigned __int16 *v20; // rax
  int v21; // eax
  int v23; // [rsp+30h] [rbp-18h] BYREF
  int v24; // [rsp+34h] [rbp-14h] BYREF
  unsigned __int16 *v25[2]; // [rsp+38h] [rbp-10h] BYREF

  v23 = 0;
  v10 = 0;
  if ( !CPolicyChannelNode::PoliciesKeyExist() )
  {
    v14 = 0;
    goto LABEL_48;
  }
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    v14 = -2147024809;
    goto LABEL_48;
  }
  *a5 = 0;
  *a6 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v23);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( !a4 )
  {
    if ( *((_DWORD *)a3 + 6) )
      goto LABEL_39;
    v17 = *(_QWORD *)a2;
    v25[0] = 0;
    v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v17 + 88))(a2, 3, v25);
    if ( v14 < 0 )
      goto LABEL_48;
    if ( *((_DWORD *)a3 + 3) == 32 )
      goto LABEL_39;
    if ( *((_DWORD *)a3 + 3) == 34 )
    {
      v19 = CPolicyChannelNode::PolicyChannelExist(v25[0]);
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) == 35 )
      {
        v18 = L"MaxSize";
      }
      else if ( *((_DWORD *)a3 + 3) == 36 )
      {
        v18 = L"ChannelAccess";
      }
      else
      {
        v11 = *((_DWORD *)a3 + 3) - 37;
        if ( *((_DWORD *)a3 + 3) == 37 )
        {
          if ( !CPolicyChannelNode::ValueExist(L"Retention", v25[0]) )
            goto LABEL_37;
          v18 = L"AutoBackupLogFiles";
        }
        else
        {
          if ( *((_DWORD *)a3 + 3) != 38 )
          {
            v14 = -2046820350;
            goto LABEL_48;
          }
          v18 = L"Enabled";
        }
      }
      v19 = CPolicyChannelNode::ValueExist(v18, v25[0]);
    }
    if ( v19 )
      goto LABEL_39;
LABEL_37:
    v14 = -2046820350;
LABEL_38:
    if ( v14 < 0 )
      goto LABEL_48;
    goto LABEL_39;
  }
  if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
  {
    v14 = -2046820335;
    goto LABEL_48;
  }
  v15 = *(_QWORD *)a2;
  v25[0] = 0;
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v15 + 88))(a2, 3, v25);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( *((_DWORD *)a3 + 3) != 32 )
  {
    if ( *((_DWORD *)a3 + 3) != 34 )
    {
      if ( *((_DWORD *)a3 + 3) != 35 && *((_DWORD *)a3 + 3) != 36 )
      {
        v11 = *((_DWORD *)a3 + 3) - 37;
        if ( v11 >= 2 )
        {
LABEL_41:
          v14 = -2147418113;
          goto LABEL_48;
        }
      }
      goto LABEL_39;
    }
    v14 = CPolicyChannel::RegisterChannel(v25[0], v16, v12, v13);
    if ( v14 < 0 )
      goto LABEL_48;
    goto LABEL_38;
  }
LABEL_39:
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v23);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( *((_DWORD *)a3 + 2) + 1 != v23 )
    goto LABEL_41;
  v20 = (unsigned __int16 *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = v20;
  v10 = (struct ICSPNode *)v20;
  if ( v20 )
  {
    *((_QWORD *)v20 + 2) = 0;
    *((_QWORD *)v20 + 3) = 0;
    *((_DWORD *)v20 + 16) = 1;
    *((_OWORD *)v20 + 2) = 0;
    *((_OWORD *)v20 + 3) = 0;
    *(_QWORD *)v20 = &CPolicyChannelNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v20 + 1) = &CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_18004B4E0);
    v14 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v20 + 136LL))(
            v20,
            a1,
            a2,
            a3);
    if ( v14 >= 0 )
    {
      *a5 = v10;
      v10 = 0;
    }
  }
  else
  {
    v10 = 0;
    v14 = -2147024882;
  }
LABEL_48:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v24 = v14;
    if ( a3 )
      v21 = *((_DWORD *)a3 + 3);
    else
      v21 = -1;
    LODWORD(v25[0]) = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&byte_180041217,
      (_DWORD)v12,
      v13,
      (__int64)v25,
      (__int64)&v24);
  }
  if ( v10 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000c4a0  push    rbp
0x18000c4a2  push    rbx
0x18000c4a3  push    rsi
0x18000c4a4  push    rdi
0x18000c4a5  push    r12
0x18000c4a7  push    r13
0x18000c4a9  push    r14
0x18000c4ab  push    r15
0x18000c4ad  mov     rbp, rsp
0x18000c4b0  sub     rsp, 48h
0x18000c4b4  mov     r15d, r9d
0x18000c4b7  mov     [rbp+var_18], 0
0x18000c4be  mov     rsi, r8
0x18000c4c1  mov     r14, rdx
0x18000c4c4  mov     r13, rcx
0x18000c4c7  xor     edi, edi
0x18000c4c9  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000c4ce  test    al, al
0x18000c4d0  jz      loc_18000C744
0x18000c4d6  test    r13, r13
0x18000c4d9  jz      loc_18000C73D
0x18000c4df  test    r14, r14
0x18000c4e2  jz      loc_18000C73D
0x18000c4e8  test    rsi, rsi
0x18000c4eb  jz      loc_18000C73D
0x18000c4f1  mov     r12, [rbp+arg_20]
0x18000c4f5  test    r12, r12
0x18000c4f8  jz      loc_18000C73D
0x18000c4fe  mov     rax, [rbp+arg_28]
0x18000c502  test    rax, rax
0x18000c505  jz      loc_18000C73D
0x18000c50b  mov     [r12], rdi
0x18000c50f  lea     rdx, [rbp+var_18]
0x18000c513  mov     [rax], edi
0x18000c515  mov     rcx, r14
0x18000c518  mov     rax, [r14]
0x18000c51b  mov     rax, [rax+88h]
0x18000c522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c527  mov     ebx, eax
0x18000c529  test    eax, eax
0x18000c52b  js      loc_18000C746
0x18000c531  test    r15d, r15d
0x18000c534  jz      loc_18000C5C2
0x18000c53a  test    byte ptr [rsi+14h], 4
0x18000c53e  jnz     short loc_18000C54A
0x18000c540  mov     ebx, 86000011h
0x18000c545  jmp     loc_18000C746
0x18000c54a  mov     rax, [r14]
0x18000c54d  lea     r8, [rbp+var_10]
0x18000c551  mov     edx, 3
0x18000c556  mov     [rbp+var_10], rdi
0x18000c55a  mov     rcx, r14
0x18000c55d  mov     rax, [rax+58h]
0x18000c561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c566  mov     ebx, eax
0x18000c568  test    eax, eax
0x18000c56a  js      loc_18000C746
0x18000c570  mov     ecx, [rsi+0Ch]
0x18000c573  sub     ecx, 20h ; ' '
0x18000c576  jz      loc_18000C677
0x18000c57c  sub     ecx, 2
0x18000c57f  jz      short loc_18000C5AA
0x18000c581  sub     ecx, 1
0x18000c584  jz      loc_18000C677
0x18000c58a  sub     ecx, 1
0x18000c58d  jz      loc_18000C677
0x18000c593  sub     ecx, 1
0x18000c596  jz      loc_18000C677
0x18000c59c  cmp     ecx, 1
0x18000c59f  jz      loc_18000C677
0x18000c5a5  jmp     loc_18000C6A1
0x18000c5aa  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000c5ae  call    ?RegisterChannel@CPolicyChannel@@SAJPEBG@Z; CPolicyChannel::RegisterChannel(ushort const *)
0x18000c5b3  mov     ebx, eax
0x18000c5b5  test    eax, eax
0x18000c5b7  js      loc_18000C746
0x18000c5bd  jmp     loc_18000C66F
0x18000c5c2  cmp     [rsi+18h], edi
0x18000c5c5  jnz     loc_18000C677
0x18000c5cb  mov     rax, [r14]
0x18000c5ce  lea     r8, [rbp+var_10]
0x18000c5d2  mov     edx, 3
0x18000c5d7  mov     [rbp+var_10], rdi
0x18000c5db  mov     rcx, r14
0x18000c5de  mov     rax, [rax+58h]
0x18000c5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5e7  mov     ebx, eax
0x18000c5e9  test    eax, eax
0x18000c5eb  js      loc_18000C746
0x18000c5f1  mov     ecx, [rsi+0Ch]
0x18000c5f4  sub     ecx, 20h ; ' '
0x18000c5f7  jz      short loc_18000C677
0x18000c5f9  sub     ecx, 2
0x18000c5fc  jz      short loc_18000C65D
0x18000c5fe  sub     ecx, 1
0x18000c601  jz      short loc_18000C654
0x18000c603  sub     ecx, 1
0x18000c606  jz      short loc_18000C64B
0x18000c608  sub     ecx, 1
0x18000c60b  jz      short loc_18000C62E
0x18000c60d  cmp     ecx, 1
0x18000c610  jz      short loc_18000C61C
0x18000c612  mov     ebx, 86000002h
0x18000c617  jmp     loc_18000C746
0x18000c61c  lea     rcx, aEnabled; "Enabled"
0x18000c623  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000c627  call    ?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z; CPolicyChannelNode::ValueExist(ushort const *,ushort const *)
0x18000c62c  jmp     short loc_18000C666
0x18000c62e  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000c632  lea     rcx, aRetention; "Retention"
0x18000c639  call    ?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z; CPolicyChannelNode::ValueExist(ushort const *,ushort const *)
0x18000c63e  test    al, al
0x18000c640  jz      short loc_18000C66A
0x18000c642  lea     rcx, aAutobackuplogf; "AutoBackupLogFiles"
0x18000c649  jmp     short loc_18000C623
0x18000c64b  lea     rcx, aChannelaccess; "ChannelAccess"
0x18000c652  jmp     short loc_18000C623
0x18000c654  lea     rcx, aMaxsize; "MaxSize"
0x18000c65b  jmp     short loc_18000C623
0x18000c65d  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000c661  call    ?PolicyChannelExist@CPolicyChannelNode@@CA_NPEBG@Z; CPolicyChannelNode::PolicyChannelExist(ushort const *)
0x18000c666  test    al, al
0x18000c668  jnz     short loc_18000C677
0x18000c66a  mov     ebx, 86000002h
0x18000c66f  test    ebx, ebx
0x18000c671  js      loc_18000C746
0x18000c677  mov     rax, [r14]
0x18000c67a  lea     rdx, [rbp+var_18]
0x18000c67e  mov     rcx, r14
0x18000c681  mov     rax, [rax+88h]
0x18000c688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68d  mov     ebx, eax
0x18000c68f  test    eax, eax
0x18000c691  js      loc_18000C746
0x18000c697  mov     eax, [rsi+8]
0x18000c69a  inc     eax
0x18000c69c  cmp     eax, [rbp+var_18]
0x18000c69f  jz      short loc_18000C6AB
0x18000c6a1  mov     ebx, 8000FFFFh
0x18000c6a6  jmp     loc_18000C746
0x18000c6ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c6b2  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000c6b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c6bc  mov     [rbp+var_10], rax
0x18000c6c0  mov     rdi, rax
0x18000c6c3  test    rax, rax
0x18000c6c6  jz      short loc_18000C734
0x18000c6c8  mov     qword ptr [rax+10h], 0
0x18000c6d0  xorps   xmm0, xmm0
0x18000c6d3  mov     qword ptr [rax+18h], 0
0x18000c6db  mov     dword ptr [rax+40h], 1
0x18000c6e2  movups  xmmword ptr [rax+20h], xmm0
0x18000c6e6  movups  xmmword ptr [rax+30h], xmm0
0x18000c6ea  lea     rax, ??_7CPolicyChannelNode@@6BICSPNode@@@; const CPolicyChannelNode::`vftable'{for `ICSPNode'}
0x18000c6f1  mov     [rdi], rax
0x18000c6f4  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000c6fb  mov     [rdi+8], rax
0x18000c6ff  lock inc cs:dword_18004B4E0
0x18000c706  test    rdi, rdi
0x18000c709  jz      short loc_18000C736
0x18000c70b  mov     rax, [rdi]
0x18000c70e  mov     r9, rsi
0x18000c711  mov     r8, r14
0x18000c714  mov     rdx, r13
0x18000c717  mov     rcx, rdi
0x18000c71a  mov     rax, [rax+88h]
0x18000c721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c726  mov     ebx, eax
0x18000c728  test    eax, eax
0x18000c72a  js      short loc_18000C746
0x18000c72c  mov     [r12], rdi
0x18000c730  xor     edi, edi
0x18000c732  jmp     short loc_18000C746
0x18000c734  xor     edi, edi
0x18000c736  mov     ebx, 8007000Eh
0x18000c73b  jmp     short loc_18000C746
0x18000c73d  mov     ebx, 80070057h
0x18000c742  jmp     short loc_18000C746
0x18000c744  xor     ebx, ebx
0x18000c746  mov     eax, cs:dword_18004AE90
0x18000c74c  cmp     eax, 5
0x18000c74f  jbe     short loc_18000C782
0x18000c751  mov     [rbp+var_14], ebx
0x18000c754  test    rsi, rsi
0x18000c757  jz      short loc_18000C75E
0x18000c759  mov     eax, [rsi+0Ch]
0x18000c75c  jmp     short loc_18000C761
0x18000c75e  or      eax, 0FFFFFFFFh
0x18000c761  mov     dword ptr [rbp+var_10], eax
0x18000c764  lea     rdx, byte_180041217
0x18000c76b  lea     rax, [rbp+var_14]
0x18000c76f  mov     [rsp+48h+var_20], rax
0x18000c774  lea     rax, [rbp+var_10]
0x18000c778  mov     [rsp+48h+var_28], rax
0x18000c77d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c782  test    rdi, rdi
0x18000c785  jz      short loc_18000C796
0x18000c787  mov     rax, [rdi]
0x18000c78a  mov     rcx, rdi
0x18000c78d  mov     rax, [rax+10h]
0x18000c791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c796  mov     eax, ebx
0x18000c798  add     rsp, 48h
0x18000c79c  pop     r15
0x18000c79e  pop     r14
0x18000c7a0  pop     r13
0x18000c7a2  pop     r12
0x18000c7a4  pop     rdi
0x18000c7a5  pop     rsi
0x18000c7a6  pop     rbx
0x18000c7a7  pop     rbp
0x18000c7a8  retn
```
