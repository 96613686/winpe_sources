# ADPDatabase::VerifyDatabaseStaticConfigurationUnderLock(void)

- ea: `0x180033db8`
- end: `0x180033f58`
- name: `?VerifyDatabaseStaticConfigurationUnderLock@ADPDatabase@@AEAAXXZ`
- size: `416`
- prototype: `void __fastcall(ADPDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180033350`

## callees

- `0x180001008`
- `0x180002250`
- `0x18000e1d0`
- `0x180013830`
- `0x1800328a0`
- `0x180033db8`
- `0x180034a80`
- `0x180034bc8`

## string_xrefs

- `0x180033e77`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033ece`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033f1c`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033e88`: `PRAGMA cache_size;`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ADPDatabase::VerifyDatabaseStaticConfigurationUnderLock(ADPDatabase *this)
{
  const wchar_t *v2; // rbx
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  char *v6; // rdx
  char *v7; // rax
  int v8; // [rsp+20h] [rbp-60h]
  int v9; // [rsp+20h] [rbp-60h]
  int v10; // [rsp+20h] [rbp-60h]
  char *v11; // [rsp+30h] [rbp-50h]
  char *v12; // [rsp+30h] [rbp-50h]
  const wchar_t *v13; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h]
  char v15[8]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = (const wchar_t *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) > 7u )
    v2 = *(const wchar_t **)v2;
  v3 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v3 > 5u )
  {
    v13 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)v3,
      (__int64)byte_1801004ED,
      v4,
      v5,
      &v13);
  }
  v13 = (const wchar_t *)"PRAGMA synchronous;";
  v14 = 19;
  sqlite3_exec_single_text_result_cpp(v15, *((_QWORD *)this + 4), &v13);
  if ( v16 > 0xF )
  {
    v6 = *(char **)v15;
    v7 = *(char **)v15;
  }
  else
  {
    v6 = v15;
    v7 = v15;
  }
  LOBYTE(v8) = *v7 != 50;
  wil::details::in1diag3::FailFast_HrIfMsg(
    retaddr,
    (void *)0x224,
    (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
    (const char *)0x8007064ALL,
    v8,
    (bool)"%hs",
    v6);
  v13 = (const wchar_t *)"PRAGMA cache_size;";
  v14 = 18;
  LODWORD(v11) = sqlite3_exec_single_int_result_cpp(*((_QWORD *)this + 4), &v13);
  LOBYTE(v9) = (_DWORD)v11 != -32000;
  wil::details::in1diag3::FailFast_HrIfMsg(
    retaddr,
    (void *)0x226,
    (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
    (const char *)0x8007064ALL,
    v9,
    (bool)"%d",
    v11);
  v13 = (const wchar_t *)"PRAGMA foreign_keys;";
  v14 = 20;
  LODWORD(v12) = sqlite3_exec_single_int_result_cpp(*((_QWORD *)this + 4), &v13);
  LOBYTE(v10) = (_DWORD)v12 != 1;
  wil::details::in1diag3::FailFast_HrIfMsg(
    retaddr,
    (void *)0x228,
    (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
    (const char *)0x8007064ALL,
    v10,
    (bool)"%d",
    v12);
  std::string::~string((char **)v15);
}

```

## disassembly

```asm
0x180033db8  mov     [rsp-8+arg_8], rbx
0x180033dbd  mov     [rsp-8+arg_10], rdi
0x180033dc2  push    rbp
0x180033dc3  mov     rbp, rsp
0x180033dc6  sub     rsp, 80h
0x180033dcd  mov     rax, cs:__security_cookie
0x180033dd4  xor     rax, rsp
0x180033dd7  mov     [rbp+var_10], rax
0x180033ddb  mov     rdi, rcx
0x180033dde  lea     rbx, [rcx+68h]
0x180033de2  cmp     qword ptr [rbx+18h], 7
0x180033de7  jbe     short loc_180033DEC
0x180033de9  mov     rbx, [rbx]
0x180033dec  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180033df1  mov     rcx, [rax+8]
0x180033df5  mov     eax, [rcx]
0x180033df7  cmp     eax, 5
0x180033dfa  jbe     short loc_180033E15
0x180033dfc  mov     [rbp+var_40], rbx
0x180033e00  lea     rax, [rbp+var_40]
0x180033e04  mov     qword ptr [rsp+80h+var_60], rax
0x180033e09  lea     rdx, byte_1801004ED
0x180033e10  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180033e15  lea     rax, aPragmaSynchron; "PRAGMA synchronous;"
0x180033e1c  mov     [rbp+var_40], rax
0x180033e20  mov     [rbp+var_38], 13h
0x180033e28  lea     r8, [rbp+var_40]
0x180033e2c  mov     rdx, [rdi+20h]
0x180033e30  lea     rcx, [rbp+var_30]
0x180033e34  call    ?sqlite3_exec_single_text_result_cpp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; sqlite3_exec_single_text_result_cpp(sqlite3 *,std::string_view)
0x180033e39  nop
0x180033e3a  cmp     [rbp+var_18], 0Fh
0x180033e3f  ja      short loc_180033E4B
0x180033e41  lea     rdx, [rbp+var_30]
0x180033e45  lea     rax, [rbp+var_30]
0x180033e49  jmp     short loc_180033E52
0x180033e4b  mov     rdx, qword ptr [rbp+var_30]
0x180033e4f  mov     rax, rdx
0x180033e52  cmp     byte ptr [rax], 32h ; '2'
0x180033e55  setnz   al
0x180033e58  mov     rcx, [rbp+8]; this
0x180033e5c  mov     [rsp+80h+var_50], rdx; char *
0x180033e61  lea     rdx, aHs; "%hs"
0x180033e68  mov     qword ptr [rsp+80h+var_58], rdx; bool
0x180033e6d  mov     byte ptr [rsp+80h+var_60], al; int
0x180033e71  mov     r9d, 8007064Ah; char *
0x180033e77  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033e7e  mov     edx, 224h; void *
0x180033e83  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033e88  lea     rax, aPragmaCacheSiz; "PRAGMA cache_size;"
0x180033e8f  mov     [rbp+var_40], rax
0x180033e93  mov     [rbp+var_38], 12h
0x180033e9b  lea     rdx, [rbp+var_40]
0x180033e9f  mov     rcx, [rdi+20h]
0x180033ea3  call    ?sqlite3_exec_single_int_result_cpp@@YAHPEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_exec_single_int_result_cpp(sqlite3 *,std::string_view)
0x180033ea8  cmp     eax, 0FFFF8300h
0x180033ead  setnz   dl
0x180033eb0  mov     rcx, [rbp+8]; this
0x180033eb4  mov     dword ptr [rsp+80h+var_50], eax; char *
0x180033eb8  lea     rbx, aD; "%d"
0x180033ebf  mov     qword ptr [rsp+80h+var_58], rbx; bool
0x180033ec4  mov     byte ptr [rsp+80h+var_60], dl; int
0x180033ec8  mov     r9d, 8007064Ah; char *
0x180033ece  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033ed5  mov     edx, 226h; void *
0x180033eda  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033edf  lea     rax, aPragmaForeignK; "PRAGMA foreign_keys;"
0x180033ee6  mov     [rbp+var_40], rax
0x180033eea  mov     [rbp+var_38], 14h
0x180033ef2  lea     rdx, [rbp+var_40]
0x180033ef6  mov     rcx, [rdi+20h]
0x180033efa  call    ?sqlite3_exec_single_int_result_cpp@@YAHPEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_exec_single_int_result_cpp(sqlite3 *,std::string_view)
0x180033eff  cmp     eax, 1
0x180033f02  setnz   dl
0x180033f05  mov     rcx, [rbp+8]; this
0x180033f09  mov     dword ptr [rsp+80h+var_50], eax; char *
0x180033f0d  mov     qword ptr [rsp+80h+var_58], rbx; bool
0x180033f12  mov     byte ptr [rsp+80h+var_60], dl; int
0x180033f16  mov     r9d, 8007064Ah; char *
0x180033f1c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033f23  mov     edx, 228h; void *
0x180033f28  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033f2d  nop
0x180033f2e  lea     rcx, [rbp+var_30]
0x180033f32  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033f37  mov     rcx, [rbp+var_10]
0x180033f3b  xor     rcx, rsp; StackCookie
0x180033f3e  call    __security_check_cookie
0x180033f43  lea     r11, [rsp+80h+var_s0]
0x180033f4b  mov     rbx, [r11+18h]
0x180033f4f  mov     rdi, [r11+20h]
0x180033f53  mov     rsp, r11
0x180033f56  pop     rbp
0x180033f57  retn
```
