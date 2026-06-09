# CAudioSession::RemoveClientReference(bool)

- ea: `0x18002fe30`
- end: `0x18003027c`
- name: `?RemoveClientReference@CAudioSession@@UEAAJ_N@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CAudioSession *__hidden this, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x18002a04c`
- `0x18002fe30`
- `0x180030b5c`
- `0x180072450`
- `0x1800cdfbc`
- `0x1800cfd9c`
- `0x1800e8490`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ffdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ffdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ffee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ffee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030210`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002ff0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002ff0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800300b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800300b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ff4d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ff4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ff26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ff26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ff6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ff6b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800300d0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800300d0`

## string_xrefs

- `0x180030266`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_ee85f21a7da73824226bb42893b0f656_Traceguids);
    }
LABEL_7:
    if ( this )
      (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
    v4 = (*(__int64 (__fastcall **)(struct IAudioService *))(*(_QWORD *)g_AudioService + 120LL))(g_AudioService);
    if ( this )
      (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
    v25[0] = off_18016EB40;
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
    v24 = *((_DWORD *)this + 82);
    WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_ee85f21a7da73824226bb42893b0f656_Traceguids, this);
  }
  if ( v3 )
    goto LABEL_7;
  return 0;
}

```

## disassembly

```asm
0x18002fe30  mov     [rsp+arg_0], rbx
0x18002fe35  mov     [rsp+arg_10], rbp
0x18002fe3a  push    rsi
0x18002fe3b  push    rdi
0x18002fe3c  push    r12
0x18002fe3e  push    r14
0x18002fe40  push    r15
0x18002fe42  sub     rsp, 0B0h
0x18002fe49  mov     rbx, rcx
0x18002fe4c  xor     dil, dil
0x18002fe4f  mov     esi, 0FFFFFFFFh
0x18002fe54  test    dl, dl
0x18002fe56  jnz     loc_180030193
0x18002fe5c  mov     eax, esi
0x18002fe5e  lock xadd [rcx+148h], eax
0x18002fe66  cmp     eax, 1
0x18002fe69  jz      loc_18003013F
0x18002fe6f  lea     rax, WPP_GLOBAL_Control
0x18002fe76  mov     r10, cs:WPP_GLOBAL_Control
0x18002fe7d  cmp     r10, rax
0x18002fe80  jz      short loc_18002FE8D
0x18002fe82  test    byte ptr [r10+1Ch], 40h
0x18002fe87  jnz     loc_180030227
0x18002fe8d  test    dil, dil
0x18002fe90  jz      loc_180030121
0x18002fe96  test    rbx, rbx
0x18002fe99  jz      short loc_18002FEAB
0x18002fe9b  mov     rax, [rbx]
0x18002fe9e  mov     rcx, rbx
0x18002fea1  mov     rax, [rax+8]
0x18002fea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feaa  nop
0x18002feab  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18002feb2  mov     rax, [rcx]
0x18002feb5  mov     rax, [rax+78h]
0x18002feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002febe  mov     r15, rax
0x18002fec1  test    rbx, rbx
0x18002fec4  jz      short loc_18002FED6
0x18002fec6  mov     rcx, [rbx]
0x18002fec9  mov     rax, [rcx+8]
0x18002fecd  mov     rcx, rbx
0x18002fed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fed5  nop
0x18002fed6  lea     rax, off_18016EB40
0x18002fedd  mov     [rsp+0D8h+var_A8], rax
0x18002fee2  mov     [rsp+0D8h+var_A0], rbx
0x18002fee7  lea     rax, [rsp+0D8h+var_A8]
0x18002feec  mov     [rsp+0D8h+var_70], rax
0x18002fef1  xor     r12d, r12d
0x18002fef4  mov     edi, r12d
0x18002fef7  movzx   eax, byte ptr [r15+50h]
0x18002fefc  nop
0x18002fefd  test    al, al
0x18002feff  jnz     loc_1800300D6
0x18002ff05  cmp     [r15], rdi
0x18002ff08  jnz     short loc_18002FF87
0x18002ff0a  xor     ecx, ecx; reserved
0x18002ff0c  call    cs:__imp_CreateThreadpool
0x18002ff12  mov     [r15], rax
0x18002ff15  test    rax, rax
0x18002ff18  jz      loc_1800301F9
0x18002ff1e  mov     edx, 1; cthrdMic
0x18002ff23  mov     rcx, [r15]; ptpp
0x18002ff26  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002ff2c  test    eax, eax
0x18002ff2e  jnz     short loc_18002FF4D
0x18002ff30  call    cs:__imp_GetLastError
0x18002ff36  mov     edi, eax
0x18002ff38  test    eax, eax
0x18002ff3a  jle     short loc_18002FF45
0x18002ff3c  movzx   edi, ax
0x18002ff3f  or      edi, 80070000h
0x18002ff45  test    edi, edi
0x18002ff47  js      loc_1800300D6
0x18002ff4d  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002ff53  mov     [r15+0A8h], rax
0x18002ff5a  test    rax, rax
0x18002ff5d  jz      loc_180030210
0x18002ff63  mov     edx, 1; cthrdMost
0x18002ff68  mov     rcx, [r15]; ptpp
0x18002ff6b  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002ff71  mov     rax, [r15]
0x18002ff74  mov     [r15+10h], rax
0x18002ff78  mov     rax, [r15+0A8h]
0x18002ff7f  mov     [r15+18h], rax
0x18002ff83  mov     [r15+20h], r12
0x18002ff87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ff8e  mov     ecx, 18h; unsigned __int64
0x18002ff93  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ff98  mov     r14, rax
0x18002ff9b  test    rax, rax
0x18002ff9e  jz      loc_1800301A3
0x18002ffa4  mov     [rax], r12
0x18002ffa7  mov     [rax+8], r12
0x18002ffab  mov     [rax+10h], r12
0x18002ffaf  mov     [rsp+0D8h+var_30], r12
0x18002ffb7  mov     rcx, [rsp+0D8h+var_70]
0x18002ffbc  test    rcx, rcx
0x18002ffbf  jz      short loc_18002FFD9
0x18002ffc1  mov     rax, [rcx]
0x18002ffc4  lea     rdx, [rsp+0D8h+var_68]
0x18002ffc9  mov     rax, [rax]
0x18002ffcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffd1  mov     [rsp+0D8h+var_30], rax
0x18002ffd9  mov     [r14+10h], r15
0x18002ffdd  call    cs:__imp_GetProcessHeap
0x18002ffe3  mov     rcx, rax; hHeap
0x18002ffe6  xor     edx, edx; dwFlags
0x18002ffe8  mov     r8d, 50h ; 'P'; dwBytes
0x18002ffee  call    cs:__imp_HeapAlloc
0x18002fff4  mov     rbp, rax
0x18002fff7  test    rax, rax
0x18002fffa  jz      loc_1800301D7
0x180030000  mov     dword ptr [rax+8], 1
0x180030007  mov     dword ptr [rax+0Ch], 1
0x18003000e  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030015  mov     [rbp+0], rax
0x180030019  lea     rcx, [rbp+10h]
0x18003001d  lea     rdx, [rsp+0D8h+var_68]
0x180030022  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x180030027  lea     rax, [rbp+10h]
0x18003002b  mov     [r14], rax
0x18003002e  mov     rdi, [r14+8]
0x180030032  mov     [r14+8], rbp
0x180030036  test    rdi, rdi
0x180030039  jz      short loc_18003006E
0x18003003b  mov     eax, esi
0x18003003d  lock xadd [rdi+8], eax
0x180030042  cmp     eax, 1
0x180030045  jnz     short loc_18003006E
0x180030047  mov     rax, [rdi]
0x18003004a  mov     rcx, rdi
0x18003004d  mov     rax, [rax]
0x180030050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030055  lock xadd [rdi+0Ch], esi
0x18003005a  cmp     esi, 1
0x18003005d  jnz     short loc_18003006E
0x18003005f  mov     rax, [rdi]
0x180030062  mov     rcx, rdi
0x180030065  mov     rax, [rax+8]
0x180030069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003006e  mov     rsi, [r14]
0x180030071  mov     edi, 8007000Eh
0x180030076  test    rsi, rsi
0x180030079  cmovnz  edi, r12d
0x18003007d  mov     rcx, [rsp+0D8h+var_30]
0x180030085  test    rcx, rcx
0x180030088  jz      short loc_1800300A1
0x18003008a  mov     rax, [rcx]
0x18003008d  lea     rdx, [rsp+0D8h+var_68]
0x180030092  cmp     rcx, rdx
0x180030095  setnz   dl
0x180030098  mov     rax, [rax+20h]
0x18003009c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300a1  test    rsi, rsi
0x1800300a4  jz      loc_1800301CA
0x1800300aa  lea     r8, [r15+8]; pcbe
0x1800300ae  mov     rdx, r14; pv
0x1800300b1  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800300b8  call    cs:__imp_CreateThreadpoolWork
0x1800300be  mov     rsi, rax
0x1800300c1  test    rax, rax
0x1800300c4  jz      loc_1800301AD
0x1800300ca  mov     edi, r12d
0x1800300cd  mov     rcx, rsi; pwk
0x1800300d0  call    cs:__imp_SubmitThreadpoolWork
0x1800300d6  mov     rcx, [rsp+0D8h+var_70]
0x1800300db  test    rcx, rcx
0x1800300de  jz      short loc_1800300FC
0x1800300e0  mov     rax, [rcx]
0x1800300e3  lea     rdx, [rsp+0D8h+var_A8]
0x1800300e8  cmp     rcx, rdx
0x1800300eb  setnz   dl
0x1800300ee  mov     rax, [rax+20h]
0x1800300f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f7  mov     [rsp+0D8h+var_70], r12
0x1800300fc  mov     rcx, [rsp+0D8h]; this
0x180030104  test    edi, edi
0x180030106  js      loc_180030263
0x18003010c  test    rbx, rbx
0x18003010f  jz      short loc_180030121
0x180030111  mov     rax, [rbx]
0x180030114  mov     rcx, rbx
0x180030117  mov     rax, [rax+10h]
0x18003011b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030120  nop
0x180030121  xor     eax, eax
0x180030123  lea     r11, [rsp+0D8h+var_28]
0x18003012b  mov     rbx, [r11+30h]
0x18003012f  mov     rbp, [r11+40h]
0x180030133  mov     rsp, r11
0x180030136  pop     r15
0x180030138  pop     r14
0x18003013a  pop     r12
0x18003013c  pop     rdi
0x18003013d  pop     rsi
0x18003013e  retn
0x18003013f  mov     rax, [rcx]
0x180030142  mov     rax, [rax+100h]
0x180030149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003014e  lea     rax, WPP_GLOBAL_Control
0x180030155  mov     rcx, cs:WPP_GLOBAL_Control
0x18003015c  cmp     rcx, rax
0x18003015f  jz      loc_18002FE96
0x180030165  test    byte ptr [rcx+1Ch], 40h
0x180030169  jz      loc_18002FE96
0x18003016f  cmp     byte ptr [rcx+19h], 4
0x180030173  jb      loc_18002FE96
0x180030179  mov     edx, 3Ch ; '<'
0x18003017e  lea     r8, WPP_ee85f21a7da73824226bb42893b0f656_Traceguids
0x180030185  mov     rcx, [rcx+10h]
0x180030189  call    WPP_SF_
0x18003018e  jmp     loc_18002FE96
0x180030193  lock add [rcx+14Ch], esi
0x18003019a  setz    dil
0x18003019e  jmp     loc_18002FE5C
0x1800301a3  mov     edi, 8007000Eh
0x1800301a8  jmp     loc_1800300D6
0x1800301ad  call    cs:__imp_GetLastError
0x1800301b3  mov     edi, eax
0x1800301b5  test    eax, eax
0x1800301b7  jle     short loc_1800301C2
0x1800301b9  movzx   edi, ax
0x1800301bc  or      edi, 80070000h
0x1800301c2  test    edi, edi
0x1800301c4  jns     loc_1800300CD
0x1800301ca  mov     rcx, r14; this
0x1800301cd  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x1800301d2  jmp     loc_1800300D6
0x1800301d7  mov     rbp, r12
0x1800301da  jmp     loc_180030027
0x1800301df  test    edi, edi
0x1800301e1  js      loc_1800300D6
0x1800301e7  jmp     loc_18002FF1E
0x1800301ec  test    edi, edi
0x1800301ee  js      loc_1800300D6
0x1800301f4  jmp     loc_18002FF63
0x1800301f9  call    cs:__imp_GetLastError
0x1800301ff  mov     edi, eax
0x180030201  test    eax, eax
0x180030203  jle     short loc_1800301DF
0x180030205  movzx   edi, ax
0x180030208  or      edi, 80070000h
0x18003020e  jmp     short loc_1800301DF
0x180030210  call    cs:__imp_GetLastError
0x180030216  mov     edi, eax
0x180030218  test    eax, eax
0x18003021a  jle     short loc_1800301EC
0x18003021c  movzx   edi, ax
0x18003021f  or      edi, 80070000h
0x180030225  jmp     short loc_1800301EC
0x180030227  cmp     byte ptr [r10+19h], 4
0x18003022c  jb      loc_18002FE8D
0x180030232  mov     edx, 3Dh ; '='
0x180030237  mov     eax, [rcx+14Ch]
0x18003023d  mov     [rsp+0D8h+var_B0], eax
0x180030241  mov     eax, [rcx+148h]
0x180030247  mov     [rsp+0D8h+var_B8], eax
0x18003024b  mov     r9, rbx
0x18003024e  lea     r8, WPP_ee85f21a7da73824226bb42893b0f656_Traceguids
0x180030255  mov     rcx, [r10+10h]
0x180030259  call    WPP_SF_qdd
0x18003025e  jmp     loc_18002FE8D
0x180030263  mov     r9d, edi; char *
0x180030266  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18003026d  mov     edx, 0D92h; void *
0x180030272  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030277  jmp     loc_18003010C
```
