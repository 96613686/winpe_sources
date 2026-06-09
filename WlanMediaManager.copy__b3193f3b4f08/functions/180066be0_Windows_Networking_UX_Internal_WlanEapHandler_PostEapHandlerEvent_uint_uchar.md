# Windows::Networking::UX::Internal::WlanEapHandler::PostEapHandlerEvent(uint,uchar *)

- ea: `0x180066be0`
- end: `0x180066d5e`
- name: `?PostEapHandlerEvent@WlanEapHandler@Internal@UX@Networking@Windows@@UEAAJIPEAE@Z`
- size: `382`
- prototype: `int(Windows::Networking::UX::Internal::WlanEapHandler *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800043bc`
- `0x180006249`
- `0x1800097b4`
- `0x18000de4c`
- `0x180012178`
- `0x18001d4d4`
- `0x180066be0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ca0`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanEapHandler::PostEapHandlerEvent(
        Windows::Networking::UX::Internal::WlanEapHandler *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  SIZE_T v4; // rsi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  _BYTE *v8; // rax
  _BYTE *v9; // rcx
  _BYTE *i; // rdx
  void *v11; // rax
  void *v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ebx
  _DWORD *v17; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  _DWORD *v19; // [rsp+88h] [rbp+20h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5a64d569884a399185adf6485bd90084_Traceguids);
  v6 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v6[2] = 16;
    v6[4] = 0;
    *(_QWORD *)v6 = &Windows::Networking::UX::Internal::WlanEapHandlerEvent::`vftable';
    *((_QWORD *)v6 + 3) = 0;
    v19 = v6;
    v8 = CoTaskMemAlloc(v4);
    v9 = v8;
    if ( v8 )
    {
      for ( i = &v8[v4]; v8 != i; ++v8 )
        *v8 = 0;
    }
    v11 = (void *)*((_QWORD *)v7 + 3);
    *((_QWORD *)v7 + 3) = v9;
    if ( v11 )
      CoTaskMemFree(v11);
    v12 = (void *)*((_QWORD *)v7 + 3);
    if ( !v12 )
    {
      v15 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\statemachine\\lib\\wlanstatemachine.cpp",
        (const char *)0x8007000ELL,
        (int)v17);
      goto LABEL_17;
    }
    memcpy_0(v12, a3, v4);
    v7[4] = v4;
    v13 = (__int64 *)*((_QWORD *)this + 4);
    v19 = 0;
    v14 = *v13;
    v17 = v7;
    v15 = (*(__int64 (__fastcall **)(__int64 *, _DWORD **))(v14 + 48))(v13, &v17);
  }
  else
  {
    v15 = -2147024882;
    v19 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5a64d569884a399185adf6485bd90084_Traceguids, v15);
LABEL_17:
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v19);
  return v15;
}

```

## disassembly

```asm
0x180066be0  push    rbx
0x180066be2  push    rbp
0x180066be3  push    rsi
0x180066be4  push    rdi
0x180066be5  push    r12
0x180066be7  push    r14
0x180066be9  sub     rsp, 38h
0x180066bed  mov     rbp, r8
0x180066bf0  mov     esi, edx
0x180066bf2  mov     r14, rcx
0x180066bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180066bfc  lea     r12, WPP_GLOBAL_Control
0x180066c03  cmp     rcx, r12
0x180066c06  jz      short loc_180066C23
0x180066c08  test    byte ptr [rcx+1Ch], 8
0x180066c0c  jz      short loc_180066C23
0x180066c0e  mov     rcx, [rcx+10h]
0x180066c12  lea     r8, WPP_5a64d569884a399185adf6485bd90084_Traceguids
0x180066c19  mov     edx, 0Ah
0x180066c1e  call    WPP_SF_
0x180066c23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066c2a  mov     ecx, 20h ; ' '; unsigned __int64
0x180066c2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180066c34  mov     rbx, rax
0x180066c37  test    rax, rax
0x180066c3a  jz      loc_180066D07
0x180066c40  mov     dword ptr [rax+8], 10h
0x180066c47  mov     rcx, rsi; cb
0x180066c4a  lea     rax, ??_7WlanEapHandlerEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanEapHandlerEvent::`vftable'
0x180066c51  mov     dword ptr [rbx+10h], 0
0x180066c58  mov     [rbx], rax
0x180066c5b  mov     qword ptr [rbx+18h], 0
0x180066c63  mov     [rsp+68h+arg_18], rbx
0x180066c6b  call    cs:__imp_CoTaskMemAlloc
0x180066c71  mov     rcx, rax
0x180066c74  test    rax, rax
0x180066c77  jz      short loc_180066C90
0x180066c79  lea     rdx, [rsi+rax]
0x180066c7d  cmp     rax, rdx
0x180066c80  jz      short loc_180066C90
0x180066c82  xor     r8d, r8d
0x180066c85  mov     [rax], r8b
0x180066c88  inc     rax
0x180066c8b  cmp     rax, rdx
0x180066c8e  jnz     short loc_180066C82
0x180066c90  mov     rax, [rbx+18h]
0x180066c94  mov     [rbx+18h], rcx
0x180066c98  test    rax, rax
0x180066c9b  jz      short loc_180066CA6
0x180066c9d  mov     rcx, rax; pv
0x180066ca0  call    cs:__imp_CoTaskMemFree
0x180066ca6  mov     rcx, [rbx+18h]; void *
0x180066caa  test    rcx, rcx
0x180066cad  jz      short loc_180066CE7
0x180066caf  mov     r8, rsi; Size
0x180066cb2  mov     rdx, rbp; Src
0x180066cb5  call    memcpy_0
0x180066cba  mov     [rbx+10h], esi
0x180066cbd  lea     rdx, [rsp+68h+var_48]
0x180066cc2  mov     rcx, [r14+20h]
0x180066cc6  mov     [rsp+68h+arg_18], 0
0x180066cd2  mov     rax, [rcx]
0x180066cd5  mov     [rsp+68h+var_48], rbx
0x180066cda  mov     rax, [rax+30h]
0x180066cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ce3  mov     ebx, eax
0x180066ce5  jmp     short loc_180066D18
0x180066ce7  mov     rcx, [rsp+68h]; this
0x180066cec  lea     r8, aOnecoreuapNetU_6; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180066cf3  mov     ebx, 8007000Eh
0x180066cf8  mov     edx, 39h ; '9'; void *
0x180066cfd  mov     r9d, ebx; char *
0x180066d00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066d05  jmp     short loc_180066D42
0x180066d07  mov     ebx, 8007000Eh
0x180066d0c  mov     [rsp+68h+arg_18], 0
0x180066d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d1f  cmp     rcx, r12
0x180066d22  jz      short loc_180066D42
0x180066d24  test    byte ptr [rcx+1Ch], 8
0x180066d28  jz      short loc_180066D42
0x180066d2a  mov     rcx, [rcx+10h]
0x180066d2e  lea     r8, WPP_5a64d569884a399185adf6485bd90084_Traceguids
0x180066d35  mov     edx, 0Bh
0x180066d3a  mov     r9d, ebx
0x180066d3d  call    WPP_SF_d
0x180066d42  lea     rcx, [rsp+68h+arg_18]
0x180066d4a  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x180066d4f  mov     eax, ebx
0x180066d51  add     rsp, 38h
0x180066d55  pop     r14
0x180066d57  pop     r12
0x180066d59  pop     rdi
0x180066d5a  pop     rsi
0x180066d5b  pop     rbp
0x180066d5c  pop     rbx
0x180066d5d  retn
```
