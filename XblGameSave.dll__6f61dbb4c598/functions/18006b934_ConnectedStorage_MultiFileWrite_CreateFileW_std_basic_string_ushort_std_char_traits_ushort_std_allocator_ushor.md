# ConnectedStorage::MultiFileWrite::CreateFileW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006b934`
- end: `0x18006badd`
- name: `?CreateFileW@MultiFileWrite@ConnectedStorage@@QEAA?AV?$shared_ptr@VFile@ConnectedStorage@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0@Z`
- size: `425`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180049e54`
- `0x18004a8c8`
- `0x18005d1a0`
- `0x1800622b0`
- `0x180065a04`
- `0x180072068`

## callees

- `0x180004078`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18003ee9c`
- `0x18004ec4c`
- `0x18006b0c0`
- `0x18006b25c`
- `0x18006b42c`
- `0x18006b4b0`
- `0x18006b5f0`
- `0x18006b934`
- `0x18006bae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006baab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006baab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ba99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b9a1`

## string_xrefs

- `0x18006bacb`: `MultiFileWrite::CreateFile called after done`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall ConnectedStorage::MultiFileWrite::CreateFileW(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  const unsigned __int16 *v8; // r8
  HSTRING v9; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  HSTRING *v14; // rbx
  HSTRING *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  HSTRING v19; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v20; // [rsp+40h] [rbp-29h] BYREF
  __int128 v21; // [rsp+48h] [rbp-21h] BYREF
  __int128 *v22; // [rsp+58h] [rbp-11h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v24[10]; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+D0h] [rbp+67h] BYREF
  _QWORD *v26; // [rsp+D8h] [rbp+6Fh]

  v26 = a2;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 16),
    (char *)a3);
  if ( *(_DWORD *)(a1 + 64) == 1 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x8000FFFFLL,
      (int)L"MultiFileWrite::CreateFile called after done",
      v8);
  ConnectedStorage::MultiFileWrite::GenerateStagingName(&string);
  v9 = (HSTRING)operator new(0x258u);
  v19 = v9;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v11 = a3;
  else
    v11 = *(_QWORD *)a3;
  v12 = ConnectedStorage::File::File((__int64)v9, v11, (__int64)StringRawBuffer, 2, 1);
  std::shared_ptr<ConnectedStorage::File>::shared_ptr<ConnectedStorage::File>(a2, v12);
  v22 = &v21;
  v21 = 0;
  v13 = a2[1];
  if ( v13 )
  {
    *(_QWORD *)&v21 = *a2;
    *((_QWORD *)&v21 + 1) = v13;
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 12));
  }
  v14 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v19, a4);
  v15 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v20, a3);
  ConnectedStorage::MultiFileWrite::Entry::Entry(
    (__int64)v24,
    (const struct ConnectedStorage::SimpleHStringWrapper *)v15,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&string,
    (const struct ConnectedStorage::SimpleHStringWrapper *)v14,
    &v21);
  WindowsDeleteString(v20);
  v20 = 0;
  WindowsDeleteString(v19);
  v19 = 0;
  v17 = *(_QWORD *)(a1 + 80);
  if ( v17 == *(_QWORD *)(a1 + 88) )
  {
    std::vector<ConnectedStorage::MultiFileWrite::Entry>::_Emplace_reallocate<ConnectedStorage::MultiFileWrite::Entry const &>(
      (_QWORD *)(a1 + 72),
      v17,
      (__int64)v24);
  }
  else
  {
    std::_Default_allocator_traits<std::allocator<ConnectedStorage::MultiFileWrite::Entry>>::construct<ConnectedStorage::MultiFileWrite::Entry,ConnectedStorage::MultiFileWrite::Entry const &>(
      v16,
      v17,
      v24);
    *(_QWORD *)(a1 + 80) += 40LL;
  }
  ConnectedStorage::MultiFileWrite::Entry::~Entry((ConnectedStorage::MultiFileWrite::Entry *)v24);
  WindowsDeleteString(string);
  string = 0;
  LeaveCriticalSection(lpCriticalSection[0]);
  return a2;
}

```

## disassembly

```asm
0x18006b934  mov     [rsp-8+arg_10], rbx
0x18006b939  mov     [rsp-8+arg_8], rdx
0x18006b93e  push    rbp
0x18006b93f  push    rsi
0x18006b940  push    rdi
0x18006b941  push    r14
0x18006b943  push    r15
0x18006b945  lea     rbp, [rsp-37h]
0x18006b94a  sub     rsp, 0A0h
0x18006b951  mov     r15, r9
0x18006b954  mov     rsi, r8
0x18006b957  mov     rdi, rdx
0x18006b95a  mov     r14, rcx
0x18006b95d  mov     [rbp+57h+var_90], 0
0x18006b964  lea     rdx, [rcx+10h]; struct ConnectedStorage::Mutex *
0x18006b968  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18006b96c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18006b971  nop
0x18006b972  cmp     dword ptr [r14+40h], 1
0x18006b977  jz      loc_18006BACB
0x18006b97d  mov     rdx, r15
0x18006b980  lea     rcx, [rbp+57h+string]; string
0x18006b984  call    ?GenerateStagingName@MultiFileWrite@ConnectedStorage@@CA?AVSimpleHStringWrapper@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::MultiFileWrite::GenerateStagingName(std::wstring const &)
0x18006b989  nop
0x18006b98a  mov     ecx, 258h; Size
0x18006b98f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b994  mov     rbx, rax
0x18006b997  mov     [rbp+57h+var_88], rax
0x18006b99b  xor     edx, edx; length
0x18006b99d  mov     rcx, [rbp+57h+string]; string
0x18006b9a1  call    cs:__imp_WindowsGetStringRawBuffer
0x18006b9a7  cmp     qword ptr [rsi+18h], 7
0x18006b9ac  jbe     short loc_18006B9B3
0x18006b9ae  mov     rdx, [rsi]
0x18006b9b1  jmp     short loc_18006B9B6
0x18006b9b3  mov     rdx, rsi
0x18006b9b6  mov     dword ptr [rsp+0C0h+var_A0], 1
0x18006b9be  mov     r9d, 2
0x18006b9c4  mov     r8, rax
0x18006b9c7  mov     rcx, rbx
0x18006b9ca  call    ??0File@ConnectedStorage@@QEAA@PEBG0W4Access@01@W4CloseBehavior@01@@Z; ConnectedStorage::File::File(ushort const *,ushort const *,ConnectedStorage::File::Access,ConnectedStorage::File::CloseBehavior)
0x18006b9cf  nop
0x18006b9d0  mov     rdx, rax
0x18006b9d3  mov     rcx, rdi
0x18006b9d6  call    ??$?0VFile@ConnectedStorage@@$0A@@?$shared_ptr@VFile@ConnectedStorage@@@std@@QEAA@PEAVFile@ConnectedStorage@@@Z; std::shared_ptr<ConnectedStorage::File>::shared_ptr<ConnectedStorage::File>(ConnectedStorage::File *)
0x18006b9db  mov     [rbp+57h+var_90], 1
0x18006b9e2  lea     rax, [rbp+57h+var_78]
0x18006b9e6  mov     [rbp+57h+var_68], rax
0x18006b9ea  xorps   xmm0, xmm0
0x18006b9ed  movdqu  [rbp+57h+var_78], xmm0
0x18006b9f2  mov     rcx, [rdi+8]
0x18006b9f6  test    rcx, rcx
0x18006b9f9  jz      short loc_18006BA0A
0x18006b9fb  mov     rax, [rdi]
0x18006b9fe  mov     qword ptr [rbp+57h+var_78], rax
0x18006ba02  mov     qword ptr [rbp+57h+var_78+8], rcx
0x18006ba06  lock inc dword ptr [rcx+0Ch]
0x18006ba0a  mov     rdx, r15
0x18006ba0d  lea     rcx, [rbp+57h+var_88]; string
0x18006ba11  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x18006ba16  mov     rbx, rax
0x18006ba19  mov     rdx, rsi
0x18006ba1c  lea     rcx, [rbp+57h+var_80]; string
0x18006ba20  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x18006ba25  nop
0x18006ba26  lea     rcx, [rbp+57h+var_78]
0x18006ba2a  mov     [rsp+0C0h+var_A0], rcx
0x18006ba2f  mov     r9, rbx
0x18006ba32  lea     r8, [rbp+57h+string]
0x18006ba36  mov     rdx, rax
0x18006ba39  lea     rcx, [rbp+57h+var_50]
0x18006ba3d  call    ??0Entry@MultiFileWrite@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@2@00V?$weak_ptr@VFile@ConnectedStorage@@@std@@@Z; ConnectedStorage::MultiFileWrite::Entry::Entry(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::weak_ptr<ConnectedStorage::File>)
0x18006ba42  nop
0x18006ba43  mov     rcx, [rbp+57h+var_80]; string
0x18006ba47  call    cs:__imp_WindowsDeleteString
0x18006ba4d  mov     [rbp+57h+var_80], 0
0x18006ba55  mov     rcx, [rbp+57h+var_88]; string
0x18006ba59  call    cs:__imp_WindowsDeleteString
0x18006ba5f  mov     [rbp+57h+var_88], 0
0x18006ba67  mov     rdx, [r14+50h]
0x18006ba6b  lea     r8, [rbp+57h+var_50]
0x18006ba6f  cmp     rdx, [r14+58h]
0x18006ba73  jz      short loc_18006BA81
0x18006ba75  call    ??$construct@UEntry@MultiFileWrite@ConnectedStorage@@AEBU123@@?$_Default_allocator_traits@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@SAXAEAV?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@1@QEAUEntry@MultiFileWrite@ConnectedStorage@@AEBU345@@Z; std::_Default_allocator_traits<std::allocator<ConnectedStorage::MultiFileWrite::Entry>>::construct<ConnectedStorage::MultiFileWrite::Entry,ConnectedStorage::MultiFileWrite::Entry const &>(std::allocator<ConnectedStorage::MultiFileWrite::Entry> &,ConnectedStorage::MultiFileWrite::Entry * const,ConnectedStorage::MultiFileWrite::Entry const &)
0x18006ba7a  add     qword ptr [r14+50h], 28h ; '('
0x18006ba7f  jmp     short loc_18006BA8B
0x18006ba81  lea     rcx, [r14+48h]
0x18006ba85  call    ??$_Emplace_reallocate@AEBUEntry@MultiFileWrite@ConnectedStorage@@@?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@AEAAPEAUEntry@MultiFileWrite@ConnectedStorage@@QEAU234@AEBU234@@Z; std::vector<ConnectedStorage::MultiFileWrite::Entry>::_Emplace_reallocate<ConnectedStorage::MultiFileWrite::Entry const &>(ConnectedStorage::MultiFileWrite::Entry * const,ConnectedStorage::MultiFileWrite::Entry const &)
0x18006ba8a  nop
0x18006ba8b  lea     rcx, [rbp+57h+var_50]; this
0x18006ba8f  call    ??1Entry@MultiFileWrite@ConnectedStorage@@QEAA@XZ; ConnectedStorage::MultiFileWrite::Entry::~Entry(void)
0x18006ba94  nop
0x18006ba95  mov     rcx, [rbp+57h+string]; string
0x18006ba99  call    cs:__imp_WindowsDeleteString
0x18006ba9f  mov     [rbp+57h+string], 0
0x18006baa7  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18006baab  call    cs:__imp_LeaveCriticalSection
0x18006bab1  mov     rax, rdi
0x18006bab4  mov     rbx, [rsp+0C0h+arg_10]
0x18006babc  add     rsp, 0A0h
0x18006bac3  pop     r15
0x18006bac5  pop     r14
0x18006bac7  pop     rdi
0x18006bac8  pop     rsi
0x18006bac9  pop     rbp
0x18006baca  retn
0x18006bacb  lea     rdx, aMultifilewrite_4; "MultiFileWrite::CreateFile called after"...
0x18006bad2  mov     ecx, 8000FFFFh; this
0x18006bad7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
