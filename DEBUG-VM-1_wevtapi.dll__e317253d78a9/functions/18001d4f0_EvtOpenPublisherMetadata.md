# EvtOpenPublisherMetadata

- ea: `0x18001d4f0`
- end: `0x18001d8ca`
- name: `EvtOpenPublisherMetadata`
- size: `986`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, LPCWSTR PublisherId, LPCWSTR LogFilePath, LCID Locale, DWORD Flags)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18000a100`
- `0x18000c404`
- `0x180013f6c`
- `0x18001d4f0`
- `0x18001d8d0`
- `0x18001d9e0`
- `0x18001eaf4`
- `0x180021534`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5f9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001d720`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001d720`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18001d702`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18001d702`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EVT_HANDLE __stdcall EvtOpenPublisherMetadata(
        EVT_HANDLE Session,
        LPCWSTR PublisherId,
        LPCWSTR LogFilePath,
        LCID Locale,
        DWORD Flags)
{
  const wchar_t *v6; // rbx
  __int64 v7; // rdi
  void *v8; // rsi
  DWORD v9; // r14d
  unsigned int ThreadUILanguage; // ecx
  int v11; // ecx
  __int64 v12; // rcx
  DWORD v13; // r14d
  int v15; // ecx
  __int64 v16; // rdi
  __int64 v17; // rax
  DWORD LastError; // edi
  LCID v19; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B8h] BYREF
  wmi::RefBase *v22; // [rsp+58h] [rbp-B0h] BYREF
  void *v23; // [rsp+60h] [rbp-A8h]
  __int128 pExceptionObject; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+78h] [rbp-90h]
  int v26; // [rsp+80h] [rbp-88h]
  int v27; // [rsp+84h] [rbp-84h]
  int v28; // [rsp+88h] [rbp-80h]
  __int128 v29; // [rsp+90h] [rbp-78h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-68h]
  DWORD v31; // [rsp+A8h] [rbp-60h]
  int v32; // [rsp+ACh] [rbp-5Ch]
  int v33; // [rsp+B0h] [rbp-58h]
  wchar_t *v34[2]; // [rsp+B8h] [rbp-50h] BYREF
  char v35; // [rsp+C8h] [rbp-40h] BYREF
  EvtException *v36; // [rsp+D8h] [rbp-30h] BYREF
  LPCWSTR v37; // [rsp+118h] [rbp+10h] BYREF
  LPCWSTR v38; // [rsp+120h] [rbp+18h] BYREF

  v38 = LogFilePath;
  v37 = PublisherId;
  v6 = LogFilePath;
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v23 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v9 = Flags;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v25 = 0;
      v26 = 87;
      v27 = -1;
      v28 = 1713;
      throw (EvtException *)&pExceptionObject;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
    if ( v6 )
    {
      FullyQualifyFilePath(v34, v6);
      v6 = v34[0];
      v38 = v34[0];
      if ( !FileExists(v34[0]) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, LastError);
        }
        v29 = 0;
        v30 = 0;
        v31 = LastError;
        v32 = -1;
        v33 = 1723;
        throw (EvtException *)&v29;
      }
    }
    ThreadUILanguage = Locale;
    v19 = Locale;
    if ( !Locale )
    {
      ThreadUILanguage = GetThreadUILanguage();
      v19 = ThreadUILanguage;
      if ( ((ThreadUILanguage - 4096) & 0xFFFFFBFF) == 0 )
      {
        ThreadUILanguage = GetThreadLocale();
        v19 = ThreadUILanguage;
      }
    }
    if ( v6 && LocaleMetaData::IsLocalePresent(ThreadUILanguage, v6) )
    {
      v20 = 0;
      v12 = HandleTable::Emplace<LocaleMetadataObject,wchar_t const * &,wchar_t const * &,unsigned long &,unsigned long &>(
              v11,
              (unsigned int)&v20,
              (unsigned int)&v37,
              (unsigned int)&v38,
              (__int64)&v19);
      if ( v12 )
      {
        *(_QWORD *)(v12 + 16) = v20;
        _InterlockedAdd((volatile signed __int32 *)(v12 + 8), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v12 + 24), 1u);
        v7 = v12;
        v21 = v12;
        v22 = 0;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v22);
        v13 = 0;
      }
      else
      {
        v13 = 14;
      }
      if ( v7 )
      {
        v8 = *(void **)(v7 + 16);
        v21 = 0;
        *(_BYTE *)(v7 + 29) = 1;
      }
      else
      {
        v8 = 0;
      }
      v23 = v8;
    }
    else
    {
      GetSession(&v22);
      if ( !Locale )
        v9 = 256;
      Flags = v9;
      v20 = 0;
      v16 = HandleTable::Emplace<PublisherMetadataObject,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,unsigned long &,unsigned long &>(
              v15,
              (unsigned int)&v20,
              (unsigned int)&v22,
              (unsigned int)&v37,
              (__int64)&v38,
              (__int64)&v19,
              (__int64)&Flags);
      if ( v16 )
      {
        *(_QWORD *)(v16 + 16) = v20;
        _InterlockedAdd((volatile signed __int32 *)(v16 + 8), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v16 + 24), 1u);
        v21 = v16;
        v20 = 0;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v20);
        v13 = 0;
        if ( *(_BYTE *)(v16 + 28) == 12 )
          v17 = v16;
        else
          v17 = 0;
        v8 = *(void **)(v16 + 16);
        v21 = 0;
        *(_BYTE *)(v16 + 29) = 1;
        v23 = v8;
        *(_QWORD *)(v17 + 56) = v8;
      }
      else
      {
        v13 = 14;
      }
      if ( v22 )
        wmi::RefBase::Release(v22);
    }
    if ( (char *)v34[0] != &v35 )
      operator delete(v34[0]);
  }
  catch ( EvtException *v36 )
  {
    Flags = *((_DWORD *)v36 + 6);
    v13 = Flags;
    v8 = v23;
  }
  SetLastError(v13);
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v21);
  return v8;
}

```

## disassembly

```asm
0x18001d4f0  mov     [rsp+arg_0], rbx
0x18001d4f5  mov     [rsp+arg_10], r8
0x18001d4fa  mov     [rsp+arg_8], rdx
0x18001d4ff  push    rsi
0x18001d500  push    rdi
0x18001d501  push    r12
0x18001d503  push    r14
0x18001d505  push    r15
0x18001d507  sub     rsp, 0E0h
0x18001d50e  mov     r15d, r9d
0x18001d511  mov     rbx, r8
0x18001d514  mov     r12, rcx
0x18001d517  xor     edi, edi
0x18001d519  mov     [rsp+108h+var_B8], rdi
0x18001d51e  xor     esi, esi
0x18001d520  mov     [rsp+108h+var_A8], rsi
0x18001d525  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001d52a  mov     r14d, [rsp+108h+Flags]
0x18001d532  test    r14d, r14d
0x18001d535  jnz     loc_18001D739
0x18001d53b  lea     rcx, [rsp+108h+var_50]
0x18001d543  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d548  nop
0x18001d549  test    rbx, rbx
0x18001d54c  jnz     loc_18001D7B8
0x18001d552  mov     ecx, r15d; unsigned int
0x18001d555  mov     [rsp+108h+var_C8], ecx
0x18001d559  test    r15d, r15d
0x18001d55c  jz      loc_18001D702
0x18001d562  test    rbx, rbx
0x18001d565  jz      loc_18001D625
0x18001d56b  mov     rdx, rbx; wchar_t *
0x18001d56e  call    ?IsLocalePresent@LocaleMetaData@@SA_NKPEB_W@Z; LocaleMetaData::IsLocalePresent(ulong,wchar_t const *)
0x18001d573  test    al, al
0x18001d575  jz      loc_18001D625
0x18001d57b  mov     [rsp+108h+var_C0], 0
0x18001d584  lea     rax, [rsp+108h+var_C8]
0x18001d589  mov     [rsp+108h+var_E8], rax
0x18001d58e  lea     r9, [rsp+108h+arg_10]
0x18001d596  lea     r8, [rsp+108h+arg_8]
0x18001d59e  lea     rdx, [rsp+108h+var_C0]
0x18001d5a3  call    ??$Emplace@VLocaleMetadataObject@@AEAPEB_WAEAPEB_WAEAKAEAK@HandleTable@@QEAAPEAVLocaleMetadataObject@@AEAPEAXAEAPEB_W1AEAK2@Z; HandleTable::Emplace<LocaleMetadataObject,wchar_t const * &,wchar_t const * &,ulong &,ulong &>(void * &,wchar_t const * &,wchar_t const * &,ulong &,ulong &)
0x18001d5a8  mov     rcx, rax
0x18001d5ab  mov     ebx, 1
0x18001d5b0  test    rax, rax
0x18001d5b3  jnz     loc_18001D87C
0x18001d5b9  lea     r14d, [rax+0Eh]
0x18001d5bd  test    rdi, rdi
0x18001d5c0  jz      loc_18001D8B0
0x18001d5c6  mov     rsi, [rdi+10h]
0x18001d5ca  mov     [rsp+108h+var_B8], 0
0x18001d5d3  xchg    bl, [rdi+1Dh]
0x18001d5d6  mov     [rsp+108h+var_A8], rsi
0x18001d5db  lea     rax, [rsp+108h+var_40]
0x18001d5e3  mov     rcx, [rsp+108h+var_50]; void *
0x18001d5eb  cmp     rcx, rax
0x18001d5ee  jz      short loc_18001D5F6
0x18001d5f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d5f5  nop
0x18001d5f6  mov     ecx, r14d; dwErrCode
0x18001d5f9  call    cs:__imp_SetLastError
0x18001d5ff  nop
0x18001d600  lea     rcx, [rsp+108h+var_B8]; this
0x18001d605  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001d60a  mov     rax, rsi
0x18001d60d  mov     rbx, [rsp+108h+arg_0]
0x18001d615  add     rsp, 0E0h
0x18001d61c  pop     r15
0x18001d61e  pop     r14
0x18001d620  pop     r12
0x18001d622  pop     rdi
0x18001d623  pop     rsi
0x18001d624  retn
0x18001d625  mov     rdx, r12
0x18001d628  lea     rcx, [rsp+108h+var_B0]; void *
0x18001d62d  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001d632  nop
0x18001d633  mov     eax, 100h
0x18001d638  test    r15d, r15d
0x18001d63b  cmovz   r14d, eax
0x18001d63f  mov     [rsp+108h+Flags], r14d
0x18001d647  mov     [rsp+108h+var_C0], 0
0x18001d650  lea     rax, [rsp+108h+Flags]
0x18001d658  mov     [rsp+108h+var_D8], rax
0x18001d65d  lea     rax, [rsp+108h+var_C8]
0x18001d662  mov     [rsp+108h+var_E0], rax
0x18001d667  lea     rax, [rsp+108h+arg_10]
0x18001d66f  mov     [rsp+108h+var_E8], rax
0x18001d674  lea     r9, [rsp+108h+arg_8]
0x18001d67c  lea     r8, [rsp+108h+var_B0]
0x18001d681  lea     rdx, [rsp+108h+var_C0]
0x18001d686  call    ??$Emplace@VPublisherMetadataObject@@AEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAPEB_WAEAKAEAK@HandleTable@@QEAAPEAVPublisherMetadataObject@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@AEAPEB_W2AEAK3@Z; HandleTable::Emplace<PublisherMetadataObject,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,ulong &,ulong &>(void * &,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,ulong &,ulong &)
0x18001d68b  mov     rdi, rax
0x18001d68e  test    rax, rax
0x18001d691  jz      loc_18001D731
0x18001d697  mov     rax, [rsp+108h+var_C0]
0x18001d69c  mov     [rdi+10h], rax
0x18001d6a0  mov     ebx, 1
0x18001d6a5  lock add [rdi+8], ebx
0x18001d6a9  lock add [rdi+18h], ebx
0x18001d6ad  mov     [rsp+108h+var_B8], rdi
0x18001d6b2  mov     [rsp+108h+var_C0], 0
0x18001d6bb  lea     rcx, [rsp+108h+var_C0]; this
0x18001d6c0  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001d6c5  xor     r14d, r14d
0x18001d6c8  cmp     byte ptr [rdi+1Ch], 0Ch
0x18001d6cc  jnz     short loc_18001D6FE
0x18001d6ce  mov     rax, rdi
0x18001d6d1  mov     rsi, [rdi+10h]
0x18001d6d5  mov     [rsp+108h+var_B8], r14
0x18001d6da  xchg    bl, [rdi+1Dh]
0x18001d6dd  mov     [rsp+108h+var_A8], rsi
0x18001d6e2  mov     [rax+38h], rsi
0x18001d6e6  mov     rcx, [rsp+108h+var_B0]; this
0x18001d6eb  test    rcx, rcx
0x18001d6ee  jz      loc_18001D5DB
0x18001d6f4  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001d6f9  jmp     loc_18001D5DB
0x18001d6fe  xor     eax, eax
0x18001d700  jmp     short loc_18001D6D1
0x18001d702  call    cs:__imp_GetThreadUILanguage
0x18001d708  movzx   ecx, ax
0x18001d70b  mov     [rsp+108h+var_C8], ecx
0x18001d70f  lea     eax, [rcx-1000h]
0x18001d715  test    eax, 0FFFFFBFFh
0x18001d71a  jnz     loc_18001D562
0x18001d720  call    cs:__imp_GetThreadLocale
0x18001d726  mov     ecx, eax
0x18001d728  mov     [rsp+108h+var_C8], eax
0x18001d72c  jmp     loc_18001D562
0x18001d731  mov     r14d, 0Eh
0x18001d737  jmp     short loc_18001D6E6
0x18001d739  lea     rax, WPP_GLOBAL_Control
0x18001d740  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d747  cmp     rcx, rax
0x18001d74a  jz      short loc_18001D773
0x18001d74c  mov     ebx, 1
0x18001d751  test    [rcx+1Ch], bl
0x18001d754  jz      short loc_18001D773
0x18001d756  cmp     byte ptr [rcx+19h], 2
0x18001d75a  jb      short loc_18001D773
0x18001d75c  lea     edx, [rbx+31h]
0x18001d75f  lea     r9d, [rbx+56h]
0x18001d763  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001d76a  mov     rcx, [rcx+10h]
0x18001d76e  call    WPP_SF_D
0x18001d773  xorps   xmm0, xmm0
0x18001d776  movdqu  [rsp+108h+pExceptionObject], xmm0
0x18001d77c  mov     [rsp+108h+var_90], 0
0x18001d785  mov     [rsp+108h+var_88], 57h ; 'W'
0x18001d790  mov     [rsp+108h+var_84], 0FFFFFFFFh
0x18001d79b  mov     [rsp+108h+var_80], 6B1h
0x18001d7a6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001d7ad  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001d7b2  call    _CxxThrowException_0
0x18001d7b8  mov     rdx, rbx
0x18001d7bb  lea     rcx, [rsp+108h+var_50]
0x18001d7c3  call    FullyQualifyFilePath
0x18001d7c8  mov     rbx, [rsp+108h+var_50]
0x18001d7d0  mov     [rsp+108h+arg_10], rbx
0x18001d7d8  mov     rcx, rbx; wchar_t *
0x18001d7db  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x18001d7e0  test    al, al
0x18001d7e2  jnz     loc_18001D552
0x18001d7e8  call    cs:__imp_GetLastError
0x18001d7ee  mov     edi, eax
0x18001d7f0  mov     eax, 507h
0x18001d7f5  test    edi, edi
0x18001d7f7  cmovz   edi, eax
0x18001d7fa  lea     rax, WPP_GLOBAL_Control
0x18001d801  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d808  cmp     rcx, rax
0x18001d80b  jz      short loc_18001D833
0x18001d80d  mov     ebx, 1
0x18001d812  test    [rcx+1Ch], bl
0x18001d815  jz      short loc_18001D833
0x18001d817  cmp     byte ptr [rcx+19h], 2
0x18001d81b  jb      short loc_18001D833
0x18001d81d  lea     edx, [rbx+32h]
0x18001d820  mov     r9d, edi
0x18001d823  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001d82a  mov     rcx, [rcx+10h]
0x18001d82e  call    WPP_SF_D
0x18001d833  xorps   xmm0, xmm0
0x18001d836  movdqu  [rsp+108h+var_78], xmm0
0x18001d83f  mov     [rsp+108h+var_68], 0
0x18001d84b  mov     [rsp+108h+var_60], edi
0x18001d852  mov     [rsp+108h+var_5C], 0FFFFFFFFh
0x18001d85d  mov     [rsp+108h+var_58], 6BBh
0x18001d868  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001d86f  lea     rcx, [rsp+108h+var_78]; pExceptionObject
0x18001d877  call    _CxxThrowException_0
0x18001d87c  mov     rax, [rsp+108h+var_C0]
0x18001d881  mov     [rcx+10h], rax
0x18001d885  lock add [rcx+8], ebx
0x18001d889  lock add [rcx+18h], ebx
0x18001d88d  mov     rdi, rcx
0x18001d890  mov     [rsp+108h+var_B8], rcx
0x18001d895  mov     [rsp+108h+var_B0], 0
0x18001d89e  lea     rcx, [rsp+108h+var_B0]; this
0x18001d8a3  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001d8a8  xor     r14d, r14d
0x18001d8ab  jmp     loc_18001D5BD
0x18001d8b0  xor     esi, esi
0x18001d8b2  jmp     loc_18001D5D6
0x18001d8b7  mov     r14d, [rsp+108h+Flags]
0x18001d8bf  mov     rsi, [rsp+108h+var_A8]
0x18001d8c4  jmp     loc_18001D5F6
```
