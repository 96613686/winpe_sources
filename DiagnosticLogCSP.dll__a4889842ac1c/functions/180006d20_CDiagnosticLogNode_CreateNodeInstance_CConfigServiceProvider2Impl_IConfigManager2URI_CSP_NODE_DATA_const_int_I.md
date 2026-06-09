# CDiagnosticLogNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180006d20`
- end: `0x180006ed0`
- name: `?CreateNodeInstance@CDiagnosticLogNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x180006d20`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CDiagnosticLogNode::CreateNodeInstance(
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
    if ( (_DWORD)a4 || !*((_DWORD *)a3 + 6) )
    {
      v12 = -2046820335;
    }
    else
    {
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
            *v13 = &CDiagnosticLogNode::`vftable'{for `ICSPNode'};
            v13[1] = &CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'};
            _InterlockedIncrement(&dword_1800494E0);
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v16 = v12;
    if ( a3 )
      v14 = *((_DWORD *)a3 + 3);
    else
      v14 = -1;
    LODWORD(v17) = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&byte_18003E7F7,
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
0x180006d20  mov     r11, rsp
0x180006d23  push    rbx
0x180006d24  push    rbp
0x180006d25  push    rsi
0x180006d26  push    rdi
0x180006d27  push    r14
0x180006d29  push    r15
0x180006d2b  sub     rsp, 48h
0x180006d2f  xor     ebx, ebx
0x180006d31  mov     dword ptr [r11+8], 0
0x180006d39  mov     rsi, r8
0x180006d3c  mov     r15, rdx
0x180006d3f  mov     rbp, rcx
0x180006d42  test    rcx, rcx
0x180006d45  jz      loc_180006E68
0x180006d4b  test    rdx, rdx
0x180006d4e  jz      loc_180006E68
0x180006d54  test    r8, r8
0x180006d57  jz      loc_180006E68
0x180006d5d  mov     r14, [rsp+78h+arg_20]
0x180006d65  test    r14, r14
0x180006d68  jz      loc_180006E68
0x180006d6e  mov     rax, [rsp+78h+arg_28]
0x180006d76  test    rax, rax
0x180006d79  jz      loc_180006E68
0x180006d7f  mov     [r14], rbx
0x180006d82  mov     [rax], ebx
0x180006d84  test    r9d, r9d
0x180006d87  jnz     loc_180006E61
0x180006d8d  cmp     [r8+18h], ebx
0x180006d91  jz      loc_180006E61
0x180006d97  mov     rax, [rdx]
0x180006d9a  mov     rcx, r15
0x180006d9d  lea     rdx, [r11+8]
0x180006da1  mov     rax, [rax+88h]
0x180006da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dad  mov     edi, eax
0x180006daf  test    eax, eax
0x180006db1  js      loc_180006E6D
0x180006db7  mov     eax, [rsi+8]
0x180006dba  inc     eax
0x180006dbc  cmp     eax, [rsp+78h+arg_0]
0x180006dc3  jz      short loc_180006DCF
0x180006dc5  mov     edi, 8000FFFFh
0x180006dca  jmp     loc_180006E6D
0x180006dcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006dd6  mov     ecx, 48h ; 'H'; unsigned __int64
0x180006ddb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006de0  mov     [rsp+78h+var_40], rax
0x180006de5  mov     rbx, rax
0x180006de8  test    rax, rax
0x180006deb  jz      short loc_180006E58
0x180006ded  mov     qword ptr [rax+10h], 0
0x180006df5  xorps   xmm0, xmm0
0x180006df8  mov     qword ptr [rax+18h], 0
0x180006e00  mov     dword ptr [rax+40h], 1
0x180006e07  movups  xmmword ptr [rax+20h], xmm0
0x180006e0b  movups  xmmword ptr [rax+30h], xmm0
0x180006e0f  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNode@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNode'}
0x180006e16  mov     [rbx], rax
0x180006e19  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNodeTransactioning@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'}
0x180006e20  mov     [rbx+8], rax
0x180006e24  lock inc cs:dword_1800494E0
0x180006e2b  test    rbx, rbx
0x180006e2e  jz      short loc_180006E5A
0x180006e30  mov     rax, [rbx]
0x180006e33  mov     r9, rsi
0x180006e36  mov     r8, r15
0x180006e39  mov     rdx, rbp
0x180006e3c  mov     rcx, rbx
0x180006e3f  mov     rax, [rax+88h]
0x180006e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4b  mov     edi, eax
0x180006e4d  test    eax, eax
0x180006e4f  js      short loc_180006E6D
0x180006e51  mov     [r14], rbx
0x180006e54  xor     ebx, ebx
0x180006e56  jmp     short loc_180006E6D
0x180006e58  xor     ebx, ebx
0x180006e5a  mov     edi, 8007000Eh
0x180006e5f  jmp     short loc_180006E6D
0x180006e61  mov     edi, 86000011h
0x180006e66  jmp     short loc_180006E6D
0x180006e68  mov     edi, 80070057h
0x180006e6d  mov     eax, cs:dword_180048E90
0x180006e73  cmp     eax, 5
0x180006e76  jbe     short loc_180006EAD
0x180006e78  mov     [rsp+78h+var_48], edi
0x180006e7c  test    rsi, rsi
0x180006e7f  jz      short loc_180006E86
0x180006e81  mov     eax, [rsi+0Ch]
0x180006e84  jmp     short loc_180006E89
0x180006e86  or      eax, 0FFFFFFFFh
0x180006e89  mov     dword ptr [rsp+78h+var_40], eax
0x180006e8d  lea     rdx, byte_18003E7F7
0x180006e94  lea     rax, [rsp+78h+var_48]
0x180006e99  mov     [rsp+78h+var_50], rax
0x180006e9e  lea     rax, [rsp+78h+var_40]
0x180006ea3  mov     [rsp+78h+var_58], rax
0x180006ea8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006ead  test    rbx, rbx
0x180006eb0  jz      short loc_180006EC1
0x180006eb2  mov     rax, [rbx]
0x180006eb5  mov     rcx, rbx
0x180006eb8  mov     rax, [rax+10h]
0x180006ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec1  mov     eax, edi
0x180006ec3  add     rsp, 48h
0x180006ec7  pop     r15
0x180006ec9  pop     r14
0x180006ecb  pop     rdi
0x180006ecc  pop     rsi
0x180006ecd  pop     rbp
0x180006ece  pop     rbx
0x180006ecf  retn
```
