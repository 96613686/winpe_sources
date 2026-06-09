# CFileDownloadDMChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180009710`
- end: `0x18000998b`
- name: `?CreateNodeInstance@CFileDownloadDMChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `635`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x1800090b4`
- `0x180009710`
- `0x180009994`
- `0x1800116a4`
- `0x180011dd0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CFileDownloadDMChannelNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v9; // rdi
  struct ICSPNode **v10; // r15
  unsigned int *v11; // rax
  int BlockNumber; // ebx
  struct ICSPNode *v13; // rax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-30h] BYREF
  int v17; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-28h] BYREF
  _OWORD v19[2]; // [rsp+40h] [rbp-20h] BYREF
  struct ICSPNode *v20; // [rsp+90h] [rbp+30h] BYREF

  v17 = 0;
  v9 = 0;
  if ( a1 && a2 && a3 && (v10 = a5) != 0 && (v11 = a6) != 0 )
  {
    *a5 = 0;
    *v11 = 0;
    if ( (_DWORD)a4 )
    {
      BlockNumber = -2046820335;
      goto LABEL_33;
    }
    if ( !*((_DWORD *)a3 + 6) )
    {
      v18 = 0;
      BlockNumber = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                      a2,
                      3,
                      &v18);
      if ( BlockNumber < 0 )
        goto LABEL_33;
      memset(v19, 0, sizeof(v19));
      if ( (int)CFileDownload_DMChannel::Initialize((CFileDownload_DMChannel *)v19, v18, (int)a3, a4) < 0 )
        goto LABEL_11;
      if ( *((_DWORD *)a3 + 3) != 22
        && *((_DWORD *)a3 + 3) != 23
        && *((_DWORD *)a3 + 3) != 24
        && *((_DWORD *)a3 + 3) != 25
        && *((_DWORD *)a3 + 3) != 26
        && *((_DWORD *)a3 + 3) != 27 )
      {
        if ( *((_DWORD *)a3 + 3) != 28 )
          goto LABEL_11;
        LODWORD(v20) = 0;
        v16 = 0;
        BlockNumber = CFileDownloadDMChannelNode::GetBlockNumber(a2, (int *)&v20);
        if ( BlockNumber < 0 )
          goto LABEL_12;
        BlockNumber = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)v19, &v16);
        if ( BlockNumber < 0 )
          goto LABEL_12;
        if ( (int)v20 < 0 || (int)v20 >= v16 )
        {
LABEL_11:
          BlockNumber = -2046820350;
LABEL_12:
          CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)v19);
          goto LABEL_33;
        }
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)v19);
    }
    BlockNumber = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v17);
    if ( BlockNumber >= 0 )
    {
      if ( *((_DWORD *)a3 + 2) + 1 == v17 )
      {
        v13 = (struct ICSPNode *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v9 = v13;
        v20 = v13;
        if ( v13 )
        {
          *((_QWORD *)v13 + 2) = 0;
          *((_QWORD *)v13 + 3) = 0;
          *((_DWORD *)v13 + 16) = 1;
          *((_OWORD *)v13 + 2) = 0;
          *((_OWORD *)v13 + 3) = 0;
          *(_QWORD *)v13 = &CFileDownloadDMChannelNode::`vftable'{for `ICSPNode'};
          *((_QWORD *)v13 + 1) = &CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'};
          _InterlockedIncrement(&dword_1800494E0);
          BlockNumber = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v13 + 136LL))(
                          v13,
                          a1,
                          a2,
                          a3);
          if ( BlockNumber >= 0 )
          {
            *v10 = v9;
            v9 = 0;
          }
        }
        else
        {
          v9 = 0;
          BlockNumber = -2147024882;
        }
      }
      else
      {
        BlockNumber = -2147418113;
      }
    }
  }
  else
  {
    BlockNumber = -2147024809;
  }
LABEL_33:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v20) = BlockNumber;
    if ( a3 )
      v14 = *((_DWORD *)a3 + 3);
    else
      v14 = -1;
    v16 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&word_18003EDCE,
      (__int64)a3,
      a4,
      (__int64)&v16,
      (__int64)&v20);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)BlockNumber;
}

```

## disassembly

```asm
0x180009710  mov     [rsp-28h+arg_8], rbx
0x180009715  mov     [rsp-28h+arg_10], rsi
0x18000971a  push    rbp
0x18000971b  push    rdi
0x18000971c  push    r12
0x18000971e  push    r14
0x180009720  push    r15
0x180009722  mov     rbp, rsp
0x180009725  sub     rsp, 60h
0x180009729  mov     rsi, r8
0x18000972c  mov     r14, rdx
0x18000972f  mov     r12, rcx
0x180009732  mov     [rbp+var_2C], 0
0x180009739  xor     edi, edi
0x18000973b  test    rcx, rcx
0x18000973e  jz      loc_18000991B
0x180009744  test    rdx, rdx
0x180009747  jz      loc_18000991B
0x18000974d  test    r8, r8
0x180009750  jz      loc_18000991B
0x180009756  mov     r15, [rbp+arg_20]
0x18000975a  test    r15, r15
0x18000975d  jz      loc_18000991B
0x180009763  mov     rax, [rbp+arg_28]
0x180009767  test    rax, rax
0x18000976a  jz      loc_18000991B
0x180009770  mov     [r15], rdi
0x180009773  mov     [rax], edi
0x180009775  test    r9d, r9d
0x180009778  jz      short loc_180009784
0x18000977a  mov     ebx, 86000011h
0x18000977f  jmp     loc_180009920
0x180009784  cmp     [r8+18h], edi
0x180009788  jnz     loc_180009856
0x18000978e  mov     [rbp+var_28], rdi
0x180009792  mov     rax, [rdx]
0x180009795  lea     r8, [rbp+var_28]
0x180009799  mov     edx, 3
0x18000979e  mov     rcx, r14
0x1800097a1  mov     rax, [rax+58h]
0x1800097a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097aa  mov     ebx, eax
0x1800097ac  test    eax, eax
0x1800097ae  js      loc_180009920
0x1800097b4  xorps   xmm0, xmm0
0x1800097b7  movdqu  [rbp+var_20], xmm0
0x1800097bc  xorps   xmm1, xmm1
0x1800097bf  movdqu  [rbp+var_10], xmm1
0x1800097c4  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x1800097c8  lea     rcx, [rbp+var_20]; this
0x1800097cc  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x1800097d1  test    eax, eax
0x1800097d3  jns     short loc_1800097E8
0x1800097d5  mov     ebx, 86000002h
0x1800097da  lea     rcx, [rbp+var_20]; this
0x1800097de  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x1800097e3  jmp     loc_180009920
0x1800097e8  mov     ecx, [rsi+0Ch]
0x1800097eb  sub     ecx, 16h
0x1800097ee  jz      short loc_18000984D
0x1800097f0  sub     ecx, 1
0x1800097f3  jz      short loc_18000984D
0x1800097f5  sub     ecx, 1
0x1800097f8  jz      short loc_18000984D
0x1800097fa  sub     ecx, 1
0x1800097fd  jz      short loc_18000984D
0x1800097ff  sub     ecx, 1
0x180009802  jz      short loc_18000984D
0x180009804  sub     ecx, 1
0x180009807  jz      short loc_18000984D
0x180009809  cmp     ecx, 1
0x18000980c  jnz     short loc_1800097D5
0x18000980e  mov     dword ptr [rbp+arg_0], 0
0x180009815  mov     [rbp+var_30], 0
0x18000981c  lea     rdx, [rbp+arg_0]; int *
0x180009820  mov     rcx, r14; struct IConfigManager2URI *
0x180009823  call    ?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z; CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)
0x180009828  mov     ebx, eax
0x18000982a  test    eax, eax
0x18000982c  js      short loc_1800097DA
0x18000982e  lea     rdx, [rbp+var_30]; int *
0x180009832  lea     rcx, [rbp+var_20]; this
0x180009836  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x18000983b  mov     ebx, eax
0x18000983d  test    eax, eax
0x18000983f  js      short loc_1800097DA
0x180009841  mov     eax, dword ptr [rbp+arg_0]
0x180009844  test    eax, eax
0x180009846  js      short loc_1800097D5
0x180009848  cmp     eax, [rbp+var_30]
0x18000984b  jge     short loc_1800097D5
0x18000984d  lea     rcx, [rbp+var_20]; this
0x180009851  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009856  mov     rax, [r14]
0x180009859  lea     rdx, [rbp+var_2C]
0x18000985d  mov     rcx, r14
0x180009860  mov     rax, [rax+88h]
0x180009867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000986c  mov     ebx, eax
0x18000986e  test    eax, eax
0x180009870  js      loc_180009920
0x180009876  mov     eax, [rsi+8]
0x180009879  inc     eax
0x18000987b  cmp     eax, [rbp+var_2C]
0x18000987e  jz      short loc_18000988A
0x180009880  mov     ebx, 8000FFFFh
0x180009885  jmp     loc_180009920
0x18000988a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009891  mov     ecx, 48h ; 'H'; unsigned __int64
0x180009896  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000989b  mov     rdi, rax
0x18000989e  mov     [rbp+arg_0], rax
0x1800098a2  test    rax, rax
0x1800098a5  jz      short loc_180009912
0x1800098a7  mov     qword ptr [rax+10h], 0
0x1800098af  mov     qword ptr [rax+18h], 0
0x1800098b7  mov     dword ptr [rax+40h], 1
0x1800098be  xorps   xmm0, xmm0
0x1800098c1  movups  xmmword ptr [rax+20h], xmm0
0x1800098c5  movups  xmmword ptr [rax+30h], xmm0
0x1800098c9  lea     rax, ??_7CFileDownloadDMChannelNode@@6BICSPNode@@@; const CFileDownloadDMChannelNode::`vftable'{for `ICSPNode'}
0x1800098d0  mov     [rdi], rax
0x1800098d3  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNodeTransactioning@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'}
0x1800098da  mov     [rdi+8], rax
0x1800098de  lock inc cs:dword_1800494E0
0x1800098e5  test    rdi, rdi
0x1800098e8  jz      short loc_180009914
0x1800098ea  mov     rax, [rdi]
0x1800098ed  mov     r9, rsi
0x1800098f0  mov     r8, r14
0x1800098f3  mov     rdx, r12
0x1800098f6  mov     rcx, rdi
0x1800098f9  mov     rax, [rax+88h]
0x180009900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009905  mov     ebx, eax
0x180009907  test    eax, eax
0x180009909  js      short loc_180009920
0x18000990b  mov     [r15], rdi
0x18000990e  xor     edi, edi
0x180009910  jmp     short loc_180009920
0x180009912  xor     edi, edi
0x180009914  mov     ebx, 8007000Eh
0x180009919  jmp     short loc_180009920
0x18000991b  mov     ebx, 80070057h
0x180009920  mov     eax, cs:dword_180048E90
0x180009926  cmp     eax, 5
0x180009929  jbe     short loc_18000995C
0x18000992b  mov     dword ptr [rbp+arg_0], ebx
0x18000992e  test    rsi, rsi
0x180009931  jz      short loc_180009938
0x180009933  mov     eax, [rsi+0Ch]
0x180009936  jmp     short loc_18000993B
0x180009938  or      eax, 0FFFFFFFFh
0x18000993b  mov     [rbp+var_30], eax
0x18000993e  lea     rax, [rbp+arg_0]
0x180009942  mov     [rsp+60h+var_38], rax
0x180009947  lea     rax, [rbp+var_30]
0x18000994b  mov     [rsp+60h+var_40], rax
0x180009950  lea     rdx, word_18003EDCE
0x180009957  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000995c  test    rdi, rdi
0x18000995f  jz      short loc_180009970
0x180009961  mov     rax, [rdi]
0x180009964  mov     rcx, rdi
0x180009967  mov     rax, [rax+10h]
0x18000996b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009970  mov     eax, ebx
0x180009972  lea     r11, [rsp+60h+var_s0]
0x180009977  mov     rbx, [r11+38h]
0x18000997b  mov     rsi, [r11+40h]
0x18000997f  mov     rsp, r11
0x180009982  pop     r15
0x180009984  pop     r14
0x180009986  pop     r12
0x180009988  pop     rdi
0x180009989  pop     rbp
0x18000998a  retn
```
