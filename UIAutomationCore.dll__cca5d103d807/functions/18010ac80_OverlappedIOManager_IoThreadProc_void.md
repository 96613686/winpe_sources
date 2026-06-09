# OverlappedIOManager::IoThreadProc(void)

- ea: `0x18010ac80`
- end: `0x18010b206`
- name: `?IoThreadProc@OverlappedIOManager@@AEAAXXZ`
- size: `1414`
- prototype: `void __fastcall __noreturn(OverlappedIOManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18010ac70`

## callees

- `0x18002f580`
- `0x180080cc0`
- `0x1800be9c8`
- `0x18010ac80`
- `0x18010b20c`
- `0x18010b27c`
- `0x18010b55c`
- `0x18010b5b4`
- `0x18010b728`
- `0x1801ae0a0`
- `0x1801ae14c`
- `0x1801ae45c`
- `0x1801e8344`
- `0x1801e887c`
- `0x1801e88a0`
- `0x1801fce84`
- `0x18024f1b8`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18010afef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18010afef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010afbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010afbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010b008`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010b008`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18010b079`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18010b079`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010aed5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010b0d0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010aed5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010b0d0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010aca7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010aca7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010b103`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010b103`

## string_xrefs

- `0x18010b1d0`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18010af04`: `onecore\windows\accessibletech\common\unboundedwaiter.cpp`
- `0x18010af27`: `onecore\windows\accessibletech\common\unboundedwaiter.cpp`
- `0x18010b120`: `onecore\windows\accessibletech\common\unboundedwaiter.cpp`
- `0x18010b1e2`: `onecore\windows\accessibletech\common\unboundedwaiter.cpp`
- `0x18010b1f4`: `onecore\windows\accessibletech\common\unboundedwaiter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn OverlappedIOManager::IoThreadProc(OverlappedIOManager *this)
{
  HRESULT v2; // r12d
  __int64 v3; // rcx
  int v4; // edi
  UnboundedWaiter **v5; // r14
  OverlappedIOManager *v6; // rbx
  char *v7; // rcx
  UnboundedWaiter *v8; // rbx
  unsigned __int64 v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  int v12; // edi
  _QWORD *i; // rbx
  __int64 v14; // rax
  void **v15; // rbp
  char *v16; // rbx
  int v17; // eax
  int v18; // edi
  UnboundedWaiter *v19; // rdi
  __int64 v20; // rbx
  DWORD v21; // ebp
  const char *v22; // r9
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // ebx
  void *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // rax
  const char *v33; // r9
  DWORD v34; // r14d
  const char *v35; // r9
  unsigned __int64 v36; // r10
  unsigned __int64 v37; // rax
  char *v38; // rcx
  int v39; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  void *v41; // [rsp+80h] [rbp+8h] BYREF

  v2 = 0;
  if ( BasicUiaUtils::IsDesktop() )
  {
    v2 = CoInitializeEx(0, 0);
    v3 = *((_QWORD *)this + 12);
    if ( v3 )
    {
      if ( (*(int (__fastcall **)(__int64, OverlappedIOManager *, GUID *, char *))(*(_QWORD *)v3 + 24LL))(
             v3,
             this,
             &GUID_e87645f8_f771_4847_8f57_e030e9f03d5f,
             (char *)this + 104) < 0 )
      {
        *((_DWORD *)this + 26) = 0;
        Error::InternalErrorWorker(L"Could not register OverlappedIOManager into the GIT");
      }
    }
  }
  v4 = 1;
  while ( 1 )
  {
    do
    {
      v5 = (UnboundedWaiter **)((char *)this + 112);
      v6 = (OverlappedIOManager *)*((_QWORD *)this + 1);
      if ( v6 )
      {
        do
        {
          LODWORD(v41) = 0;
          (*(void (__fastcall **)(OverlappedIOManager *, void **))(*(_QWORD *)v6 + 32LL))(v6, &v41);
          if ( (_DWORD)v41 )
            v4 = 1;
          if ( *((_DWORD *)this + 5) )
          {
            v4 = 1;
            *((_DWORD *)this + 5) = 0;
            v6 = this;
          }
          v6 = (OverlappedIOManager *)*((_QWORD *)v6 + 1);
        }
        while ( v6 );
        v5 = (UnboundedWaiter **)((char *)this + 112);
      }
      if ( v4 )
      {
        v7 = (char *)*((_QWORD *)this + 3);
        if ( v7 )
        {
          if ( v7 != (char *)this + 56 )
            operator delete(v7);
          v5 = (UnboundedWaiter **)((char *)this + 112);
        }
        v8 = *v5;
        *v5 = 0;
        if ( v8 )
        {
          UnboundedWaiter::~UnboundedWaiter(v8);
          operator delete(v8);
        }
        v9 = 8 * (*((int *)this + 4) + 1LL);
        if ( !is_mul_ok(*((int *)this + 4) + 1LL, 8u) )
          v9 = -1;
        v10 = operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
        *((_QWORD *)this + 3) = v10;
        v11 = (_QWORD *)((char *)this + 56);
        v12 = 1;
        if ( v10 )
        {
          *v10 = *v11;
          for ( i = (_QWORD *)*((_QWORD *)this + 1); i; i = (_QWORD *)i[1] )
          {
            v14 = (*(__int64 (__fastcall **)(_QWORD *))(*i + 48LL))(i);
            if ( v14 )
              *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v12++) = v14;
          }
        }
        else
        {
          *((_QWORD *)this + 3) = v11;
        }
        *((_DWORD *)this + 8) = v12;
        v15 = (void **)*((_QWORD *)this + 3);
        v16 = (char *)operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
        if ( v16 )
        {
          *(_OWORD *)(v16 + 72) = 0;
          *(_OWORD *)(v16 + 88) = 0;
          *((_QWORD *)v16 + 13) = 0;
          *(_QWORD *)v16 = 0;
          *((_QWORD *)v16 + 1) = 0;
          *((_QWORD *)v16 + 2) = 0;
          *((_QWORD *)v16 + 3) = 0;
          *((_QWORD *)v16 + 4) = 0;
          *((_QWORD *)v16 + 5) = 0;
          *((_QWORD *)v16 + 6) = 0;
          *((_QWORD *)v16 + 7) = 0;
          *((_QWORD *)v16 + 8) = 0;
          std::deque<IA2ProxyTextRange::NodeAndOffset>::deque<IA2ProxyTextRange::NodeAndOffset>(v16 + 72);
          v17 = UnboundedWaiter::Initialize((UnboundedWaiter *)v16, v15, v12);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\unboundedwaiter.cpp",
              (const char *)(unsigned int)v17,
              v39);
            std::default_delete<UnboundedWaiter>::operator()(v23, v16);
          }
          else
          {
            v19 = *v5;
            *v5 = (UnboundedWaiter *)v16;
            if ( v19 )
            {
              UnboundedWaiter::~UnboundedWaiter(v19);
              operator delete(v19);
            }
            v18 = 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\unboundedwaiter.cpp",
            (const char *)0x8007000ELL,
            v39);
          v18 = -2147024882;
        }
        if ( v18 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x4EE,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
            (const char *)(unsigned int)v18,
            v39);
        v4 = 0;
      }
      v20 = *((_QWORD *)this + 14);
      if ( *(_QWORD *)(v20 + 8) - *(_QWORD *)v20 == 24 )
      {
        v21 = WaitForMultipleObjects(
                (__int64)(*(_QWORD *)(*(_QWORD *)v20 + 8LL) - **(_QWORD **)v20) >> 3,
                **(const HANDLE ***)v20,
                0,
                0xFFFFFFFF);
        if ( v21 == -1 )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x36,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\unboundedwaiter.cpp",
            v22);
      }
      else
      {
        v33 = *(const char **)(v20 + 104);
        if ( v33 )
        {
          v36 = *(_QWORD *)(v20 + 96);
          v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 80) + 8 * ((*(_QWORD *)(v20 + 88) - 1LL) & (v36 >> 2)))
                          + 4 * (v36 & 3));
          *(_QWORD *)(v20 + 104) = v33 - 1;
          v37 = 0;
          if ( v33 != (const char *)1 )
            v37 = v36 + 1;
          *(_QWORD *)(v20 + 96) = v37;
          if ( v21 == -1 )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x4B,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\unboundedwaiter.cpp",
              v33);
        }
        else
        {
          UnboundedWaiter::SignalAllThreadsToStartWait(*((UnboundedWaiter **)this + 14));
          v34 = WaitForMultipleObjects(
                  (__int64)(*(_QWORD *)(v20 + 32) - *(_QWORD *)(v20 + 24)) >> 3,
                  *(const HANDLE **)(v20 + 24),
                  0,
                  0xFFFFFFFF);
          v21 = UnboundedWaiter::CollectResultForWaiter((UnboundedWaiter *)v20, v34);
          if ( v21 == -1 )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x42,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\unboundedwaiter.cpp",
              v35);
          UnboundedWaiter::StopAndCollectResultFromAllWaiterExcept((UnboundedWaiter *)v20, v34);
        }
      }
    }
    while ( v21 );
    v24 = *((_DWORD *)this + 35);
    if ( v24 == 1 )
      break;
    if ( v24 == 2 )
    {
      WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
      v28 = (void *)*((_QWORD *)this + 9);
      v41 = v28;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 40LL))(*((_QWORD *)this + 18));
      v29 = *((_QWORD *)this + 18);
      v30 = *(_QWORD *)(v29 + 8);
      if ( v30 )
        *(_QWORD *)(v30 + 16) = *(_QWORD *)(v29 + 16);
      v31 = *(_QWORD *)(v29 + 16);
      v32 = *(_QWORD *)(v29 + 8);
      if ( v31 )
        *(_QWORD *)(v31 + 8) = v32;
      else
        *((_QWORD *)this + 1) = v32;
      *(_QWORD *)(v29 + 16) = 0;
      *(_QWORD *)(v29 + 8) = 0;
      *((_QWORD *)this + 18) = 0;
      --*((_DWORD *)this + 4);
      v4 = 1;
      if ( v28 )
        ReleaseMutex(v28);
    }
    else if ( v24 == 3 )
    {
      OverlappedIOManager::DisconnectAllChannelsExcept(this, *((struct ChannelInfo **)this + 18));
LABEL_45:
      v4 = 1;
    }
    *((_DWORD *)this + 35) = 0;
    if ( *((_DWORD *)this + 4) )
    {
      v27 = 0;
    }
    else
    {
      v27 = 1;
      v38 = (char *)*((_QWORD *)this + 3);
      if ( v38 && v38 != (char *)this + 56 )
        operator delete(v38);
      *((_QWORD *)this + 3) = 0;
      *((_DWORD *)this + 8) = 0;
      *((_DWORD *)this + 30) = 0;
    }
    if ( *((_BYTE *)this + 136) )
      SetEvent(*((HANDLE *)this + 8));
    if ( v27 )
    {
      if ( BasicUiaUtils::IsDesktop() )
      {
        if ( *((_DWORD *)this + 26) )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 32LL))(*((_QWORD *)this + 12));
          *((_DWORD *)this + 26) = 0;
        }
        if ( v2 >= 0 )
          CoUninitialize();
      }
      FreeLibraryAndExitThread(*((HMODULE *)this + 21), 0);
    }
  }
  v25 = *((_QWORD *)this + 18);
  *(_QWORD *)(v25 + 8) = *((_QWORD *)this + 1);
  v26 = *((_QWORD *)this + 1);
  if ( v26 )
    *(_QWORD *)(v26 + 16) = v25;
  *((_QWORD *)this + 1) = v25;
  *((_QWORD *)this + 18) = 0;
  ++*((_DWORD *)this + 4);
  goto LABEL_45;
}

```

## disassembly

```asm
0x18010ac80  push    rbx
0x18010ac82  push    rbp
0x18010ac83  push    rsi
0x18010ac84  push    rdi
0x18010ac85  push    r12
0x18010ac87  push    r13
0x18010ac89  push    r14
0x18010ac8b  push    r15
0x18010ac8d  sub     rsp, 38h
0x18010ac91  mov     rsi, rcx
0x18010ac94  xor     r13d, r13d
0x18010ac97  mov     r12d, r13d
0x18010ac9a  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x18010ac9f  test    al, al
0x18010aca1  jz      short loc_18010ACDB
0x18010aca3  xor     edx, edx; dwCoInit
0x18010aca5  xor     ecx, ecx; pvReserved
0x18010aca7  call    cs:__imp_CoInitializeEx
0x18010acad  mov     r12d, eax
0x18010acb0  mov     rcx, [rsi+60h]
0x18010acb4  test    rcx, rcx
0x18010acb7  jz      short loc_18010ACDB
0x18010acb9  mov     rdx, [rcx]
0x18010acbc  mov     rax, [rdx+18h]
0x18010acc0  lea     r9, [rsi+68h]
0x18010acc4  lea     r8, _GUID_e87645f8_f771_4847_8f57_e030e9f03d5f
0x18010accb  mov     rdx, rsi
0x18010acce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010acd3  test    eax, eax
0x18010acd5  js      loc_18010B132
0x18010acdb  mov     ebp, 1
0x18010ace0  mov     edi, ebp
0x18010ace2  lea     r14, [rsi+70h]
0x18010ace6  mov     rbx, [rsi+8]
0x18010acea  test    rbx, rbx
0x18010aced  jz      short loc_18010AD31
0x18010acef  nop
0x18010acf0  mov     dword ptr [rsp+78h+arg_0], r13d
0x18010acf8  mov     rax, [rbx]
0x18010acfb  lea     rdx, [rsp+78h+arg_0]
0x18010ad03  mov     rcx, rbx
0x18010ad06  mov     rax, [rax+20h]
0x18010ad0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ad0f  cmp     dword ptr [rsp+78h+arg_0], 0
0x18010ad17  cmovnz  edi, ebp
0x18010ad1a  cmp     dword ptr [rsi+14h], 0
0x18010ad1e  jnz     loc_18010AF4E
0x18010ad24  mov     rbx, [rbx+8]
0x18010ad28  test    rbx, rbx
0x18010ad2b  jnz     short loc_18010ACF0
0x18010ad2d  lea     r14, [rsi+70h]
0x18010ad31  test    edi, edi
0x18010ad33  jz      loc_18010AEA6
0x18010ad39  mov     rcx, [rsi+18h]; Block
0x18010ad3d  test    rcx, rcx
0x18010ad40  jz      short loc_18010AD54
0x18010ad42  lea     rax, [rsi+38h]
0x18010ad46  cmp     rcx, rax
0x18010ad49  jz      short loc_18010AD50
0x18010ad4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010ad50  lea     r14, [rsi+70h]
0x18010ad54  mov     rbx, [r14]
0x18010ad57  mov     [r14], r13
0x18010ad5a  test    rbx, rbx
0x18010ad5d  jz      short loc_18010AD74
0x18010ad5f  mov     rcx, rbx; this
0x18010ad62  call    ??1UnboundedWaiter@@QEAA@XZ; UnboundedWaiter::~UnboundedWaiter(void)
0x18010ad67  mov     edx, 70h ; 'p'
0x18010ad6c  mov     rcx, rbx; Block
0x18010ad6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010ad74  movsxd  rcx, dword ptr [rsi+10h]
0x18010ad78  inc     rcx
0x18010ad7b  mov     eax, 8
0x18010ad80  mul     rcx
0x18010ad83  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010ad8a  cmovb   rax, rcx
0x18010ad8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010ad95  mov     rcx, rax; unsigned __int64
0x18010ad98  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18010ad9d  mov     rcx, rax
0x18010ada0  mov     [rsi+18h], rax
0x18010ada4  lea     rax, [rsi+38h]
0x18010ada8  mov     edi, ebp
0x18010adaa  test    rcx, rcx
0x18010adad  jz      loc_18010AF45
0x18010adb3  mov     rax, [rax]
0x18010adb6  mov     [rcx], rax
0x18010adb9  mov     rbx, [rsi+8]
0x18010adbd  test    rbx, rbx
0x18010adc0  jz      short loc_18010ADFA
0x18010adc2  nop     dword ptr [rax+00h]
0x18010adc6  nop     word ptr [rax+rax+00000000h]
0x18010add0  mov     rax, [rbx]
0x18010add3  mov     rcx, rbx
0x18010add6  mov     rax, [rax+30h]
0x18010adda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010addf  test    rax, rax
0x18010ade2  jz      short loc_18010ADF1
0x18010ade4  movsxd  rdx, edi
0x18010ade7  mov     rcx, [rsi+18h]
0x18010adeb  mov     [rcx+rdx*8], rax
0x18010adef  inc     edi
0x18010adf1  mov     rbx, [rbx+8]
0x18010adf5  test    rbx, rbx
0x18010adf8  jnz     short loc_18010ADD0
0x18010adfa  mov     [rsi+20h], edi
0x18010adfd  mov     rbp, [rsi+18h]
0x18010ae01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010ae08  mov     ecx, 70h ; 'p'; unsigned __int64
0x18010ae0d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18010ae12  mov     rbx, rax
0x18010ae15  test    rax, rax
0x18010ae18  jz      loc_18010AEF9
0x18010ae1e  xorps   xmm0, xmm0
0x18010ae21  xor     eax, eax
0x18010ae23  movups  xmmword ptr [rbx+48h], xmm0
0x18010ae27  movups  xmmword ptr [rbx+58h], xmm0
0x18010ae2b  mov     [rbx+68h], rax
0x18010ae2f  mov     [rbx], r13
0x18010ae32  mov     [rbx+8], r13
0x18010ae36  mov     [rbx+10h], r13
0x18010ae3a  mov     [rbx+18h], r13
0x18010ae3e  mov     [rbx+20h], r13
0x18010ae42  mov     [rbx+28h], r13
0x18010ae46  mov     [rbx+30h], r13
0x18010ae4a  mov     [rbx+38h], r13
0x18010ae4e  mov     [rbx+40h], r13
0x18010ae52  lea     rcx, [rbx+48h]
0x18010ae56  call    ??0?$deque@VNodeAndOffset@IA2ProxyTextRange@@V?$allocator@VNodeAndOffset@IA2ProxyTextRange@@@std@@@std@@QEAA@XZ; std::deque<IA2ProxyTextRange::NodeAndOffset>::deque<IA2ProxyTextRange::NodeAndOffset>(void)
0x18010ae5b  mov     r8d, edi; int
0x18010ae5e  mov     rdx, rbp; void **
0x18010ae61  mov     rcx, rbx; this
0x18010ae64  call    ?Initialize@UnboundedWaiter@@AEAAJPEAPEAXH@Z; UnboundedWaiter::Initialize(void * *,int)
0x18010ae69  mov     edi, eax
0x18010ae6b  test    eax, eax
0x18010ae6d  js      loc_18010AF1F
0x18010ae73  mov     rdi, [r14]
0x18010ae76  mov     [r14], rbx
0x18010ae79  test    rdi, rdi
0x18010ae7c  jz      short loc_18010AE93
0x18010ae7e  mov     rcx, rdi; this
0x18010ae81  call    ??1UnboundedWaiter@@QEAA@XZ; UnboundedWaiter::~UnboundedWaiter(void)
0x18010ae86  mov     edx, 70h ; 'p'
0x18010ae8b  mov     rcx, rdi; Block
0x18010ae8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010ae93  mov     edi, r13d
0x18010ae96  mov     rcx, [rsp+78h]; this
0x18010ae9b  test    edi, edi
0x18010ae9d  js      loc_18010B1CD
0x18010aea3  mov     edi, r13d
0x18010aea6  mov     rbx, [rsi+70h]
0x18010aeaa  mov     rcx, [rbx]
0x18010aead  mov     rax, [rbx+8]
0x18010aeb1  sub     rax, rcx
0x18010aeb4  cmp     rax, 18h
0x18010aeb8  jnz     loc_18010B0A3
0x18010aebe  mov     rdx, [rcx]; lpHandles
0x18010aec1  mov     rcx, [rcx+8]
0x18010aec5  sub     rcx, rdx
0x18010aec8  sar     rcx, 3; nCount
0x18010aecc  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18010aed2  xor     r8d, r8d; bWaitAll
0x18010aed5  call    cs:__imp_WaitForMultipleObjects
0x18010aedb  mov     ebp, eax
0x18010aedd  mov     rcx, [rsp+78h]; this
0x18010aee2  cmp     eax, 0FFFFFFFFh
0x18010aee5  jz      loc_18010B1E2
0x18010aeeb  test    ebp, ebp
0x18010aeed  jz      short loc_18010AF5C
0x18010aeef  mov     ebp, 1
0x18010aef4  jmp     loc_18010ACE2
0x18010aef9  mov     rcx, [rsp+78h]; this
0x18010aefe  mov     r9d, 8007000Eh; char *
0x18010af04  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\commo"...
0x18010af0b  mov     edx, 0Dh; void *
0x18010af10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010af15  mov     edi, 8007000Eh
0x18010af1a  jmp     loc_18010AE96
0x18010af1f  mov     rcx, [rsp+78h]; this
0x18010af24  mov     r9d, eax; char *
0x18010af27  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\commo"...
0x18010af2e  mov     edx, 0Eh; void *
0x18010af33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010af38  mov     rdx, rbx
0x18010af3b  call    ??R?$default_delete@VUnboundedWaiter@@@std@@QEBAXPEAVUnboundedWaiter@@@Z; std::default_delete<UnboundedWaiter>::operator()(UnboundedWaiter *)
0x18010af40  jmp     loc_18010AE96
0x18010af45  mov     [rsi+18h], rax
0x18010af49  jmp     loc_18010ADFA
0x18010af4e  mov     edi, ebp
0x18010af50  mov     [rsi+14h], r13d
0x18010af54  mov     rbx, rsi
0x18010af57  jmp     loc_18010AD24
0x18010af5c  mov     eax, [rsi+8Ch]
0x18010af62  cmp     eax, 1
0x18010af65  jnz     loc_18010AFF6
0x18010af6b  mov     rcx, [rsi+90h]
0x18010af72  mov     rax, [rsi+8]
0x18010af76  mov     [rcx+8], rax
0x18010af7a  mov     rax, [rsi+8]
0x18010af7e  test    rax, rax
0x18010af81  jz      short loc_18010AF87
0x18010af83  mov     [rax+10h], rcx
0x18010af87  mov     [rsi+8], rcx
0x18010af8b  mov     [rsi+90h], r13
0x18010af92  inc     dword ptr [rsi+10h]
0x18010af95  mov     edi, 1
0x18010af9a  mov     [rsi+8Ch], r13d
0x18010afa1  cmp     dword ptr [rsi+10h], 0
0x18010afa5  jz      loc_18010B1A0
0x18010afab  mov     ebx, r13d
0x18010afae  cmp     byte ptr [rsi+88h], 0
0x18010afb5  jz      short loc_18010AFC1
0x18010afb7  mov     rcx, [rsi+40h]; hEvent
0x18010afbb  call    cs:__imp_SetEvent
0x18010afc1  test    ebx, ebx
0x18010afc3  jz      loc_18010AEEF
0x18010afc9  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x18010afce  test    al, al
0x18010afd0  jz      short loc_18010AFE6
0x18010afd2  mov     edx, [rsi+68h]
0x18010afd5  test    edx, edx
0x18010afd7  jnz     loc_18010B08A
0x18010afdd  test    r12d, r12d
0x18010afe0  jns     loc_18010B103
0x18010afe6  xor     edx, edx; dwExitCode
0x18010afe8  mov     rcx, [rsi+0A8h]; hLibModule
0x18010afef  call    cs:__imp_FreeLibraryAndExitThread
0x18010aff5  int     3; Trap to Debugger
0x18010aff6  cmp     eax, 2
0x18010aff9  jnz     loc_18010B183
0x18010afff  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18010b004  mov     rcx, [rsi+48h]; hHandle
0x18010b008  call    cs:__imp_WaitForSingleObject
0x18010b00e  mov     rbx, [rsi+48h]
0x18010b012  mov     [rsp+78h+arg_0], rbx
0x18010b01a  mov     rcx, [rsi+90h]
0x18010b021  mov     rax, [rcx]
0x18010b024  mov     rax, [rax+28h]
0x18010b028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b02d  mov     rdx, [rsi+90h]
0x18010b034  mov     r8, [rdx+8]
0x18010b038  test    r8, r8
0x18010b03b  jz      short loc_18010B045
0x18010b03d  mov     rax, [rdx+10h]
0x18010b041  mov     [r8+10h], rax
0x18010b045  mov     r8, [rdx+10h]
0x18010b049  mov     rax, [rdx+8]
0x18010b04d  test    r8, r8
0x18010b050  jnz     short loc_18010B084
0x18010b052  mov     [rsi+8], rax
0x18010b056  mov     [rdx+10h], r13
0x18010b05a  mov     [rdx+8], r13
0x18010b05e  mov     [rsi+90h], r13
0x18010b065  dec     dword ptr [rsi+10h]
0x18010b068  mov     edi, 1
0x18010b06d  test    rbx, rbx
0x18010b070  jz      loc_18010AF9A
0x18010b076  mov     rcx, rbx; hMutex
0x18010b079  call    cs:__imp_ReleaseMutex
0x18010b07f  jmp     loc_18010AF9A
0x18010b084  mov     [r8+8], rax
0x18010b088  jmp     short loc_18010B056
0x18010b08a  mov     rcx, [rsi+60h]
0x18010b08e  mov     rax, [rcx]
0x18010b091  mov     rax, [rax+20h]
0x18010b095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b09a  mov     [rsi+68h], r13d
0x18010b09e  jmp     loc_18010AFDD
0x18010b0a3  mov     r9, [rbx+68h]; char *
0x18010b0a7  test    r9, r9
0x18010b0aa  jnz     loc_18010B147
0x18010b0b0  mov     rcx, rbx; this
0x18010b0b3  call    ?SignalAllThreadsToStartWait@UnboundedWaiter@@AEBAXXZ; UnboundedWaiter::SignalAllThreadsToStartWait(void)
0x18010b0b8  mov     rdx, [rbx+18h]; lpHandles
0x18010b0bc  mov     rcx, [rbx+20h]
0x18010b0c0  sub     rcx, rdx
0x18010b0c3  sar     rcx, 3; nCount
0x18010b0c7  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18010b0cd  xor     r8d, r8d; bWaitAll
0x18010b0d0  call    cs:__imp_WaitForMultipleObjects
0x18010b0d6  mov     r14d, eax
0x18010b0d9  mov     edx, eax; int
0x18010b0db  mov     rcx, rbx; this
0x18010b0de  call    ?CollectResultForWaiter@UnboundedWaiter@@AEAAKH@Z; UnboundedWaiter::CollectResultForWaiter(int)
0x18010b0e3  mov     ebp, eax
0x18010b0e5  mov     rcx, [rsp+78h]; this
0x18010b0ea  cmp     eax, 0FFFFFFFFh
0x18010b0ed  jz      loc_18010B1F4
0x18010b0f3  mov     edx, r14d; unsigned int
0x18010b0f6  mov     rcx, rbx; this
0x18010b0f9  call    ?StopAndCollectResultFromAllWaiterExcept@UnboundedWaiter@@AEAAXK@Z; UnboundedWaiter::StopAndCollectResultFromAllWaiterExcept(ulong)
0x18010b0fe  jmp     loc_18010AEEB
0x18010b103  call    cs:__imp_CoUninitialize
0x18010b109  jmp     loc_18010AFE6
0x18010b10e  mov     [rbx+60h], rax
0x18010b112  mov     rcx, [rsp+78h]; this
0x18010b117  cmp     ebp, 0FFFFFFFFh
0x18010b11a  jnz     loc_18010AEEB
0x18010b120  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\commo"...
0x18010b127  mov     edx, 4Bh ; 'K'; void *
  ... truncated ...
```
