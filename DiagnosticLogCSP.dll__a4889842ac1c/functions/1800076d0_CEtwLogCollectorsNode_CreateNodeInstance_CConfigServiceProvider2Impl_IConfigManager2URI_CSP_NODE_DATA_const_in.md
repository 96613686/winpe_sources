# CEtwLogCollectorsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x1800076d0`
- end: `0x180007a22`
- name: `?CreateNodeInstance@CEtwLogCollectorsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `850`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007460`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x1800076d0`
- `0x1800090b4`
- `0x18000de80`
- `0x18000dff4`
- `0x18000e054`
- `0x18000e158`
- `0x18000e374`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CEtwLogCollectorsNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v9; // rdi
  struct ICSPNode **v10; // r12
  unsigned int *v11; // r15
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned __int16 *v21; // rax
  int v22; // eax
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-30h] BYREF
  __int128 v26; // [rsp+40h] [rbp-28h] BYREF
  __int64 v27; // [rsp+50h] [rbp-18h]
  int v28; // [rsp+B0h] [rbp+48h] BYREF

  v28 = 0;
  v9 = 0;
  v26 = 0;
  v27 = 0;
  if ( !a1 || !a2 || !a3 || (v10 = a5) == 0 || (v11 = a6) == 0 )
  {
    v12 = -2147024809;
    goto LABEL_45;
  }
  *a5 = 0;
  *v11 = 0;
  if ( !(_DWORD)a4 )
  {
    if ( !*((_DWORD *)a3 + 6) )
    {
      v25 = 0;
      v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
              a2,
              3,
              &v25);
      if ( v12 < 0 )
        goto LABEL_45;
      if ( (int)CEtwLogCollector::IsCollectorRegistered(v25) < 0 )
        goto LABEL_21;
      v14 = *((_DWORD *)a3 + 3);
      if ( v14 > 8 )
      {
        v19 = v14 - 9;
        if ( !v19 || (v20 = v19 - 1) == 0 || v20 - 1 <= 1 )
        {
          lpSubKey = 0;
          v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, LPCWSTR *))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  5,
                  &lpSubKey);
          if ( v12 < 0 )
            goto LABEL_45;
          v12 = CEtwLogCollector::Open((CEtwLogCollector *)&v26, v25);
          if ( v12 < 0 )
            goto LABEL_45;
          if ( (int)CEtwLogCollector::IsProviderRegistered((CEtwLogCollector *)&v26, lpSubKey) >= 0 )
            goto LABEL_37;
        }
LABEL_21:
        v12 = -2046820350;
        goto LABEL_45;
      }
      if ( v14 != 8 )
      {
        v15 = v14 - 3;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( v18 )
              {
                if ( v18 != 1 )
                  goto LABEL_21;
              }
              else
              {
                *v11 = 2;
              }
            }
          }
        }
      }
    }
LABEL_37:
    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v28);
    if ( v12 < 0 )
      goto LABEL_45;
    if ( *((_DWORD *)a3 + 2) + 1 != v28 )
      goto LABEL_39;
    v21 = (unsigned __int16 *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = (struct ICSPNode *)v21;
    v25 = v21;
    if ( v21 )
    {
      *((_QWORD *)v21 + 2) = 0;
      *((_QWORD *)v21 + 3) = 0;
      *((_DWORD *)v21 + 16) = 1;
      *((_OWORD *)v21 + 2) = 0;
      *((_OWORD *)v21 + 3) = 0;
      *(_QWORD *)v21 = &CEtwLogCollectorsNode::`vftable'{for `ICSPNode'};
      *((_QWORD *)v21 + 1) = &CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'};
      _InterlockedIncrement(&dword_1800494E0);
      v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v21 + 136LL))(
              v21,
              a1,
              a2,
              a3);
      if ( v12 >= 0 )
      {
        *v10 = v9;
        v9 = 0;
      }
    }
    else
    {
      v9 = 0;
      v12 = -2147024882;
    }
    goto LABEL_45;
  }
  if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
  {
    v12 = -2046820335;
    goto LABEL_45;
  }
  v25 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
          a2,
          3,
          &v25);
  if ( v12 < 0 )
    goto LABEL_45;
  if ( *((_DWORD *)a3 + 3) == 3 )
  {
    v13 = CEtwLogCollector::RegisterCollector(v25);
LABEL_15:
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_45;
    goto LABEL_37;
  }
  if ( *((_DWORD *)a3 + 3) != 9 )
  {
LABEL_39:
    v12 = -2147418113;
    goto LABEL_45;
  }
  lpSubKey = 0;
  v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, LPCWSTR *))(*(_QWORD *)a2 + 88LL))(
          a2,
          5,
          &lpSubKey);
  if ( v12 >= 0 )
  {
    v12 = CEtwLogCollector::Open((CEtwLogCollector *)&v26, v25);
    if ( v12 >= 0 )
    {
      v13 = CEtwLogCollector::RegisterProvider((CEtwLogCollector *)&v26, lpSubKey);
      goto LABEL_15;
    }
  }
LABEL_45:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(lpSubKey) = v12;
    if ( a3 )
      v22 = *((_DWORD *)a3 + 3);
    else
      v22 = -1;
    LODWORD(v25) = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&dword_18003E9CC,
      (__int64)a3,
      a4,
      (__int64)&v25,
      (__int64)&lpSubKey);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v9 + 16LL))(v9);
  CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)&v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800076d0  push    rbp
0x1800076d2  push    rbx
0x1800076d3  push    rsi
0x1800076d4  push    rdi
0x1800076d5  push    r12
0x1800076d7  push    r13
0x1800076d9  push    r14
0x1800076db  push    r15
0x1800076dd  mov     rbp, rsp
0x1800076e0  sub     rsp, 68h
0x1800076e4  mov     rsi, r8
0x1800076e7  mov     r14, rdx
0x1800076ea  mov     r13, rcx
0x1800076ed  mov     [rbp+arg_0], 0
0x1800076f4  xor     edi, edi
0x1800076f6  xorps   xmm0, xmm0
0x1800076f9  movdqu  [rbp+var_28], xmm0
0x1800076fe  mov     [rbp+var_18], rdi
0x180007702  test    rcx, rcx
0x180007705  jz      loc_1800079B0
0x18000770b  test    rdx, rdx
0x18000770e  jz      loc_1800079B0
0x180007714  test    r8, r8
0x180007717  jz      loc_1800079B0
0x18000771d  mov     r12, [rbp+arg_20]
0x180007721  test    r12, r12
0x180007724  jz      loc_1800079B0
0x18000772a  mov     r15, [rbp+arg_28]
0x18000772e  test    r15, r15
0x180007731  jz      loc_1800079B0
0x180007737  mov     [r12], rdi
0x18000773b  mov     [r15], edi
0x18000773e  test    r9d, r9d
0x180007741  jz      loc_1800077FA
0x180007747  test    byte ptr [r8+14h], 4
0x18000774c  jnz     short loc_180007758
0x18000774e  mov     ebx, 86000011h
0x180007753  jmp     loc_1800079B5
0x180007758  mov     [rbp+var_30], 0
0x180007760  mov     rax, [rdx]
0x180007763  lea     r8, [rbp+var_30]
0x180007767  mov     edx, 3
0x18000776c  mov     rcx, r14
0x18000776f  mov     rax, [rax+58h]
0x180007773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007778  mov     ebx, eax
0x18000777a  test    eax, eax
0x18000777c  js      loc_1800079B5
0x180007782  cmp     dword ptr [rsi+0Ch], 3
0x180007786  jz      short loc_1800077EF
0x180007788  cmp     dword ptr [rsi+0Ch], 9
0x18000778c  jnz     loc_180007914
0x180007792  mov     [rbp+lpSubKey], 0
0x18000779a  mov     rax, [r14]
0x18000779d  lea     r8, [rbp+lpSubKey]
0x1800077a1  mov     edx, 5
0x1800077a6  mov     rcx, r14
0x1800077a9  mov     rax, [rax+58h]
0x1800077ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b2  mov     ebx, eax
0x1800077b4  test    eax, eax
0x1800077b6  js      loc_1800079B5
0x1800077bc  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800077c0  lea     rcx, [rbp+var_28]; this
0x1800077c4  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x1800077c9  mov     ebx, eax
0x1800077cb  test    eax, eax
0x1800077cd  js      loc_1800079B5
0x1800077d3  mov     rdx, [rbp+lpSubKey]; unsigned __int16 *
0x1800077d7  lea     rcx, [rbp+var_28]; this
0x1800077db  call    ?RegisterProvider@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::RegisterProvider(ushort const *)
0x1800077e0  mov     ebx, eax
0x1800077e2  test    eax, eax
0x1800077e4  js      loc_1800079B5
0x1800077ea  jmp     loc_1800078EA
0x1800077ef  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800077f3  call    ?RegisterCollector@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::RegisterCollector(ushort const *)
0x1800077f8  jmp     short loc_1800077E0
0x1800077fa  cmp     dword ptr [r8+18h], 0
0x1800077ff  jnz     loc_1800078EA
0x180007805  mov     [rbp+var_30], 0
0x18000780d  mov     rax, [rdx]
0x180007810  lea     r8, [rbp+var_30]
0x180007814  mov     edx, 3
0x180007819  mov     rcx, r14
0x18000781c  mov     rax, [rax+58h]
0x180007820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007825  mov     ebx, eax
0x180007827  test    eax, eax
0x180007829  js      loc_1800079B5
0x18000782f  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180007833  call    ?IsCollectorRegistered@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::IsCollectorRegistered(ushort const *)
0x180007838  test    eax, eax
0x18000783a  jns     short loc_180007846
0x18000783c  mov     ebx, 86000002h
0x180007841  jmp     loc_1800079B5
0x180007846  mov     eax, [rsi+0Ch]
0x180007849  cmp     eax, 8
0x18000784c  ja      short loc_180007880
0x18000784e  jz      loc_1800078EA
0x180007854  sub     eax, 3
0x180007857  jz      loc_1800078EA
0x18000785d  sub     eax, 1
0x180007860  jz      loc_1800078EA
0x180007866  sub     eax, 1
0x180007869  jz      short loc_1800078EA
0x18000786b  sub     eax, 1
0x18000786e  jz      short loc_180007877
0x180007870  cmp     eax, 1
0x180007873  jz      short loc_1800078EA
0x180007875  jmp     short loc_18000783C
0x180007877  mov     dword ptr [r15], 2
0x18000787e  jmp     short loc_1800078EA
0x180007880  sub     eax, 9
0x180007883  jz      short loc_180007894
0x180007885  sub     eax, 1
0x180007888  jz      short loc_180007894
0x18000788a  sub     eax, 1
0x18000788d  jz      short loc_180007894
0x18000788f  cmp     eax, 1
0x180007892  jnz     short loc_18000783C
0x180007894  mov     [rbp+lpSubKey], 0
0x18000789c  mov     rax, [r14]
0x18000789f  lea     r8, [rbp+lpSubKey]
0x1800078a3  mov     edx, 5
0x1800078a8  mov     rcx, r14
0x1800078ab  mov     rax, [rax+58h]
0x1800078af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b4  mov     ebx, eax
0x1800078b6  test    eax, eax
0x1800078b8  js      loc_1800079B5
0x1800078be  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800078c2  lea     rcx, [rbp+var_28]; this
0x1800078c6  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x1800078cb  mov     ebx, eax
0x1800078cd  test    eax, eax
0x1800078cf  js      loc_1800079B5
0x1800078d5  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800078d9  lea     rcx, [rbp+var_28]; this
0x1800078dd  call    ?IsProviderRegistered@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::IsProviderRegistered(ushort const *)
0x1800078e2  test    eax, eax
0x1800078e4  js      loc_18000783C
0x1800078ea  mov     rax, [r14]
0x1800078ed  lea     rdx, [rbp+arg_0]
0x1800078f1  mov     rcx, r14
0x1800078f4  mov     rax, [rax+88h]
0x1800078fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007900  mov     ebx, eax
0x180007902  test    eax, eax
0x180007904  js      loc_1800079B5
0x18000790a  mov     eax, [rsi+8]
0x18000790d  inc     eax
0x18000790f  cmp     eax, [rbp+arg_0]
0x180007912  jz      short loc_18000791E
0x180007914  mov     ebx, 8000FFFFh
0x180007919  jmp     loc_1800079B5
0x18000791e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007925  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000792a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000792f  mov     rdi, rax
0x180007932  mov     [rbp+var_30], rax
0x180007936  test    rax, rax
0x180007939  jz      short loc_1800079A7
0x18000793b  mov     qword ptr [rax+10h], 0
0x180007943  mov     qword ptr [rax+18h], 0
0x18000794b  mov     dword ptr [rax+40h], 1
0x180007952  xorps   xmm0, xmm0
0x180007955  movups  xmmword ptr [rax+20h], xmm0
0x180007959  movups  xmmword ptr [rax+30h], xmm0
0x18000795d  lea     rax, ??_7CEtwLogCollectorsNode@@6BICSPNode@@@; const CEtwLogCollectorsNode::`vftable'{for `ICSPNode'}
0x180007964  mov     [rdi], rax
0x180007967  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000796e  mov     [rdi+8], rax
0x180007972  lock inc cs:dword_1800494E0
0x180007979  test    rdi, rdi
0x18000797c  jz      short loc_1800079A9
0x18000797e  mov     rax, [rdi]
0x180007981  mov     r9, rsi
0x180007984  mov     r8, r14
0x180007987  mov     rdx, r13
0x18000798a  mov     rcx, rdi
0x18000798d  mov     rax, [rax+88h]
0x180007994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007999  mov     ebx, eax
0x18000799b  test    eax, eax
0x18000799d  js      short loc_1800079B5
0x18000799f  mov     [r12], rdi
0x1800079a3  xor     edi, edi
0x1800079a5  jmp     short loc_1800079B5
0x1800079a7  xor     edi, edi
0x1800079a9  mov     ebx, 8007000Eh
0x1800079ae  jmp     short loc_1800079B5
0x1800079b0  mov     ebx, 80070057h
0x1800079b5  mov     eax, cs:dword_180048E90
0x1800079bb  cmp     eax, 5
0x1800079be  jbe     short loc_1800079F1
0x1800079c0  mov     dword ptr [rbp+lpSubKey], ebx
0x1800079c3  test    rsi, rsi
0x1800079c6  jz      short loc_1800079CD
0x1800079c8  mov     eax, [rsi+0Ch]
0x1800079cb  jmp     short loc_1800079D0
0x1800079cd  or      eax, 0FFFFFFFFh
0x1800079d0  mov     dword ptr [rbp+var_30], eax
0x1800079d3  lea     rax, [rbp+lpSubKey]
0x1800079d7  mov     [rsp+68h+var_40], rax
0x1800079dc  lea     rax, [rbp+var_30]
0x1800079e0  mov     [rsp+68h+var_48], rax
0x1800079e5  lea     rdx, dword_18003E9CC
0x1800079ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800079f1  test    rdi, rdi
0x1800079f4  jz      short loc_180007A06
0x1800079f6  mov     rax, [rdi]
0x1800079f9  mov     rcx, rdi
0x1800079fc  mov     rax, [rax+10h]
0x180007a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a05  nop
0x180007a06  lea     rcx, [rbp+var_28]; this
0x180007a0a  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007a0f  mov     eax, ebx
0x180007a11  add     rsp, 68h
0x180007a15  pop     r15
0x180007a17  pop     r14
0x180007a19  pop     r13
0x180007a1b  pop     r12
0x180007a1d  pop     rdi
0x180007a1e  pop     rsi
0x180007a1f  pop     rbx
0x180007a20  pop     rbp
0x180007a21  retn
```
