# Microsoft::CoreUI::IExportMessageLoopExtensions::ExportAdapter$::Run(MsgRunMode)

- ea: `0x1800200b0`
- end: `0x18002054a`
- name: `?Run@ExportAdapter$@IExportMessageLoopExtensions@CoreUI@Microsoft@@UEAAJW4MsgRunMode@@@Z`
- size: `1178`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ffcc`
- `0x1800200b0`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x18008ae1c`
- `0x1800c7f4c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002011a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002011a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800204d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800204d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002029a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002029a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002053e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002053e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800204c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800204c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002013f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002013f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020199`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002026f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020199`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002026f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020135`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020170`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020185`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002025c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002033d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800203a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002049b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020135`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020170`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020185`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002025c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002033d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800203a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002049b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageLoopExtensions::ExportAdapter$::Run(__int64 a1, unsigned int a2)
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
  void (__fastcall ***ComInterface)(const void *, __int64, _QWORD); // rcx
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
  unsigned int v37; // [rsp+78h] [rbp+10h]
  LPVOID v38; // [rsp+80h] [rbp+18h]

  v37 = a2;
  v3 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v3 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)a1, retaddr);
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
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
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
      if ( &Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$ == (__int64 *)*v18 )
        break;
      ++v16;
    }
    ComInterface = (void (__fastcall ***)(const void *, __int64, _QWORD))v18[1];
    if ( ComInterface )
      goto LABEL_29;
LABEL_54:
    if ( v13 && v15 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = (void (__fastcall ***)(const void *, __int64, _QWORD))CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                                                                             (CFlat::ComImportAdapter *)v13,
                                                                             (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$);
LABEL_29:
    (**ComInterface)(ComInterface, v13, v37);
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
0x1800200b0  mov     [rsp+arg_8], edx
0x1800200b4  push    rbx
0x1800200b5  push    rsi
0x1800200b6  push    rdi
0x1800200b7  push    r12
0x1800200b9  push    r13
0x1800200bb  push    r14
0x1800200bd  push    r15
0x1800200bf  sub     rsp, 30h
0x1800200c3  mov     r13, rcx
0x1800200c6  mov     rbx, [rcx+10h]
0x1800200ca  cmp     qword ptr [rbx+18h], 0
0x1800200cf  jz      loc_180020326
0x1800200d5  mov     r12, [rsp+68h]
0x1800200da  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x1800200e1  jz      loc_180020426
0x1800200e7  mov     rbx, [rbx+10h]
0x1800200eb  test    rbx, rbx
0x1800200ee  jnz     loc_18002032D
0x1800200f4  mov     rdi, rbx
0x1800200f7  xor     esi, esi
0x1800200f9  mov     r14d, esi
0x1800200fc  xor     r15b, r15b
0x1800200ff  test    rdi, rdi
0x180020102  jz      loc_180020395
0x180020108  test    r15b, r15b
0x18002010b  jnz     short loc_18002014C
0x18002010d  mov     r14, [rdi+58h]
0x180020111  test    r14, r14
0x180020114  jz      short loc_18002014C
0x180020116  lea     rcx, [r14+10h]; lpCriticalSection
0x18002011a  call    cs:__imp_EnterCriticalSection
0x180020120  mov     ecx, [r14+3Ch]
0x180020124  lea     eax, [rcx+1]
0x180020127  mov     [r14+3Ch], eax
0x18002012b  test    ecx, ecx
0x18002012d  jnz     short loc_180020149
0x18002012f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020135  call    cs:__imp_TlsGetValue
0x18002013b  mov     [r14+40h], rax
0x18002013f  call    cs:__imp_GetCurrentThreadId
0x180020145  mov     [r14+48h], eax
0x180020149  mov     r15b, 1
0x18002014c  mov     eax, [rdi+48h]
0x18002014f  test    eax, eax
0x180020151  jnz     loc_180020475
0x180020157  test    rbx, rbx
0x18002015a  jz      short loc_180020165
0x18002015c  cmp     rdi, rbx
0x18002015f  jnz     loc_18002045D
0x180020165  test    r14, r14
0x180020168  jz      short loc_1800201AB
0x18002016a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020170  call    cs:__imp_TlsGetValue
0x180020176  test    rax, rax
0x180020179  jnz     loc_18002046F
0x18002017f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020185  call    cs:__imp_TlsGetValue
0x18002018b  cmp     rax, rdi
0x18002018e  jz      short loc_1800201A7
0x180020190  mov     rdx, rdi; lpTlsValue
0x180020193  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020199  call    cs:__imp_TlsSetValue
0x18002019f  test    eax, eax
0x1800201a1  jz      loc_180020508
0x1800201a7  lock inc dword ptr [rdi+8]
0x1800201ab  mov     r15d, esi
0x1800201ae  test    r15d, r15d
0x1800201b1  js      loc_1800202FE
0x1800201b7  test    rbx, rbx
0x1800201ba  jz      loc_180020495
0x1800201c0  mov     [rsp+68h+arg_10], rbx
0x1800201c8  mov     rax, [r13+10h]
0x1800201cc  mov     rdi, [rax+18h]
0x1800201d0  mov     [rsp+68h+arg_0], rdi
0x1800201d5  test    rdi, rdi
0x1800201d8  jz      short loc_1800201E6
0x1800201da  mov     eax, [rdi+10h]
0x1800201dd  test    eax, eax
0x1800201df  jle     short loc_1800201E6
0x1800201e1  inc     eax
0x1800201e3  mov     [rdi+10h], eax
0x1800201e6  mov     r10, [rdi+8]
0x1800201ea  mov     edx, esi
0x1800201ec  movzx   r9d, word ptr [r10]
0x1800201f0  lea     r11, ?TypeId$@IExportMessageLoopExtensions@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageLoopExtensions@CoreUI@Microsoft@@UIMessageLoopExtensions@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageLoopExtensions,IMessageLoopExtensions,0> const Microsoft::CoreUI::IExportMessageLoopExtensions::TypeId$
0x1800201f7  cmp     edx, r9d
0x1800201fa  jge     loc_180020353
0x180020200  movsxd  rcx, edx
0x180020203  sub     rcx, r9
0x180020206  add     rcx, rcx
0x180020209  lea     rax, [r10+rcx*8]
0x18002020d  cmp     r11, [rax]
0x180020210  jnz     loc_18002031F
0x180020216  mov     rcx, [rax+8]
0x18002021a  test    rcx, rcx
0x18002021d  jz      loc_180020356
0x180020223  mov     rax, [rcx]
0x180020226  mov     r8d, [rsp+68h+arg_8]
0x18002022b  mov     rdx, rdi
0x18002022e  mov     rax, [rax]
0x180020231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020236  nop
0x180020237  test    rdi, rdi
0x18002023a  jz      short loc_180020245
0x18002023c  mov     rcx, rdi; this
0x18002023f  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180020244  nop
0x180020245  mov     r14d, [rbx+70h]
0x180020249  mov     [rbx+70h], esi
0x18002024c  cmp     byte ptr [rbx+4Fh], 0
0x180020250  jnz     loc_1800202FE
0x180020256  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002025c  call    cs:__imp_TlsGetValue
0x180020262  test    rax, rax
0x180020265  jz      short loc_18002027D
0x180020267  xor     edx, edx; lpTlsValue
0x180020269  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002026f  call    cs:__imp_TlsSetValue
0x180020275  test    eax, eax
0x180020277  jz      loc_180020522
0x18002027d  mov     rdi, [rbx+50h]
0x180020281  mov     [rbx+50h], rsi
0x180020285  mov     rcx, [rbx+58h]
0x180020289  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x18002028d  jnz     short loc_180020296
0x18002028f  mov     [rcx+40h], rsi
0x180020293  mov     [rcx+48h], esi
0x180020296  add     rcx, 10h; lpCriticalSection
0x18002029a  call    cs:__imp_LeaveCriticalSection
0x1800202a0  mov     eax, 0FFFFFFFFh
0x1800202a5  lock xadd [rbx+8], eax
0x1800202aa  cmp     eax, 1
0x1800202ad  jz      loc_18002042F
0x1800202b3  test    rdi, rdi
0x1800202b6  jz      short loc_1800202F5
0x1800202b8  nop     dword ptr [rax+rax+00000000h]
0x1800202c0  mov     rbx, [rdi]
0x1800202c3  mov     [rdi], rsi
0x1800202c6  mov     r8, [rdi+18h]
0x1800202ca  movzx   ecx, byte ptr [rdi+8]
0x1800202ce  test    ecx, ecx
0x1800202d0  jz      loc_180020528
0x1800202d6  sub     ecx, 1
0x1800202d9  jz      loc_180020417
0x1800202df  cmp     ecx, 1
0x1800202e2  jz      short loc_180020311
0x1800202e4  mov     rcx, rdi; Block
0x1800202e7  call    cs:__imp_free
0x1800202ed  mov     rdi, rbx
0x1800202f0  test    rbx, rbx
0x1800202f3  jnz     short loc_1800202C0
0x1800202f5  test    r14d, r14d
0x1800202f8  jnz     loc_180020534
0x1800202fe  mov     eax, r15d
0x180020301  add     rsp, 30h
0x180020305  pop     r15
0x180020307  pop     r14
0x180020309  pop     r13
0x18002030b  pop     r12
0x18002030d  pop     rdi
0x18002030e  pop     rsi
0x18002030f  pop     rbx
0x180020310  retn
0x180020311  mov     rcx, [rdi+10h]
0x180020315  mov     rax, r8
0x180020318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002031d  jmp     short loc_1800202E4
0x18002031f  inc     edx
0x180020321  jmp     loc_1800201F7
0x180020326  mov     eax, 87B10201h
0x18002032b  jmp     short loc_180020301
0x18002032d  cmp     byte ptr [rbx+4Fh], 0
0x180020331  jz      loc_1800200F4
0x180020337  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002033d  call    cs:__imp_TlsGetValue
0x180020343  cmp     rax, rbx
0x180020346  jnz     loc_1800200F4
0x18002034c  xor     esi, esi
0x18002034e  jmp     loc_1800201AB
0x180020353  mov     rcx, rsi
0x180020356  test    rdi, rdi
0x180020359  jz      loc_180020223
0x18002035f  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x180020366  cmp     r10, rax
0x180020369  jnz     loc_180020223
0x18002036f  mov     rdx, r11; struct CFlat::ComInterfaceTypeId *
0x180020372  mov     rcx, rdi; this
0x180020375  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x18002037a  mov     rcx, rax
0x18002037d  jmp     loc_180020223
0x180020382  test    r15b, r15b
0x180020385  jz      short loc_180020395
0x180020387  mov     rcx, r14; this
0x18002038a  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18002038f  mov     r14, rsi
0x180020392  xor     r15b, r15b
0x180020395  test    rbx, rbx
0x180020398  jnz     loc_1800200FF
0x18002039e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800203a4  call    cs:__imp_TlsGetValue
0x1800203aa  mov     rdi, rax
0x1800203ad  test    rax, rax
0x1800203b0  jnz     loc_1800200FF
0x1800203b6  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x1800203bb  mov     rdi, rax
0x1800203be  test    rax, rax
0x1800203c1  jnz     loc_1800200FF
0x1800203c7  mov     eax, 87B10101h
0x1800203cc  mov     dword ptr [rsp+68h+arg_10], eax
0x1800203d3  mov     dword ptr [rsp+68h+arg_0], eax
0x1800203d7  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x1800203de  test    rcx, rcx
0x1800203e1  jz      short loc_18002040A
0x1800203e3  mov     rax, [rcx]
0x1800203e6  mov     r8, r12
0x1800203e9  lea     rdx, [rsp+68h+arg_0]
0x1800203ee  mov     rax, [rax+30h]
0x1800203f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203f7  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800203fb  mov     dword ptr [rsp+68h+arg_10], eax
0x180020402  test    eax, eax
0x180020404  jns     loc_1800200FF
0x18002040a  mov     r15d, dword ptr [rsp+68h+arg_10]
0x180020412  jmp     loc_1800201AE
0x180020417  mov     rax, [r8]
0x18002041a  mov     rax, [rax+10h]
0x18002041e  mov     rcx, r8; char16_t *
0x180020421  jmp     loc_180020318
0x180020426  mov     rdx, r12; void *
0x180020429  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x18002042f  mov     dword ptr [rbx+8], 1
0x180020436  mov     rax, [rbx]
0x180020439  mov     rcx, rbx
0x18002043c  mov     rax, [rax+8]
0x180020440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020445  mov     rax, [rbx]
0x180020448  mov     edx, 1
0x18002044d  mov     rcx, rbx
0x180020450  mov     rax, [rax]
0x180020453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020458  jmp     loc_1800202B3
0x18002045d  mov     r8d, 87B10102h; int
0x180020463  mov     rdx, r12; void *
0x180020466  mov     ecx, r8d; int
0x180020469  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18002046f  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180020475  sub     eax, 1
0x180020478  jz      loc_180020382
0x18002047e  cmp     eax, 1
0x180020481  jnz     loc_180020382
0x180020487  mov     rax, [rdi+60h]
0x18002048b  test    rax, rax
0x18002048e  jnz     short loc_1800204B1
0x180020490  mov     r14d, esi
0x180020493  jmp     short loc_1800204B8
0x180020495  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002049b  call    cs:__imp_TlsGetValue
0x1800204a1  mov     rbx, rax
0x1800204a4  mov     [rsp+68h+arg_10], rax
0x1800204ac  jmp     loc_1800201C8
0x1800204b1  mov     r14d, [rax+98h]
0x1800204b8  call    cs:__imp_GetCurrentThreadId
0x1800204be  cmp     r14d, eax
0x1800204c1  jz      short loc_1800204DA
0x1800204c3  call    cs:__imp_GetCurrentThread
0x1800204c9  mov     rcx, rax; hHandle
0x1800204cc  xor     r8d, r8d; bAlertable
0x1800204cf  mov     edx, 7530h; dwMilliseconds
0x1800204d4  call    cs:__imp_WaitForSingleObjectEx
0x1800204da  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x1800204e1  test    rcx, rcx
0x1800204e4  jz      short loc_1800204F5
0x1800204e6  mov     rax, [rcx]
0x1800204e9  mov     rdx, r12
0x1800204ec  mov     rax, [rax+38h]
0x1800204f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204f5  mov     r15d, 87B10103h
0x1800204fb  mov     rcx, rdi; void *
0x1800204fe  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180020503  jmp     loc_1800201AE
0x180020508  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002050e  xor     esi, esi
0x180020510  mov     r15d, dword ptr [rsp+68h+arg_0]
0x180020515  mov     rbx, [rsp+68h+arg_10]
0x18002051d  jmp     loc_180020245
0x180020522  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180020528  mov     rax, [r8]
0x18002052b  mov     rax, [rax+8]
0x18002052f  jmp     loc_18002041E
0x180020534  mov     ecx, r14d; int
0x180020537  call    ?ConvertHRToWin32Error@Win32ErrorHandling@CFlat@@SAIH@Z; CFlat::Win32ErrorHandling::ConvertHRToWin32Error(int)
0x18002053c  mov     ecx, eax; dwErrCode
0x18002053e  call    cs:__imp_SetLastError
0x180020544  jmp     loc_1800202FE
```
