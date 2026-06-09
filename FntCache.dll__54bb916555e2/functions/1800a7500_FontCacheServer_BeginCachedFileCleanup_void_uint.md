# FontCacheServer::BeginCachedFileCleanup(void *,uint)

- ea: `0x1800a7500`
- end: `0x1800a769c`
- name: `?BeginCachedFileCleanup@FontCacheServer@@AEAAPEAXPEAXI@Z`
- size: `412`
- prototype: `FileCleanup *__fastcall(FontCacheServer *this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800b1ad0`
- `0x1800b2430`

## callees

- `0x180010ca0`
- `0x180011a00`
- `0x180028c50`
- `0x180068e24`
- `0x180076ca4`
- `0x1800a1558`
- `0x1800a1960`
- `0x1800a7500`
- `0x1800a76a4`
- `0x1800aaa58`
- `0x1800b1d64`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a755d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a755d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7662`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7605`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7605`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
FileCleanup *__fastcall FontCacheServer::BeginCachedFileCleanup(FontCacheServer *this, void *a2, unsigned int a3)
{
  FileCleanup **v7; // rsi
  FileCleanup *v8; // rbx
  volatile signed __int32 **v9; // rax
  FileCleanup *v10; // r14
  FileCleanup *v11; // rcx
  FileCleanup *v12; // rbx
  FileCleanup **v13; // rax
  FileCleanup *v14; // [rsp+20h] [rbp-20h] BYREF
  LPCRITICAL_SECTION v15; // [rsp+28h] [rbp-18h] BYREF
  struct DWrite::RefString::Data *v16; // [rsp+30h] [rbp-10h] BYREF
  FileCleanup *v17; // [rsp+38h] [rbp-8h]
  HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp+48h] BYREF

  LODWORD(hObject) = 0;
  LockHolder::LockHolder((LockHolder *)&v15, (FontCacheServer *)((char *)this + 200));
  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (FontCacheServer *)((char *)this + 136));
  if ( *((_BYTE *)this + 176) )
  {
    LeaveCriticalSection(lpCriticalSection);
    LeaveCriticalSection(v15);
    return 0;
  }
  else
  {
    v7 = (FileCleanup **)((char *)this + 248);
    if ( !*((_QWORD *)this + 31) )
    {
      if ( !a3 )
        a3 = (unsigned int)(3 * *((_DWORD *)this + 64)) >> 2;
      v8 = (FileCleanup *)operator new(0x38u);
      v17 = v8;
      v9 = (volatile signed __int32 **)(*(__int64 (__fastcall **)(_QWORD, struct DWrite::RefString::Data **))(**((_QWORD **)this + 7) + 120LL))(
                                         *((_QWORD *)this + 7),
                                         &v16);
      LODWORD(hObject) = 1;
      v10 = FileCleanup::FileCleanup(v8, v9, a3);
      v14 = v10;
      ComPtr<FileCleanup>::AddRef(&v14);
      DWrite::RefString::DecrementRef(v16);
      if ( !*((_QWORD *)this + 30) )
        ThreadpoolWork::Initialize(
          (FontCacheServer *)((char *)this + 240),
          (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))FontCacheServer::CachedFileCleanupCallback,
          this);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 30));
      if ( v7 != &v14 )
      {
        v11 = *v7;
        v14 = 0;
        *v7 = v10;
        ComPtr<IFontSetCache>::Deref(v11);
      }
      ComPtr<FileCleanup>::Deref(&v14);
    }
    v12 = 0;
    if ( a2 )
    {
      v13 = (FileCleanup **)CloneSynchronizationHandle(&hObject, *((_QWORD *)*v7 + 6), a2);
      v12 = *v13;
      *v13 = 0;
      v17 = v12;
      if ( hObject )
        CloseHandle(hObject);
      if ( !v12 )
        OSException::ThrowLastError();
    }
    LeaveCriticalSection(lpCriticalSection);
    LeaveCriticalSection(v15);
    return v12;
  }
}

```

## disassembly

```asm
0x1800a7500  mov     [rsp-28h+arg_8], rbx
0x1800a7505  push    rbp
0x1800a7506  push    rsi
0x1800a7507  push    rdi
0x1800a7508  push    r14
0x1800a750a  push    r15
0x1800a750c  mov     rbp, rsp
0x1800a750f  sub     rsp, 40h
0x1800a7513  mov     r14d, r8d
0x1800a7516  mov     r15, rdx
0x1800a7519  mov     rdi, rcx
0x1800a751c  mov     dword ptr [rbp+hObject], 0
0x1800a7523  lea     rdx, [rcx+0C8h]; struct Lock *
0x1800a752a  lea     rcx, [rbp+var_18]; this
0x1800a752e  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a7533  nop
0x1800a7534  lea     rdx, [rdi+88h]; struct Lock *
0x1800a753b  lea     rcx, [rbp+lpCriticalSection]; this
0x1800a753f  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a7544  nop
0x1800a7545  cmp     byte ptr [rdi+0B0h], 0
0x1800a754c  jz      short loc_1800A756A
0x1800a754e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800a7552  call    cs:__imp_LeaveCriticalSection
0x1800a7558  nop
0x1800a7559  mov     rcx, [rbp+var_18]; lpCriticalSection
0x1800a755d  call    cs:__imp_LeaveCriticalSection
0x1800a7563  xor     eax, eax
0x1800a7565  jmp     loc_1800A768B
0x1800a756a  lea     rsi, [rdi+0F8h]
0x1800a7571  cmp     qword ptr [rsi], 0
0x1800a7575  jnz     loc_1800A7631
0x1800a757b  test    r14d, r14d
0x1800a757e  jnz     short loc_1800A758E
0x1800a7580  mov     eax, [rdi+100h]
0x1800a7586  lea     r14d, [rax+rax*2]
0x1800a758a  shr     r14d, 2
0x1800a758e  mov     ecx, 38h ; '8'; Size
0x1800a7593  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a7598  mov     rbx, rax
0x1800a759b  mov     [rbp+var_8], rax
0x1800a759f  mov     rcx, [rdi+38h]
0x1800a75a3  mov     rdx, [rcx]
0x1800a75a6  mov     rax, [rdx+78h]
0x1800a75aa  lea     rdx, [rbp+var_10]
0x1800a75ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75b3  nop
0x1800a75b4  mov     dword ptr [rbp+hObject], 1
0x1800a75bb  mov     r8d, r14d; unsigned int
0x1800a75be  mov     rdx, rax; struct DWrite::RefString *
0x1800a75c1  mov     rcx, rbx; this
0x1800a75c4  call    ??0FileCleanup@@QEAA@AEBVRefString@DWrite@@I@Z; FileCleanup::FileCleanup(DWrite::RefString const &,uint)
0x1800a75c9  mov     r14, rax
0x1800a75cc  mov     [rbp+var_20], rax
0x1800a75d0  lea     rcx, [rbp+var_20]
0x1800a75d4  call    ?AddRef@?$ComPtr@VFileCleanup@@@@AEBAXXZ; ComPtr<FileCleanup>::AddRef(void)
0x1800a75d9  nop
0x1800a75da  mov     rcx, [rbp+var_10]; struct DWrite::RefString::Data *
0x1800a75de  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a75e3  lea     rbx, [rdi+0F0h]
0x1800a75ea  cmp     qword ptr [rbx], 0
0x1800a75ee  jnz     short loc_1800A7602
0x1800a75f0  mov     r8, rdi; void *
0x1800a75f3  lea     rdx, ?CachedFileCleanupCallback@FontCacheServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x1800a75fa  mov     rcx, rbx; this
0x1800a75fd  call    ?Initialize@ThreadpoolWork@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; ThreadpoolWork::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800a7602  mov     rcx, [rbx]; pwk
0x1800a7605  call    cs:__imp_SubmitThreadpoolWork
0x1800a760b  lea     rax, [rbp+var_20]
0x1800a760f  cmp     rsi, rax
0x1800a7612  jz      short loc_1800A7628
0x1800a7614  mov     rcx, [rsi]
0x1800a7617  mov     [rbp+var_20], 0
0x1800a761f  mov     [rsi], r14
0x1800a7622  call    ?Deref@?$ComPtr@UIFontSetCache@@@@CAXPEAUIFontSetCache@@@Z; ComPtr<IFontSetCache>::Deref(IFontSetCache *)
0x1800a7627  nop
0x1800a7628  lea     rcx, [rbp+var_20]
0x1800a762c  call    ?Deref@?$ComPtr@VFileCleanup@@@@AEAAXXZ; ComPtr<FileCleanup>::Deref(void)
0x1800a7631  xor     ebx, ebx
0x1800a7633  test    r15, r15
0x1800a7636  jz      short loc_1800A7673
0x1800a7638  mov     rdx, [rsi]
0x1800a763b  mov     r8, r15
0x1800a763e  mov     rdx, [rdx+30h]
0x1800a7642  lea     rcx, [rbp+hObject]
0x1800a7646  call    ?CloneSynchronizationHandle@@YA?AVWin32Handle@@PEAX0@Z; CloneSynchronizationHandle(void *,void *)
0x1800a764b  mov     rbx, [rax]
0x1800a764e  mov     qword ptr [rax], 0
0x1800a7655  mov     [rbp+var_8], rbx
0x1800a7659  mov     rcx, [rbp+hObject]; hObject
0x1800a765d  test    rcx, rcx
0x1800a7660  jz      short loc_1800A7668
0x1800a7662  call    cs:__imp_CloseHandle
0x1800a7668  test    rbx, rbx
0x1800a766b  jnz     short loc_1800A7673
0x1800a766d  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800a7673  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800a7677  call    cs:__imp_LeaveCriticalSection
0x1800a767d  nop
0x1800a767e  mov     rcx, [rbp+var_18]; lpCriticalSection
0x1800a7682  call    cs:__imp_LeaveCriticalSection
0x1800a7688  mov     rax, rbx
0x1800a768b  mov     rbx, [rsp+40h+arg_8]
0x1800a7690  add     rsp, 40h
0x1800a7694  pop     r15
0x1800a7696  pop     r14
0x1800a7698  pop     rdi
0x1800a7699  pop     rsi
0x1800a769a  pop     rbp
0x1800a769b  retn
```
