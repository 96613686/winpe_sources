# Microsoft::DiagnosticsHub::StandardCollector::AgentController::PostBytesToListener(_GUID,CollectorByteMessage const *)

- ea: `0x18000fec4`
- end: `0x180010120`
- name: `?PostBytesToListener@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJU_GUID@@PEBUCollectorByteMessage@@@Z`
- size: `604`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::AgentController *__hidden this, struct _GUID *__struct_ptr, const struct CollectorByteMessage *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004c50`

## callees

- `0x180008ea8`
- `0x18000fec4`
- `0x18003d864`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180010039`
- `KERNEL32!LeaveCriticalSection` at `0x180010044`
- `KERNEL32!LeaveCriticalSection` at `0x180010039`
- `KERNEL32!LeaveCriticalSection` at `0x180010044`
- `KERNEL32!EnterCriticalSection` at `0x18000ff1d`
- `KERNEL32!EnterCriticalSection` at `0x18000ff1d`
- `ole32!StringFromGUID2` at `0x18000ffa8`
- `ole32!StringFromGUID2` at `0x18001007a`
- `ole32!StringFromGUID2` at `0x18000ffa8`
- `ole32!StringFromGUID2` at `0x18001007a`

## string_xrefs

- `0x1800100a1`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18001009a`: `OnReceiveBytesFromTool for agent %s failed. (%#08x)`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::PostBytesToListener(
        Microsoft::DiagnosticsHub::StandardCollector::AgentController *this,
        struct _GUID *a2,
        const struct CollectorByteMessage *a3)
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
      v16 = (*(__int64 (__fastcall **)(__int64, const struct CollectorByteMessage *))(*(_QWORD *)v22 + 48LL))(v22, a3);
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
          L"OnReceiveBytesFromTool for agent %s failed. (%#08x)",
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
0x18000fec4  push    rbp
0x18000fec6  push    rbx
0x18000fec7  push    rsi
0x18000fec8  push    rdi
0x18000fec9  push    r12
0x18000fecb  push    r14
0x18000fecd  push    r15
0x18000fecf  lea     rbp, [rsp-50h]
0x18000fed4  sub     rsp, 150h
0x18000fedb  mov     rax, cs:__security_cookie
0x18000fee2  xor     rax, rsp
0x18000fee5  mov     [rbp+80h+var_40], rax
0x18000fee9  mov     r15, r8
0x18000feec  mov     rsi, rdx
0x18000feef  mov     rdi, rcx
0x18000fef2  mov     al, [rcx+2B1h]
0x18000fef8  xor     r12d, r12d
0x18000fefb  test    al, al
0x18000fefd  jz      short loc_18000FF09
0x18000feff  mov     eax, 0E1110013h
0x18000ff04  jmp     loc_1800100CE
0x18000ff09  mov     [rsp+180h+var_130], r12
0x18000ff0e  lea     rbx, [rcx+118h]
0x18000ff15  mov     [rsp+180h+var_138], rbx
0x18000ff1a  mov     rcx, rbx; lpCriticalSection
0x18000ff1d  call    cs:__imp_EnterCriticalSection
0x18000ff23  nop
0x18000ff24  lea     r14, [rdi+140h]
0x18000ff2b  mov     r9, 0CBF29CE484222325h
0x18000ff35  mov     rdx, r9
0x18000ff38  mov     rcx, r12
0x18000ff3b  mov     r8, 100000001B3h
0x18000ff45  movzx   eax, byte ptr [rsi+rcx]
0x18000ff49  xor     rdx, rax
0x18000ff4c  imul    rdx, r8
0x18000ff50  inc     rcx
0x18000ff53  cmp     rcx, 8
0x18000ff57  jb      short loc_18000FF45
0x18000ff59  mov     rcx, r12
0x18000ff5c  movzx   eax, byte ptr [rsi+rcx+8]
0x18000ff61  xor     r9, rax
0x18000ff64  imul    r9, r8
0x18000ff68  inc     rcx
0x18000ff6b  cmp     rcx, 8
0x18000ff6f  jb      short loc_18000FF5C
0x18000ff71  xor     r9, rdx
0x18000ff74  mov     r8, rsi
0x18000ff77  lea     rdx, [rsp+180h+var_148]
0x18000ff7c  mov     rcx, r14
0x18000ff7f  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x18000ff84  mov     rcx, [rax+8]
0x18000ff88  test    rcx, rcx
0x18000ff8b  jnz     short loc_18000FF91
0x18000ff8d  mov     rcx, [r14+8]
0x18000ff91  cmp     rcx, [rdi+148h]
0x18000ff98  jnz     short loc_180010014
0x18000ff9a  mov     r8d, 27h ; '''; cchMax
0x18000ffa0  lea     rdx, [rsp+180h+sz]; lpsz
0x18000ffa5  mov     rcx, rsi; rguid
0x18000ffa8  call    cs:__imp_StringFromGUID2
0x18000ffae  test    eax, eax
0x18000ffb0  jz      loc_180010106
0x18000ffb6  mov     [rbp+80h+var_D2], r12w
0x18000ffbb  mov     [rbp+80h+var_84], r12w
0x18000ffc0  xorps   xmm0, xmm0
0x18000ffc3  movups  xmmword ptr [rsp+180h+var_148], xmm0
0x18000ffc8  movzx   r9d, word ptr [rdi+2A0h]; unsigned __int16
0x18000ffd0  lea     r8, [rsp+180h+sz]; unsigned __int16 *
0x18000ffd5  mov     edx, 0E1110006h; int
0x18000ffda  lea     rcx, [rsp+180h+var_148]; this
0x18000ffdf  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x18000ffe4  nop
0x18000ffe5  lea     rdx, aUnknownError; "<unknown error>"
0x18000ffec  mov     rax, [rsp+180h+var_148]
0x18000fff1  test    rax, rax
0x18000fff4  cmovnz  rdx, rax; struct _GUID *
0x18000fff8  lea     rcx, IID_ICollectionSession; this
0x18000ffff  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180010004  mov     edi, dword ptr [rsp+180h+var_148+8]
0x180010008  lea     rcx, [rsp+180h+var_148]; this
0x18001000d  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180010012  jmp     short loc_180010036
0x180010014  mov     rcx, [rcx+20h]
0x180010018  mov     rax, [rcx]
0x18001001b  lea     r8, [rsp+180h+var_130]
0x180010020  lea     rdx, _GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322
0x180010027  mov     rax, [rax]
0x18001002a  call    cs:__guard_dispatch_icall_fptr
0x180010030  mov     edi, eax
0x180010032  test    eax, eax
0x180010034  jns     short loc_180010041
0x180010036  mov     rcx, rbx; lpCriticalSection
0x180010039  call    cs:__imp_LeaveCriticalSection
0x18001003f  jmp     short loc_1800100B4
0x180010041  mov     rcx, rbx; lpCriticalSection
0x180010044  call    cs:__imp_LeaveCriticalSection
0x18001004a  mov     rcx, [rsp+180h+var_130]
0x18001004f  mov     rax, [rcx]
0x180010052  mov     rdx, r15
0x180010055  mov     rax, [rax+30h]
0x180010059  call    cs:__guard_dispatch_icall_fptr
0x18001005f  mov     ebx, eax
0x180010061  test    eax, eax
0x180010063  jns     short loc_1800100B1
0x180010065  mov     rdi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001006c  mov     r8d, 27h ; '''; cchMax
0x180010072  lea     rdx, [rsp+180h+sz]; lpsz
0x180010077  mov     rcx, rsi; rguid
0x18001007a  call    cs:__imp_StringFromGUID2
0x180010080  test    eax, eax
0x180010082  jz      short loc_1800100EC
0x180010084  lfence
0x180010087  mov     [rbp+80h+var_D2], r12w
0x18001008c  mov     [rbp+80h+var_84], r12w
0x180010091  mov     [rsp+180h+var_160], ebx
0x180010095  lea     r9, [rsp+180h+sz]
0x18001009a  lea     r8, aOnreceivebytes; "OnReceiveBytesFromTool for agent %s fai"...
0x1800100a1  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800100a8  lea     rcx, [rdi+70h]; this
0x1800100ac  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800100b1  mov     edi, r12d
0x1800100b4  mov     rcx, [rsp+180h+var_130]
0x1800100b9  test    rcx, rcx
0x1800100bc  jz      short loc_1800100CC
0x1800100be  mov     rdx, [rcx]
0x1800100c1  mov     rax, [rdx+10h]
0x1800100c5  call    cs:__guard_dispatch_icall_fptr
0x1800100cb  nop
0x1800100cc  mov     eax, edi
0x1800100ce  mov     rcx, [rbp+80h+var_40]
0x1800100d2  xor     rcx, rsp; StackCookie
0x1800100d5  call    __security_check_cookie
0x1800100da  add     rsp, 150h
0x1800100e1  pop     r15
0x1800100e3  pop     r14
0x1800100e5  pop     r12
0x1800100e7  pop     rdi
0x1800100e8  pop     rsi
0x1800100e9  pop     rbx
0x1800100ea  pop     rbp
0x1800100eb  retn
0x1800100ec  mov     [rsp+180h+pExceptionObject], 8007000Eh
0x1800100f4  lea     rdx, _TI1J; pThrowInfo
0x1800100fb  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180010100  call    _CxxThrowException_0
0x180010106  mov     [rsp+180h+pExceptionObject], 8007000Eh
0x18001010e  lea     rdx, _TI1J; pThrowInfo
0x180010115  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18001011a  call    _CxxThrowException_0
```
