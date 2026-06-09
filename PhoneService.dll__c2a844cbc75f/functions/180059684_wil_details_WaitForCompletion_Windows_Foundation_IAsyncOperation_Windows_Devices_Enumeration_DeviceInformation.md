# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180059684`
- end: `0x1800598ee`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `618`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180066450`

## callees

- `0x180005c54`
- `0x18000a9e8`
- `0x18000b760`
- `0x18000c03c`
- `0x180059684`
- `0x18005b0e0`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059811`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059811`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800596dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800596dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005971b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005971b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005970a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005970a`

## string_xrefs

- `0x180059768`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800597a1`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800597cd`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180059821`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>(
        __int64 (__fastcall ***a1)(__int64, GUID *, __int64 *))
{
  void *v2; // rax
  int v3; // edi
  _QWORD *v4; // rbx
  wil::details *v5; // rcx
  HANDLE Event; // r14
  void *v7; // rdi
  DWORD LastError; // r15d
  unsigned int v9; // r8d
  const char *v10; // r9
  int v11; // eax
  int LastErrorFailHr; // eax
  HRESULT v14; // eax
  __int64 (__fastcall **v15)(__int64, GUID *, __int64 *); // rax
  __int64 v16; // rcx
  int lpdwindex; // [rsp+20h] [rbp-48h]
  int lpdwindexa; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  DWORD dwindex; // [rsp+40h] [rbp-28h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
  {
    v3 = -2147024882;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v3,
      lpdwindex);
    return (unsigned int)v3;
  }
  v4 = (_QWORD *)`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>'::`2'::CompletionDelegate::CompletionDelegate(v2);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v7 = (void *)v4[7];
    if ( v7 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
      SetLastError(LastError);
    }
    v4[7] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    v3 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      if ( v4 )
        (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
      goto LABEL_16;
    }
  }
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  }
  v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), _QWORD *))(*a1)[6])(a1, v4);
  v3 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v11,
      lpdwindex);
    if ( !v4 )
      return (unsigned int)v3;
LABEL_12:
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return (unsigned int)v3;
  }
  pHandles = (HANDLE)v4[7];
  dwindex = 0;
  v14 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v14,
      lpdwindexa);
    goto LABEL_12;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v15 = *a1;
    v20 = 0;
    v3 = (*v15)((__int64)a1, &GUID_00000036_0000_0000_c000_000000000046, &v20);
    if ( v3 >= 0 )
    {
      v19 = -2147418113;
      v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v19);
      if ( v3 >= 0 )
        v3 = v19;
    }
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_12;
  }
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180059684  push    rbp
0x180059686  push    rbx
0x180059687  push    rsi
0x180059688  push    rdi
0x180059689  push    r14
0x18005968b  push    r15
0x18005968d  mov     rbp, rsp
0x180059690  sub     rsp, 68h
0x180059694  mov     rax, cs:__security_cookie
0x18005969b  xor     rax, rsp
0x18005969e  mov     [rbp+var_18], rax
0x1800596a2  mov     rsi, rcx
0x1800596a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800596ac  mov     ecx, 40h ; '@'; unsigned __int64
0x1800596b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800596b6  test    rax, rax
0x1800596b9  jnz     short loc_1800596C5
0x1800596bb  mov     edi, 8007000Eh
0x1800596c0  jmp     loc_1800597C9
0x1800596c5  mov     rcx, rax
0x1800596c8  call    ??0CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAA@XZ; `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::CompletionDelegate(void)
0x1800596cd  mov     r9d, 1F0003h; dwDesiredAccess
0x1800596d3  xor     r8d, r8d; dwFlags
0x1800596d6  xor     edx, edx; lpName
0x1800596d8  xor     ecx, ecx; lpEventAttributes
0x1800596da  mov     rbx, rax
0x1800596dd  call    cs:__imp_CreateEventExW
0x1800596e3  mov     r14, rax
0x1800596e6  test    rax, rax
0x1800596e9  jz      loc_180059792
0x1800596ef  call    cs:__imp_GetLastError
0x1800596f5  mov     rdi, [rbx+38h]
0x1800596f9  test    rdi, rdi
0x1800596fc  jz      short loc_180059721
0x1800596fe  call    cs:__imp_GetLastError
0x180059704  mov     rcx, rdi; hObject
0x180059707  mov     r15d, eax
0x18005970a  call    cs:__imp_CloseHandle
0x180059710  test    eax, eax
0x180059712  jz      loc_1800598DF
0x180059718  mov     ecx, r15d; dwErrCode
0x18005971b  call    cs:__imp_SetLastError
0x180059721  mov     [rbx+38h], r14
0x180059725  test    rbx, rbx
0x180059728  jz      short loc_180059748
0x18005972a  mov     rax, [rbx]
0x18005972d  mov     rcx, rbx
0x180059730  mov     rax, [rax+8]
0x180059734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059739  mov     rax, [rbx]
0x18005973c  mov     rcx, rbx
0x18005973f  mov     rax, [rax+10h]
0x180059743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059748  mov     rax, [rsi]
0x18005974b  mov     rdx, rbx
0x18005974e  mov     rcx, rsi
0x180059751  mov     rax, [rax+30h]
0x180059755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005975a  mov     edi, eax
0x18005975c  test    eax, eax
0x18005975e  jns     loc_1800597E8
0x180059764  mov     rcx, [rbp+30h]; this
0x180059768  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005976f  mov     r9d, eax; char *
0x180059772  mov     edx, 649h; void *
0x180059777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005977c  test    rbx, rbx
0x18005977f  jz      short loc_1800597E1
0x180059781  mov     rcx, [rbx]
0x180059784  mov     rax, [rcx+10h]
0x180059788  mov     rcx, rbx
0x18005978b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059790  jmp     short loc_1800597E1
0x180059792  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180059797  mov     edi, eax
0x180059799  test    eax, eax
0x18005979b  jns     short loc_180059725
0x18005979d  mov     rcx, [rbp+30h]; this
0x1800597a1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800597a8  mov     r9d, eax; char *
0x1800597ab  mov     edx, 62Bh; void *
0x1800597b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800597b5  test    rbx, rbx
0x1800597b8  jz      short loc_1800597C9
0x1800597ba  mov     rax, [rbx]
0x1800597bd  mov     rcx, rbx
0x1800597c0  mov     rax, [rax+10h]
0x1800597c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597c9  mov     rcx, [rbp+30h]; this
0x1800597cd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800597d4  mov     r9d, edi; char *
0x1800597d7  mov     edx, 648h; void *
0x1800597dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800597e1  mov     eax, edi
0x1800597e3  jmp     loc_1800598C6
0x1800597e8  mov     rax, [rbx+38h]
0x1800597ec  lea     r9, [rbp+pHandles]; pHandles
0x1800597f0  mov     r8d, 1; cHandles
0x1800597f6  mov     [rbp+pHandles], rax
0x1800597fa  lea     rax, [rbp+dwindex]
0x1800597fe  mov     [rbp+dwindex], 0
0x180059805  or      edx, 0FFFFFFFFh; dwTimeout
0x180059808  mov     qword ptr [rsp+68h+lpdwindex], rax; int
0x18005980d  lea     ecx, [r8+7]; dwFlags
0x180059811  call    cs:__imp_CoWaitForMultipleHandles
0x180059817  mov     edi, eax
0x180059819  test    eax, eax
0x18005981b  jns     short loc_18005983A
0x18005981d  mov     rcx, [rbp+30h]; this
0x180059821  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180059828  mov     r9d, eax; char *
0x18005982b  mov     edx, 655h; void *
0x180059830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059835  jmp     loc_180059781
0x18005983a  mov     eax, [rbx+30h]
0x18005983d  cmp     eax, 1
0x180059840  jz      short loc_1800598B5
0x180059842  mov     rax, [rsi]
0x180059845  lea     r8, [rbp+var_30]
0x180059849  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180059850  mov     [rbp+var_30], 0
0x180059858  mov     rcx, rsi
0x18005985b  mov     rax, [rax]
0x18005985e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059863  mov     edi, eax
0x180059865  test    eax, eax
0x180059867  js      short loc_18005988C
0x180059869  mov     rcx, [rbp+var_30]
0x18005986d  lea     rdx, [rbp+var_38]
0x180059871  mov     [rbp+var_38], 8000FFFFh
0x180059878  mov     rax, [rcx]
0x18005987b  mov     rax, [rax+40h]
0x18005987f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059884  test    eax, eax
0x180059886  mov     edi, eax
0x180059888  cmovns  edi, [rbp+var_38]
0x18005988c  mov     rcx, [rbp+var_30]
0x180059890  test    rcx, rcx
0x180059893  jz      short loc_1800598A9
0x180059895  mov     [rbp+var_30], 0
0x18005989d  mov     rax, [rcx]
0x1800598a0  mov     rax, [rax+10h]
0x1800598a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598a9  mov     rax, [rbx]
0x1800598ac  mov     rax, [rax+10h]
0x1800598b0  jmp     loc_180059788
0x1800598b5  mov     rax, [rbx]
0x1800598b8  mov     rcx, rbx
0x1800598bb  mov     rax, [rax+10h]
0x1800598bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598c4  xor     eax, eax
0x1800598c6  mov     rcx, [rbp+var_18]
0x1800598ca  xor     rcx, rsp; StackCookie
0x1800598cd  call    __security_check_cookie
0x1800598d2  add     rsp, 68h
0x1800598d6  pop     r15
0x1800598d8  pop     r14
0x1800598da  pop     rdi
0x1800598db  pop     rsi
0x1800598dc  pop     rbx
0x1800598dd  pop     rbp
0x1800598de  retn
0x1800598df  mov     rcx, [rbp+30h]; this
0x1800598e3  mov     edx, 0A0Bh; void *
0x1800598e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
