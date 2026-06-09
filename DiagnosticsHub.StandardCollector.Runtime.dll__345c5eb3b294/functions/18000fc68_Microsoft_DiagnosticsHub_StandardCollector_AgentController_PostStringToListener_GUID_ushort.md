# Microsoft::DiagnosticsHub::StandardCollector::AgentController::PostStringToListener(_GUID,ushort *)

- ea: `0x18000fc68`
- end: `0x18000fec4`
- name: `?PostStringToListener@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJU_GUID@@PEAG@Z`
- size: `604`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::AgentController *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004c20`

## callees

- `0x180008ea8`
- `0x18000fc68`
- `0x18003d864`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000fddd`
- `KERNEL32!LeaveCriticalSection` at `0x18000fde8`
- `KERNEL32!LeaveCriticalSection` at `0x18000fddd`
- `KERNEL32!LeaveCriticalSection` at `0x18000fde8`
- `KERNEL32!EnterCriticalSection` at `0x18000fcc1`
- `KERNEL32!EnterCriticalSection` at `0x18000fcc1`
- `ole32!StringFromGUID2` at `0x18000fd4c`
- `ole32!StringFromGUID2` at `0x18000fe1e`
- `ole32!StringFromGUID2` at `0x18000fd4c`
- `ole32!StringFromGUID2` at `0x18000fe1e`

## string_xrefs

- `0x18000fe45`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000fe3e`: `OnReceiveStringFromTool for agent %s failed. (%#08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::PostStringToListener(
        Microsoft::DiagnosticsHub::StandardCollector::AgentController *this,
        struct _GUID *a2,
        unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rcx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  const OLECHAR *v14; // rdx
  int v15; // edi
  int v16; // ebx
  DiagHubCommon::LogStream *v17; // rdi
  int v18; // [rsp+20h] [rbp-E0h]
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID *v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  char *v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[39]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v24; // [rsp+AEh] [rbp-52h]
  __int16 v25; // [rsp+FCh] [rbp-4h]

  if ( *((_BYTE *)this + 689) )
    return 3775987731LL;
  v22 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 280);
  v21 = (char *)this + 280;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 7);
  v8 = 0xCBF29CE484222325uLL;
  v9 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v9 = 0x100000001B3LL * (*((unsigned __int8 *)&a2->Data1 + i) ^ (unsigned __int64)v9);
  for ( j = 0; j < 8; ++j )
    v8 = 0x100000001B3LL * (a2->Data4[j] ^ (unsigned __int64)v8);
  v12 = *(_QWORD *)(std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                      (char *)this + 320,
                      v20,
                      a2,
                      v9 ^ v8)
                  + 8);
  if ( !v12 )
    v12 = *((_QWORD *)this + 41);
  if ( v12 == *((_QWORD *)this + 41) )
  {
    if ( !StringFromGUID2(a2, sz, 39) )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v24 = 0;
    v25 = 0;
    *(_OWORD *)v20 = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)v20,
      -518979578,
      sz,
      *((_WORD *)this + 336));
    v14 = L"<unknown error>";
    if ( v20[0] )
      v14 = (const OLECHAR *)v20[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v14, v13);
    v15 = (int)v20[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v20);
  }
  else
  {
    v15 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v12 + 32))(
            *(_QWORD *)(v12 + 32),
            &GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322,
            &v22);
    if ( v15 >= 0 )
    {
      LeaveCriticalSection(v7);
      v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v22 + 40LL))(v22, a3);
      if ( v16 < 0 )
      {
        v17 = _logger;
        if ( !StringFromGUID2(a2, sz, 39) )
        {
          pExceptionObject = -2147024882;
          throw (long *)&pExceptionObject;
        }
        _mm_lfence();
        v24 = 0;
        v25 = 0;
        v18 = v16;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)v17 + 112),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
          L"OnReceiveStringFromTool for agent %s failed. (%#08x)",
          sz,
          v18);
      }
      v15 = 0;
      goto LABEL_20;
    }
  }
  LeaveCriticalSection(v7);
LABEL_20:
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000fc68  push    rbp
0x18000fc6a  push    rbx
0x18000fc6b  push    rsi
0x18000fc6c  push    rdi
0x18000fc6d  push    r12
0x18000fc6f  push    r14
0x18000fc71  push    r15
0x18000fc73  lea     rbp, [rsp-50h]
0x18000fc78  sub     rsp, 150h
0x18000fc7f  mov     rax, cs:__security_cookie
0x18000fc86  xor     rax, rsp
0x18000fc89  mov     [rbp+80h+var_40], rax
0x18000fc8d  mov     r15, r8
0x18000fc90  mov     rsi, rdx
0x18000fc93  mov     rdi, rcx
0x18000fc96  mov     al, [rcx+2B1h]
0x18000fc9c  xor     r12d, r12d
0x18000fc9f  test    al, al
0x18000fca1  jz      short loc_18000FCAD
0x18000fca3  mov     eax, 0E1110013h
0x18000fca8  jmp     loc_18000FE72
0x18000fcad  mov     [rsp+180h+var_130], r12
0x18000fcb2  lea     rbx, [rcx+118h]
0x18000fcb9  mov     [rsp+180h+var_138], rbx
0x18000fcbe  mov     rcx, rbx; lpCriticalSection
0x18000fcc1  call    cs:__imp_EnterCriticalSection
0x18000fcc7  nop
0x18000fcc8  lea     r14, [rdi+140h]
0x18000fccf  mov     r9, 0CBF29CE484222325h
0x18000fcd9  mov     rdx, r9
0x18000fcdc  mov     rcx, r12
0x18000fcdf  mov     r8, 100000001B3h
0x18000fce9  movzx   eax, byte ptr [rsi+rcx]
0x18000fced  xor     rdx, rax
0x18000fcf0  imul    rdx, r8
0x18000fcf4  inc     rcx
0x18000fcf7  cmp     rcx, 8
0x18000fcfb  jb      short loc_18000FCE9
0x18000fcfd  mov     rcx, r12
0x18000fd00  movzx   eax, byte ptr [rsi+rcx+8]
0x18000fd05  xor     r9, rax
0x18000fd08  imul    r9, r8
0x18000fd0c  inc     rcx
0x18000fd0f  cmp     rcx, 8
0x18000fd13  jb      short loc_18000FD00
0x18000fd15  xor     r9, rdx
0x18000fd18  mov     r8, rsi
0x18000fd1b  lea     rdx, [rsp+180h+var_148]
0x18000fd20  mov     rcx, r14
0x18000fd23  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x18000fd28  mov     rcx, [rax+8]
0x18000fd2c  test    rcx, rcx
0x18000fd2f  jnz     short loc_18000FD35
0x18000fd31  mov     rcx, [r14+8]
0x18000fd35  cmp     rcx, [rdi+148h]
0x18000fd3c  jnz     short loc_18000FDB8
0x18000fd3e  mov     r8d, 27h ; '''; cchMax
0x18000fd44  lea     rdx, [rsp+180h+sz]; lpsz
0x18000fd49  mov     rcx, rsi; rguid
0x18000fd4c  call    cs:__imp_StringFromGUID2
0x18000fd52  test    eax, eax
0x18000fd54  jz      loc_18000FEAA
0x18000fd5a  mov     [rbp+80h+var_D2], r12w
0x18000fd5f  mov     [rbp+80h+var_84], r12w
0x18000fd64  xorps   xmm0, xmm0
0x18000fd67  movups  xmmword ptr [rsp+180h+var_148], xmm0
0x18000fd6c  movzx   r9d, word ptr [rdi+2A0h]; unsigned __int16
0x18000fd74  lea     r8, [rsp+180h+sz]; unsigned __int16 *
0x18000fd79  mov     edx, 0E1110006h; int
0x18000fd7e  lea     rcx, [rsp+180h+var_148]; this
0x18000fd83  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x18000fd88  nop
0x18000fd89  lea     rdx, aUnknownError; "<unknown error>"
0x18000fd90  mov     rax, [rsp+180h+var_148]
0x18000fd95  test    rax, rax
0x18000fd98  cmovnz  rdx, rax; struct _GUID *
0x18000fd9c  lea     rcx, IID_ICollectionSession; this
0x18000fda3  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18000fda8  mov     edi, dword ptr [rsp+180h+var_148+8]
0x18000fdac  lea     rcx, [rsp+180h+var_148]; this
0x18000fdb1  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18000fdb6  jmp     short loc_18000FDDA
0x18000fdb8  mov     rcx, [rcx+20h]
0x18000fdbc  mov     rax, [rcx]
0x18000fdbf  lea     r8, [rsp+180h+var_130]
0x18000fdc4  lea     rdx, _GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322
0x18000fdcb  mov     rax, [rax]
0x18000fdce  call    cs:__guard_dispatch_icall_fptr
0x18000fdd4  mov     edi, eax
0x18000fdd6  test    eax, eax
0x18000fdd8  jns     short loc_18000FDE5
0x18000fdda  mov     rcx, rbx; lpCriticalSection
0x18000fddd  call    cs:__imp_LeaveCriticalSection
0x18000fde3  jmp     short loc_18000FE58
0x18000fde5  mov     rcx, rbx; lpCriticalSection
0x18000fde8  call    cs:__imp_LeaveCriticalSection
0x18000fdee  mov     rcx, [rsp+180h+var_130]
0x18000fdf3  mov     rax, [rcx]
0x18000fdf6  mov     rdx, r15
0x18000fdf9  mov     rax, [rax+28h]
0x18000fdfd  call    cs:__guard_dispatch_icall_fptr
0x18000fe03  mov     ebx, eax
0x18000fe05  test    eax, eax
0x18000fe07  jns     short loc_18000FE55
0x18000fe09  mov     rdi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000fe10  mov     r8d, 27h ; '''; cchMax
0x18000fe16  lea     rdx, [rsp+180h+sz]; lpsz
0x18000fe1b  mov     rcx, rsi; rguid
0x18000fe1e  call    cs:__imp_StringFromGUID2
0x18000fe24  test    eax, eax
0x18000fe26  jz      short loc_18000FE90
0x18000fe28  lfence
0x18000fe2b  mov     [rbp+80h+var_D2], r12w
0x18000fe30  mov     [rbp+80h+var_84], r12w
0x18000fe35  mov     [rsp+180h+var_160], ebx
0x18000fe39  lea     r9, [rsp+180h+sz]
0x18000fe3e  lea     r8, aOnreceivestrin; "OnReceiveStringFromTool for agent %s fa"...
0x18000fe45  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000fe4c  lea     rcx, [rdi+70h]; this
0x18000fe50  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000fe55  mov     edi, r12d
0x18000fe58  mov     rcx, [rsp+180h+var_130]
0x18000fe5d  test    rcx, rcx
0x18000fe60  jz      short loc_18000FE70
0x18000fe62  mov     rdx, [rcx]
0x18000fe65  mov     rax, [rdx+10h]
0x18000fe69  call    cs:__guard_dispatch_icall_fptr
0x18000fe6f  nop
0x18000fe70  mov     eax, edi
0x18000fe72  mov     rcx, [rbp+80h+var_40]
0x18000fe76  xor     rcx, rsp; StackCookie
0x18000fe79  call    __security_check_cookie
0x18000fe7e  add     rsp, 150h
0x18000fe85  pop     r15
0x18000fe87  pop     r14
0x18000fe89  pop     r12
0x18000fe8b  pop     rdi
0x18000fe8c  pop     rsi
0x18000fe8d  pop     rbx
0x18000fe8e  pop     rbp
0x18000fe8f  retn
0x18000fe90  mov     [rsp+180h+pExceptionObject], 8007000Eh
0x18000fe98  lea     rdx, _TI1J; pThrowInfo
0x18000fe9f  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000fea4  call    _CxxThrowException_0
0x18000feaa  mov     [rsp+180h+pExceptionObject], 8007000Eh
0x18000feb2  lea     rdx, _TI1J; pThrowInfo
0x18000feb9  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000febe  call    _CxxThrowException_0
```
