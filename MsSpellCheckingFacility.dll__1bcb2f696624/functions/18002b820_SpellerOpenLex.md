# SpellerOpenLex

- ea: `0x18002b820`
- end: `0x18002bdfc`
- name: `SpellerOpenLex`
- size: `1500`
- prototype: `__int64 __fastcall(struct Speller::CSpellChecker *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180092ad0`

## callees

- `0x180003560`
- `0x18001ee7c`
- `0x1800202e4`
- `0x18002b820`
- `0x18002be04`
- `0x180039a70`
- `0x180042c1c`
- `0x18004e3bc`
- `0x18004f720`
- `0x180050e08`
- `0x180061320`
- `0x18006144c`
- `0x180062344`
- `0x180095954`
- `0x180095a24`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bad8`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b9dd`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b9dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b9ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b9ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall SpellerOpenLex(struct Speller::CSpellChecker *a1, _QWORD *a2, __int64 a3)
{
  const struct INLTopLexicon *v6; // rdx
  CBasicTopLexicon *v7; // r14
  CBasicTopLexicon *v8; // rbx
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rcx
  HANDLE FileW; // rax
  void *v13; // rbx
  __int64 v14; // r8
  DWORD v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  struct ILspBinary *v19; // r14
  __int64 v20; // rcx
  CBasicTopLexicon *Lexicon; // r12
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  CBasicTopLexicon *v27; // rax
  CBasicTopLexicon *v28; // rsi
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 Module; // [rsp+40h] [rbp-118h] BYREF
  CBasicTopLexicon *v34; // [rsp+48h] [rbp-110h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-108h] BYREF
  int pExceptionObject; // [rsp+58h] [rbp-100h] BYREF
  int v37; // [rsp+5Ch] [rbp-FCh] BYREF
  int v38; // [rsp+60h] [rbp-F8h] BYREF
  ulong v39; // [rsp+64h] [rbp-F4h] BYREF
  ulong v40; // [rsp+68h] [rbp-F0h] BYREF
  ulong v41; // [rsp+6Ch] [rbp-ECh] BYREF
  ulong v42; // [rsp+70h] [rbp-E8h] BYREF
  ulong v43; // [rsp+74h] [rbp-E4h] BYREF
  ulong v44; // [rsp+78h] [rbp-E0h] BYREF
  int v45; // [rsp+7Ch] [rbp-DCh] BYREF
  int v46; // [rsp+80h] [rbp-D8h] BYREF
  int v47; // [rsp+84h] [rbp-D4h] BYREF
  int v48; // [rsp+88h] [rbp-D0h] BYREF
  CBasicTopLexicon *v49; // [rsp+90h] [rbp-C8h]
  char *v50[4]; // [rsp+A0h] [rbp-B8h] BYREF
  _QWORD v51[7]; // [rsp+C0h] [rbp-98h] BYREF
  _QWORD *v52; // [rsp+F8h] [rbp-60h]
  CNLException *v53; // [rsp+100h] [rbp-58h] BYREF

  v34 = (CBasicTopLexicon *)operator new(0xE8u);
  v7 = CBasicTopLexicon::CBasicTopLexicon(v34, v6);
  v8 = v7;
  v49 = v7;
  if ( !a1 )
  {
    pExceptionObject = 8454146;
    throw (long *)&pExceptionObject;
  }
  if ( !a3 || !a2 )
  {
    v48 = 2;
    CxxThrowException_0(&v48, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
  }
  v9 = *((_DWORD *)a2 + 3);
  if ( v9 == 4 )
  {
    if ( !*a2 || !*(_WORD *)*a2 )
    {
      v45 = 2;
      CxxThrowException_0(&v45, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
    }
    if ( *((_DWORD *)a2 + 2) )
    {
      v37 = 5;
      CxxThrowException_0(&v37, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
    }
    Module = 0;
    if ( *((__int64 *)a1 + 152) > 0 )
    {
      v38 = 5;
      CxxThrowException_0(&v38, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
    }
    v10 = *((unsigned __int16 *)a2 + 8);
    *((_DWORD *)a1 + 126) = v10;
    *((_DWORD *)a1 + 485) = v10;
    *((_BYTE *)a1 + 1025) = 1;
    std::wstring::wstring(v50, (_WORD *)*a2);
    Module = ResourceLoader6::ResourceCache::GetModule(v11, (__int64)v50);
    std::wstring::_Tidy_deallocate(v50);
    if ( Module )
    {
      try
      {
        v34 = (CBasicTopLexicon *)operator new(0x58u);
        v19 = (struct ILspBinary *)CLspBinary::CLspBinary(v34);
        FileSize.QuadPart = (LONGLONG)v19;
        if ( !(*(unsigned int (__fastcall **)(struct ILspBinary *, __int64, _QWORD))(*(_QWORD *)v19 + 24LL))(
                v19,
                Module,
                0) )
        {
          Module = 0;
          v44 = 8781827;
          throw &v44;
        }
        Speller::CSpellerDataStorage::SetSpellerBinary((struct Speller::CSpellChecker *)((char *)a1 + 488), v19);
        if ( v19 )
          (*(void (__fastcall **)(struct ILspBinary *))(*(_QWORD *)v19 + 16LL))(v19);
        FileSize.QuadPart = 0;
        v51[0] = &std::_Func_impl_no_alloc<_lambda_b82002623363505e2d9f80013be3c037_,INLTopLexicon *,HINSTANCE__ * const &>::`vftable';
        v52 = v51;
        Lexicon = (CBasicTopLexicon *)LexiconCache<HINSTANCE__ *,INLTopLexicon>::GetLexicon(v20, &Module, v51);
        v34 = Lexicon;
        if ( v52 )
        {
          v22 = v51;
          LOBYTE(v22) = v52 != v51;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v52 + 32LL))(v52, v22);
        }
        v23 = *((_QWORD *)a1 + 152);
        v24 = *((_QWORD *)a1 + 153);
        if ( v23 >= v24 )
        {
          v25 = v23 + 1;
          if ( v23 < 8 )
            v23 = 8;
          if ( v25 < v24 + v23 )
            v25 = v24 + v23;
          if ( v25 > v24 )
          {
            try
            {
              CArray<unsigned short const *,CArrayAllocator_malloc>::ReallocWorker((char *)a1 + 1208);
            }
            catch ( _com_error )
            {
              LexiconCache<HINSTANCE__ *,INLTopLexicon>::ReleaseLexicon(v26, v34);
              throw;
            }
          }
        }
        *(_QWORD *)(*((_QWORD *)a1 + 151) + 8LL * (*((_QWORD *)a1 + 152))++) = Lexicon;
        *(_QWORD *)(a3 + 8) = Lexicon;
        LoadAuxiliaryLexicons(a1, (const unsigned __int16 *)*a2);
      }
      catch ( _com_error )
      {
        Module = 0;
        throw;
      }
    }
    else
    {
      if ( !(*(unsigned __int8 (__fastcall **)(CBasicTopLexicon *, _QWORD))(*(_QWORD *)v7 + 264LL))(v7, *a2) )
      {
        v43 = 9568259;
        throw &v43;
      }
      FileSize.QuadPart = 0;
      FileW = CreateFileW((LPCWSTR)*a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v13 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v39 = 9568259;
        throw &v39;
      }
      if ( !GetFileSizeEx(FileW, &FileSize) || FileSize.HighPart )
      {
        CloseHandle(v13);
        v42 = 9568259;
        throw &v42;
      }
      CloseHandle(v13);
      v14 = *((_QWORD *)v7 + 18);
      v15 = *(unsigned __int8 *)(FileSize.LowPart - 4 + v14)
          | ((*(unsigned __int8 *)(FileSize.LowPart - 3 + v14)
            | ((*(unsigned __int8 *)(FileSize.LowPart - 2 + v14)
              | (*(unsigned __int8 *)(FileSize.LowPart - 1 + v14) << 8)) << 8)) << 8);
      if ( v15 >= FileSize.LowPart )
      {
        v40 = 9568259;
        throw &v40;
      }
      try
      {
        Speller::CSpellerDataStorage::SetSpellerBinary(
          (struct Speller::CSpellChecker *)((char *)a1 + 488),
          (const unsigned __int8 *)(v14
                                  + (*(unsigned __int8 *)(FileSize.LowPart - 4 + v14)
                                   | ((*(unsigned __int8 *)(FileSize.LowPart - 3 + v14)
                                     | ((*(unsigned __int8 *)(FileSize.LowPart - 2 + v14)
                                       | (*(unsigned __int8 *)(FileSize.LowPart - 1 + v14) << 8)) << 8)) << 8))),
          (int)(FileSize.LowPart - v15 - 4));
      }
      catch ( CNLException *v53 )
      {
        v41 = 9568259;
        throw &v41;
      }
      *(_QWORD *)(a3 + 8) = v7;
      v8 = 0;
      v49 = 0;
      v16 = *((_QWORD *)a1 + 152);
      v17 = *((_QWORD *)a1 + 153);
      if ( v16 >= v17 )
      {
        v18 = v16 + 1;
        if ( v16 < 8 )
          v16 = 8;
        if ( v18 < v17 + v16 )
          v18 = v17 + v16;
        if ( v18 > v17 )
          CArray<unsigned short const *,CArrayAllocator_malloc>::ReallocWorker((char *)a1 + 1208);
      }
      *(_QWORD *)(*((_QWORD *)a1 + 151) + 8LL * (*((_QWORD *)a1 + 152))++) = v7;
    }
    *(_WORD *)(a3 + 28) = *((_WORD *)a1 + 970);
    *(_DWORD *)(a3 + 24) = 1;
    if ( *(_QWORD *)a3 && *(_DWORD *)(a3 + 16) )
      **(_WORD **)a3 = 0;
  }
  else
  {
    if ( (unsigned int)(v9 - 2) > 1 )
    {
      v46 = 2;
      CxxThrowException_0(&v46, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
    }
    v34 = (CBasicTopLexicon *)operator new(0x48u);
    v27 = (CBasicTopLexicon *)UserDictionary::UserDictionary(v34, *((unsigned int *)a2 + 3));
    v28 = v27;
    v34 = v27;
    if ( *(_DWORD *)(a3 + 16) )
    {
      if ( !*(_QWORD *)a3 )
      {
        v47 = 2;
        CxxThrowException_0(&v47, (_ThrowInfo *)&TI1_AW4_unnamed_enum_ptecNoErrors___);
      }
      **(_WORD **)a3 = 0;
    }
    *(_QWORD *)(a3 + 8) = v27;
    *(_DWORD *)(a3 + 20) = 0;
    *(_DWORD *)(a3 + 24) = *(unsigned __int8 *)(*((_QWORD *)v27 + 7) + 58LL);
    *(_WORD *)(a3 + 28) = (*(__int64 (__fastcall **)(CBasicTopLexicon *))(*(_QWORD *)v27 + 40LL))(v27);
    v34 = 0;
    v29 = *((_QWORD *)a1 + 156);
    v30 = *((_QWORD *)a1 + 157);
    if ( v29 >= v30 )
    {
      v31 = v29 + 1;
      if ( v29 < 8 )
        v29 = 8;
      if ( v31 < v30 + v29 )
        v31 = v30 + v29;
      if ( v31 > v30 )
        CArray<unsigned short const *,CArrayAllocator_malloc>::ReallocWorker((char *)a1 + 1240);
    }
    *(_QWORD *)(*((_QWORD *)a1 + 155) + 8LL * (*((_QWORD *)a1 + 156))++) = v28;
  }
  if ( v8 )
    (*(void (__fastcall **)(CBasicTopLexicon *, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
  return 0;
}

```

## disassembly

```asm
0x18002b820  push    rbx
0x18002b822  push    rsi
0x18002b823  push    rdi
0x18002b824  push    r12
0x18002b826  push    r13
0x18002b828  push    r14
0x18002b82a  push    r15
0x18002b82c  sub     rsp, 120h
0x18002b833  mov     rax, cs:__security_cookie
0x18002b83a  xor     rax, rsp
0x18002b83d  mov     [rsp+158h+var_48], rax
0x18002b845  mov     rdi, r8
0x18002b848  mov     rsi, rdx
0x18002b84b  mov     r15, rcx
0x18002b84e  mov     ecx, 0E8h; Size
0x18002b853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b858  mov     [rsp+158h+var_110], rax
0x18002b85d  mov     rcx, rax; this
0x18002b860  call    ??0CBasicTopLexicon@@QEAA@PEBVINLTopLexicon@@@Z; CBasicTopLexicon::CBasicTopLexicon(INLTopLexicon const *)
0x18002b865  mov     r14, rax
0x18002b868  mov     rbx, rax
0x18002b86b  mov     [rsp+158h+var_C8], rax
0x18002b873  xor     r12d, r12d
0x18002b876  test    r15, r15
0x18002b879  jnz     short loc_18002B894
0x18002b87b  mov     [rsp+158h+pExceptionObject], 810002h
0x18002b883  lea     rdx, _TI1J; pThrowInfo
0x18002b88a  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18002b88f  call    _CxxThrowException_0
0x18002b894  test    rdi, rdi
0x18002b897  jz      loc_18002BDA5
0x18002b89d  test    rsi, rsi
0x18002b8a0  jz      loc_18002BDA5
0x18002b8a6  mov     eax, [rsi+0Ch]
0x18002b8a9  cmp     eax, 4
0x18002b8ac  jnz     loc_18002BC98
0x18002b8b2  mov     rax, [rsi]
0x18002b8b5  test    rax, rax
0x18002b8b8  jz      loc_18002BC7E
0x18002b8be  cmp     [rax], r12w
0x18002b8c2  jz      loc_18002BC7E
0x18002b8c8  cmp     [rsi+8], r12d
0x18002b8cc  jz      short loc_18002B8E7
0x18002b8ce  mov     [rsp+158h+var_FC], 5
0x18002b8d6  lea     rdx, _TI1?AW4_unnamed_enum_ptecNoErrors_@@; pThrowInfo
0x18002b8dd  lea     rcx, [rsp+158h+var_FC]; pExceptionObject
0x18002b8e2  call    _CxxThrowException_0
0x18002b8e7  mov     [rsp+158h+var_118], r12
0x18002b8ec  cmp     [r15+4C0h], r12
0x18002b8f3  jle     short loc_18002B90E
0x18002b8f5  mov     [rsp+158h+var_F8], 5
0x18002b8fd  lea     rdx, _TI1?AW4_unnamed_enum_ptecNoErrors_@@; pThrowInfo
0x18002b904  lea     rcx, [rsp+158h+var_F8]; pExceptionObject
0x18002b909  call    _CxxThrowException_0
0x18002b90e  lea     r13, [r15+1E8h]
0x18002b915  movzx   eax, word ptr [rsi+10h]
0x18002b919  mov     [r13+10h], eax
0x18002b91d  mov     [r13+5ACh], eax
0x18002b924  mov     byte ptr [r13+219h], 1
0x18002b92c  mov     rdx, [rsi]
0x18002b92f  lea     rcx, [rsp+158h+var_B8]
0x18002b937  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b93c  nop
0x18002b93d  lea     rdx, [rsp+158h+var_B8]
0x18002b945  call    ?GetModule@ResourceCache@ResourceLoader6@@QEAAPEAUHINSTANCE__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; ResourceLoader6::ResourceCache::GetModule(std::wstring const &,bool)
0x18002b94a  mov     [rsp+158h+var_118], rax
0x18002b94f  lea     rcx, [rsp+158h+var_B8]
0x18002b957  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b95c  cmp     [rsp+158h+var_118], r12
0x18002b961  jnz     loc_18002BB11
0x18002b967  mov     rax, [r14]
0x18002b96a  mov     rdx, [rsi]
0x18002b96d  mov     rcx, r14
0x18002b970  mov     rax, [rax+108h]
0x18002b977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b97c  test    al, al
0x18002b97e  jz      loc_18002BAF7
0x18002b984  mov     qword ptr [rsp+158h+FileSize], r12
0x18002b989  mov     [rsp+158h+hTemplateFile], r12; hTemplateFile
0x18002b98e  mov     [rsp+158h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b996  mov     [rsp+158h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b99e  xor     r9d, r9d; lpSecurityAttributes
0x18002b9a1  mov     edx, 80000000h; dwDesiredAccess
0x18002b9a6  lea     r8d, [r9+1]; dwShareMode
0x18002b9aa  mov     rcx, [rsi]; lpFileName
0x18002b9ad  call    cs:__imp_CreateFileW
0x18002b9b3  mov     rbx, rax
0x18002b9b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b9ba  jnz     short loc_18002B9D5
0x18002b9bc  mov     [rsp+158h+var_F4], 920003h
0x18002b9c4  lea     rdx, _TI1K; pThrowInfo
0x18002b9cb  lea     rcx, [rsp+158h+var_F4]; pExceptionObject
0x18002b9d0  call    _CxxThrowException_0
0x18002b9d5  lea     rdx, [rsp+158h+FileSize]; lpFileSize
0x18002b9da  mov     rcx, rbx; hFile
0x18002b9dd  call    cs:__imp_GetFileSizeEx
0x18002b9e3  test    eax, eax
0x18002b9e5  jz      loc_18002BAD5
0x18002b9eb  cmp     dword ptr [rsp+158h+FileSize+4], r12d
0x18002b9f0  jnz     loc_18002BAD5
0x18002b9f6  mov     rcx, rbx; hObject
0x18002b9f9  call    cs:__imp_CloseHandle
0x18002b9ff  mov     r8, [r14+90h]
0x18002ba06  mov     r9d, dword ptr [rsp+158h+FileSize]
0x18002ba0b  lea     eax, [r9-1]
0x18002ba0f  movzx   edx, byte ptr [rax+r8]
0x18002ba14  shl     edx, 8
0x18002ba17  lea     eax, [r9-2]
0x18002ba1b  movzx   eax, byte ptr [rax+r8]
0x18002ba20  or      edx, eax
0x18002ba22  shl     edx, 8
0x18002ba25  lea     eax, [r9-3]
0x18002ba29  movzx   eax, byte ptr [rax+r8]
0x18002ba2e  or      edx, eax
0x18002ba30  shl     edx, 8
0x18002ba33  lea     eax, [r9-4]
0x18002ba37  movzx   eax, byte ptr [rax+r8]
0x18002ba3c  or      edx, eax
0x18002ba3e  mov     eax, edx
0x18002ba40  add     rdx, r8; Src
0x18002ba43  mov     ecx, r9d
0x18002ba46  sub     ecx, eax
0x18002ba48  sub     ecx, 4
0x18002ba4b  cmp     eax, r9d
0x18002ba4e  jb      short loc_18002BA6A
0x18002ba50  mov     [rsp+158h+var_F0], 920003h
0x18002ba58  lea     rdx, _TI1K; pThrowInfo
0x18002ba5f  lea     rcx, [rsp+158h+var_F0]; pExceptionObject
0x18002ba64  call    _CxxThrowException_0
0x18002ba6a  movsxd  r8, ecx; unsigned __int64
0x18002ba6d  mov     rcx, r13; this
0x18002ba70  call    ?SetSpellerBinary@CSpellerDataStorage@Speller@@QEAAXPEBE_K@Z; Speller::CSpellerDataStorage::SetSpellerBinary(uchar const *,unsigned __int64)
0x18002ba75  nop
0x18002ba76  mov     [rdi+8], r14
0x18002ba7a  lea     rsi, [r15+4B8h]
0x18002ba81  mov     rbx, r12
0x18002ba84  mov     [rsp+158h+var_C8], rbx
0x18002ba8c  mov     rcx, [rsi+8]
0x18002ba90  mov     r8, [rsi+10h]
0x18002ba94  cmp     rcx, r8
0x18002ba97  jl      short loc_18002BAC1
0x18002ba99  lea     rdx, [rcx+1]
0x18002ba9d  mov     eax, 8
0x18002baa2  cmp     rcx, rax
0x18002baa5  cmovl   rcx, rax
0x18002baa9  lea     rax, [r8+rcx]
0x18002baad  cmp     rdx, rax
0x18002bab0  cmovl   rdx, rax
0x18002bab4  cmp     rdx, r8
0x18002bab7  jle     short loc_18002BAC1
0x18002bab9  mov     rcx, rsi
0x18002babc  call    ?ReallocWorker@?$CArray@PEBGVCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<ushort const *,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x18002bac1  mov     rcx, [rsi+8]
0x18002bac5  mov     rax, [rsi]
0x18002bac8  mov     [rax+rcx*8], r14
0x18002bacc  inc     qword ptr [rsi+8]
0x18002bad0  jmp     loc_18002BC4C
0x18002bad5  mov     rcx, rbx; hObject
0x18002bad8  call    cs:__imp_CloseHandle
0x18002bade  mov     [rsp+158h+var_E8], 920003h
0x18002bae6  lea     rdx, _TI1K; pThrowInfo
0x18002baed  lea     rcx, [rsp+158h+var_E8]; pExceptionObject
0x18002baf2  call    _CxxThrowException_0
0x18002baf7  mov     [rsp+158h+var_E4], 920003h
0x18002baff  lea     rdx, _TI1K; pThrowInfo
0x18002bb06  lea     rcx, [rsp+158h+var_E4]; pExceptionObject
0x18002bb0b  call    _CxxThrowException_0
0x18002bb11  mov     ecx, 58h ; 'X'; Size
0x18002bb16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bb1b  mov     [rsp+158h+var_110], rax
0x18002bb20  mov     rcx, rax
0x18002bb23  call    ??0CLspBinary@@QEAA@W4ELspBinaryType@@G@Z; CLspBinary::CLspBinary(ELspBinaryType,ushort)
0x18002bb28  mov     r14, rax
0x18002bb2b  mov     qword ptr [rsp+158h+FileSize], rax
0x18002bb30  mov     rax, [rax]
0x18002bb33  xor     r8d, r8d
0x18002bb36  mov     rdx, [rsp+158h+var_118]
0x18002bb3b  mov     rcx, r14
0x18002bb3e  mov     rax, [rax+18h]
0x18002bb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb47  test    eax, eax
0x18002bb49  jnz     short loc_18002BB69
0x18002bb4b  mov     [rsp+158h+var_118], r12
0x18002bb50  mov     [rsp+158h+var_E0], 860003h
0x18002bb58  lea     rdx, _TI1K; pThrowInfo
0x18002bb5f  lea     rcx, [rsp+158h+var_E0]; pExceptionObject
0x18002bb64  call    _CxxThrowException_0
0x18002bb69  mov     rdx, r14; struct ILspBinary *
0x18002bb6c  mov     rcx, r13; this
0x18002bb6f  call    ?SetSpellerBinary@CSpellerDataStorage@Speller@@QEAAXPEAUILspBinary@@@Z; Speller::CSpellerDataStorage::SetSpellerBinary(ILspBinary *)
0x18002bb74  test    r14, r14
0x18002bb77  jz      short loc_18002BB88
0x18002bb79  mov     rax, [r14]
0x18002bb7c  mov     rcx, r14
0x18002bb7f  mov     rax, [rax+10h]
0x18002bb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb88  mov     qword ptr [rsp+158h+FileSize], r12
0x18002bb8d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_b82002623363505e2d9f80013be3c037_@@PEAVINLTopLexicon@@AEBQEAUHINSTANCE__@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_b82002623363505e2d9f80013be3c037_,INLTopLexicon *,HINSTANCE__ * const &>::`vftable'
0x18002bb94  mov     [rsp+158h+var_98], rax
0x18002bb9c  lea     rax, [rsp+158h+var_98]
0x18002bba4  mov     [rsp+158h+var_60], rax
0x18002bbac  lea     r8, [rsp+158h+var_98]
0x18002bbb4  lea     rdx, [rsp+158h+var_118]
0x18002bbb9  call    ?GetLexicon@?$LexiconCache@PEAUHINSTANCE__@@VINLTopLexicon@@@@QEAAPEAVINLTopLexicon@@AEBQEAUHINSTANCE__@@AEBV?$function@$$A6APEAVINLTopLexicon@@AEBQEAUHINSTANCE__@@@Z@std@@@Z; LexiconCache<HINSTANCE__ *,INLTopLexicon>::GetLexicon(HINSTANCE__ * const &,std::function<INLTopLexicon * (HINSTANCE__ * const &)> const &)
0x18002bbbe  mov     r12, rax
0x18002bbc1  mov     [rsp+158h+var_110], rax
0x18002bbc6  mov     rcx, [rsp+158h+var_60]
0x18002bbce  test    rcx, rcx
0x18002bbd1  jz      short loc_18002BBEE
0x18002bbd3  mov     rax, [rcx]
0x18002bbd6  lea     rdx, [rsp+158h+var_98]
0x18002bbde  cmp     rcx, rdx
0x18002bbe1  setnz   dl
0x18002bbe4  mov     rax, [rax+20h]
0x18002bbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbed  nop
0x18002bbee  lea     r14, [r15+4B8h]
0x18002bbf5  mov     rcx, [r14+8]
0x18002bbf9  mov     r8, [r14+10h]
0x18002bbfd  cmp     rcx, r8
0x18002bc00  jl      short loc_18002BC2A
0x18002bc02  lea     rdx, [rcx+1]
0x18002bc06  mov     eax, 8
0x18002bc0b  cmp     rcx, rax
0x18002bc0e  cmovl   rcx, rax
0x18002bc12  lea     rax, [r8+rcx]
0x18002bc16  cmp     rdx, rax
0x18002bc19  cmovl   rdx, rax
0x18002bc1d  cmp     rdx, r8
0x18002bc20  jle     short loc_18002BC2A
0x18002bc22  mov     rcx, r14
0x18002bc25  call    ?ReallocWorker@?$CArray@PEBGVCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<ushort const *,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x18002bc2a  mov     rcx, [r14+8]
0x18002bc2e  mov     rax, [r14]
0x18002bc31  mov     [rax+rcx*8], r12
0x18002bc35  inc     qword ptr [r14+8]
0x18002bc39  mov     [rdi+8], r12
0x18002bc3d  mov     rdx, [rsi]; unsigned __int16 *
0x18002bc40  mov     rcx, r15; struct Speller::CSpellChecker *
0x18002bc43  call    ?LoadAuxiliaryLexicons@@YAXPEAVCSpellChecker@Speller@@PEBG@Z; LoadAuxiliaryLexicons(Speller::CSpellChecker *,ushort const *)
0x18002bc48  nop
0x18002bc49  xor     r12d, r12d
0x18002bc4c  movzx   eax, word ptr [r15+794h]
0x18002bc54  mov     [rdi+1Ch], ax
0x18002bc58  mov     dword ptr [rdi+18h], 1
0x18002bc5f  mov     rcx, [rdi]
0x18002bc62  test    rcx, rcx
0x18002bc65  jz      loc_18002BD88
0x18002bc6b  cmp     [rdi+10h], r12d
0x18002bc6f  jbe     loc_18002BD88
0x18002bc75  mov     [rcx], r12w
0x18002bc79  jmp     loc_18002BD88
0x18002bc7e  mov     eax, 2
0x18002bc83  mov     [rsp+158h+var_DC], eax
0x18002bc87  lea     rdx, _TI1?AW4_unnamed_enum_ptecNoErrors_@@; pThrowInfo
0x18002bc8e  lea     rcx, [rsp+158h+var_DC]; pExceptionObject
0x18002bc93  call    _CxxThrowException_0
0x18002bc98  add     eax, 0FFFFFFFEh
0x18002bc9b  cmp     eax, 1
0x18002bc9e  jbe     short loc_18002BCC0
0x18002bca0  mov     eax, 2
0x18002bca5  mov     [rsp+158h+var_D8], eax
0x18002bcac  lea     rdx, _TI1?AW4_unnamed_enum_ptecNoErrors_@@; pThrowInfo
0x18002bcb3  lea     rcx, [rsp+158h+var_D8]; pExceptionObject
0x18002bcbb  call    _CxxThrowException_0
0x18002bcc0  mov     ecx, 48h ; 'H'; Size
0x18002bcc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bcca  mov     [rsp+158h+var_110], rax
0x18002bccf  mov     edx, [rsi+0Ch]
0x18002bcd2  mov     rcx, rax
0x18002bcd5  call    ??0UserDictionary@@QEAA@W4PROOFLEXTYPE@@K@Z; UserDictionary::UserDictionary(PROOFLEXTYPE,ulong)
0x18002bcda  mov     rsi, rax
0x18002bcdd  mov     [rsp+158h+var_110], rax
0x18002bce2  cmp     [rdi+10h], r12d
0x18002bce6  jbe     short loc_18002BD12
0x18002bce8  mov     rcx, [rdi]
0x18002bceb  test    rcx, rcx
0x18002bcee  jnz     short loc_18002BD0E
0x18002bcf0  lea     eax, [rcx+2]
0x18002bcf3  mov     [rsp+158h+var_D4], eax
0x18002bcfa  lea     rdx, _TI1?AW4_unnamed_enum_ptecNoErrors_@@; pThrowInfo
0x18002bd01  lea     rcx, [rsp+158h+var_D4]; pExceptionObject
0x18002bd09  call    _CxxThrowException_0
0x18002bd0e  mov     [rcx], r12w
0x18002bd12  mov     [rdi+8], rsi
0x18002bd16  mov     [rdi+14h], r12d
0x18002bd1a  mov     rax, [rax+38h]
0x18002bd1e  movzx   ecx, byte ptr [rax+3Ah]
0x18002bd22  mov     [rdi+18h], ecx
0x18002bd25  mov     rax, [rsi]
0x18002bd28  mov     rcx, rsi
0x18002bd2b  mov     rax, [rax+28h]
0x18002bd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd34  mov     [rdi+1Ch], ax
0x18002bd38  lea     rdi, [r15+4D8h]
0x18002bd3f  mov     [rsp+158h+var_110], r12
0x18002bd44  mov     rcx, [rdi+8]
0x18002bd48  mov     r8, [rdi+10h]
0x18002bd4c  cmp     rcx, r8
0x18002bd4f  jl      short loc_18002BD79
  ... truncated ...
```
