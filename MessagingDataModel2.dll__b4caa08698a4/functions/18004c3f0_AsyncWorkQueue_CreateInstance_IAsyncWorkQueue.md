# AsyncWorkQueue::CreateInstance(IAsyncWorkQueue * *)

- ea: `0x18004c3f0`
- end: `0x18004c50c`
- name: `?CreateInstance@AsyncWorkQueue@@SAJPEAPEAUIAsyncWorkQueue@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct IAsyncWorkQueue **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002d5c0`
- `0x180059560`
- `0x180070620`
- `0x180075134`

## callees

- `0x180003e00`
- `0x180005c50`
- `0x1800089b8`
- `0x18004c3f0`
- `0x1800c6902`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004c441`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004c441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004c4b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004c4b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004c496`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004c496`

## pseudocode

```c
__int64 __fastcall AsyncWorkQueue::CreateInstance(PTP_WORK **a1)
{
  PTP_WORK *v2; // rax
  PTP_WORK *v3; // rbx
  PTP_WORK v4; // rax
  PTP_WORK ThreadpoolWork; // rdi
  struct _TP_WORK *v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  PTP_WORK *v10; // [rsp+20h] [rbp-18h] BYREF

  v2 = (PTP_WORK *)operator new(0x70u);
  v3 = v2;
  if ( !v2 )
  {
    v8 = -2147024882;
    goto LABEL_12;
  }
  memset_0((char *)v2 + 12, 0, 0x64u);
  *((_DWORD *)v3 + 2) = 0;
  *v3 = (PTP_WORK)&AsyncWorkQueue::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v3 + 2), 0, 0);
  utl::list<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *,utl::allocator<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *>>::list<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *,utl::allocator<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *>>(v3 + 7);
  v3[10] = 0;
  *((_DWORD *)v3 + 22) = 0;
  *((_DWORD *)v3 + 23) = 0;
  v3[12] = 0;
  *((_DWORD *)v3 + 26) = 0;
  v4 = *v3;
  v10 = v3;
  (*((void (__fastcall **)(PTP_WORK *))v4 + 1))(v3);
  ThreadpoolWork = CreateThreadpoolWork(AsyncWorkQueue::WorkCallBack, v3, 0);
  v6 = v3[12];
  if ( ThreadpoolWork == v6 )
  {
    ThreadpoolWork = v3[12];
  }
  else
  {
    if ( v6 )
      CloseThreadpoolWork(v3[12]);
    v3[12] = ThreadpoolWork;
  }
  if ( ThreadpoolWork )
  {
    *a1 = v3;
    v8 = 0;
LABEL_12:
    v10 = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return v8;
}

```

## disassembly

```asm
0x18004c3f0  mov     [rsp+arg_8], rbx
0x18004c3f5  mov     [rsp+arg_10], rsi
0x18004c3fa  push    rdi
0x18004c3fb  sub     rsp, 30h
0x18004c3ff  mov     rsi, rcx
0x18004c402  mov     ecx, 70h ; 'p'; Size
0x18004c407  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c40c  mov     rbx, rax
0x18004c40f  test    rax, rax
0x18004c412  jz      loc_18004C4E2
0x18004c418  xor     edx, edx; Val
0x18004c41a  lea     rcx, [rax+0Ch]; void *
0x18004c41e  lea     r8d, [rdx+64h]; Size
0x18004c422  call    memset_0
0x18004c427  lea     rax, ??_7AsyncWorkQueue@@6B@; const AsyncWorkQueue::`vftable'
0x18004c42e  mov     dword ptr [rbx+8], 0
0x18004c435  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004c439  mov     [rbx], rax
0x18004c43c  xor     r8d, r8d; Flags
0x18004c43f  xor     edx, edx; dwSpinCount
0x18004c441  call    cs:__imp_InitializeCriticalSectionEx
0x18004c447  lea     rcx, [rbx+38h]
0x18004c44b  call    ??0?$list@PEAU?$RcsEventNotification@UImsClientEnumerationCompletedEventNotificationArgs@@@@V?$allocator@PEAU?$RcsEventNotification@UImsClientEnumerationCompletedEventNotificationArgs@@@@@utl@@@utl@@QEAA@XZ; utl::list<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *,utl::allocator<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *>>::list<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *,utl::allocator<RcsEventNotification<ImsClientEnumerationCompletedEventNotificationArgs> *>>(void)
0x18004c450  mov     qword ptr [rbx+50h], 0
0x18004c458  mov     rcx, rbx
0x18004c45b  mov     dword ptr [rbx+58h], 0
0x18004c462  mov     dword ptr [rbx+5Ch], 0
0x18004c469  mov     qword ptr [rbx+60h], 0
0x18004c471  mov     dword ptr [rbx+68h], 0
0x18004c478  mov     rax, [rbx]
0x18004c47b  mov     [rsp+38h+var_18], rbx
0x18004c480  mov     rax, [rax+8]
0x18004c484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c489  xor     r8d, r8d; pcbe
0x18004c48c  lea     rcx, ?WorkCallBack@AsyncWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004c493  mov     rdx, rbx; pv
0x18004c496  call    cs:__imp_CreateThreadpoolWork
0x18004c49c  mov     rdi, rax
0x18004c49f  mov     rax, [rbx+60h]
0x18004c4a3  cmp     rdi, rax
0x18004c4a6  jz      short loc_18004C4BC
0x18004c4a8  test    rax, rax
0x18004c4ab  jz      short loc_18004C4B6
0x18004c4ad  mov     rcx, rax; pwk
0x18004c4b0  call    cs:__imp_CloseThreadpoolWork
0x18004c4b6  mov     [rbx+60h], rdi
0x18004c4ba  jmp     short loc_18004C4BF
0x18004c4bc  mov     rdi, rax
0x18004c4bf  test    rdi, rdi
0x18004c4c2  jnz     short loc_18004C4DB
0x18004c4c4  call    cs:__imp_GetLastError
0x18004c4ca  mov     ebx, eax
0x18004c4cc  test    eax, eax
0x18004c4ce  jle     short loc_18004C4F0
0x18004c4d0  movzx   ebx, ax
0x18004c4d3  or      ebx, 80070000h
0x18004c4d9  jmp     short loc_18004C4F0
0x18004c4db  mov     [rsi], rbx
0x18004c4de  xor     ebx, ebx
0x18004c4e0  jmp     short loc_18004C4E7
0x18004c4e2  mov     ebx, 8007000Eh
0x18004c4e7  mov     [rsp+38h+var_18], 0
0x18004c4f0  lea     rcx, [rsp+38h+var_18]
0x18004c4f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c4fa  mov     rsi, [rsp+38h+arg_10]
0x18004c4ff  mov     eax, ebx
0x18004c501  mov     rbx, [rsp+38h+arg_8]
0x18004c506  add     rsp, 30h
0x18004c50a  pop     rdi
0x18004c50b  retn
```
