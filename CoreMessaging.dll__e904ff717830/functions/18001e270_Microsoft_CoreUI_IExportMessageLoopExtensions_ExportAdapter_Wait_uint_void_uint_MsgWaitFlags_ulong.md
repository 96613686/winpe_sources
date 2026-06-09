# Microsoft::CoreUI::IExportMessageLoopExtensions::ExportAdapter$::Wait(uint,void * *,uint,MsgWaitFlags,ulong *)

- ea: `0x18001e270`
- end: `0x18001e757`
- name: `?Wait@ExportAdapter$@IExportMessageLoopExtensions@CoreUI@Microsoft@@UEAAJIPEAPEAXIW4MsgWaitFlags@@PEAK@Z`
- size: `1255`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001e270`
- `0x18001ffcc`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x18008ae1c`
- `0x1800c7f4c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e4f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e4f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e2e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e2e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e6e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e6e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e74b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e74b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e6d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e6d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e30c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e6c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e30c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e6c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e366`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e481`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e366`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e481`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e302`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e33d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e352`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e46e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e54d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e5b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e6ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e302`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e33d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e352`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e46e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e54d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e5b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e6ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageLoopExtensions::ExportAdapter$::Wait(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        int a5,
        char *a6)
{
  __int64 v7; // rbx
  LPVOID v8; // rbx
  struct Cn::Context *Value; // rdi
  char v10; // r15
  __int64 v11; // r14
  int v12; // ecx
  int v13; // eax
  const char16_t *v14; // rcx
  const char16_t *v15; // rcx
  int v16; // r12d
  char *v17; // r14
  __int64 v18; // rdi
  int v19; // eax
  __int64 *v20; // r10
  int v21; // edx
  __int64 v22; // r9
  __int64 *v23; // rax
  const void *ComInterface; // rcx
  int v25; // r15d
  int v26; // r14d
  const char16_t *v27; // rcx
  _QWORD *v28; // rdi
  __int64 v29; // rcx
  __int64 v31; // rdx
  _QWORD *v32; // rbx
  __int64 v33; // r8
  __int64 v35; // rcx
  void (__fastcall *v36)(__int64, __int64, __int64); // rax
  __int64 v37; // rax
  int v38; // r14d
  HANDLE CurrentThread; // rax
  DWORD v40; // eax
  int v41; // [rsp+40h] [rbp-58h]
  char v42; // [rsp+48h] [rbp-50h] BYREF
  void *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v44; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v45; // [rsp+A8h] [rbp+10h]
  __int64 v46; // [rsp+B0h] [rbp+18h]
  int v47; // [rsp+B8h] [rbp+20h]

  v47 = a4;
  v46 = a3;
  v45 = a2;
  v7 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v7 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)a1, retaddr);
  v8 = *(LPVOID *)(v7 + 16);
  if ( !v8 || !*((_BYTE *)v8 + 79) || TlsGetValue(Cn::Context::s_tlsStorage) != v8 )
  {
    Value = (struct Cn::Context *)v8;
    v10 = 0;
    while ( 1 )
    {
      if ( Value )
      {
        v11 = *((_QWORD *)Value + 11);
        if ( v11 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
          v12 = *(_DWORD *)(v11 + 60);
          *(_DWORD *)(v11 + 60) = v12 + 1;
          if ( !v12 )
          {
            *(_QWORD *)(v11 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
            *(_DWORD *)(v11 + 72) = GetCurrentThreadId();
          }
          v10 = 1;
        }
        v13 = *((_DWORD *)Value + 18);
        if ( !v13 )
        {
          if ( v8 && Value != v8 )
            CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
          if ( v11 )
          {
            if ( TlsGetValue(Cn::Context::s_tlsStorage) )
              CFlat::Abandonment::Fail(v14);
            if ( TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
              CFlat::Abandonment::Fail(v15);
            _InterlockedIncrement((volatile signed __int32 *)Value + 2);
          }
          break;
        }
        if ( v13 == 2 )
        {
          v37 = *((_QWORD *)Value + 12);
          if ( v37 )
            v38 = *(_DWORD *)(v37 + 152);
          else
            v38 = 0;
          if ( v38 != GetCurrentThreadId() )
          {
            CurrentThread = GetCurrentThread();
            WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
          }
          if ( Cn::Process::Host )
            (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
              Cn::Process::Host,
              retaddr);
          v16 = -2018443005;
          CFlat::EntryExit::OnEndCallToCFlat(Value);
          goto LABEL_19;
        }
        if ( v10 )
        {
          Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v11);
          v10 = 0;
        }
      }
      if ( !v8 )
      {
        Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
        if ( !Value )
        {
          Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
          if ( !Value )
          {
            v41 = -2018443007;
            LODWORD(v44) = -2018443007;
            if ( !Cn::Process::Host
              || ((*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
                    Cn::Process::Host,
                    &v44,
                    retaddr),
                  v41 = v44,
                  (int)v44 < 0) )
            {
              v16 = v41;
              goto LABEL_19;
            }
          }
        }
      }
    }
  }
  v16 = 0;
LABEL_19:
  if ( v16 >= 0 )
  {
    if ( !v8 )
      v8 = TlsGetValue(Cn::Context::s_tlsStorage);
    v17 = a6;
    if ( a6 )
      *(_DWORD *)a6 = 0;
    v18 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
    v44 = v18;
    if ( v18 )
    {
      v19 = *(_DWORD *)(v18 + 16);
      if ( v19 > 0 )
        *(_DWORD *)(v18 + 16) = v19 + 1;
    }
    v20 = *(__int64 **)(v18 + 8);
    v21 = 0;
    v22 = *(unsigned __int16 *)v20;
    while ( 1 )
    {
      if ( v21 >= (int)v22 )
      {
        ComInterface = 0;
        goto LABEL_59;
      }
      v23 = &v20[2 * (v21 - v22)];
      if ( &Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$ == (__int64 *)*v23 )
        break;
      ++v21;
    }
    ComInterface = (const void *)v23[1];
    if ( ComInterface )
      goto LABEL_31;
LABEL_59:
    if ( v18 && v20 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v18,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$);
LABEL_31:
    v25 = (*(__int64 (__fastcall **)(const void *, __int64, _QWORD, __int64, int, int))(*(_QWORD *)ComInterface + 8LL))(
            ComInterface,
            v18,
            v45,
            v46,
            v47,
            a5);
    if ( v18 )
      System::Object::Release$((System::Object *)v18);
    if ( v17 && &v42 != v17 )
      *(_DWORD *)v17 = v25;
    v26 = *((_DWORD *)v8 + 28);
    *((_DWORD *)v8 + 28) = 0;
    if ( !*((_BYTE *)v8 + 79) )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) && !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
        CFlat::Abandonment::Fail(v27);
      v28 = (_QWORD *)*((_QWORD *)v8 + 10);
      *((_QWORD *)v8 + 10) = 0;
      v29 = *((_QWORD *)v8 + 11);
      if ( (*(_DWORD *)(v29 + 60))-- == 1 )
      {
        *(_QWORD *)(v29 + 64) = 0;
        *(_DWORD *)(v29 + 72) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)v8 + 2) = 1;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 8LL))(v8);
        (**(void (__fastcall ***)(LPVOID, __int64))v8)(v8, 1);
      }
      if ( v28 )
      {
        while ( 1 )
        {
          v32 = (_QWORD *)*v28;
          *v28 = 0;
          v33 = v28[3];
          if ( !*((_BYTE *)v28 + 8) )
            break;
          if ( *((_BYTE *)v28 + 8) == 1 )
          {
            v36 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v33 + 16LL);
LABEL_71:
            v35 = v28[3];
            goto LABEL_52;
          }
          if ( *((_BYTE *)v28 + 8) == 2 )
          {
            v35 = v28[2];
            v36 = (void (__fastcall *)(__int64, __int64, __int64))v28[3];
LABEL_52:
            v36(v35, v31, v33);
          }
          free(v28);
          v28 = v32;
          if ( !v32 )
            goto LABEL_48;
        }
        v36 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v33 + 8LL);
        goto LABEL_71;
      }
LABEL_48:
      if ( v26 )
      {
        v40 = CFlat::Win32ErrorHandling::ConvertHRToWin32Error(v26);
        SetLastError(v40);
      }
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001e270  mov     [rsp+arg_18], r9d
0x18001e275  mov     [rsp+arg_10], r8
0x18001e27a  mov     [rsp+arg_8], edx
0x18001e27e  push    rbx
0x18001e27f  push    rsi
0x18001e280  push    rdi
0x18001e281  push    r12
0x18001e283  push    r13
0x18001e285  push    r14
0x18001e287  push    r15
0x18001e289  sub     rsp, 60h
0x18001e28d  mov     r13, rcx
0x18001e290  mov     rbx, [rcx+10h]
0x18001e294  cmp     qword ptr [rbx+18h], 0
0x18001e299  jz      loc_18001E536
0x18001e29f  mov     r12, [rsp+98h]
0x18001e2a7  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18001e2ae  jz      loc_18001E636
0x18001e2b4  mov     rbx, [rbx+10h]
0x18001e2b8  test    rbx, rbx
0x18001e2bb  jnz     loc_18001E53D
0x18001e2c1  mov     rdi, rbx
0x18001e2c4  xor     esi, esi
0x18001e2c6  mov     r14d, esi
0x18001e2c9  xor     r15b, r15b
0x18001e2cc  test    rdi, rdi
0x18001e2cf  jz      loc_18001E5A5
0x18001e2d5  test    r15b, r15b
0x18001e2d8  jnz     short loc_18001E319
0x18001e2da  mov     r14, [rdi+58h]
0x18001e2de  test    r14, r14
0x18001e2e1  jz      short loc_18001E319
0x18001e2e3  lea     rcx, [r14+10h]; lpCriticalSection
0x18001e2e7  call    cs:__imp_EnterCriticalSection
0x18001e2ed  mov     ecx, [r14+3Ch]
0x18001e2f1  lea     eax, [rcx+1]
0x18001e2f4  mov     [r14+3Ch], eax
0x18001e2f8  test    ecx, ecx
0x18001e2fa  jnz     short loc_18001E316
0x18001e2fc  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e302  call    cs:__imp_TlsGetValue
0x18001e308  mov     [r14+40h], rax
0x18001e30c  call    cs:__imp_GetCurrentThreadId
0x18001e312  mov     [r14+48h], eax
0x18001e316  mov     r15b, 1
0x18001e319  mov     eax, [rdi+48h]
0x18001e31c  test    eax, eax
0x18001e31e  jnz     loc_18001E685
0x18001e324  test    rbx, rbx
0x18001e327  jz      short loc_18001E332
0x18001e329  cmp     rdi, rbx
0x18001e32c  jnz     loc_18001E66D
0x18001e332  test    r14, r14
0x18001e335  jz      short loc_18001E378
0x18001e337  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e33d  call    cs:__imp_TlsGetValue
0x18001e343  test    rax, rax
0x18001e346  jnz     loc_18001E67F
0x18001e34c  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e352  call    cs:__imp_TlsGetValue
0x18001e358  cmp     rax, rdi
0x18001e35b  jz      short loc_18001E374
0x18001e35d  mov     rdx, rdi; lpTlsValue
0x18001e360  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e366  call    cs:__imp_TlsSetValue
0x18001e36c  test    eax, eax
0x18001e36e  jz      loc_18001E715
0x18001e374  lock inc dword ptr [rdi+8]
0x18001e378  mov     r12d, esi
0x18001e37b  test    r12d, r12d
0x18001e37e  js      loc_18001E50E
0x18001e384  test    rbx, rbx
0x18001e387  jz      loc_18001E6A5
0x18001e38d  mov     [rsp+98h+var_58], rbx
0x18001e392  mov     r14, [rsp+98h+arg_28]
0x18001e39a  test    r14, r14
0x18001e39d  jz      short loc_18001E3A2
0x18001e39f  mov     [r14], esi
0x18001e3a2  mov     rax, [r13+10h]
0x18001e3a6  mov     rdi, [rax+18h]
0x18001e3aa  mov     [rsp+98h+arg_0], rdi
0x18001e3b2  test    rdi, rdi
0x18001e3b5  jz      short loc_18001E3C3
0x18001e3b7  mov     eax, [rdi+10h]
0x18001e3ba  test    eax, eax
0x18001e3bc  jle     short loc_18001E3C3
0x18001e3be  inc     eax
0x18001e3c0  mov     [rdi+10h], eax
0x18001e3c3  mov     r10, [rdi+8]
0x18001e3c7  mov     edx, esi
0x18001e3c9  movzx   r9d, word ptr [r10]
0x18001e3cd  lea     r11, ?TypeId$@IExportMessageLoopExtensions@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageLoopExtensions@CoreUI@Microsoft@@UIMessageLoopExtensions@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageLoopExtensions,IMessageLoopExtensions,0> const Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$
0x18001e3d4  cmp     edx, r9d
0x18001e3d7  jge     loc_18001E563
0x18001e3dd  movsxd  rcx, edx
0x18001e3e0  sub     rcx, r9
0x18001e3e3  add     rcx, rcx
0x18001e3e6  lea     rax, [r10+rcx*8]
0x18001e3ea  cmp     r11, [rax]
0x18001e3ed  jnz     loc_18001E52F
0x18001e3f3  mov     rcx, [rax+8]
0x18001e3f7  test    rcx, rcx
0x18001e3fa  jz      loc_18001E566
0x18001e400  mov     rax, [rcx]
0x18001e403  mov     edx, [rsp+98h+arg_20]
0x18001e40a  mov     [rsp+98h+var_70], edx
0x18001e40e  mov     edx, [rsp+98h+arg_18]
0x18001e415  mov     [rsp+98h+var_78], edx
0x18001e419  mov     r9, [rsp+98h+arg_10]
0x18001e421  mov     r8d, [rsp+98h+arg_8]
0x18001e429  mov     rdx, rdi
0x18001e42c  mov     rax, [rax+8]
0x18001e430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e435  mov     r15d, eax
0x18001e438  test    rdi, rdi
0x18001e43b  jz      short loc_18001E445
0x18001e43d  mov     rcx, rdi; this
0x18001e440  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18001e445  test    r14, r14
0x18001e448  jz      short loc_18001E457
0x18001e44a  lea     rax, [rsp+98h+var_50]
0x18001e44f  cmp     rax, r14
0x18001e452  jz      short loc_18001E457
0x18001e454  mov     [r14], r15d
0x18001e457  mov     r14d, [rbx+70h]
0x18001e45b  mov     [rbx+70h], esi
0x18001e45e  cmp     byte ptr [rbx+4Fh], 0
0x18001e462  jnz     loc_18001E50E
0x18001e468  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e46e  call    cs:__imp_TlsGetValue
0x18001e474  test    rax, rax
0x18001e477  jz      short loc_18001E48F
0x18001e479  xor     edx, edx; lpTlsValue
0x18001e47b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e481  call    cs:__imp_TlsSetValue
0x18001e487  test    eax, eax
0x18001e489  jz      loc_18001E72F
0x18001e48f  mov     rdi, [rbx+50h]
0x18001e493  mov     [rbx+50h], rsi
0x18001e497  mov     rcx, [rbx+58h]
0x18001e49b  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x18001e49f  jnz     short loc_18001E4A8
0x18001e4a1  mov     [rcx+40h], rsi
0x18001e4a5  mov     [rcx+48h], esi
0x18001e4a8  add     rcx, 10h; lpCriticalSection
0x18001e4ac  call    cs:__imp_LeaveCriticalSection
0x18001e4b2  mov     eax, 0FFFFFFFFh
0x18001e4b7  lock xadd [rbx+8], eax
0x18001e4bc  cmp     eax, 1
0x18001e4bf  jz      loc_18001E63F
0x18001e4c5  test    rdi, rdi
0x18001e4c8  jz      short loc_18001E505
0x18001e4ca  nop     word ptr [rax+rax+00h]
0x18001e4d0  mov     rbx, [rdi]
0x18001e4d3  mov     [rdi], rsi
0x18001e4d6  mov     r8, [rdi+18h]
0x18001e4da  movzx   ecx, byte ptr [rdi+8]
0x18001e4de  test    ecx, ecx
0x18001e4e0  jz      loc_18001E735
0x18001e4e6  sub     ecx, 1
0x18001e4e9  jz      loc_18001E627
0x18001e4ef  cmp     ecx, 1
0x18001e4f2  jz      short loc_18001E521
0x18001e4f4  mov     rcx, rdi; Block
0x18001e4f7  call    cs:__imp_free
0x18001e4fd  mov     rdi, rbx
0x18001e500  test    rbx, rbx
0x18001e503  jnz     short loc_18001E4D0
0x18001e505  test    r14d, r14d
0x18001e508  jnz     loc_18001E741
0x18001e50e  mov     eax, r12d
0x18001e511  add     rsp, 60h
0x18001e515  pop     r15
0x18001e517  pop     r14
0x18001e519  pop     r13
0x18001e51b  pop     r12
0x18001e51d  pop     rdi
0x18001e51e  pop     rsi
0x18001e51f  pop     rbx
0x18001e520  retn
0x18001e521  mov     rcx, [rdi+10h]
0x18001e525  mov     rax, r8
0x18001e528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e52d  jmp     short loc_18001E4F4
0x18001e52f  inc     edx
0x18001e531  jmp     loc_18001E3D4
0x18001e536  mov     eax, 87B10201h
0x18001e53b  jmp     short loc_18001E511
0x18001e53d  cmp     byte ptr [rbx+4Fh], 0
0x18001e541  jz      loc_18001E2C1
0x18001e547  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e54d  call    cs:__imp_TlsGetValue
0x18001e553  cmp     rax, rbx
0x18001e556  jnz     loc_18001E2C1
0x18001e55c  xor     esi, esi
0x18001e55e  jmp     loc_18001E378
0x18001e563  mov     rcx, rsi
0x18001e566  test    rdi, rdi
0x18001e569  jz      loc_18001E400
0x18001e56f  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x18001e576  cmp     r10, rax
0x18001e579  jnz     loc_18001E400
0x18001e57f  mov     rdx, r11; struct CFlat::ComInterfaceTypeId *
0x18001e582  mov     rcx, rdi; this
0x18001e585  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x18001e58a  mov     rcx, rax
0x18001e58d  jmp     loc_18001E400
0x18001e592  test    r15b, r15b
0x18001e595  jz      short loc_18001E5A5
0x18001e597  mov     rcx, r14; this
0x18001e59a  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18001e59f  mov     r14, rsi
0x18001e5a2  xor     r15b, r15b
0x18001e5a5  test    rbx, rbx
0x18001e5a8  jnz     loc_18001E2CC
0x18001e5ae  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e5b4  call    cs:__imp_TlsGetValue
0x18001e5ba  mov     rdi, rax
0x18001e5bd  test    rax, rax
0x18001e5c0  jnz     loc_18001E2CC
0x18001e5c6  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18001e5cb  mov     rdi, rax
0x18001e5ce  test    rax, rax
0x18001e5d1  jnz     loc_18001E2CC
0x18001e5d7  mov     eax, 87B10101h
0x18001e5dc  mov     dword ptr [rsp+98h+var_58], eax
0x18001e5e0  mov     dword ptr [rsp+98h+arg_0], eax
0x18001e5e7  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001e5ee  test    rcx, rcx
0x18001e5f1  jz      short loc_18001E61D
0x18001e5f3  mov     rax, [rcx]
0x18001e5f6  mov     r8, r12
0x18001e5f9  lea     rdx, [rsp+98h+arg_0]
0x18001e601  mov     rax, [rax+30h]
0x18001e605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e60a  mov     eax, dword ptr [rsp+98h+arg_0]
0x18001e611  mov     dword ptr [rsp+98h+var_58], eax
0x18001e615  test    eax, eax
0x18001e617  jns     loc_18001E2CC
0x18001e61d  mov     r12d, dword ptr [rsp+98h+var_58]
0x18001e622  jmp     loc_18001E37B
0x18001e627  mov     rax, [r8]
0x18001e62a  mov     rax, [rax+10h]
0x18001e62e  mov     rcx, r8; char16_t *
0x18001e631  jmp     loc_18001E528
0x18001e636  mov     rdx, r12; void *
0x18001e639  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x18001e63f  mov     dword ptr [rbx+8], 1
0x18001e646  mov     rax, [rbx]
0x18001e649  mov     rcx, rbx
0x18001e64c  mov     rax, [rax+8]
0x18001e650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e655  mov     rax, [rbx]
0x18001e658  mov     edx, 1
0x18001e65d  mov     rcx, rbx
0x18001e660  mov     rax, [rax]
0x18001e663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e668  jmp     loc_18001E4C5
0x18001e66d  mov     r8d, 87B10102h; int
0x18001e673  mov     rdx, r12; void *
0x18001e676  mov     ecx, r8d; int
0x18001e679  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18001e67f  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001e685  sub     eax, 1
0x18001e688  jz      loc_18001E592
0x18001e68e  cmp     eax, 1
0x18001e691  jnz     loc_18001E592
0x18001e697  mov     rax, [rdi+60h]
0x18001e69b  test    rax, rax
0x18001e69e  jnz     short loc_18001E6BE
0x18001e6a0  mov     r14d, esi
0x18001e6a3  jmp     short loc_18001E6C5
0x18001e6a5  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e6ab  call    cs:__imp_TlsGetValue
0x18001e6b1  mov     rbx, rax
0x18001e6b4  mov     [rsp+98h+var_58], rax
0x18001e6b9  jmp     loc_18001E392
0x18001e6be  mov     r14d, [rax+98h]
0x18001e6c5  call    cs:__imp_GetCurrentThreadId
0x18001e6cb  cmp     r14d, eax
0x18001e6ce  jz      short loc_18001E6E7
0x18001e6d0  call    cs:__imp_GetCurrentThread
0x18001e6d6  mov     rcx, rax; hHandle
0x18001e6d9  xor     r8d, r8d; bAlertable
0x18001e6dc  mov     edx, 7530h; dwMilliseconds
0x18001e6e1  call    cs:__imp_WaitForSingleObjectEx
0x18001e6e7  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001e6ee  test    rcx, rcx
0x18001e6f1  jz      short loc_18001E702
0x18001e6f3  mov     rax, [rcx]
0x18001e6f6  mov     rdx, r12
0x18001e6f9  mov     rax, [rax+38h]
0x18001e6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e702  mov     r12d, 87B10103h
0x18001e708  mov     rcx, rdi; void *
0x18001e70b  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x18001e710  jmp     loc_18001E37B
0x18001e715  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001e71b  xor     esi, esi
0x18001e71d  mov     r12d, dword ptr [rsp+98h+arg_0]
  ... truncated ...
```
