# DdcCommandHandlerDesktopFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002880`
- end: `0x1800029cb`
- name: `?CreateInstance@DdcCommandHandlerDesktopFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktopFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800016d4`
- `0x1800026ac`
- `0x180002880`
- `0x18000c010`

## string_xrefs

- `0x18000296a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`
- `0x1800029b1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`
- `0x18000299d`: `CPR(pCommandHandler)`
- `0x18000295b`: `CHR(pCommandHandler->QueryInterface(riid, ppvObject))`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktopFactory::CreateInstance(
        DdcCommandHandlerDesktopFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // edi
  int v8; // edx
  int v9; // ecx
  _DWORD *v10; // rbx
  volatile signed __int32 *v11; // rax
  int v12; // edx
  int v13; // ecx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      v7 = -2147221232;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)this,
          (_DWORD)a2,
          -2147221232,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomm"
                        "andhandlerdesktop.cpp",
          110,
          (__int64)"CBR(pUnkOuter == nullptr)");
    }
    else
    {
      v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 )
      {
        v11 = (volatile signed __int32 *)*((_QWORD *)this + 2);
        *(_QWORD *)v10 = &DdcCommandHandlerDesktop::`vftable';
        v10[2] = 1;
        *((_QWORD *)v10 + 2) = v11;
        _InterlockedIncrement(v11);
        v7 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v10)(v10, a3, a4);
        if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v13,
            v12,
            v7,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcco"
                          "mmandhandlerdesktop.cpp",
            115,
            (__int64)"CHR(pCommandHandler->QueryInterface(riid, ppvObject))");
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else
      {
        v7 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcco"
                          "mmandhandlerdesktop.cpp",
            114,
            (__int64)"CPR(pCommandHandler)");
      }
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        106,
        (__int64)"CPR(ppvObject)");
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002880  push    rbx
0x180002882  push    rbp
0x180002883  push    rsi
0x180002884  push    rdi
0x180002885  sub     rsp, 38h
0x180002889  mov     rdi, r9
0x18000288c  mov     rbp, r8
0x18000288f  mov     rsi, rcx
0x180002892  test    r9, r9
0x180002895  jnz     short loc_1800028C2
0x180002897  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000289e  mov     edi, 80070057h
0x1800028a3  jz      loc_1800029C0
0x1800028a9  lea     rax, aCprPpvobject; "CPR(ppvObject)"
0x1800028b0  mov     [rsp+58h+var_30], rax
0x1800028b5  mov     [rsp+58h+var_38], 6Ah ; 'j'
0x1800028bd  jmp     loc_1800029B1
0x1800028c2  mov     qword ptr [r9], 0
0x1800028c9  test    rdx, rdx
0x1800028cc  jz      short loc_1800028F9
0x1800028ce  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800028d5  mov     edi, 80040110h
0x1800028da  jz      loc_1800029C0
0x1800028e0  lea     rax, aCbrPunkouterNu; "CBR(pUnkOuter == nullptr)"
0x1800028e7  mov     [rsp+58h+var_30], rax
0x1800028ec  mov     [rsp+58h+var_38], 6Eh ; 'n'
0x1800028f4  jmp     loc_1800029B1
0x1800028f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002900  mov     ecx, 18h; unsigned __int64
0x180002905  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000290a  mov     [rsp+58h+arg_18], rax
0x18000290f  mov     rbx, rax
0x180002912  test    rax, rax
0x180002915  jz      short loc_18000298F
0x180002917  mov     rax, [rsi+10h]
0x18000291b  lea     rcx, ??_7DdcCommandHandlerDesktop@@6B@; const DdcCommandHandlerDesktop::`vftable'
0x180002922  mov     [rbx], rcx
0x180002925  mov     dword ptr [rbx+8], 1
0x18000292c  mov     [rbx+10h], rax
0x180002930  lock inc dword ptr [rax]
0x180002933  test    rbx, rbx
0x180002936  jz      short loc_18000298F
0x180002938  mov     rax, [rbx]
0x18000293b  mov     r8, rdi
0x18000293e  mov     rdx, rbp
0x180002941  mov     rcx, rbx
0x180002944  mov     rax, [rax]
0x180002947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294c  mov     edi, eax
0x18000294e  test    eax, eax
0x180002950  jns     short loc_18000297E
0x180002952  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002959  jz      short loc_18000297E
0x18000295b  lea     rax, aChrPcommandhan; "CHR(pCommandHandler->QueryInterface(rii"...
0x180002962  mov     r8d, edi
0x180002965  mov     [rsp+58h+var_30], rax
0x18000296a  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180002971  mov     [rsp+58h+var_38], 73h ; 's'
0x180002979  call    McTemplateU0dsqs_EventWriteTransfer
0x18000297e  mov     rax, [rbx]
0x180002981  mov     rcx, rbx
0x180002984  mov     rax, [rax+10h]
0x180002988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298d  jmp     short loc_1800029C0
0x18000298f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002996  mov     edi, 8007000Eh
0x18000299b  jz      short loc_1800029C0
0x18000299d  lea     rax, aCprPcommandhan_0; "CPR(pCommandHandler)"
0x1800029a4  mov     [rsp+58h+var_30], rax
0x1800029a9  mov     [rsp+58h+var_38], 72h ; 'r'
0x1800029b1  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800029b8  mov     r8d, edi
0x1800029bb  call    McTemplateU0dsqs_EventWriteTransfer
0x1800029c0  mov     eax, edi
0x1800029c2  add     rsp, 38h
0x1800029c6  pop     rdi
0x1800029c7  pop     rsi
0x1800029c8  pop     rbp
0x1800029c9  pop     rbx
0x1800029ca  retn
```
