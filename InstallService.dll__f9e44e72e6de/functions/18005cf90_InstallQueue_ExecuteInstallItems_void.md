# InstallQueue::_ExecuteInstallItems(void)

- ea: `0x18005cf90`
- end: `0x18005d2a6`
- name: `?_ExecuteInstallItems@InstallQueue@@AEAAXXZ`
- size: `790`
- prototype: `void __fastcall(InstallQueue *__hidden this)`
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800555f0`
- `0x1800573e0`
- `0x180059838`
- `0x18005a9a4`
- `0x18005ca4c`
- `0x180061e3c`
- `0x180061fb0`

## callees

- `0x18000e44c`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c414`
- `0x18004e9a8`
- `0x18005cf90`
- `0x18005dd38`
- `0x18005f6f8`
- `0x180062724`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d27f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d27f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d025`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d025`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005d001`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005d001`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d177`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d177`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d133`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d133`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d16e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005d16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d0db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d0db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d1a7`

## string_xrefs

- `0x18005cfdd`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005d111`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005d1d9`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005d26b`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005cfd0`: `InstallQueue::_ExecuteInstallItems`
- `0x18005d104`: `InstallQueue::_ExecuteInstallItems`
- `0x18005d1cc`: `InstallQueue::_ExecuteInstallItems`
- `0x18005d25e`: `InstallQueue::_ExecuteInstallItems`
- `0x18005d0f0`: `productId = %s is ready to install. Scheduling it on a separate thread`
- `0x18005d1bc`: `productId = %s is not ready to execute, putting it back at the top of the pending queue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InstallQueue::_ExecuteInstallItems(RTL_SRWLOCK *this)
{
  unsigned __int64 v2; // r12
  RTL_SRWLOCK *v3; // rbx
  char v4; // si
  RTL_SRWLOCK **v5; // rax
  RTL_SRWLOCK **v6; // rbx
  PCWSTR StringRawBuffer; // rax
  struct _TP_WORK *ThreadpoolWork; // rbx
  int v9; // ebx
  PCWSTR v10; // rax
  int v11; // ecx
  __int64 v12; // [rsp+40h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-10h]
  RTL_SRWLOCK **v14; // [rsp+A8h] [rbp+48h] BYREF
  struct WindowsUpdate::Internal::InstallItem *v15; // [rsp+B0h] [rbp+50h] BYREF

  InstallQueue::_ScheduleItemsThatAreReady((InstallQueue *)this);
  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
    0x5C0u,
    "InstallQueue::_ExecuteInstallItems",
    -1,
    L"Looking for the next item to start",
    0,
    0);
  InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
  v2 = (unsigned int)dword_1802CA684;
  v3 = this + 35;
  do
  {
    v4 = 0;
    AcquireSRWLockExclusive(this + 24);
    if ( this[28].Ptr >= (PVOID)v2 || (v3 = this + 35, LODWORD(this[35].Ptr)) )
    {
      LODWORD(v14) = 0;
      if ( (*(int (__fastcall **)(PVOID, RTL_SRWLOCK ***))(*(_QWORD *)this[26].Ptr + 56LL))(this[26].Ptr, &v14) >= 0 )
      {
        v11 = (int)v14;
      }
      else
      {
        v11 = -1;
        LODWORD(v14) = -1;
        v3 = this + 35;
      }
      LODWORD(v13) = v3->Ptr;
      LODWORD(v12) = v11;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x5F7u,
        "InstallQueue::_ExecuteInstallItems",
        -1,
        L"Nothing can be started.  Pending: %d, Active: %d, Suspends: %d",
        0,
        0,
        v12,
        this[28].Ptr,
        v13);
    }
    else
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v15);
      if ( (int)InstallQueue::_GetNextPendingItem((InstallQueue *)this, &v15) >= 0 )
      {
        v4 = 1;
        LOBYTE(v14) = 0;
        if ( (int)InstallQueue::_IsItemReadyToExecute((InstallQueue *)this, (HSTRING *)v15, (bool *)&v14) >= 0 )
        {
          if ( (_BYTE)v14 )
          {
            v5 = (RTL_SRWLOCK **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
            v6 = v5;
            if ( v5 )
              *(_OWORD *)v5 = 0;
            else
              v6 = 0;
            v14 = v6;
            if ( v6 )
            {
              *v6 = this;
              v6[1] = (RTL_SRWLOCK *)v15;
              StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v15 + 31), 0);
              LogMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                0x5DBu,
                "InstallQueue::_ExecuteInstallItems",
                -1,
                L"productId = %s is ready to install. Scheduling it on a separate thread",
                0,
                0,
                StringRawBuffer);
              v14 = 0;
              ThreadpoolWork = CreateThreadpoolWork(InstallQueue::s_ExecuteInstallItem, v6, 0);
              if ( ThreadpoolWork )
              {
                (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
                std::list<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>>::_Emplace<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem> const &>(
                  &this[27],
                  this[27].Ptr,
                  &v15);
                v15 = 0;
                SubmitThreadpoolWork(ThreadpoolWork);
                CloseThreadpoolWork(ThreadpoolWork);
              }
            }
            else
            {
              v9 = (*(__int64 (__fastcall **)(PVOID, _QWORD, struct WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)this[26].Ptr + 88LL))(
                     this[26].Ptr,
                     0,
                     v15);
              v10 = WindowsGetStringRawBuffer(*((HSTRING *)v15 + 31), 0);
              LogMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                0x5EAu,
                "InstallQueue::_ExecuteInstallItems",
                v9,
                L"productId = %s is not ready to execute, putting it back at the top of the pending queue",
                0,
                0,
                v10);
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v15);
      v3 = this + 35;
    }
    ReleaseSRWLockExclusive(this + 24);
  }
  while ( v4 );
}

```

## disassembly

```asm
0x18005cf90  mov     [rsp-38h+arg_0], rbx
0x18005cf95  push    rbp
0x18005cf96  push    rsi
0x18005cf97  push    rdi
0x18005cf98  push    r12
0x18005cf9a  push    r13
0x18005cf9c  push    r14
0x18005cf9e  push    r15
0x18005cfa0  mov     rbp, rsp
0x18005cfa3  sub     rsp, 60h
0x18005cfa7  mov     rdi, rcx
0x18005cfaa  call    ?_ScheduleItemsThatAreReady@InstallQueue@@AEAAXXZ; InstallQueue::_ScheduleItemsThatAreReady(void)
0x18005cfaf  xor     r13d, r13d
0x18005cfb2  mov     [rsp+60h+var_28], r13; unsigned __int16 *
0x18005cfb7  mov     [rsp+60h+var_30], r13; char *
0x18005cfbc  lea     rax, aLookingForTheN; "Looking for the next item to start"
0x18005cfc3  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18005cfc8  mov     [rsp+60h+var_40], 0FFFFFFFFh; int
0x18005cfd0  lea     r9, aInstallqueueEx_0; "InstallQueue::_ExecuteInstallItems"
0x18005cfd7  mov     r8d, 5C0h; unsigned int
0x18005cfdd  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005cfe4  lea     ecx, [r13+3]; unsigned int
0x18005cfe8  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18005cfed  xor     r9d, r9d; Context
0x18005cff0  xor     r8d, r8d; Parameter
0x18005cff3  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x18005cffa  lea     rcx, InitOnce; InitOnce
0x18005d001  call    cs:__imp_InitOnceExecuteOnce
0x18005d007  lea     r14, [rdi+0C0h]
0x18005d00e  mov     r12d, cs:dword_1802CA684
0x18005d015  lea     r15, [rdi+118h]
0x18005d01c  mov     rbx, r15
0x18005d01f  mov     sil, r13b
0x18005d022  mov     rcx, r14; SRWLock
0x18005d025  call    cs:__imp_AcquireSRWLockExclusive
0x18005d02b  cmp     [rdi+0E0h], r12
0x18005d032  jnb     loc_18005D1FD
0x18005d038  lea     rbx, [rdi+118h]
0x18005d03f  cmp     [rbx], r13d
0x18005d042  jnz     loc_18005D1FD
0x18005d048  mov     [rbp+arg_10], r13
0x18005d04c  lea     rcx, [rbp+arg_10]
0x18005d050  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005d055  lea     rdx, [rbp+arg_10]; struct WindowsUpdate::Internal::InstallItem **
0x18005d059  mov     rcx, rdi; this
0x18005d05c  call    ?_GetNextPendingItem@InstallQueue@@AEAAJPEAPEAVInstallItem@Internal@WindowsUpdate@@@Z; InstallQueue::_GetNextPendingItem(WindowsUpdate::Internal::InstallItem * *)
0x18005d061  test    eax, eax
0x18005d063  js      loc_18005D1EB
0x18005d069  mov     sil, 1
0x18005d06c  mov     byte ptr [rbp+arg_8], r13b
0x18005d070  lea     r8, [rbp+arg_8]; bool *
0x18005d074  mov     rdx, [rbp+arg_10]; struct WindowsUpdate::Internal::InstallItem *
0x18005d078  mov     rcx, rdi; this
0x18005d07b  call    ?_IsItemReadyToExecute@InstallQueue@@AEAAJPEAVInstallItem@Internal@WindowsUpdate@@PEA_N@Z; InstallQueue::_IsItemReadyToExecute(WindowsUpdate::Internal::InstallItem *,bool *)
0x18005d080  test    eax, eax
0x18005d082  js      loc_18005D1EB
0x18005d088  cmp     byte ptr [rbp+arg_8], r13b
0x18005d08c  jz      loc_18005D1EB
0x18005d092  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d099  mov     ecx, 10h; unsigned __int64
0x18005d09e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d0a3  mov     rbx, rax
0x18005d0a6  test    rax, rax
0x18005d0a9  jz      short loc_18005D0B3
0x18005d0ab  xorps   xmm0, xmm0
0x18005d0ae  movups  xmmword ptr [rax], xmm0
0x18005d0b1  jmp     short loc_18005D0B6
0x18005d0b3  mov     rbx, r13
0x18005d0b6  mov     [rbp+arg_8], rbx
0x18005d0ba  test    rbx, rbx
0x18005d0bd  jz      loc_18005D17F
0x18005d0c3  mov     [rbx], rdi
0x18005d0c6  mov     rax, [rbp+arg_10]
0x18005d0ca  mov     [rbx+8], rax
0x18005d0ce  xor     edx, edx; length
0x18005d0d0  mov     rcx, [rbp+arg_10]
0x18005d0d4  mov     rcx, [rcx+0F8h]; string
0x18005d0db  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d0e1  mov     [rsp+60h+var_20], rax
0x18005d0e6  mov     [rsp+60h+var_28], r13; unsigned __int16 *
0x18005d0eb  mov     [rsp+60h+var_30], r13; char *
0x18005d0f0  lea     rax, aProductidSIsRe; "productId = %s is ready to install. Sch"...
0x18005d0f7  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18005d0fc  mov     [rsp+60h+var_40], 0FFFFFFFFh; int
0x18005d104  lea     r9, aInstallqueueEx_0; "InstallQueue::_ExecuteInstallItems"
0x18005d10b  mov     r8d, 5DBh; unsigned int
0x18005d111  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005d118  mov     ecx, 3; unsigned int
0x18005d11d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005d122  mov     [rbp+arg_8], r13
0x18005d126  xor     r8d, r8d; pcbe
0x18005d129  mov     rdx, rbx; pv
0x18005d12c  lea     rcx, ?s_ExecuteInstallItem@InstallQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005d133  call    cs:__imp_CreateThreadpoolWork
0x18005d139  mov     rbx, rax
0x18005d13c  test    rax, rax
0x18005d13f  jz      loc_18005D1EB
0x18005d145  mov     rcx, [rdi]
0x18005d148  mov     rax, [rcx+8]
0x18005d14c  mov     rcx, rdi
0x18005d14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d154  lea     rcx, [rdi+0D8h]
0x18005d15b  lea     r8, [rbp+arg_10]
0x18005d15f  mov     rdx, [rcx]
0x18005d162  call    ??$_Emplace@AEBV?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@@?$list@V?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@V?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@PEAX@1@QEAU21@AEBV?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@@Z; std::list<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>>::_Emplace<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem> const &>(std::_List_node<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>,void *> * const,Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem> const &)
0x18005d167  mov     [rbp+arg_10], r13
0x18005d16b  mov     rcx, rbx; pwk
0x18005d16e  call    cs:__imp_SubmitThreadpoolWork
0x18005d174  mov     rcx, rbx; pwk
0x18005d177  call    cs:__imp_CloseThreadpoolWork
0x18005d17d  jmp     short loc_18005D1EB
0x18005d17f  mov     rcx, [rdi+0D0h]
0x18005d186  mov     rax, [rcx]
0x18005d189  mov     r8, [rbp+arg_10]
0x18005d18d  xor     edx, edx
0x18005d18f  mov     rax, [rax+58h]
0x18005d193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d198  mov     ebx, eax
0x18005d19a  xor     edx, edx; length
0x18005d19c  mov     rcx, [rbp+arg_10]
0x18005d1a0  mov     rcx, [rcx+0F8h]; string
0x18005d1a7  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d1ad  mov     [rsp+60h+var_20], rax
0x18005d1b2  mov     [rsp+60h+var_28], r13; unsigned __int16 *
0x18005d1b7  mov     [rsp+60h+var_30], r13; char *
0x18005d1bc  lea     rax, aProductidSIsNo; "productId = %s is not ready to execute,"...
0x18005d1c3  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18005d1c8  mov     [rsp+60h+var_40], ebx; int
0x18005d1cc  lea     r9, aInstallqueueEx_0; "InstallQueue::_ExecuteInstallItems"
0x18005d1d3  mov     r8d, 5EAh; unsigned int
0x18005d1d9  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005d1e0  mov     ecx, 3; unsigned int
0x18005d1e5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005d1ea  nop
0x18005d1eb  lea     rcx, [rbp+arg_10]
0x18005d1ef  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005d1f4  lea     rbx, [rdi+118h]
0x18005d1fb  jmp     short loc_18005D27C
0x18005d1fd  mov     dword ptr [rbp+arg_8], r13d
0x18005d201  mov     rcx, [rdi+0D0h]
0x18005d208  mov     rax, [rcx]
0x18005d20b  lea     rdx, [rbp+arg_8]
0x18005d20f  mov     rax, [rax+38h]
0x18005d213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d218  test    eax, eax
0x18005d21a  jns     short loc_18005D227
0x18005d21c  or      ecx, 0FFFFFFFFh
0x18005d21f  mov     dword ptr [rbp+arg_8], ecx
0x18005d222  mov     rbx, r15
0x18005d225  jmp     short loc_18005D22A
0x18005d227  mov     ecx, dword ptr [rbp+arg_8]
0x18005d22a  mov     eax, [rbx]
0x18005d22c  mov     [rsp+60h+var_10], eax
0x18005d230  mov     rax, [rdi+0E0h]
0x18005d237  mov     [rsp+60h+var_18], rax
0x18005d23c  mov     dword ptr [rsp+60h+var_20], ecx
0x18005d240  mov     [rsp+60h+var_28], r13; unsigned __int16 *
0x18005d245  mov     [rsp+60h+var_30], r13; char *
0x18005d24a  lea     rax, aNothingCanBeSt; "Nothing can be started.  Pending: %d, A"...
0x18005d251  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18005d256  mov     [rsp+60h+var_40], 0FFFFFFFFh; int
0x18005d25e  lea     r9, aInstallqueueEx_0; "InstallQueue::_ExecuteInstallItems"
0x18005d265  mov     r8d, 5F7h; unsigned int
0x18005d26b  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005d272  mov     ecx, 3; unsigned int
0x18005d277  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005d27c  mov     rcx, r14; SRWLock
0x18005d27f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d285  test    sil, sil
0x18005d288  jnz     loc_18005D01F
0x18005d28e  mov     rbx, [rsp+60h+arg_0]
0x18005d296  add     rsp, 60h
0x18005d29a  pop     r15
0x18005d29c  pop     r14
0x18005d29e  pop     r13
0x18005d2a0  pop     r12
0x18005d2a2  pop     rdi
0x18005d2a3  pop     rsi
0x18005d2a4  pop     rbp
0x18005d2a5  retn
```
