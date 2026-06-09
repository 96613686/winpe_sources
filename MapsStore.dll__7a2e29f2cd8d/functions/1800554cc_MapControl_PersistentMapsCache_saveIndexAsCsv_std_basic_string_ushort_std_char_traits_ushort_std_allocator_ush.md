# MapControl::PersistentMapsCache::saveIndexAsCsv(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800554cc`
- end: `0x18005579d`
- name: `?saveIndexAsCsv@PersistentMapsCache@MapControl@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x1800551c0`

## callees

- `0x18000d090`
- `0x1800126c4`
- `0x180012720`
- `0x180016548`
- `0x1800165dc`
- `0x180016cbc`
- `0x180017da0`
- `0x18001b9e0`
- `0x180021d80`
- `0x18002da34`
- `0x18002f724`
- `0x18002f774`
- `0x18002f7b4`
- `0x18003c84c`
- `0x18004df64`
- `0x18004e1c8`
- `0x180053428`
- `0x1800554cc`
- `0x180077bdc`
- `0x180077cac`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800555c7`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800555c7`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180055528`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180055632`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180055528`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180055632`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x180055622`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x180055622`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18005557d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x180055594`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800555ab`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800555e2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18005557d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x180055594`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800555ab`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800555e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005553d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005553d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005564d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005564d`

## string_xrefs

- `0x18005550d`: `DataType, version, id, persist, size, File Path, File on disk`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall MapControl::PersistentMapsCache::saveIndexAsCsv(__int64 a1, int a2)
{
  __int64 v4; // rax
  int *v5; // rdi
  int *i; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  int v22; // r9d
  __int64 v23; // r8
  __int64 v24; // r10
  _BYTE v26[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v30; // [rsp+50h] [rbp-B0h]
  _BYTE v31[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[232]; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v34)(); // [rsp+160h] [rbp+60h] BYREF
  __int64 v35; // [rsp+168h] [rbp+68h] BYREF
  char v36; // [rsp+170h] [rbp+70h]
  __int64 v37; // [rsp+178h] [rbp+78h]
  _QWORD v38[3]; // [rsp+180h] [rbp+80h] BYREF
  char v39; // [rsp+198h] [rbp+98h]
  __int64 v40; // [rsp+1A0h] [rbp+A0h]
  _QWORD *v41; // [rsp+1B8h] [rbp+B8h]
  _BYTE v42[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v31);
  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         v32,
         "DataType, version, id, persist, size, File Path, File on disk");
  std::basic_ostream<unsigned short>::operator<<(v4, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v27 = a1 + 176;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  v5 = *(int **)(a1 + 224);
  for ( i = *(int **)v5; i != v5; i = *(int **)i )
  {
    std::wstring::wstring(&v34);
    MapControl::PersistentMapsCache::buildPath(i + 4, (__int64)&v34);
    v7 = std::basic_ostream<unsigned short>::operator<<(v32, (unsigned int)i[5]);
    v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, ", ");
    v9 = std::basic_ostream<unsigned short>::operator<<(v8, (unsigned int)i[6]);
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, ", ");
    v11 = std::basic_ostream<unsigned short>::operator<<(v10, (unsigned int)i[4]);
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, ", ");
    v13 = std::basic_ostream<unsigned short>::operator<<(v12, *(unsigned __int8 *)(*((_QWORD *)i + 4) + 16LL));
    v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, ", ");
    v15 = std::basic_ostream<unsigned short>::operator<<(v14, *(unsigned int *)(*((_QWORD *)i + 4) + 12LL));
    v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, ", ");
    v17 = std::operator<<<unsigned short>(v16, &v34);
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, ", ");
    LOBYTE(v19) = Pal::IO::fileExists(&v34, *(unsigned int *)(a1 + 384));
    v20 = std::basic_ostream<unsigned short>::operator<<(v18, v19);
    std::basic_ostream<unsigned short>::operator<<(v20, std::endl<unsigned short,std::char_traits<unsigned short>>);
    std::wstring::_Tidy_deallocate(&v34);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  Pal::ManualResetEvent::ManualResetEvent((Pal::ManualResetEvent *)v26);
  std::basic_stringbuf<unsigned short>::str(v33, v42);
  v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
  Pal::IO::beginWriteFile((unsigned int)&v29, a2, v21, v22, *(_DWORD *)(a1 + 384));
  v28 = v26;
  v27 = a1;
  v34 = MapControl::PersistentMapsCache::indexWriteDone;
  std::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>(
    &v35,
    &v27,
    v23,
    &v28);
  v38[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),MapControl::PersistentMapsCache *,std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable';
  v38[1] = v34;
  v38[2] = v35;
  v39 = v36;
  v40 = v37;
  v41 = v38;
  Pal::AsyncOperation<unsigned __int64>::setCallback(v24, v38);
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy(v38);
  Pal::ManualResetEvent::wait((Pal::ManualResetEvent *)v26);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  std::wstring::_Tidy_deallocate(v42);
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(v26);
  return std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v31);
}

```

## disassembly

```asm
0x1800554cc  mov     [rsp-8+arg_10], rbx
0x1800554d1  push    rbp
0x1800554d2  push    rsi
0x1800554d3  push    rdi
0x1800554d4  push    r12
0x1800554d6  push    r13
0x1800554d8  push    r14
0x1800554da  push    r15
0x1800554dc  lea     rbp, [rsp-0F0h]
0x1800554e4  sub     rsp, 1F0h
0x1800554eb  mov     rax, cs:__security_cookie
0x1800554f2  xor     rax, rsp
0x1800554f5  mov     [rbp+120h+var_40], rax
0x1800554fc  mov     r12, rdx
0x1800554ff  mov     r15, rcx
0x180055502  lea     rcx, [rsp+220h+var_1C0]
0x180055507  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18005550c  nop
0x18005550d  lea     rdx, aDatatypeVersio; "DataType, version, id, persist, size, F"...
0x180055514  lea     rcx, [rsp+220h+var_1B0]
0x180055519  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18005551e  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180055525  mov     rcx, rax
0x180055528  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18005552e  lea     rbx, [r15+0B0h]
0x180055535  mov     [rsp+220h+var_1E8], rbx
0x18005553a  mov     rcx, rbx; lpCriticalSection
0x18005553d  call    cs:__imp_EnterCriticalSection
0x180055543  nop
0x180055544  mov     rdi, [r15+0E0h]
0x18005554b  mov     rsi, [rdi]
0x18005554e  lea     r13, asc_1800C5150; ", "
0x180055555  cmp     rsi, rdi
0x180055558  jz      loc_18005564A
0x18005555e  lea     rcx, [rbp+120h+var_C0]
0x180055562  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180055567  nop
0x180055568  lea     rdx, [rbp+120h+var_C0]
0x18005556c  lea     rcx, [rsi+10h]
0x180055570  call    ?buildPath@PersistentMapsCache@MapControl@@SAXAEBUPersistentDataKey@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::PersistentMapsCache::buildPath(MapControl::PersistentDataKey const &,std::wstring *)
0x180055575  mov     edx, [rsi+14h]
0x180055578  lea     rcx, [rsp+220h+var_1B0]
0x18005557d  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x180055583  mov     rcx, rax
0x180055586  mov     rdx, r13
0x180055589  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18005558e  mov     edx, [rsi+18h]
0x180055591  mov     rcx, rax
0x180055594  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x18005559a  mov     rcx, rax
0x18005559d  mov     rdx, r13
0x1800555a0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800555a5  mov     edx, [rsi+10h]
0x1800555a8  mov     rcx, rax
0x1800555ab  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x1800555b1  mov     rcx, rax
0x1800555b4  mov     rdx, r13
0x1800555b7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800555bc  mov     rcx, [rsi+20h]
0x1800555c0  movzx   edx, byte ptr [rcx+10h]
0x1800555c4  mov     rcx, rax
0x1800555c7  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x1800555cd  mov     rcx, rax
0x1800555d0  mov     rdx, r13
0x1800555d3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800555d8  mov     rdx, [rsi+20h]
0x1800555dc  mov     edx, [rdx+0Ch]
0x1800555df  mov     rcx, rax
0x1800555e2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x1800555e8  mov     rcx, rax
0x1800555eb  mov     rdx, r13
0x1800555ee  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800555f3  mov     rcx, rax
0x1800555f6  lea     rdx, [rbp+120h+var_C0]
0x1800555fa  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800555ff  mov     rcx, rax
0x180055602  mov     rdx, r13
0x180055605  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18005560a  mov     r14, rax
0x18005560d  mov     edx, [r15+180h]
0x180055614  lea     rcx, [rbp+120h+var_C0]
0x180055618  call    ?fileExists@IO@Pal@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z; Pal::IO::fileExists(std::wstring const &,Pal::FileLocation)
0x18005561d  mov     dl, al
0x18005561f  mov     rcx, r14
0x180055622  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z; std::basic_ostream<ushort>::operator<<(bool)
0x180055628  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x18005562f  mov     rcx, rax
0x180055632  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180055638  nop
0x180055639  lea     rcx, [rbp+120h+var_C0]
0x18005563d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055642  mov     rsi, [rsi]
0x180055645  jmp     loc_180055555
0x18005564a  mov     rcx, rbx; lpCriticalSection
0x18005564d  call    cs:__imp_LeaveCriticalSection
0x180055653  lea     rcx, [rsp+220h+var_1F0]; this
0x180055658  call    ??0ManualResetEvent@Pal@@QEAA@XZ; Pal::ManualResetEvent::ManualResetEvent(void)
0x18005565d  nop
0x18005565e  lea     rdx, [rbp+120h+var_60]
0x180055665  lea     rcx, [rsp+220h+var_1A8]
0x18005566a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18005566f  nop
0x180055670  mov     r9, [rbp+120h+var_50]
0x180055677  add     r9, r9
0x18005567a  lea     rcx, [rbp+120h+var_60]
0x180055681  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055686  mov     r8, rax
0x180055689  mov     eax, [r15+180h]
0x180055690  mov     [rsp+220h+var_200], eax
0x180055694  mov     rdx, r12
0x180055697  lea     rcx, [rsp+220h+var_1D8]
0x18005569c  call    ?beginWriteFile@IO@Pal@@SA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEBX_KW4FileLocation@2@@Z; Pal::IO::beginWriteFile(std::wstring const &,void const *,unsigned __int64,Pal::FileLocation)
0x1800556a1  nop
0x1800556a2  mov     r10, [rsp+220h+var_1D8]
0x1800556a7  lea     rax, [rsp+220h+var_1F0]
0x1800556ac  mov     [rsp+220h+var_1E0], rax
0x1800556b1  mov     [rsp+220h+var_1E8], r15
0x1800556b6  lea     rax, ?indexWriteDone@PersistentMapsCache@MapControl@@AEAAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@Z; MapControl::PersistentMapsCache::indexWriteDone(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *)
0x1800556bd  mov     [rbp+120h+var_C0], rax
0x1800556c1  lea     r9, [rsp+220h+var_1E0]
0x1800556c6  lea     rdx, [rsp+220h+var_1E8]
0x1800556cb  lea     rcx, [rbp+120h+var_B8]
0x1800556cf  call    ??$?0PEAVPersistentMapsCache@MapControl@@AEBU?$_Ph@$00@std@@PEAVManualResetEvent@Pal@@$0A@@?$tuple@PEAVPersistentMapsCache@MapControl@@U?$_Ph@$00@std@@PEAVManualResetEvent@Pal@@@std@@QEAA@$$QEAPEAVPersistentMapsCache@MapControl@@AEBU?$_Ph@$00@1@$$QEAPEAVManualResetEvent@Pal@@@Z; std::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>(MapControl::PersistentMapsCache * &&,std::_Ph<1> const &,Pal::ManualResetEvent * &&)
0x1800556d4  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8PersistentMapsCache@MapControl@@EAAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@6@@ZPEAV34@AEBU?$_Ph@$00@2@PEAV76@@std@@XAEAV?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),MapControl::PersistentMapsCache *,std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable'
0x1800556db  mov     [rbp+120h+var_A0], rcx
0x1800556e2  mov     rax, [rbp+120h+var_C0]
0x1800556e6  mov     [rbp+120h+var_98], rax
0x1800556ed  mov     rax, [rbp+120h+var_B8]
0x1800556f1  mov     [rbp+120h+var_90], rax
0x1800556f8  mov     al, [rbp+120h+var_B0]
0x1800556fb  mov     [rbp+120h+var_88], al
0x180055701  mov     rax, [rbp+120h+var_A8]
0x180055705  mov     [rbp+120h+var_80], rax
0x18005570c  lea     rax, [rbp+120h+var_A0]
0x180055713  mov     [rbp+120h+var_68], rax
0x18005571a  lea     rdx, [rbp+120h+var_A0]
0x180055721  mov     rcx, r10
0x180055724  call    ?setCallback@?$AsyncOperation@_K@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@_K@Pal@@@Z@std@@@Z; Pal::AsyncOperation<unsigned __int64>::setCallback(std::function<void (Pal::AsyncOperation<unsigned __int64> &)> const &)
0x180055729  nop
0x18005572a  lea     rcx, [rbp+120h+var_A0]
0x180055731  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x180055736  lea     rcx, [rsp+220h+var_1F0]; this
0x18005573b  call    ?wait@ManualResetEvent@Pal@@QEAAXXZ; Pal::ManualResetEvent::wait(void)
0x180055740  nop
0x180055741  mov     rcx, [rsp+220h+var_1D0]; this
0x180055746  test    rcx, rcx
0x180055749  jz      short loc_180055751
0x18005574b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055750  nop
0x180055751  lea     rcx, [rbp+120h+var_60]
0x180055758  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005575d  nop
0x18005575e  lea     rcx, [rsp+220h+var_1F0]
0x180055763  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180055768  nop
0x180055769  lea     rcx, [rsp+220h+var_1C0]
0x18005576e  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x180055773  mov     rcx, [rbp+120h+var_40]
0x18005577a  xor     rcx, rsp; StackCookie
0x18005577d  call    __security_check_cookie
0x180055782  mov     rbx, [rsp+220h+arg_10]
0x18005578a  add     rsp, 1F0h
0x180055791  pop     r15
0x180055793  pop     r14
0x180055795  pop     r13
0x180055797  pop     r12
0x180055799  pop     rdi
0x18005579a  pop     rsi
0x18005579b  pop     rbp
0x18005579c  retn
```
