# sih::mutex::CreateUserBoundaryDescriptor(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x140024520`
- end: `0x14002473b`
- name: `?CreateUserBoundaryDescriptor@mutex@sih@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteBoundaryDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `539`
- prototype: `HANDLE *__fastcall(HANDLE *, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024764`

## callees

- `0x140006fc8`
- `0x1400073f0`
- `0x14000cb54`
- `0x14000e130`
- `0x14001b640`
- `0x14001b7e8`
- `0x14001c230`
- `0x140024520`
- `0x140045dc0`
- `0x1400481f8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140024565`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140024565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024654`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140024616`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140024616`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140024630`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140024630`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x14002468d`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x14002468d`

## string_xrefs

- `0x1400246c9`: `ConvertSidToStringSid`
- `0x140024705`: `CreateBoundaryDescriptor`
- `0x140024693`: `AddSIDToBoundaryDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
HANDLE *__fastcall sih::mutex::CreateUserBoundaryDescriptor(HANDLE *a1, void *a2, _QWORD *a3)
{
  LPWSTR v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rax
  const WCHAR *v9; // rcx
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int LastErrorHr; // eax
  int v15; // ecx
  unsigned int v16; // eax
  _BYTE pExceptionObject[32]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-31h] BYREF
  HANDLE BoundaryDescriptor[2]; // [rsp+A8h] [rbp-11h] BYREF
  LPWSTR StringSid; // [rsp+B8h] [rbp-1h] BYREF
  LPCWSTR Name[2]; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v23; // [rsp+D0h] [rbp+17h]

  BoundaryDescriptor[1] = a3;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
  {
    std::string::string(v18, "ConvertSidToStringSid");
    LastErrorHr = GetLastErrorHr(v13);
    sih::hr_exception::hr_exception(pExceptionObject, LastErrorHr, v18);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v6 = StringSid;
  v7 = a3[2];
  if ( v7 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  std::wstring::wstring(v18, v7, L"_", 1);
  v8 = std::wstring::append(v18, v6);
  *(_OWORD *)Name = 0;
  v23 = 0;
  *(_OWORD *)Name = *(_OWORD *)v8;
  v23 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(v18);
  v9 = (const WCHAR *)Name;
  if ( *((_QWORD *)&v23 + 1) > 7u )
    v9 = Name[0];
  BoundaryDescriptor[0] = CreateBoundaryDescriptorW(v9, 0);
  if ( !BoundaryDescriptor[0] )
  {
    std::string::string(pExceptionObject, "CreateBoundaryDescriptor");
    v16 = GetLastErrorHr(v15);
    sih::hr_exception::hr_exception(v19, v16, pExceptionObject);
    throw (sih::hr_exception *)v19;
  }
  if ( !AddSIDToBoundaryDescriptor(BoundaryDescriptor, a2) )
  {
    DeleteBoundaryDescriptor(BoundaryDescriptor[0]);
    std::string::string(v19, "AddSIDToBoundaryDescriptor");
    v12 = GetLastErrorHr(v11);
    sih::hr_exception::hr_exception(pExceptionObject, v12, v19);
    throw (sih::hr_exception *)pExceptionObject;
  }
  *a1 = BoundaryDescriptor[0];
  std::wstring::~wstring(Name);
  if ( StringSid )
    LocalFree(StringSid);
  std::wstring::~wstring(a3);
  return a1;
}

```

## disassembly

```asm
0x140024520  mov     [rsp-8+arg_18], rbx
0x140024525  push    rbp
0x140024526  push    rsi
0x140024527  push    rdi
0x140024528  push    r14
0x14002452a  push    r15
0x14002452c  lea     rbp, [rsp-37h]
0x140024531  sub     rsp, 0F0h
0x140024538  mov     rax, cs:__security_cookie
0x14002453f  xor     rax, rsp
0x140024542  mov     [rbp+57h+var_30], rax
0x140024546  mov     rbx, r8
0x140024549  mov     rsi, rdx
0x14002454c  mov     rdi, rcx
0x14002454f  mov     [rbp+57h+StringSid], rcx
0x140024553  mov     [rbp+57h+var_60], rbx
0x140024557  xor     r15d, r15d
0x14002455a  mov     [rbp+57h+StringSid], r15
0x14002455e  lea     rdx, [rbp+57h+StringSid]; StringSid
0x140024562  mov     rcx, rsi; Sid
0x140024565  call    cs:__imp_ConvertSidToStringSidW
0x14002456b  test    eax, eax
0x14002456d  jz      loc_1400246C9
0x140024573  mov     r14, [rbp+57h+StringSid]
0x140024577  mov     rcx, [rbx+10h]
0x14002457b  mov     rax, 7FFFFFFFFFFFFFFEh
0x140024585  sub     rax, rcx
0x140024588  cmp     rax, 1
0x14002458c  jb      loc_1400246FF
0x140024592  mov     r9, rbx
0x140024595  cmp     qword ptr [rbx+18h], 7
0x14002459a  jbe     short loc_14002459F
0x14002459c  mov     r9, [rbx]
0x14002459f  mov     [rsp+110h+var_E0], 1; __int64
0x1400245a8  lea     rax, asc_1400576D8; "_"
0x1400245af  mov     [rsp+110h+Src], rax; Src
0x1400245b4  mov     [rsp+110h+var_F0], rcx; __int64
0x1400245b9  lea     rcx, [rbp+57h+var_A8]; void *
0x1400245bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1400245c2  nop
0x1400245c3  mov     rdx, r14; void *
0x1400245c6  lea     rcx, [rbp+57h+var_A8]; Src
0x1400245ca  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1400245cf  xorps   xmm0, xmm0
0x1400245d2  movups  xmmword ptr [rbp+57h+Name], xmm0
0x1400245d6  xorps   xmm1, xmm1
0x1400245d9  movdqu  [rbp+57h+var_40], xmm1
0x1400245de  movups  xmm0, xmmword ptr [rax]
0x1400245e1  movups  xmmword ptr [rbp+57h+Name], xmm0
0x1400245e5  movups  xmm1, xmmword ptr [rax+10h]
0x1400245e9  movups  [rbp+57h+var_40], xmm1
0x1400245ed  mov     [rax+10h], r15
0x1400245f1  mov     qword ptr [rax+18h], 7
0x1400245f9  mov     [rax], r15w
0x1400245fd  lea     rcx, [rbp+57h+var_A8]; void *
0x140024601  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024606  lea     rcx, [rbp+57h+Name]
0x14002460a  cmp     qword ptr [rbp+57h+var_40+8], 7
0x14002460f  cmova   rcx, [rbp+57h+Name]; Name
0x140024614  xor     edx, edx; Flags
0x140024616  call    cs:__imp_CreateBoundaryDescriptorW
0x14002461c  mov     [rbp+57h+BoundaryDescriptor], rax
0x140024620  test    rax, rax
0x140024623  jz      loc_140024705
0x140024629  mov     rdx, rsi; RequiredSid
0x14002462c  lea     rcx, [rbp+57h+BoundaryDescriptor]; BoundaryDescriptor
0x140024630  call    cs:__imp_AddSIDToBoundaryDescriptor
0x140024636  test    eax, eax
0x140024638  jz      short loc_140024689
0x14002463a  mov     rax, [rbp+57h+BoundaryDescriptor]
0x14002463e  mov     [rdi], rax
0x140024641  lea     rcx, [rbp+57h+Name]; void *
0x140024645  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002464a  nop
0x14002464b  mov     rcx, [rbp+57h+StringSid]; hMem
0x14002464f  test    rcx, rcx
0x140024652  jz      short loc_14002465B
0x140024654  call    cs:__imp_LocalFree
0x14002465a  nop
0x14002465b  mov     rcx, rbx; void *
0x14002465e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024663  mov     rax, rdi
0x140024666  mov     rcx, [rbp+57h+var_30]
0x14002466a  xor     rcx, rsp; StackCookie
0x14002466d  call    __security_check_cookie
0x140024672  mov     rbx, [rsp+110h+arg_18]
0x14002467a  add     rsp, 0F0h
0x140024681  pop     r15
0x140024683  pop     r14
0x140024685  pop     rdi
0x140024686  pop     rsi
0x140024687  pop     rbp
0x140024688  retn
0x140024689  mov     rcx, [rbp+57h+BoundaryDescriptor]; BoundaryDescriptor
0x14002468d  call    cs:__imp_DeleteBoundaryDescriptor
0x140024693  lea     rdx, aAddsidtobounda_0; "AddSIDToBoundaryDescriptor"
0x14002469a  lea     rcx, [rbp+57h+var_88]
0x14002469e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400246a3  nop
0x1400246a4  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x1400246a9  mov     edx, eax
0x1400246ab  lea     r8, [rbp+57h+var_88]
0x1400246af  lea     rcx, [rbp+57h+pExceptionObject]
0x1400246b3  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x1400246b8  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400246bf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400246c3  call    _CxxThrowException
0x1400246c9  lea     rdx, aConvertsidtost; "ConvertSidToStringSid"
0x1400246d0  lea     rcx, [rbp+57h+var_A8]
0x1400246d4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400246d9  nop
0x1400246da  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x1400246df  mov     edx, eax
0x1400246e1  lea     r8, [rbp+57h+var_A8]
0x1400246e5  lea     rcx, [rbp+57h+pExceptionObject]
0x1400246e9  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x1400246ee  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400246f5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400246f9  call    _CxxThrowException
0x1400246ff  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140024705  lea     rdx, aCreateboundary_0; "CreateBoundaryDescriptor"
0x14002470c  lea     rcx, [rbp+57h+pExceptionObject]
0x140024710  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024715  nop
0x140024716  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x14002471b  mov     edx, eax
0x14002471d  lea     r8, [rbp+57h+pExceptionObject]
0x140024721  lea     rcx, [rbp+57h+var_88]
0x140024725  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x14002472a  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140024731  lea     rcx, [rbp+57h+var_88]; pExceptionObject
0x140024735  call    _CxxThrowException
```
