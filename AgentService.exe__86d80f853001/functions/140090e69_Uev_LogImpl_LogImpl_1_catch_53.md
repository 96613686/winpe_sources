# _Uev::LogImpl::LogImpl_::_1_::catch$53

- ea: `0x140090e69`
- end: `0x140090f48`
- name: `_Uev::LogImpl::LogImpl_::_1_::catch$53`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000ba60`
- `0x14000c2b8`
- `0x1400205f4`
- `0x140020cd4`
- `0x140090e69`
- `0x14009b010`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140090eac`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140090eac`

## string_xrefs

- `0x140090ef8`: `Common`
- `0x140090f0c`: `LogImpl::LogImpl() - An error occurred while opening the local debug log file. Debug logging to the local file will be disabled.`

## pseudocode

```c
__int64 __fastcall Uev::LogImpl::LogImpl_::_1_::catch_53(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = a2[8];
  v4 = *(_QWORD *)(v3 + 72);
  *(_QWORD *)(v3 + 72) = 0;
  if ( v4 )
  {
    if ( !std::filebuf::close(v4 + 8) )
      std::ios::setstate(v4 + *(int *)(*(_QWORD *)v4 + 4LL), 2);
    (**(void (__fastcall ***)(__int64, __int64))(*(int *)(*(_QWORD *)v4 + 4LL) + v4))(
      v4 + *(int *)(*(_QWORD *)v4 + 4LL),
      1);
  }
  *((_OWORD *)a2 + 24) = 0;
  a2[50] = 0;
  a2[51] = 0;
  std::wstring::_Construct<1,wchar_t *>(a2 + 48, L"Common", 6u);
  Uev::LogImpl::Write(
    v3,
    8,
    a2 + 48,
    L"LogImpl::LogImpl() - An error occurred while opening the local debug log file. Debug logging to the local file will be disabled.");
  std::wstring::_Tidy_deallocate(a2 + 48);
  return 0;
}

```

## disassembly

```asm
0x140090e69  mov     [rsp+arg_8], rdx
0x140090e6e  push    rbx
0x140090e6f  push    rbp
0x140090e70  push    rdi
0x140090e71  sub     rsp, 30h
0x140090e75  mov     rbp, rdx
0x140090e78  mov     rdi, [rbp+40h]
0x140090e7c  mov     rbx, [rdi+48h]
0x140090e80  mov     qword ptr [rdi+48h], 0
0x140090e88  test    rbx, rbx
0x140090e8b  jz      short loc_140090ED2
0x140090e8d  lea     rcx, [rbx+8]
0x140090e91  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x140090e96  test    rax, rax
0x140090e99  jnz     short loc_140090EB2
0x140090e9b  mov     rax, [rbx]
0x140090e9e  movsxd  rcx, dword ptr [rax+4]
0x140090ea2  add     rcx, rbx
0x140090ea5  xor     r8d, r8d
0x140090ea8  lea     edx, [r8+2]
0x140090eac  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140090eb2  mov     rax, [rbx]
0x140090eb5  movsxd  rcx, dword ptr [rax+4]
0x140090eb9  add     rcx, rbx
0x140090ebc  movsxd  rdx, dword ptr [rax+4]
0x140090ec0  mov     rax, [rdx+rbx]
0x140090ec4  mov     edx, 1
0x140090ec9  mov     rax, [rax]
0x140090ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090ed1  nop
0x140090ed2  xorps   xmm0, xmm0
0x140090ed5  movups  xmmword ptr [rbp+180h], xmm0
0x140090edc  mov     qword ptr [rbp+190h], 0
0x140090ee7  mov     qword ptr [rbp+198h], 0
0x140090ef2  mov     r8d, 6
0x140090ef8  lea     rdx, aCommon; "Common"
0x140090eff  lea     rcx, [rbp+180h]
0x140090f06  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140090f0b  nop
0x140090f0c  lea     r9, aLogimplLogimpl; "LogImpl::LogImpl() - An error occurred "...
0x140090f13  lea     r8, [rbp+180h]
0x140090f1a  mov     edx, 8
0x140090f1f  mov     rcx, rdi
0x140090f22  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x140090f27  nop
0x140090f28  lea     rcx, [rbp+180h]
0x140090f2f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140090f34  nop
0x140090f35  mov     rax, 0
0x140090f3f  add     rsp, 30h
0x140090f43  pop     rdi
0x140090f44  pop     rbp
0x140090f45  pop     rbx
0x140090f46  retn
```
