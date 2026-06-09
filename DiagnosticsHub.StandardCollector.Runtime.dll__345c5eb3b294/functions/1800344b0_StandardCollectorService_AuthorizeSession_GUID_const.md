# StandardCollectorService::AuthorizeSession(_GUID const &)

- ea: `0x1800344b0`
- end: `0x1800346b1`
- name: `?AuthorizeSession@StandardCollectorService@@UEAAJAEBU_GUID@@@Z`
- size: `513`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010540`
- `0x180031db0`
- `0x180031fe4`
- `0x1800344b0`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x180034518`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003454d`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034518`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003454d`
- `KERNEL32!AcquireSRWLockShared` at `0x1800344ee`
- `KERNEL32!AcquireSRWLockShared` at `0x1800344ee`
- `KERNEL32!CloseHandle` at `0x180034649`
- `KERNEL32!CloseHandle` at `0x180034649`
- `ole32!StringFromGUID2` at `0x1800345f3`
- `ole32!StringFromGUID2` at `0x1800345f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034655`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034655`

## string_xrefs

- `0x180034617`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall StandardCollectorService::AuthorizeSession(RTL_SRWLOCK *this, const struct _GUID *a2)
{
  __int64 v4; // rbx
  RTL_SRWLOCK *v5; // rsi
  int UserTokenOfCaller; // esi
  __int64 v7; // rdi
  HANDLE v8; // rdi
  int IsAdministrator; // eax
  DiagHubCommon::LogStream *v10; // rsi
  _QWORD *pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-D8h] BYREF
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h]
  OLECHAR sz[112]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+120h] [rbp+20h] BYREF

  v4 = 0;
  v15 = 0;
  v5 = this + 11;
  AcquireSRWLockShared(this + 11);
  pExceptionObject = 0;
  std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
    &this[12],
    &pExceptionObject);
  if ( pExceptionObject == this[13].Ptr )
  {
    ReleaseSRWLockShared(v5);
    UserTokenOfCaller = -2147024809;
  }
  else
  {
    v7 = pExceptionObject[5];
    if ( v7 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 8LL))(pExceptionObject[5]);
      v4 = v7;
      v15 = v7;
    }
    ReleaseSRWLockShared(v5);
    Block = 0;
    hObject = 0;
    UserTokenOfCaller = anonymous_namespace_::GetUserTokenOfCaller(&Block, &hObject);
    v8 = hObject;
    if ( UserTokenOfCaller >= 0 )
    {
      IsAdministrator = anonymous_namespace_::QueryIsAdministrator(hObject);
      UserTokenOfCaller = IsAdministrator;
      if ( IsAdministrator >= 0 )
      {
        if ( IsAdministrator )
        {
          UserTokenOfCaller = -2147024891;
        }
        else
        {
          v17 = 0;
          UserTokenOfCaller = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v4)(
                                v4,
                                &GUID_136ebf68_b310_41fd_a41f_853cee6cc0da,
                                &v17);
          if ( UserTokenOfCaller >= 0 )
          {
            UserTokenOfCaller = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
            if ( UserTokenOfCaller >= 0 )
            {
              v10 = _logger;
              if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
              {
                if ( !StringFromGUID2(a2, sz, 39) )
                {
                  LODWORD(pExceptionObject) = -2147024882;
                  throw (long *)&pExceptionObject;
                }
                sz[39] = 0;
                sz[78] = 0;
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)v10 + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
                  L"Session '%s' authorized",
                  sz);
              }
              UserTokenOfCaller = 0;
            }
          }
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
    if ( v8 )
      CloseHandle(v8);
    free(Block);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)UserTokenOfCaller;
}

```

## disassembly

```asm
0x1800344b0  mov     [rsp-8+arg_10], rbx
0x1800344b5  push    rbp
0x1800344b6  push    rsi
0x1800344b7  push    rdi
0x1800344b8  push    r14
0x1800344ba  push    r15
0x1800344bc  lea     rbp, [rsp-30h]
0x1800344c1  sub     rsp, 130h
0x1800344c8  mov     rax, cs:__security_cookie
0x1800344cf  xor     rax, rsp
0x1800344d2  mov     [rbp+50h+var_28], rax
0x1800344d6  mov     r14, rdx
0x1800344d9  mov     rdi, rcx
0x1800344dc  xor     r15d, r15d
0x1800344df  mov     ebx, r15d
0x1800344e2  mov     [rsp+150h+var_118], rbx
0x1800344e7  lea     rsi, [rcx+58h]
0x1800344eb  mov     rcx, rsi; SRWLock
0x1800344ee  call    cs:__imp_AcquireSRWLockShared
0x1800344f4  mov     [rsp+150h+pExceptionObject], r15
0x1800344f9  lea     rcx, [rdi+60h]
0x1800344fd  mov     r8, r14
0x180034500  lea     rdx, [rsp+150h+pExceptionObject]
0x180034505  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18003450a  mov     rax, [rsp+150h+pExceptionObject]
0x18003450f  cmp     rax, [rdi+68h]
0x180034513  jnz     short loc_180034528
0x180034515  mov     rcx, rsi; SRWLock
0x180034518  call    cs:__imp_ReleaseSRWLockShared
0x18003451e  mov     esi, 80070057h
0x180034523  jmp     loc_18003465C
0x180034528  mov     rdi, [rax+28h]
0x18003452c  test    rdi, rdi
0x18003452f  jz      short loc_18003454A
0x180034531  mov     rax, [rdi]
0x180034534  mov     rcx, rdi
0x180034537  mov     rax, [rax+8]
0x18003453b  call    cs:__guard_dispatch_icall_fptr
0x180034541  nop
0x180034542  mov     rbx, rdi
0x180034545  mov     [rsp+150h+var_118], rbx
0x18003454a  mov     rcx, rsi; SRWLock
0x18003454d  call    cs:__imp_ReleaseSRWLockShared
0x180034553  mov     [rsp+150h+Block], r15
0x180034558  mov     [rsp+150h+hObject], r15
0x18003455d  lea     rdx, [rsp+150h+hObject]
0x180034562  lea     rcx, [rsp+150h+Block]
0x180034567  call    _anonymous_namespace___GetUserTokenOfCaller
0x18003456c  mov     esi, eax
0x18003456e  mov     rdi, [rsp+150h+hObject]
0x180034573  test    eax, eax
0x180034575  js      loc_180034641
0x18003457b  mov     rcx, rdi; ClientToken
0x18003457e  call    _anonymous_namespace___QueryIsAdministrator
0x180034583  mov     esi, eax
0x180034585  test    eax, eax
0x180034587  js      loc_180034641
0x18003458d  jz      short loc_180034599
0x18003458f  mov     esi, 80070005h
0x180034594  jmp     loc_180034641
0x180034599  mov     [rbp+50h+var_30], r15
0x18003459d  mov     rax, [rbx]
0x1800345a0  lea     r8, [rbp+50h+var_30]
0x1800345a4  lea     rdx, _GUID_136ebf68_b310_41fd_a41f_853cee6cc0da
0x1800345ab  mov     rcx, rbx
0x1800345ae  mov     rax, [rax]
0x1800345b1  call    cs:__guard_dispatch_icall_fptr
0x1800345b7  mov     esi, eax
0x1800345b9  test    eax, eax
0x1800345bb  js      short loc_18003462A
0x1800345bd  mov     rcx, [rbp+50h+var_30]
0x1800345c1  mov     rax, [rcx]
0x1800345c4  mov     rax, [rax+20h]
0x1800345c8  call    cs:__guard_dispatch_icall_fptr
0x1800345ce  mov     esi, eax
0x1800345d0  test    eax, eax
0x1800345d2  js      short loc_18003462A
0x1800345d4  mov     rsi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800345db  mov     rax, [rsi+40h]
0x1800345df  cmp     [rsi+38h], rax
0x1800345e3  jz      short loc_180034627
0x1800345e5  mov     r8d, 27h ; '''; cchMax
0x1800345eb  lea     rdx, [rsp+150h+sz]; lpsz
0x1800345f0  mov     rcx, r14; rguid
0x1800345f3  call    cs:__imp_StringFromGUID2
0x1800345f9  test    eax, eax
0x1800345fb  jz      loc_180034697
0x180034601  mov     [rbp+50h+var_C2], r15w
0x180034606  mov     [rbp+50h+var_74], r15w
0x18003460b  lea     r9, [rsp+150h+sz]
0x180034610  lea     r8, aSessionSAuthor; "Session '%s' authorized"
0x180034617  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003461e  lea     rcx, [rsi+38h]; this
0x180034622  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180034627  mov     esi, r15d
0x18003462a  mov     rcx, [rbp+50h+var_30]
0x18003462e  test    rcx, rcx
0x180034631  jz      short loc_180034641
0x180034633  mov     rax, [rcx]
0x180034636  mov     rax, [rax+10h]
0x18003463a  call    cs:__guard_dispatch_icall_fptr
0x180034640  nop
0x180034641  test    rdi, rdi
0x180034644  jz      short loc_180034650
0x180034646  mov     rcx, rdi; hObject
0x180034649  call    cs:__imp_CloseHandle
0x18003464f  nop
0x180034650  mov     rcx, [rsp+150h+Block]; Block
0x180034655  call    cs:__imp_free
0x18003465b  nop
0x18003465c  test    rbx, rbx
0x18003465f  jz      short loc_180034672
0x180034661  mov     rcx, [rbx]
0x180034664  mov     rax, [rcx+10h]
0x180034668  mov     rcx, rbx
0x18003466b  call    cs:__guard_dispatch_icall_fptr
0x180034671  nop
0x180034672  mov     eax, esi
0x180034674  mov     rcx, [rbp+50h+var_28]
0x180034678  xor     rcx, rsp; StackCookie
0x18003467b  call    __security_check_cookie
0x180034680  mov     rbx, [rsp+150h+arg_10]
0x180034688  add     rsp, 130h
0x18003468f  pop     r15
0x180034691  pop     r14
0x180034693  pop     rdi
0x180034694  pop     rsi
0x180034695  pop     rbp
0x180034696  retn
0x180034697  mov     dword ptr [rsp+150h+pExceptionObject], 8007000Eh
0x18003469f  lea     rdx, _TI1J; pThrowInfo
0x1800346a6  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800346ab  call    _CxxThrowException_0
```
