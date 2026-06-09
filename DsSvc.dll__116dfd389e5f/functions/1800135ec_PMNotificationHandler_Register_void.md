# PMNotificationHandler::Register(void)

- ea: `0x1800135ec`
- end: `0x1800136d7`
- name: `?Register@PMNotificationHandler@@QEAAJXZ`
- size: `235`
- prototype: `__int64 __fastcall(PMNotificationHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d21c`

## callees

- `0x180002ac8`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c9f4`
- `0x1800135ec`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013625`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013625`

## pseudocode

```c
__int64 __fastcall PMNotificationHandler::Register(PMNotificationHandler *this)
{
  int v1; // ebx
  _QWORD *v3; // r14
  HRESULT Instance; // eax
  void **v5; // rcx
  struct IUnknown *v6; // rax
  int *v7; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-38h]

  v1 = 0;
  if ( !*(_DWORD *)this )
  {
    v3 = (_QWORD *)((char *)this + 8);
    if ( *((_QWORD *)this + 1) )
      goto LABEL_6;
    Instance = CoCreateInstance(&CLSID_PMNotifications, 0, 0x17u, &IID_IPMNotificationManager, (LPVOID *)this + 1);
    if ( Instance != -2147221164 )
      v1 = Instance;
    if ( v1 >= 0 )
    {
LABEL_6:
      v6 = (struct IUnknown *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
      {
        v5 = &DSNotificationSink::`vftable';
        LODWORD(v6[1].lpVtbl) = 0;
        v6->lpVtbl = (struct IUnknownVtbl *)&DSNotificationSink::`vftable';
      }
      if ( *((struct IUnknown **)this + 2) != v6 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 2, v6);
      if ( *((_QWORD *)this + 2) )
      {
        if ( !*v3 || (v1 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, 1), v1 >= 0) )
        {
          *(_DWORD *)this = 1;
          return (unsigned int)v1;
        }
      }
      else
      {
        v1 = -2147024809;
      }
    }
    v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)v5);
    LODWORD(ppv) = v1;
    DSLogger::LogError((DSLogger *)v7, L"PMNotificationHandler::Register", 76, L"hr=0x%x.", ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800135ec  push    rbx
0x1800135ee  push    rsi
0x1800135ef  push    rdi
0x1800135f0  push    r14
0x1800135f2  sub     rsp, 38h
0x1800135f6  xor     ebx, ebx
0x1800135f8  mov     rdi, rcx
0x1800135fb  cmp     [rcx], ebx
0x1800135fd  jnz     loc_1800136CB
0x180013603  lea     r14, [rcx+8]
0x180013607  cmp     [r14], rbx
0x18001360a  jnz     short loc_180013637
0x18001360c  lea     r9, IID_IPMNotificationManager; riid
0x180013613  mov     [rsp+58h+ppv], r14; ppv
0x180013618  xor     edx, edx; pUnkOuter
0x18001361a  lea     r8d, [rbx+17h]; dwClsContext
0x18001361e  lea     rcx, CLSID_PMNotifications; rclsid
0x180013625  call    cs:__imp_CoCreateInstance
0x18001362b  cmp     eax, 80040154h
0x180013630  cmovnz  ebx, eax
0x180013633  test    ebx, ebx
0x180013635  js      short loc_1800136A2
0x180013637  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001363e  mov     ecx, 10h; unsigned __int64
0x180013643  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013648  test    rax, rax
0x18001364b  jz      short loc_18001365E
0x18001364d  lea     rcx, ??_7DSNotificationSink@@6B@; const DSNotificationSink::`vftable'
0x180013654  mov     dword ptr [rax+8], 0
0x18001365b  mov     [rax], rcx
0x18001365e  lea     rsi, [rdi+10h]
0x180013662  cmp     [rsi], rax
0x180013665  jz      short loc_180013672
0x180013667  mov     rdx, rax; struct IUnknown *
0x18001366a  mov     rcx, rsi; struct IUnknown **
0x18001366d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180013672  mov     r8, [rsi]
0x180013675  test    r8, r8
0x180013678  jnz     short loc_180013681
0x18001367a  mov     ebx, 80070057h
0x18001367f  jmp     short loc_1800136A2
0x180013681  mov     rcx, [r14]
0x180013684  mov     esi, 1
0x180013689  test    rcx, rcx
0x18001368c  jz      short loc_1800136C9
0x18001368e  mov     rax, [rcx]
0x180013691  mov     edx, esi
0x180013693  mov     rax, [rax+18h]
0x180013697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001369c  mov     ebx, eax
0x18001369e  test    eax, eax
0x1800136a0  jns     short loc_1800136C9
0x1800136a2  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800136a7  lea     r9, aHr0xX; "hr=0x%x."
0x1800136ae  mov     dword ptr [rsp+58h+ppv], ebx
0x1800136b2  mov     r8d, 4Ch ; 'L'; unsigned int
0x1800136b8  lea     rdx, aPmnotification; "PMNotificationHandler::Register"
0x1800136bf  mov     rcx, rax; this
0x1800136c2  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800136c7  jmp     short loc_1800136CB
0x1800136c9  mov     [rdi], esi
0x1800136cb  mov     eax, ebx
0x1800136cd  add     rsp, 38h
0x1800136d1  pop     r14
0x1800136d3  pop     rdi
0x1800136d4  pop     rsi
0x1800136d5  pop     rbx
0x1800136d6  retn
```
