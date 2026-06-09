# CArchiveDefinitionNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000abc0`
- end: `0x18000ad5d`
- name: `?CreateNodeInstance@CArchiveDefinitionNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x18000abc0`
- `0x180039010`

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
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // r8
  __int64 v15; // r9
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
        _InterlockedIncrement(&dword_18004B4E0);
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v19) = *((_DWORD *)a3 + 3);
    v18 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned __int8 *)byte_180040FBF,
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
0x18000abc0  mov     rax, rsp
0x18000abc3  push    rbx
0x18000abc4  push    rbp
0x18000abc5  push    rsi
0x18000abc6  push    rdi
0x18000abc7  push    r14
0x18000abc9  push    r15
0x18000abcb  sub     rsp, 48h
0x18000abcf  mov     dword ptr [rax+8], 0
0x18000abd6  mov     rsi, r8
0x18000abd9  mov     r15, rdx
0x18000abdc  mov     rbp, rcx
0x18000abdf  test    rcx, rcx
0x18000abe2  jz      loc_18000AD4A
0x18000abe8  test    rdx, rdx
0x18000abeb  jz      loc_18000AD4A
0x18000abf1  test    r8, r8
0x18000abf4  jz      loc_18000AD4A
0x18000abfa  mov     r14, [rsp+78h+arg_20]
0x18000ac02  test    r14, r14
0x18000ac05  jz      loc_18000AD4A
0x18000ac0b  mov     rax, [rsp+78h+arg_28]
0x18000ac13  test    rax, rax
0x18000ac16  jz      loc_18000AD4A
0x18000ac1c  xor     ebx, ebx
0x18000ac1e  mov     [r14], rbx
0x18000ac21  mov     [rax], ebx
0x18000ac23  cmp     dword ptr [r8+0Ch], 1Eh
0x18000ac28  jnz     short loc_18000AC30
0x18000ac2a  mov     dword ptr [rax], 2
0x18000ac30  mov     rax, [rdx]
0x18000ac33  mov     rcx, r15
0x18000ac36  lea     rdx, [rsp+78h+arg_0]
0x18000ac3e  mov     rax, [rax+88h]
0x18000ac45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac4a  mov     edi, eax
0x18000ac4c  test    eax, eax
0x18000ac4e  js      loc_18000ACFC
0x18000ac54  mov     eax, [rsi+8]
0x18000ac57  inc     eax
0x18000ac59  cmp     eax, [rsp+78h+arg_0]
0x18000ac60  jz      short loc_18000AC6C
0x18000ac62  mov     edi, 8000FFFFh
0x18000ac67  jmp     loc_18000ACFC
0x18000ac6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac73  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000ac78  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac7d  mov     [rsp+78h+var_40], rax
0x18000ac82  mov     rbx, rax
0x18000ac85  test    rax, rax
0x18000ac88  jz      short loc_18000ACF5
0x18000ac8a  mov     qword ptr [rax+10h], 0
0x18000ac92  xorps   xmm0, xmm0
0x18000ac95  mov     qword ptr [rax+18h], 0
0x18000ac9d  mov     dword ptr [rax+40h], 1
0x18000aca4  movups  xmmword ptr [rax+20h], xmm0
0x18000aca8  movups  xmmword ptr [rax+30h], xmm0
0x18000acac  lea     rax, ??_7CArchiveDefinitionNode@@6BICSPNode@@@; const CArchiveDefinitionNode::`vftable'{for `ICSPNode'}
0x18000acb3  mov     [rbx], rax
0x18000acb6  lea     rax, ??_7CArchiveDefinitionNode@@6BICSPNodeTransactioning@@@; const CArchiveDefinitionNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000acbd  mov     [rbx+8], rax
0x18000acc1  lock inc cs:dword_18004B4E0
0x18000acc8  test    rbx, rbx
0x18000accb  jz      short loc_18000ACF7
0x18000accd  mov     rax, [rbx]
0x18000acd0  mov     r9, rsi
0x18000acd3  mov     r8, r15
0x18000acd6  mov     rdx, rbp
0x18000acd9  mov     rcx, rbx
0x18000acdc  mov     rax, [rax+88h]
0x18000ace3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace8  mov     edi, eax
0x18000acea  test    eax, eax
0x18000acec  js      short loc_18000ACFC
0x18000acee  mov     [r14], rbx
0x18000acf1  xor     ebx, ebx
0x18000acf3  jmp     short loc_18000ACFC
0x18000acf5  xor     ebx, ebx
0x18000acf7  mov     edi, 8007000Eh
0x18000acfc  mov     eax, cs:dword_18004AE90
0x18000ad02  cmp     eax, 5
0x18000ad05  jbe     short loc_18000AD32
0x18000ad07  mov     eax, [rsi+0Ch]
0x18000ad0a  lea     rdx, byte_180040FBF
0x18000ad11  mov     dword ptr [rsp+78h+var_40], eax
0x18000ad15  lea     rax, [rsp+78h+var_48]
0x18000ad1a  mov     [rsp+78h+var_50], rax
0x18000ad1f  lea     rax, [rsp+78h+var_40]
0x18000ad24  mov     [rsp+78h+var_58], rax
0x18000ad29  mov     [rsp+78h+var_48], edi
0x18000ad2d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ad32  test    rbx, rbx
0x18000ad35  jz      short loc_18000AD46
0x18000ad37  mov     rax, [rbx]
0x18000ad3a  mov     rcx, rbx
0x18000ad3d  mov     rax, [rax+10h]
0x18000ad41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad46  mov     eax, edi
0x18000ad48  jmp     short loc_18000AD4F
0x18000ad4a  mov     eax, 80070057h
0x18000ad4f  add     rsp, 48h
0x18000ad53  pop     r15
0x18000ad55  pop     r14
0x18000ad57  pop     rdi
0x18000ad58  pop     rsi
0x18000ad59  pop     rbp
0x18000ad5a  pop     rbx
0x18000ad5b  retn
```
