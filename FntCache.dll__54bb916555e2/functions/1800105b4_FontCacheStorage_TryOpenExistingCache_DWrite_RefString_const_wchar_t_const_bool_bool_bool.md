# FontCacheStorage::TryOpenExistingCache(DWrite::RefString const &,wchar_t const *,bool,bool,bool)

- ea: `0x1800105b4`
- end: `0x1800109b3`
- name: `?TryOpenExistingCache@FontCacheStorage@@QEAAJAEBVRefString@DWrite@@PEB_W_N22@Z`
- size: `1023`
- prototype: `__int64 __fastcall(FontCacheStorage *this, const struct DWrite::RefString *, const wchar_t *, char, char, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callers

- `0x1800109bc`
- `0x180068b20`

## callees

- `0x1800086ac`
- `0x18000d55c`
- `0x18000e3f0`
- `0x18000e920`
- `0x18000f354`
- `0x18000f7bc`
- `0x1800105b4`
- `0x180010d70`
- `0x180010dc4`
- `0x180010e24`
- `0x180010e94`
- `0x1800113a4`
- `0x180028c50`
- `0x18009e420`
- `0x1800a3b30`
- `0x1800a3bc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800107a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800107a0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800108cd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800108cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FontCacheStorage::TryOpenExistingCache(
        FontCacheStorage *this,
        const struct DWrite::RefString *a2,
        const wchar_t *a3,
        char a4,
        char a5,
        bool a6)
{
  char *v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  struct DWrite::RefString::Data *v13; // rbx
  int v14; // eax
  unsigned int v15; // r15d
  int v16; // r9d
  int v17; // eax
  __int64 v19; // rcx
  signed int LastError; // eax
  unsigned int v21; // r15d
  struct DWrite::RefString::Data *v22; // [rsp+30h] [rbp-C8h] BYREF
  void *v23; // [rsp+38h] [rbp-C0h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-B8h]
  const wchar_t *v25; // [rsp+48h] [rbp-B0h]
  __int64 v26; // [rsp+50h] [rbp-A8h]
  char v27; // [rsp+58h] [rbp-A0h]
  struct DWrite::RefString::Data *v28; // [rsp+60h] [rbp-98h]
  void *v29; // [rsp+68h] [rbp-90h] BYREF
  struct DWrite::RefString::Data *v30[2]; // [rsp+70h] [rbp-88h] BYREF
  HANDLE hObject[3]; // [rsp+80h] [rbp-78h] BYREF
  _QWORD v32[12]; // [rsp+98h] [rbp-60h] BYREF

  v30[1] = (struct DWrite::RefString::Data *)0x676E696E65706FLL;
  *((_QWORD *)this + 3) = 0x676E696E65706FLL;
  v8 = (char *)this + 16;
  EventLogger::LogEvent<EventTag>((char *)this + 16, 0x656761726F7453LL, 0x6574617473LL, 0x676E696E65706FLL);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  v11 = *(_QWORD *)a2;
  v23 = (void *)(*(_QWORD *)a2 + 8LL);
  v24 = *(unsigned int *)(v11 + 4);
  v25 = a3;
  v26 = v10;
  DWrite::RefString::RefString(&v22, &v23);
  v28 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
  if ( a6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v22);
    DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)&DWrite::RefString::empty_);
    v13 = v22;
    v28 = v22;
    goto LABEL_5;
  }
  do
    ++v9;
  while ( a3[v9] );
  v19 = *(_QWORD *)a2;
  LOWORD(v25) = 126;
  v32[0] = v19 + 8;
  v32[1] = *(unsigned int *)(v19 + 4);
  v32[2] = v25;
  v32[3] = a3;
  v32[4] = v9;
  DWrite::RefString::RefString(v30, v32, v12);
  v13 = v30[0];
  _InterlockedIncrement((volatile signed __int32 *)v30[0]);
  DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)&DWrite::RefString::empty_);
  v28 = v13;
  DWrite::RefString::DecrementRef(v13);
  if ( MoveFileExW((LPCWSTR)v22 + 4, (LPCWSTR)v13 + 4, 1u) )
  {
LABEL_5:
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v14 = File::TryOpen((__int64)&v23, (const WCHAR *)v13 + 4, 5u);
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( v14 != -2003283965 )
        EventLogger::LogEvent<long,EventTag,unsigned int>(
          (_DWORD)v8,
          1919906899,
          1869771365,
          v14,
          0x676E696E65706FLL,
          585);
      *((_QWORD *)this + 3) = 1953066601;
      EventLogger::LogEvent<EventTag>(v8, 0x656761726F7453LL, 0x6574617473LL, 1953066601);
      File::Close((File *)&v23);
      DWrite::RefString::DecrementRef(v13);
      DWrite::RefString::DecrementRef(v22);
      return v15;
    }
    else
    {
      if ( v24 > 0xFFFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
      FileMapping::FileMapping((FileMapping *)hObject, v23, (unsigned int)v24);
      LOBYTE(v16) = a4;
      CacheWriter::CreateExistingServerCache((unsigned int)&v29, (unsigned int)hObject, v26, v16, a5);
      FileMapping::operator=((char *)this + 72, hObject);
      IntrusivePtr<CacheWriter>::operator=((char *)this + 96, &v29);
      File::operator=((char *)this + 32, &v23);
      v17 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 72LL) + 32LL);
      *((_QWORD *)this + 3) = 0x64656E65706FLL;
      EventLogger::LogEvent<EventTag,unsigned int>((_DWORD)v8, 1919906899, 1952543859, 1852141679, v17);
      if ( a6 )
      {
        *((_QWORD *)this + 3) = 0x64656873756C66LL;
        EventLogger::LogEvent<EventTag>(v8, 0x656761726F7453LL, 0x6574617473LL, 0x64656873756C66LL);
      }
      ReleaseReference<CacheWriter>(v29);
      if ( hObject[0] )
      {
        CloseHandle(hObject[0]);
        hObject[0] = 0;
        hObject[2] = 0;
      }
      File::Close((File *)&v23);
      DWrite::RefString::DecrementRef(v13);
      DWrite::RefString::DecrementRef(v22);
      return v15;
    }
  }
  LastError = GetLastError();
  if ( LastError <= 0 )
    v21 = LastError;
  else
    v21 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != 2 )
    EventLogger::LogEvent<long,EventTag,unsigned int>((_DWORD)v8, 1919906899, 1869771365, v21, 0x676E696E65706FLL, 567);
  *((_QWORD *)this + 3) = 1953066601;
  EventLogger::LogEvent<EventTag>(v8, 0x656761726F7453LL, 0x6574617473LL, 1953066601);
  DWrite::RefString::DecrementRef(v13);
  DWrite::RefString::DecrementRef(v22);
  return v21;
}

```

## disassembly

```asm
0x1800105b4  mov     [rsp+arg_18], r9b
0x1800105b9  mov     [rsp+arg_8], rdx
0x1800105be  mov     [rsp+arg_0], rcx
0x1800105c3  push    rbx
0x1800105c4  push    rsi
0x1800105c5  push    rdi
0x1800105c6  push    r12
0x1800105c8  push    r13
0x1800105ca  push    r14
0x1800105cc  push    r15
0x1800105ce  sub     rsp, 0C0h
0x1800105d5  mov     r15, r8
0x1800105d8  mov     r13, rcx
0x1800105db  mov     rsi, 676E696E65706Fh
0x1800105e5  mov     [rsp+0F8h+var_80], rsi
0x1800105ea  mov     [rcx+18h], rsi
0x1800105ee  mov     r14, 6574617473h
0x1800105f8  lea     r12, [rcx+10h]
0x1800105fc  mov     rdi, 656761726F7453h
0x180010606  mov     r9, rsi
0x180010609  mov     r8, r14
0x18001060c  mov     rdx, rdi
0x18001060f  mov     rcx, r12
0x180010612  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x180010617  nop
0x180010618  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001061c  mov     rdx, rbx
0x18001061f  xor     eax, eax
0x180010621  inc     rdx
0x180010624  cmp     [r15+rdx*2], ax
0x180010629  jnz     short loc_180010621
0x18001062b  mov     rcx, [rsp+0F8h+arg_8]
0x180010633  mov     rcx, [rcx]
0x180010636  lea     rax, [rcx+8]
0x18001063a  mov     [rsp+0F8h+var_C0], rax
0x18001063f  mov     eax, [rcx+4]
0x180010642  mov     [rsp+0F8h+var_B8], rax
0x180010647  mov     [rsp+0F8h+var_B0], r15
0x18001064c  mov     [rsp+0F8h+var_A8], rdx
0x180010651  lea     rdx, [rsp+0F8h+var_C0]
0x180010656  lea     rcx, [rsp+0F8h+var_C8]
0x18001065b  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x180010660  nop
0x180010661  lea     rcx, ?empty_@RefString@DWrite@@0UData@12@A; struct DWrite::RefString::Data *
0x180010668  mov     [rsp+0F8h+var_98], rcx
0x18001066d  xor     eax, eax
0x18001066f  cmp     [rsp+0F8h+arg_28], al
0x180010676  jz      loc_180010834
0x18001067c  mov     rax, [rsp+0F8h+var_C8]
0x180010681  lock inc dword ptr [rax]
0x180010684  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180010689  mov     rbx, [rsp+0F8h+var_C8]
0x18001068e  mov     [rsp+0F8h+var_98], rbx
0x180010693  xor     r15d, r15d
0x180010696  mov     [rsp+0F8h+var_C0], r15
0x18001069b  mov     [rsp+0F8h+var_B8], r15
0x1800106a0  mov     [rsp+0F8h+var_B0], r15
0x1800106a5  mov     [rsp+0F8h+var_A8], r15
0x1800106aa  mov     [rsp+0F8h+var_A0], r15b
0x1800106af  lea     rdx, [rbx+8]
0x1800106b3  mov     r8d, 5
0x1800106b9  lea     rcx, [rsp+0F8h+var_C0]
0x1800106be  call    ?TryOpen@File@@QEAAJPEB_WW4OpenMode@1@@Z; File::TryOpen(wchar_t const *,File::OpenMode)
0x1800106c3  mov     r15d, eax
0x1800106c6  test    eax, eax
0x1800106c8  js      loc_1800107EB
0x1800106ce  mov     eax, 0FFFFFFFFh
0x1800106d3  cmp     [rsp+0F8h+var_B8], rax
0x1800106d8  ja      loc_180010982
0x1800106de  mov     r8d, dword ptr [rsp+0F8h+var_B8]; unsigned __int64
0x1800106e3  mov     rdx, [rsp+0F8h+var_C0]; void *
0x1800106e8  lea     rcx, [rsp+0F8h+hObject]; this
0x1800106f0  call    ??0FileMapping@@QEAA@PEAX_K@Z; FileMapping::FileMapping(void *,unsigned __int64)
0x1800106f5  nop
0x1800106f6  mov     al, [rsp+0F8h+arg_20]
0x1800106fd  mov     byte ptr [rsp+0F8h+var_D8], al
0x180010701  mov     r9b, [rsp+0F8h+arg_18]
0x180010709  mov     r8, [rsp+0F8h+var_A8]
0x18001070e  lea     rdx, [rsp+0F8h+hObject]
0x180010716  lea     rcx, [rsp+0F8h+var_90]
0x18001071b  call    ?CreateExistingServerCache@CacheWriter@@SA?AV?$IntrusivePtr@VCacheWriter@@@@AEBVFileMapping@@VDateTime@@_N2@Z; CacheWriter::CreateExistingServerCache(FileMapping const &,DateTime,bool,bool)
0x180010720  lea     rcx, [r13+48h]
0x180010724  lea     rdx, [rsp+0F8h+hObject]
0x18001072c  call    ??4FileMapping@@QEAAAEAV0@$$QEAV0@@Z; FileMapping::operator=(FileMapping &&)
0x180010731  lea     rdx, [rsp+0F8h+var_90]
0x180010736  lea     rcx, [r13+60h]
0x18001073a  call    ??4?$IntrusivePtr@VCacheWriter@@@@QEAAAEAV0@$$QEAV0@@Z; IntrusivePtr<CacheWriter>::operator=(IntrusivePtr<CacheWriter> &&)
0x18001073f  lea     rcx, [r13+20h]
0x180010743  lea     rdx, [rsp+0F8h+var_C0]
0x180010748  call    ??4File@@QEAAAEAV0@$$QEAV0@@Z; File::operator=(File &&)
0x18001074d  mov     rax, [r13+60h]
0x180010751  mov     rcx, [rax+48h]
0x180010755  mov     eax, [rcx+20h]
0x180010758  mov     r9, 64656E65706Fh
0x180010762  mov     [r13+18h], r9
0x180010766  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18001076a  mov     r8, r14
0x18001076d  mov     rdx, rdi
0x180010770  mov     rcx, r12
0x180010773  call    ??$LogEvent@VEventTag@@I@EventLogger@@QEBAXVEventTag@@00I@Z; EventLogger::LogEvent<EventTag,uint>(EventTag,EventTag,EventTag,uint)
0x180010778  xor     esi, esi
0x18001077a  cmp     [rsp+0F8h+arg_28], sil
0x180010782  jnz     loc_180010988
0x180010788  mov     rcx, [rsp+0F8h+var_90]; void *
0x18001078d  call    ??$ReleaseReference@VCacheWriter@@@@YAXPEAVCacheWriter@@@Z; ReleaseReference<CacheWriter>(CacheWriter *)
0x180010792  nop
0x180010793  mov     rcx, [rsp+0F8h+hObject]; hObject
0x18001079b  test    rcx, rcx
0x18001079e  jz      short loc_1800107B6
0x1800107a0  call    cs:__imp_CloseHandle
0x1800107a6  mov     [rsp+0F8h+hObject], rsi
0x1800107ae  mov     [rsp+0F8h+var_68], rsi
0x1800107b6  lea     rcx, [rsp+0F8h+var_C0]; this
0x1800107bb  call    ?Close@File@@QEAAXXZ; File::Close(void)
0x1800107c0  nop
0x1800107c1  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800107c4  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800107c9  nop
0x1800107ca  mov     rcx, [rsp+0F8h+var_C8]; struct DWrite::RefString::Data *
0x1800107cf  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800107d4  nop
0x1800107d5  mov     eax, r15d
0x1800107d8  add     rsp, 0C0h
0x1800107df  pop     r15
0x1800107e1  pop     r14
0x1800107e3  pop     r13
0x1800107e5  pop     r12
0x1800107e7  pop     rdi
0x1800107e8  pop     rsi
0x1800107e9  pop     rbx
0x1800107ea  retn
0x1800107eb  cmp     r15d, 88985003h
0x1800107f2  jnz     loc_180010958
0x1800107f8  mov     r9d, 74696E69h
0x1800107fe  mov     [r13+18h], r9
0x180010802  mov     r8, r14
0x180010805  mov     rdx, rdi
0x180010808  mov     rcx, r12
0x18001080b  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x180010810  nop
0x180010811  lea     rcx, [rsp+0F8h+var_C0]; this
0x180010816  call    ?Close@File@@QEAAXXZ; File::Close(void)
0x18001081b  nop
0x18001081c  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18001081f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180010824  nop
0x180010825  mov     rcx, [rsp+0F8h+var_C8]; struct DWrite::RefString::Data *
0x18001082a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18001082f  mov     eax, r15d
0x180010832  jmp     short loc_1800107D8
0x180010834  inc     rbx
0x180010837  cmp     [r15+rbx*2], ax
0x18001083c  jnz     short loc_180010834
0x18001083e  mov     rax, [rsp+0F8h+arg_8]
0x180010846  mov     rcx, [rax]
0x180010849  mov     eax, 7Eh ; '~'
0x18001084e  mov     word ptr [rsp+0F8h+var_B0], ax
0x180010853  lea     rax, [rcx+8]
0x180010857  mov     [rsp+0F8h+var_60], rax
0x18001085f  mov     eax, [rcx+4]
0x180010862  mov     [rsp+0F8h+var_58], rax
0x18001086a  mov     rax, [rsp+0F8h+var_B0]
0x18001086f  mov     [rsp+0F8h+var_50], rax
0x180010877  mov     [rsp+0F8h+var_48], r15
0x18001087f  mov     [rsp+0F8h+var_40], rbx
0x180010887  lea     rdx, [rsp+0F8h+var_60]
0x18001088f  lea     rcx, [rsp+0F8h+var_88]
0x180010894  call    ??$?0V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t>,wchar_t const *>> const &)
0x180010899  mov     rbx, [rsp+0F8h+var_88]
0x18001089e  lock inc dword ptr [rbx]
0x1800108a1  lea     rcx, ?empty_@RefString@DWrite@@0UData@12@A; struct DWrite::RefString::Data *
0x1800108a8  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800108ad  mov     [rsp+0F8h+var_98], rbx
0x1800108b2  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800108b5  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800108ba  lea     rdx, [rbx+8]; lpNewFileName
0x1800108be  mov     rcx, [rsp+0F8h+var_C8]
0x1800108c3  add     rcx, 8; lpExistingFileName
0x1800108c7  mov     r8d, 1; dwFlags
0x1800108cd  call    cs:__imp_MoveFileExW
0x1800108d3  xor     r15d, r15d
0x1800108d6  test    eax, eax
0x1800108d8  jnz     loc_180010696
0x1800108de  call    cs:__imp_GetLastError
0x1800108e4  test    eax, eax
0x1800108e6  jle     short loc_18001092C
0x1800108e8  movzx   r15d, ax
0x1800108ec  or      r15d, 80070000h
0x1800108f3  cmp     eax, 2
0x1800108f6  jnz     short loc_180010931
0x1800108f8  mov     r9d, 74696E69h
0x1800108fe  mov     [r13+18h], r9
0x180010902  mov     r8, r14
0x180010905  mov     rdx, rdi
0x180010908  mov     rcx, r12
0x18001090b  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x180010910  nop
0x180010911  mov     rcx, rbx; struct DWrite::RefString::Data *
0x180010914  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180010919  nop
0x18001091a  mov     rcx, [rsp+0F8h+var_C8]; struct DWrite::RefString::Data *
0x18001091f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180010924  mov     eax, r15d
0x180010927  jmp     loc_1800107D8
0x18001092c  mov     r15d, eax
0x18001092f  jmp     short loc_1800108F3
0x180010931  mov     r8, 726F727265h
0x18001093b  mov     [rsp+0F8h+var_D0], 237h
0x180010943  mov     [rsp+0F8h+var_D8], rsi
0x180010948  mov     r9d, r15d
0x18001094b  mov     rdx, rdi
0x18001094e  mov     rcx, r12
0x180010951  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180010956  jmp     short loc_1800108F8
0x180010958  mov     r8, 726F727265h
0x180010962  mov     [rsp+0F8h+var_D0], 249h
0x18001096a  mov     [rsp+0F8h+var_D8], rsi
0x18001096f  mov     r9d, r15d
0x180010972  mov     rdx, rdi
0x180010975  mov     rcx, r12
0x180010978  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x18001097d  jmp     loc_1800107F8
0x180010982  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x180010988  mov     r9, 64656873756C66h
0x180010992  mov     [r13+18h], r9
0x180010996  mov     r8, r14
0x180010999  mov     rdx, rdi
0x18001099c  mov     rcx, r12
0x18001099f  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x1800109a4  jmp     loc_180010788
0x1800109a9  mov     r15d, dword ptr [rsp+0F8h+var_C8]
0x1800109ae  jmp     loc_1800107D5
```
