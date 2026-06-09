# Sharing::OperationQueue::EnqueueOperation(Sharing::IQueuedOperation *)

- ea: `0x18001efa0`
- end: `0x18001f0d9`
- name: `?EnqueueOperation@OperationQueue@Sharing@@QEAAJPEAUIQueuedOperation@2@@Z`
- size: `313`
- prototype: `__int64 __fastcall(PVOID pv, struct Sharing::IQueuedOperation *)`
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800143f0`
- `0x18001b150`
- `0x18001c0a0`
- `0x18001c4d0`
- `0x18004ab40`
- `0x18004ad00`
- `0x18004b000`
- `0x1800514b0`

## callees

- `0x180004928`
- `0x180004a70`
- `0x180010d04`
- `0x1800130ec`
- `0x18001efa0`
- `0x18001f200`
- `0x180046bd8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f01c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f01c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001efe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001efe0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001f082`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001f082`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Sharing::OperationQueue::EnqueueOperation(char *pv, struct Sharing::IQueuedOperation *a2)
{
  __int64 v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned int v6; // edi
  volatile int *v7; // rdx
  signed __int64 v8; // rax
  signed __int64 v9; // rtt
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct Sharing::IQueuedOperation *v13; // [rsp+30h] [rbp+8h] BYREF
  char *v14; // [rsp+38h] [rbp+10h]

  v13 = a2;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v13);
  v4 = (*(unsigned __int8 (__fastcall **)(struct Sharing::IQueuedOperation *))(*(_QWORD *)a2 + 48LL))(a2);
  v5 = (struct _RTL_CRITICAL_SECTION *)(pv + 288);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 288));
  v14 = pv + 288;
  if ( pv[34] )
  {
    v6 = -2147467260;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\windows\\cdp\\sharingplatform\\inc\\OperationQueue.h",
      (const char *)0x80004004LL,
      v11);
    if ( v5 )
      LeaveCriticalSection(v5);
  }
  else
  {
    std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation> const &>(
      (__int64)&pv[32 * v4 + 48 + 8 * v4],
      &v13);
    if ( pv[32] )
      goto LABEL_15;
    pv[32] = 1;
    v8 = *((_QWORD *)pv + 3);
    while ( v8 >= 0 )
    {
      if ( (_DWORD)v8 != 0x7FFFFFFF )
      {
        v9 = v8;
        v8 = _InterlockedCompareExchange64((volatile signed __int64 *)pv + 3, v8 + 1, v8);
        if ( v9 != v8 )
          continue;
      }
      goto LABEL_11;
    }
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v8 + 16), v7);
LABEL_11:
    if ( TrySubmitThreadpoolCallback(Sharing::OperationQueue::ThreadPoolThunk, pv, 0) )
    {
LABEL_15:
      if ( pv != (char *)-288LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 288));
      v6 = 0;
    }
    else
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::Release(pv);
      pv[32] = 0;
      if ( pv != (char *)-288LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 288));
      v6 = -2147467259;
    }
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v13);
  return v6;
}

```

## disassembly

```asm
0x18001efa0  mov     rax, rsp
0x18001efa3  mov     [rax+18h], rbx
0x18001efa7  mov     [rax+20h], rsi
0x18001efab  push    rdi; int
0x18001efac  sub     rsp, 20h
0x18001efb0  mov     rbx, rdx
0x18001efb3  mov     rdi, rcx
0x18001efb6  mov     [rax+8], rdx
0x18001efba  lea     rcx, [rax+8]
0x18001efbe  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18001efc3  nop
0x18001efc4  mov     rax, [rbx]
0x18001efc7  mov     rcx, rbx
0x18001efca  mov     rax, [rax+30h]
0x18001efce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efd3  movzx   esi, al
0x18001efd6  lea     rbx, [rdi+120h]
0x18001efdd  mov     rcx, rbx; lpCriticalSection
0x18001efe0  call    cs:__imp_EnterCriticalSection
0x18001efe6  mov     [rsp+28h+arg_8], rbx
0x18001efeb  cmp     byte ptr [rdi+22h], 0
0x18001efef  jz      short loc_18001F027
0x18001eff1  mov     rcx, [rsp+28h]; this
0x18001eff6  mov     edi, 80004004h
0x18001effb  mov     r9d, edi; char *
0x18001effe  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\cdp\\sharingplatfo"...
0x18001f005  mov     edx, 83h; void *
0x18001f00a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f00f  nop
0x18001f010  test    rbx, rbx
0x18001f013  jz      loc_18001F0BD
0x18001f019  mov     rcx, rbx; lpCriticalSection
0x18001f01c  call    cs:__imp_LeaveCriticalSection
0x18001f022  jmp     loc_18001F0BD
0x18001f027  lea     rcx, ds:6[rsi*4]
0x18001f02f  add     rcx, rsi
0x18001f032  lea     rcx, [rdi+rcx*8]
0x18001f036  lea     rdx, [rsp+28h+arg_0]
0x18001f03b  call    ??$_Emplace_back_internal@AEBV?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@?$deque@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@std@@@std@@AEAAXAEBV?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@Z; std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation> const &>(Microsoft::WRL::ComPtr<Sharing::IQueuedOperation> const &)
0x18001f040  cmp     byte ptr [rdi+20h], 0
0x18001f044  jnz     short loc_18001F0AD
0x18001f046  mov     byte ptr [rdi+20h], 1
0x18001f04a  mov     rax, [rdi+18h]
0x18001f04e  test    rax, rax
0x18001f051  js      short loc_18001F068
0x18001f053  cmp     eax, 7FFFFFFFh
0x18001f058  jz      short loc_18001F075
0x18001f05a  lea     rcx, [rax+1]
0x18001f05e  lock cmpxchg [rdi+18h], rcx
0x18001f064  jnz     short loc_18001F04E
0x18001f066  jmp     short loc_18001F075
0x18001f068  lea     rcx, ds:10h[rax*2]; this
0x18001f070  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18001f075  xor     r8d, r8d; pcbe
0x18001f078  mov     rdx, rdi; pv
0x18001f07b  lea     rcx, ?ThreadPoolThunk@OperationQueue@Sharing@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001f082  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001f088  test    eax, eax
0x18001f08a  jnz     short loc_18001F0AD
0x18001f08c  mov     rcx, rdi
0x18001f08f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::Release(void)
0x18001f094  mov     byte ptr [rdi+20h], 0
0x18001f098  test    rbx, rbx
0x18001f09b  jz      short loc_18001F0A6
0x18001f09d  mov     rcx, rbx; lpCriticalSection
0x18001f0a0  call    cs:__imp_LeaveCriticalSection
0x18001f0a6  mov     edi, 80004005h
0x18001f0ab  jmp     short loc_18001F0BD
0x18001f0ad  test    rbx, rbx
0x18001f0b0  jz      short loc_18001F0BB
0x18001f0b2  mov     rcx, rbx; lpCriticalSection
0x18001f0b5  call    cs:__imp_LeaveCriticalSection
0x18001f0bb  xor     edi, edi
0x18001f0bd  lea     rcx, [rsp+28h+arg_0]
0x18001f0c2  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f0c7  mov     eax, edi
0x18001f0c9  mov     rbx, [rsp+28h+arg_10]
0x18001f0ce  mov     rsi, [rsp+28h+arg_18]
0x18001f0d3  add     rsp, 20h
0x18001f0d7  pop     rdi
0x18001f0d8  retn
```
