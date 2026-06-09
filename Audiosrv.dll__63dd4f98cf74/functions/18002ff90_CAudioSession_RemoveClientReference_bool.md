# CAudioSession::RemoveClientReference(bool)

- ea: `0x18002ff90`
- end: `0x1800303dc`
- name: `?RemoveClientReference@CAudioSession@@UEAAJ_N@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CAudioSession *this, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x18002a1ac`
- `0x18002ff90`
- `0x180030cbc`
- `0x180071f50`
- `0x1800cbfcc`
- `0x1800cddac`
- `0x1800e7d10`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003013d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003013d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003014e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003014e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003030d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003030d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030370`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003006c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003006c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030218`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030218`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800300ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800300ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180030086`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180030086`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800300cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800300cb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180030230`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180030230`

## string_xrefs

- `0x1800303c6`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAudioSession::RemoveClientReference(CAudioSession *this, char a2)
{
  bool v3; // di
  __int64 v4; // r15
  signed int v5; // edi
  PTP_POOL Threadpool; // rax
  signed int v7; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 *v9; // rax
  __int64 *v10; // r14
  HANDLE ProcessHeap; // rax
  _DWORD *v12; // rax
  unsigned int v13; // edx
  _DWORD *v14; // rbp
  volatile signed __int32 *v15; // rdi
  __int64 v16; // rsi
  _BYTE *v17; // rdx
  struct _TP_WORK *ThreadpoolWork; // rsi
  _QWORD *v19; // rdx
  signed int v21; // eax
  signed int LastError; // eax
  signed int v23; // eax
  int v24; // [rsp+20h] [rbp-B8h]
  _QWORD v25[7]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD *v26; // [rsp+68h] [rbp-70h]
  _BYTE v27[56]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE *v28; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v3 = 0;
  if ( a2 )
    v3 = _InterlockedAdd((volatile signed __int32 *)this + 83, 0xFFFFFFFF) == 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 82, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 256LL))(this);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_ee85f21a7da73824226bb42893b0f656_Traceguids);
    }
LABEL_7:
    if ( this )
      (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
    v4 = (*(__int64 (__fastcall **)(struct IAudioService *))(*(_QWORD *)g_AudioService + 120LL))(g_AudioService);
    if ( this )
      (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
    v25[0] = off_18016FB40;
    v25[1] = this;
    v26 = v25;
    v5 = 0;
    if ( *(_BYTE *)(v4 + 80) )
      goto LABEL_37;
    if ( !*(_QWORD *)v4 )
    {
      Threadpool = CreateThreadpool(0);
      *(_QWORD *)v4 = Threadpool;
      if ( !Threadpool )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_37;
      }
      if ( !SetThreadpoolThreadMinimum(*(PTP_POOL *)v4, 1u) )
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_37;
      }
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *(_QWORD *)(v4 + 168) = ThreadpoolCleanupGroup;
      if ( !ThreadpoolCleanupGroup )
      {
        v23 = GetLastError();
        v5 = v23;
        if ( v23 > 0 )
          v5 = (unsigned __int16)v23 | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_37;
      }
      SetThreadpoolThreadMaximum(*(PTP_POOL *)v4, 1u);
      *(_QWORD *)(v4 + 16) = *(_QWORD *)v4;
      *(_QWORD *)(v4 + 24) = *(_QWORD *)(v4 + 168);
      *(_QWORD *)(v4 + 32) = 0;
    }
    v9 = (__int64 *)operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      v5 = -2147024882;
      goto LABEL_37;
    }
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v28 = 0;
    if ( v26 )
      v28 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v26)(v26, v27);
    v10[2] = v4;
    ProcessHeap = GetProcessHeap();
    v12 = HeapAlloc(ProcessHeap, 0, 0x50u);
    v14 = v12;
    if ( v12 )
    {
      v12[2] = 1;
      v12[3] = 1;
      *(_QWORD *)v12 = &std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable';
      std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(v12 + 4, v27);
    }
    else
    {
      v14 = 0;
    }
    *v10 = (__int64)(v14 + 4);
    v15 = (volatile signed __int32 *)v10[1];
    v10[1] = (__int64)v14;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = *v10;
    v5 = -2147024882;
    if ( *v10 )
      v5 = 0;
    if ( v28 )
    {
      v17 = v27;
      LOBYTE(v17) = v28 != v27;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v17);
    }
    if ( v16 )
    {
      ThreadpoolWork = CreateThreadpoolWork(CSerialWorkQueue::WorkCallback, v10, (PTP_CALLBACK_ENVIRON)(v4 + 8));
      if ( ThreadpoolWork )
      {
        v5 = 0;
LABEL_36:
        SubmitThreadpoolWork(ThreadpoolWork);
LABEL_37:
        if ( v26 )
        {
          v19 = v25;
          LOBYTE(v19) = v26 != v25;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v26 + 32LL))(v26, v19);
          v26 = 0;
        }
        if ( v5 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xD92,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
            (const char *)(unsigned int)v5,
            v24);
        if ( this )
          (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 16LL))(this);
        return 0;
      }
      v21 = GetLastError();
      v5 = v21;
      if ( v21 > 0 )
        v5 = (unsigned __int16)v21 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_36;
    }
    _WorkTask::`scalar deleting destructor'((_WorkTask *)v10, v13);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      WPP_ee85f21a7da73824226bb42893b0f656_Traceguids,
      this,
      *((_DWORD *)this + 82),
      *((_DWORD *)this + 83));
  }
  if ( v3 )
    goto LABEL_7;
  return 0;
}

```

## disassembly

```asm
0x18002ff90  mov     [rsp+arg_0], rbx
0x18002ff95  mov     [rsp+arg_10], rbp
0x18002ff9a  push    rsi
0x18002ff9b  push    rdi
0x18002ff9c  push    r12
0x18002ff9e  push    r14
0x18002ffa0  push    r15
0x18002ffa2  sub     rsp, 0B0h
0x18002ffa9  mov     rbx, rcx
0x18002ffac  xor     dil, dil
0x18002ffaf  mov     esi, 0FFFFFFFFh
0x18002ffb4  test    dl, dl
0x18002ffb6  jnz     loc_1800302F3
0x18002ffbc  mov     eax, esi
0x18002ffbe  lock xadd [rcx+148h], eax
0x18002ffc6  cmp     eax, 1
0x18002ffc9  jz      loc_18003029F
0x18002ffcf  lea     rax, WPP_GLOBAL_Control
0x18002ffd6  mov     r10, cs:WPP_GLOBAL_Control
0x18002ffdd  cmp     r10, rax
0x18002ffe0  jz      short loc_18002FFED
0x18002ffe2  test    byte ptr [r10+1Ch], 40h
0x18002ffe7  jnz     loc_180030387
0x18002ffed  test    dil, dil
0x18002fff0  jz      loc_180030281
0x18002fff6  test    rbx, rbx
0x18002fff9  jz      short loc_18003000B
0x18002fffb  mov     rax, [rbx]
0x18002fffe  mov     rcx, rbx
0x180030001  mov     rax, [rax+8]
0x180030005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003000a  nop
0x18003000b  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180030012  mov     rax, [rcx]
0x180030015  mov     rax, [rax+78h]
0x180030019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003001e  mov     r15, rax
0x180030021  test    rbx, rbx
0x180030024  jz      short loc_180030036
0x180030026  mov     rcx, [rbx]
0x180030029  mov     rax, [rcx+8]
0x18003002d  mov     rcx, rbx
0x180030030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030035  nop
0x180030036  lea     rax, off_18016FB40
0x18003003d  mov     [rsp+0D8h+var_A8], rax
0x180030042  mov     [rsp+0D8h+var_A0], rbx
0x180030047  lea     rax, [rsp+0D8h+var_A8]
0x18003004c  mov     [rsp+0D8h+var_70], rax
0x180030051  xor     r12d, r12d
0x180030054  mov     edi, r12d
0x180030057  movzx   eax, byte ptr [r15+50h]
0x18003005c  nop
0x18003005d  test    al, al
0x18003005f  jnz     loc_180030236
0x180030065  cmp     [r15], rdi
0x180030068  jnz     short loc_1800300E7
0x18003006a  xor     ecx, ecx; reserved
0x18003006c  call    cs:__imp_CreateThreadpool
0x180030072  mov     [r15], rax
0x180030075  test    rax, rax
0x180030078  jz      loc_180030359
0x18003007e  mov     edx, 1; cthrdMic
0x180030083  mov     rcx, [r15]; ptpp
0x180030086  call    cs:__imp_SetThreadpoolThreadMinimum
0x18003008c  test    eax, eax
0x18003008e  jnz     short loc_1800300AD
0x180030090  call    cs:__imp_GetLastError
0x180030096  mov     edi, eax
0x180030098  test    eax, eax
0x18003009a  jle     short loc_1800300A5
0x18003009c  movzx   edi, ax
0x18003009f  or      edi, 80070000h
0x1800300a5  test    edi, edi
0x1800300a7  js      loc_180030236
0x1800300ad  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800300b3  mov     [r15+0A8h], rax
0x1800300ba  test    rax, rax
0x1800300bd  jz      loc_180030370
0x1800300c3  mov     edx, 1; cthrdMost
0x1800300c8  mov     rcx, [r15]; ptpp
0x1800300cb  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800300d1  mov     rax, [r15]
0x1800300d4  mov     [r15+10h], rax
0x1800300d8  mov     rax, [r15+0A8h]
0x1800300df  mov     [r15+18h], rax
0x1800300e3  mov     [r15+20h], r12
0x1800300e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800300ee  mov     ecx, 18h; unsigned __int64
0x1800300f3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800300f8  mov     r14, rax
0x1800300fb  test    rax, rax
0x1800300fe  jz      loc_180030303
0x180030104  mov     [rax], r12
0x180030107  mov     [rax+8], r12
0x18003010b  mov     [rax+10h], r12
0x18003010f  mov     [rsp+0D8h+var_30], r12
0x180030117  mov     rcx, [rsp+0D8h+var_70]
0x18003011c  test    rcx, rcx
0x18003011f  jz      short loc_180030139
0x180030121  mov     rax, [rcx]
0x180030124  lea     rdx, [rsp+0D8h+var_68]
0x180030129  mov     rax, [rax]
0x18003012c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030131  mov     [rsp+0D8h+var_30], rax
0x180030139  mov     [r14+10h], r15
0x18003013d  call    cs:__imp_GetProcessHeap
0x180030143  mov     rcx, rax; hHeap
0x180030146  xor     edx, edx; dwFlags
0x180030148  mov     r8d, 50h ; 'P'; dwBytes
0x18003014e  call    cs:__imp_HeapAlloc
0x180030154  mov     rbp, rax
0x180030157  test    rax, rax
0x18003015a  jz      loc_180030337
0x180030160  mov     dword ptr [rax+8], 1
0x180030167  mov     dword ptr [rax+0Ch], 1
0x18003016e  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030175  mov     [rbp+0], rax
0x180030179  lea     rcx, [rbp+10h]
0x18003017d  lea     rdx, [rsp+0D8h+var_68]
0x180030182  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x180030187  lea     rax, [rbp+10h]
0x18003018b  mov     [r14], rax
0x18003018e  mov     rdi, [r14+8]
0x180030192  mov     [r14+8], rbp
0x180030196  test    rdi, rdi
0x180030199  jz      short loc_1800301CE
0x18003019b  mov     eax, esi
0x18003019d  lock xadd [rdi+8], eax
0x1800301a2  cmp     eax, 1
0x1800301a5  jnz     short loc_1800301CE
0x1800301a7  mov     rax, [rdi]
0x1800301aa  mov     rcx, rdi
0x1800301ad  mov     rax, [rax]
0x1800301b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301b5  lock xadd [rdi+0Ch], esi
0x1800301ba  cmp     esi, 1
0x1800301bd  jnz     short loc_1800301CE
0x1800301bf  mov     rax, [rdi]
0x1800301c2  mov     rcx, rdi
0x1800301c5  mov     rax, [rax+8]
0x1800301c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301ce  mov     rsi, [r14]
0x1800301d1  mov     edi, 8007000Eh
0x1800301d6  test    rsi, rsi
0x1800301d9  cmovnz  edi, r12d
0x1800301dd  mov     rcx, [rsp+0D8h+var_30]
0x1800301e5  test    rcx, rcx
0x1800301e8  jz      short loc_180030201
0x1800301ea  mov     rax, [rcx]
0x1800301ed  lea     rdx, [rsp+0D8h+var_68]
0x1800301f2  cmp     rcx, rdx
0x1800301f5  setnz   dl
0x1800301f8  mov     rax, [rax+20h]
0x1800301fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030201  test    rsi, rsi
0x180030204  jz      loc_18003032A
0x18003020a  lea     r8, [r15+8]; pcbe
0x18003020e  mov     rdx, r14; pv
0x180030211  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180030218  call    cs:__imp_CreateThreadpoolWork
0x18003021e  mov     rsi, rax
0x180030221  test    rax, rax
0x180030224  jz      loc_18003030D
0x18003022a  mov     edi, r12d
0x18003022d  mov     rcx, rsi; pwk
0x180030230  call    cs:__imp_SubmitThreadpoolWork
0x180030236  mov     rcx, [rsp+0D8h+var_70]
0x18003023b  test    rcx, rcx
0x18003023e  jz      short loc_18003025C
0x180030240  mov     rax, [rcx]
0x180030243  lea     rdx, [rsp+0D8h+var_A8]
0x180030248  cmp     rcx, rdx
0x18003024b  setnz   dl
0x18003024e  mov     rax, [rax+20h]
0x180030252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030257  mov     [rsp+0D8h+var_70], r12
0x18003025c  mov     rcx, [rsp+0D8h]; this
0x180030264  test    edi, edi
0x180030266  js      loc_1800303C3
0x18003026c  test    rbx, rbx
0x18003026f  jz      short loc_180030281
0x180030271  mov     rax, [rbx]
0x180030274  mov     rcx, rbx
0x180030277  mov     rax, [rax+10h]
0x18003027b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030280  nop
0x180030281  xor     eax, eax
0x180030283  lea     r11, [rsp+0D8h+var_28]
0x18003028b  mov     rbx, [r11+30h]
0x18003028f  mov     rbp, [r11+40h]
0x180030293  mov     rsp, r11
0x180030296  pop     r15
0x180030298  pop     r14
0x18003029a  pop     r12
0x18003029c  pop     rdi
0x18003029d  pop     rsi
0x18003029e  retn
0x18003029f  mov     rax, [rcx]
0x1800302a2  mov     rax, [rax+100h]
0x1800302a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ae  lea     rax, WPP_GLOBAL_Control
0x1800302b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302bc  cmp     rcx, rax
0x1800302bf  jz      loc_18002FFF6
0x1800302c5  test    byte ptr [rcx+1Ch], 40h
0x1800302c9  jz      loc_18002FFF6
0x1800302cf  cmp     byte ptr [rcx+19h], 4
0x1800302d3  jb      loc_18002FFF6
0x1800302d9  mov     edx, 3Ch ; '<'
0x1800302de  lea     r8, WPP_ee85f21a7da73824226bb42893b0f656_Traceguids
0x1800302e5  mov     rcx, [rcx+10h]
0x1800302e9  call    WPP_SF_
0x1800302ee  jmp     loc_18002FFF6
0x1800302f3  lock add [rcx+14Ch], esi
0x1800302fa  setz    dil
0x1800302fe  jmp     loc_18002FFBC
0x180030303  mov     edi, 8007000Eh
0x180030308  jmp     loc_180030236
0x18003030d  call    cs:__imp_GetLastError
0x180030313  mov     edi, eax
0x180030315  test    eax, eax
0x180030317  jle     short loc_180030322
0x180030319  movzx   edi, ax
0x18003031c  or      edi, 80070000h
0x180030322  test    edi, edi
0x180030324  jns     loc_18003022D
0x18003032a  mov     rcx, r14; this
0x18003032d  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x180030332  jmp     loc_180030236
0x180030337  mov     rbp, r12
0x18003033a  jmp     loc_180030187
0x18003033f  test    edi, edi
0x180030341  js      loc_180030236
0x180030347  jmp     loc_18003007E
0x18003034c  test    edi, edi
0x18003034e  js      loc_180030236
0x180030354  jmp     loc_1800300C3
0x180030359  call    cs:__imp_GetLastError
0x18003035f  mov     edi, eax
0x180030361  test    eax, eax
0x180030363  jle     short loc_18003033F
0x180030365  movzx   edi, ax
0x180030368  or      edi, 80070000h
0x18003036e  jmp     short loc_18003033F
0x180030370  call    cs:__imp_GetLastError
0x180030376  mov     edi, eax
0x180030378  test    eax, eax
0x18003037a  jle     short loc_18003034C
0x18003037c  movzx   edi, ax
0x18003037f  or      edi, 80070000h
0x180030385  jmp     short loc_18003034C
0x180030387  cmp     byte ptr [r10+19h], 4
0x18003038c  jb      loc_18002FFED
0x180030392  mov     edx, 3Dh ; '='
0x180030397  mov     eax, [rcx+14Ch]
0x18003039d  mov     [rsp+0D8h+var_B0], eax
0x1800303a1  mov     eax, [rcx+148h]
0x1800303a7  mov     [rsp+0D8h+var_B8], eax
0x1800303ab  mov     r9, rbx
0x1800303ae  lea     r8, WPP_ee85f21a7da73824226bb42893b0f656_Traceguids
0x1800303b5  mov     rcx, [r10+10h]
0x1800303b9  call    WPP_SF_qdd
0x1800303be  jmp     loc_18002FFED
0x1800303c3  mov     r9d, edi; char *
0x1800303c6  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800303cd  mov     edx, 0D92h; void *
0x1800303d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800303d7  jmp     loc_18003026C
```
