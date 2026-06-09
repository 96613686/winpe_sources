# CDeviceStateNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x1800093a0`
- end: `0x180009555`
- name: `?CreateNodeInstance@CDeviceStateNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `437`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180002b88`
- `0x1800093a0`
- `0x180037010`

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
      (__int64)byte_18003ECA9,
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
0x1800093a0  mov     rax, rsp
0x1800093a3  push    rbx
0x1800093a4  push    rbp
0x1800093a5  push    rsi
0x1800093a6  push    rdi
0x1800093a7  push    r14
0x1800093a9  push    r15
0x1800093ab  sub     rsp, 48h
0x1800093af  xor     ebx, ebx
0x1800093b1  mov     dword ptr [rax+8], 0
0x1800093b8  mov     rsi, r8
0x1800093bb  mov     r15, rdx
0x1800093be  mov     rbp, rcx
0x1800093c1  test    rcx, rcx
0x1800093c4  jz      loc_1800094ED
0x1800093ca  test    rdx, rdx
0x1800093cd  jz      loc_1800094ED
0x1800093d3  test    r8, r8
0x1800093d6  jz      loc_1800094ED
0x1800093dc  mov     r14, [rsp+78h+arg_20]
0x1800093e4  test    r14, r14
0x1800093e7  jz      loc_1800094ED
0x1800093ed  mov     rax, [rsp+78h+arg_28]
0x1800093f5  test    rax, rax
0x1800093f8  jz      loc_1800094ED
0x1800093fe  mov     [r14], rbx
0x180009401  mov     [rax], ebx
0x180009403  test    r9d, r9d
0x180009406  jz      short loc_180009412
0x180009408  mov     edi, 86000011h
0x18000940d  jmp     loc_1800094F2
0x180009412  cmp     dword ptr [r8+0Ch], 13h
0x180009417  jnz     short loc_18000941F
0x180009419  mov     dword ptr [rax], 2
0x18000941f  mov     rax, [rdx]
0x180009422  mov     rcx, r15
0x180009425  lea     rdx, [rsp+78h+arg_0]
0x18000942d  mov     rax, [rax+88h]
0x180009434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009439  mov     edi, eax
0x18000943b  test    eax, eax
0x18000943d  js      loc_1800094F2
0x180009443  mov     eax, [rsi+8]
0x180009446  inc     eax
0x180009448  cmp     eax, [rsp+78h+arg_0]
0x18000944f  jz      short loc_18000945B
0x180009451  mov     edi, 8000FFFFh
0x180009456  jmp     loc_1800094F2
0x18000945b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009462  mov     ecx, 48h ; 'H'; unsigned __int64
0x180009467  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000946c  mov     [rsp+78h+var_40], rax
0x180009471  mov     rbx, rax
0x180009474  test    rax, rax
0x180009477  jz      short loc_1800094E4
0x180009479  mov     qword ptr [rax+10h], 0
0x180009481  xorps   xmm0, xmm0
0x180009484  mov     qword ptr [rax+18h], 0
0x18000948c  mov     dword ptr [rax+40h], 1
0x180009493  movups  xmmword ptr [rax+20h], xmm0
0x180009497  movups  xmmword ptr [rax+30h], xmm0
0x18000949b  lea     rax, ??_7CDeviceStateNode@@6BICSPNode@@@; const CDeviceStateNode::`vftable'{for `ICSPNode'}
0x1800094a2  mov     [rbx], rax
0x1800094a5  lea     rax, ??_7CDeviceStateNode@@6BICSPNodeTransactioning@@@; const CDeviceStateNode::`vftable'{for `ICSPNodeTransactioning'}
0x1800094ac  mov     [rbx+8], rax
0x1800094b0  lock inc cs:dword_1800494E0
0x1800094b7  test    rbx, rbx
0x1800094ba  jz      short loc_1800094E6
0x1800094bc  mov     rax, [rbx]
0x1800094bf  mov     r9, rsi
0x1800094c2  mov     r8, r15
0x1800094c5  mov     rdx, rbp
0x1800094c8  mov     rcx, rbx
0x1800094cb  mov     rax, [rax+88h]
0x1800094d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d7  mov     edi, eax
0x1800094d9  test    eax, eax
0x1800094db  js      short loc_1800094F2
0x1800094dd  mov     [r14], rbx
0x1800094e0  xor     ebx, ebx
0x1800094e2  jmp     short loc_1800094F2
0x1800094e4  xor     ebx, ebx
0x1800094e6  mov     edi, 8007000Eh
0x1800094eb  jmp     short loc_1800094F2
0x1800094ed  mov     edi, 80070057h
0x1800094f2  mov     eax, cs:dword_180048E90
0x1800094f8  cmp     eax, 5
0x1800094fb  jbe     short loc_180009532
0x1800094fd  mov     [rsp+78h+var_48], edi
0x180009501  test    rsi, rsi
0x180009504  jz      short loc_18000950B
0x180009506  mov     eax, [rsi+0Ch]
0x180009509  jmp     short loc_18000950E
0x18000950b  or      eax, 0FFFFFFFFh
0x18000950e  mov     dword ptr [rsp+78h+var_40], eax
0x180009512  lea     rdx, byte_18003ECA9
0x180009519  lea     rax, [rsp+78h+var_48]
0x18000951e  mov     [rsp+78h+var_50], rax
0x180009523  lea     rax, [rsp+78h+var_40]
0x180009528  mov     [rsp+78h+var_58], rax
0x18000952d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009532  test    rbx, rbx
0x180009535  jz      short loc_180009546
0x180009537  mov     rax, [rbx]
0x18000953a  mov     rcx, rbx
0x18000953d  mov     rax, [rax+10h]
0x180009541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009546  mov     eax, edi
0x180009548  add     rsp, 48h
0x18000954c  pop     r15
0x18000954e  pop     r14
0x180009550  pop     rdi
0x180009551  pop     rsi
0x180009552  pop     rbp
0x180009553  pop     rbx
0x180009554  retn
```
