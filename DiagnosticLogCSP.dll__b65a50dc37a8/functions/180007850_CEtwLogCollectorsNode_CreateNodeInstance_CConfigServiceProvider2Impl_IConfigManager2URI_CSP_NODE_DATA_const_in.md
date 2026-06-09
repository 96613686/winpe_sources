# CEtwLogCollectorsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180007850`
- end: `0x180007ba3`
- name: `?CreateNodeInstance@CEtwLogCollectorsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `851`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800075c0`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x180007850`
- `0x1800092f8`
- `0x18000e558`
- `0x18000e6dc`
- `0x18000e744`
- `0x18000e858`
- `0x18000ea88`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      _InterlockedIncrement(&dword_18004B4E0);
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(lpSubKey) = v12;
    if ( a3 )
      v22 = *((_DWORD *)a3 + 3);
    else
      v22 = -1;
    LODWORD(v25) = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (unsigned __int8 *)&dword_1800409CC,
      (__int64)a3,
      a4,
      (__int64)&v25,
      (__int64)&lpSubKey);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v9 + 16LL))(v9);
  CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007850  push    rbp
0x180007852  push    rbx
0x180007853  push    rsi
0x180007854  push    rdi
0x180007855  push    r12
0x180007857  push    r13
0x180007859  push    r14
0x18000785b  push    r15
0x18000785d  mov     rbp, rsp
0x180007860  sub     rsp, 68h
0x180007864  mov     rsi, r8
0x180007867  mov     r14, rdx
0x18000786a  mov     r13, rcx
0x18000786d  mov     [rbp+arg_0], 0
0x180007874  xor     edi, edi
0x180007876  xorps   xmm0, xmm0
0x180007879  movdqu  [rbp+var_28], xmm0
0x18000787e  mov     [rbp+var_18], rdi
0x180007882  test    rcx, rcx
0x180007885  jz      loc_180007B30
0x18000788b  test    rdx, rdx
0x18000788e  jz      loc_180007B30
0x180007894  test    r8, r8
0x180007897  jz      loc_180007B30
0x18000789d  mov     r12, [rbp+arg_20]
0x1800078a1  test    r12, r12
0x1800078a4  jz      loc_180007B30
0x1800078aa  mov     r15, [rbp+arg_28]
0x1800078ae  test    r15, r15
0x1800078b1  jz      loc_180007B30
0x1800078b7  mov     [r12], rdi
0x1800078bb  mov     [r15], edi
0x1800078be  test    r9d, r9d
0x1800078c1  jz      loc_18000797A
0x1800078c7  test    byte ptr [r8+14h], 4
0x1800078cc  jnz     short loc_1800078D8
0x1800078ce  mov     ebx, 86000011h
0x1800078d3  jmp     loc_180007B35
0x1800078d8  mov     [rbp+var_30], 0
0x1800078e0  mov     rax, [rdx]
0x1800078e3  lea     r8, [rbp+var_30]
0x1800078e7  mov     edx, 3
0x1800078ec  mov     rcx, r14
0x1800078ef  mov     rax, [rax+58h]
0x1800078f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f8  mov     ebx, eax
0x1800078fa  test    eax, eax
0x1800078fc  js      loc_180007B35
0x180007902  cmp     dword ptr [rsi+0Ch], 3
0x180007906  jz      short loc_18000796F
0x180007908  cmp     dword ptr [rsi+0Ch], 9
0x18000790c  jnz     loc_180007A94
0x180007912  mov     [rbp+lpSubKey], 0
0x18000791a  mov     rax, [r14]
0x18000791d  lea     r8, [rbp+lpSubKey]
0x180007921  mov     edx, 5
0x180007926  mov     rcx, r14
0x180007929  mov     rax, [rax+58h]
0x18000792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007932  mov     ebx, eax
0x180007934  test    eax, eax
0x180007936  js      loc_180007B35
0x18000793c  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180007940  lea     rcx, [rbp+var_28]; this
0x180007944  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007949  mov     ebx, eax
0x18000794b  test    eax, eax
0x18000794d  js      loc_180007B35
0x180007953  mov     rdx, [rbp+lpSubKey]; unsigned __int16 *
0x180007957  lea     rcx, [rbp+var_28]; this
0x18000795b  call    ?RegisterProvider@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::RegisterProvider(ushort const *)
0x180007960  mov     ebx, eax
0x180007962  test    eax, eax
0x180007964  js      loc_180007B35
0x18000796a  jmp     loc_180007A6A
0x18000796f  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180007973  call    ?RegisterCollector@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::RegisterCollector(ushort const *)
0x180007978  jmp     short loc_180007960
0x18000797a  cmp     dword ptr [r8+18h], 0
0x18000797f  jnz     loc_180007A6A
0x180007985  mov     [rbp+var_30], 0
0x18000798d  mov     rax, [rdx]
0x180007990  lea     r8, [rbp+var_30]
0x180007994  mov     edx, 3
0x180007999  mov     rcx, r14
0x18000799c  mov     rax, [rax+58h]
0x1800079a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a5  mov     ebx, eax
0x1800079a7  test    eax, eax
0x1800079a9  js      loc_180007B35
0x1800079af  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800079b3  call    ?IsCollectorRegistered@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::IsCollectorRegistered(ushort const *)
0x1800079b8  test    eax, eax
0x1800079ba  jns     short loc_1800079C6
0x1800079bc  mov     ebx, 86000002h
0x1800079c1  jmp     loc_180007B35
0x1800079c6  mov     eax, [rsi+0Ch]
0x1800079c9  cmp     eax, 8
0x1800079cc  ja      short loc_180007A00
0x1800079ce  jz      loc_180007A6A
0x1800079d4  sub     eax, 3
0x1800079d7  jz      loc_180007A6A
0x1800079dd  sub     eax, 1
0x1800079e0  jz      loc_180007A6A
0x1800079e6  sub     eax, 1
0x1800079e9  jz      short loc_180007A6A
0x1800079eb  sub     eax, 1
0x1800079ee  jz      short loc_1800079F7
0x1800079f0  cmp     eax, 1
0x1800079f3  jz      short loc_180007A6A
0x1800079f5  jmp     short loc_1800079BC
0x1800079f7  mov     dword ptr [r15], 2
0x1800079fe  jmp     short loc_180007A6A
0x180007a00  sub     eax, 9
0x180007a03  jz      short loc_180007A14
0x180007a05  sub     eax, 1
0x180007a08  jz      short loc_180007A14
0x180007a0a  sub     eax, 1
0x180007a0d  jz      short loc_180007A14
0x180007a0f  cmp     eax, 1
0x180007a12  jnz     short loc_1800079BC
0x180007a14  mov     [rbp+lpSubKey], 0
0x180007a1c  mov     rax, [r14]
0x180007a1f  lea     r8, [rbp+lpSubKey]
0x180007a23  mov     edx, 5
0x180007a28  mov     rcx, r14
0x180007a2b  mov     rax, [rax+58h]
0x180007a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a34  mov     ebx, eax
0x180007a36  test    eax, eax
0x180007a38  js      loc_180007B35
0x180007a3e  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180007a42  lea     rcx, [rbp+var_28]; this
0x180007a46  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007a4b  mov     ebx, eax
0x180007a4d  test    eax, eax
0x180007a4f  js      loc_180007B35
0x180007a55  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180007a59  lea     rcx, [rbp+var_28]; this
0x180007a5d  call    ?IsProviderRegistered@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::IsProviderRegistered(ushort const *)
0x180007a62  test    eax, eax
0x180007a64  js      loc_1800079BC
0x180007a6a  mov     rax, [r14]
0x180007a6d  lea     rdx, [rbp+arg_0]
0x180007a71  mov     rcx, r14
0x180007a74  mov     rax, [rax+88h]
0x180007a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a80  mov     ebx, eax
0x180007a82  test    eax, eax
0x180007a84  js      loc_180007B35
0x180007a8a  mov     eax, [rsi+8]
0x180007a8d  inc     eax
0x180007a8f  cmp     eax, [rbp+arg_0]
0x180007a92  jz      short loc_180007A9E
0x180007a94  mov     ebx, 8000FFFFh
0x180007a99  jmp     loc_180007B35
0x180007a9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007aa5  mov     ecx, 48h ; 'H'; unsigned __int64
0x180007aaa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007aaf  mov     rdi, rax
0x180007ab2  mov     [rbp+var_30], rax
0x180007ab6  test    rax, rax
0x180007ab9  jz      short loc_180007B27
0x180007abb  mov     qword ptr [rax+10h], 0
0x180007ac3  mov     qword ptr [rax+18h], 0
0x180007acb  mov     dword ptr [rax+40h], 1
0x180007ad2  xorps   xmm0, xmm0
0x180007ad5  movups  xmmword ptr [rax+20h], xmm0
0x180007ad9  movups  xmmword ptr [rax+30h], xmm0
0x180007add  lea     rax, ??_7CEtwLogCollectorsNode@@6BICSPNode@@@; const CEtwLogCollectorsNode::`vftable'{for `ICSPNode'}
0x180007ae4  mov     [rdi], rax
0x180007ae7  lea     rax, ??_7CEventLogChannelsNode@@6BICSPNodeTransactioning@@@; const CEventLogChannelsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180007aee  mov     [rdi+8], rax
0x180007af2  lock inc cs:dword_18004B4E0
0x180007af9  test    rdi, rdi
0x180007afc  jz      short loc_180007B29
0x180007afe  mov     rax, [rdi]
0x180007b01  mov     r9, rsi
0x180007b04  mov     r8, r14
0x180007b07  mov     rdx, r13
0x180007b0a  mov     rcx, rdi
0x180007b0d  mov     rax, [rax+88h]
0x180007b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b19  mov     ebx, eax
0x180007b1b  test    eax, eax
0x180007b1d  js      short loc_180007B35
0x180007b1f  mov     [r12], rdi
0x180007b23  xor     edi, edi
0x180007b25  jmp     short loc_180007B35
0x180007b27  xor     edi, edi
0x180007b29  mov     ebx, 8007000Eh
0x180007b2e  jmp     short loc_180007B35
0x180007b30  mov     ebx, 80070057h
0x180007b35  mov     eax, cs:dword_18004AE90
0x180007b3b  cmp     eax, 5
0x180007b3e  jbe     short loc_180007B71
0x180007b40  mov     dword ptr [rbp+lpSubKey], ebx
0x180007b43  test    rsi, rsi
0x180007b46  jz      short loc_180007B4D
0x180007b48  mov     eax, [rsi+0Ch]
0x180007b4b  jmp     short loc_180007B50
0x180007b4d  or      eax, 0FFFFFFFFh
0x180007b50  mov     dword ptr [rbp+var_30], eax
0x180007b53  lea     rax, [rbp+lpSubKey]
0x180007b57  mov     [rsp+68h+var_40], rax
0x180007b5c  lea     rax, [rbp+var_30]
0x180007b60  mov     [rsp+68h+var_48], rax
0x180007b65  lea     rdx, dword_1800409CC
0x180007b6c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007b71  test    rdi, rdi
0x180007b74  jz      short loc_180007B86
0x180007b76  mov     rax, [rdi]
0x180007b79  mov     rcx, rdi
0x180007b7c  mov     rax, [rax+10h]
0x180007b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b85  nop
0x180007b86  lea     rcx, [rbp+var_28]; this
0x180007b8a  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007b8f  mov     eax, ebx
0x180007b91  add     rsp, 68h
0x180007b95  pop     r15
0x180007b97  pop     r14
0x180007b99  pop     r13
0x180007b9b  pop     r12
0x180007b9d  pop     rdi
0x180007b9e  pop     rsi
0x180007b9f  pop     rbx
0x180007ba0  pop     rbp
0x180007ba1  retn
```
