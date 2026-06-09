# _lambda_1a7f1932cacecdc3f91b63d5a743a5d4_::operator()

- ea: `0x1800394d8`
- end: `0x180039a68`
- name: `_lambda_1a7f1932cacecdc3f91b63d5a743a5d4_::operator()`
- size: `1424`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x180096ad0`

## callees

- `0x180005e08`
- `0x180005f64`
- `0x180007878`
- `0x180011a6c`
- `0x1800222ac`
- `0x1800293c8`
- `0x1800394d8`
- `0x180039a70`
- `0x180039adc`
- `0x18003a2ec`
- `0x18003e74c`
- `0x18004186c`
- `0x180046e48`
- `0x180046e94`
- `0x18004a68c`
- `0x18004d010`
- `0x180061320`
- `0x18006144c`
- `0x1800619a8`
- `0x180062344`
- `0x180062350`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039654`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800396c7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800396c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800395fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800395fe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003971b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003971b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall lambda_1a7f1932cacecdc3f91b63d5a743a5d4_::operator()(__int64 a1, const WCHAR *a2)
{
  _QWORD *v4; // rdx
  HANDLE FileW; // rsi
  __int64 v6; // rbx
  _QWORD *v8; // rdx
  unsigned __int8 *v9; // rbx
  const unsigned __int8 *v10; // r8
  int v11; // r9d
  __int64 v12; // rsi
  __int64 v13; // r14
  unsigned __int64 v14; // r12
  unsigned __int64 i; // rsi
  const wchar_t *v16; // rax
  __int64 v17; // rsi
  _QWORD *v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-350h]
  __int64 v22; // [rsp+40h] [rbp-338h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-330h] BYREF
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-328h] BYREF
  __int128 v25; // [rsp+58h] [rbp-320h] BYREF
  __int64 v26; // [rsp+68h] [rbp-310h]
  char v27; // [rsp+70h] [rbp-308h]
  unsigned __int8 *v28; // [rsp+78h] [rbp-300h]
  _QWORD v29[3]; // [rsp+80h] [rbp-2F8h] BYREF
  void **pExceptionObject; // [rsp+98h] [rbp-2E0h] BYREF
  int v31; // [rsp+A0h] [rbp-2D8h]
  __int128 v32; // [rsp+A8h] [rbp-2D0h]
  int v33; // [rsp+B8h] [rbp-2C0h]
  int v34; // [rsp+C8h] [rbp-2B0h]
  __int128 v35; // [rsp+D0h] [rbp-2A8h]
  __int64 v36; // [rsp+E0h] [rbp-298h]
  char v37[24]; // [rsp+E8h] [rbp-290h] BYREF
  _QWORD v38[7]; // [rsp+100h] [rbp-278h] BYREF
  _QWORD *v39; // [rsp+138h] [rbp-240h]
  _BYTE v40[64]; // [rsp+140h] [rbp-238h] BYREF
  HANDLE v41; // [rsp+180h] [rbp-1F8h]
  _BYTE v42[64]; // [rsp+190h] [rbp-1E8h] BYREF
  __int64 v43; // [rsp+1D0h] [rbp-1A8h]
  _QWORD v44[7]; // [rsp+1E0h] [rbp-198h] BYREF
  _QWORD *v45; // [rsp+218h] [rbp-160h]
  unsigned __int16 v46[16]; // [rsp+220h] [rbp-158h] BYREF
  unsigned __int16 v47[128]; // [rsp+240h] [rbp-138h] BYREF

  v25 = 0;
  v26 = 0;
  v27 = 1;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v28 = (unsigned __int8 *)operator new(0x48u);
  v22 = UserDictionary::UserDictionary(v28, 1);
  *(_BYTE *)(*(_QWORD *)(v22 + 56) + 613LL) = 1;
  v44[0] = &std::_Func_impl_no_alloc<void (*)(UserDictionary *),void,UserDictionary *>::`vftable';
  v44[1] = FinishBulkAdd;
  v45 = v44;
  std::function<int (void *)>::function<int (void *)>(v42, v44);
  v43 = v22;
  if ( v45 )
  {
    v4 = v44;
    LOBYTE(v4) = v45 != v44;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v45 + 32LL))(v45, v4);
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = v22;
    v22 = 0;
    std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v42);
    std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(&v22);
    CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(&v25);
    return v6;
  }
  else
  {
    v38[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
    v38[1] = CloseHandle;
    v39 = v38;
    std::function<int (void *)>::function<int (void *)>(v40, v38);
    v41 = FileW;
    if ( v39 )
    {
      v8 = v38;
      LOBYTE(v8) = v39 != v38;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v39 + 32LL))(v39, v8);
      v39 = 0;
    }
    if ( !GetFileSizeEx(FileW, &FileSize) || FileSize.HighPart )
    {
      v19 = v22;
      v22 = 0;
      std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v40);
      std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v42);
      std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(&v22);
      CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(&v25);
      return v19;
    }
    else
    {
      v9 = (unsigned __int8 *)operator new[](saturated_mul((unsigned __int64)FileSize.LowPart >> 1, 2u));
      v28 = v9;
      if ( ReadFile(FileW, v9, FileSize.LowPart, &NumberOfBytesRead, 0) && NumberOfBytesRead == FileSize.LowPart )
      {
        XORCrypt::CryptBuffer(v9, FileSize.LowPart, v10, v11);
        Configuration::Config::Read(
          (Configuration::Config *)&v25,
          (const unsigned __int16 *)v9,
          (unsigned __int64)FileSize.LowPart >> 1);
        if ( *((_QWORD *)&v25 + 1) == 1 )
        {
          v13 = CArray<Speller::CLexEntry,CArrayAllocator_malloc>::ElementAt(&v25, 0);
          v14 = *(_QWORD *)(v13 + 40);
          for ( i = 0; i < v14; ++i )
          {
            if ( i >= *(_QWORD *)(v13 + 40) )
            {
              v31 = -2147024809;
              v32 = 0;
              pExceptionObject = &CNLException::`vftable';
              v33 = -2147024809;
              v34 = 0;
              v35 = 0;
              v36 = 0;
              throw (CNLException *)&pExceptionObject;
            }
            v16 = (const wchar_t *)CArray<unsigned short,CArrayAllocator_malloc>::ElementAt(
                                     *(_QWORD *)(v13 + 32) + 32LL + (i << 6),
                                     0);
            LODWORD(dwFlagsAndAttributes) = 16;
            if ( swscanf_s(v16, L"%s %s", v47, 128, v46, dwFlagsAndAttributes) != 2 )
              goto LABEL_22;
            UDRTrie::AddChange(*(UDRTrie **)(v22 + 56), v47, v46);
            *(_BYTE *)(v22 + 64) = 1;
          }
          v18 = **(_QWORD ***)(a1 + 8);
          v29[0] = &v22;
          v29[1] = *(_QWORD *)a1;
          std::for_each_std::_Tree_const_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____________lambda_74e809d93e81bbb0e34fe502fd9698dc___(
            v37,
            *v18,
            v18,
            v29);
          UDRTrie::operator delete(v9);
          std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v40);
          std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v42);
          v20 = v22;
          v22 = 0;
          std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(&v22);
          CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(&v25);
          return v20;
        }
        else
        {
          v12 = v22;
          v22 = 0;
          UDRTrie::operator delete(v9);
          if ( v41 )
            std::_Func_class<int,void *>::operator()(v40);
          std::_Func_class<void,UserDictionary *>::_Tidy(v40);
          std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v42);
          CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(&v25);
          return v12;
        }
      }
      else
      {
LABEL_22:
        v17 = v22;
        v22 = 0;
        UDRTrie::operator delete(v9);
        std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v40);
        std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v42);
        std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(&v22);
        CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(&v25);
        return v17;
      }
    }
  }
}

```

## disassembly

```asm
0x1800394d8  mov     [rsp+arg_0], rbx
0x1800394dd  mov     [rsp+arg_10], rsi
0x1800394e2  push    rdi
0x1800394e3  push    r12
0x1800394e5  push    r13
0x1800394e7  push    r14
0x1800394e9  push    r15
0x1800394eb  sub     rsp, 350h
0x1800394f2  mov     rax, cs:__security_cookie
0x1800394f9  xor     rax, rsp
0x1800394fc  mov     [rsp+378h+var_38], rax
0x180039504  mov     rsi, rdx
0x180039507  mov     r13, rcx
0x18003950a  xorps   xmm0, xmm0
0x18003950d  movdqu  [rsp+378h+var_320], xmm0
0x180039513  xor     edi, edi
0x180039515  mov     [rsp+378h+var_310], rdi
0x18003951a  lea     r14d, [rdi+1]
0x18003951e  mov     [rsp+378h+var_308], r14b
0x180039523  mov     qword ptr [rsp+378h+FileSize], rdi
0x180039528  mov     [rsp+378h+NumberOfBytesRead], edi
0x18003952c  lea     ecx, [rdi+48h]; Size
0x18003952f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039534  mov     [rsp+378h+var_300], rax
0x180039539  mov     edx, r14d
0x18003953c  mov     rcx, rax
0x18003953f  call    ??0UserDictionary@@QEAA@W4PROOFLEXTYPE@@K@Z; UserDictionary::UserDictionary(PROOFLEXTYPE,ulong)
0x180039544  nop
0x180039545  mov     [rsp+378h+var_338], rax
0x18003954a  mov     rax, [rsp+378h+var_338]
0x18003954f  mov     rcx, [rax+38h]
0x180039553  mov     [rcx+265h], r14b
0x18003955a  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAVUserDictionary@@@ZXPEAV1@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(UserDictionary *),void,UserDictionary *>::`vftable'
0x180039561  mov     [rsp+378h+var_198], rax
0x180039569  lea     rax, ?FinishBulkAdd@@YAXPEAVUserDictionary@@@Z; FinishBulkAdd(UserDictionary *)
0x180039570  mov     [rsp+378h+var_190], rax
0x180039578  lea     rax, [rsp+378h+var_198]
0x180039580  mov     [rsp+378h+var_160], rax
0x180039588  mov     rbx, [rsp+378h+var_338]
0x18003958d  lea     rdx, [rsp+378h+var_198]
0x180039595  lea     rcx, [rsp+378h+var_1E8]
0x18003959d  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x1800395a2  mov     [rsp+378h+var_1A8], rbx
0x1800395aa  mov     rcx, [rsp+378h+var_160]
0x1800395b2  test    rcx, rcx
0x1800395b5  jz      short loc_1800395D1
0x1800395b7  mov     rax, [rcx]
0x1800395ba  lea     rdx, [rsp+378h+var_198]
0x1800395c2  cmp     rcx, rdx
0x1800395c5  setnz   dl
0x1800395c8  mov     rax, [rax+20h]
0x1800395cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395d1  cmp     qword ptr [rsi+18h], 7
0x1800395d6  jbe     short loc_1800395DB
0x1800395d8  mov     rsi, [rsi]
0x1800395db  mov     [rsp+378h+hTemplateFile], rdi; hTemplateFile
0x1800395e0  mov     dword ptr [rsp+378h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800395e8  mov     [rsp+378h+dwCreationDisposition], 3; dwCreationDisposition
0x1800395f0  xor     r9d, r9d; lpSecurityAttributes
0x1800395f3  mov     r8d, r14d; dwShareMode
0x1800395f6  mov     edx, 80000000h; dwDesiredAccess
0x1800395fb  mov     rcx, rsi; lpFileName
0x1800395fe  call    cs:__imp_CreateFileW
0x180039604  mov     rsi, rax
0x180039607  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003960b  cmp     rax, rbx
0x18003960e  jnz     short loc_180039645
0x180039610  mov     rbx, [rsp+378h+var_338]
0x180039615  mov     [rsp+378h+var_338], rdi
0x18003961a  lea     rcx, [rsp+378h+var_1E8]
0x180039622  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x180039627  nop
0x180039628  lea     rcx, [rsp+378h+var_338]
0x18003962d  call    ??1?$unique_ptr@VUserDictionary@@U?$default_delete@VUserDictionary@@@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(void)
0x180039632  nop
0x180039633  lea     rcx, [rsp+378h+var_320]
0x180039638  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x18003963d  mov     rax, rbx
0x180039640  jmp     loc_180039A3B
0x180039645  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x18003964c  mov     [rsp+378h+var_278], rax
0x180039654  mov     rax, cs:__imp_CloseHandle
0x18003965b  mov     [rsp+378h+var_270], rax
0x180039663  lea     rax, [rsp+378h+var_278]
0x18003966b  mov     [rsp+378h+var_240], rax
0x180039673  lea     rdx, [rsp+378h+var_278]
0x18003967b  lea     rcx, [rsp+378h+var_238]
0x180039683  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x180039688  mov     [rsp+378h+var_1F8], rsi
0x180039690  mov     rcx, [rsp+378h+var_240]
0x180039698  test    rcx, rcx
0x18003969b  jz      short loc_1800396BF
0x18003969d  mov     rax, [rcx]
0x1800396a0  lea     rdx, [rsp+378h+var_278]
0x1800396a8  cmp     rcx, rdx
0x1800396ab  setnz   dl
0x1800396ae  mov     rax, [rax+20h]
0x1800396b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396b7  mov     [rsp+378h+var_240], rdi
0x1800396bf  lea     rdx, [rsp+378h+FileSize]; lpFileSize
0x1800396c4  mov     rcx, rsi; hFile
0x1800396c7  call    cs:__imp_GetFileSizeEx
0x1800396cd  test    eax, eax
0x1800396cf  jz      loc_1800399D7
0x1800396d5  cmp     dword ptr [rsp+378h+FileSize+4], edi
0x1800396d9  jnz     loc_1800399D7
0x1800396df  mov     ecx, dword ptr [rsp+378h+FileSize]
0x1800396e3  shr     rcx, 1
0x1800396e6  mov     r15d, 2
0x1800396ec  mov     eax, r15d
0x1800396ef  mul     rcx
0x1800396f2  cmovb   rax, rbx
0x1800396f6  mov     rcx, rax; unsigned __int64
0x1800396f9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800396fe  mov     rbx, rax
0x180039701  mov     [rsp+378h+var_300], rax
0x180039706  mov     qword ptr [rsp+378h+dwCreationDisposition], rdi; lpOverlapped
0x18003970b  lea     r9, [rsp+378h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180039710  mov     r8d, dword ptr [rsp+378h+FileSize]; nNumberOfBytesToRead
0x180039715  mov     rdx, rax; lpBuffer
0x180039718  mov     rcx, rsi; hFile
0x18003971b  call    cs:__imp_ReadFile
0x180039721  test    eax, eax
0x180039723  jz      loc_18003998B
0x180039729  mov     edx, dword ptr [rsp+378h+FileSize]; unsigned int
0x18003972d  cmp     [rsp+378h+NumberOfBytesRead], edx
0x180039731  jnz     loc_18003998B
0x180039737  mov     rcx, rbx; unsigned __int8 *
0x18003973a  call    ?CryptBuffer@XORCrypt@@SAXPEAEKPEBEH@Z; XORCrypt::CryptBuffer(uchar *,ulong,uchar const *,int)
0x18003973f  mov     r8d, dword ptr [rsp+378h+FileSize]
0x180039744  shr     r8, 1; unsigned __int64
0x180039747  mov     rdx, rbx; unsigned __int16 *
0x18003974a  lea     rcx, [rsp+378h+var_320]; this
0x18003974f  call    ?Read@Config@Configuration@@QEAAXPEBG_K@Z; Configuration::Config::Read(ushort const *,unsigned __int64)
0x180039754  cmp     qword ptr [rsp+378h+var_320+8], r14
0x180039759  jz      short loc_1800397D3
0x18003975b  mov     rsi, [rsp+378h+var_338]
0x180039760  mov     [rsp+378h+var_338], rdi
0x180039765  mov     edx, r15d
0x180039768  mov     rcx, rbx; void *
0x18003976b  call    ??3UDRTrie@@SAXPEAX@Z; UDRTrie::operator delete(void *)
0x180039770  nop
0x180039771  mov     rdx, [rsp+378h+var_1F8]
0x180039779  test    rdx, rdx
0x18003977c  jz      short loc_18003978B
0x18003977e  lea     rcx, [rsp+378h+var_238]
0x180039786  call    ??R?$_Func_class@HPEAX@std@@QEBAHPEAX@Z; std::_Func_class<int,void *>::operator()(void *)
0x18003978b  lea     rcx, [rsp+378h+var_238]
0x180039793  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180039798  nop
0x180039799  lea     rcx, [rsp+378h+var_1E8]
0x1800397a1  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x1800397a6  nop
0x1800397a7  mov     rcx, [rsp+378h+var_338]
0x1800397ac  test    rcx, rcx
0x1800397af  jz      short loc_1800397C1
0x1800397b1  mov     r8, [rcx]
0x1800397b4  mov     edx, r14d
0x1800397b7  mov     rax, [r8+18h]
0x1800397bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397c0  nop
0x1800397c1  lea     rcx, [rsp+378h+var_320]
0x1800397c6  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x1800397cb  mov     rax, rsi
0x1800397ce  jmp     loc_180039A3B
0x1800397d3  xor     edx, edx
0x1800397d5  lea     rcx, [rsp+378h+var_320]
0x1800397da  call    ?ElementAt@?$CArray@VCLexEntry@Speller@@VCArrayAllocator_malloc@@@@QEBAAEAVCLexEntry@Speller@@_J@Z; CArray<Speller::CLexEntry,CArrayAllocator_malloc>::ElementAt(__int64)
0x1800397df  mov     r14, rax
0x1800397e2  mov     r12, [rax+28h]
0x1800397e6  mov     rsi, rdi
0x1800397e9  cmp     rsi, r12
0x1800397ec  jnb     loc_180039922
0x1800397f2  cmp     rsi, [r14+28h]
0x1800397f6  jb      short loc_180039852
0x1800397f8  mov     ecx, 80070057h
0x1800397fd  mov     [rsp+378h+var_2D8], ecx
0x180039804  xorps   xmm0, xmm0
0x180039807  movdqu  [rsp+378h+var_2D0], xmm0
0x180039810  lea     rax, ??_7CNLException@@6B@; const CNLException::`vftable'
0x180039817  mov     [rsp+378h+pExceptionObject], rax
0x18003981f  mov     [rsp+378h+var_2C0], ecx
0x180039826  mov     [rsp+378h+var_2B0], edi
0x18003982d  movdqu  [rsp+378h+var_2A8], xmm0
0x180039836  mov     [rsp+378h+var_298], rdi
0x18003983e  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180039845  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x18003984d  call    _CxxThrowException_0
0x180039852  mov     rcx, rsi
0x180039855  shl     rcx, 6
0x180039859  mov     rax, [r14+20h]
0x18003985d  add     rax, 20h ; ' '
0x180039861  add     rcx, rax
0x180039864  xor     edx, edx
0x180039866  call    ?ElementAt@?$CArray@GVCArrayAllocator_malloc@@@@QEBAAEAG_J@Z; CArray<ushort,CArrayAllocator_malloc>::ElementAt(__int64)
0x18003986b  mov     dword ptr [rsp+378h+dwFlagsAndAttributes], 10h
0x180039873  lea     rcx, [rsp+378h+var_158]
0x18003987b  mov     qword ptr [rsp+378h+dwCreationDisposition], rcx
0x180039880  mov     r9d, 80h
0x180039886  lea     r8, [rsp+378h+var_138]
0x18003988e  lea     rdx, aSS_0; "%s %s"
0x180039895  mov     rcx, rax; Buffer
0x180039898  call    swscanf_s
0x18003989d  cmp     eax, r15d
0x1800398a0  jz      short loc_1800398F1
0x1800398a2  mov     rsi, [rsp+378h+var_338]
0x1800398a7  mov     [rsp+378h+var_338], rdi
0x1800398ac  mov     rdx, r15
0x1800398af  mov     rcx, rbx; void *
0x1800398b2  call    ??3UDRTrie@@SAXPEAX@Z; UDRTrie::operator delete(void *)
0x1800398b7  nop
0x1800398b8  lea     rcx, [rsp+378h+var_238]
0x1800398c0  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x1800398c5  nop
0x1800398c6  lea     rcx, [rsp+378h+var_1E8]
0x1800398ce  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x1800398d3  nop
0x1800398d4  lea     rcx, [rsp+378h+var_338]
0x1800398d9  call    ??1?$unique_ptr@VUserDictionary@@U?$default_delete@VUserDictionary@@@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(void)
0x1800398de  nop
0x1800398df  lea     rcx, [rsp+378h+var_320]
0x1800398e4  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x1800398e9  mov     rax, rsi
0x1800398ec  jmp     loc_180039A3B
0x1800398f1  mov     r15, [rsp+378h+var_338]
0x1800398f6  lea     r8, [rsp+378h+var_158]; unsigned __int16 *
0x1800398fe  lea     rdx, [rsp+378h+var_138]; unsigned __int16 *
0x180039906  mov     rcx, [r15+38h]; this
0x18003990a  call    ?AddChange@UDRTrie@@QEAAXPEBG0@Z; UDRTrie::AddChange(ushort const *,ushort const *)
0x18003990f  mov     byte ptr [r15+40h], 1
0x180039914  inc     rsi
0x180039917  mov     r15d, 2
0x18003991d  jmp     loc_1800397E9
0x180039922  mov     rdx, [r13+8]
0x180039926  mov     rdx, [rdx]
0x180039929  lea     rax, [rsp+378h+var_338]
0x18003992e  mov     [rsp+378h+var_2F8], rax
0x180039936  mov     rax, [r13+0]
0x18003993a  mov     [rsp+378h+var_2F0], rax
0x180039942  lea     r9, [rsp+378h+var_2F8]
0x18003994a  mov     r8, rdx
0x18003994d  mov     rdx, [rdx]
0x180039950  lea     rcx, [rsp+378h+var_290]
0x180039958  call    std__for_each_std___Tree_const_iterator_std___Tree_val_std___Tree_simple_types_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const__std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____________lambda_74e809d93e81bbb0e34fe502fd9698dc___
0x18003995d  nop
0x18003995e  mov     rdx, r15
0x180039961  mov     rcx, rbx; void *
0x180039964  call    ??3UDRTrie@@SAXPEAX@Z; UDRTrie::operator delete(void *)
0x180039969  nop
0x18003996a  lea     rcx, [rsp+378h+var_238]
0x180039972  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180039977  nop
0x180039978  lea     rcx, [rsp+378h+var_1E8]
0x180039980  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x180039985  nop
0x180039986  jmp     loc_180039A19
0x18003998b  mov     rsi, [rsp+378h+var_338]
0x180039990  mov     [rsp+378h+var_338], rdi
0x180039995  mov     rdx, r15
0x180039998  mov     rcx, rbx; void *
0x18003999b  call    ??3UDRTrie@@SAXPEAX@Z; UDRTrie::operator delete(void *)
0x1800399a0  nop
0x1800399a1  lea     rcx, [rsp+378h+var_238]
0x1800399a9  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x1800399ae  nop
0x1800399af  lea     rcx, [rsp+378h+var_1E8]
0x1800399b7  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x1800399bc  nop
0x1800399bd  lea     rcx, [rsp+378h+var_338]
0x1800399c2  call    ??1?$unique_ptr@VUserDictionary@@U?$default_delete@VUserDictionary@@@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(void)
0x1800399c7  nop
0x1800399c8  lea     rcx, [rsp+378h+var_320]
0x1800399cd  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x1800399d2  mov     rax, rsi
0x1800399d5  jmp     short loc_180039A3B
0x1800399d7  mov     rbx, [rsp+378h+var_338]
0x1800399dc  mov     [rsp+378h+var_338], rdi
0x1800399e1  lea     rcx, [rsp+378h+var_238]
0x1800399e9  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x1800399ee  nop
0x1800399ef  lea     rcx, [rsp+378h+var_1E8]
0x1800399f7  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x1800399fc  nop
0x1800399fd  lea     rcx, [rsp+378h+var_338]
0x180039a02  call    ??1?$unique_ptr@VUserDictionary@@U?$default_delete@VUserDictionary@@@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(void)
0x180039a07  nop
0x180039a08  lea     rcx, [rsp+378h+var_320]
0x180039a0d  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x180039a12  mov     rax, rbx
0x180039a15  jmp     short loc_180039A3B
0x180039a17  xor     edi, edi
0x180039a19  mov     rbx, [rsp+378h+var_338]
0x180039a1e  mov     [rsp+378h+var_338], rdi
0x180039a23  lea     rcx, [rsp+378h+var_338]
0x180039a28  call    ??1?$unique_ptr@VUserDictionary@@U?$default_delete@VUserDictionary@@@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary>::~unique_ptr<UserDictionary>(void)
0x180039a2d  nop
0x180039a2e  lea     rcx, [rsp+378h+var_320]
0x180039a33  call    ??1?$CArray@VConfigSection@Configuration@@VCArrayAllocator_malloc@@@@QEAA@XZ; CArray<Configuration::ConfigSection,CArrayAllocator_malloc>::~CArray<Configuration::ConfigSection,CArrayAllocator_malloc>(void)
0x180039a38  mov     rax, rbx
0x180039a3b  mov     rcx, [rsp+378h+var_38]
  ... truncated ...
```
