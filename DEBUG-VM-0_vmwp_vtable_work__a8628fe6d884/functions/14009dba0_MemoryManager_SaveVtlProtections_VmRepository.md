# MemoryManager::SaveVtlProtections(VmRepository *)

- ea: `0x14009dba0`
- end: `0x14009e46e`
- name: `?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z`
- size: `2254`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct VmRepository *)`
- caller_count: `3`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14009abe0`
- `0x14009c004`
- `0x1400cfa88`

## callees

- `0x140023da0`
- `0x140023f74`
- `0x14003364c`
- `0x140040fd8`
- `0x1400417a8`
- `0x140054508`
- `0x140054630`
- `0x14005b628`
- `0x14005ecc4`
- `0x14006af38`
- `0x14009cfd0`
- `0x14009d7ac`
- `0x14009d7cc`
- `0x14009dba0`
- `0x1400e5a8c`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x140172cf0`
- `0x1401fec18`
- `0x140201664`
- `0x140201a2c`
- `0x1402023e8`
- `0x140203024`
- `0x140203484`
- `0x140204698`
- `0x14020e5a0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009e05d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14009e05d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009e25c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14009e25c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009dff7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14009dff7`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009e147`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x14009e147`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009e1cf`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14009e1cf`
- `ntdll!NtQuerySystemInformation` at `0x14009dd02`
- `ntdll!NtQuerySystemInformation` at `0x14009dd02`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009e0ac`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x14009e0ac`
- `vid!VidVsmQueryProtectionsDirty` at `0x14009dc8b`
- `vid!VidVsmQueryProtectionsDirty` at `0x14009dc8b`

## string_xrefs

- `0x14009de43`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MemoryManager::SaveVtlProtections(MemoryManager *this, struct VmRepository *a2)
{
  int v4; // r13d
  __int64 v5; // r8
  int v6; // eax
  const char *v7; // r9
  NTSTATUS v8; // eax
  __int64 v9; // r15
  __int64 v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rsi
  _BYTE *First; // rax
  __int64 v15; // r9
  _BYTE *v16; // rdi
  _BYTE *v17; // rcx
  _BYTE **v18; // rbx
  ULONG_PTR v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  const char *v24; // r9
  const char *v25; // r9
  unsigned __int64 v26; // r12
  __int64 i; // rcx
  unsigned __int64 v28; // r12
  unsigned __int64 v29; // r15
  unsigned __int64 j; // r12
  _QWORD *v31; // rax
  const char *v32; // r9
  __int64 **v33; // rcx
  __int64 *k; // rax
  __int64 *v35; // rbx
  __int64 *m; // rcx
  __int64 v37; // r9
  HANDLE *v38; // rbx
  HANDLE *v39; // rdi
  const char *v40; // r9
  __int64 *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rdx
  _OWORD *v45; // rax
  __int64 **v46; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  int v49; // eax
  int cbSize; // [rsp+20h] [rbp-568h]
  _OWORD *v52; // [rsp+48h] [rbp-540h] BYREF
  __int64 v53; // [rsp+50h] [rbp-538h]
  __int64 v54; // [rsp+58h] [rbp-530h]
  __int64 v55; // [rsp+60h] [rbp-528h] BYREF
  char *v56[2]; // [rsp+68h] [rbp-520h] BYREF
  __int64 v57; // [rsp+78h] [rbp-510h]
  _BYTE v58[8]; // [rsp+80h] [rbp-508h] BYREF
  void *v59; // [rsp+88h] [rbp-500h] BYREF
  DWORD ExitCode[2]; // [rsp+90h] [rbp-4F8h] BYREF
  int v61; // [rsp+98h] [rbp-4F0h] BYREF
  ULONG ReturnLength; // [rsp+9Ch] [rbp-4ECh] BYREF
  __int128 v63; // [rsp+A0h] [rbp-4E8h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-4D8h]
  ULONG_PTR Size[2]; // [rsp+C0h] [rbp-4C8h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-4B8h] BYREF
  char v67; // [rsp+D8h] [rbp-4B0h]
  _QWORD v68[2]; // [rsp+E0h] [rbp-4A8h] BYREF
  __int64 **v69; // [rsp+F0h] [rbp-498h]
  __int64 v70; // [rsp+F8h] [rbp-490h]
  __int128 Value; // [rsp+100h] [rbp-488h] BYREF
  _OWORD v72[3]; // [rsp+110h] [rbp-478h] BYREF
  _BYTE SystemInformation[1040]; // [rsp+140h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+0h]

  v4 = 0;
  ReturnLength = 0;
  if ( *((_DWORD *)this + 36) >= 0x700u )
  {
    v61 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 448LL))(*((_QWORD *)this + 4));
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 88LL))(v5, &v61);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17F0,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)(unsigned int)v6,
        cbSize);
    if ( ((1 << v61) & 0x1C) == 0 && (*((_DWORD *)this + 96) || MemoryManager::AreAnySecureVtlsEnabled(this)) )
    {
      v58[0] = 0;
      if ( !(unsigned int)VidVsmQueryProtectionsDirty(*((_QWORD *)this + 2), v58) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1809,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          v7);
      if ( !*((_DWORD *)this + 96) || v58[0] )
      {
        memset_0(SystemInformation, 0, 0x408u);
        ReturnLength = 0;
        v8 = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, &ReturnLength);
        if ( v8 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x1827,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v8,
            cbSize);
        v9 = Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(retaddr);
        v55 = v9;
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
        Size[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 88LL))(v10);
        *(_OWORD *)v56 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v56, a2, 1);
        if ( SLODWORD(v56[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1830,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)LODWORD(v56[1]),
            cbSize);
        v66 = 0;
        v67 = 0;
        v68[0] = 0;
        v68[1] = 0;
        v11 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
        *v11 = v11;
        v11[1] = v11;
        v11[2] = v11;
        *((_WORD *)v11 + 12) = 257;
        v68[0] = v11;
        v69 = 0;
        v70 = 0;
        v12 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
        *v12 = v12;
        v12[1] = v12;
        v12[2] = v12;
        *((_WORD *)v12 + 12) = 257;
        v69 = (__int64 **)v12;
        v13 = *((_QWORD *)this + 20) + 24LL;
        if ( !(unsigned int)RrwLockAcquireShared(v13, 0xFFFFFFFFLL) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            cbSize);
        v57 = v13;
        *(_QWORD *)ExitCode = 0;
        First = (_BYTE *)MemoryBlockContainer::IteratorGetFirst(*((_QWORD *)this + 20), ExitCode);
        v16 = First;
        v59 = First;
        if ( First )
        {
          v17 = First;
          v18 = *(_BYTE ***)ExitCode;
          v19 = Size[0];
          do
          {
            if ( *v16 )
            {
              Size[0] = 0;
              Size[1] = 0;
              LOBYTE(v15) = 1;
              LOBYTE(v20) = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONG_PTR *, __int64))(*(_QWORD *)v9 + 16LL))(
                              v9,
                              *(unsigned __int8 *)((unsigned __int8)v17[184] + v19 + 280),
                              Size,
                              v15);
              LOWORD(ExitCode[0]) = (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 48LL))(
                                      v9,
                                      v20);
              v21 = std::map<unsigned short,std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>>::_Try_emplace<unsigned short const &,>(
                      v68,
                      &v52,
                      ExitCode);
              v22 = *(_QWORD *)v21 + 40LL;
              v23 = *(_QWORD *)(*(_QWORD *)v21 + 48LL);
              if ( v23 == *(_QWORD *)(*(_QWORD *)v21 + 56LL) )
              {
                std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>::_Emplace_reallocate<MemoryBlock * &>(
                  (const void **)v22,
                  (_BYTE *)v23,
                  (__int64 *)&v59);
              }
              else
              {
                *(_QWORD *)v23 = v16;
                *(_QWORD *)(v23 + 8) = 0;
                *(_QWORD *)(v22 + 8) += 16LL;
              }
            }
            if ( v18 == *(_BYTE ***)(*((_QWORD *)this + 20) + 8LL) )
              break;
            v16 = *v18++;
            v59 = v16;
            v17 = v16;
          }
          while ( v16 );
        }
        v63 = 0;
        v64 = 0;
        try
        {
          v35 = *(__int64 **)v68[0];
          while ( !*((_BYTE *)v35 + 25) )
          {
            Value = *(_OWORD *)&SystemInformation[16 * *((unsigned __int16 *)v35 + 16) + 8];
            memset(v72, 0, sizeof(v72));
            Size[0] = 48;
            if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v72, 1u, 0, Size) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1877,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v24);
            v52 = v72;
            LOBYTE(v53) = 1;
            if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v72, 0, 0x30003u, &Value, 0x10u, 0, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1885,
                (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                v25);
            v26 = 0;
            for ( i = v35[5]; i != v35[6]; i += 16 )
              v26 += *(_QWORD *)(*(_QWORD *)i + 120LL);
            v28 = v26 >> 22;
            v29 = (unsigned __int64)(unsigned int)RtlNumberOfSetBitsUlongPtr(Value) >> 1;
            if ( v29 >= v28 )
              v29 = v28;
            if ( v29 <= 8 )
            {
              if ( !v29 )
                v29 = 1;
            }
            else
            {
              v29 = 8;
            }
            for ( j = 0; j < v29; ++j )
            {
              v31 = operator new(0x18u);
              *(_WORD *)v31 = *((_WORD *)v35 + 16);
              v31[1] = this;
              v31[2] = &v66;
              v59 = v31;
              *(_QWORD *)ExitCode = CreateRemoteThreadEx(
                                      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                      0,
                                      0,
                                      MemoryManager::SaveVtlProtectionThread,
                                      v31,
                                      0,
                                      (LPPROC_THREAD_ATTRIBUTE_LIST)v72,
                                      0);
              std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::emplace_back<void *>(
                &v63,
                ExitCode);
              if ( (unsigned __int64)(*(_QWORD *)(*((_QWORD *)&v63 + 1) - 8LL) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0x18C1,
                  (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
                  v32);
              v4 |= 1u;
              v59 = 0;
              std::unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>::~unique_ptr<MemoryManager::SaveVtlProtectionThreadContext>(&v59);
            }
            LOBYTE(v53) = 0;
            DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v72);
            v33 = (__int64 **)v35[2];
            if ( *((_BYTE *)v33 + 25) )
            {
              for ( k = (__int64 *)v35[1]; !*((_BYTE *)k + 25) && v35 == (__int64 *)k[2]; k = (__int64 *)k[1] )
                v35 = k;
              v35 = k;
            }
            else
            {
              v35 = (__int64 *)v35[2];
              for ( m = *v33; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                v35 = m;
            }
          }
          MemoryManager::WaitForAllThreadsToExit(&v63);
          v39 = (HANDLE *)*((_QWORD *)&v63 + 1);
          v38 = (HANDLE *)v63;
        }
        catch ( ... )
        {
          v59 = 0;
          wil::AcquireSRWLockExclusive(&v59, &v66);
          v67 = 1;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v59);
          MemoryManager::WaitForAllThreadsToExit(&v63);
          throw;
        }
        while ( v38 != v39 )
        {
          ExitCode[0] = 0;
          if ( !GetExitCodeThread(*v38, ExitCode) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x18E3,
              (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
              v40);
          v37 = ExitCode[0];
          if ( (ExitCode[0] & 0x80000000) != 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18E4,
              (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
              (const char *)ExitCode[0],
              cbSize);
          ++v38;
        }
        v41 = *v69;
        while ( !*((_BYTE *)v41 + 25) )
        {
          LOBYTE(v37) = v58[0];
          std::_Sort_unchecked_MemoryBlockVtlProtectionChunk____lambda_aed391eee51fbb281f32e46a7fb4a9b9___(
            v41[5],
            v41[6],
            0xAAAAAAAAAAAAAAABuLL * ((v41[6] - v41[5]) >> 4),
            v37);
          v42 = v41[4];
          v43 = v41[7];
          v41[7] = 0;
          v44 = v41[6];
          v41[6] = 0;
          v45 = (_OWORD *)v41[5];
          v41[5] = 0;
          v52 = v45;
          v53 = v44;
          v54 = v43;
          MemoryBlock::SaveVtlProtections(v42, *((unsigned int *)this + 96), a2, &v52);
          v46 = (__int64 **)v41[2];
          if ( *((_BYTE *)v46 + 25) )
          {
            for ( n = (__int64 *)v41[1]; !*((_BYTE *)n + 25) && v41 == (__int64 *)n[2]; n = (__int64 *)n[1] )
              v41 = n;
            v41 = n;
          }
          else
          {
            v41 = (__int64 *)v41[2];
            for ( ii = *v46; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
              v41 = ii;
          }
        }
        if ( (_QWORD)v63 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v63,
            *((_QWORD *)&v63 + 1));
          std::_Deallocate<16>((void *)v63, (struct std::nothrow_t *)((v64 - v63) & 0xFFFFFFFFFFFFFFF8uLL));
          v63 = 0;
          v64 = 0;
        }
        RrwLockRelease(v13);
        MemoryManager::SaveVtlProtectionContext::~SaveVtlProtectionContext((MemoryManager::SaveVtlProtectionContext *)&v66);
        v49 = (*(__int64 (__fastcall **)(struct VmRepository *))(*(_QWORD *)a2 + 56LL))(a2);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1911,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v49,
            cbSize);
        ++*((_DWORD *)this + 96);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v56);
        Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v55);
      }
    }
  }
}

```

## disassembly

```asm
0x14009dba0  mov     [rsp+arg_10], rbx
0x14009dba5  mov     [rsp+arg_18], rsi
0x14009dbaa  push    rdi
0x14009dbab  push    r12
0x14009dbad  push    r13
0x14009dbaf  push    r14
0x14009dbb1  push    r15
0x14009dbb3  sub     rsp, 560h
0x14009dbba  mov     rax, cs:__security_cookie
0x14009dbc1  xor     rax, rsp
0x14009dbc4  mov     [rsp+588h+var_38], rax
0x14009dbcc  mov     r12, rdx
0x14009dbcf  mov     [rsp+588h+var_548], rdx
0x14009dbd4  mov     r14, rcx
0x14009dbd7  xor     edi, edi
0x14009dbd9  mov     r13d, edi
0x14009dbdc  mov     [rsp+588h+ReturnLength], edi
0x14009dbe3  cmp     dword ptr [rcx+90h], 700h
0x14009dbed  jb      loc_14009E440
0x14009dbf3  mov     [rsp+588h+var_4F0], edi
0x14009dbfa  mov     rcx, [rcx+20h]
0x14009dbfe  mov     rax, [rcx]
0x14009dc01  mov     rax, [rax+1C0h]
0x14009dc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dc0d  mov     r8, rax
0x14009dc10  mov     rcx, [rax]
0x14009dc13  mov     rax, [rcx+58h]
0x14009dc17  lea     rdx, [rsp+588h+var_4F0]
0x14009dc1f  mov     rcx, r8
0x14009dc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dc27  mov     rcx, [rsp+588h]; this
0x14009dc2f  test    eax, eax
0x14009dc31  jns     short loc_14009DC48
0x14009dc33  mov     r9d, eax; char *
0x14009dc36  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dc3d  mov     edx, 17F0h; void *
0x14009dc42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009dc48  mov     ecx, [rsp+588h+var_4F0]
0x14009dc4f  mov     eax, 1
0x14009dc54  shl     eax, cl
0x14009dc56  test    al, 1Ch
0x14009dc58  jnz     loc_14009E440
0x14009dc5e  cmp     [r14+180h], edi
0x14009dc65  jnz     short loc_14009DC77
0x14009dc67  mov     rcx, r14; this
0x14009dc6a  call    ?AreAnySecureVtlsEnabled@MemoryManager@@AEBA_NXZ; MemoryManager::AreAnySecureVtlsEnabled(void)
0x14009dc6f  test    al, al
0x14009dc71  jz      loc_14009E440
0x14009dc77  mov     [rsp+588h+var_508], dil
0x14009dc7f  lea     rdx, [rsp+588h+var_508]
0x14009dc87  mov     rcx, [r14+10h]
0x14009dc8b  call    cs:__imp_VidVsmQueryProtectionsDirty
0x14009dc92  nop     dword ptr [rax+rax+00h]
0x14009dc97  mov     rcx, [rsp+588h]; this
0x14009dc9f  test    eax, eax
0x14009dca1  jnz     short loc_14009DCB5
0x14009dca3  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dcaa  mov     edx, 1809h; void *
0x14009dcaf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009dcb5  cmp     [r14+180h], edi
0x14009dcbc  jz      short loc_14009DCCC
0x14009dcbe  cmp     [rsp+588h+var_508], dil
0x14009dcc6  jz      loc_14009E440
0x14009dccc  mov     ebx, 408h
0x14009dcd1  mov     r8d, ebx; Size
0x14009dcd4  xor     edx, edx; Val
0x14009dcd6  lea     rcx, [rsp+588h+SystemInformation]; void *
0x14009dcde  call    memset_0
0x14009dce3  mov     [rsp+588h+ReturnLength], edi
0x14009dcea  lea     r9, [rsp+588h+ReturnLength]; ReturnLength
0x14009dcf2  mov     r8d, ebx; SystemInformationLength
0x14009dcf5  lea     rdx, [rsp+588h+SystemInformation]; SystemInformation
0x14009dcfd  mov     ecx, 37h ; '7'; SystemInformationClass
0x14009dd02  call    cs:__imp_NtQuerySystemInformation
0x14009dd09  nop     dword ptr [rax+rax+00h]
0x14009dd0e  mov     rcx, [rsp+588h]; this
0x14009dd16  test    eax, eax
0x14009dd18  jns     short loc_14009DD2F
0x14009dd1a  mov     r9d, eax; char *
0x14009dd1d  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dd24  mov     edx, 1827h; void *
0x14009dd29  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14009dd2f  call    ?OpenShared@?$VmSingletonObject@VNumaPhysicalTopologyInfo@@UINumaPhysicalTopologyInfo@@@Vml@@SAPEAUINumaPhysicalTopologyInfo@@XZ; Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared(void)
0x14009dd34  mov     r15, rax
0x14009dd37  mov     [rsp+588h+var_528], rax
0x14009dd3c  mov     rcx, [r14+28h]
0x14009dd40  mov     rdx, [rcx]
0x14009dd43  mov     rax, [rdx+8]
0x14009dd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dd4c  mov     rdx, rax
0x14009dd4f  mov     rcx, [rax]
0x14009dd52  mov     rax, [rcx+58h]
0x14009dd56  mov     rcx, rdx
0x14009dd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dd5e  mov     [rsp+588h+Size], rax
0x14009dd66  xorps   xmm0, xmm0
0x14009dd69  movups  xmmword ptr [rsp+588h+var_520], xmm0
0x14009dd6e  mov     r8d, 1
0x14009dd74  mov     rdx, r12
0x14009dd77  lea     rcx, [rsp+588h+var_520]
0x14009dd7c  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14009dd81  nop
0x14009dd82  mov     r9d, dword ptr [rsp+588h+var_520+8]; char *
0x14009dd87  mov     rcx, [rsp+588h]; this
0x14009dd8f  test    r9d, r9d
0x14009dd92  jns     short loc_14009DDA6
0x14009dd94  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009dd9b  mov     edx, 1830h; void *
0x14009dda0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009dda6  xor     eax, eax
0x14009dda8  mov     [rsp+588h+var_4B8], rax
0x14009ddb0  mov     [rsp+588h+var_4B0], dil
0x14009ddb8  mov     [rsp+588h+var_4A8], rdi
0x14009ddc0  mov     [rsp+588h+var_4A0], rdi
0x14009ddc8  lea     ebx, [rax+40h]
0x14009ddcb  mov     ecx, ebx
0x14009ddcd  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14009ddd2  mov     [rax], rax
0x14009ddd5  mov     [rax+8], rax
0x14009ddd9  mov     [rax+10h], rax
0x14009dddd  mov     word ptr [rax+18h], 101h
0x14009dde3  mov     [rsp+588h+var_4A8], rax
0x14009ddeb  mov     [rsp+588h+var_498], rdi
0x14009ddf3  mov     [rsp+588h+var_490], rdi
0x14009ddfb  mov     ecx, ebx
0x14009ddfd  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14009de02  mov     [rax], rax
0x14009de05  mov     [rax+8], rax
0x14009de09  mov     [rax+10h], rax
0x14009de0d  mov     word ptr [rax+18h], 101h
0x14009de13  mov     [rsp+588h+var_498], rax
0x14009de1b  mov     rsi, [r14+0A0h]
0x14009de22  add     rsi, 18h
0x14009de26  or      edx, 0FFFFFFFFh
0x14009de29  mov     rcx, rsi
0x14009de2c  call    RrwLockAcquireShared
0x14009de31  test    eax, eax
0x14009de33  jnz     short loc_14009DE55
0x14009de35  mov     rcx, [rsp+588h]; this
0x14009de3d  mov     r9d, 102h; char *
0x14009de43  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14009de4a  mov     edx, 249h; void *
0x14009de4f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009de55  mov     [rsp+588h+var_510], rsi
0x14009de5a  mov     qword ptr [rsp+588h+ExitCode], rdi
0x14009de62  lea     rdx, [rsp+588h+ExitCode]
0x14009de6a  mov     rcx, [r14+0A0h]
0x14009de71  call    ?IteratorGetFirst@MemoryBlockContainer@@QEAAPEAVMemoryBlock@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMemoryBlock@@@std@@@std@@@std@@@Z; MemoryBlockContainer::IteratorGetFirst(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MemoryBlock *>>> &)
0x14009de76  mov     rdi, rax
0x14009de79  mov     [rsp+588h+var_500], rax
0x14009de81  test    rax, rax
0x14009de84  jz      loc_14009DF75
0x14009de8a  mov     rcx, rax
0x14009de8d  mov     rbx, qword ptr [rsp+588h+ExitCode]
0x14009de95  mov     r12, [rsp+588h+Size]
0x14009de9d  cmp     byte ptr [rdi], 0
0x14009dea0  jz      loc_14009DF4D
0x14009dea6  mov     [rsp+588h+Size], 0
0x14009deb2  mov     [rsp+588h+var_4C0], 0
0x14009debe  mov     rax, [r15]
0x14009dec1  movzx   edx, byte ptr [rcx+0B8h]
0x14009dec8  mov     r9b, 1
0x14009decb  lea     r8, [rsp+588h+Size]
0x14009ded3  mov     dl, [rdx+r12+118h]
0x14009dedb  mov     rcx, r15
0x14009dede  mov     rax, [rax+10h]
0x14009dee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dee7  mov     rcx, [r15]
0x14009deea  mov     dl, al
0x14009deec  mov     rax, [rcx+30h]
0x14009def0  mov     rcx, r15
0x14009def3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009def8  movzx   eax, al
0x14009defb  mov     word ptr [rsp+588h+ExitCode], ax
0x14009df03  lea     r8, [rsp+588h+ExitCode]
0x14009df0b  lea     rdx, [rsp+588h+var_540]
0x14009df10  lea     rcx, [rsp+588h+var_4A8]
0x14009df18  call    ??$_Try_emplace@AEBG$$V@?$map@GV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBGV?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBG@Z; std::map<ushort,std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>>::_Try_emplace<ushort const &,>(ushort const &)
0x14009df1d  mov     rcx, [rax]
0x14009df20  add     rcx, 28h ; '('
0x14009df24  mov     rdx, [rcx+8]
0x14009df28  cmp     rdx, [rcx+10h]
0x14009df2c  jz      short loc_14009DF40
0x14009df2e  mov     [rdx], rdi
0x14009df31  mov     qword ptr [rdx+8], 0
0x14009df39  add     qword ptr [rcx+8], 10h
0x14009df3e  jmp     short loc_14009DF4D
0x14009df40  lea     r8, [rsp+588h+var_500]
0x14009df48  call    ??$_Emplace_reallocate@AEAPEAVMemoryBlock@@@?$vector@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@V?$allocator@UMemoryBlockSaveVtlProtectionContext@MemoryManager@@@std@@@std@@AEAAPEAUMemoryBlockSaveVtlProtectionContext@MemoryManager@@QEAU23@AEAPEAVMemoryBlock@@@Z; std::vector<MemoryManager::MemoryBlockSaveVtlProtectionContext>::_Emplace_reallocate<MemoryBlock * &>(MemoryManager::MemoryBlockSaveVtlProtectionContext * const,MemoryBlock * &)
0x14009df4d  mov     rax, [r14+0A0h]
0x14009df54  cmp     rbx, [rax+8]
0x14009df58  jz      short loc_14009DF75
0x14009df5a  mov     rdi, [rbx]
0x14009df5d  add     rbx, 8
0x14009df61  mov     [rsp+588h+var_500], rdi
0x14009df69  mov     rcx, rdi
0x14009df6c  test    rdi, rdi
0x14009df6f  jnz     loc_14009DE9D
0x14009df75  xorps   xmm1, xmm1
0x14009df78  movdqu  [rsp+588h+var_4E8], xmm1
0x14009df81  xor     r15d, r15d
0x14009df84  mov     [rsp+588h+var_4D8], r15
0x14009df8c  mov     rbx, [rsp+588h+var_4A8]
0x14009df94  mov     rbx, [rbx]
0x14009df97  cmp     [rbx+19h], r15b
0x14009df9b  jnz     loc_14009E22A
0x14009dfa1  movzx   eax, word ptr [rbx+20h]
0x14009dfa5  add     rax, rax
0x14009dfa8  movups  xmm0, [rsp+rax*8+588h+var_440]
0x14009dfb0  movdqu  [rsp+588h+Value], xmm0
0x14009dfb9  xorps   xmm1, xmm1
0x14009dfbc  movups  [rsp+588h+var_478], xmm1
0x14009dfc4  movups  [rsp+588h+var_468], xmm1
0x14009dfcc  movups  [rsp+588h+var_458], xmm1
0x14009dfd4  mov     [rsp+588h+Size], 30h ; '0'
0x14009dfe0  lea     r9, [rsp+588h+Size]; lpSize
0x14009dfe8  xor     r8d, r8d; dwFlags
0x14009dfeb  lea     edx, [r8+1]; dwAttributeCount
0x14009dfef  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x14009dff7  call    cs:__imp_InitializeProcThreadAttributeList
0x14009dffe  nop     dword ptr [rax+rax+00h]
0x14009e003  mov     rcx, [rsp+588h]; this
0x14009e00b  test    eax, eax
0x14009e00d  jnz     short loc_14009E020
0x14009e00f  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009e016  mov     edx, 1877h; void *
0x14009e01b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e020  lea     rdi, [rsp+588h+var_478]
0x14009e028  mov     [rsp+588h+var_540], rdi
0x14009e02d  mov     byte ptr [rsp+588h+var_538], 1
0x14009e032  mov     [rsp+588h+lpReturnSize], r15; lpReturnSize
0x14009e037  mov     [rsp+588h+lpPreviousValue], r15; lpPreviousValue
0x14009e03c  mov     [rsp+588h+cbSize], 10h; cbSize
0x14009e045  lea     r9, [rsp+588h+Value]; lpValue
0x14009e04d  xor     edx, edx; dwFlags
0x14009e04f  mov     r8d, 30003h; Attribute
0x14009e055  lea     rcx, [rsp+588h+var_478]; lpAttributeList
0x14009e05d  call    cs:__imp_UpdateProcThreadAttribute
0x14009e064  nop     dword ptr [rax+rax+00h]
0x14009e069  mov     rcx, [rsp+588h]; this
0x14009e071  test    eax, eax
0x14009e073  jnz     short loc_14009E086
0x14009e075  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14009e07c  mov     edx, 1885h; void *
0x14009e081  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e086  mov     r12, r15
0x14009e089  mov     rcx, [rbx+28h]
0x14009e08d  jmp     short loc_14009E09A
0x14009e08f  mov     rax, [rcx]
0x14009e092  add     r12, [rax+78h]
0x14009e096  add     rcx, 10h
0x14009e09a  cmp     rcx, [rbx+30h]
0x14009e09e  jnz     short loc_14009E08F
0x14009e0a0  shr     r12, 16h
0x14009e0a4  mov     rcx, qword ptr [rsp+588h+Value]
0x14009e0ac  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x14009e0b3  nop     dword ptr [rax+rax+00h]
0x14009e0b8  mov     r15d, eax
0x14009e0bb  shr     r15, 1
0x14009e0be  cmp     r15, r12
0x14009e0c1  cmovnb  r15, r12
0x14009e0c5  cmp     r15, 8
0x14009e0c9  jbe     short loc_14009E0D3
0x14009e0cb  mov     r15d, 8
0x14009e0d1  jmp     short loc_14009E0DF
0x14009e0d3  cmp     r15, 1
0x14009e0d7  jnb     short loc_14009E0DF
0x14009e0d9  mov     r15d, 1
0x14009e0df  xor     r12d, r12d
0x14009e0e2  cmp     r12, r15
0x14009e0e5  jnb     loc_14009E1C4
0x14009e0eb  mov     ecx, 18h; Size
0x14009e0f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009e0f5  movzx   ecx, word ptr [rbx+20h]
0x14009e0f9  mov     [rax], cx
0x14009e0fc  mov     [rax+8], r14
0x14009e100  lea     rcx, [rsp+588h+var_4B8]
0x14009e108  mov     [rax+10h], rcx
0x14009e10c  mov     [rsp+588h+var_500], rax
0x14009e114  mov     [rsp+588h+lpThreadId], 0; lpThreadId
0x14009e11d  lea     rcx, [rsp+588h+var_478]
0x14009e125  mov     [rsp+588h+lpReturnSize], rcx; lpAttributeList
0x14009e12a  mov     dword ptr [rsp+588h+lpPreviousValue], 0; dwCreationFlags
0x14009e132  mov     [rsp+588h+cbSize], rax; lpParameter
0x14009e137  lea     r9, ?SaveVtlProtectionThread@MemoryManager@@CAKPEAX@Z; lpStartAddress
0x14009e13e  xor     r8d, r8d; dwStackSize
0x14009e141  xor     edx, edx; lpThreadAttributes
0x14009e143  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x14009e147  call    cs:__imp_CreateRemoteThreadEx
0x14009e14e  nop     dword ptr [rax+rax+00h]
0x14009e153  mov     qword ptr [rsp+588h+ExitCode], rax
0x14009e15b  lea     rdx, [rsp+588h+ExitCode]
0x14009e163  lea     rcx, [rsp+588h+var_4E8]
0x14009e16b  call    ??$emplace_back@PEAX@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAPEAX@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::emplace_back<void *>(void * &&)
0x14009e170  mov     rax, qword ptr [rsp+588h+var_4E8+8]
0x14009e178  mov     rcx, [rax-8]
0x14009e17c  dec     rcx
0x14009e17f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14009e183  ja      short loc_14009E1AA
0x14009e185  or      r13d, 1
  ... truncated ...
```
