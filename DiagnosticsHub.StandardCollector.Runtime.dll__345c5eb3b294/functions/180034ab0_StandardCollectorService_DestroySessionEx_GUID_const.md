# StandardCollectorService::DestroySessionEx(_GUID const &)

- ea: `0x180034ab0`
- end: `0x180034ea5`
- name: `?DestroySessionEx@StandardCollectorService@@QEAAJAEBU_GUID@@@Z`
- size: `1013`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180034eb0`

## callees

- `0x180010540`
- `0x1800317d8`
- `0x180033d7c`
- `0x180034ab0`
- `0x18003d864`
- `0x180049b50`
- `0x18004a078`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180034d41`
- `KERNEL32!SetEvent` at `0x180034e00`
- `KERNEL32!SetEvent` at `0x180034d41`
- `KERNEL32!SetEvent` at `0x180034e00`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034b73`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034c4e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034b73`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034c4e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034b4c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034b4c`
- `ole32!CoUninitialize` at `0x180034d2d`
- `ole32!CoUninitialize` at `0x180034dec`
- `ole32!CoUninitialize` at `0x180034d2d`
- `ole32!CoUninitialize` at `0x180034dec`
- `ole32!CoInitializeEx` at `0x180034c68`
- `ole32!CoInitializeEx` at `0x180034c68`
- `ole32!StringFromGUID2` at `0x180034b10`
- `ole32!StringFromGUID2` at `0x180034e3c`
- `ole32!StringFromGUID2` at `0x180034b10`
- `ole32!StringFromGUID2` at `0x180034e3c`
- `ole32!CoDisconnectObject` at `0x180034c8a`
- `ole32!CoDisconnectObject` at `0x180034c8a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034da5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034da5`

## string_xrefs

- `0x180034b35`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180034e5d`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StandardCollectorService::DestroySessionEx(RTL_SRWLOCK *this, const struct _GUID *a2)
{
  DiagHubCommon::LogStream *v4; // rbx
  _QWORD *v5; // rbx
  HRESULT v6; // r14d
  LPUNKNOWN v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int64 i; // rdx
  unsigned __int64 j; // rdx
  __int64 v12; // rcx
  _QWORD *Ptr; // rdx
  PVOID v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rbx
  char v17; // di
  void *v18; // rcx
  volatile signed __int32 *v19; // rbx
  DiagHubCommon::LogStream *v21; // rbx
  char v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+28h] [rbp-D8h]
  OLECHAR sz[39]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v25; // [rsp+7Eh] [rbp-82h]
  __int16 v26; // [rsp+CCh] [rbp-34h]
  LPUNKNOWN pUnk[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v28; // [rsp+120h] [rbp+20h]
  int pExceptionObject; // [rsp+130h] [rbp+30h] BYREF
  void *Block; // [rsp+138h] [rbp+38h] BYREF

  *(_OWORD *)pUnk = 0;
  v28 = 0;
  v4 = _logger;
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    if ( !StringFromGUID2(a2, sz, 39) )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v25 = 0;
    v26 = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)v4 + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Destroying session '%s'",
      sz);
  }
  AcquireSRWLockExclusive(this + 12);
  Block = 0;
  std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
    &this[13],
    &Block);
  v5 = Block;
  if ( Block == this[14].Ptr )
  {
    ReleaseSRWLockExclusive(this + 12);
    v6 = -2147024809;
    v7 = pUnk[1];
    goto LABEL_31;
  }
  StandardCollectorService::SessionContainer::operator=(pUnk, (char *)Block + 32);
  v8 = 0xCBF29CE484222325uLL;
  v9 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v9 = 0x100000001B3LL * (*((unsigned __int8 *)v5 + i + 16) ^ (unsigned __int64)v9);
  for ( j = 0; j < 8; ++j )
    v8 = 0x100000001B3LL * (*((unsigned __int8 *)v5 + j + 24) ^ (unsigned __int64)v8);
  v12 = 2 * ((__int64)this[19].Ptr & (v9 ^ v8));
  Ptr = this[16].Ptr;
  if ( (_QWORD *)Ptr[v12 + 1] == v5 )
  {
    if ( (_QWORD *)Ptr[v12] == v5 )
    {
      v14 = this[14].Ptr;
      Ptr[v12] = v14;
    }
    else
    {
      v14 = (PVOID)v5[1];
    }
    Ptr[v12 + 1] = v14;
  }
  else if ( (_QWORD *)Ptr[v12] == v5 )
  {
    Ptr[v12] = *v5;
  }
  v15 = *v5;
  --this[15].Ptr;
  *(_QWORD *)v5[1] = v15;
  *(_QWORD *)(v15 + 8) = v5[1];
  StandardCollectorService::SessionContainer::~SessionContainer((StandardCollectorService::SessionContainer *)(v5 + 4));
  operator delete(v5);
  ReleaseSRWLockExclusive(this + 12);
  v16 = v28 + 16;
  v23 = v28 + 16;
  v17 = 0;
  v6 = CoInitializeEx(0, 0);
  v7 = pUnk[1];
  if ( v6 < 0 )
    goto LABEL_27;
  v17 = 1;
  v22 = 1;
  CoDisconnectObject(pUnk[1], 0);
  pExceptionObject = 0;
  ((void (__fastcall *)(LPUNKNOWN, int *))v7->lpVtbl[4].AddRef)(v7, &pExceptionObject);
  if ( (unsigned int)(pExceptionObject - 2) <= 1 )
  {
    v18 = 0;
    Block = 0;
    if ( v7 )
    {
      if ( ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, void **))v7->lpVtbl->QueryInterface)(
             v7,
             &GUID_136ebf68_b310_41fd_a41f_853cee6cc0da,
             &Block) >= 0 )
      {
        v18 = Block;
      }
      else
      {
        v18 = 0;
        Block = 0;
      }
    }
    if ( v18 )
    {
      v6 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v18 + 40LL))(v18, 0);
      if ( v6 < 0 )
      {
        if ( Block )
          (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
LABEL_27:
        if ( v17 )
          CoUninitialize();
        if ( *(int *)(v16 + 8) >= 0 )
          SetEvent(*(HANDLE *)v16);
        goto LABEL_31;
      }
      v18 = Block;
    }
    if ( v18 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  CoUninitialize();
  if ( *(int *)(v16 + 8) >= 0 )
    SetEvent(*(HANDLE *)v16);
  (*(void (__fastcall **)(PVOID, const struct _GUID *))(*(_QWORD *)this[22].Ptr + 32LL))(this[22].Ptr, a2);
  v21 = _logger;
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    if ( !StringFromGUID2(a2, sz, 39) )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v25 = 0;
    v26 = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)v21 + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Session '%s' has been destroyed",
      sz,
      v22,
      v23);
  }
  v6 = 0;
LABEL_31:
  v19 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  if ( v7 )
    ((void (__fastcall *)(LPUNKNOWN))v7->lpVtbl->Release)(v7);
  free(pUnk[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180034ab0  mov     [rsp-8+arg_10], rbx
0x180034ab5  push    rbp
0x180034ab6  push    rsi
0x180034ab7  push    rdi
0x180034ab8  push    r12
0x180034aba  push    r13
0x180034abc  push    r14
0x180034abe  push    r15
0x180034ac0  lea     rbp, [rsp-50h]
0x180034ac5  sub     rsp, 150h
0x180034acc  mov     rax, cs:__security_cookie
0x180034ad3  xor     rax, rsp
0x180034ad6  mov     [rbp+80h+var_40], rax
0x180034ada  mov     r12, rdx
0x180034add  mov     r15, rcx
0x180034ae0  xorps   xmm0, xmm0
0x180034ae3  movdqu  xmmword ptr [rbp+80h+pUnk], xmm0
0x180034ae8  xorps   xmm1, xmm1
0x180034aeb  movdqu  [rbp+80h+var_60], xmm1
0x180034af0  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180034af7  mov     rax, [rbx+40h]
0x180034afb  xor     r13d, r13d
0x180034afe  cmp     [rbx+38h], rax
0x180034b02  jz      short loc_180034B45
0x180034b04  lea     r8d, [r13+27h]; cchMax
0x180034b08  lea     rdx, [rsp+180h+sz]; lpsz
0x180034b0d  mov     rcx, r12; rguid
0x180034b10  call    cs:__imp_StringFromGUID2
0x180034b16  test    eax, eax
0x180034b18  jz      loc_180034E8D
0x180034b1e  mov     [rsp+180h+var_102], r13w
0x180034b24  mov     [rbp+80h+var_B4], r13w
0x180034b29  lea     r9, [rsp+180h+sz]
0x180034b2e  lea     r8, aDestroyingSess; "Destroying session '%s'"
0x180034b35  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180034b3c  lea     rcx, [rbx+38h]; this
0x180034b40  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180034b45  lea     rdi, [r15+60h]
0x180034b49  mov     rcx, rdi; SRWLock
0x180034b4c  call    cs:__imp_AcquireSRWLockExclusive
0x180034b52  mov     [rbp+80h+Block], r13
0x180034b56  lea     rcx, [r15+68h]
0x180034b5a  mov     r8, r12
0x180034b5d  lea     rdx, [rbp+80h+Block]
0x180034b61  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x180034b66  mov     rbx, [rbp+80h+Block]
0x180034b6a  cmp     rbx, [r15+70h]
0x180034b6e  jnz     short loc_180034B88
0x180034b70  mov     rcx, rdi; SRWLock
0x180034b73  call    cs:__imp_ReleaseSRWLockExclusive
0x180034b79  mov     r14d, 80070057h
0x180034b7f  mov     rsi, [rbp+80h+pUnk+8]
0x180034b83  jmp     loc_180034D48
0x180034b88  lea     rdx, [rbx+20h]
0x180034b8c  lea     rcx, [rbp+80h+pUnk]
0x180034b90  call    ??4SessionContainer@StandardCollectorService@@QEAAAEAU01@$$QEAU01@@Z; StandardCollectorService::SessionContainer::operator=(StandardCollectorService::SessionContainer &&)
0x180034b95  mov     rcx, 0CBF29CE484222325h
0x180034b9f  mov     r8, rcx
0x180034ba2  mov     rdx, r13
0x180034ba5  mov     r9, 100000001B3h
0x180034baf  movzx   eax, byte ptr [rdx+rbx+10h]
0x180034bb4  xor     r8, rax
0x180034bb7  imul    r8, r9
0x180034bbb  inc     rdx
0x180034bbe  cmp     rdx, 8
0x180034bc2  jb      short loc_180034BAF
0x180034bc4  mov     rdx, r13
0x180034bc7  movzx   eax, byte ptr [rdx+rbx+18h]
0x180034bcc  xor     rcx, rax
0x180034bcf  imul    rcx, r9
0x180034bd3  inc     rdx
0x180034bd6  cmp     rdx, 8
0x180034bda  jb      short loc_180034BC7
0x180034bdc  xor     rcx, r8
0x180034bdf  and     rcx, [r15+98h]
0x180034be6  add     rcx, rcx
0x180034be9  mov     rdx, [r15+80h]
0x180034bf0  cmp     [rdx+rcx*8+8], rbx
0x180034bf5  jnz     short loc_180034C12
0x180034bf7  cmp     [rdx+rcx*8], rbx
0x180034bfb  jnz     short loc_180034C07
0x180034bfd  mov     rax, [r15+70h]
0x180034c01  mov     [rdx+rcx*8], rax
0x180034c05  jmp     short loc_180034C0B
0x180034c07  mov     rax, [rbx+8]
0x180034c0b  mov     [rdx+rcx*8+8], rax
0x180034c10  jmp     short loc_180034C1F
0x180034c12  cmp     [rdx+rcx*8], rbx
0x180034c16  jnz     short loc_180034C1F
0x180034c18  mov     rax, [rbx]
0x180034c1b  mov     [rdx+rcx*8], rax
0x180034c1f  mov     rdx, [rbx]
0x180034c22  dec     qword ptr [r15+78h]
0x180034c26  mov     rax, [rbx+8]
0x180034c2a  mov     [rax], rdx
0x180034c2d  mov     rax, [rbx+8]
0x180034c31  mov     [rdx+8], rax
0x180034c35  lea     rcx, [rbx+20h]; this
0x180034c39  call    ??1SessionContainer@StandardCollectorService@@QEAA@XZ; StandardCollectorService::SessionContainer::~SessionContainer(void)
0x180034c3e  mov     edx, 40h ; '@'
0x180034c43  mov     rcx, rbx; Block
0x180034c46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034c4b  mov     rcx, rdi; SRWLock
0x180034c4e  call    cs:__imp_ReleaseSRWLockExclusive
0x180034c54  mov     rbx, qword ptr [rbp+80h+var_60]
0x180034c58  add     rbx, 10h
0x180034c5c  mov     [rsp+180h+var_158], rbx
0x180034c61  mov     dil, r13b
0x180034c64  xor     edx, edx; dwCoInit
0x180034c66  xor     ecx, ecx; pvReserved
0x180034c68  call    cs:__imp_CoInitializeEx
0x180034c6e  mov     r14d, eax
0x180034c71  mov     rsi, [rbp+80h+pUnk+8]
0x180034c75  test    eax, eax
0x180034c77  js      loc_180034D28
0x180034c7d  mov     dil, 1
0x180034c80  mov     [rsp+180h+var_160], dil
0x180034c85  xor     edx, edx; dwReserved
0x180034c87  mov     rcx, rsi; pUnk
0x180034c8a  call    cs:__imp_CoDisconnectObject
0x180034c90  mov     [rbp+80h+pExceptionObject], r13d
0x180034c94  mov     rax, [rsi]
0x180034c97  lea     rdx, [rbp+80h+pExceptionObject]
0x180034c9b  mov     rcx, rsi
0x180034c9e  mov     rax, [rax+68h]
0x180034ca2  call    cs:__guard_dispatch_icall_fptr
0x180034ca8  mov     eax, [rbp+80h+pExceptionObject]
0x180034cab  add     eax, 0FFFFFFFEh
0x180034cae  cmp     eax, 1
0x180034cb1  ja      loc_180034DEC
0x180034cb7  mov     rcx, r13
0x180034cba  mov     [rbp+80h+Block], rcx
0x180034cbe  test    rsi, rsi
0x180034cc1  jz      short loc_180034CEE
0x180034cc3  mov     rax, [rsi]
0x180034cc6  lea     r8, [rbp+80h+Block]
0x180034cca  lea     rdx, _GUID_136ebf68_b310_41fd_a41f_853cee6cc0da
0x180034cd1  mov     rcx, rsi
0x180034cd4  mov     rax, [rax]
0x180034cd7  call    cs:__guard_dispatch_icall_fptr
0x180034cdd  test    eax, eax
0x180034cdf  jns     short loc_180034CEA
0x180034ce1  mov     rcx, r13
0x180034ce4  mov     [rbp+80h+Block], rcx
0x180034ce8  jmp     short loc_180034CEE
0x180034cea  mov     rcx, [rbp+80h+Block]
0x180034cee  test    rcx, rcx
0x180034cf1  jz      loc_180034DD9
0x180034cf7  mov     rax, [rcx]
0x180034cfa  xor     edx, edx
0x180034cfc  mov     rax, [rax+28h]
0x180034d00  call    cs:__guard_dispatch_icall_fptr
0x180034d06  mov     r14d, eax
0x180034d09  test    eax, eax
0x180034d0b  jns     loc_180034DD5
0x180034d11  mov     rcx, [rbp+80h+Block]
0x180034d15  test    rcx, rcx
0x180034d18  jz      short loc_180034D28
0x180034d1a  mov     rax, [rcx]
0x180034d1d  mov     rax, [rax+10h]
0x180034d21  call    cs:__guard_dispatch_icall_fptr
0x180034d27  nop
0x180034d28  test    dil, dil
0x180034d2b  jz      short loc_180034D34
0x180034d2d  call    cs:__imp_CoUninitialize
0x180034d33  nop
0x180034d34  mov     eax, [rbx+8]
0x180034d37  shr     eax, 1Fh
0x180034d3a  test    al, al
0x180034d3c  jnz     short loc_180034D48
0x180034d3e  mov     rcx, [rbx]; hEvent
0x180034d41  call    cs:__imp_SetEvent
0x180034d47  nop
0x180034d48  mov     rbx, qword ptr [rbp+80h+var_60+8]
0x180034d4c  test    rbx, rbx
0x180034d4f  jz      short loc_180034D8B
0x180034d51  or      eax, 0FFFFFFFFh
0x180034d54  lock xadd [rbx+8], eax
0x180034d59  cmp     eax, 1
0x180034d5c  jnz     short loc_180034D8B
0x180034d5e  mov     rax, [rbx]
0x180034d61  mov     rcx, rbx
0x180034d64  mov     rax, [rax]
0x180034d67  call    cs:__guard_dispatch_icall_fptr
0x180034d6d  or      eax, 0FFFFFFFFh
0x180034d70  lock xadd [rbx+0Ch], eax
0x180034d75  cmp     eax, 1
0x180034d78  jnz     short loc_180034D8B
0x180034d7a  mov     rax, [rbx]
0x180034d7d  mov     rcx, rbx
0x180034d80  mov     rax, [rax+8]
0x180034d84  call    cs:__guard_dispatch_icall_fptr
0x180034d8a  nop
0x180034d8b  test    rsi, rsi
0x180034d8e  jz      short loc_180034DA1
0x180034d90  mov     rdx, [rsi]
0x180034d93  mov     rcx, rsi
0x180034d96  mov     rax, [rdx+10h]
0x180034d9a  call    cs:__guard_dispatch_icall_fptr
0x180034da0  nop
0x180034da1  mov     rcx, [rbp+80h+pUnk]; Block
0x180034da5  call    cs:__imp_free
0x180034dab  mov     eax, r14d
0x180034dae  mov     rcx, [rbp+80h+var_40]
0x180034db2  xor     rcx, rsp; StackCookie
0x180034db5  call    __security_check_cookie
0x180034dba  mov     rbx, [rsp+180h+arg_10]
0x180034dc2  add     rsp, 150h
0x180034dc9  pop     r15
0x180034dcb  pop     r14
0x180034dcd  pop     r13
0x180034dcf  pop     r12
0x180034dd1  pop     rdi
0x180034dd2  pop     rsi
0x180034dd3  pop     rbp
0x180034dd4  retn
0x180034dd5  mov     rcx, [rbp+80h+Block]
0x180034dd9  test    rcx, rcx
0x180034ddc  jz      short loc_180034DEC
0x180034dde  mov     rax, [rcx]
0x180034de1  mov     rax, [rax+10h]
0x180034de5  call    cs:__guard_dispatch_icall_fptr
0x180034deb  nop
0x180034dec  call    cs:__imp_CoUninitialize
0x180034df2  nop
0x180034df3  mov     eax, [rbx+8]
0x180034df6  shr     eax, 1Fh
0x180034df9  test    al, al
0x180034dfb  jnz     short loc_180034E06
0x180034dfd  mov     rcx, [rbx]; hEvent
0x180034e00  call    cs:__imp_SetEvent
0x180034e06  mov     rcx, [r15+0B0h]
0x180034e0d  mov     rax, [rcx]
0x180034e10  mov     rdx, r12
0x180034e13  mov     rax, [rax+20h]
0x180034e17  call    cs:__guard_dispatch_icall_fptr
0x180034e1d  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180034e24  mov     rax, [rbx+40h]
0x180034e28  cmp     [rbx+38h], rax
0x180034e2c  jz      short loc_180034E6D
0x180034e2e  mov     r8d, 27h ; '''; cchMax
0x180034e34  lea     rdx, [rsp+180h+sz]; lpsz
0x180034e39  mov     rcx, r12; rguid
0x180034e3c  call    cs:__imp_StringFromGUID2
0x180034e42  test    eax, eax
0x180034e44  jz      short loc_180034E75
0x180034e46  mov     [rsp+180h+var_102], r13w
0x180034e4c  mov     [rbp+80h+var_B4], r13w
0x180034e51  lea     r9, [rsp+180h+sz]
0x180034e56  lea     r8, aSessionSHasBee; "Session '%s' has been destroyed"
0x180034e5d  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180034e64  lea     rcx, [rbx+38h]; this
0x180034e68  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180034e6d  mov     r14d, r13d
0x180034e70  jmp     loc_180034D48
0x180034e75  mov     [rbp+80h+pExceptionObject], 8007000Eh
0x180034e7c  lea     rdx, _TI1J; pThrowInfo
0x180034e83  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180034e87  call    _CxxThrowException_0
0x180034e8d  mov     [rbp+80h+pExceptionObject], 8007000Eh
0x180034e94  lea     rdx, _TI1J; pThrowInfo
0x180034e9b  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180034e9f  call    _CxxThrowException_0
```
