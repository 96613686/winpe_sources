# Microsoft::CoreUI::Messaging::AnonymousStream::Send(unsigned __int64,void const *,uint)

- ea: `0x1800a2900`
- end: `0x1800a2b1c`
- name: `?Send@AnonymousStream@Messaging@CoreUI@Microsoft@@UEAAJ_KPEBXI@Z`
- size: `540`
- prototype: `int(Microsoft::CoreUI::Messaging::AnonymousStream *__hidden this, unsigned __int64, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800406a0`
- `0x18004140c`
- `0x18004177c`
- `0x18009d670`
- `0x1800a1f68`
- `0x1800a2900`
- `0x1800c89fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a2aed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a2aed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a2972`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a2972`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a29a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2a6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a29a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2a6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2ac0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2adf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2ac0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2a73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2a73`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Messaging::AnonymousStream::Send(
        Microsoft::CoreUI::Messaging::AnonymousStream *this,
        unsigned __int64 a2,
        const void *a3,
        unsigned int a4)
{
  size_t v4; // rbx
  unsigned int v8; // r15d
  void *v9; // rsi
  char *v10; // r14
  void *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 TargetNL; // rax
  unsigned int v15; // ebx
  DWORD v16; // eax
  char v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v19[4]; // [rsp+54h] [rbp-ACh] BYREF
  char *v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+64h] [rbp-9Ch]
  char v23; // [rsp+70h] [rbp-90h] BYREF

  v4 = a4;
  if ( !a2 )
    return 2276591622LL;
  if ( !a3 && a4 )
    return 2147500035LL;
  v8 = a4 + 16;
  if ( a4 + 16 >= 0x100 )
  {
    v11 = malloc(v8);
    v9 = v11;
    if ( !v11 )
      Cn::Process::NotifyOutOfMemory(v8);
    v10 = (char *)v11;
  }
  else
  {
    v9 = 0;
    v10 = &v23;
  }
  *((_DWORD *)v10 + 2) = v8;
  memcpy_0(v10 + 16, a3, v4);
  AcquireSRWLockShared(&Cn::Threading::InterconnectQueue::s_lockType);
  if ( a2 >> 46 < (unsigned int)qword_1801050A8
    && (_mm_lfence(), (v12 = *((_QWORD *)Cn::Threading::InterconnectQueue::s_arKeyToQueue + (a2 >> 46))) != 0)
    && *(_BYTE *)(v12 + 144) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    v18 = 0;
    v17 = 0;
    CurrentThreadId = GetCurrentThreadId();
    TargetNL = Microsoft::CoreUI::Identity::IdentityTable::GetTargetNL(
                 (unsigned int)&Microsoft::CoreUI::Dispatch::ThreadContext::s_identityTable,
                 CurrentThreadId,
                 a2,
                 (unsigned int)&v18,
                 (__int64)&v17);
    if ( v17 )
    {
      if ( v18 )
      {
        v15 = -2018375675;
      }
      else
      {
        *(_QWORD *)v10 = TargetNL;
        v22 = 0;
        v20 = v10;
        v21 = v4 + 16;
        AcquireSRWLockShared((PSRWLOCK)(v12 + 96));
        v16 = GetCurrentThreadId();
        Cn::Threading::InterconnectQueue::PostItem_LockedByCaller(
          v12,
          *(unsigned int *)(v12 + 160),
          &v20,
          1,
          -16,
          v16,
          0,
          0,
          0,
          v19);
        if ( v12 != -96 )
          ReleaseSRWLockShared((PSRWLOCK)(v12 + 96));
        v15 = 0;
      }
    }
    else
    {
      v15 = -2018375674;
    }
    Cn::Engine::ProcessItem::Release((Cn::Engine::ProcessItem *)v12);
  }
  else
  {
    v15 = -2018375674;
  }
  ReleaseSRWLockShared(&Cn::Threading::InterconnectQueue::s_lockType);
  if ( v9 )
    free(v9);
  return v15;
}

```

## disassembly

```asm
0x1800a2900  mov     [rsp-8+arg_0], rbx
0x1800a2905  push    rbp
0x1800a2906  push    rsi
0x1800a2907  push    rdi
0x1800a2908  push    r12
0x1800a290a  push    r13
0x1800a290c  push    r14
0x1800a290e  push    r15
0x1800a2910  lea     rbp, [rsp-80h]
0x1800a2915  sub     rsp, 180h
0x1800a291c  mov     rax, cs:__security_cookie
0x1800a2923  xor     rax, rsp
0x1800a2926  mov     [rbp+0B0h+var_40], rax
0x1800a292a  mov     ebx, r9d
0x1800a292d  mov     r13, r8
0x1800a2930  mov     r12, rdx
0x1800a2933  test    rdx, rdx
0x1800a2936  jnz     short loc_1800A2942
0x1800a2938  mov     eax, 87B20806h
0x1800a293d  jmp     loc_1800A2AF5
0x1800a2942  test    r13, r13
0x1800a2945  jnz     short loc_1800A2956
0x1800a2947  test    r9d, r9d
0x1800a294a  jz      short loc_1800A2956
0x1800a294c  mov     eax, 80004003h
0x1800a2951  jmp     loc_1800A2AF5
0x1800a2956  lea     r15d, [rbx+10h]
0x1800a295a  cmp     r15d, 100h
0x1800a2961  jnb     short loc_1800A296C
0x1800a2963  xor     esi, esi
0x1800a2965  lea     r14, [rsp+1B0h+var_140]
0x1800a296a  jmp     short loc_1800A298B
0x1800a296c  mov     ecx, r15d; Size
0x1800a296f  mov     edi, r15d
0x1800a2972  call    cs:__imp_malloc
0x1800a2978  mov     rsi, rax
0x1800a297b  test    rax, rax
0x1800a297e  jnz     short loc_1800A2988
0x1800a2980  mov     ecx, edi; unsigned __int64
0x1800a2982  call    ?NotifyOutOfMemory@Process@Cn@@SAX_K@Z; Cn::Process::NotifyOutOfMemory(unsigned __int64)
0x1800a2988  mov     r14, rax
0x1800a298b  mov     r8, rbx; Size
0x1800a298e  mov     [r14+8], r15d
0x1800a2992  lea     rcx, [r14+10h]; void *
0x1800a2996  mov     rdx, r13; Src
0x1800a2999  call    memcpy_0
0x1800a299e  lea     rcx, ?s_lockType@InterconnectQueue@Threading@Cn@@0USlimLock@23@A; SRWLock
0x1800a29a5  call    cs:__imp_AcquireSRWLockShared
0x1800a29ab  mov     rax, r12
0x1800a29ae  shr     rax, 2Eh
0x1800a29b2  cmp     eax, dword ptr cs:qword_1801050A8
0x1800a29b8  jnb     loc_1800A2AD3
0x1800a29be  lfence
0x1800a29c1  mov     ecx, eax
0x1800a29c3  xor     r13d, r13d
0x1800a29c6  mov     rax, cs:?s_arKeyToQueue@InterconnectQueue@Threading@Cn@@0V?$GlobalVectorF@PEAVInterconnectQueue@Threading@Cn@@@Engine@3@A; Cn::Engine::GlobalVectorF<Cn::Threading::InterconnectQueue *> Cn::Threading::InterconnectQueue::s_arKeyToQueue
0x1800a29cd  mov     rdi, [rax+rcx*8]
0x1800a29d1  test    rdi, rdi
0x1800a29d4  jz      loc_1800A2AD3
0x1800a29da  cmp     [rdi+90h], r13b
0x1800a29e1  jz      loc_1800A2AD3
0x1800a29e7  lock inc dword ptr [rdi+8]
0x1800a29eb  mov     ebx, [rdi+0FCh]
0x1800a29f1  mov     rax, 1FFFFFFFFFFFh
0x1800a29fb  and     r12, rax
0x1800a29fe  shl     rbx, 2Eh
0x1800a2a02  or      rbx, r12
0x1800a2a05  mov     [rsp+1B0h+var_15F], r13b
0x1800a2a0a  mov     [rsp+1B0h+var_160], r13b
0x1800a2a0f  call    cs:__imp_GetCurrentThreadId
0x1800a2a15  lea     rcx, [rsp+1B0h+var_160]
0x1800a2a1a  mov     r8, rbx
0x1800a2a1d  mov     [rsp+1B0h+var_190], rcx
0x1800a2a22  lea     r9, [rsp+1B0h+var_15F]
0x1800a2a27  lea     rcx, ?s_identityTable@ThreadContext@Dispatch@CoreUI@Microsoft@@2UIdentityTable@Identity@34@A; Microsoft::CoreUI::Identity::IdentityTable Microsoft::CoreUI::Dispatch::ThreadContext::s_identityTable
0x1800a2a2e  mov     edx, eax
0x1800a2a30  call    ?GetTargetNL@IdentityTable@Identity@CoreUI@Microsoft@@QEAA_KIUHIDENTITY@34@U?$Ref@_N@CFlat@@1@Z; Microsoft::CoreUI::Identity::IdentityTable::GetTargetNL(uint,Microsoft::CoreUI::HIDENTITY,CFlat::Ref<bool>,CFlat::Ref<bool>)
0x1800a2a35  cmp     [rsp+1B0h+var_160], r13b
0x1800a2a3a  jnz     short loc_1800A2A46
0x1800a2a3c  mov     ebx, 87B20806h
0x1800a2a41  jmp     loc_1800A2AC9
0x1800a2a46  cmp     [rsp+1B0h+var_15F], r13b
0x1800a2a4b  jz      short loc_1800A2A54
0x1800a2a4d  mov     ebx, 87B20805h
0x1800a2a52  jmp     short loc_1800A2AC9
0x1800a2a54  lea     rbx, [rdi+60h]
0x1800a2a58  mov     [r14], rax
0x1800a2a5b  mov     rcx, rbx; SRWLock
0x1800a2a5e  mov     [rsp+1B0h+var_14C], r13d
0x1800a2a63  mov     [rsp+1B0h+var_158], r14
0x1800a2a68  mov     [rsp+1B0h+var_150], r15d
0x1800a2a6d  call    cs:__imp_AcquireSRWLockShared
0x1800a2a73  call    cs:__imp_GetCurrentThreadId
0x1800a2a79  mov     edx, [rdi+0A0h]
0x1800a2a7f  lea     rcx, [rsp+1B0h+var_15C]
0x1800a2a84  mov     [rsp+1B0h+var_168], rcx
0x1800a2a89  lea     r8, [rsp+1B0h+var_158]
0x1800a2a8e  mov     [rsp+1B0h+var_170], r13d
0x1800a2a93  mov     r9d, 1
0x1800a2a99  mov     [rsp+1B0h+var_178], r13d
0x1800a2a9e  mov     rcx, rdi
0x1800a2aa1  mov     [rsp+1B0h+var_180], r13d
0x1800a2aa6  mov     [rsp+1B0h+var_188], eax
0x1800a2aaa  mov     [rsp+1B0h+var_190], 0FFFFFFFFFFFFFFF0h
0x1800a2ab3  call    ?PostItem_LockedByCaller@InterconnectQueue@Threading@Cn@@SA_NPEAV123@IPEAUInterconnectItem@23@HW4RegistrarClientId@Registrar@CoreUI@Microsoft@@IIIW4InterconnectBufferFlags@23@PEAW4923@@Z; Cn::Threading::InterconnectQueue::PostItem_LockedByCaller(Cn::Threading::InterconnectQueue *,uint,Cn::Threading::InterconnectItem *,int,Microsoft::CoreUI::Registrar::RegistrarClientId,uint,uint,uint,Cn::Threading::InterconnectBufferFlags,Cn::Threading::InterconnectBufferFlags *)
0x1800a2ab8  test    rbx, rbx
0x1800a2abb  jz      short loc_1800A2AC6
0x1800a2abd  mov     rcx, rbx; SRWLock
0x1800a2ac0  call    cs:__imp_ReleaseSRWLockShared
0x1800a2ac6  mov     ebx, r13d
0x1800a2ac9  mov     rcx, rdi; this
0x1800a2acc  call    ?Release@ProcessItem@Engine@Cn@@QEAAXXZ; Cn::Engine::ProcessItem::Release(void)
0x1800a2ad1  jmp     short loc_1800A2AD8
0x1800a2ad3  mov     ebx, 87B20806h
0x1800a2ad8  lea     rcx, ?s_lockType@InterconnectQueue@Threading@Cn@@0USlimLock@23@A; SRWLock
0x1800a2adf  call    cs:__imp_ReleaseSRWLockShared
0x1800a2ae5  test    rsi, rsi
0x1800a2ae8  jz      short loc_1800A2AF3
0x1800a2aea  mov     rcx, rsi; Block
0x1800a2aed  call    cs:__imp_free
0x1800a2af3  mov     eax, ebx
0x1800a2af5  mov     rcx, [rbp+0B0h+var_40]
0x1800a2af9  xor     rcx, rsp; StackCookie
0x1800a2afc  call    __security_check_cookie
0x1800a2b01  mov     rbx, [rsp+1B0h+arg_0]
0x1800a2b09  add     rsp, 180h
0x1800a2b10  pop     r15
0x1800a2b12  pop     r14
0x1800a2b14  pop     r13
0x1800a2b16  pop     r12
0x1800a2b18  pop     rdi
0x1800a2b19  pop     rsi
0x1800a2b1a  pop     rbp
0x1800a2b1b  retn
```
