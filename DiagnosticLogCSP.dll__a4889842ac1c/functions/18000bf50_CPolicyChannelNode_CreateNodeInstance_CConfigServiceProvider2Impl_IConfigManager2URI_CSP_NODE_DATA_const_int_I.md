# CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000bf50`
- end: `0x18000c259`
- name: `?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `777`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bcc0`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x18000bf50`
- `0x18000cb9c`
- `0x18000cd38`
- `0x18000d09c`
- `0x180013090`
- `0x180037010`

## string_xrefs

- `0x18000c0fb`: `ChannelAccess`

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
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  bool v18; // al
  unsigned __int16 *v19; // rax
  int v20; // eax
  int v22; // [rsp+30h] [rbp-18h] BYREF
  int v23; // [rsp+34h] [rbp-14h] BYREF
  unsigned __int16 *v24[2]; // [rsp+38h] [rbp-10h] BYREF

  v22 = 0;
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
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v22);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( !a4 )
  {
    if ( *((_DWORD *)a3 + 6) )
      goto LABEL_39;
    v16 = *(_QWORD *)a2;
    v24[0] = 0;
    v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v16 + 88))(a2, 3, v24);
    if ( v14 < 0 )
      goto LABEL_48;
    if ( *((_DWORD *)a3 + 3) == 32 )
      goto LABEL_39;
    if ( *((_DWORD *)a3 + 3) == 34 )
    {
      v18 = CPolicyChannelNode::PolicyChannelExist(v24[0]);
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) == 35 )
      {
        v17 = L"MaxSize";
      }
      else if ( *((_DWORD *)a3 + 3) == 36 )
      {
        v17 = L"ChannelAccess";
      }
      else
      {
        v11 = (unsigned int)(*((_DWORD *)a3 + 3) - 37);
        if ( *((_DWORD *)a3 + 3) == 37 )
        {
          if ( !CPolicyChannelNode::ValueExist(L"Retention", v24[0]) )
            goto LABEL_37;
          v17 = L"AutoBackupLogFiles";
        }
        else
        {
          if ( *((_DWORD *)a3 + 3) != 38 )
          {
            v14 = -2046820350;
            goto LABEL_48;
          }
          v17 = L"Enabled";
        }
      }
      v18 = CPolicyChannelNode::ValueExist(v17, v24[0]);
    }
    if ( v18 )
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
  v24[0] = 0;
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(v15 + 88))(a2, 3, v24);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( *((_DWORD *)a3 + 3) != 32 )
  {
    if ( *((_DWORD *)a3 + 3) != 34 )
    {
      if ( *((_DWORD *)a3 + 3) != 35 && *((_DWORD *)a3 + 3) != 36 )
      {
        v11 = (unsigned int)(*((_DWORD *)a3 + 3) - 37);
        if ( (unsigned int)v11 >= 2 )
        {
LABEL_41:
          v14 = -2147418113;
          goto LABEL_48;
        }
      }
      goto LABEL_39;
    }
    v14 = CPolicyChannel::RegisterChannel(v24[0]);
    if ( v14 < 0 )
      goto LABEL_48;
    goto LABEL_38;
  }
LABEL_39:
  v14 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v22);
  if ( v14 < 0 )
    goto LABEL_48;
  if ( *((_DWORD *)a3 + 2) + 1 != v22 )
    goto LABEL_41;
  v19 = (unsigned __int16 *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v24[0] = v19;
  v10 = (struct ICSPNode *)v19;
  if ( v19 )
  {
    *((_QWORD *)v19 + 2) = 0;
    *((_QWORD *)v19 + 3) = 0;
    *((_DWORD *)v19 + 16) = 1;
    *((_OWORD *)v19 + 2) = 0;
    *((_OWORD *)v19 + 3) = 0;
    *(_QWORD *)v19 = &CPolicyChannelNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v19 + 1) = &CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_1800494E0);
    v14 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v19 + 136LL))(
            v19,
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v23 = v14;
    if ( a3 )
      v20 = *((_DWORD *)a3 + 3);
    else
      v20 = -1;
    LODWORD(v24[0]) = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (__int64)&byte_18003F217,
      v12,
      v13,
      (__int64)v24,
      (__int64)&v23);
  }
  if ( v10 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000bf50  push    rbp
0x18000bf52  push    rbx
0x18000bf53  push    rsi
0x18000bf54  push    rdi
0x18000bf55  push    r12
0x18000bf57  push    r13
0x18000bf59  push    r14
0x18000bf5b  push    r15
0x18000bf5d  mov     rbp, rsp
0x18000bf60  sub     rsp, 48h
0x18000bf64  mov     r15d, r9d
0x18000bf67  mov     [rbp+var_18], 0
0x18000bf6e  mov     rsi, r8
0x18000bf71  mov     r14, rdx
0x18000bf74  mov     r13, rcx
0x18000bf77  xor     edi, edi
0x18000bf79  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000bf7e  test    al, al
0x18000bf80  jz      loc_18000C1F4
0x18000bf86  test    r13, r13
0x18000bf89  jz      loc_18000C1ED
0x18000bf8f  test    r14, r14
0x18000bf92  jz      loc_18000C1ED
0x18000bf98  test    rsi, rsi
0x18000bf9b  jz      loc_18000C1ED
0x18000bfa1  mov     r12, [rbp+arg_20]
0x18000bfa5  test    r12, r12
0x18000bfa8  jz      loc_18000C1ED
0x18000bfae  mov     rax, [rbp+arg_28]
0x18000bfb2  test    rax, rax
0x18000bfb5  jz      loc_18000C1ED
0x18000bfbb  mov     [r12], rdi
0x18000bfbf  lea     rdx, [rbp+var_18]
0x18000bfc3  mov     [rax], edi
0x18000bfc5  mov     rcx, r14
0x18000bfc8  mov     rax, [r14]
0x18000bfcb  mov     rax, [rax+88h]
0x18000bfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd7  mov     ebx, eax
0x18000bfd9  test    eax, eax
0x18000bfdb  js      loc_18000C1F6
0x18000bfe1  test    r15d, r15d
0x18000bfe4  jz      loc_18000C072
0x18000bfea  test    byte ptr [rsi+14h], 4
0x18000bfee  jnz     short loc_18000BFFA
0x18000bff0  mov     ebx, 86000011h
0x18000bff5  jmp     loc_18000C1F6
0x18000bffa  mov     rax, [r14]
0x18000bffd  lea     r8, [rbp+var_10]
0x18000c001  mov     edx, 3
0x18000c006  mov     [rbp+var_10], rdi
0x18000c00a  mov     rcx, r14
0x18000c00d  mov     rax, [rax+58h]
0x18000c011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c016  mov     ebx, eax
0x18000c018  test    eax, eax
0x18000c01a  js      loc_18000C1F6
0x18000c020  mov     ecx, [rsi+0Ch]
0x18000c023  sub     ecx, 20h ; ' '
0x18000c026  jz      loc_18000C127
0x18000c02c  sub     ecx, 2
0x18000c02f  jz      short loc_18000C05A
0x18000c031  sub     ecx, 1
0x18000c034  jz      loc_18000C127
0x18000c03a  sub     ecx, 1
0x18000c03d  jz      loc_18000C127
0x18000c043  sub     ecx, 1
0x18000c046  jz      loc_18000C127
0x18000c04c  cmp     ecx, 1
0x18000c04f  jz      loc_18000C127
0x18000c055  jmp     loc_18000C151
0x18000c05a  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000c05e  call    ?RegisterChannel@CPolicyChannel@@SAJPEBG@Z; CPolicyChannel::RegisterChannel(ushort const *)
0x18000c063  mov     ebx, eax
0x18000c065  test    eax, eax
0x18000c067  js      loc_18000C1F6
0x18000c06d  jmp     loc_18000C11F
0x18000c072  cmp     [rsi+18h], edi
0x18000c075  jnz     loc_18000C127
0x18000c07b  mov     rax, [r14]
0x18000c07e  lea     r8, [rbp+var_10]
0x18000c082  mov     edx, 3
0x18000c087  mov     [rbp+var_10], rdi
0x18000c08b  mov     rcx, r14
0x18000c08e  mov     rax, [rax+58h]
0x18000c092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c097  mov     ebx, eax
0x18000c099  test    eax, eax
0x18000c09b  js      loc_18000C1F6
0x18000c0a1  mov     ecx, [rsi+0Ch]
0x18000c0a4  sub     ecx, 20h ; ' '
0x18000c0a7  jz      short loc_18000C127
0x18000c0a9  sub     ecx, 2
0x18000c0ac  jz      short loc_18000C10D
0x18000c0ae  sub     ecx, 1
0x18000c0b1  jz      short loc_18000C104
0x18000c0b3  sub     ecx, 1
0x18000c0b6  jz      short loc_18000C0FB
0x18000c0b8  sub     ecx, 1
0x18000c0bb  jz      short loc_18000C0DE
0x18000c0bd  cmp     ecx, 1
0x18000c0c0  jz      short loc_18000C0CC
0x18000c0c2  mov     ebx, 86000002h
0x18000c0c7  jmp     loc_18000C1F6
0x18000c0cc  lea     rcx, aEnabled; "Enabled"
0x18000c0d3  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000c0d7  call    ?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z; CPolicyChannelNode::ValueExist(ushort const *,ushort const *)
0x18000c0dc  jmp     short loc_18000C116
0x18000c0de  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000c0e2  lea     rcx, aRetention; "Retention"
0x18000c0e9  call    ?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z; CPolicyChannelNode::ValueExist(ushort const *,ushort const *)
0x18000c0ee  test    al, al
0x18000c0f0  jz      short loc_18000C11A
0x18000c0f2  lea     rcx, aAutobackuplogf; "AutoBackupLogFiles"
0x18000c0f9  jmp     short loc_18000C0D3
0x18000c0fb  lea     rcx, aChannelaccess; "ChannelAccess"
0x18000c102  jmp     short loc_18000C0D3
0x18000c104  lea     rcx, aMaxsize; "MaxSize"
0x18000c10b  jmp     short loc_18000C0D3
0x18000c10d  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18000c111  call    ?PolicyChannelExist@CPolicyChannelNode@@CA_NPEBG@Z; CPolicyChannelNode::PolicyChannelExist(ushort const *)
0x18000c116  test    al, al
0x18000c118  jnz     short loc_18000C127
0x18000c11a  mov     ebx, 86000002h
0x18000c11f  test    ebx, ebx
0x18000c121  js      loc_18000C1F6
0x18000c127  mov     rax, [r14]
0x18000c12a  lea     rdx, [rbp+var_18]
0x18000c12e  mov     rcx, r14
0x18000c131  mov     rax, [rax+88h]
0x18000c138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c13d  mov     ebx, eax
0x18000c13f  test    eax, eax
0x18000c141  js      loc_18000C1F6
0x18000c147  mov     eax, [rsi+8]
0x18000c14a  inc     eax
0x18000c14c  cmp     eax, [rbp+var_18]
0x18000c14f  jz      short loc_18000C15B
0x18000c151  mov     ebx, 8000FFFFh
0x18000c156  jmp     loc_18000C1F6
0x18000c15b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c162  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000c167  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c16c  mov     [rbp+var_10], rax
0x18000c170  mov     rdi, rax
0x18000c173  test    rax, rax
0x18000c176  jz      short loc_18000C1E4
0x18000c178  mov     qword ptr [rax+10h], 0
0x18000c180  xorps   xmm0, xmm0
0x18000c183  mov     qword ptr [rax+18h], 0
0x18000c18b  mov     dword ptr [rax+40h], 1
0x18000c192  movups  xmmword ptr [rax+20h], xmm0
0x18000c196  movups  xmmword ptr [rax+30h], xmm0
0x18000c19a  lea     rax, ??_7CPolicyChannelNode@@6BICSPNode@@@; const CPolicyChannelNode::`vftable'{for `ICSPNode'}
0x18000c1a1  mov     [rdi], rax
0x18000c1a4  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000c1ab  mov     [rdi+8], rax
0x18000c1af  lock inc cs:dword_1800494E0
0x18000c1b6  test    rdi, rdi
0x18000c1b9  jz      short loc_18000C1E6
0x18000c1bb  mov     rax, [rdi]
0x18000c1be  mov     r9, rsi
0x18000c1c1  mov     r8, r14
0x18000c1c4  mov     rdx, r13
0x18000c1c7  mov     rcx, rdi
0x18000c1ca  mov     rax, [rax+88h]
0x18000c1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d6  mov     ebx, eax
0x18000c1d8  test    eax, eax
0x18000c1da  js      short loc_18000C1F6
0x18000c1dc  mov     [r12], rdi
0x18000c1e0  xor     edi, edi
0x18000c1e2  jmp     short loc_18000C1F6
0x18000c1e4  xor     edi, edi
0x18000c1e6  mov     ebx, 8007000Eh
0x18000c1eb  jmp     short loc_18000C1F6
0x18000c1ed  mov     ebx, 80070057h
0x18000c1f2  jmp     short loc_18000C1F6
0x18000c1f4  xor     ebx, ebx
0x18000c1f6  mov     eax, cs:dword_180048E90
0x18000c1fc  cmp     eax, 5
0x18000c1ff  jbe     short loc_18000C232
0x18000c201  mov     [rbp+var_14], ebx
0x18000c204  test    rsi, rsi
0x18000c207  jz      short loc_18000C20E
0x18000c209  mov     eax, [rsi+0Ch]
0x18000c20c  jmp     short loc_18000C211
0x18000c20e  or      eax, 0FFFFFFFFh
0x18000c211  mov     dword ptr [rbp+var_10], eax
0x18000c214  lea     rdx, byte_18003F217
0x18000c21b  lea     rax, [rbp+var_14]
0x18000c21f  mov     [rsp+48h+var_20], rax
0x18000c224  lea     rax, [rbp+var_10]
0x18000c228  mov     [rsp+48h+var_28], rax
0x18000c22d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c232  test    rdi, rdi
0x18000c235  jz      short loc_18000C246
0x18000c237  mov     rax, [rdi]
0x18000c23a  mov     rcx, rdi
0x18000c23d  mov     rax, [rax+10h]
0x18000c241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c246  mov     eax, ebx
0x18000c248  add     rsp, 48h
0x18000c24c  pop     r15
0x18000c24e  pop     r14
0x18000c250  pop     r13
0x18000c252  pop     r12
0x18000c254  pop     rdi
0x18000c255  pop     rsi
0x18000c256  pop     rbx
0x18000c257  pop     rbp
0x18000c258  retn
```
