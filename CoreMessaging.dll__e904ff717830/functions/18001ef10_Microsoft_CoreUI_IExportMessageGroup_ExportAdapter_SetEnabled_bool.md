# Microsoft::CoreUI::IExportMessageGroup::ExportAdapter$::SetEnabled(bool)

- ea: `0x18001ef10`
- end: `0x18001f3aa`
- name: `?SetEnabled@ExportAdapter$@IExportMessageGroup@CoreUI@Microsoft@@UEAAJ_N@Z`
- size: `1178`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageGroup::ExportAdapter$ *__hidden this, bool)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ef10`
- `0x18001ffcc`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x18008ae1c`
- `0x1800c7f4c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f147`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f147`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f334`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f334`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f39e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f39e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f318`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001eff9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f0d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001eff9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f0d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ef95`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001efd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001efe5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f0be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f19d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f204`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f2fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ef95`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001efd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001efe5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f0be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f19d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f204`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f2fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageGroup::ExportAdapter$::SetEnabled(
        Microsoft::CoreUI::IExportMessageGroup::ExportAdapter$ *this,
        unsigned __int8 a2)
{
  __int64 v3; // rbx
  LPVOID v4; // rbx
  struct Cn::Context *Value; // rdi
  char v6; // r15
  __int64 v7; // r14
  int v8; // ecx
  int v9; // eax
  const char16_t *v10; // rcx
  const char16_t *v11; // rcx
  int v12; // r15d
  __int64 v13; // rdi
  int v14; // eax
  __int64 *v15; // r10
  int v16; // edx
  __int64 v17; // r9
  __int64 *v18; // rax
  const void *ComInterface; // rcx
  int v20; // r14d
  const char16_t *v21; // rcx
  _QWORD *v22; // rdi
  __int64 v23; // rcx
  __int64 v25; // rdx
  _QWORD *v26; // rbx
  __int64 v27; // r8
  __int64 v29; // rcx
  void (__fastcall *v30)(__int64, __int64, __int64); // rax
  __int64 v31; // rax
  int v32; // r14d
  HANDLE CurrentThread; // rax
  DWORD v34; // eax
  void *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v36; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 v37; // [rsp+78h] [rbp+10h]
  LPVOID v38; // [rsp+80h] [rbp+18h]

  v37 = a2;
  v3 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v3 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v4 = *(LPVOID *)(v3 + 16);
  if ( !v4 || !*((_BYTE *)v4 + 79) || TlsGetValue(Cn::Context::s_tlsStorage) != v4 )
  {
    Value = (struct Cn::Context *)v4;
    v6 = 0;
    while ( 1 )
    {
      if ( Value )
      {
        v7 = *((_QWORD *)Value + 11);
        if ( v7 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
          v8 = *(_DWORD *)(v7 + 60);
          *(_DWORD *)(v7 + 60) = v8 + 1;
          if ( !v8 )
          {
            *(_QWORD *)(v7 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
            *(_DWORD *)(v7 + 72) = GetCurrentThreadId();
          }
          v6 = 1;
        }
        v9 = *((_DWORD *)Value + 18);
        if ( !v9 )
        {
          if ( v4 && Value != v4 )
            CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
          if ( v7 )
          {
            if ( TlsGetValue(Cn::Context::s_tlsStorage) )
              CFlat::Abandonment::Fail(v10);
            if ( TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
              CFlat::Abandonment::Fail(v11);
            _InterlockedIncrement((volatile signed __int32 *)Value + 2);
          }
          break;
        }
        if ( v9 == 2 )
        {
          v31 = *((_QWORD *)Value + 12);
          if ( v31 )
            v32 = *(_DWORD *)(v31 + 152);
          else
            v32 = 0;
          if ( v32 != GetCurrentThreadId() )
          {
            CurrentThread = GetCurrentThread();
            WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
          }
          if ( Cn::Process::Host )
            (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
              Cn::Process::Host,
              retaddr);
          v12 = -2018443005;
          CFlat::EntryExit::OnEndCallToCFlat(Value);
          goto LABEL_19;
        }
        if ( v6 )
        {
          Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v7);
          v6 = 0;
        }
      }
      if ( !v4 )
      {
        Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
        if ( !Value )
        {
          Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
          if ( !Value )
          {
            LODWORD(v38) = -2018443007;
            LODWORD(v36) = -2018443007;
            if ( !Cn::Process::Host
              || ((*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
                    Cn::Process::Host,
                    &v36,
                    retaddr),
                  LODWORD(v38) = v36,
                  (int)v36 < 0) )
            {
              v12 = (int)v38;
              goto LABEL_19;
            }
          }
        }
      }
    }
  }
  v12 = 0;
LABEL_19:
  if ( v12 >= 0 )
  {
    if ( !v4 )
      v4 = TlsGetValue(Cn::Context::s_tlsStorage);
    v38 = v4;
    v13 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    v36 = v13;
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 16);
      if ( v14 > 0 )
        *(_DWORD *)(v13 + 16) = v14 + 1;
    }
    v15 = *(__int64 **)(v13 + 8);
    v16 = 0;
    v17 = *(unsigned __int16 *)v15;
    while ( 1 )
    {
      if ( v16 >= (int)v17 )
      {
        ComInterface = 0;
        goto LABEL_54;
      }
      v18 = &v15[2 * (v16 - v17)];
      if ( &Microsoft::CoreUI::IExportMessageGroup::TypeId$ == (__int64 *)*v18 )
        break;
      ++v16;
    }
    ComInterface = (const void *)v18[1];
    if ( ComInterface )
      goto LABEL_29;
LABEL_54:
    if ( v13 && v15 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v13,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageGroup::TypeId$);
LABEL_29:
    (*(void (__fastcall **)(const void *, __int64, _QWORD))(*(_QWORD *)ComInterface + 24LL))(ComInterface, v13, v37);
    if ( v13 )
      System::Object::Release$((System::Object *)v13);
    v20 = *((_DWORD *)v4 + 28);
    *((_DWORD *)v4 + 28) = 0;
    if ( !*((_BYTE *)v4 + 79) )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) && !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
        CFlat::Abandonment::Fail(v21);
      v22 = (_QWORD *)*((_QWORD *)v4 + 10);
      *((_QWORD *)v4 + 10) = 0;
      v23 = *((_QWORD *)v4 + 11);
      if ( (*(_DWORD *)(v23 + 60))-- == 1 )
      {
        *(_QWORD *)(v23 + 64) = 0;
        *(_DWORD *)(v23 + 72) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v23 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)v4 + 2) = 1;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 8LL))(v4);
        (**(void (__fastcall ***)(LPVOID, __int64))v4)(v4, 1);
      }
      if ( v22 )
      {
        while ( 1 )
        {
          v26 = (_QWORD *)*v22;
          *v22 = 0;
          v27 = v22[3];
          if ( !*((_BYTE *)v22 + 8) )
            break;
          if ( *((_BYTE *)v22 + 8) == 1 )
          {
            v30 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v27 + 16LL);
LABEL_66:
            v29 = v22[3];
            goto LABEL_47;
          }
          if ( *((_BYTE *)v22 + 8) == 2 )
          {
            v29 = v22[2];
            v30 = (void (__fastcall *)(__int64, __int64, __int64))v22[3];
LABEL_47:
            v30(v29, v25, v27);
          }
          free(v22);
          v22 = v26;
          if ( !v26 )
            goto LABEL_43;
        }
        v30 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v27 + 8LL);
        goto LABEL_66;
      }
LABEL_43:
      if ( v20 )
      {
        v34 = CFlat::Win32ErrorHandling::ConvertHRToWin32Error(v20);
        SetLastError(v34);
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp+arg_8], dl
0x18001ef14  push    rbx
0x18001ef15  push    rsi
0x18001ef16  push    rdi
0x18001ef17  push    r12
0x18001ef19  push    r13
0x18001ef1b  push    r14
0x18001ef1d  push    r15
0x18001ef1f  sub     rsp, 30h
0x18001ef23  mov     r13, rcx
0x18001ef26  mov     rbx, [rcx+10h]
0x18001ef2a  cmp     qword ptr [rbx+18h], 0
0x18001ef2f  jz      loc_18001F186
0x18001ef35  mov     r12, [rsp+68h]
0x18001ef3a  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18001ef41  jz      loc_18001F286
0x18001ef47  mov     rbx, [rbx+10h]
0x18001ef4b  test    rbx, rbx
0x18001ef4e  jnz     loc_18001F18D
0x18001ef54  mov     rdi, rbx
0x18001ef57  xor     esi, esi
0x18001ef59  mov     r14d, esi
0x18001ef5c  xor     r15b, r15b
0x18001ef5f  test    rdi, rdi
0x18001ef62  jz      loc_18001F1F5
0x18001ef68  test    r15b, r15b
0x18001ef6b  jnz     short loc_18001EFAC
0x18001ef6d  mov     r14, [rdi+58h]
0x18001ef71  test    r14, r14
0x18001ef74  jz      short loc_18001EFAC
0x18001ef76  lea     rcx, [r14+10h]; lpCriticalSection
0x18001ef7a  call    cs:__imp_EnterCriticalSection
0x18001ef80  mov     ecx, [r14+3Ch]
0x18001ef84  lea     eax, [rcx+1]
0x18001ef87  mov     [r14+3Ch], eax
0x18001ef8b  test    ecx, ecx
0x18001ef8d  jnz     short loc_18001EFA9
0x18001ef8f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001ef95  call    cs:__imp_TlsGetValue
0x18001ef9b  mov     [r14+40h], rax
0x18001ef9f  call    cs:__imp_GetCurrentThreadId
0x18001efa5  mov     [r14+48h], eax
0x18001efa9  mov     r15b, 1
0x18001efac  mov     eax, [rdi+48h]
0x18001efaf  test    eax, eax
0x18001efb1  jnz     loc_18001F2D5
0x18001efb7  test    rbx, rbx
0x18001efba  jz      short loc_18001EFC5
0x18001efbc  cmp     rdi, rbx
0x18001efbf  jnz     loc_18001F2BD
0x18001efc5  test    r14, r14
0x18001efc8  jz      short loc_18001F00B
0x18001efca  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001efd0  call    cs:__imp_TlsGetValue
0x18001efd6  test    rax, rax
0x18001efd9  jnz     loc_18001F2CF
0x18001efdf  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001efe5  call    cs:__imp_TlsGetValue
0x18001efeb  cmp     rax, rdi
0x18001efee  jz      short loc_18001F007
0x18001eff0  mov     rdx, rdi; lpTlsValue
0x18001eff3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001eff9  call    cs:__imp_TlsSetValue
0x18001efff  test    eax, eax
0x18001f001  jz      loc_18001F368
0x18001f007  lock inc dword ptr [rdi+8]
0x18001f00b  mov     r15d, esi
0x18001f00e  test    r15d, r15d
0x18001f011  js      loc_18001F15E
0x18001f017  test    rbx, rbx
0x18001f01a  jz      loc_18001F2F5
0x18001f020  mov     [rsp+68h+arg_10], rbx
0x18001f028  mov     rax, [r13+10h]
0x18001f02c  mov     rdi, [rax+18h]
0x18001f030  mov     [rsp+68h+arg_0], rdi
0x18001f035  test    rdi, rdi
0x18001f038  jz      short loc_18001F046
0x18001f03a  mov     eax, [rdi+10h]
0x18001f03d  test    eax, eax
0x18001f03f  jle     short loc_18001F046
0x18001f041  inc     eax
0x18001f043  mov     [rdi+10h], eax
0x18001f046  mov     r10, [rdi+8]
0x18001f04a  mov     edx, esi
0x18001f04c  movzx   r9d, word ptr [r10]
0x18001f050  lea     r11, ?TypeId$@IExportMessageGroup@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageGroup@CoreUI@Microsoft@@UIMessageGroup@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageGroup,IMessageGroup,0> const Microsoft::CoreUI::IExportMessageGroup::TypeId$
0x18001f057  cmp     edx, r9d
0x18001f05a  jge     loc_18001F1B3
0x18001f060  movsxd  rcx, edx
0x18001f063  sub     rcx, r9
0x18001f066  add     rcx, rcx
0x18001f069  lea     rax, [r10+rcx*8]
0x18001f06d  cmp     r11, [rax]
0x18001f070  jnz     loc_18001F17F
0x18001f076  mov     rcx, [rax+8]
0x18001f07a  test    rcx, rcx
0x18001f07d  jz      loc_18001F1B6
0x18001f083  mov     rax, [rcx]
0x18001f086  movzx   r8d, [rsp+68h+arg_8]
0x18001f08c  mov     rdx, rdi
0x18001f08f  mov     rax, [rax+18h]
0x18001f093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f098  nop
0x18001f099  test    rdi, rdi
0x18001f09c  jz      short loc_18001F0A7
0x18001f09e  mov     rcx, rdi; this
0x18001f0a1  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18001f0a6  nop
0x18001f0a7  mov     r14d, [rbx+70h]
0x18001f0ab  mov     [rbx+70h], esi
0x18001f0ae  cmp     byte ptr [rbx+4Fh], 0
0x18001f0b2  jnz     loc_18001F15E
0x18001f0b8  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f0be  call    cs:__imp_TlsGetValue
0x18001f0c4  test    rax, rax
0x18001f0c7  jz      short loc_18001F0DF
0x18001f0c9  xor     edx, edx; lpTlsValue
0x18001f0cb  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f0d1  call    cs:__imp_TlsSetValue
0x18001f0d7  test    eax, eax
0x18001f0d9  jz      loc_18001F382
0x18001f0df  mov     rdi, [rbx+50h]
0x18001f0e3  mov     [rbx+50h], rsi
0x18001f0e7  mov     rcx, [rbx+58h]
0x18001f0eb  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x18001f0ef  jnz     short loc_18001F0F8
0x18001f0f1  mov     [rcx+40h], rsi
0x18001f0f5  mov     [rcx+48h], esi
0x18001f0f8  add     rcx, 10h; lpCriticalSection
0x18001f0fc  call    cs:__imp_LeaveCriticalSection
0x18001f102  mov     eax, 0FFFFFFFFh
0x18001f107  lock xadd [rbx+8], eax
0x18001f10c  cmp     eax, 1
0x18001f10f  jz      loc_18001F28F
0x18001f115  test    rdi, rdi
0x18001f118  jz      short loc_18001F155
0x18001f11a  nop     word ptr [rax+rax+00h]
0x18001f120  mov     rbx, [rdi]
0x18001f123  mov     [rdi], rsi
0x18001f126  mov     r8, [rdi+18h]
0x18001f12a  movzx   ecx, byte ptr [rdi+8]
0x18001f12e  test    ecx, ecx
0x18001f130  jz      loc_18001F388
0x18001f136  sub     ecx, 1
0x18001f139  jz      loc_18001F277
0x18001f13f  cmp     ecx, 1
0x18001f142  jz      short loc_18001F171
0x18001f144  mov     rcx, rdi; Block
0x18001f147  call    cs:__imp_free
0x18001f14d  mov     rdi, rbx
0x18001f150  test    rbx, rbx
0x18001f153  jnz     short loc_18001F120
0x18001f155  test    r14d, r14d
0x18001f158  jnz     loc_18001F394
0x18001f15e  mov     eax, r15d
0x18001f161  add     rsp, 30h
0x18001f165  pop     r15
0x18001f167  pop     r14
0x18001f169  pop     r13
0x18001f16b  pop     r12
0x18001f16d  pop     rdi
0x18001f16e  pop     rsi
0x18001f16f  pop     rbx
0x18001f170  retn
0x18001f171  mov     rcx, [rdi+10h]
0x18001f175  mov     rax, r8
0x18001f178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f17d  jmp     short loc_18001F144
0x18001f17f  inc     edx
0x18001f181  jmp     loc_18001F057
0x18001f186  mov     eax, 87B10201h
0x18001f18b  jmp     short loc_18001F161
0x18001f18d  cmp     byte ptr [rbx+4Fh], 0
0x18001f191  jz      loc_18001EF54
0x18001f197  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f19d  call    cs:__imp_TlsGetValue
0x18001f1a3  cmp     rax, rbx
0x18001f1a6  jnz     loc_18001EF54
0x18001f1ac  xor     esi, esi
0x18001f1ae  jmp     loc_18001F00B
0x18001f1b3  mov     rcx, rsi
0x18001f1b6  test    rdi, rdi
0x18001f1b9  jz      loc_18001F083
0x18001f1bf  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x18001f1c6  cmp     r10, rax
0x18001f1c9  jnz     loc_18001F083
0x18001f1cf  mov     rdx, r11; struct CFlat::ComInterfaceTypeId *
0x18001f1d2  mov     rcx, rdi; this
0x18001f1d5  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x18001f1da  mov     rcx, rax
0x18001f1dd  jmp     loc_18001F083
0x18001f1e2  test    r15b, r15b
0x18001f1e5  jz      short loc_18001F1F5
0x18001f1e7  mov     rcx, r14; this
0x18001f1ea  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18001f1ef  mov     r14, rsi
0x18001f1f2  xor     r15b, r15b
0x18001f1f5  test    rbx, rbx
0x18001f1f8  jnz     loc_18001EF5F
0x18001f1fe  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f204  call    cs:__imp_TlsGetValue
0x18001f20a  mov     rdi, rax
0x18001f20d  test    rax, rax
0x18001f210  jnz     loc_18001EF5F
0x18001f216  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18001f21b  mov     rdi, rax
0x18001f21e  test    rax, rax
0x18001f221  jnz     loc_18001EF5F
0x18001f227  mov     eax, 87B10101h
0x18001f22c  mov     dword ptr [rsp+68h+arg_10], eax
0x18001f233  mov     dword ptr [rsp+68h+arg_0], eax
0x18001f237  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001f23e  test    rcx, rcx
0x18001f241  jz      short loc_18001F26A
0x18001f243  mov     rax, [rcx]
0x18001f246  mov     r8, r12
0x18001f249  lea     rdx, [rsp+68h+arg_0]
0x18001f24e  mov     rax, [rax+30h]
0x18001f252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f257  mov     eax, dword ptr [rsp+68h+arg_0]
0x18001f25b  mov     dword ptr [rsp+68h+arg_10], eax
0x18001f262  test    eax, eax
0x18001f264  jns     loc_18001EF5F
0x18001f26a  mov     r15d, dword ptr [rsp+68h+arg_10]
0x18001f272  jmp     loc_18001F00E
0x18001f277  mov     rax, [r8]
0x18001f27a  mov     rax, [rax+10h]
0x18001f27e  mov     rcx, r8; char16_t *
0x18001f281  jmp     loc_18001F178
0x18001f286  mov     rdx, r12; void *
0x18001f289  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x18001f28f  mov     dword ptr [rbx+8], 1
0x18001f296  mov     rax, [rbx]
0x18001f299  mov     rcx, rbx
0x18001f29c  mov     rax, [rax+8]
0x18001f2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a5  mov     rax, [rbx]
0x18001f2a8  mov     edx, 1
0x18001f2ad  mov     rcx, rbx
0x18001f2b0  mov     rax, [rax]
0x18001f2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b8  jmp     loc_18001F115
0x18001f2bd  mov     r8d, 87B10102h; int
0x18001f2c3  mov     rdx, r12; void *
0x18001f2c6  mov     ecx, r8d; int
0x18001f2c9  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18001f2cf  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001f2d5  sub     eax, 1
0x18001f2d8  jz      loc_18001F1E2
0x18001f2de  cmp     eax, 1
0x18001f2e1  jnz     loc_18001F1E2
0x18001f2e7  mov     rax, [rdi+60h]
0x18001f2eb  test    rax, rax
0x18001f2ee  jnz     short loc_18001F311
0x18001f2f0  mov     r14d, esi
0x18001f2f3  jmp     short loc_18001F318
0x18001f2f5  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f2fb  call    cs:__imp_TlsGetValue
0x18001f301  mov     rbx, rax
0x18001f304  mov     [rsp+68h+arg_10], rax
0x18001f30c  jmp     loc_18001F028
0x18001f311  mov     r14d, [rax+98h]
0x18001f318  call    cs:__imp_GetCurrentThreadId
0x18001f31e  cmp     r14d, eax
0x18001f321  jz      short loc_18001F33A
0x18001f323  call    cs:__imp_GetCurrentThread
0x18001f329  mov     rcx, rax; hHandle
0x18001f32c  xor     r8d, r8d; bAlertable
0x18001f32f  mov     edx, 7530h; dwMilliseconds
0x18001f334  call    cs:__imp_WaitForSingleObjectEx
0x18001f33a  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001f341  test    rcx, rcx
0x18001f344  jz      short loc_18001F355
0x18001f346  mov     rax, [rcx]
0x18001f349  mov     rdx, r12
0x18001f34c  mov     rax, [rax+38h]
0x18001f350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f355  mov     r15d, 87B10103h
0x18001f35b  mov     rcx, rdi; void *
0x18001f35e  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x18001f363  jmp     loc_18001F00E
0x18001f368  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001f36e  xor     esi, esi
0x18001f370  mov     r15d, dword ptr [rsp+68h+arg_0]
0x18001f375  mov     rbx, [rsp+68h+arg_10]
0x18001f37d  jmp     loc_18001F0A7
0x18001f382  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001f388  mov     rax, [r8]
0x18001f38b  mov     rax, [rax+8]
0x18001f38f  jmp     loc_18001F27E
0x18001f394  mov     ecx, r14d; int
0x18001f397  call    ?ConvertHRToWin32Error@Win32ErrorHandling@CFlat@@SAIH@Z; CFlat::Win32ErrorHandling::ConvertHRToWin32Error(int)
0x18001f39c  mov     ecx, eax; dwErrCode
0x18001f39e  call    cs:__imp_SetLastError
0x18001f3a4  jmp     loc_18001F15E
```
