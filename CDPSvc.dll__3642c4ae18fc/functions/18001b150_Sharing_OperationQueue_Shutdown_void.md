# Sharing::OperationQueue::Shutdown(void)

- ea: `0x18001b150`
- end: `0x18001b3fd`
- name: `?Shutdown@OperationQueue@Sharing@@QEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180047e98`
- `0x180050d7c`

## callees

- `0x180004928`
- `0x180010d04`
- `0x18001b150`
- `0x18001b404`
- `0x18001efa0`
- `0x1800225a0`
- `0x180022614`
- `0x180026014`
- `0x1800457b8`
- `0x18004c4c0`
- `0x18004f478`
- `0x18004fce0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b35a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b35a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Sharing::OperationQueue::Shutdown(char *pv)
{
  struct Sharing::IQueuedOperation *v2; // rbx
  int v3; // r15d
  __int64 v4; // r9
  struct Microsoft::WRL::Wrappers::Event *v5; // r8
  struct Microsoft::WRL::Wrappers::Event *v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // esi
  char *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rsi
  struct Microsoft::WRL::Wrappers::Event *v16; // r8
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  struct Sharing::IQueuedOperation *v19; // [rsp+38h] [rbp-C8h]
  char *v20; // [rsp+40h] [rbp-C0h]
  char v21; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[240]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v19 = 0;
  `eh vector constructor iterator'(
    v22,
    0x28u,
    6u,
    (void (*)(void *))std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>,
    std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::~deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 288));
  v20 = pv + 288;
  v3 = 5;
  v4 = 5;
  do
  {
    v5 = (struct Microsoft::WRL::Wrappers::Event *)&pv[40 * v4 + 48];
    v6 = (struct Microsoft::WRL::Wrappers::Event *)&v22[40 * v4];
    if ( v5 != v6 )
    {
      v7 = *(_QWORD **)v5;
      *(_QWORD *)v5 = *(_QWORD *)v6;
      *(_QWORD *)v6 = v7;
      if ( *(_QWORD *)v5 )
        **(_QWORD **)v5 = v5;
      if ( *(_QWORD *)v6 )
        **(_QWORD **)v6 = v6;
      v8 = *((_QWORD *)v5 + 1);
      *((_QWORD *)v5 + 1) = *((_QWORD *)v6 + 1);
      *((_QWORD *)v6 + 1) = v8;
      v9 = *((_QWORD *)v5 + 2);
      *((_QWORD *)v5 + 2) = *((_QWORD *)v6 + 2);
      *((_QWORD *)v6 + 2) = v9;
      v10 = *((_QWORD *)v5 + 3);
      *((_QWORD *)v5 + 3) = *((_QWORD *)v6 + 3);
      *((_QWORD *)v6 + 3) = v10;
      v11 = *((_QWORD *)v5 + 4);
      *((_QWORD *)v5 + 4) = *((_QWORD *)v6 + 4);
      *((_QWORD *)v6 + 4) = v11;
    }
    --v4;
  }
  while ( v4 );
  if ( pv[32] )
  {
    v12 = *((_DWORD *)pv + 9);
    if ( v12 != GetCurrentThreadId() )
    {
      v13 = (char *)Microsoft::WRL::Details::Make<Sharing::WaitOperation,>(&v18);
      v2 = 0;
      if ( &v21 != v13 )
      {
        v2 = *(struct Sharing::IQueuedOperation **)v13;
        *(_QWORD *)v13 = 0;
      }
      v19 = v2;
      v14 = v18;
      if ( v18 )
      {
        v18 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::ISharingSessionMessageReceivedEventArgs>::Release(v14);
      }
      if ( v2 )
        Sharing::OperationQueue::EnqueueOperation(pv, v2);
    }
  }
  pv[34] = 1;
  if ( pv != (char *)-288LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 288));
  do
  {
    while ( *(_QWORD *)&v22[40 * v3 + 32] )
    {
      v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v22[40 * v3 + 8]
                                  + 8 * ((*(_QWORD *)&v22[40 * v3 + 24] >> 1) & (*(_QWORD *)&v22[40 * v3 + 16] - 1LL)))
                      + 8 * (*(_QWORD *)&v22[40 * v3 + 24] & 1LL));
      v15 = v18;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 64LL))(v15);
      std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::pop_front(&v22[40 * v3]);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v18);
    }
    --v3;
  }
  while ( v3 > 0 );
  if ( v2 && Sharing::WaitOperation::Wait(v2, 0x7D0u, v5) < 0 )
  {
    v18 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(pv + 288));
    Microsoft::WRL::ComPtr<ICDPDevice>::operator=(&v18, pv + 40);
    if ( pv != (char *)-288LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 288));
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18);
    Sharing::WaitOperation::Wait(v2, 0x7530u, v16);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v18);
  }
  `eh vector destructor iterator'(
    v22,
    0x28u,
    6u,
    std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::~deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>);
  if ( v2 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::ISharingSessionMessageReceivedEventArgs>::Release(v2);
  return 0;
}

```

## disassembly

```asm
0x18001b150  mov     [rsp-8+arg_8], rbx
0x18001b155  mov     [rsp-8+arg_10], rsi
0x18001b15a  push    rbp
0x18001b15b  push    rdi
0x18001b15c  push    r12
0x18001b15e  push    r14
0x18001b160  push    r15
0x18001b162  lea     rbp, [rsp-50h]
0x18001b167  sub     rsp, 150h
0x18001b16e  mov     rax, cs:__security_cookie
0x18001b175  xor     rax, rsp
0x18001b178  mov     [rbp+70h+var_30], rax
0x18001b17c  mov     r14, rcx
0x18001b17f  xor     ebx, ebx
0x18001b181  mov     [rsp+170h+var_138], rbx
0x18001b186  lea     rsi, ??1?$deque@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::~deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>(void)
0x18001b18d  mov     [rsp+170h+var_150], rsi; void (*)(void *)
0x18001b192  lea     r9, ??0?$deque@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18001b199  lea     edx, [rbx+28h]; unsigned __int64
0x18001b19c  lea     r8d, [rbx+6]; unsigned __int64
0x18001b1a0  lea     rcx, [rsp+170h+var_120]; void *
0x18001b1a5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001b1aa  nop
0x18001b1ab  lea     rdi, [r14+120h]
0x18001b1b2  mov     rcx, rdi; lpCriticalSection
0x18001b1b5  call    cs:__imp_EnterCriticalSection
0x18001b1bb  mov     [rsp+170h+var_130], rdi
0x18001b1c0  lea     r15d, [rbx+5]
0x18001b1c4  mov     r9d, r15d
0x18001b1c7  lea     rax, [r9+r9*4]
0x18001b1cb  lea     r8, [r14+30h]
0x18001b1cf  lea     r8, [r8+rax*8]
0x18001b1d3  lea     rdx, [rsp+170h+var_120]
0x18001b1d8  lea     rdx, [rdx+rax*8]
0x18001b1dc  cmp     r8, rdx
0x18001b1df  jz      short loc_18001B243
0x18001b1e1  mov     rcx, [r8]
0x18001b1e4  mov     rax, [rdx]
0x18001b1e7  mov     [r8], rax
0x18001b1ea  mov     [rdx], rcx
0x18001b1ed  mov     rax, [r8]
0x18001b1f0  test    rax, rax
0x18001b1f3  jz      short loc_18001B1F8
0x18001b1f5  mov     [rax], r8
0x18001b1f8  mov     rax, [rdx]
0x18001b1fb  test    rax, rax
0x18001b1fe  jz      short loc_18001B203
0x18001b200  mov     [rax], rdx
0x18001b203  mov     rcx, [r8+8]
0x18001b207  mov     rax, [rdx+8]
0x18001b20b  mov     [r8+8], rax
0x18001b20f  mov     [rdx+8], rcx
0x18001b213  mov     rcx, [r8+10h]
0x18001b217  mov     rax, [rdx+10h]
0x18001b21b  mov     [r8+10h], rax
0x18001b21f  mov     [rdx+10h], rcx
0x18001b223  mov     rcx, [r8+18h]
0x18001b227  mov     rax, [rdx+18h]
0x18001b22b  mov     [r8+18h], rax
0x18001b22f  mov     [rdx+18h], rcx
0x18001b233  mov     rcx, [r8+20h]
0x18001b237  mov     rax, [rdx+20h]
0x18001b23b  mov     [r8+20h], rax
0x18001b23f  mov     [rdx+20h], rcx
0x18001b243  sub     r9, 1
0x18001b247  jnz     loc_18001B1C7
0x18001b24d  cmp     [r14+20h], r9b
0x18001b251  jz      short loc_18001B2AE
0x18001b253  mov     esi, [r14+24h]
0x18001b257  call    cs:__imp_GetCurrentThreadId
0x18001b25d  cmp     esi, eax
0x18001b25f  jz      short loc_18001B2AE
0x18001b261  lea     rcx, [rsp+170h+var_140]
0x18001b266  call    ??$Make@VWaitOperation@Sharing@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWaitOperation@Sharing@@@12@XZ; Microsoft::WRL::Details::Make<Sharing::WaitOperation,>(void)
0x18001b26b  xor     ebx, ebx
0x18001b26d  lea     rcx, [rsp+170h+var_128]
0x18001b272  cmp     rcx, rax
0x18001b275  jz      short loc_18001B281
0x18001b277  mov     rbx, [rax]
0x18001b27a  mov     qword ptr [rax], 0
0x18001b281  mov     [rsp+170h+var_138], rbx
0x18001b286  mov     rcx, [rsp+170h+var_140]
0x18001b28b  test    rcx, rcx
0x18001b28e  jz      short loc_18001B29E
0x18001b290  mov     [rsp+170h+var_140], 0
0x18001b299  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UISharingSessionMessageReceivedEventArgs@SharingPlatform@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::ISharingSessionMessageReceivedEventArgs>::Release(void)
0x18001b29e  test    rbx, rbx
0x18001b2a1  jz      short loc_18001B2AE
0x18001b2a3  mov     rdx, rbx; struct Sharing::IQueuedOperation *
0x18001b2a6  mov     rcx, r14; pv
0x18001b2a9  call    ?EnqueueOperation@OperationQueue@Sharing@@QEAAJPEAUIQueuedOperation@2@@Z; Sharing::OperationQueue::EnqueueOperation(Sharing::IQueuedOperation *)
0x18001b2ae  mov     byte ptr [r14+22h], 1
0x18001b2b3  test    rdi, rdi
0x18001b2b6  jz      short loc_18001B2C1
0x18001b2b8  mov     rcx, rdi; lpCriticalSection
0x18001b2bb  call    cs:__imp_LeaveCriticalSection
0x18001b2c1  mov     eax, r15d
0x18001b2c4  lea     r12, [rax+rax*4]
0x18001b2c8  cmp     [rsp+r12*8+170h+var_100], 0
0x18001b2ce  jz      short loc_18001B330
0x18001b2d0  mov     rsi, [rsp+r12*8+170h+var_108]
0x18001b2d5  mov     rcx, [rsp+r12*8+170h+var_110]
0x18001b2da  dec     rcx
0x18001b2dd  mov     rax, rsi
0x18001b2e0  shr     rax, 1
0x18001b2e3  and     rcx, rax
0x18001b2e6  mov     rax, [rsp+r12*8+170h+var_118]
0x18001b2eb  and     esi, 1
0x18001b2ee  mov     rax, [rax+rcx*8]
0x18001b2f2  mov     rsi, [rax+rsi*8]
0x18001b2f6  mov     [rsp+170h+var_140], rsi
0x18001b2fb  lea     rcx, [rsp+170h+var_140]
0x18001b300  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18001b305  nop
0x18001b306  mov     rax, [rsi]
0x18001b309  mov     rcx, rsi
0x18001b30c  mov     rax, [rax+40h]
0x18001b310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b315  lea     rcx, [rsp+170h+var_120]
0x18001b31a  lea     rcx, [rcx+r12*8]
0x18001b31e  call    ?pop_front@?$deque@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@std@@@std@@QEAAXXZ; std::deque<Microsoft::WRL::ComPtr<Sharing::IQueuedOperation>>::pop_front(void)
0x18001b323  nop
0x18001b324  lea     rcx, [rsp+170h+var_140]
0x18001b329  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001b32e  jmp     short loc_18001B2C8
0x18001b330  dec     r15d
0x18001b333  test    r15d, r15d
0x18001b336  jg      short loc_18001B2C1
0x18001b338  test    rbx, rbx
0x18001b33b  jz      short loc_18001B3AB
0x18001b33d  mov     edx, 7D0h; unsigned int
0x18001b342  mov     rcx, rbx; this
0x18001b345  call    ?Wait@WaitOperation@Sharing@@QEAAJKPEAVEvent@Wrappers@WRL@Microsoft@@@Z; Sharing::WaitOperation::Wait(ulong,Microsoft::WRL::Wrappers::Event *)
0x18001b34a  test    eax, eax
0x18001b34c  jns     short loc_18001B3AB
0x18001b34e  mov     [rsp+170h+var_140], 0
0x18001b357  mov     rcx, rdi; lpCriticalSection
0x18001b35a  call    cs:__imp_EnterCriticalSection
0x18001b360  lea     rdx, [r14+28h]
0x18001b364  lea     rcx, [rsp+170h+var_140]
0x18001b369  call    ??4?$ComPtr@VICDPDevice@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ICDPDevice>::operator=(Microsoft::WRL::ComPtr<ICDPDevice> const &)
0x18001b36e  test    rdi, rdi
0x18001b371  jz      short loc_18001B37C
0x18001b373  mov     rcx, rdi; lpCriticalSection
0x18001b376  call    cs:__imp_LeaveCriticalSection
0x18001b37c  mov     rcx, [rsp+170h+var_140]
0x18001b381  test    rcx, rcx
0x18001b384  jz      short loc_18001B392
0x18001b386  mov     rax, [rcx]
0x18001b389  mov     rax, [rax+40h]
0x18001b38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b392  mov     edx, 7530h; unsigned int
0x18001b397  mov     rcx, rbx; this
0x18001b39a  call    ?Wait@WaitOperation@Sharing@@QEAAJKPEAVEvent@Wrappers@WRL@Microsoft@@@Z; Sharing::WaitOperation::Wait(ulong,Microsoft::WRL::Wrappers::Event *)
0x18001b39f  nop
0x18001b3a0  lea     rcx, [rsp+170h+var_140]
0x18001b3a5  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001b3aa  nop
0x18001b3ab  lea     r9, ??1?$deque@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIQueuedOperation@Sharing@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18001b3b2  mov     edx, 28h ; '('; unsigned __int64
0x18001b3b7  lea     r8d, [rdx-22h]; unsigned __int64
0x18001b3bb  lea     rcx, [rsp+170h+var_120]; void *
0x18001b3c0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001b3c5  nop
0x18001b3c6  test    rbx, rbx
0x18001b3c9  jz      short loc_18001B3D3
0x18001b3cb  mov     rcx, rbx
0x18001b3ce  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UISharingSessionMessageReceivedEventArgs@SharingPlatform@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::ISharingSessionMessageReceivedEventArgs>::Release(void)
0x18001b3d3  xor     eax, eax
0x18001b3d5  mov     rcx, [rbp+70h+var_30]
0x18001b3d9  xor     rcx, rsp; StackCookie
0x18001b3dc  call    __security_check_cookie
0x18001b3e1  lea     r11, [rsp+170h+var_20]
0x18001b3e9  mov     rbx, [r11+38h]
0x18001b3ed  mov     rsi, [r11+40h]
0x18001b3f1  mov     rsp, r11
0x18001b3f4  pop     r15
0x18001b3f6  pop     r14
0x18001b3f8  pop     r12
0x18001b3fa  pop     rdi
0x18001b3fb  pop     rbp
0x18001b3fc  retn
```
