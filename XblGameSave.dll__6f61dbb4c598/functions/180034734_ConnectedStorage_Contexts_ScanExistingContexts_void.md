# ConnectedStorage::Contexts::ScanExistingContexts(void)

- ea: `0x180034734`
- end: `0x180034a32`
- name: `?ScanExistingContexts@Contexts@ConnectedStorage@@AEBAXXZ`
- size: `766`
- prototype: `void __fastcall(ConnectedStorage::Contexts *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800346d0`

## callees

- `0x180003c70`
- `0x1800078e8`
- `0x18000ab18`
- `0x18000cb9c`
- `0x18001bf48`
- `0x18001c040`
- `0x18001f4a0`
- `0x18001f5e0`
- `0x180022dec`
- `0x1800318bc`
- `0x180033414`
- `0x180034734`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034911`
- `ntdll!RtlIsMultiSessionSku` at `0x180034928`
- `ntdll!RtlIsMultiSessionSku` at `0x180034928`

## pseudocode

```c
void __fastcall ConnectedStorage::Contexts::ScanExistingContexts(ConnectedStorage::Contexts *this)
{
  ConnectedStorage::Contexts *v1; // rsi
  __int64 v2; // rcx
  _QWORD *v3; // rbx
  int v4; // edi
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, _QWORD, _QWORD, HSTRING *, HSTRING *, HSTRING *, _BYTE *); // r13
  HSTRING *AddressOf; // r12
  HSTRING *v8; // r15
  HSTRING *v9; // rax
  char *v10; // r8
  const unsigned __int16 *v11; // r8
  __int64 v12; // r14
  __int64 v13; // r15
  _BYTE v14[8]; // [rsp+40h] [rbp-178h] BYREF
  HSTRING string; // [rsp+48h] [rbp-170h] BYREF
  HSTRING v16; // [rsp+50h] [rbp-168h] BYREF
  _QWORD *v17; // [rsp+58h] [rbp-160h]
  HSTRING v18; // [rsp+60h] [rbp-158h] BYREF
  ConnectedStorage::Contexts *v19; // [rsp+68h] [rbp-150h]
  _QWORD *v20; // [rsp+70h] [rbp-148h]
  ConnectedStorage::Contexts *v21; // [rsp+78h] [rbp-140h]
  _QWORD *v22; // [rsp+80h] [rbp-138h]
  _QWORD v23[3]; // [rsp+88h] [rbp-130h] BYREF
  _QWORD v24[2]; // [rsp+A0h] [rbp-118h] BYREF
  _QWORD v25[8]; // [rsp+B0h] [rbp-108h] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp-C8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+110h] [rbp-A8h] BYREF
  _BYTE v28[32]; // [rsp+120h] [rbp-98h] BYREF
  _DWORD v29[16]; // [rsp+140h] [rbp-78h] BYREF

  v1 = this;
  v19 = this;
  v21 = this;
  ConnectedStorage::PendingUploadLogger::ClearPendingUploadsForDeletedUsers();
  v20 = (_QWORD *)((char *)v1 + 168);
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v1 + 21) + 48LL))(*((_QWORD *)v1 + 21), v23);
  v2 = v23[0];
  v3 = (_QWORD *)v23[0];
  v22 = (_QWORD *)v23[1];
  while ( 1 )
  {
    v17 = v3;
    if ( v3 == v22 )
      break;
    try
    {
      v14[0] = 0;
      v4 = 0;
      v18 = 0;
      v16 = 0;
      string = 0;
      v5 = *v20;
      v6 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING *, HSTRING *, HSTRING *, _BYTE *))(*(_QWORD *)*v20 + 8LL);
      AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
      v8 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v16);
      v9 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v18);
      v6(v5, *v3, 0, v9, v8, AddressOf, v14);
      if ( !v14[0] )
      {
        ConnectedStorage::Mutex::Lock::Lock(
          (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
          (ConnectedStorage::Contexts *)((char *)v1 + 176),
          v10);
        v25[0] = off_180090620;
        v25[1] = v21;
        v25[2] = v3;
        v25[3] = &v18;
        v25[4] = &v16;
        v25[5] = &string;
        v25[6] = v14;
        v25[7] = v25;
        ConnectedStorage::PendingUploadLogger::EnumeratePendingUploadsForUser(&v16, &string, v25);
        LeaveCriticalSection(lpCriticalSection[0]);
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v16);
      v16 = 0;
      WindowsDeleteString(v18);
    }
    catch ( ConnectedStorage::ComError v29 )
    {
      LODWORD(string) = v29[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v29);
      v3 = v17;
      v4 = (int)string;
      v1 = v19;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(string) = -2147024882;
      v3 = v17;
      v4 = -2147024882;
      v1 = v19;
    }
    catch ( ... )
    {
      LODWORD(string) = -2147467259;
      v3 = v17;
      v4 = -2147467259;
      v1 = v19;
    }
    if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    {
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v20 + 56LL))(*v20, v28);
      ConnectedStorage::Contexts::GetAllContexts(v1);
      v12 = v26[0];
      v24[0] = v21;
      v24[1] = v28;
      v13 = v26[1];
      while ( v12 != v13 )
      {
        lambda_1e4e71d5fefea8a9649a8ab9d35d1697_::operator()(v24, v12);
        v12 += 56;
      }
      std::vector<XblGameSaveProviderInfo>::_Tidy(v26);
      std::vector<ConnectedStorage::SimpleHStringWrapper>::_Tidy(v28);
    }
    if ( v4 < 0 )
      ConnectedStorage::ReportErrorNoThrow(
        (ConnectedStorage *)(unsigned int)v4,
        (int)L"Contexts::ScanExistingContexts",
        v11);
    ++v3;
    v2 = v23[0];
  }
  if ( v2 )
    std::_Deallocate<16>(v2, (v23[2] - v2) & 0xFFFFFFFFFFFFFFF8uLL);
}

```

## disassembly

```asm
0x180034734  mov     [rsp+arg_8], rbx
0x180034739  mov     [rsp+arg_10], rsi
0x18003473e  push    rdi
0x18003473f  push    r12
0x180034741  push    r13
0x180034743  push    r14
0x180034745  push    r15
0x180034747  sub     rsp, 190h
0x18003474e  mov     rax, cs:__security_cookie
0x180034755  xor     rax, rsp
0x180034758  mov     [rsp+1B8h+var_38], rax
0x180034760  mov     rsi, rcx
0x180034763  mov     [rsp+1B8h+var_150], rcx
0x180034768  mov     [rsp+1B8h+var_140], rcx
0x18003476d  call    ?ClearPendingUploadsForDeletedUsers@PendingUploadLogger@ConnectedStorage@@SAXXZ; ConnectedStorage::PendingUploadLogger::ClearPendingUploadsForDeletedUsers(void)
0x180034772  lea     rax, [rsi+0A8h]
0x180034779  mov     [rsp+1B8h+var_148], rax
0x18003477e  mov     rcx, [rax]
0x180034781  mov     rax, [rcx]
0x180034784  lea     rdx, [rsp+1B8h+var_130]
0x18003478c  mov     rax, [rax+30h]
0x180034790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034795  nop
0x180034796  mov     rcx, [rsp+1B8h+var_130]
0x18003479e  mov     rbx, rcx
0x1800347a1  mov     rax, [rsp+1B8h+var_128]
0x1800347a9  mov     [rsp+1B8h+var_138], rax
0x1800347b1  mov     [rsp+1B8h+var_160], rbx
0x1800347b6  cmp     rbx, [rsp+1B8h+var_138]
0x1800347be  jz      loc_1800349EC
0x1800347c4  mov     [rsp+1B8h+var_178], 0
0x1800347c9  xor     edi, edi
0x1800347cb  mov     [rsp+1B8h+var_158], rdi
0x1800347d0  mov     [rsp+1B8h+var_168], rdi
0x1800347d5  mov     [rsp+1B8h+string], rdi
0x1800347da  mov     rax, [rsp+1B8h+var_148]
0x1800347df  mov     r14, [rax]
0x1800347e2  mov     rax, [r14]
0x1800347e5  mov     r13, [rax+8]
0x1800347e9  lea     rcx, [rsp+1B8h+string]; this
0x1800347ee  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800347f3  mov     r12, rax
0x1800347f6  lea     rcx, [rsp+1B8h+var_168]; this
0x1800347fb  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180034800  mov     r15, rax
0x180034803  lea     rcx, [rsp+1B8h+var_158]; this
0x180034808  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18003480d  lea     rcx, [rsp+1B8h+var_178]
0x180034812  mov     [rsp+1B8h+var_188], rcx
0x180034817  mov     [rsp+1B8h+var_190], r12
0x18003481c  mov     [rsp+1B8h+var_198], r15
0x180034821  mov     r9, rax
0x180034824  xor     r8d, r8d
0x180034827  mov     rdx, [rbx]
0x18003482a  mov     rcx, r14
0x18003482d  mov     rax, r13
0x180034830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034835  cmp     [rsp+1B8h+var_178], dil
0x18003483a  jnz     loc_1800348E4
0x180034840  lea     rdx, [rsi+0B0h]; struct ConnectedStorage::Mutex *
0x180034847  lea     rcx, [rsp+1B8h+lpCriticalSection]; this
0x18003484f  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180034854  nop
0x180034855  lea     rax, off_180090620
0x18003485c  mov     [rsp+1B8h+var_108], rax
0x180034864  mov     rax, [rsp+1B8h+var_140]
0x180034869  mov     [rsp+1B8h+var_100], rax
0x180034871  mov     [rsp+1B8h+var_F8], rbx
0x180034879  lea     rax, [rsp+1B8h+var_158]
0x18003487e  mov     [rsp+1B8h+var_F0], rax
0x180034886  lea     rax, [rsp+1B8h+var_168]
0x18003488b  mov     [rsp+1B8h+var_E8], rax
0x180034893  lea     rax, [rsp+1B8h+string]
0x180034898  mov     [rsp+1B8h+var_E0], rax
0x1800348a0  lea     rax, [rsp+1B8h+var_178]
0x1800348a5  mov     [rsp+1B8h+var_D8], rax
0x1800348ad  lea     rax, [rsp+1B8h+var_108]
0x1800348b5  mov     [rsp+1B8h+var_D0], rax
0x1800348bd  lea     r8, [rsp+1B8h+var_108]
0x1800348c5  lea     rdx, [rsp+1B8h+string]
0x1800348ca  lea     rcx, [rsp+1B8h+var_168]
0x1800348cf  call    ?EnumeratePendingUploadsForUser@PendingUploadLogger@ConnectedStorage@@SAXAEBVSimpleHStringWrapper@2@0V?$function@$$A6AXAEBVSimpleHStringWrapper@ConnectedStorage@@0@Z@std@@@Z; ConnectedStorage::PendingUploadLogger::EnumeratePendingUploadsForUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>)
0x1800348d4  nop
0x1800348d5  mov     rcx, [rsp+1B8h+lpCriticalSection]; lpCriticalSection
0x1800348dd  call    cs:__imp_LeaveCriticalSection
0x1800348e3  nop
0x1800348e4  mov     rcx, [rsp+1B8h+string]; string
0x1800348e9  call    cs:__imp_WindowsDeleteString
0x1800348ef  mov     [rsp+1B8h+string], 0
0x1800348f8  mov     rcx, [rsp+1B8h+var_168]; string
0x1800348fd  call    cs:__imp_WindowsDeleteString
0x180034903  mov     [rsp+1B8h+var_168], 0
0x18003490c  mov     rcx, [rsp+1B8h+var_158]; string
0x180034911  call    cs:__imp_WindowsDeleteString
0x180034917  nop
0x180034918  jmp     short loc_180034928
0x18003491a  mov     rbx, [rsp+1B8h+var_160]
0x18003491f  mov     edi, dword ptr [rsp+1B8h+string]
0x180034923  mov     rsi, [rsp+1B8h+var_150]
0x180034928  call    cs:__imp_RtlIsMultiSessionSku
0x18003492e  test    al, al
0x180034930  jnz     loc_1800349C9
0x180034936  mov     rax, [rsp+1B8h+var_148]
0x18003493b  mov     rcx, [rax]
0x18003493e  mov     rax, [rcx]
0x180034941  lea     rdx, [rsp+1B8h+var_98]
0x180034949  mov     rax, [rax+38h]
0x18003494d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034952  nop
0x180034953  lea     rdx, [rsp+1B8h+var_C8]
0x18003495b  mov     rcx, rsi; this
0x18003495e  call    ?GetAllContexts@Contexts@ConnectedStorage@@QEBA?AV?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@XZ; ConnectedStorage::Contexts::GetAllContexts(void)
0x180034963  nop
0x180034964  mov     r14, [rsp+1B8h+var_C8]
0x18003496c  mov     rax, [rsp+1B8h+var_140]
0x180034971  mov     [rsp+1B8h+var_118], rax
0x180034979  lea     rax, [rsp+1B8h+var_98]
0x180034981  mov     [rsp+1B8h+var_110], rax
0x180034989  mov     r15, [rsp+1B8h+var_C0]
0x180034991  jmp     short loc_1800349A9
0x180034993  jmp     short loc_18003491A
0x180034995  mov     rdx, r14
0x180034998  lea     rcx, [rsp+1B8h+var_118]
0x1800349a0  call    _lambda_1e4e71d5fefea8a9649a8ab9d35d1697___operator__
0x1800349a5  add     r14, 38h ; '8'
0x1800349a9  cmp     r14, r15
0x1800349ac  jnz     short loc_180034995
0x1800349ae  lea     rcx, [rsp+1B8h+var_C8]
0x1800349b6  call    ?_Tidy@?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@AEAAXXZ; std::vector<XblGameSaveProviderInfo>::_Tidy(void)
0x1800349bb  nop
0x1800349bc  lea     rcx, [rsp+1B8h+var_98]
0x1800349c4  call    ?_Tidy@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@AEAAXXZ; std::vector<ConnectedStorage::SimpleHStringWrapper>::_Tidy(void)
0x1800349c9  test    edi, edi
0x1800349cb  jns     short loc_1800349DB
0x1800349cd  lea     rdx, aContextsScanex; "Contexts::ScanExistingContexts"
0x1800349d4  mov     ecx, edi; this
0x1800349d6  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x1800349db  add     rbx, 8
0x1800349df  mov     rcx, [rsp+1B8h+var_130]
0x1800349e7  jmp     loc_1800347B1
0x1800349ec  test    rcx, rcx
0x1800349ef  jz      short loc_180034A05
0x1800349f1  mov     rdx, [rsp+1B8h+var_120]
0x1800349f9  sub     rdx, rcx
0x1800349fc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180034a00  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180034a05  mov     rcx, [rsp+1B8h+var_38]
0x180034a0d  xor     rcx, rsp; StackCookie
0x180034a10  call    __security_check_cookie
0x180034a15  lea     r11, [rsp+1B8h+var_28]
0x180034a1d  mov     rbx, [r11+38h]
0x180034a21  mov     rsi, [r11+40h]
0x180034a25  mov     rsp, r11
0x180034a28  pop     r15
0x180034a2a  pop     r14
0x180034a2c  pop     r13
0x180034a2e  pop     r12
0x180034a30  pop     rdi
0x180034a31  retn
```
