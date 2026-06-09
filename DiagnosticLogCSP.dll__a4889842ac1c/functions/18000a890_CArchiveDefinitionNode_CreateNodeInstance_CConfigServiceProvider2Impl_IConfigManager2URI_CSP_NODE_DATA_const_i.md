# CArchiveDefinitionNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000a890`
- end: `0x18000aa2c`
- name: `?CreateNodeInstance@CArchiveDefinitionNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x18000a890`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CArchiveDefinitionNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v9; // r14
  unsigned int *v10; // rax
  struct ICSPNode *v11; // rbx
  int v12; // ecx
  int v13; // edi
  int v14; // r8d
  int v15; // r9d
  _QWORD *v16; // rax
  int v18; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-40h] BYREF
  int v20; // [rsp+80h] [rbp+8h] BYREF

  v20 = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v9 = a5;
  if ( !a5 )
    return 2147942487LL;
  v10 = a6;
  if ( !a6 )
    return 2147942487LL;
  v11 = 0;
  *a5 = 0;
  *v10 = 0;
  if ( *((_DWORD *)a3 + 3) == 30 )
    *v10 = 2;
  v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v20);
  if ( v13 >= 0 )
  {
    if ( *((_DWORD *)a3 + 2) + 1 == v20 )
    {
      v16 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v16;
      v11 = (struct ICSPNode *)v16;
      if ( v16 )
      {
        v16[2] = 0;
        v16[3] = 0;
        *((_DWORD *)v16 + 16) = 1;
        *((_OWORD *)v16 + 2) = 0;
        *((_OWORD *)v16 + 3) = 0;
        *v16 = &CArchiveDefinitionNode::`vftable'{for `ICSPNode'};
        v16[1] = &CArchiveDefinitionNode::`vftable'{for `ICSPNodeTransactioning'};
        _InterlockedIncrement(&dword_1800494E0);
        v13 = (*(__int64 (__fastcall **)(_QWORD *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*v16 + 136LL))(
                v16,
                a1,
                a2,
                a3);
        if ( v13 >= 0 )
        {
          *v9 = v11;
          v11 = 0;
        }
      }
      else
      {
        v11 = 0;
        v13 = -2147024882;
      }
    }
    else
    {
      v13 = -2147418113;
    }
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v19) = *((_DWORD *)a3 + 3);
    v18 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&byte_18003EFBF,
      v14,
      v15,
      (__int64)&v19,
      (__int64)&v18);
  }
  if ( v11 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a890  mov     rax, rsp
0x18000a893  push    rbx
0x18000a894  push    rbp
0x18000a895  push    rsi
0x18000a896  push    rdi
0x18000a897  push    r14
0x18000a899  push    r15
0x18000a89b  sub     rsp, 48h
0x18000a89f  mov     dword ptr [rax+8], 0
0x18000a8a6  mov     rsi, r8
0x18000a8a9  mov     r15, rdx
0x18000a8ac  mov     rbp, rcx
0x18000a8af  test    rcx, rcx
0x18000a8b2  jz      loc_18000AA1A
0x18000a8b8  test    rdx, rdx
0x18000a8bb  jz      loc_18000AA1A
0x18000a8c1  test    r8, r8
0x18000a8c4  jz      loc_18000AA1A
0x18000a8ca  mov     r14, [rsp+78h+arg_20]
0x18000a8d2  test    r14, r14
0x18000a8d5  jz      loc_18000AA1A
0x18000a8db  mov     rax, [rsp+78h+arg_28]
0x18000a8e3  test    rax, rax
0x18000a8e6  jz      loc_18000AA1A
0x18000a8ec  xor     ebx, ebx
0x18000a8ee  mov     [r14], rbx
0x18000a8f1  mov     [rax], ebx
0x18000a8f3  cmp     dword ptr [r8+0Ch], 1Eh
0x18000a8f8  jnz     short loc_18000A900
0x18000a8fa  mov     dword ptr [rax], 2
0x18000a900  mov     rax, [rdx]
0x18000a903  mov     rcx, r15
0x18000a906  lea     rdx, [rsp+78h+arg_0]
0x18000a90e  mov     rax, [rax+88h]
0x18000a915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a91a  mov     edi, eax
0x18000a91c  test    eax, eax
0x18000a91e  js      loc_18000A9CC
0x18000a924  mov     eax, [rsi+8]
0x18000a927  inc     eax
0x18000a929  cmp     eax, [rsp+78h+arg_0]
0x18000a930  jz      short loc_18000A93C
0x18000a932  mov     edi, 8000FFFFh
0x18000a937  jmp     loc_18000A9CC
0x18000a93c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a943  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000a948  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a94d  mov     [rsp+78h+var_40], rax
0x18000a952  mov     rbx, rax
0x18000a955  test    rax, rax
0x18000a958  jz      short loc_18000A9C5
0x18000a95a  mov     qword ptr [rax+10h], 0
0x18000a962  xorps   xmm0, xmm0
0x18000a965  mov     qword ptr [rax+18h], 0
0x18000a96d  mov     dword ptr [rax+40h], 1
0x18000a974  movups  xmmword ptr [rax+20h], xmm0
0x18000a978  movups  xmmword ptr [rax+30h], xmm0
0x18000a97c  lea     rax, ??_7CArchiveDefinitionNode@@6BICSPNode@@@; const CArchiveDefinitionNode::`vftable'{for `ICSPNode'}
0x18000a983  mov     [rbx], rax
0x18000a986  lea     rax, ??_7CArchiveDefinitionNode@@6BICSPNodeTransactioning@@@; const CArchiveDefinitionNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000a98d  mov     [rbx+8], rax
0x18000a991  lock inc cs:dword_1800494E0
0x18000a998  test    rbx, rbx
0x18000a99b  jz      short loc_18000A9C7
0x18000a99d  mov     rax, [rbx]
0x18000a9a0  mov     r9, rsi
0x18000a9a3  mov     r8, r15
0x18000a9a6  mov     rdx, rbp
0x18000a9a9  mov     rcx, rbx
0x18000a9ac  mov     rax, [rax+88h]
0x18000a9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b8  mov     edi, eax
0x18000a9ba  test    eax, eax
0x18000a9bc  js      short loc_18000A9CC
0x18000a9be  mov     [r14], rbx
0x18000a9c1  xor     ebx, ebx
0x18000a9c3  jmp     short loc_18000A9CC
0x18000a9c5  xor     ebx, ebx
0x18000a9c7  mov     edi, 8007000Eh
0x18000a9cc  mov     eax, cs:dword_180048E90
0x18000a9d2  cmp     eax, 5
0x18000a9d5  jbe     short loc_18000AA02
0x18000a9d7  mov     eax, [rsi+0Ch]
0x18000a9da  lea     rdx, byte_18003EFBF
0x18000a9e1  mov     dword ptr [rsp+78h+var_40], eax
0x18000a9e5  lea     rax, [rsp+78h+var_48]
0x18000a9ea  mov     [rsp+78h+var_50], rax
0x18000a9ef  lea     rax, [rsp+78h+var_40]
0x18000a9f4  mov     [rsp+78h+var_58], rax
0x18000a9f9  mov     [rsp+78h+var_48], edi
0x18000a9fd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000aa02  test    rbx, rbx
0x18000aa05  jz      short loc_18000AA16
0x18000aa07  mov     rax, [rbx]
0x18000aa0a  mov     rcx, rbx
0x18000aa0d  mov     rax, [rax+10h]
0x18000aa11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa16  mov     eax, edi
0x18000aa18  jmp     short loc_18000AA1F
0x18000aa1a  mov     eax, 80070057h
0x18000aa1f  add     rsp, 48h
0x18000aa23  pop     r15
0x18000aa25  pop     r14
0x18000aa27  pop     rdi
0x18000aa28  pop     rsi
0x18000aa29  pop     rbp
0x18000aa2a  pop     rbx
0x18000aa2b  retn
```
