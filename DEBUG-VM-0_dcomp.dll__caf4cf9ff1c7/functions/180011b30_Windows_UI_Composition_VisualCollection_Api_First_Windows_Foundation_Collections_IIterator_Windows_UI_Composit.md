# Windows::UI::Composition::VisualCollection::Api::First(Windows::Foundation::Collections::IIterator<Windows::UI::Composition::Visual *> * *)

- ea: `0x180011b30`
- end: `0x1800120db`
- name: `?First@Api@VisualCollection@Composition@UI@Windows@@UEAAJPEAPEAU?$IIterator@PEAVVisual@Composition@UI@Windows@@@Collections@Foundation@5@@Z`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180010f90`
- `0x180011b30`
- `0x180012da0`
- `0x180012ee8`
- `0x180013528`
- `0x18001358c`
- `0x180014e14`
- `0x180036f90`
- `0x1800e77ac`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011dd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011dd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011dbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e82`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011cf7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011ec9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011cf7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180011ec9`

## string_xrefs

- `0x180011ce9`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180011ebb`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180011bc3`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisualcollection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCollection::Api::First(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rsi
  int v5; // ecx
  int v6; // eax
  unsigned int v7; // r15d
  int v8; // edx
  int v9; // ecx
  void **v10; // rcx
  char *v11; // r14
  char *v12; // rdi
  char *v13; // rbx
  char *i; // rbx
  unsigned __int64 v15; // rdx
  char *v16; // rcx
  int v18; // edx
  int v19; // ecx
  void **v20; // rcx
  char *v21; // r14
  char *v22; // rdi
  char *j; // rbx
  unsigned __int64 v24; // rdx
  __int64 v25; // r12
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v27; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v28; // rcx
  volatile signed __int32 *v29; // r14
  int v30; // ebx
  Microsoft::WRL2::ContextSession *v31; // rcx
  volatile signed __int32 **v32; // r8
  char *v33; // rbx
  char v34; // cl
  volatile signed __int32 *v35; // rcx
  volatile signed __int32 *v36; // rbx
  volatile signed __int32 *v37; // rcx
  _BYTE *v38; // rcx
  __int128 v39; // [rsp+20h] [rbp-30h] BYREF
  __int64 v40; // [rsp+30h] [rbp-20h]
  __int128 v41; // [rsp+38h] [rbp-18h] BYREF
  __int64 v42; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  *a2 = 0;
  v4 = *(_QWORD *)(a1 - 120);
  if ( *(_DWORD *)(v4 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
  v5 = *(_DWORD *)(v4 + 64);
  if ( v5 != *(_DWORD *)(v4 + 72) + *(_DWORD *)(v4 + 68) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v4 + 64) = v5 + 1;
  if ( (*(_BYTE *)(a1 - 96) & 2) != 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 248LL))(*(_QWORD *)(a1 + 24));
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisualcollection.cpp",
        (const char *)(unsigned int)v6,
        v39);
      DoStackCaptureDirect(v7, 0x110u);
      goto LABEL_6;
    }
    v25 = *(_QWORD *)(a1 + 24);
    ProcessHeap = GetProcessHeap();
    v27 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 0, 0x58u);
    if ( !v27 )
    {
      v7 = -2147024882;
      DoStackCaptureDirect(-2147024882, 0x115u);
      goto LABEL_6;
    }
    *(_OWORD *)v27 = 0;
    *((_OWORD *)v27 + 1) = 0;
    *((_OWORD *)v27 + 2) = 0;
    *((_OWORD *)v27 + 3) = 0;
    *((_OWORD *)v27 + 4) = 0;
    *((_QWORD *)v27 + 10) = 0;
    v28 = Microsoft::WRL::Details::ModuleBase::module_;
    *((_DWORD *)v27 + 4) = 1;
    *((_QWORD *)v27 + 1) = 0;
    if ( v28 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v28 + 8LL))(v28);
    *(_QWORD *)v27 = &Windows::UI::Composition::VisualIterator::`vftable';
    Windows::UI::Composition::VisualIterator::Api::Api((Windows::UI::Composition::VisualIterator::Api *)(v27 + 14));
    *((_QWORD *)v27 + 9) = 0;
    *((_QWORD *)v27 + 10) = 0;
    *((_QWORD *)v27 + 1) = &Windows::UI::Composition::VisualIterator::s_InterfaceType;
    v29 = *(volatile signed __int32 **)(v25 + 24);
    *((_QWORD *)v27 + 3) = v29;
    if ( v29 != v27 )
    {
      if ( _InterlockedIncrement(v29 + 4) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 80LL))(v29);
      v30 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v29 + 3) + 56LL) + 40LL);
      if ( v30 == GetCurrentThreadId() )
      {
        v31 = 0;
LABEL_41:
        v32 = (volatile signed __int32 **)*((_QWORD *)v29 + 5);
        if ( *v32 != v29 + 8 )
          __fastfail(3u);
        *((_QWORD *)v27 + 4) = v29 + 8;
        *((_QWORD *)v27 + 5) = v32;
        *v32 = v27 + 8;
        *((_QWORD *)v29 + 5) = v27 + 8;
        if ( v31 )
          Microsoft::WRL2::ContextSession::EndApiEntry(v31);
        goto LABEL_51;
      }
      Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)v29 + 3));
      v31 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)v29 + 3);
      if ( (v29[12] & 2) != 0 )
        goto LABEL_41;
      Microsoft::WRL2::ContextSession::EndApiEntry(v31);
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
    }
LABEL_51:
    v34 = *((_BYTE *)v27 + 49);
    *((_BYTE *)v27 + 48) = 31;
    *((_BYTE *)v27 + 49) ^= (*((_BYTE *)v29 + 49) ^ v34) & 1;
    if ( *((_QWORD *)v27 + 9) != v25 )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)(v25 + 16)) == 1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      v35 = (volatile signed __int32 *)*((_QWORD *)v27 + 9);
      *((_QWORD *)v27 + 9) = v25;
      if ( v35 && _InterlockedExchangeAdd(v35 + 4, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v35 + 64LL))(v35, 1);
    }
    v36 = *(volatile signed __int32 **)(v25 + 160);
    if ( *((volatile signed __int32 **)v27 + 10) != v36 )
    {
      if ( v36 && _InterlockedIncrement(v36 + 4) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 80LL))(v36);
      v37 = (volatile signed __int32 *)*((_QWORD *)v27 + 10);
      *((_QWORD *)v27 + 10) = v36;
      if ( v37 && _InterlockedExchangeAdd(v37 + 4, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v37 + 64LL))(v37, 1);
    }
    v7 = 0;
    *a2 = v27 + 14;
LABEL_6:
    v8 = *(_DWORD *)(v4 + 72);
    v9 = v8 + *(_DWORD *)(v4 + 68);
    if ( --*(_DWORD *)(v4 + 64) == v9 )
    {
      v42 = 0;
      v41 = 0;
      if ( v8 || (v10 = (void **)(v4 + 120), &v41 == (__int128 *)(v4 + 120)) )
      {
        v12 = (char *)*((_QWORD *)&v41 + 1);
        v11 = (char *)v41;
      }
      else
      {
        v11 = (char *)*v10;
        *v10 = 0;
        v12 = *(char **)(v4 + 128);
        *(_QWORD *)(v4 + 128) = 0;
        v42 = *(_QWORD *)(v4 + 136);
        *(_QWORD *)&v41 = v11;
        *((_QWORD *)&v41 + 1) = v12;
        *(_QWORD *)(v4 + 136) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
      if ( v11 != v12 )
      {
        Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v41);
        v12 = (char *)*((_QWORD *)&v41 + 1);
        v11 = (char *)v41;
        if ( (_QWORD)v41 != *((_QWORD *)&v41 + 1) )
        {
          v13 = (char *)v41;
          do
          {
            std::_Func_class<void,>::_Tidy(v13);
            v13 += 64;
          }
          while ( v13 != v12 );
          v12 = v11;
        }
      }
      if ( !v11 )
        return v7;
      for ( i = v11; i != v12; i += 64 )
        std::_Func_class<void,>::_Tidy(i);
      v15 = (v42 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFC0uLL;
      if ( v15 < 0x1000 )
      {
        v16 = v11;
LABEL_20:
        operator delete(v16, v15);
        return v7;
      }
      v16 = (char *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v16 - 8) <= 0x1F )
      {
        v15 += 39LL;
        goto LABEL_20;
      }
LABEL_75:
      __fastfail(5u);
    }
LABEL_74:
    Microsoft::WRL2::FailFast::Unexpected("ContextSession end counts");
  }
  RoOriginateErrorW(2147483667LL, 0, L"The given object has already been closed / disposed and may no longer be used.");
  v18 = *(_DWORD *)(v4 + 72);
  v19 = v18 + *(_DWORD *)(v4 + 68);
  if ( --*(_DWORD *)(v4 + 64) != v19 )
    goto LABEL_74;
  v40 = 0;
  v39 = 0;
  if ( v18 || (v20 = (void **)(v4 + 120), &v39 == (__int128 *)(v4 + 120)) )
  {
    v22 = (char *)*((_QWORD *)&v39 + 1);
    v21 = (char *)v39;
  }
  else
  {
    v21 = (char *)*v20;
    *v20 = 0;
    v22 = *(char **)(v4 + 128);
    *(_QWORD *)(v4 + 128) = 0;
    v40 = *(_QWORD *)(v4 + 136);
    *(_QWORD *)&v39 = v21;
    *((_QWORD *)&v39 + 1) = v22;
    *(_QWORD *)(v4 + 136) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 56) + 24LL));
  if ( v21 != v22 )
  {
    Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v39);
    v22 = (char *)*((_QWORD *)&v39 + 1);
    v21 = (char *)v39;
    if ( (_QWORD)v39 != *((_QWORD *)&v39 + 1) )
    {
      v33 = (char *)v39;
      do
      {
        std::_Func_class<void,>::_Tidy(v33);
        v33 += 64;
      }
      while ( v33 != v22 );
      v22 = v21;
    }
  }
  if ( !v21 )
    return 2147483667LL;
  for ( j = v21; j != v22; j += 64 )
    std::_Func_class<void,>::_Tidy(j);
  v24 = (v40 - (_QWORD)v21) & 0xFFFFFFFFFFFFFFC0uLL;
  if ( v24 < 0x1000 )
  {
    operator delete(v21, v24);
    return 2147483667LL;
  }
  v38 = (_BYTE *)*((_QWORD *)v21 - 1);
  if ( (unsigned __int64)(v21 - v38 - 8) > 0x1F )
    goto LABEL_75;
  operator delete(v38, v24 + 39);
  return 2147483667LL;
}

```

## disassembly

```asm
0x180011b30  push    rbp
0x180011b32  push    rbx
0x180011b33  push    rsi
0x180011b34  push    r12
0x180011b36  push    r13
0x180011b38  mov     rbp, rsp
0x180011b3b  sub     rsp, 50h
0x180011b3f  xor     r12d, r12d
0x180011b42  mov     r13, rdx
0x180011b45  mov     [rdx], r12
0x180011b48  mov     rbx, rcx
0x180011b4b  mov     rsi, [rcx-78h]
0x180011b4f  mov     eax, [rsi+5Ch]
0x180011b52  test    eax, eax
0x180011b54  jnz     loc_180012073
0x180011b5a  mov     rcx, [rsi+38h]
0x180011b5e  add     rcx, 18h; lpCriticalSection
0x180011b62  call    cs:__imp_EnterCriticalSection
0x180011b68  mov     eax, [rsi+44h]
0x180011b6b  add     eax, [rsi+48h]
0x180011b6e  mov     ecx, [rsi+40h]
0x180011b71  cmp     ecx, eax
0x180011b73  jnz     loc_180012066
0x180011b79  mov     [rsp+50h+arg_8], rdi
0x180011b81  lea     eax, [rcx+1]
0x180011b84  mov     [rsi+40h], eax
0x180011b87  test    byte ptr [rbx-60h], 2
0x180011b8b  mov     [rsp+50h+arg_10], r14
0x180011b93  mov     [rsp+50h+arg_18], r15
0x180011b9b  jz      loc_180011CE9
0x180011ba1  mov     rcx, [rbx+18h]
0x180011ba5  mov     rax, [rcx]
0x180011ba8  mov     rax, [rax+0F8h]
0x180011baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb4  mov     r15d, eax
0x180011bb7  test    eax, eax
0x180011bb9  jns     loc_180011DBB
0x180011bbf  mov     rcx, [rbp+28h]; this
0x180011bc3  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180011bca  mov     r9d, eax; char *
0x180011bcd  mov     edx, 45h ; 'E'; void *
0x180011bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bd7  mov     edx, 110h; unsigned int
0x180011bdc  mov     ecx, r15d; int
0x180011bdf  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180011be4  mov     ecx, [rsi+44h]
0x180011be7  mov     edx, [rsi+48h]
0x180011bea  add     ecx, edx
0x180011bec  dec     dword ptr [rsi+40h]
0x180011bef  cmp     [rsi+40h], ecx
0x180011bf2  jnz     loc_1800120C7
0x180011bf8  mov     [rbp+var_8], r12
0x180011bfc  xorps   xmm0, xmm0
0x180011bff  movdqu  [rbp+var_18], xmm0
0x180011c04  test    edx, edx
0x180011c06  jnz     loc_180012006
0x180011c0c  lea     rcx, [rsi+78h]
0x180011c10  lea     rax, [rbp+var_18]
0x180011c14  cmp     rax, rcx
0x180011c17  jz      loc_180012006
0x180011c1d  mov     r14, [rcx]
0x180011c20  mov     [rcx], r12
0x180011c23  mov     rdi, [rcx+8]
0x180011c27  mov     [rcx+8], r12
0x180011c2b  mov     rax, [rcx+10h]
0x180011c2f  mov     [rbp+var_8], rax
0x180011c33  mov     qword ptr [rbp+var_18], r14
0x180011c37  mov     qword ptr [rbp+var_18+8], rdi
0x180011c3b  mov     [rcx+10h], r12
0x180011c3f  mov     rcx, [rsi+38h]
0x180011c43  add     rcx, 18h; lpCriticalSection
0x180011c47  call    cs:__imp_LeaveCriticalSection
0x180011c4d  cmp     r14, rdi
0x180011c50  jz      short loc_180011C84
0x180011c52  lea     rcx, [rbp+var_18]
0x180011c56  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x180011c5b  mov     r14, qword ptr [rbp+var_18]
0x180011c5f  mov     rdi, qword ptr [rbp+var_18+8]
0x180011c63  cmp     r14, rdi
0x180011c66  jz      short loc_180011C84
0x180011c68  mov     rbx, r14
0x180011c6b  nop     dword ptr [rax+rax+00h]
0x180011c70  mov     rcx, rbx
0x180011c73  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011c78  add     rbx, 40h ; '@'
0x180011c7c  cmp     rbx, rdi
0x180011c7f  jnz     short loc_180011C70
0x180011c81  mov     rdi, r14
0x180011c84  test    r14, r14
0x180011c87  jz      short loc_180011CC2
0x180011c89  mov     rbx, r14
0x180011c8c  cmp     r14, rdi
0x180011c8f  jz      short loc_180011CA2
0x180011c91  mov     rcx, rbx
0x180011c94  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011c99  add     rbx, 40h ; '@'
0x180011c9d  cmp     rbx, rdi
0x180011ca0  jnz     short loc_180011C91
0x180011ca2  mov     rdx, [rbp+var_8]
0x180011ca6  sub     rdx, r14
0x180011ca9  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x180011cad  cmp     rdx, 1000h
0x180011cb4  jnb     loc_180012020
0x180011cba  mov     rcx, r14; void *
0x180011cbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011cc2  mov     eax, r15d
0x180011cc5  mov     r14, [rsp+50h+arg_10]
0x180011ccd  mov     rdi, [rsp+50h+arg_8]
0x180011cd5  mov     r15, [rsp+50h+arg_18]
0x180011cdd  add     rsp, 50h
0x180011ce1  pop     r13
0x180011ce3  pop     r12
0x180011ce5  pop     rsi
0x180011ce6  pop     rbx
0x180011ce7  pop     rbp
0x180011ce8  retn
0x180011ce9  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180011cf0  xor     edx, edx
0x180011cf2  mov     ecx, 80000013h
0x180011cf7  call    cs:__imp_RoOriginateErrorW
0x180011cfd  mov     ecx, [rsi+44h]
0x180011d00  mov     edx, [rsi+48h]
0x180011d03  add     ecx, edx
0x180011d05  dec     dword ptr [rsi+40h]
0x180011d08  cmp     [rsi+40h], ecx
0x180011d0b  jnz     loc_1800120C7
0x180011d11  mov     [rbp+var_20], r12
0x180011d15  xorps   xmm0, xmm0
0x180011d18  movdqu  [rbp+var_30], xmm0
0x180011d1d  test    edx, edx
0x180011d1f  jnz     loc_180012013
0x180011d25  lea     rcx, [rsi+78h]
0x180011d29  lea     rax, [rbp+var_30]
0x180011d2d  cmp     rax, rcx
0x180011d30  jz      loc_180012013
0x180011d36  mov     r14, [rcx]
0x180011d39  mov     [rcx], r12
0x180011d3c  mov     rdi, [rcx+8]
0x180011d40  mov     [rcx+8], r12
0x180011d44  mov     rax, [rcx+10h]
0x180011d48  mov     [rbp+var_20], rax
0x180011d4c  mov     qword ptr [rbp+var_30], r14
0x180011d50  mov     qword ptr [rbp+var_30+8], rdi
0x180011d54  mov     [rcx+10h], r12
0x180011d58  mov     rcx, [rsi+38h]
0x180011d5c  add     rcx, 18h; lpCriticalSection
0x180011d60  call    cs:__imp_LeaveCriticalSection
0x180011d66  cmp     r14, rdi
0x180011d69  jnz     loc_180011ED1
0x180011d6f  test    r14, r14
0x180011d72  jz      short loc_180011DB1
0x180011d74  mov     rbx, r14
0x180011d77  cmp     r14, rdi
0x180011d7a  jz      short loc_180011D91
0x180011d7c  nop     dword ptr [rax+00h]
0x180011d80  mov     rcx, rbx
0x180011d83  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011d88  add     rbx, 40h ; '@'
0x180011d8c  cmp     rbx, rdi
0x180011d8f  jnz     short loc_180011D80
0x180011d91  mov     rdx, [rbp+var_20]
0x180011d95  sub     rdx, r14
0x180011d98  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x180011d9c  cmp     rdx, 1000h
0x180011da3  jnb     loc_18001203E
0x180011da9  mov     rcx, r14; void *
0x180011dac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011db1  mov     eax, 80000013h
0x180011db6  jmp     loc_180011CC5
0x180011dbb  mov     r12, [rbx+18h]
0x180011dbf  call    cs:__imp_GetProcessHeap
0x180011dc5  xor     edx, edx; dwFlags
0x180011dc7  mov     r8d, 58h ; 'X'; dwBytes
0x180011dcd  mov     rcx, rax; hHeap
0x180011dd0  call    cs:__imp_HeapAlloc
0x180011dd6  mov     rdi, rax
0x180011dd9  test    rax, rax
0x180011ddc  jz      loc_180011FEB
0x180011de2  xorps   xmm0, xmm0
0x180011de5  xor     eax, eax
0x180011de7  mov     r15d, 1
0x180011ded  movups  xmmword ptr [rdi], xmm0
0x180011df0  movups  xmmword ptr [rdi+10h], xmm0
0x180011df4  movups  xmmword ptr [rdi+20h], xmm0
0x180011df8  movups  xmmword ptr [rdi+30h], xmm0
0x180011dfc  movups  xmmword ptr [rdi+40h], xmm0
0x180011e00  mov     [rdi+50h], rax
0x180011e04  test    rdi, rdi
0x180011e07  jz      short loc_180011E46
0x180011e09  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180011e10  xor     ebx, ebx
0x180011e12  mov     [rdi+10h], r15d
0x180011e16  mov     [rdi+8], rbx
0x180011e1a  test    rcx, rcx
0x180011e1d  jz      short loc_180011E2B
0x180011e1f  mov     rax, [rcx]
0x180011e22  mov     rax, [rax+8]
0x180011e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e2b  lea     rax, ??_7VisualIterator@Composition@UI@Windows@@6B@; const Windows::UI::Composition::VisualIterator::`vftable'
0x180011e32  lea     rcx, [rdi+38h]; this
0x180011e36  mov     [rdi], rax
0x180011e39  call    ??0Api@VisualIterator@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::VisualIterator::Api::Api(void)
0x180011e3e  mov     [rdi+48h], rbx
0x180011e42  mov     [rdi+50h], rbx
0x180011e46  lea     rax, ?s_InterfaceType@VisualIterator@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::VisualIterator::s_InterfaceType
0x180011e4d  mov     [rdi+8], rax
0x180011e51  mov     r14, [r12+18h]
0x180011e56  mov     [rdi+18h], r14
0x180011e5a  cmp     r14, rdi
0x180011e5d  jz      loc_180011F25
0x180011e63  mov     eax, r15d
0x180011e66  lock xadd [r14+10h], eax
0x180011e6c  inc     eax
0x180011e6e  cmp     eax, r15d
0x180011e71  jz      loc_1800120A9
0x180011e77  mov     rax, [r14+18h]
0x180011e7b  mov     rcx, [rax+38h]
0x180011e7f  mov     ebx, [rcx+28h]
0x180011e82  call    cs:__imp_GetCurrentThreadId
0x180011e88  cmp     ebx, eax
0x180011e8a  jnz     short loc_180011EA2
0x180011e8c  xor     ecx, ecx; this
0x180011e8e  mov     r8, [r14+28h]
0x180011e92  lea     rdx, [r14+20h]
0x180011e96  cmp     [r8], rdx
0x180011e99  jz      short loc_180011F09
0x180011e9b  mov     ecx, 3
0x180011ea0  int     29h; Win8: RtlFailFast(ecx)
0x180011ea2  mov     rcx, [r14+18h]; this
0x180011ea6  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180011eab  test    byte ptr [r14+30h], 2
0x180011eb0  mov     rcx, [r14+18h]; this
0x180011eb4  jnz     short loc_180011E8E
0x180011eb6  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180011ebb  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180011ec2  xor     edx, edx
0x180011ec4  mov     ecx, 80000013h
0x180011ec9  call    cs:__imp_RoOriginateErrorW
0x180011ecf  jmp     short loc_180011F25
0x180011ed1  lea     rcx, [rbp+var_30]
0x180011ed5  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x180011eda  mov     r14, qword ptr [rbp+var_30]
0x180011ede  mov     rdi, qword ptr [rbp+var_30+8]
0x180011ee2  cmp     r14, rdi
0x180011ee5  jz      loc_180011D6F
0x180011eeb  mov     rbx, r14
0x180011eee  xchg    ax, ax
0x180011ef0  mov     rcx, rbx
0x180011ef3  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011ef8  add     rbx, 40h ; '@'
0x180011efc  cmp     rbx, rdi
0x180011eff  jnz     short loc_180011EF0
0x180011f01  mov     rdi, r14
0x180011f04  jmp     loc_180011D6F
0x180011f09  mov     [rdi+20h], rdx
0x180011f0d  lea     rax, [rdi+20h]
0x180011f11  mov     [rax+8], r8
0x180011f15  mov     [r8], rax
0x180011f18  mov     [rdx+8], rax
0x180011f1c  test    rcx, rcx
0x180011f1f  jnz     loc_1800120BD
0x180011f25  movzx   ecx, byte ptr [rdi+31h]
0x180011f29  mov     byte ptr [rdi+30h], 1Fh
0x180011f2d  xor     cl, [r14+31h]
0x180011f31  mov     r14d, 0FFFFFFFFh
0x180011f37  and     cl, r15b
0x180011f3a  xor     [rdi+31h], cl
0x180011f3d  cmp     [rdi+48h], r12
0x180011f41  jz      short loc_180011F82
0x180011f43  mov     eax, r15d
0x180011f46  lock xadd [r12+10h], eax
0x180011f4d  inc     eax
0x180011f4f  cmp     eax, r15d
0x180011f52  jz      loc_180012080
0x180011f58  mov     rcx, [rdi+48h]
0x180011f5c  mov     [rdi+48h], r12
0x180011f60  test    rcx, rcx
0x180011f63  jz      short loc_180011F82
0x180011f65  mov     eax, r14d
0x180011f68  lock xadd [rcx+10h], eax
0x180011f6d  cmp     eax, r15d
0x180011f70  jnz     short loc_180011F82
0x180011f72  mov     rax, [rcx]
0x180011f75  movzx   edx, r15b
0x180011f79  mov     rax, [rax+40h]
0x180011f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f82  mov     rbx, [r12+0A0h]
0x180011f8a  cmp     [rdi+50h], rbx
0x180011f8e  jz      short loc_180011FD1
0x180011f90  test    rbx, rbx
0x180011f93  jz      short loc_180011FA8
0x180011f95  lock xadd [rbx+10h], r15d
0x180011f9b  inc     r15d
0x180011f9e  cmp     r15d, 1
0x180011fa2  jz      loc_180012095
0x180011fa8  mov     rcx, [rdi+50h]
0x180011fac  mov     [rdi+50h], rbx
0x180011fb0  test    rcx, rcx
0x180011fb3  jz      short loc_180011FD1
0x180011fb5  lock xadd [rcx+10h], r14d
  ... truncated ...
```
