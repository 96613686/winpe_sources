# CServerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003fe0`
- end: `0x1400040d1`
- name: `?CreateInstance@CServerClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(CServerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003c48`
- `0x140003fe0`
- `0x140005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000406d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000406d`
- `WsmSvc!CreateProvHost` at `0x140004053`
- `WsmSvc!CreateProvHost` at `0x140004053`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140004094`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140004094`

## pseudocode

```c
__int64 __fastcall CServerClassFactory::CreateInstance(
        CServerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // ebx
  __int64 (__fastcall ***ProvHost)(void *, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v9)(void *, const struct _GUID *, void **); // rdi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_91e5af8dacc63f96ce1cf96a1a9af1d4_Traceguids);
  *a4 = 0;
  if ( a2 )
  {
    v7 = -2147221232;
  }
  else
  {
    ProvHost = (__int64 (__fastcall ***)(void *, const struct _GUID *, void **))CreateProvHost(
                                                                                  g_Hwnd,
                                                                                  &g_HostRegisterProfile,
                                                                                  &g_HostRegisterNoProfile,
                                                                                  &g_ObjectsInProgress);
    v9 = ProvHost;
    if ( ProvHost )
    {
      v7 = (**ProvHost)(ProvHost, a3, a4);
      if ( v7 < 0 )
        WSManMemory::Free(v9, 0);
    }
    else
    {
      v7 = -2147024882;
      SetEvent(g_shutdownEvent);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_91e5af8dacc63f96ce1cf96a1a9af1d4_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140003fe0  push    rbx
0x140003fe2  push    rsi
0x140003fe3  push    rdi
0x140003fe4  push    r14
0x140003fe6  sub     rsp, 28h
0x140003fea  mov     rbx, r9
0x140003fed  mov     rsi, r8
0x140003ff0  mov     rdi, rdx
0x140003ff3  lea     r14, WPP_GLOBAL_Control
0x140003ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x140004001  cmp     rcx, r14
0x140004004  jz      short loc_140004024
0x140004006  test    dword ptr [rcx+1Ch], 100h
0x14000400d  jz      short loc_140004024
0x14000400f  mov     edx, 0Ch
0x140004014  lea     r8, WPP_91e5af8dacc63f96ce1cf96a1a9af1d4_Traceguids
0x14000401b  mov     rcx, [rcx+10h]
0x14000401f  call    WPP_SF_
0x140004024  mov     qword ptr [rbx], 0
0x14000402b  test    rdi, rdi
0x14000402e  jz      short loc_140004037
0x140004030  mov     ebx, 80040110h
0x140004035  jmp     short loc_14000409B
0x140004037  lea     r9, ?g_ObjectsInProgress@@3JA; long g_ObjectsInProgress
0x14000403e  lea     r8, ?g_HostRegisterNoProfile@@3KA; ulong g_HostRegisterNoProfile
0x140004045  lea     rdx, ?g_HostRegisterProfile@@3KA; ulong g_HostRegisterProfile
0x14000404c  mov     rcx, cs:?g_Hwnd@@3PEAUHWND__@@EA; HWND__ * g_Hwnd
0x140004053  call    cs:__imp_?CreateProvHost@@YAPEAXPEAUHWND__@@PEAK1PEAJ@Z; CreateProvHost(HWND__ *,ulong *,ulong *,long *)
0x140004059  mov     rdi, rax
0x14000405c  test    rax, rax
0x14000405f  jnz     short loc_140004075
0x140004061  mov     ebx, 8007000Eh
0x140004066  mov     rcx, cs:?g_shutdownEvent@@3PEAXEA; hEvent
0x14000406d  call    cs:__imp_SetEvent
0x140004073  jmp     short loc_14000409B
0x140004075  mov     rax, [rax]
0x140004078  mov     r8, rbx
0x14000407b  mov     rdx, rsi
0x14000407e  mov     rcx, rdi
0x140004081  mov     rax, [rax]
0x140004084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004089  mov     ebx, eax
0x14000408b  test    eax, eax
0x14000408d  jns     short loc_14000409B
0x14000408f  xor     edx, edx
0x140004091  mov     rcx, rdi
0x140004094  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x14000409a  nop
0x14000409b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040a2  cmp     rcx, r14
0x1400040a5  jz      short loc_1400040C5
0x1400040a7  test    dword ptr [rcx+1Ch], 100h
0x1400040ae  jz      short loc_1400040C5
0x1400040b0  mov     edx, 0Dh
0x1400040b5  lea     r8, WPP_91e5af8dacc63f96ce1cf96a1a9af1d4_Traceguids
0x1400040bc  mov     rcx, [rcx+10h]
0x1400040c0  call    WPP_SF_
0x1400040c5  mov     eax, ebx
0x1400040c7  add     rsp, 28h
0x1400040cb  pop     r14
0x1400040cd  pop     rdi
0x1400040ce  pop     rsi
0x1400040cf  pop     rbx
0x1400040d0  retn
```
