# DdcTaskStateHandlerDesktopFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003520`
- end: `0x18000366b`
- name: `?CreateInstance@DdcTaskStateHandlerDesktopFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktopFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016d4`
- `0x1800026ac`
- `0x180003520`
- `0x18000c010`

## string_xrefs

- `0x18000360a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddctaskstatehandlerdesktop.cpp`
- `0x180003651`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddctaskstatehandlerdesktop.cpp`
- `0x18000363d`: `CPR(pTaskStateHandler)`
- `0x1800035fb`: `CHR(pTaskStateHandler->QueryInterface(riid, ppvObject))`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktopFactory::CreateInstance(
        DdcTaskStateHandlerDesktopFactory *this,
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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddctask"
                        "statehandlerdesktop.cpp",
          107,
          (__int64)"CBR(pUnkOuter == nullptr)");
    }
    else
    {
      v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 )
      {
        v11 = (volatile signed __int32 *)*((_QWORD *)this + 2);
        *(_QWORD *)v10 = &DdcTaskStateHandlerDesktop::`vftable';
        v10[2] = 1;
        *((_QWORD *)v10 + 2) = v11;
        _InterlockedIncrement(v11);
        v7 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v10)(v10, a3, a4);
        if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v13,
            v12,
            v7,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcta"
                          "skstatehandlerdesktop.cpp",
            112,
            (__int64)"CHR(pTaskStateHandler->QueryInterface(riid, ppvObject))");
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
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcta"
                          "skstatehandlerdesktop.cpp",
            111,
            (__int64)"CPR(pTaskStateHandler)");
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddctaskst"
                      "atehandlerdesktop.cpp",
        103,
        (__int64)"CPR(ppvObject)");
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003520  push    rbx
0x180003522  push    rbp
0x180003523  push    rsi
0x180003524  push    rdi
0x180003525  sub     rsp, 38h
0x180003529  mov     rdi, r9
0x18000352c  mov     rbp, r8
0x18000352f  mov     rsi, rcx
0x180003532  test    r9, r9
0x180003535  jnz     short loc_180003562
0x180003537  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000353e  mov     edi, 80070057h
0x180003543  jz      loc_180003660
0x180003549  lea     rax, aCprPpvobject; "CPR(ppvObject)"
0x180003550  mov     [rsp+58h+var_30], rax
0x180003555  mov     [rsp+58h+var_38], 67h ; 'g'
0x18000355d  jmp     loc_180003651
0x180003562  mov     qword ptr [r9], 0
0x180003569  test    rdx, rdx
0x18000356c  jz      short loc_180003599
0x18000356e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003575  mov     edi, 80040110h
0x18000357a  jz      loc_180003660
0x180003580  lea     rax, aCbrPunkouterNu; "CBR(pUnkOuter == nullptr)"
0x180003587  mov     [rsp+58h+var_30], rax
0x18000358c  mov     [rsp+58h+var_38], 6Bh ; 'k'
0x180003594  jmp     loc_180003651
0x180003599  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800035a0  mov     ecx, 18h; unsigned __int64
0x1800035a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800035aa  mov     [rsp+58h+arg_18], rax
0x1800035af  mov     rbx, rax
0x1800035b2  test    rax, rax
0x1800035b5  jz      short loc_18000362F
0x1800035b7  mov     rax, [rsi+10h]
0x1800035bb  lea     rcx, ??_7DdcTaskStateHandlerDesktop@@6B@; const DdcTaskStateHandlerDesktop::`vftable'
0x1800035c2  mov     [rbx], rcx
0x1800035c5  mov     dword ptr [rbx+8], 1
0x1800035cc  mov     [rbx+10h], rax
0x1800035d0  lock inc dword ptr [rax]
0x1800035d3  test    rbx, rbx
0x1800035d6  jz      short loc_18000362F
0x1800035d8  mov     rax, [rbx]
0x1800035db  mov     r8, rdi
0x1800035de  mov     rdx, rbp
0x1800035e1  mov     rcx, rbx
0x1800035e4  mov     rax, [rax]
0x1800035e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ec  mov     edi, eax
0x1800035ee  test    eax, eax
0x1800035f0  jns     short loc_18000361E
0x1800035f2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800035f9  jz      short loc_18000361E
0x1800035fb  lea     rax, aChrPtaskstateh_0; "CHR(pTaskStateHandler->QueryInterface(r"...
0x180003602  mov     r8d, edi
0x180003605  mov     [rsp+58h+var_30], rax
0x18000360a  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003611  mov     [rsp+58h+var_38], 70h ; 'p'
0x180003619  call    McTemplateU0dsqs_EventWriteTransfer
0x18000361e  mov     rax, [rbx]
0x180003621  mov     rcx, rbx
0x180003624  mov     rax, [rax+10h]
0x180003628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362d  jmp     short loc_180003660
0x18000362f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003636  mov     edi, 8007000Eh
0x18000363b  jz      short loc_180003660
0x18000363d  lea     rax, aCprPtaskstateh_0; "CPR(pTaskStateHandler)"
0x180003644  mov     [rsp+58h+var_30], rax
0x180003649  mov     [rsp+58h+var_38], 6Fh ; 'o'
0x180003651  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003658  mov     r8d, edi
0x18000365b  call    McTemplateU0dsqs_EventWriteTransfer
0x180003660  mov     eax, edi
0x180003662  add     rsp, 38h
0x180003666  pop     rdi
0x180003667  pop     rsi
0x180003668  pop     rbp
0x180003669  pop     rbx
0x18000366a  retn
```
