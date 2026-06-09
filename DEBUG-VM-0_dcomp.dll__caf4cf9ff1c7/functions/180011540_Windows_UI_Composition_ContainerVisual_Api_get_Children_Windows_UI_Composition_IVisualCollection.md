# Windows::UI::Composition::ContainerVisual::Api::get_Children(Windows::UI::Composition::IVisualCollection * *)

- ea: `0x180011540`
- end: `0x180011b25`
- name: `?get_Children@Api@ContainerVisual@Composition@UI@Windows@@UEAAJPEAPEAUIVisualCollection@345@@Z`
- size: `1509`
- prototype: `__int64 __fastcall(Windows::UI::Composition::ContainerVisual::Api *__hidden this, struct Windows::UI::Composition::IVisualCollection **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011020`
- `0x180011070`
- `0x18001109c`
- `0x180011540`
- `0x180012da0`
- `0x180012ee8`
- `0x180013528`
- `0x18001358c`
- `0x180014e14`
- `0x180036f90`
- `0x18003ced8`
- `0x1800e77ac`
- `0x1800f6f34`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800118e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800118e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011577`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011577`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800115c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800115c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116d8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011724`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001173d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011724`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001173d`

## string_xrefs

- `0x180011716`: `The given object has already been closed / disposed and may no longer be used.`
- `0x18001172f`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180011a20`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ContainerVisual::Api::get_Children(
        Windows::UI::Composition::ContainerVisual::Api *this,
        struct Windows::UI::Composition::IVisualCollection **a2)
{
  volatile signed __int32 *v2; // r14
  __int64 v4; // rbx
  int v5; // ecx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  _DWORD *v8; // rax
  _DWORD *v9; // rsi
  struct Microsoft::WRL::Details::ModuleBase *v10; // rcx
  volatile signed __int32 *v11; // rcx
  __int64 v12; // r14
  int v13; // edi
  Microsoft::WRL2::ContextSession *v14; // rcx
  _QWORD *v15; // r8
  int v16; // edx
  int v17; // ecx
  void **v18; // rcx
  char *v19; // rsi
  char *v20; // rdi
  char *j; // rbx
  unsigned __int64 v22; // rdx
  char *i; // rbx
  unsigned __int64 v25; // rdx
  char *v26; // rcx
  unsigned int v27; // r15d
  struct Windows::UI::Composition::IVisualCollection *v28; // rax
  int v29; // edx
  int v30; // ecx
  void **v31; // rcx
  char *v32; // rsi
  char *v33; // rdi
  char *v34; // rbx
  char *v35; // rbx
  char v36; // cl
  int v37; // eax
  __int64 v38; // rdx
  char v39; // al
  int v40; // eax
  _BYTE *v41; // rcx
  int v42; // [rsp+20h] [rbp-40h]
  __int128 v43; // [rsp+30h] [rbp-30h] BYREF
  __int64 v44; // [rsp+40h] [rbp-20h]
  __int128 v45; // [rsp+48h] [rbp-18h] BYREF
  __int64 v46; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v2 = (volatile signed __int32 *)((char *)this - 336);
  *a2 = 0;
  v4 = *((_QWORD *)this - 39);
  if ( *(_DWORD *)(v4 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
  v5 = *(_DWORD *)(v4 + 64);
  if ( v5 != *(_DWORD *)(v4 + 72) + *(_DWORD *)(v4 + 68) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v4 + 64) = v5 + 1;
  if ( (v2[12] & 2) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 0, 0xB0u);
    if ( !v7 )
    {
      v27 = -2147024882;
      DoStackCaptureDirect(-2147024882, 0x5Bu);
      goto LABEL_45;
    }
    v8 = memset_0(v7, 0, 0xB0u);
    v9 = v8;
    if ( v8 )
    {
      v10 = Microsoft::WRL::Details::ModuleBase::module_;
      v8[4] = 1;
      *((_QWORD *)v8 + 1) = 0;
      if ( v10 )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
      Windows::UI::Composition::CompositionObject::Api::Api((Windows::UI::Composition::CompositionObject::Api *)(v9 + 14));
      Windows::UI::Composition::CompositionObject::Partner::Partner((Windows::UI::Composition::CompositionObject::Partner *)(v9 + 28));
      *((_QWORD *)v9 + 16) = &CSparseStorage::s_defaultEmptyAllocatedStorage;
      *(_QWORD *)v9 = &Windows::UI::Composition::VisualCollection::`vftable';
      Windows::UI::Composition::VisualCollection::Api::Api((Windows::UI::Composition::VisualCollection::Api *)(v9 + 36));
      *((_QWORD *)v9 + 21) = 0;
    }
    else
    {
      v9 = 0;
    }
    *((_QWORD *)v9 + 1) = &Windows::UI::Composition::VisualCollection::s_InterfaceType;
    if ( *((volatile signed __int32 **)v9 + 21) != v2 )
    {
      if ( _InterlockedIncrement(v2 + 4) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 80LL))(v2);
      v11 = (volatile signed __int32 *)*((_QWORD *)v9 + 21);
      *((_QWORD *)v9 + 21) = v2;
      if ( v11 && _InterlockedExchangeAdd(v11 + 4, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v11 + 64LL))(v11, 1);
    }
    v12 = *((_QWORD *)v2 + 3);
    *((_QWORD *)v9 + 3) = v12;
    if ( (_DWORD *)v12 != v9 )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)(v12 + 16)) == 1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 80LL))(v12);
      v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 24) + 56LL) + 40LL);
      if ( v13 == GetCurrentThreadId() )
      {
        v14 = 0;
LABEL_20:
        v15 = *(_QWORD **)(v12 + 40);
        if ( *v15 != v12 + 32 )
          __fastfail(3u);
        *((_QWORD *)v9 + 4) = v12 + 32;
        *((_QWORD *)v9 + 5) = v15;
        *v15 = v9 + 8;
        *(_QWORD *)(v12 + 40) = v9 + 8;
        if ( v14 )
          Microsoft::WRL2::ContextSession::EndApiEntry(v14);
        goto LABEL_60;
      }
      Microsoft::WRL2::ContextSession::BeginApiEntry(*(Microsoft::WRL2::ContextSession **)(v12 + 24));
      v14 = *(Microsoft::WRL2::ContextSession **)(v12 + 24);
      if ( (*(_BYTE *)(v12 + 48) & 2) != 0 )
        goto LABEL_20;
      Microsoft::WRL2::ContextSession::EndApiEntry(v14);
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
    }
LABEL_60:
    v36 = *((_BYTE *)v9 + 49);
    *((_BYTE *)v9 + 48) = 31;
    *((_BYTE *)v9 + 49) ^= (*(_BYTE *)(v12 + 49) ^ v36) & 1;
    v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, _DWORD *))(**(_QWORD **)(*(_QWORD *)(v12 + 408) + 32LL)
                                                                        + 24LL))(
            *(_QWORD *)(*(_QWORD *)(v12 + 408) + 32LL),
            *(unsigned int *)(*(_QWORD *)(v12 + 408) + 64LL),
            v9,
            v9 + 34);
    v27 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
        (const char *)(unsigned int)v37,
        v42);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
      DoStackCaptureDirect(v27, 0x5Bu);
    }
    else
    {
      v39 = *(_BYTE *)(v12 + 436);
      if ( (v39 & 1) == 0 )
      {
        *(_BYTE *)(v12 + 436) = v39 | 1;
        if ( !*(_DWORD *)(v12 + 432) )
        {
          LOBYTE(v38) = 1;
          v40 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v12 + 416) + 48LL))(
                  *(_QWORD *)(v12 + 416),
                  v38);
          if ( v40 < 0 )
            Microsoft::WRL2::FailFast::ForHR(v40, retaddr);
        }
      }
      v9[35] |= 1u;
      if ( !v9 || v9 == (_DWORD *)-144LL )
        v28 = 0;
      else
        v28 = (struct Windows::UI::Composition::IVisualCollection *)(v9 + 38);
      *a2 = v28;
      v27 = 0;
    }
LABEL_45:
    v29 = *(_DWORD *)(v4 + 72);
    v30 = v29 + *(_DWORD *)(v4 + 68);
    if ( --*(_DWORD *)(v4 + 64) == v30 )
    {
      v46 = 0;
      v45 = 0;
      if ( v29 || (v31 = (void **)(v4 + 120), &v45 == (__int128 *)(v4 + 120)) )
      {
        v33 = (char *)*((_QWORD *)&v45 + 1);
        v32 = (char *)v45;
      }
      else
      {
        v32 = (char *)*v31;
        *v31 = 0;
        v33 = *(char **)(v4 + 128);
        *(_QWORD *)(v4 + 128) = 0;
        v46 = *(_QWORD *)(v4 + 136);
        *(_QWORD *)&v45 = v32;
        *((_QWORD *)&v45 + 1) = v33;
        *(_QWORD *)(v4 + 136) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
      if ( v32 != v33 )
      {
        Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v45);
        v33 = (char *)*((_QWORD *)&v45 + 1);
        v32 = (char *)v45;
        if ( (_QWORD)v45 != *((_QWORD *)&v45 + 1) )
        {
          v34 = (char *)v45;
          do
          {
            std::_Func_class<void,>::_Tidy(v34);
            v34 += 64;
          }
          while ( v34 != v33 );
          v33 = v32;
        }
      }
      if ( !v32 )
        return v27;
      for ( i = v32; i != v33; i += 64 )
        std::_Func_class<void,>::_Tidy(i);
      v25 = (v46 - (_QWORD)v32) & 0xFFFFFFFFFFFFFFC0uLL;
      if ( v25 < 0x1000 )
      {
        v26 = v32;
LABEL_40:
        operator delete(v26, v25);
        return v27;
      }
      v26 = (char *)*((_QWORD *)v32 - 1);
      if ( (unsigned __int64)(v32 - v26 - 8) <= 0x1F )
      {
        v25 += 39LL;
        goto LABEL_40;
      }
LABEL_79:
      __fastfail(5u);
    }
LABEL_78:
    Microsoft::WRL2::FailFast::Unexpected("ContextSession end counts");
  }
  RoOriginateErrorW(2147483667LL, 0, L"The given object has already been closed / disposed and may no longer be used.");
  v16 = *(_DWORD *)(v4 + 72);
  v17 = v16 + *(_DWORD *)(v4 + 68);
  if ( --*(_DWORD *)(v4 + 64) != v17 )
    goto LABEL_78;
  v44 = 0;
  v43 = 0;
  if ( v16 || (v18 = (void **)(v4 + 120), &v43 == (__int128 *)(v4 + 120)) )
  {
    v20 = (char *)*((_QWORD *)&v43 + 1);
    v19 = (char *)v43;
  }
  else
  {
    v19 = (char *)*v18;
    *v18 = 0;
    v20 = *(char **)(v4 + 128);
    *(_QWORD *)(v4 + 128) = 0;
    v44 = *(_QWORD *)(v4 + 136);
    *(_QWORD *)&v43 = v19;
    *((_QWORD *)&v43 + 1) = v20;
    *(_QWORD *)(v4 + 136) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
  if ( v19 != v20 )
  {
    Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v43);
    v20 = (char *)*((_QWORD *)&v43 + 1);
    v19 = (char *)v43;
    if ( (_QWORD)v43 != *((_QWORD *)&v43 + 1) )
    {
      v35 = (char *)v43;
      do
      {
        std::_Func_class<void,>::_Tidy(v35);
        v35 += 64;
      }
      while ( v35 != v20 );
      v20 = v19;
    }
  }
  if ( !v19 )
    return 2147483667LL;
  for ( j = v19; j != v20; j += 64 )
    std::_Func_class<void,>::_Tidy(j);
  v22 = (v44 - (_QWORD)v19) & 0xFFFFFFFFFFFFFFC0uLL;
  if ( v22 < 0x1000 )
  {
    operator delete(v19, v22);
    return 2147483667LL;
  }
  v41 = (_BYTE *)*((_QWORD *)v19 - 1);
  if ( (unsigned __int64)(v19 - v41 - 8) > 0x1F )
    goto LABEL_79;
  operator delete(v41, v22 + 39);
  return 2147483667LL;
}

```

## disassembly

```asm
0x180011540  push    rbp
0x180011542  push    rbx
0x180011543  push    r12
0x180011545  push    r13
0x180011547  push    r14
0x180011549  mov     rbp, rsp
0x18001154c  sub     rsp, 60h
0x180011550  xor     r13d, r13d
0x180011553  lea     r14, [rcx-150h]
0x18001155a  mov     [rdx], r13
0x18001155d  mov     r12, rdx
0x180011560  mov     rbx, [r14+18h]
0x180011564  mov     eax, [rbx+5Ch]
0x180011567  test    eax, eax
0x180011569  jnz     loc_180011ADA
0x18001156f  mov     rcx, [rbx+38h]
0x180011573  add     rcx, 18h; lpCriticalSection
0x180011577  call    cs:__imp_EnterCriticalSection
0x18001157d  mov     eax, [rbx+44h]
0x180011580  add     eax, [rbx+48h]
0x180011583  mov     ecx, [rbx+40h]
0x180011586  cmp     ecx, eax
0x180011588  jnz     loc_180011AB9
0x18001158e  mov     [rsp+60h+arg_8], rsi
0x180011596  lea     eax, [rcx+1]
0x180011599  mov     [rbx+40h], eax
0x18001159c  test    byte ptr [r14+30h], 2
0x1800115a1  mov     [rsp+60h+arg_10], rdi
0x1800115a9  mov     [rsp+60h+arg_18], r15
0x1800115b1  jz      loc_18001172F
0x1800115b7  call    cs:__imp_GetProcessHeap
0x1800115bd  xor     edx, edx; dwFlags
0x1800115bf  mov     r8d, 0B0h; dwBytes
0x1800115c5  mov     rcx, rax; hHeap
0x1800115c8  call    cs:__imp_HeapAlloc
0x1800115ce  test    rax, rax
0x1800115d1  jz      loc_180011860
0x1800115d7  xor     edx, edx; Val
0x1800115d9  mov     r8d, 0B0h; Size
0x1800115df  mov     rcx, rax; void *
0x1800115e2  call    memset_0
0x1800115e7  mov     rsi, rax
0x1800115ea  mov     edi, 1
0x1800115ef  test    rax, rax
0x1800115f2  jz      loc_180011A55
0x1800115f8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800115ff  mov     [rax+10h], edi
0x180011602  mov     [rax+8], r13
0x180011606  test    rcx, rcx
0x180011609  jz      short loc_180011617
0x18001160b  mov     rax, [rcx]
0x18001160e  mov     rax, [rax+8]
0x180011612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011617  lea     rcx, [rsi+38h]; this
0x18001161b  call    ??0Api@CompositionObject@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CompositionObject::Api::Api(void)
0x180011620  lea     rcx, [rsi+70h]; this
0x180011624  call    ??0Partner@CompositionObject@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CompositionObject::Partner::Partner(void)
0x180011629  lea     rcx, ?s_defaultEmptyAllocatedStorage@CSparseStorage@@0VAllocatedStorage@1@A; CSparseStorage::AllocatedStorage CSparseStorage::s_defaultEmptyAllocatedStorage
0x180011630  mov     [rsi+80h], rcx
0x180011637  lea     rax, ??_7VisualCollection@Composition@UI@Windows@@6B@; const Windows::UI::Composition::VisualCollection::`vftable'
0x18001163e  lea     rcx, [rsi+90h]; this
0x180011645  mov     [rsi], rax
0x180011648  call    ??0Api@VisualCollection@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::VisualCollection::Api::Api(void)
0x18001164d  mov     [rsi+0A8h], r13
0x180011654  lea     rax, ?s_InterfaceType@VisualCollection@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::VisualCollection::s_InterfaceType
0x18001165b  mov     [rsi+8], rax
0x18001165f  cmp     [rsi+0A8h], r14
0x180011666  jz      short loc_1800116AB
0x180011668  mov     eax, edi
0x18001166a  lock xadd [r14+10h], eax
0x180011670  inc     eax
0x180011672  cmp     eax, edi
0x180011674  jz      loc_180011AC6
0x18001167a  mov     rcx, [rsi+0A8h]
0x180011681  mov     [rsi+0A8h], r14
0x180011688  test    rcx, rcx
0x18001168b  jz      short loc_1800116AB
0x18001168d  mov     eax, 0FFFFFFFFh
0x180011692  lock xadd [rcx+10h], eax
0x180011697  cmp     eax, edi
0x180011699  jnz     short loc_1800116AB
0x18001169b  mov     rax, [rcx]
0x18001169e  movzx   edx, dil
0x1800116a2  mov     rax, [rax+40h]
0x1800116a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ab  mov     r14, [r14+18h]
0x1800116af  mov     [rsi+18h], r14
0x1800116b3  cmp     r14, rsi
0x1800116b6  jz      loc_18001197B
0x1800116bc  lock xadd [r14+10h], edi
0x1800116c2  inc     edi
0x1800116c4  cmp     edi, 1
0x1800116c7  jz      loc_180011AE7
0x1800116cd  mov     rax, [r14+18h]
0x1800116d1  mov     rcx, [rax+38h]
0x1800116d5  mov     edi, [rcx+28h]
0x1800116d8  call    cs:__imp_GetCurrentThreadId
0x1800116de  cmp     edi, eax
0x1800116e0  jnz     short loc_1800116FD
0x1800116e2  mov     rcx, r13; this
0x1800116e5  mov     r8, [r14+28h]
0x1800116e9  lea     rdx, [r14+20h]
0x1800116ed  cmp     [r8], rdx
0x1800116f0  jz      loc_18001195F
0x1800116f6  mov     ecx, 3
0x1800116fb  int     29h; Win8: RtlFailFast(ecx)
0x1800116fd  mov     rcx, [r14+18h]; this
0x180011701  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180011706  test    byte ptr [r14+30h], 2
0x18001170b  mov     rcx, [r14+18h]; this
0x18001170f  jnz     short loc_1800116E5
0x180011711  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180011716  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18001171d  xor     edx, edx
0x18001171f  mov     ecx, 80000013h
0x180011724  call    cs:__imp_RoOriginateErrorW
0x18001172a  jmp     loc_18001197B
0x18001172f  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180011736  xor     edx, edx
0x180011738  mov     ecx, 80000013h
0x18001173d  call    cs:__imp_RoOriginateErrorW
0x180011743  mov     ecx, [rbx+44h]
0x180011746  mov     edx, [rbx+48h]
0x180011749  add     ecx, edx
0x18001174b  dec     dword ptr [rbx+40h]
0x18001174e  cmp     [rbx+40h], ecx
0x180011751  jnz     loc_180011B11
0x180011757  mov     [rbp+var_20], r13
0x18001175b  xorps   xmm0, xmm0
0x18001175e  movdqu  [rbp+var_30], xmm0
0x180011763  test    edx, edx
0x180011765  jnz     loc_180011A88
0x18001176b  lea     rcx, [rbx+78h]
0x18001176f  lea     rax, [rbp+var_30]
0x180011773  cmp     rax, rcx
0x180011776  jz      loc_180011A88
0x18001177c  mov     rsi, [rcx]
0x18001177f  mov     [rcx], r13
0x180011782  mov     rdi, [rcx+8]
0x180011786  mov     [rcx+8], r13
0x18001178a  mov     rax, [rcx+10h]
0x18001178e  mov     [rbp+var_20], rax
0x180011792  mov     qword ptr [rbp+var_30], rsi
0x180011796  mov     qword ptr [rbp+var_30+8], rdi
0x18001179a  mov     [rcx+10h], r13
0x18001179e  mov     rcx, [rbx+38h]
0x1800117a2  add     rcx, 18h; lpCriticalSection
0x1800117a6  call    cs:__imp_LeaveCriticalSection
0x1800117ac  cmp     rsi, rdi
0x1800117af  jnz     loc_180011929
0x1800117b5  test    rsi, rsi
0x1800117b8  jz      short loc_1800117F3
0x1800117ba  mov     rbx, rsi
0x1800117bd  cmp     rsi, rdi
0x1800117c0  jz      short loc_1800117D3
0x1800117c2  mov     rcx, rbx
0x1800117c5  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800117ca  add     rbx, 40h ; '@'
0x1800117ce  cmp     rbx, rdi
0x1800117d1  jnz     short loc_1800117C2
0x1800117d3  mov     rdx, [rbp+var_20]
0x1800117d7  sub     rdx, rsi
0x1800117da  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x1800117de  cmp     rdx, 1000h
0x1800117e5  jnb     loc_180011A95
0x1800117eb  mov     rcx, rsi; void *
0x1800117ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117f3  mov     eax, 80000013h
0x1800117f8  jmp     short loc_18001183B
0x1800117fa  test    rsi, rsi
0x1800117fd  jz      short loc_180011838
0x1800117ff  mov     rbx, rsi
0x180011802  cmp     rsi, rdi
0x180011805  jz      short loc_180011818
0x180011807  mov     rcx, rbx
0x18001180a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001180f  add     rbx, 40h ; '@'
0x180011813  cmp     rbx, rdi
0x180011816  jnz     short loc_180011807
0x180011818  mov     rdx, [rbp+var_8]
0x18001181c  sub     rdx, rsi
0x18001181f  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x180011823  cmp     rdx, 1000h
0x18001182a  jnb     loc_180011A6A
0x180011830  mov     rcx, rsi; void *
0x180011833  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011838  mov     eax, r15d
0x18001183b  mov     rdi, [rsp+60h+arg_10]
0x180011843  mov     rsi, [rsp+60h+arg_8]
0x18001184b  mov     r15, [rsp+60h+arg_18]
0x180011853  add     rsp, 60h
0x180011857  pop     r14
0x180011859  pop     r13
0x18001185b  pop     r12
0x18001185d  pop     rbx
0x18001185e  pop     rbp
0x18001185f  retn
0x180011860  mov     r15d, 8007000Eh
0x180011866  mov     edx, 5Bh ; '['; unsigned int
0x18001186b  mov     ecx, r15d; int
0x18001186e  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180011873  jmp     short loc_18001187F
0x180011875  mov     rax, r13
0x180011878  mov     [r12], rax
0x18001187c  mov     r15d, r13d
0x18001187f  mov     ecx, [rbx+44h]
0x180011882  mov     edx, [rbx+48h]
0x180011885  add     ecx, edx
0x180011887  dec     dword ptr [rbx+40h]
0x18001188a  cmp     [rbx+40h], ecx
0x18001188d  jnz     loc_180011B11
0x180011893  mov     [rbp+var_8], r13
0x180011897  xorps   xmm0, xmm0
0x18001189a  movdqu  [rbp+var_18], xmm0
0x18001189f  test    edx, edx
0x1800118a1  jnz     loc_180011A5D
0x1800118a7  lea     rcx, [rbx+78h]
0x1800118ab  lea     rax, [rbp+var_18]
0x1800118af  cmp     rax, rcx
0x1800118b2  jz      loc_180011A5D
0x1800118b8  mov     rsi, [rcx]
0x1800118bb  mov     [rcx], r13
0x1800118be  mov     rdi, [rcx+8]
0x1800118c2  mov     [rcx+8], r13
0x1800118c6  mov     rax, [rcx+10h]
0x1800118ca  mov     [rbp+var_8], rax
0x1800118ce  mov     qword ptr [rbp+var_18], rsi
0x1800118d2  mov     qword ptr [rbp+var_18+8], rdi
0x1800118d6  mov     [rcx+10h], r13
0x1800118da  mov     rcx, [rbx+38h]
0x1800118de  add     rcx, 18h; lpCriticalSection
0x1800118e2  call    cs:__imp_LeaveCriticalSection
0x1800118e8  cmp     rsi, rdi
0x1800118eb  jz      loc_1800117FA
0x1800118f1  lea     rcx, [rbp+var_18]
0x1800118f5  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x1800118fa  mov     rsi, qword ptr [rbp+var_18]
0x1800118fe  mov     rdi, qword ptr [rbp+var_18+8]
0x180011902  cmp     rsi, rdi
0x180011905  jz      loc_1800117FA
0x18001190b  mov     rbx, rsi
0x18001190e  xchg    ax, ax
0x180011910  mov     rcx, rbx
0x180011913  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011918  add     rbx, 40h ; '@'
0x18001191c  cmp     rbx, rdi
0x18001191f  jnz     short loc_180011910
0x180011921  mov     rdi, rsi
0x180011924  jmp     loc_1800117FA
0x180011929  lea     rcx, [rbp+var_30]
0x18001192d  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x180011932  mov     rsi, qword ptr [rbp+var_30]
0x180011936  mov     rdi, qword ptr [rbp+var_30+8]
0x18001193a  cmp     rsi, rdi
0x18001193d  jz      loc_1800117B5
0x180011943  mov     rbx, rsi
0x180011946  mov     rcx, rbx
0x180011949  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001194e  add     rbx, 40h ; '@'
0x180011952  cmp     rbx, rdi
0x180011955  jnz     short loc_180011946
0x180011957  mov     rdi, rsi
0x18001195a  jmp     loc_1800117B5
0x18001195f  mov     [rsi+20h], rdx
0x180011963  lea     rax, [rsi+20h]
0x180011967  mov     [rax+8], r8
0x18001196b  mov     [r8], rax
0x18001196e  mov     [rdx+8], rax
0x180011972  test    rcx, rcx
0x180011975  jnz     loc_180011AFB
0x18001197b  movzx   ecx, byte ptr [rsi+31h]
0x18001197f  lea     r9, [rsi+88h]
0x180011986  mov     byte ptr [rsi+30h], 1Fh
0x18001198a  mov     r8, rsi
0x18001198d  xor     cl, [r14+31h]
0x180011991  and     cl, 1
0x180011994  xor     [rsi+31h], cl
0x180011997  mov     rdx, [r14+198h]
0x18001199e  mov     rcx, [rdx+20h]
0x1800119a2  mov     edx, [rdx+40h]
0x1800119a5  mov     rax, [rcx]
0x1800119a8  mov     rax, [rax+18h]
0x1800119ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b1  mov     r15d, eax
0x1800119b4  test    eax, eax
0x1800119b6  js      short loc_180011A1C
0x1800119b8  movzx   eax, byte ptr [r14+1B4h]
0x1800119c0  test    al, 1
0x1800119c2  jnz     short loc_1800119F3
0x1800119c4  or      al, 1
0x1800119c6  mov     [r14+1B4h], al
0x1800119cd  cmp     [r14+1B0h], r13d
0x1800119d4  jnz     short loc_1800119F3
0x1800119d6  mov     rcx, [r14+1A0h]
0x1800119dd  mov     dl, 1
0x1800119df  mov     rax, [rcx]
0x1800119e2  mov     rax, [rax+30h]
0x1800119e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119eb  test    eax, eax
0x1800119ed  js      loc_180011B05
  ... truncated ...
```
