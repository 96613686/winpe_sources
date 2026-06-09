# CInkStroke::~CInkStroke(void)

- ea: `0x180009610`
- end: `0x180009932`
- name: `??1CInkStroke@@QEAA@XZ`
- size: `802`
- prototype: `void __fastcall(CInkStroke *__hidden this)`
- caller_count: `35`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800075ac`
- `0x1800095c4`
- `0x18000b3d0`
- `0x18000b414`
- `0x18003aaec`
- `0x18003ab9c`
- `0x18003bd90`
- `0x18003cef8`
- `0x18003d030`
- `0x18003e53c`
- `0x18004392c`
- `0x1800889f0`
- `0x18008af64`
- `0x18008c454`
- `0x18008dc28`
- `0x18008e5d8`
- `0x18008ee50`
- `0x18008f040`
- `0x180092588`
- `0x180096634`
- `0x1801054f3`
- `0x180105ba7`
- `0x180107d0e`
- `0x180107d44`
- `0x180107e28`
- `0x180107e3a`
- `0x180107eb6`
- `0x180108086`
- `0x18010943b`
- `0x1801095bc`
- `0x1801095f2`
- `0x180109616`
- `0x1801096fe`
- `0x180109710`
- `0x18010974e`

## callees

- `0x1800093f0`
- `0x180009610`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009748`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009748`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000978a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000978a`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000988c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800098ef`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000988c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800098ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall CInkStroke::~CInkStroke(CInkStroke *this)
{
  __int64 v2; // rdi
  void *v3; // r14
  bool v4; // r12
  __int64 v5; // rdi
  HANDLE v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  _DWORD *v11; // rcx

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = 0;
    v4 = 0;
    v5 = *(_QWORD *)(v2 + 144);
    if ( v5 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + (unsigned int)tls_index)
                                                                     + 4LL) )
      {
        Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
        {
          `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
          dwFlags = 0;
          `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
          atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
          Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        }
      }
      v6 = `WinHeap::GetDefault'::`2'::s_WinHeap;
      if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
        v3 = HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 8u);
      else
        v3 = 0;
      if ( v3 )
        CInkModule::GetObjLock(v6, v3, v5 + 432);
      else
        v3 = 0;
      v4 = v3 != 0;
    }
    if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    if ( v4 )
    {
      v7 = *((_QWORD *)this + 2);
      if ( v7 )
      {
        v11 = *(_DWORD **)(v7 + 144);
        if ( v11 )
        {
          if ( *(_DWORD *)(v7 + 8) == 1 && !v11[4] )
            (*(void (__fastcall **)(_DWORD *, CInkStroke *))(*(_QWORD *)v11 + 32LL))(v11, this);
        }
      }
      v8 = *((_QWORD *)this + 2);
      if ( v8 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
        *((_QWORD *)this + 2) = 0;
      }
      if ( v3 )
      {
        if ( *(_QWORD *)v3 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)v3 + 8LL));
        if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + (unsigned int)tls_index)
                                                                       + 4LL) )
        {
          Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
          if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
          {
            `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
            dwFlags = 0;
            `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
            atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
            Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
          }
        }
        if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
          HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v3);
      }
    }
  }
  v9 = *((_QWORD *)this + 2);
  if ( v9 )
  {
    v10 = *(_DWORD *)(v9 + 8);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
    if ( v10 == 1 )
      *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180009610  mov     [rsp+arg_0], rcx
0x180009615  push    rbx
0x180009616  push    rsi
0x180009617  push    rdi
0x180009618  push    r12
0x18000961a  push    r13
0x18000961c  push    r14
0x18000961e  push    r15
0x180009620  sub     rsp, 20h
0x180009624  mov     rsi, rcx
0x180009627  xor     r15d, r15d
0x18000962a  mov     rdi, [rcx+10h]
0x18000962e  test    rdi, rdi
0x180009631  jz      loc_1800097C0
0x180009637  mov     r14d, r15d
0x18000963a  xor     r12b, r12b
0x18000963d  mov     rdi, [rdi+90h]
0x180009644  mov     [rsp+58h+arg_10], rdi
0x180009649  test    rdi, rdi
0x18000964c  jz      short loc_180009656
0x18000964e  lock inc dword ptr [rdi+8]
0x180009652  lock inc dword ptr [rdi+8]
0x180009656  mov     ebx, 0FFFFFFFFh
0x18000965b  mov     r13d, 1
0x180009661  test    rdi, rdi
0x180009664  jz      loc_1800096EF
0x18000966a  mov     eax, ebx
0x18000966c  lock xadd [rdi+8], eax
0x180009671  cmp     eax, r13d
0x180009674  jz      loc_180009815
0x18000967a  mov     edx, cs:_tls_index
0x180009680  mov     rax, gs:58h
0x180009689  mov     ecx, 4
0x18000968e  mov     rax, [rax+rdx*8]
0x180009692  mov     eax, [rcx+rax]
0x180009695  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18000969b  jg      loc_18000985C
0x1800096a1  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800096a8  test    rcx, rcx
0x1800096ab  jz      loc_180009854
0x1800096b1  mov     r8d, 8; dwBytes
0x1800096b7  mov     edx, cs:dwFlags; dwFlags
0x1800096bd  call    cs:__imp_HeapAlloc
0x1800096c3  mov     r14, rax
0x1800096c6  mov     [rsp+58h+arg_8], r14
0x1800096cb  test    r14, r14
0x1800096ce  jz      loc_1800098B6
0x1800096d4  lea     r8, [rdi+1B0h]
0x1800096db  mov     rdx, r14
0x1800096de  call    ?GetObjLock@CInkModule@@QEBA?AVObjLock@@AEAVSmartLockPtr@@@Z; CInkModule::GetObjLock(SmartLockPtr &)
0x1800096e3  nop
0x1800096e4  movzx   r12d, r12b
0x1800096e8  test    r14, r14
0x1800096eb  cmovnz  r12d, r13d
0x1800096ef  test    rdi, rdi
0x1800096f2  jz      short loc_180009704
0x1800096f4  mov     eax, ebx
0x1800096f6  lock xadd [rdi+8], eax
0x1800096fb  cmp     eax, 1
0x1800096fe  jz      loc_18000982B
0x180009704  test    r12b, r12b
0x180009707  jz      loc_180009791
0x18000970d  mov     rax, [rsi+10h]
0x180009711  test    rax, rax
0x180009714  jnz     loc_1800097CD
0x18000971a  mov     rcx, [rsi+10h]
0x18000971e  test    rcx, rcx
0x180009721  jz      short loc_180009737
0x180009723  mov     eax, ebx
0x180009725  lock xadd [rcx+8], eax
0x18000972a  cmp     eax, 1
0x18000972d  jz      loc_180009841
0x180009733  mov     [rsi+10h], r15
0x180009737  test    r14, r14
0x18000973a  jz      short loc_180009791
0x18000973c  mov     rcx, [r14]
0x18000973f  test    rcx, rcx
0x180009742  jz      short loc_18000974E
0x180009744  add     rcx, 8; lpCriticalSection
0x180009748  call    cs:__imp_LeaveCriticalSection
0x18000974e  mov     ecx, cs:_tls_index
0x180009754  mov     rax, gs:58h
0x18000975d  mov     edx, 4
0x180009762  mov     rax, [rax+rcx*8]
0x180009766  mov     eax, [rdx+rax]
0x180009769  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18000976f  jg      loc_1800098BE
0x180009775  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18000977c  test    rcx, rcx
0x18000977f  jz      short loc_180009791
0x180009781  mov     r8, r14; lpMem
0x180009784  mov     edx, cs:dwFlags; dwFlags
0x18000978a  call    cs:__imp_HeapFree
0x180009790  nop
0x180009791  mov     rcx, [rsi+10h]
0x180009795  test    rcx, rcx
0x180009798  jz      short loc_1800097B0
0x18000979a  mov     edi, [rcx+8]
0x18000979d  lock xadd [rcx+8], ebx
0x1800097a2  cmp     ebx, 1
0x1800097a5  jz      short loc_180009805
0x1800097a7  cmp     edi, 1
0x1800097aa  jnz     short loc_1800097B0
0x1800097ac  mov     [rsi+10h], r15
0x1800097b0  add     rsp, 20h
0x1800097b4  pop     r15
0x1800097b6  pop     r14
0x1800097b8  pop     r13
0x1800097ba  pop     r12
0x1800097bc  pop     rdi
0x1800097bd  pop     rsi
0x1800097be  pop     rbx
0x1800097bf  retn
0x1800097c0  mov     ebx, 0FFFFFFFFh
0x1800097c5  mov     r13d, 1
0x1800097cb  jmp     short loc_180009791
0x1800097cd  mov     rcx, [rax+90h]
0x1800097d4  test    rcx, rcx
0x1800097d7  jz      loc_18000971A
0x1800097dd  cmp     dword ptr [rax+8], 1
0x1800097e1  jnz     loc_18000971A
0x1800097e7  cmp     dword ptr [rcx+10h], 0
0x1800097eb  jnz     loc_18000971A
0x1800097f1  mov     rax, [rcx]
0x1800097f4  mov     rdx, rsi
0x1800097f7  mov     rax, [rax+20h]
0x1800097fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009800  jmp     loc_18000971A
0x180009805  mov     rax, [rcx]
0x180009808  mov     edx, r13d
0x18000980b  mov     rax, [rax]
0x18000980e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009813  jmp     short loc_1800097A7
0x180009815  mov     rax, [rdi]
0x180009818  mov     edx, r13d
0x18000981b  mov     rcx, rdi
0x18000981e  mov     rax, [rax]
0x180009821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009826  jmp     loc_18000967A
0x18000982b  mov     rax, [rdi]
0x18000982e  mov     edx, r13d
0x180009831  mov     rcx, rdi
0x180009834  mov     rax, [rax]
0x180009837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983c  jmp     loc_180009704
0x180009841  mov     rax, [rcx]
0x180009844  mov     edx, r13d
0x180009847  mov     rax, [rax]
0x18000984a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984f  jmp     loc_180009733
0x180009854  mov     r14, r15
0x180009857  jmp     loc_1800096C6
0x18000985c  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180009863  call    _Init_thread_header
0x180009868  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, ebx
0x18000986e  jnz     loc_1800096A1
0x180009874  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r15; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18000987b  mov     cs:dwFlags, r15d
0x180009882  xor     r8d, r8d; dwMaximumSize
0x180009885  mov     edx, 10000h; dwInitialSize
0x18000988a  xor     ecx, ecx; flOptions
0x18000988c  call    cs:__imp_HeapCreate
0x180009892  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180009899  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800098a0  call    atexit
0x1800098a5  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800098ac  call    _Init_thread_footer
0x1800098b1  jmp     loc_1800096A1
0x1800098b6  mov     r14, r15
0x1800098b9  jmp     loc_1800096E4
0x1800098be  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800098c5  call    _Init_thread_header
0x1800098ca  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800098d1  jnz     loc_180009775
0x1800098d7  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r15; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800098de  mov     cs:dwFlags, r15d
0x1800098e5  xor     r8d, r8d; dwMaximumSize
0x1800098e8  mov     edx, 10000h; dwInitialSize
0x1800098ed  xor     ecx, ecx; flOptions
0x1800098ef  call    cs:__imp_HeapCreate
0x1800098f5  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800098fc  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180009903  call    atexit
0x180009908  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18000990f  call    _Init_thread_footer
0x180009914  jmp     loc_180009775
0x180009919  xor     r15d, r15d
0x18000991c  mov     ebx, 0FFFFFFFFh
0x180009921  mov     r13d, 1
0x180009927  mov     rsi, [rsp+58h+arg_0]
0x18000992c  jmp     loc_180009791
```
