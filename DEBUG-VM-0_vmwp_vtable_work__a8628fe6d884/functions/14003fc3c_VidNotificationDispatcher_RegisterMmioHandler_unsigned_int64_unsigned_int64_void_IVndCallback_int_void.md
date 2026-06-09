# VidNotificationDispatcher::RegisterMmioHandler(unsigned __int64,unsigned __int64,void *,IVndCallback &,int,void * &)

- ea: `0x14003fc3c`
- end: `0x14003ff1c`
- name: `?RegisterMmioHandler@VidNotificationDispatcher@@QEAAJ_K0PEAXAEAUIVndCallback@@HAEAPEAX@Z`
- size: `736`
- prototype: `__int64 __fastcall(VidNotificationDispatcher *this, unsigned __int64, unsigned __int64, __int64, struct IVndCallback *, int, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140279720`

## callees

- `0x14003fc3c`
- `0x140040fd8`
- `0x1400412b4`
- `0x1400413c0`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x14009d7ac`
- `0x1400db3f0`
- `0x140132d30`
- `0x14027b4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fe63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fe63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fc80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fc80`
- `vid!VidCreateMmioGpaRange` at `0x14003fe53`
- `vid!VidCreateMmioGpaRange` at `0x14003fe53`

## string_xrefs

- `0x14003ff0a`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VidNotificationDispatcher::RegisterMmioHandler(
        VidNotificationDispatcher *this,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        struct IVndCallback *a5,
        int a6,
        void **a7)
{
  volatile signed __int32 *v11; // rdi
  DWORD CurrentThreadId; // esi
  __int64 v13; // r8
  unsigned __int32 v14; // eax
  unsigned __int32 v15; // edx
  signed int v16; // ebx
  __int64 v17; // rcx
  Vml::VmSharableObject *HandlerContext; // rsi
  signed int LastError; // eax
  _OWORD *v20; // rax
  _QWORD *v21; // rax
  signed int v22; // eax
  bool v23; // sf
  unsigned int v25; // [rsp+20h] [rbp-88h]
  int v26; // [rsp+20h] [rbp-88h]
  _QWORD v27[3]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v28[88]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v27[0] = a7;
  v11 = (volatile signed __int32 *)((char *)this + 5824);
  CurrentThreadId = GetCurrentThreadId();
  v14 = _InterlockedCompareExchange(v11, 1, 0);
  if ( v14 )
  {
    if ( *((_DWORD *)v11 + 1) == CurrentThreadId )
    {
      _InterlockedAdd(v11 + 2, 1u);
      goto LABEL_8;
    }
    do
    {
      while ( (v14 & 1) != 0 || v14 >= 4 )
      {
        LOBYTE(v13) = 1;
        if ( !(unsigned int)RrwpLockWait(v11, 0xFFFFFFFFLL, v13) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            v25);
        _m_prefetchw((const void *)v11);
        v14 = *v11;
      }
      v15 = v14;
      v14 = _InterlockedCompareExchange(v11, v14 + 1, v14);
    }
    while ( v14 != v15 );
  }
  _InterlockedExchange(v11 + 1, CurrentThreadId);
LABEL_8:
  v27[2] = v11;
  if ( (unsigned int)VidNotificationDispatcher::VerifyUnhandledMmioRange(this, a2, a3) )
  {
    HandlerContext = VidNotificationDispatcher::CreateHandlerContext((__int64)this, 0, a4, (__int64)a5, a6);
    if ( !HandlerContext )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x291,
        (unsigned int)"onecore\\vm\\worker\\vidpartition\\vnd.cpp",
        (const char *)0x8000FFFFLL,
        v26);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402DC200);
      goto LABEL_32;
    }
    v20 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
    }
    *((_QWORD *)HandlerContext + 24) = v20;
    if ( !v20 )
    {
      v16 = -2147024882;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecore\\vm\\worker\\vidpartition\\vnd.cpp",
        (const char *)0x8000FFFFLL,
        v26);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402DC2C0);
      goto LABEL_35;
    }
    *((_QWORD *)HandlerContext + 22) = a2;
    *((_QWORD *)HandlerContext + 23) = a3;
    v21 = v20 + 1;
    v21[1] = v21;
    *v21 = v21;
    if ( (unsigned int)VidCreateMmioGpaRange(
                         *((_QWORD *)this + 5),
                         a2,
                         a3,
                         HandlerContext,
                         (char *)HandlerContext + 112) )
    {
      *(_QWORD *)v27[0] = HandlerContext;
      *((_DWORD *)HandlerContext + 34) = 1;
      _InterlockedExchange((volatile __int32 *)this + 192, 1);
      v27[0] = a2;
      v27[1] = HandlerContext;
      std::_Tree<std::_Tmap_traits<unsigned __int64,VND_HANDLER_CONTEXT *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,VND_HANDLER_CONTEXT *>>,0>>::_Emplace<std::pair<unsigned __int64,VND_HANDLER_CONTEXT *>>(
        (char *)this + 80,
        v28,
        v27);
      v16 = 0;
      goto LABEL_37;
    }
    v22 = GetLastError();
    v16 = v22;
    if ( (v22 & 0x1FFF0000) != 0 )
    {
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v16 = v22 & 0xFFFFFFF | 0x80000000;
        goto LABEL_32;
      }
    }
    else
    {
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v16 = (unsigned __int16)v22 | 0x80070000;
LABEL_32:
        v23 = v16 < 0;
      }
    }
    if ( !v23 || !HandlerContext )
      goto LABEL_37;
LABEL_35:
    VidNotificationDispatcher::DeleteHandlerContext(this, HandlerContext);
    goto LABEL_37;
  }
  v16 = -2147024883;
  if ( g_BreakOnChildAssert )
    v17 = 0;
  else
    v17 = 0x4000;
  if ( (unsigned int)VmlIsDebugTraceEnabled(v17) )
    VmlDebugTraceEx(g_BreakOnChildAssert == 0 ? 0x4000 : 0, &off_1402DC218);
LABEL_37:
  RrwLockRelease(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14003fc3c  push    rbx
0x14003fc3e  push    rbp
0x14003fc3f  push    rsi
0x14003fc40  push    rdi
0x14003fc41  push    r12
0x14003fc43  push    r13
0x14003fc45  push    r14
0x14003fc47  push    r15
0x14003fc49  sub     rsp, 68h
0x14003fc4d  mov     r12, r9
0x14003fc50  mov     r15, r8
0x14003fc53  mov     r14, rdx
0x14003fc56  mov     rbp, rcx
0x14003fc59  mov     r13, [rsp+0A8h+arg_20]
0x14003fc61  mov     eax, [rsp+0A8h+arg_28]
0x14003fc68  mov     [rsp+0A8h+var_78], eax
0x14003fc6c  mov     rax, [rsp+0A8h+arg_30]
0x14003fc74  mov     [rsp+0A8h+var_70], rax
0x14003fc79  lea     rdi, [rcx+16C0h]
0x14003fc80  call    cs:__imp_GetCurrentThreadId
0x14003fc87  nop     dword ptr [rax+rax+00h]
0x14003fc8c  mov     esi, eax
0x14003fc8e  mov     ebx, 1
0x14003fc93  xor     eax, eax
0x14003fc95  lock cmpxchg [rdi], ebx
0x14003fc99  jz      short loc_14003FCBE
0x14003fc9b  mov     ecx, [rdi+4]
0x14003fc9e  cmp     ecx, esi
0x14003fca0  jnz     short loc_14003FCA8
0x14003fca2  lock add [rdi+8], ebx
0x14003fca6  jmp     short loc_14003FCC1
0x14003fca8  test    bl, al
0x14003fcaa  jnz     short loc_14003FCEE
0x14003fcac  cmp     eax, 4
0x14003fcaf  jnb     short loc_14003FCEE
0x14003fcb1  mov     edx, eax
0x14003fcb3  lea     ecx, [rax+1]
0x14003fcb6  lock cmpxchg [rdi], ecx
0x14003fcba  cmp     eax, edx
0x14003fcbc  jnz     short loc_14003FCA8
0x14003fcbe  xchg    esi, [rdi+4]
0x14003fcc1  mov     [rsp+0A8h+var_60], rdi
0x14003fcc6  mov     r8, r15; unsigned __int64
0x14003fcc9  mov     rdx, r14; unsigned __int64
0x14003fccc  mov     rcx, rbp; this
0x14003fccf  call    ?VerifyUnhandledMmioRange@VidNotificationDispatcher@@QEAAH_K0@Z; VidNotificationDispatcher::VerifyUnhandledMmioRange(unsigned __int64,unsigned __int64)
0x14003fcd4  test    eax, eax
0x14003fcd6  jnz     short loc_14003FD39
0x14003fcd8  mov     ebx, 8007000Dh
0x14003fcdd  mov     esi, 4000h
0x14003fce2  cmp     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x14003fce8  jz      short loc_14003FD0B
0x14003fcea  xor     ecx, ecx
0x14003fcec  jmp     short loc_14003FD0D
0x14003fcee  mov     r8b, bl
0x14003fcf1  or      edx, 0FFFFFFFFh
0x14003fcf4  mov     rcx, rdi
0x14003fcf7  call    RrwpLockWait
0x14003fcfc  test    eax, eax
0x14003fcfe  jz      loc_14003FEFC
0x14003fd04  prefetchw byte ptr [rdi]
0x14003fd07  mov     eax, [rdi]
0x14003fd09  jmp     short loc_14003FCA8
0x14003fd0b  mov     ecx, esi
0x14003fd0d  call    VmlIsDebugTraceEnabled
0x14003fd12  test    eax, eax
0x14003fd14  jz      loc_14003FEE0
0x14003fd1a  mov     eax, cs:?g_BreakOnChildAssert@@3HA; int g_BreakOnChildAssert
0x14003fd20  neg     eax
0x14003fd22  sbb     ecx, ecx
0x14003fd24  not     ecx
0x14003fd26  and     ecx, esi
0x14003fd28  lea     rdx, off_1402DC218; "Unexpected error.\n"
0x14003fd2f  call    VmlDebugTraceEx
0x14003fd34  jmp     loc_14003FEE0
0x14003fd39  mov     eax, [rsp+0A8h+var_78]
0x14003fd3d  mov     [rsp+0A8h+var_88], eax; int
0x14003fd41  mov     r9, r13
0x14003fd44  mov     r8, r12
0x14003fd47  xor     edx, edx
0x14003fd49  mov     rcx, rbp
0x14003fd4c  call    ?CreateHandlerContext@VidNotificationDispatcher@@AEAAPEAUVND_HANDLER_CONTEXT@@W4_VND_HANDLER_TYPE@@PEAXPEAUIVndCallback@@H@Z; VidNotificationDispatcher::CreateHandlerContext(_VND_HANDLER_TYPE,void *,IVndCallback *,int)
0x14003fd51  mov     rsi, rax
0x14003fd54  test    rax, rax
0x14003fd57  jnz     short loc_14003FDB5
0x14003fd59  call    cs:__imp_GetLastError
0x14003fd60  nop     dword ptr [rax+rax+00h]
0x14003fd65  mov     ebx, eax
0x14003fd67  test    eax, eax
0x14003fd69  jle     short loc_14003FD74
0x14003fd6b  movzx   ebx, ax
0x14003fd6e  or      ebx, 80070000h
0x14003fd74  mov     rcx, [rsp+0A8h]; this
0x14003fd7c  mov     r9d, 8000FFFFh; char *
0x14003fd82  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x14003fd89  mov     edx, 291h; void *
0x14003fd8e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14003fd93  xor     ecx, ecx
0x14003fd95  call    VmlIsDebugTraceEnabled
0x14003fd9a  test    eax, eax
0x14003fd9c  jz      loc_14003FE97
0x14003fda2  lea     rdx, off_1402DC200; "Unexpected error.\n"
0x14003fda9  xor     ecx, ecx
0x14003fdab  call    VmlDebugTraceEx
0x14003fdb0  jmp     loc_14003FE97
0x14003fdb5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003fdbc  mov     ecx, 20h ; ' '; unsigned __int64
0x14003fdc1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003fdc6  test    rax, rax
0x14003fdc9  jz      short loc_14003FDD5
0x14003fdcb  xorps   xmm0, xmm0
0x14003fdce  movups  xmmword ptr [rax], xmm0
0x14003fdd1  movups  xmmword ptr [rax+10h], xmm0
0x14003fdd5  mov     [rsi+0C0h], rax
0x14003fddc  test    rax, rax
0x14003fddf  jnz     short loc_14003FE24
0x14003fde1  mov     ebx, 8007000Eh
0x14003fde6  mov     rcx, [rsp+0A8h]; this
0x14003fdee  mov     r9d, 8000FFFFh; char *
0x14003fdf4  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x14003fdfb  mov     edx, 299h; void *
0x14003fe00  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14003fe05  xor     ecx, ecx
0x14003fe07  call    VmlIsDebugTraceEnabled
0x14003fe0c  test    eax, eax
0x14003fe0e  jz      loc_14003FEA0
0x14003fe14  lea     rdx, off_1402DC2C0; "Unexpected error.\n"
0x14003fe1b  xor     ecx, ecx
0x14003fe1d  call    VmlDebugTraceEx
0x14003fe22  jmp     short loc_14003FEA0
0x14003fe24  mov     [rsi+0B0h], r14
0x14003fe2b  mov     [rsi+0B8h], r15
0x14003fe32  add     rax, 10h
0x14003fe36  mov     [rax+8], rax
0x14003fe3a  mov     [rax], rax
0x14003fe3d  lea     rax, [rsi+70h]
0x14003fe41  mov     qword ptr [rsp+0A8h+var_88], rax
0x14003fe46  mov     r9, rsi
0x14003fe49  mov     r8, r15
0x14003fe4c  mov     rdx, r14
0x14003fe4f  mov     rcx, [rbp+28h]
0x14003fe53  call    cs:__imp_VidCreateMmioGpaRange
0x14003fe5a  nop     dword ptr [rax+rax+00h]
0x14003fe5f  test    eax, eax
0x14003fe61  jnz     short loc_14003FEAD
0x14003fe63  call    cs:__imp_GetLastError
0x14003fe6a  nop     dword ptr [rax+rax+00h]
0x14003fe6f  mov     ebx, eax
0x14003fe71  test    eax, 1FFF0000h
0x14003fe76  jnz     short loc_14003FE87
0x14003fe78  test    eax, eax
0x14003fe7a  jle     short loc_14003FE99
0x14003fe7c  movzx   ebx, bx
0x14003fe7f  or      ebx, 80070000h
0x14003fe85  jmp     short loc_14003FE97
0x14003fe87  test    ebx, ebx
0x14003fe89  jle     short loc_14003FE99
0x14003fe8b  and     ebx, 0FFFFFFFh
0x14003fe91  or      ebx, 80000000h
0x14003fe97  test    ebx, ebx
0x14003fe99  jns     short loc_14003FEE0
0x14003fe9b  test    rsi, rsi
0x14003fe9e  jz      short loc_14003FEE0
0x14003fea0  mov     rdx, rsi; struct VND_HANDLER_CONTEXT *
0x14003fea3  mov     rcx, rbp; this
0x14003fea6  call    ?DeleteHandlerContext@VidNotificationDispatcher@@AEAAXPEAUVND_HANDLER_CONTEXT@@@Z; VidNotificationDispatcher::DeleteHandlerContext(VND_HANDLER_CONTEXT *)
0x14003feab  jmp     short loc_14003FEE0
0x14003fead  mov     rax, [rsp+0A8h+var_70]
0x14003feb2  mov     [rax], rsi
0x14003feb5  mov     [rsi+88h], ebx
0x14003febb  xchg    ebx, [rbp+300h]
0x14003fec1  mov     [rsp+0A8h+var_70], r14
0x14003fec6  mov     [rsp+0A8h+var_68], rsi
0x14003fecb  lea     rcx, [rbp+50h]
0x14003fecf  lea     r8, [rsp+0A8h+var_70]
0x14003fed4  lea     rdx, [rsp+0A8h+var_58]
0x14003fed9  call    ??$_Emplace@U?$pair@_KPEAUVND_HANDLER_CONTEXT@@@std@@@?$_Tree@V?$_Tmap_traits@_KPEAUVND_HANDLER_CONTEXT@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAUVND_HANDLER_CONTEXT@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,VND_HANDLER_CONTEXT *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,VND_HANDLER_CONTEXT *>>,0>>::_Emplace<std::pair<unsigned __int64,VND_HANDLER_CONTEXT *>>(std::pair<unsigned __int64,VND_HANDLER_CONTEXT *> &&)
0x14003fede  xor     ebx, ebx
0x14003fee0  mov     rcx, rdi
0x14003fee3  call    RrwLockRelease
0x14003fee8  mov     eax, ebx
0x14003feea  add     rsp, 68h
0x14003feee  pop     r15
0x14003fef0  pop     r14
0x14003fef2  pop     r13
0x14003fef4  pop     r12
0x14003fef6  pop     rdi
0x14003fef7  pop     rsi
0x14003fef8  pop     rbp
0x14003fef9  pop     rbx
0x14003fefa  retn
0x14003fefc  mov     rcx, [rsp+0A8h]; this
0x14003ff04  mov     r9d, 102h; char *
0x14003ff0a  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14003ff11  mov     edx, 2FEh; void *
0x14003ff16  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
