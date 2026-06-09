# ConnectedStorage::ContainerSnapshot::UploadAtomsComplete(ConnectedStorage::WebService::Status,std::function<void (ConnectedStorage::UploadResult)>)

- ea: `0x18007bca8`
- end: `0x18007bf63`
- name: `?UploadAtomsComplete@ContainerSnapshot@ConnectedStorage@@AEBAXW4Status@WebService@2@V?$function@$$A6AXW4UploadResult@ConnectedStorage@@@Z@std@@@Z`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ca70`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x180010e90`
- `0x1800113bc`
- `0x1800136a8`
- `0x1800190f0`
- `0x180019128`
- `0x18001ed74`
- `0x18002a1dc`
- `0x18002e420`
- `0x18002ec70`
- `0x1800396b8`
- `0x1800796b8`
- `0x18007b3e8`
- `0x18007bca8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bdd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bdd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bd9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bd9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ConnectedStorage::ContainerSnapshot::UploadAtomsComplete(HSTRING a1, int a2, char *a3)
{
  __int64 v3; // rbx
  HSTRING v4; // rsi
  char *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // r14d
  unsigned int v9; // r15d
  int v10; // r12d
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // rdi
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v15; // rax
  _QWORD *v16; // rax
  struct ConnectedStorage::WebService *v17; // rdi
  __int64 v18; // r14
  void (__fastcall *v19)(struct ConnectedStorage::WebService *, _BYTE *, HSTRING *, HSTRING, HSTRING, HSTRING, ConnectedStorage::SimpleHStringWrapper *, _BYTE *); // r15
  ConnectedStorage::SimpleHStringWrapper *Json; // r14
  HSTRING *v21; // rax
  unsigned __int64 v23; // [rsp+28h] [rbp-1B0h]
  unsigned int v24; // [rsp+40h] [rbp-198h]
  HSTRING string; // [rsp+50h] [rbp-188h] BYREF
  char *v26; // [rsp+58h] [rbp-180h]
  char *v27; // [rsp+60h] [rbp-178h]
  std::_Ref_count_base *v28[2]; // [rsp+68h] [rbp-170h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-160h] BYREF
  std::_Ref_count_base *v30; // [rsp+80h] [rbp-158h]
  _BYTE v31[8]; // [rsp+88h] [rbp-150h] BYREF
  std::_Ref_count_base *v32; // [rsp+90h] [rbp-148h]
  _BYTE v33[56]; // [rsp+98h] [rbp-140h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-108h]
  HSTRING v35; // [rsp+D8h] [rbp-100h] BYREF
  _QWORD v36[2]; // [rsp+110h] [rbp-C8h] BYREF
  _BYTE v37[64]; // [rsp+120h] [rbp-B8h] BYREF
  _DWORD v38[16]; // [rsp+160h] [rbp-78h] BYREF

  v3 = (__int64)a3;
  v27 = a3;
  v4 = a1;
  string = a1;
  v26 = a3;
  if ( a2 != 8 )
  {
    v5 = a3;
    if ( a2 == 6 )
    {
      v6 = 2;
LABEL_20:
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        v5,
        v6,
        a3);
      return std::function<long (void)>::~function<long (void)>(v3);
    }
LABEL_19:
    v6 = 0;
    goto LABEL_20;
  }
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 38),
    a3);
  *(_OWORD *)v28 = 0;
  std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(v4 + 34, v28);
  if ( v28[1] )
    std::_Ref_count_base::_Decref(v28[1]);
  v7 = *((_QWORD *)v4 + 28);
  if ( v7 )
  {
    v8 = *((_DWORD *)v4 + 64);
    v9 = *((_DWORD *)v4 + 63);
    v10 = *((_DWORD *)v4 + 62);
    v11 = *((_QWORD *)v4 + 29) - v7;
    v12 = *((_QWORD *)v4 + 33);
    v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 30);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)string + 7), 0);
    v15 = (ConnectedStorage *)WindowsGetStringRawBuffer(*((HSTRING *)string + 8), 0);
    LODWORD(v23) = v10;
    ConnectedStorage::EventWriteWebUploadSummary(v15, StringRawBuffer, v13, v12, v11, v23, v9, v8, v24);
    v3 = (__int64)v27;
    v4 = string;
  }
  LeaveCriticalSection(lpCriticalSection);
  try
  {
    v16 = (_QWORD *)std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(v4 + 2, v28);
    std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(&lpCriticalSection, v16);
    if ( v28[1] )
      std::_Ref_count_base::_Decref(v28[1]);
    v17 = ConnectedStorage::WebService::Instance();
    v18 = *(_QWORD *)v17;
    v27 = v33;
    std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(v36, &lpCriticalSection);
    std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
      (__int64)v37,
      v3);
    v34 = 0;
    v34 = std::_Global_new_std::_Func_impl_no_alloc__lambda_c7241225bf3a15771f87e7dc282d6c1a__void_enum_ConnectedStorage::WebService::Status_ConnectedStorage::SimpleHStringWrapper_const_____lambda_c7241225bf3a15771f87e7dc282d6c1a___(v36);
    v19 = *(void (__fastcall **)(struct ConnectedStorage::WebService *, _BYTE *, HSTRING *, HSTRING, HSTRING, HSTRING, ConnectedStorage::SimpleHStringWrapper *, _BYTE *))(v18 + 72);
    Json = ConnectedStorage::BlobRecords::GetJson((_QWORD *)v4 + 14, (ConnectedStorage::SimpleHStringWrapper *)&string);
    v21 = ConnectedStorage::ContextDesc::ContextDesc(&v35, (const struct ConnectedStorage::ContextDesc *)(v4 + 10));
    v19(v17, v31, v21, v4 + 22, v4 + 24, v4 + 26, Json, v33);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    WindowsDeleteString(string);
    string = 0;
    lambda_c7241225bf3a15771f87e7dc282d6c1a_::__lambda_c7241225bf3a15771f87e7dc282d6c1a_(v36);
    if ( v30 )
      std::_Ref_count_base::_Decwref(v30);
  }
  catch ( ConnectedStorage::ComError v38 )
  {
    LODWORD(string) = v38[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v38);
    if ( (int)string < 0 )
    {
LABEL_18:
      v3 = (__int64)v26;
      v5 = v26;
      goto LABEL_19;
    }
    v3 = (__int64)v26;
    return std::function<long (void)>::~function<long (void)>(v3);
  }
  catch ( std::bad_alloc )
  {
    goto LABEL_18;
  }
  catch ( ... )
  {
    goto LABEL_18;
  }
  return std::function<long (void)>::~function<long (void)>(v3);
}

```

## disassembly

```asm
0x18007bca8  mov     [rsp+arg_8], rbx
0x18007bcad  mov     [rsp+arg_18], rsi
0x18007bcb2  push    rdi
0x18007bcb3  push    r12
0x18007bcb5  push    r13
0x18007bcb7  push    r14
0x18007bcb9  push    r15
0x18007bcbb  sub     rsp, 1B0h
0x18007bcc2  mov     rax, cs:__security_cookie
0x18007bcc9  xor     rax, rsp
0x18007bccc  mov     [rsp+1D8h+var_38], rax
0x18007bcd4  mov     rbx, r8
0x18007bcd7  mov     [rsp+1D8h+var_178], rbx
0x18007bcdc  mov     rsi, rcx
0x18007bcdf  mov     [rsp+1D8h+string], rcx
0x18007bce4  mov     [rsp+1D8h+var_180], rbx
0x18007bce9  cmp     edx, 8
0x18007bcec  jz      short loc_18007BD04
0x18007bcee  mov     rcx, rbx
0x18007bcf1  cmp     edx, 6
0x18007bcf4  jnz     loc_18007BF26
0x18007bcfa  mov     edx, 2
0x18007bcff  jmp     loc_18007BF28
0x18007bd04  lea     rdx, [rcx+98h]; struct ConnectedStorage::Mutex *
0x18007bd0b  lea     rcx, [rsp+1D8h+lpCriticalSection]; this
0x18007bd10  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18007bd15  xorps   xmm0, xmm0
0x18007bd18  movdqu  xmmword ptr [rsp+1D8h+var_170], xmm0
0x18007bd1e  lea     rcx, [rsi+88h]
0x18007bd25  lea     rdx, [rsp+1D8h+var_170]
0x18007bd2a  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x18007bd2f  mov     rcx, [rsp+1D8h+var_170+8]; this
0x18007bd34  test    rcx, rcx
0x18007bd37  jz      short loc_18007BD3E
0x18007bd39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007bd3e  mov     rax, [rsi+0E0h]
0x18007bd45  test    rax, rax
0x18007bd48  jz      loc_18007BDCF
0x18007bd4e  mov     r14d, [rsi+100h]
0x18007bd55  mov     r15d, [rsi+0FCh]
0x18007bd5c  mov     r12d, [rsi+0F8h]
0x18007bd63  mov     r13, [rsi+0E8h]
0x18007bd6a  sub     r13, rax
0x18007bd6d  mov     rdi, [rsi+108h]
0x18007bd74  mov     rsi, [rsi+0F0h]
0x18007bd7b  xor     edx, edx; length
0x18007bd7d  mov     rcx, [rsp+1D8h+string]
0x18007bd82  mov     rcx, [rcx+38h]; string
0x18007bd86  call    cs:__imp_WindowsGetStringRawBuffer
0x18007bd8c  mov     rbx, rax
0x18007bd8f  xor     edx, edx; length
0x18007bd91  mov     rax, [rsp+1D8h+string]
0x18007bd96  mov     rcx, [rax+40h]; string
0x18007bd9a  call    cs:__imp_WindowsGetStringRawBuffer
0x18007bda0  mov     [rsp+1D8h+var_1A0], r14d; unsigned int
0x18007bda5  mov     [rsp+1D8h+var_1A8], r15d; unsigned int
0x18007bdaa  mov     dword ptr [rsp+1D8h+var_1B0], r12d; unsigned __int64
0x18007bdaf  mov     [rsp+1D8h+var_1B8], r13; unsigned __int64
0x18007bdb4  mov     r9, rdi; unsigned __int64
0x18007bdb7  mov     r8, rsi; unsigned __int16 *
0x18007bdba  mov     rdx, rbx; unsigned __int16 *
0x18007bdbd  mov     rcx, rax; this
0x18007bdc0  call    ?EventWriteWebUploadSummary@ConnectedStorage@@YAXQEBG0_K11III@Z; ConnectedStorage::EventWriteWebUploadSummary(ushort const * const,ushort const * const,unsigned __int64,unsigned __int64,unsigned __int64,uint,uint,uint)
0x18007bdc5  mov     rbx, [rsp+1D8h+var_178]
0x18007bdca  mov     rsi, [rsp+1D8h+string]
0x18007bdcf  mov     rcx, [rsp+1D8h+lpCriticalSection]; lpCriticalSection
0x18007bdd4  call    cs:__imp_LeaveCriticalSection
0x18007bdda  lea     rcx, [rsi+8]
0x18007bdde  lea     rdx, [rsp+1D8h+var_170]
0x18007bde3  call    ?shared_from_this@?$enable_shared_from_this@VNtmOperation@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@2@XZ; std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(void)
0x18007bde8  mov     rdx, rax
0x18007bdeb  lea     rcx, [rsp+1D8h+lpCriticalSection]
0x18007bdf0  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18007bdf5  nop
0x18007bdf6  mov     rcx, [rsp+1D8h+var_170+8]; this
0x18007bdfb  test    rcx, rcx
0x18007bdfe  jz      short loc_18007BE05
0x18007be00  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007be05  call    ?Instance@WebService@ConnectedStorage@@SAPEAV12@XZ; ConnectedStorage::WebService::Instance(void)
0x18007be0a  mov     rdi, rax
0x18007be0d  mov     r14, [rax]
0x18007be10  lea     rax, [rsp+1D8h+var_140]
0x18007be18  mov     [rsp+1D8h+var_178], rax
0x18007be1d  lea     rdx, [rsp+1D8h+lpCriticalSection]
0x18007be22  lea     rcx, [rsp+1D8h+var_C8]
0x18007be2a  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18007be2f  nop
0x18007be30  mov     rdx, rbx
0x18007be33  lea     rcx, [rsp+1D8h+var_B8]
0x18007be3b  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x18007be40  nop
0x18007be41  mov     [rsp+1D8h+var_108], 0
0x18007be4d  lea     rcx, [rsp+1D8h+var_C8]
0x18007be55  call    std___Global_new_std___Func_impl_no_alloc__lambda_c7241225bf3a15771f87e7dc282d6c1a__void_enum_ConnectedStorage__WebService__Status_ConnectedStorage__SimpleHStringWrapper_const_____lambda_c7241225bf3a15771f87e7dc282d6c1a___
0x18007be5a  mov     [rsp+1D8h+var_108], rax
0x18007be62  mov     r15, [r14+48h]
0x18007be66  lea     rcx, [rsi+70h]
0x18007be6a  lea     rdx, [rsp+1D8h+string]
0x18007be6f  call    ?GetJson@BlobRecords@ConnectedStorage@@QEBA?AVSimpleHStringWrapper@2@XZ; ConnectedStorage::BlobRecords::GetJson(void)
0x18007be74  mov     r14, rax
0x18007be77  lea     rdx, [rsi+28h]; struct ConnectedStorage::ContextDesc *
0x18007be7b  lea     rcx, [rsp+1D8h+var_100]; this
0x18007be83  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x18007be88  lea     rcx, [rsi+68h]
0x18007be8c  lea     rdx, [rsi+60h]
0x18007be90  lea     r9, [rsi+58h]
0x18007be94  lea     r8, [rsp+1D8h+var_140]
0x18007be9c  mov     qword ptr [rsp+1D8h+var_1A0], r8
0x18007bea1  mov     qword ptr [rsp+1D8h+var_1A8], r14
0x18007bea6  mov     [rsp+1D8h+var_1B0], rcx
0x18007beab  mov     [rsp+1D8h+var_1B8], rdx
0x18007beb0  mov     r8, rax
0x18007beb3  lea     rdx, [rsp+1D8h+var_150]
0x18007bebb  mov     rcx, rdi
0x18007bebe  mov     rax, r15
0x18007bec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bec6  mov     rcx, [rsp+1D8h+var_148]; this
0x18007bece  test    rcx, rcx
0x18007bed1  jz      short loc_18007BED9
0x18007bed3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007bed8  nop
0x18007bed9  mov     rcx, [rsp+1D8h+string]; string
0x18007bede  call    cs:__imp_WindowsDeleteString
0x18007bee4  mov     [rsp+1D8h+string], 0
0x18007beed  lea     rcx, [rsp+1D8h+var_C8]
0x18007bef5  call    _lambda_c7241225bf3a15771f87e7dc282d6c1a_____lambda_c7241225bf3a15771f87e7dc282d6c1a_
0x18007befa  nop
0x18007befb  mov     rcx, [rsp+1D8h+var_158]; this
0x18007bf03  test    rcx, rcx
0x18007bf06  jz      short loc_18007BF0E
0x18007bf08  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18007bf0d  nop
0x18007bf0e  jmp     short loc_18007BF2E
0x18007bf10  cmp     dword ptr [rsp+1D8h+string], 0
0x18007bf15  jl      short loc_18007BF1E
0x18007bf17  mov     rbx, [rsp+1D8h+var_180]
0x18007bf1c  jmp     short loc_18007BF2E
0x18007bf1e  mov     rbx, [rsp+1D8h+var_180]
0x18007bf23  mov     rcx, rbx
0x18007bf26  xor     edx, edx
0x18007bf28  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x18007bf2d  nop
0x18007bf2e  mov     rcx, rbx
0x18007bf31  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18007bf36  mov     rcx, [rsp+1D8h+var_38]
0x18007bf3e  xor     rcx, rsp; StackCookie
0x18007bf41  call    __security_check_cookie
0x18007bf46  lea     r11, [rsp+1D8h+var_28]
0x18007bf4e  mov     rbx, [r11+38h]
0x18007bf52  mov     rsi, [r11+48h]
0x18007bf56  mov     rsp, r11
0x18007bf59  pop     r15
0x18007bf5b  pop     r14
0x18007bf5d  pop     r13
0x18007bf5f  pop     r12
0x18007bf61  pop     rdi
0x18007bf62  retn
```
