# PhoneNotificationManager::GetListenerIdentity(IPhoneServiceListener *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18000c960`
- end: `0x18000cccc`
- name: `?GetListenerIdentity@PhoneNotificationManager@@QEAAJPEAUIPhoneServiceListener@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@1@Z`
- size: `876`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180087c30`
- `0x1800883e0`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x18000c058`
- `0x18000c960`
- `0x18000cce0`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c996`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc65`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cb49`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cb49`
- `PhoneUtil!GetUserSecurityIdentifierForToken` at `0x18000cacd`
- `PhoneUtil!GetUserSecurityIdentifierForToken` at `0x18000cacd`

## pseudocode

```c
__int64 __fastcall PhoneNotificationManager::GetListenerIdentity(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v9; // rdx
  _WORD *v10; // r8
  unsigned __int64 v11; // r9
  __int64 *v12; // r10
  __int64 v13; // rdx
  char v14; // cl
  __int64 *v15; // rsi
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 *v18; // rcx
  int UserSecurityIdentifierForToken; // eax
  BackTraceCollection *v21; // rcx
  unsigned int v22; // edi
  __int64 v23; // r8
  signed int LastError; // eax
  BackTraceCollection *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  BackTraceCollection *v29; // rcx
  BackTraceCollection *v30; // rcx
  PSID Sid; // [rsp+30h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-48h] BYREF
  __int128 v33; // [rsp+40h] [rbp-40h]
  void *Block; // [rsp+50h] [rbp-30h]
  _WORD *v35; // [rsp+58h] [rbp-28h]
  _WORD v36[8]; // [rsp+60h] [rbp-20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  v10 = v36;
  Block = v36;
  v36[0] = 0;
  v35 = v36;
  v11 = 0;
  v33 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64 *, __int64, _WORD *, _QWORD))(*a2 + 8))(a2, v9, v36, 0);
    if ( (_QWORD)v33 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 16LL))(v33);
    v10 = Block;
    v11 = (unsigned __int64)a2;
    *(_QWORD *)&v33 = a2;
  }
  else
  {
    a2 = (__int64 *)v33;
  }
  v12 = (__int64 *)(a1 + 152);
  v13 = *(_QWORD *)(a1 + 168);
  if ( !v13 || (v14 = *(_BYTE *)(a1 + 184), (v15 = *(__int64 **)(v13 + 16 * (v11 & ((8LL << v14) - 1)))) == 0) )
  {
LABEL_14:
    if ( v10 != v36 )
    {
      operator delete(v10);
      a2 = (__int64 *)v33;
    }
    if ( *((_QWORD *)&v33 + 1) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _WORD *, unsigned __int64))(**((_QWORD **)&v33 + 1) + 16LL))(
        *((_QWORD *)&v33 + 1),
        v13,
        v10,
        v11);
      a2 = (__int64 *)v33;
    }
    if ( a2 )
    {
      v17 = *a2;
      v18 = a2;
LABEL_20:
      (*(void (__fastcall **)(__int64 *, __int64, _WORD *, unsigned __int64))(v17 + 16))(v18, v13, v10, v11);
    }
LABEL_21:
    LeaveCriticalSection(v4);
    return 2147943568LL;
  }
  v16 = **(__int64 ***)(v13 + 16 * (v11 & ((8LL << v14) - 1)) + 8);
  while ( 1 )
  {
    if ( v15 == v16 )
      goto LABEL_14;
    if ( v15[2] >= v11 )
    {
      if ( v15[2] > v11 )
        goto LABEL_14;
      if ( a2 == (__int64 *)v15[3] )
        break;
    }
    v15 = (__int64 *)*v15;
  }
  if ( v15 == v12 )
    goto LABEL_14;
  Sid = 0;
  UserSecurityIdentifierForToken = GetUserSecurityIdentifierForToken(
                                     (struct ISecurityToken *)v15[4],
                                     (struct _SID **)&Sid);
  v22 = UserSecurityIdentifierForToken;
  if ( UserSecurityIdentifierForToken < 0 )
  {
    BackTraceCollection::Capture(v21, UserSecurityIdentifierForToken);
    Log_HREvent_1(v22, 1, v23, 85);
LABEL_45:
    if ( Sid )
      _HeapFreer<_SID>(Sid);
    if ( Block != v36 )
      operator delete(Block);
    if ( *((_QWORD *)&v33 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v33 + 1) + 16LL))(*((_QWORD *)&v33 + 1));
    if ( (_QWORD)v33 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 16LL))(v33);
    LeaveCriticalSection(v4);
    return v22;
  }
  if ( !Sid )
  {
    if ( Block != v36 )
      operator delete(Block);
    if ( *((_QWORD *)&v33 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v33 + 1) + 16LL))(*((_QWORD *)&v33 + 1));
    v18 = (__int64 *)v33;
    if ( (_QWORD)v33 )
    {
      v17 = *(_QWORD *)v33;
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v22 = LastError;
    if ( LastError > 0 )
      v22 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v25, v22);
    v27 = 91;
    goto LABEL_43;
  }
  if ( StringSid )
  {
    v28 = -1;
    do
      ++v28;
    while ( StringSid[v28] );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a3) )
  {
    v22 = -2147024882;
    BackTraceCollection::Capture(v29, -2147024882);
    v27 = 93;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a4) )
  {
    v22 = -2147024882;
    BackTraceCollection::Capture(v30, -2147024882);
    v27 = 94;
LABEL_43:
    Log_HREvent_1(v22, 0, v26, v27);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_45;
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    _HeapFreer<_SID>(Sid);
  if ( Block != v36 )
    operator delete(Block);
  if ( *((_QWORD *)&v33 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v33 + 1) + 16LL))(*((_QWORD *)&v33 + 1));
  if ( (_QWORD)v33 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 16LL))(v33);
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x18000c960  push    rbp
0x18000c962  push    rbx
0x18000c963  push    rsi
0x18000c964  push    rdi
0x18000c965  push    r12
0x18000c967  push    r14
0x18000c969  push    r15
0x18000c96b  mov     rbp, rsp
0x18000c96e  sub     rsp, 80h
0x18000c975  mov     rax, cs:__security_cookie
0x18000c97c  xor     rax, rsp
0x18000c97f  mov     [rbp+var_10], rax
0x18000c983  lea     rbx, [rcx+70h]
0x18000c987  mov     rsi, rcx
0x18000c98a  mov     rcx, rbx; lpCriticalSection
0x18000c98d  mov     r15, r9
0x18000c990  mov     r14, r8
0x18000c993  mov     rdi, rdx
0x18000c996  call    cs:__imp_EnterCriticalSection
0x18000c99c  xor     r12d, r12d
0x18000c99f  lea     r8, [rbp+var_20]
0x18000c9a3  mov     [rbp+Block], r8
0x18000c9a7  xorps   xmm0, xmm0
0x18000c9aa  mov     [rbp+var_20], r12w
0x18000c9af  lea     rax, [rbp+var_20]
0x18000c9b3  mov     [rbp+var_28], rax
0x18000c9b7  mov     r9d, r12d
0x18000c9ba  movdqu  [rbp+var_40], xmm0
0x18000c9bf  test    rdi, rdi
0x18000c9c2  jz      short loc_18000C9F5
0x18000c9c4  mov     rax, [rdi]
0x18000c9c7  mov     rcx, rdi
0x18000c9ca  mov     rax, [rax+8]
0x18000c9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d3  mov     rcx, qword ptr [rbp+var_40]
0x18000c9d7  test    rcx, rcx
0x18000c9da  jz      short loc_18000C9E8
0x18000c9dc  mov     rax, [rcx]
0x18000c9df  mov     rax, [rax+10h]
0x18000c9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9e8  mov     r8, [rbp+Block]
0x18000c9ec  mov     r9, rdi
0x18000c9ef  mov     qword ptr [rbp+var_40], rdi
0x18000c9f3  jmp     short loc_18000C9F9
0x18000c9f5  mov     rdi, qword ptr [rbp+var_40]
0x18000c9f9  lea     r10, [rsi+98h]
0x18000ca00  mov     rdx, [r10+10h]
0x18000ca04  test    rdx, rdx
0x18000ca07  jz      short loc_18000CA47
0x18000ca09  mov     cl, [r10+20h]
0x18000ca0d  mov     eax, 8
0x18000ca12  shl     rax, cl
0x18000ca15  dec     rax
0x18000ca18  and     rax, r9
0x18000ca1b  add     rax, rax
0x18000ca1e  mov     rsi, [rdx+rax*8]
0x18000ca22  test    rsi, rsi
0x18000ca25  jz      short loc_18000CA47
0x18000ca27  mov     rax, [rdx+rax*8+8]
0x18000ca2c  mov     rcx, [rax]
0x18000ca2f  jmp     short loc_18000CA42
0x18000ca31  cmp     [rsi+10h], r9
0x18000ca35  jb      short loc_18000CA3F
0x18000ca37  ja      short loc_18000CA47
0x18000ca39  cmp     rdi, [rsi+18h]
0x18000ca3d  jz      short loc_18000CABC
0x18000ca3f  mov     rsi, [rsi]
0x18000ca42  cmp     rsi, rcx
0x18000ca45  jnz     short loc_18000CA31
0x18000ca47  lea     rax, [rbp+var_20]
0x18000ca4b  cmp     r8, rax
0x18000ca4e  jz      short loc_18000CA63
0x18000ca50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000ca57  mov     rcx, r8; Block
0x18000ca5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ca5f  mov     rdi, qword ptr [rbp+var_40]
0x18000ca63  mov     rcx, qword ptr [rbp+var_40+8]
0x18000ca67  test    rcx, rcx
0x18000ca6a  jz      short loc_18000CA7C
0x18000ca6c  mov     rax, [rcx]
0x18000ca6f  mov     rax, [rax+10h]
0x18000ca73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca78  mov     rdi, qword ptr [rbp+var_40]
0x18000ca7c  test    rdi, rdi
0x18000ca7f  jz      short loc_18000CA90
0x18000ca81  mov     rax, [rdi]
0x18000ca84  mov     rcx, rdi
0x18000ca87  mov     rax, [rax+10h]
0x18000ca8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca90  mov     rcx, rbx; lpCriticalSection
0x18000ca93  call    cs:__imp_LeaveCriticalSection
0x18000ca99  mov     eax, 80070490h
0x18000ca9e  mov     rcx, [rbp+var_10]
0x18000caa2  xor     rcx, rsp; StackCookie
0x18000caa5  call    __security_check_cookie
0x18000caaa  add     rsp, 80h
0x18000cab1  pop     r15
0x18000cab3  pop     r14
0x18000cab5  pop     r12
0x18000cab7  pop     rdi
0x18000cab8  pop     rsi
0x18000cab9  pop     rbx
0x18000caba  pop     rbp
0x18000cabb  retn
0x18000cabc  cmp     rsi, r10
0x18000cabf  jz      short loc_18000CA47
0x18000cac1  mov     [rbp+Sid], r12
0x18000cac5  lea     rdx, [rbp+Sid]
0x18000cac9  mov     rcx, [rsi+20h]
0x18000cacd  call    cs:__imp_?GetUserSecurityIdentifierForToken@@YAJPEAUISecurityToken@@PEAPEAU_SID@@@Z; GetUserSecurityIdentifierForToken(ISecurityToken *,_SID * *)
0x18000cad3  mov     edi, eax
0x18000cad5  test    eax, eax
0x18000cad7  jns     short loc_18000CAF5
0x18000cad9  mov     edx, eax; int
0x18000cadb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000cae0  mov     edx, 1
0x18000cae5  mov     ecx, edi
0x18000cae7  lea     r9d, [rdx+54h]
0x18000caeb  call    Log_HREvent_1
0x18000caf0  jmp     loc_18000CBFB
0x18000caf5  mov     rcx, [rbp+Sid]; Sid
0x18000caf9  test    rcx, rcx
0x18000cafc  jnz     short loc_18000CB41
0x18000cafe  mov     rcx, [rbp+Block]; Block
0x18000cb02  lea     rax, [rbp+var_20]
0x18000cb06  cmp     rcx, rax
0x18000cb09  jz      short loc_18000CB17
0x18000cb0b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000cb12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cb17  mov     rcx, qword ptr [rbp+var_40+8]
0x18000cb1b  test    rcx, rcx
0x18000cb1e  jz      short loc_18000CB2C
0x18000cb20  mov     rax, [rcx]
0x18000cb23  mov     rax, [rax+10h]
0x18000cb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb2c  mov     rcx, qword ptr [rbp+var_40]
0x18000cb30  test    rcx, rcx
0x18000cb33  jz      loc_18000CA90
0x18000cb39  mov     rax, [rcx]
0x18000cb3c  jmp     loc_18000CA87
0x18000cb41  lea     rdx, [rbp+StringSid]; StringSid
0x18000cb45  mov     [rbp+StringSid], r12
0x18000cb49  call    cs:__imp_ConvertSidToStringSidW
0x18000cb4f  test    eax, eax
0x18000cb51  jnz     short loc_18000CB77
0x18000cb53  call    cs:__imp_GetLastError
0x18000cb59  mov     edi, eax
0x18000cb5b  test    eax, eax
0x18000cb5d  jle     short loc_18000CB68
0x18000cb5f  movzx   edi, ax
0x18000cb62  or      edi, 80070000h
0x18000cb68  mov     edx, edi; int
0x18000cb6a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000cb6f  mov     r9d, 5Bh ; '['
0x18000cb75  jmp     short loc_18000CBE3
0x18000cb77  mov     rdx, [rbp+StringSid]
0x18000cb7b  test    rdx, rdx
0x18000cb7e  jz      short loc_18000CB90
0x18000cb80  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cb84  inc     r8
0x18000cb87  cmp     [rdx+r8*2], r12w
0x18000cb8c  jnz     short loc_18000CB84
0x18000cb8e  jmp     short loc_18000CB93
0x18000cb90  mov     r8, r12
0x18000cb93  mov     rcx, r14
0x18000cb96  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000cb9b  test    al, al
0x18000cb9d  jnz     short loc_18000CBB3
0x18000cb9f  mov     edi, 8007000Eh
0x18000cba4  mov     edx, edi; int
0x18000cba6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000cbab  mov     r9d, 5Dh ; ']'
0x18000cbb1  jmp     short loc_18000CBE3
0x18000cbb3  mov     rdx, [rsi+28h]
0x18000cbb7  mov     rcx, r15
0x18000cbba  mov     r8, [rsi+30h]
0x18000cbbe  sub     r8, rdx
0x18000cbc1  sar     r8, 1
0x18000cbc4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000cbc9  test    al, al
0x18000cbcb  jnz     loc_18000CC5C
0x18000cbd1  mov     edi, 8007000Eh
0x18000cbd6  mov     edx, edi; int
0x18000cbd8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000cbdd  mov     r9d, 5Eh ; '^'
0x18000cbe3  xor     edx, edx
0x18000cbe5  mov     ecx, edi
0x18000cbe7  call    Log_HREvent_1
0x18000cbec  mov     rcx, [rbp+StringSid]; hMem
0x18000cbf0  test    rcx, rcx
0x18000cbf3  jz      short loc_18000CBFB
0x18000cbf5  call    cs:__imp_LocalFree
0x18000cbfb  mov     rcx, [rbp+Sid]
0x18000cbff  test    rcx, rcx
0x18000cc02  jz      short loc_18000CC09
0x18000cc04  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x18000cc09  mov     rcx, [rbp+Block]; Block
0x18000cc0d  lea     rax, [rbp+var_20]
0x18000cc11  cmp     rcx, rax
0x18000cc14  jz      short loc_18000CC22
0x18000cc16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000cc1d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc22  mov     rcx, qword ptr [rbp+var_40+8]
0x18000cc26  test    rcx, rcx
0x18000cc29  jz      short loc_18000CC37
0x18000cc2b  mov     rax, [rcx]
0x18000cc2e  mov     rax, [rax+10h]
0x18000cc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc37  mov     rcx, qword ptr [rbp+var_40]
0x18000cc3b  test    rcx, rcx
0x18000cc3e  jz      short loc_18000CC4C
0x18000cc40  mov     rax, [rcx]
0x18000cc43  mov     rax, [rax+10h]
0x18000cc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4c  mov     rcx, rbx; lpCriticalSection
0x18000cc4f  call    cs:__imp_LeaveCriticalSection
0x18000cc55  mov     eax, edi
0x18000cc57  jmp     loc_18000CA9E
0x18000cc5c  mov     rcx, [rbp+StringSid]; hMem
0x18000cc60  test    rcx, rcx
0x18000cc63  jz      short loc_18000CC6B
0x18000cc65  call    cs:__imp_LocalFree
0x18000cc6b  mov     rcx, [rbp+Sid]
0x18000cc6f  test    rcx, rcx
0x18000cc72  jz      short loc_18000CC79
0x18000cc74  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x18000cc79  mov     rcx, [rbp+Block]; Block
0x18000cc7d  lea     rax, [rbp+var_20]
0x18000cc81  cmp     rcx, rax
0x18000cc84  jz      short loc_18000CC92
0x18000cc86  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000cc8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc92  mov     rcx, qword ptr [rbp+var_40+8]
0x18000cc96  test    rcx, rcx
0x18000cc99  jz      short loc_18000CCA7
0x18000cc9b  mov     rax, [rcx]
0x18000cc9e  mov     rax, [rax+10h]
0x18000cca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca7  mov     rcx, qword ptr [rbp+var_40]
0x18000ccab  test    rcx, rcx
0x18000ccae  jz      short loc_18000CCBC
0x18000ccb0  mov     rax, [rcx]
0x18000ccb3  mov     rax, [rax+10h]
0x18000ccb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccbc  mov     rcx, rbx; lpCriticalSection
0x18000ccbf  call    cs:__imp_LeaveCriticalSection
0x18000ccc5  xor     eax, eax
0x18000ccc7  jmp     loc_18000CA9E
```
