# CDiagnosticLogNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180006de0`
- end: `0x180006f91`
- name: `?CreateNodeInstance@CDiagnosticLogNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x180006de0`
- `0x180039010`

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
      (unsigned __int8 *)byte_1800407F7,
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
0x180006de0  mov     r11, rsp
0x180006de3  push    rbx
0x180006de4  push    rbp
0x180006de5  push    rsi
0x180006de6  push    rdi
0x180006de7  push    r14
0x180006de9  push    r15
0x180006deb  sub     rsp, 48h
0x180006def  xor     ebx, ebx
0x180006df1  mov     dword ptr [r11+8], 0
0x180006df9  mov     rsi, r8
0x180006dfc  mov     r15, rdx
0x180006dff  mov     rbp, rcx
0x180006e02  test    rcx, rcx
0x180006e05  jz      loc_180006F28
0x180006e0b  test    rdx, rdx
0x180006e0e  jz      loc_180006F28
0x180006e14  test    r8, r8
0x180006e17  jz      loc_180006F28
0x180006e1d  mov     r14, [rsp+78h+arg_20]
0x180006e25  test    r14, r14
0x180006e28  jz      loc_180006F28
0x180006e2e  mov     rax, [rsp+78h+arg_28]
0x180006e36  test    rax, rax
0x180006e39  jz      loc_180006F28
0x180006e3f  mov     [r14], rbx
0x180006e42  mov     [rax], ebx
0x180006e44  test    r9d, r9d
0x180006e47  jnz     loc_180006F21
0x180006e4d  cmp     [r8+18h], ebx
0x180006e51  jz      loc_180006F21
0x180006e57  mov     rax, [rdx]
0x180006e5a  mov     rcx, r15
0x180006e5d  lea     rdx, [r11+8]
0x180006e61  mov     rax, [rax+88h]
0x180006e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6d  mov     edi, eax
0x180006e6f  test    eax, eax
0x180006e71  js      loc_180006F2D
0x180006e77  mov     eax, [rsi+8]
0x180006e7a  inc     eax
0x180006e7c  cmp     eax, [rsp+78h+arg_0]
0x180006e83  jz      short loc_180006E8F
0x180006e85  mov     edi, 8000FFFFh
0x180006e8a  jmp     loc_180006F2D
0x180006e8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006e96  mov     ecx, 48h ; 'H'; unsigned __int64
0x180006e9b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006ea0  mov     [rsp+78h+var_40], rax
0x180006ea5  mov     rbx, rax
0x180006ea8  test    rax, rax
0x180006eab  jz      short loc_180006F18
0x180006ead  mov     qword ptr [rax+10h], 0
0x180006eb5  xorps   xmm0, xmm0
0x180006eb8  mov     qword ptr [rax+18h], 0
0x180006ec0  mov     dword ptr [rax+40h], 1
0x180006ec7  movups  xmmword ptr [rax+20h], xmm0
0x180006ecb  movups  xmmword ptr [rax+30h], xmm0
0x180006ecf  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNode@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNode'}
0x180006ed6  mov     [rbx], rax
0x180006ed9  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNodeTransactioning@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'}
0x180006ee0  mov     [rbx+8], rax
0x180006ee4  lock inc cs:dword_18004B4E0
0x180006eeb  test    rbx, rbx
0x180006eee  jz      short loc_180006F1A
0x180006ef0  mov     rax, [rbx]
0x180006ef3  mov     r9, rsi
0x180006ef6  mov     r8, r15
0x180006ef9  mov     rdx, rbp
0x180006efc  mov     rcx, rbx
0x180006eff  mov     rax, [rax+88h]
0x180006f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f0b  mov     edi, eax
0x180006f0d  test    eax, eax
0x180006f0f  js      short loc_180006F2D
0x180006f11  mov     [r14], rbx
0x180006f14  xor     ebx, ebx
0x180006f16  jmp     short loc_180006F2D
0x180006f18  xor     ebx, ebx
0x180006f1a  mov     edi, 8007000Eh
0x180006f1f  jmp     short loc_180006F2D
0x180006f21  mov     edi, 86000011h
0x180006f26  jmp     short loc_180006F2D
0x180006f28  mov     edi, 80070057h
0x180006f2d  mov     eax, cs:dword_18004AE90
0x180006f33  cmp     eax, 5
0x180006f36  jbe     short loc_180006F6D
0x180006f38  mov     [rsp+78h+var_48], edi
0x180006f3c  test    rsi, rsi
0x180006f3f  jz      short loc_180006F46
0x180006f41  mov     eax, [rsi+0Ch]
0x180006f44  jmp     short loc_180006F49
0x180006f46  or      eax, 0FFFFFFFFh
0x180006f49  mov     dword ptr [rsp+78h+var_40], eax
0x180006f4d  lea     rdx, byte_1800407F7
0x180006f54  lea     rax, [rsp+78h+var_48]
0x180006f59  mov     [rsp+78h+var_50], rax
0x180006f5e  lea     rax, [rsp+78h+var_40]
0x180006f63  mov     [rsp+78h+var_58], rax
0x180006f68  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006f6d  test    rbx, rbx
0x180006f70  jz      short loc_180006F81
0x180006f72  mov     rax, [rbx]
0x180006f75  mov     rcx, rbx
0x180006f78  mov     rax, [rax+10h]
0x180006f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f81  mov     eax, edi
0x180006f83  add     rsp, 48h
0x180006f87  pop     r15
0x180006f89  pop     r14
0x180006f8b  pop     rdi
0x180006f8c  pop     rsi
0x180006f8d  pop     rbp
0x180006f8e  pop     rbx
0x180006f8f  retn
```
