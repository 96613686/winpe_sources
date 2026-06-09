# CSmsConcatenateStore::Open(ushort const *)

- ea: `0x180061618`
- end: `0x180061a6c`
- name: `?Open@CSmsConcatenateStore@@QEAAJPEBG@Z`
- size: `1108`
- prototype: `__int64 __fastcall(HANDLE *this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x18004aee0`

## callees

- `0x180003a90`
- `0x180003f50`
- `0x180004998`
- `0x180051628`
- `0x18005faac`
- `0x18005fba4`
- `0x1800609fc`
- `0x180060dbc`
- `0x180061618`
- `0x180061d94`
- `0x180061f54`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800619bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800619bb`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800616bd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800616bd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800616ef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800616ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800616a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800616a2`

## string_xrefs

- `0x1800619f9`: `Open store 0x%08X, file: %S`
- `0x180061a05`: `CSmsConcatenateStore::Open`

## pseudocode

```c
__int64 __fastcall CSmsConcatenateStore::Open(HANDLE *this, LPCWSTR lpFileName)
{
  int v5; // r14d
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  __int64 v8; // rbx
  signed int updated; // ebx
  void *v10; // rax
  __int64 v11; // rax
  _DWORD *v12; // r15
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rbx
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  unsigned int v17; // eax
  volatile signed __int32 *v18; // rdi
  _OWORD *v19; // rax
  _OWORD *v20; // r8
  unsigned int v21; // r9d
  _QWORD *v22; // rdx
  signed int LastError; // eax
  volatile signed __int32 *v24; // rdi
  __int128 v25; // [rsp+40h] [rbp-30h] BYREF
  _OWORD *v26; // [rsp+50h] [rbp-20h] BYREF
  volatile signed __int32 *v27; // [rsp+58h] [rbp-18h]
  __int128 v28; // [rsp+60h] [rbp-10h]
  __int64 Buffer; // [rsp+C0h] [rbp+50h] BYREF
  _OWORD *v31; // [rsp+C8h] [rbp+58h]

  v28 = 0;
  Buffer = 0;
  if ( !lpFileName )
    return 2147942487LL;
  v5 = 1;
  if ( this[16] != (HANDLE)-1LL )
  {
    CSmsConcatenateStore::Close((CSmsConcatenateStore *)this);
    *((_DWORD *)this + 34) = 0;
  }
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 4u, 0x80000080, 0);
  this[16] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
LABEL_41:
    if ( updated < 0 )
    {
LABEL_42:
      if ( this[16] != (HANDLE)-1LL && v5 )
        updated = CSmsConcatenateStore::UpdateFileHeader((CSmsConcatenateStore *)this);
    }
  }
  else
  {
    FileSize = GetFileSize(FileW, 0);
    v8 = FileSize;
    if ( FileSize < 8
      || !ReadFile(this[16], &Buffer, 8u, 0, 0)
      || (_DWORD)Buffer != -2023476720
      || HIDWORD(Buffer) != (v8 - 8) / 0x298uLL )
    {
LABEL_7:
      updated = -2147024883;
      goto LABEL_42;
    }
    *((_DWORD *)this + 34) = HIDWORD(Buffer);
    v10 = operator new(0x298u);
    v11 = std::shared_ptr<SmsStoreItem_tag>::shared_ptr<SmsStoreItem_tag>(&v26, v10);
    v12 = *(_DWORD **)v11;
    *(_QWORD *)v11 = 0;
    *(_QWORD *)&v28 = v12;
    v13 = *(_QWORD *)(v11 + 8);
    *(_QWORD *)(v11 + 8) = 0;
    *((_QWORD *)&v28 + 1) = v13;
    v14 = v27;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    if ( !v12 )
    {
      updated = -2147024882;
      v5 = 0;
      goto LABEL_42;
    }
    updated = 0;
    v15 = 0;
    v16 = 8;
    if ( *((_DWORD *)this + 34) )
    {
      while ( 1 )
      {
        memset_0(v12, 0, 0x298u);
        updated = CSmsConcatenateStore::ReadMessage((CSmsConcatenateStore *)this, v16, (struct SmsStoreItem_tag *)v12);
        if ( updated < 0 )
        {
          *((_DWORD *)this + 34) = v15;
          goto LABEL_42;
        }
        if ( *v12 != 664 || !v12[151] && ((v17 = v12[150]) == 0 || v17 > v12[149]) )
        {
          *((_DWORD *)this + 34) = v15;
          goto LABEL_7;
        }
        v31 = operator new(0x10u);
        v18 = (volatile signed __int32 *)operator new(0x18u);
        *(_QWORD *)&v25 = v18;
        *(_OWORD *)v18 = 0;
        *((_DWORD *)v18 + 2) = 1;
        *((_DWORD *)v18 + 3) = 1;
        *(_QWORD *)v18 = &std::_Ref_count<_UUID_VECTOR>::`vftable';
        v19 = v31;
        *((_QWORD *)v18 + 2) = v31;
        v26 = v19;
        v27 = v18;
        operator delete(0);
        v20 = v31;
        *v31 = 0;
        *(_QWORD *)v20 = *((_QWORD *)v12 + 82);
        *((_DWORD *)v20 + 2) = 664 * v15 + 8;
        v21 = v12[1];
        if ( (v21 & 1) != 0 )
        {
          v25 = 0;
          _InterlockedAdd(v18 + 2, 1u);
          *(_QWORD *)&v25 = v20;
          *((_QWORD *)&v25 + 1) = v18;
          updated = CSmsConcatenateStore::AddInternal(this, v12 + 132, &v25, (v21 >> 1) & 1);
          if ( updated < 0 )
          {
            v5 = 0;
            if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(void *))v18)((void *)v18);
              if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
            }
            goto LABEL_42;
          }
        }
        else
        {
          v22 = this[14];
          if ( v22 == this[15] )
          {
            std::vector<std::shared_ptr<SmsStoreItemCache>>::_Emplace_reallocate<std::shared_ptr<SmsStoreItemCache> const &>(
              this + 13,
              v22,
              &v26);
            v18 = v27;
          }
          else
          {
            *v22 = 0;
            v22[1] = 0;
            _InterlockedAdd(v18 + 2, 1u);
            *v22 = v20;
            v22[1] = v18;
            this[14] = (char *)this[14] + 16;
          }
        }
        if ( v18 )
        {
          if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v18)((void *)v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
        ++v15;
        v16 += 664;
        if ( v15 >= *((_DWORD *)this + 34) )
          goto LABEL_41;
      }
    }
  }
  LogSmsRouterInfo("CSmsConcatenateStore::Open", 0xF1u, "Open store 0x%08X, file: %S", (_DWORD)this, lpFileName);
  v24 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
    if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180061618  mov     [rsp-38h+arg_0], rbx
0x18006161d  mov     [rsp-38h+arg_8], rdx
0x180061622  push    rbp
0x180061623  push    rsi
0x180061624  push    rdi
0x180061625  push    r12
0x180061627  push    r13
0x180061629  push    r14
0x18006162b  push    r15
0x18006162d  mov     rbp, rsp
0x180061630  sub     rsp, 70h
0x180061634  mov     rbx, rdx
0x180061637  mov     rsi, rcx
0x18006163a  xorps   xmm0, xmm0
0x18006163d  movdqu  [rbp+var_10], xmm0
0x180061642  mov     [rbp+Buffer], 0
0x18006164a  test    rdx, rdx
0x18006164d  jnz     short loc_180061659
0x18006164f  mov     eax, 80070057h
0x180061654  jmp     loc_180061A54
0x180061659  mov     r14d, 1
0x18006165f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180061663  cmp     [rcx+80h], rdi
0x18006166a  jz      short loc_18006167B
0x18006166c  call    ?Close@CSmsConcatenateStore@@QEAAJXZ; CSmsConcatenateStore::Close(void)
0x180061671  mov     dword ptr [rsi+88h], 0
0x18006167b  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180061684  mov     [rsp+70h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x18006168c  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x180061694  xor     r9d, r9d; lpSecurityAttributes
0x180061697  xor     r8d, r8d; dwShareMode
0x18006169a  mov     edx, 0C0000000h; dwDesiredAccess
0x18006169f  mov     rcx, rbx; lpFileName
0x1800616a2  call    cs:__imp_CreateFileW
0x1800616a8  mov     [rsi+80h], rax
0x1800616af  cmp     rax, rdi
0x1800616b2  jz      loc_1800619BB
0x1800616b8  xor     edx, edx; lpFileSizeHigh
0x1800616ba  mov     rcx, rax; hFile
0x1800616bd  call    cs:__imp_GetFileSize
0x1800616c3  mov     ebx, eax
0x1800616c5  cmp     eax, 8
0x1800616c8  jnb     short loc_1800616D4
0x1800616ca  mov     ebx, 8007000Dh
0x1800616cf  jmp     loc_1800619D4
0x1800616d4  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800616dd  xor     r9d, r9d; lpNumberOfBytesRead
0x1800616e0  lea     r8d, [r9+8]; nNumberOfBytesToRead
0x1800616e4  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800616e8  mov     rcx, [rsi+80h]; hFile
0x1800616ef  call    cs:__imp_ReadFile
0x1800616f5  test    eax, eax
0x1800616f7  jz      short loc_1800616CA
0x1800616f9  cmp     dword ptr [rbp+Buffer], 87643210h
0x180061700  jnz     short loc_1800616CA
0x180061702  lea     rcx, [rbx-8]
0x180061706  mov     rax, 3159721ED7E75347h
0x180061710  mul     rcx
0x180061713  shr     rdx, 7
0x180061717  mov     ecx, dword ptr [rbp+Buffer+4]
0x18006171a  cmp     rcx, rdx
0x18006171d  jnz     short loc_1800616CA
0x18006171f  mov     [rsi+88h], ecx
0x180061725  mov     ecx, 298h; Size
0x18006172a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006172f  mov     rdx, rax
0x180061732  lea     rcx, [rbp+var_20]
0x180061736  call    ??$?0USmsStoreItem_tag@@$0A@@?$shared_ptr@USmsStoreItem_tag@@@std@@QEAA@PEAUSmsStoreItem_tag@@@Z; std::shared_ptr<SmsStoreItem_tag>::shared_ptr<SmsStoreItem_tag>(SmsStoreItem_tag *)
0x18006173b  mov     r15, [rax]
0x18006173e  mov     qword ptr [rax], 0
0x180061745  mov     qword ptr [rbp+var_10], r15
0x180061749  mov     rcx, [rax+8]
0x18006174d  mov     qword ptr [rax+8], 0
0x180061755  mov     qword ptr [rbp+var_10+8], rcx
0x180061759  mov     rbx, [rbp+var_18]
0x18006175d  test    rbx, rbx
0x180061760  jz      short loc_180061795
0x180061762  mov     eax, edi
0x180061764  lock xadd [rbx+8], eax
0x180061769  add     eax, edi
0x18006176b  jnz     short loc_180061795
0x18006176d  mov     rax, [rbx]
0x180061770  mov     rcx, rbx
0x180061773  mov     rax, [rax]
0x180061776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006177b  mov     eax, edi
0x18006177d  lock xadd [rbx+0Ch], eax
0x180061782  add     eax, edi
0x180061784  jnz     short loc_180061795
0x180061786  mov     rax, [rbx]
0x180061789  mov     rcx, rbx
0x18006178c  mov     rax, [rax+8]
0x180061790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061795  test    r15, r15
0x180061798  jz      loc_1800619B1
0x18006179e  xor     ebx, ebx
0x1800617a0  xor     r12d, r12d
0x1800617a3  lea     r13d, [rbx+8]
0x1800617a7  cmp     [rsi+88h], ebx
0x1800617ad  jbe     loc_1800619ED
0x1800617b3  xor     edx, edx; Val
0x1800617b5  mov     r8d, 298h; Size
0x1800617bb  mov     rcx, r15; void *
0x1800617be  call    memset_0
0x1800617c3  mov     r8, r15; struct SmsStoreItem_tag *
0x1800617c6  mov     edx, r13d; unsigned int
0x1800617c9  mov     rcx, rsi; this
0x1800617cc  call    ?ReadMessage@CSmsConcatenateStore@@AEAAJKPEAUSmsStoreItem_tag@@@Z; CSmsConcatenateStore::ReadMessage(ulong,SmsStoreItem_tag *)
0x1800617d1  mov     ebx, eax
0x1800617d3  test    eax, eax
0x1800617d5  js      loc_1800619A8
0x1800617db  cmp     dword ptr [r15], 298h
0x1800617e2  jnz     loc_18006199C
0x1800617e8  cmp     dword ptr [r15+25Ch], 0
0x1800617f0  jnz     short loc_18006180E
0x1800617f2  mov     eax, [r15+258h]
0x1800617f9  test    eax, eax
0x1800617fb  jz      loc_18006199C
0x180061801  cmp     eax, [r15+254h]
0x180061808  ja      loc_18006199C
0x18006180e  mov     ecx, 10h; Size
0x180061813  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061818  mov     [rbp+arg_18], rax
0x18006181c  mov     ecx, 18h; Size
0x180061821  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061826  mov     rdi, rax
0x180061829  mov     qword ptr [rbp+var_30], rax
0x18006182d  xorps   xmm0, xmm0
0x180061830  movups  xmmword ptr [rax], xmm0
0x180061833  mov     [rax+8], r14d
0x180061837  mov     [rax+0Ch], r14d
0x18006183b  lea     rax, ??_7?$_Ref_count@U_UUID_VECTOR@@@std@@6B@; const std::_Ref_count<_UUID_VECTOR>::`vftable'
0x180061842  mov     [rdi], rax
0x180061845  mov     rax, [rbp+arg_18]
0x180061849  mov     [rdi+10h], rax
0x18006184d  mov     [rbp+var_20], rax
0x180061851  mov     [rbp+var_18], rdi
0x180061855  mov     edx, 10h
0x18006185a  xor     ecx, ecx; Block
0x18006185c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180061861  nop
0x180061862  xorps   xmm0, xmm0
0x180061865  mov     r8, [rbp+arg_18]
0x180061869  movups  xmmword ptr [r8], xmm0
0x18006186d  mov     rax, [r15+290h]
0x180061874  mov     [r8], rax
0x180061877  imul    eax, r12d, 298h
0x18006187e  add     eax, 8
0x180061881  mov     [r8+8], eax
0x180061885  mov     r9d, [r15+4]
0x180061889  test    r14b, r9b
0x18006188c  jz      short loc_18006190A
0x18006188e  shr     r9d, 1
0x180061891  and     r9d, r14d
0x180061894  movdqu  [rbp+var_30], xmm0
0x180061899  lock add [rdi+8], r14d
0x18006189e  mov     qword ptr [rbp+var_30], r8
0x1800618a2  mov     qword ptr [rbp+var_30+8], rdi
0x1800618a6  lea     rdx, [r15+210h]
0x1800618ad  lea     r8, [rbp+var_30]
0x1800618b1  mov     rcx, rsi
0x1800618b4  call    ?AddInternal@CSmsConcatenateStore@@AEAAJPEAUSmsFragmentInfo@@V?$shared_ptr@USmsStoreItemCache@@@std@@H@Z; CSmsConcatenateStore::AddInternal(SmsFragmentInfo *,std::shared_ptr<SmsStoreItemCache>,int)
0x1800618b9  mov     ebx, eax
0x1800618bb  test    eax, eax
0x1800618bd  jns     loc_180061947
0x1800618c3  xor     r14d, r14d
0x1800618c6  or      eax, 0FFFFFFFFh
0x1800618c9  lock xadd [rdi+8], eax
0x1800618ce  cmp     eax, 1
0x1800618d1  jnz     loc_1800619D4
0x1800618d7  mov     rax, [rdi]
0x1800618da  mov     rcx, rdi
0x1800618dd  mov     rax, [rax]
0x1800618e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618e5  or      eax, 0FFFFFFFFh
0x1800618e8  lock xadd [rdi+0Ch], eax
0x1800618ed  cmp     eax, 1
0x1800618f0  jnz     loc_1800619D4
0x1800618f6  mov     rax, [rdi]
0x1800618f9  mov     rcx, rdi
0x1800618fc  mov     rax, [rax+8]
0x180061900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061905  jmp     loc_1800619D4
0x18006190a  lea     rcx, [rsi+68h]
0x18006190e  mov     rdx, [rcx+8]
0x180061912  cmp     rdx, [rcx+10h]
0x180061916  jz      short loc_18006193A
0x180061918  mov     qword ptr [rdx], 0
0x18006191f  mov     qword ptr [rdx+8], 0
0x180061927  lock add [rdi+8], r14d
0x18006192c  mov     [rdx], r8
0x18006192f  mov     [rdx+8], rdi
0x180061933  add     qword ptr [rcx+8], 10h
0x180061938  jmp     short loc_180061947
0x18006193a  lea     r8, [rbp+var_20]
0x18006193e  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@USmsStoreItemCache@@@std@@@?$vector@V?$shared_ptr@USmsStoreItemCache@@@std@@V?$allocator@V?$shared_ptr@USmsStoreItemCache@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@USmsStoreItemCache@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<SmsStoreItemCache>>::_Emplace_reallocate<std::shared_ptr<SmsStoreItemCache> const &>(std::shared_ptr<SmsStoreItemCache> * const,std::shared_ptr<SmsStoreItemCache> const &)
0x180061943  mov     rdi, [rbp+var_18]
0x180061947  test    rdi, rdi
0x18006194a  jz      short loc_180061983
0x18006194c  or      eax, 0FFFFFFFFh
0x18006194f  lock xadd [rdi+8], eax
0x180061954  cmp     eax, 1
0x180061957  jnz     short loc_180061983
0x180061959  mov     rax, [rdi]
0x18006195c  mov     rcx, rdi
0x18006195f  mov     rax, [rax]
0x180061962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061967  or      eax, 0FFFFFFFFh
0x18006196a  lock xadd [rdi+0Ch], eax
0x18006196f  cmp     eax, 1
0x180061972  jnz     short loc_180061983
0x180061974  mov     rax, [rdi]
0x180061977  mov     rcx, rdi
0x18006197a  mov     rax, [rax+8]
0x18006197e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061983  add     r12d, r14d
0x180061986  add     r13d, 298h
0x18006198d  cmp     r12d, [rsi+88h]
0x180061994  jb      loc_1800617B3
0x18006199a  jmp     short loc_1800619D0
0x18006199c  mov     [rsi+88h], r12d
0x1800619a3  jmp     loc_1800616CA
0x1800619a8  mov     [rsi+88h], r12d
0x1800619af  jmp     short loc_1800619D4
0x1800619b1  mov     ebx, 8007000Eh
0x1800619b6  xor     r14d, r14d
0x1800619b9  jmp     short loc_1800619D4
0x1800619bb  call    cs:__imp_GetLastError
0x1800619c1  mov     ebx, eax
0x1800619c3  test    eax, eax
0x1800619c5  jle     short loc_1800619D0
0x1800619c7  movzx   ebx, ax
0x1800619ca  or      ebx, 80070000h
0x1800619d0  test    ebx, ebx
0x1800619d2  jns     short loc_1800619ED
0x1800619d4  cmp     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x1800619dc  jz      short loc_1800619ED
0x1800619de  test    r14d, r14d
0x1800619e1  jz      short loc_1800619ED
0x1800619e3  mov     rcx, rsi; this
0x1800619e6  call    ?UpdateFileHeader@CSmsConcatenateStore@@AEAAJXZ; CSmsConcatenateStore::UpdateFileHeader(void)
0x1800619eb  mov     ebx, eax
0x1800619ed  mov     rax, [rbp+arg_8]
0x1800619f1  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800619f6  mov     r9, rsi
0x1800619f9  lea     r8, aOpenStore0x08x; "Open store 0x%08X, file: %S"
0x180061a00  mov     edx, 0F1h; unsigned int
0x180061a05  lea     rcx, aCsmsconcatenat; "CSmsConcatenateStore::Open"
0x180061a0c  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180061a11  nop
0x180061a12  mov     rdi, qword ptr [rbp+var_10+8]
0x180061a16  test    rdi, rdi
0x180061a19  jz      short loc_180061A52
0x180061a1b  or      eax, 0FFFFFFFFh
0x180061a1e  lock xadd [rdi+8], eax
0x180061a23  cmp     eax, 1
0x180061a26  jnz     short loc_180061A52
0x180061a28  mov     rax, [rdi]
0x180061a2b  mov     rcx, rdi
0x180061a2e  mov     rax, [rax]
0x180061a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a36  or      eax, 0FFFFFFFFh
0x180061a39  lock xadd [rdi+0Ch], eax
0x180061a3e  cmp     eax, 1
0x180061a41  jnz     short loc_180061A52
0x180061a43  mov     rax, [rdi]
0x180061a46  mov     rcx, rdi
0x180061a49  mov     rax, [rax+8]
0x180061a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a52  mov     eax, ebx
0x180061a54  mov     rbx, [rsp+70h+arg_0]
0x180061a5c  add     rsp, 70h
0x180061a60  pop     r15
0x180061a62  pop     r14
0x180061a64  pop     r13
0x180061a66  pop     r12
0x180061a68  pop     rdi
0x180061a69  pop     rsi
0x180061a6a  pop     rbp
0x180061a6b  retn
```
