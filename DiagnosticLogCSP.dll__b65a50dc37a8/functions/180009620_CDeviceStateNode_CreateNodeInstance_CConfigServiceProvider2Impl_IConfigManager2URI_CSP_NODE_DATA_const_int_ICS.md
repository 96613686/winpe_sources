# CDeviceStateNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180009620`
- end: `0x1800097d6`
- name: `?CreateNodeInstance@CDeviceStateNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x180009620`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CDeviceStateNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v6; // rbx
  struct ICSPNode **v10; // r14
  unsigned int *v11; // rax
  int v12; // edi
  _QWORD *v13; // rax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-40h] BYREF
  int v18; // [rsp+80h] [rbp+8h] BYREF

  v6 = 0;
  v18 = 0;
  if ( a1 && a2 && a3 && (v10 = a5) != 0 && (v11 = a6) != 0 )
  {
    *a5 = 0;
    *v11 = 0;
    if ( (_DWORD)a4 )
    {
      v12 = -2046820335;
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) == 19 )
        *v11 = 2;
      v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v18);
      if ( v12 >= 0 )
      {
        if ( *((_DWORD *)a3 + 2) + 1 == v18 )
        {
          v13 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
          v17 = v13;
          v6 = (struct ICSPNode *)v13;
          if ( v13 )
          {
            v13[2] = 0;
            v13[3] = 0;
            *((_DWORD *)v13 + 16) = 1;
            *((_OWORD *)v13 + 2) = 0;
            *((_OWORD *)v13 + 3) = 0;
            *v13 = &CDeviceStateNode::`vftable'{for `ICSPNode'};
            v13[1] = &CDeviceStateNode::`vftable'{for `ICSPNodeTransactioning'};
            _InterlockedIncrement(&dword_18004B4E0);
            v12 = (*(__int64 (__fastcall **)(_QWORD *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*v13 + 136LL))(
                    v13,
                    a1,
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
        }
        else
        {
          v12 = -2147418113;
        }
      }
    }
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v16 = v12;
    if ( a3 )
      v14 = *((_DWORD *)a3 + 3);
    else
      v14 = -1;
    LODWORD(v17) = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (unsigned __int8 *)byte_180040CA9,
      (__int64)a3,
      a4,
      (__int64)&v17,
      (__int64)&v16);
  }
  if ( v6 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009620  mov     rax, rsp
0x180009623  push    rbx
0x180009624  push    rbp
0x180009625  push    rsi
0x180009626  push    rdi
0x180009627  push    r14
0x180009629  push    r15
0x18000962b  sub     rsp, 48h
0x18000962f  xor     ebx, ebx
0x180009631  mov     dword ptr [rax+8], 0
0x180009638  mov     rsi, r8
0x18000963b  mov     r15, rdx
0x18000963e  mov     rbp, rcx
0x180009641  test    rcx, rcx
0x180009644  jz      loc_18000976D
0x18000964a  test    rdx, rdx
0x18000964d  jz      loc_18000976D
0x180009653  test    r8, r8
0x180009656  jz      loc_18000976D
0x18000965c  mov     r14, [rsp+78h+arg_20]
0x180009664  test    r14, r14
0x180009667  jz      loc_18000976D
0x18000966d  mov     rax, [rsp+78h+arg_28]
0x180009675  test    rax, rax
0x180009678  jz      loc_18000976D
0x18000967e  mov     [r14], rbx
0x180009681  mov     [rax], ebx
0x180009683  test    r9d, r9d
0x180009686  jz      short loc_180009692
0x180009688  mov     edi, 86000011h
0x18000968d  jmp     loc_180009772
0x180009692  cmp     dword ptr [r8+0Ch], 13h
0x180009697  jnz     short loc_18000969F
0x180009699  mov     dword ptr [rax], 2
0x18000969f  mov     rax, [rdx]
0x1800096a2  mov     rcx, r15
0x1800096a5  lea     rdx, [rsp+78h+arg_0]
0x1800096ad  mov     rax, [rax+88h]
0x1800096b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b9  mov     edi, eax
0x1800096bb  test    eax, eax
0x1800096bd  js      loc_180009772
0x1800096c3  mov     eax, [rsi+8]
0x1800096c6  inc     eax
0x1800096c8  cmp     eax, [rsp+78h+arg_0]
0x1800096cf  jz      short loc_1800096DB
0x1800096d1  mov     edi, 8000FFFFh
0x1800096d6  jmp     loc_180009772
0x1800096db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800096e2  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800096e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800096ec  mov     [rsp+78h+var_40], rax
0x1800096f1  mov     rbx, rax
0x1800096f4  test    rax, rax
0x1800096f7  jz      short loc_180009764
0x1800096f9  mov     qword ptr [rax+10h], 0
0x180009701  xorps   xmm0, xmm0
0x180009704  mov     qword ptr [rax+18h], 0
0x18000970c  mov     dword ptr [rax+40h], 1
0x180009713  movups  xmmword ptr [rax+20h], xmm0
0x180009717  movups  xmmword ptr [rax+30h], xmm0
0x18000971b  lea     rax, ??_7CDeviceStateNode@@6BICSPNode@@@; const CDeviceStateNode::`vftable'{for `ICSPNode'}
0x180009722  mov     [rbx], rax
0x180009725  lea     rax, ??_7CDeviceStateNode@@6BICSPNodeTransactioning@@@; const CDeviceStateNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000972c  mov     [rbx+8], rax
0x180009730  lock inc cs:dword_18004B4E0
0x180009737  test    rbx, rbx
0x18000973a  jz      short loc_180009766
0x18000973c  mov     rax, [rbx]
0x18000973f  mov     r9, rsi
0x180009742  mov     r8, r15
0x180009745  mov     rdx, rbp
0x180009748  mov     rcx, rbx
0x18000974b  mov     rax, [rax+88h]
0x180009752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009757  mov     edi, eax
0x180009759  test    eax, eax
0x18000975b  js      short loc_180009772
0x18000975d  mov     [r14], rbx
0x180009760  xor     ebx, ebx
0x180009762  jmp     short loc_180009772
0x180009764  xor     ebx, ebx
0x180009766  mov     edi, 8007000Eh
0x18000976b  jmp     short loc_180009772
0x18000976d  mov     edi, 80070057h
0x180009772  mov     eax, cs:dword_18004AE90
0x180009778  cmp     eax, 5
0x18000977b  jbe     short loc_1800097B2
0x18000977d  mov     [rsp+78h+var_48], edi
0x180009781  test    rsi, rsi
0x180009784  jz      short loc_18000978B
0x180009786  mov     eax, [rsi+0Ch]
0x180009789  jmp     short loc_18000978E
0x18000978b  or      eax, 0FFFFFFFFh
0x18000978e  mov     dword ptr [rsp+78h+var_40], eax
0x180009792  lea     rdx, byte_180040CA9
0x180009799  lea     rax, [rsp+78h+var_48]
0x18000979e  mov     [rsp+78h+var_50], rax
0x1800097a3  lea     rax, [rsp+78h+var_40]
0x1800097a8  mov     [rsp+78h+var_58], rax
0x1800097ad  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800097b2  test    rbx, rbx
0x1800097b5  jz      short loc_1800097C6
0x1800097b7  mov     rax, [rbx]
0x1800097ba  mov     rcx, rbx
0x1800097bd  mov     rax, [rax+10h]
0x1800097c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097c6  mov     eax, edi
0x1800097c8  add     rsp, 48h
0x1800097cc  pop     r15
0x1800097ce  pop     r14
0x1800097d0  pop     rdi
0x1800097d1  pop     rsi
0x1800097d2  pop     rbp
0x1800097d3  pop     rbx
0x1800097d4  retn
```
