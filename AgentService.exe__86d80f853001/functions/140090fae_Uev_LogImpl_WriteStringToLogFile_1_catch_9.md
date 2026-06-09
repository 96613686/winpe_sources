# _Uev::LogImpl::WriteStringToLogFile_::_1_::catch$9

- ea: `0x140090fae`
- end: `0x14009107b`
- name: `_Uev::LogImpl::WriteStringToLogFile_::_1_::catch$9`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000ba60`
- `0x14000c2b8`
- `0x1400205f4`
- `0x140020cd4`
- `0x140090fae`
- `0x14009b010`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140090ff1`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140090ff1`

## string_xrefs

- `0x140091034`: `Common`
- `0x140091045`: `LogImpl::WriteStringToLogFile() - Failed to write message to local debug log file. Debug logging to the local file will be disabled.`

## pseudocode

```c
__int64 __fastcall Uev::LogImpl::WriteStringToLogFile_::_1_::catch_9(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = a2[9];
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
  *((_OWORD *)a2 + 5) = 0;
  a2[12] = 0;
  a2[13] = 0;
  std::wstring::_Construct<1,wchar_t *>(a2 + 10, L"Common", 6u);
  Uev::LogImpl::Write(
    v3,
    8,
    a2 + 10,
    L"LogImpl::WriteStringToLogFile() - Failed to write message to local debug log file. Debug logging to the local file w"
     "ill be disabled.");
  std::wstring::_Tidy_deallocate(a2 + 10);
  return 0;
}

```

## disassembly

```asm
0x140090fae  mov     [rsp+arg_8], rdx
0x140090fb3  push    rbx
0x140090fb4  push    rbp
0x140090fb5  push    rdi
0x140090fb6  sub     rsp, 40h
0x140090fba  mov     rbp, rdx
0x140090fbd  mov     rdi, [rbp+48h]
0x140090fc1  mov     rbx, [rdi+48h]
0x140090fc5  mov     qword ptr [rdi+48h], 0
0x140090fcd  test    rbx, rbx
0x140090fd0  jz      short loc_140091017
0x140090fd2  lea     rcx, [rbx+8]
0x140090fd6  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x140090fdb  test    rax, rax
0x140090fde  jnz     short loc_140090FF7
0x140090fe0  mov     rax, [rbx]
0x140090fe3  movsxd  rcx, dword ptr [rax+4]
0x140090fe7  add     rcx, rbx
0x140090fea  xor     r8d, r8d
0x140090fed  lea     edx, [r8+2]
0x140090ff1  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140090ff7  mov     rax, [rbx]
0x140090ffa  movsxd  rcx, dword ptr [rax+4]
0x140090ffe  add     rcx, rbx
0x140091001  movsxd  rdx, dword ptr [rax+4]
0x140091005  mov     rax, [rdx+rbx]
0x140091009  mov     edx, 1
0x14009100e  mov     rax, [rax]
0x140091011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091016  nop
0x140091017  xorps   xmm0, xmm0
0x14009101a  movups  xmmword ptr [rbp+50h], xmm0
0x14009101e  mov     qword ptr [rbp+60h], 0
0x140091026  mov     qword ptr [rbp+68h], 0
0x14009102e  mov     r8d, 6
0x140091034  lea     rdx, aCommon; "Common"
0x14009103b  lea     rcx, [rbp+50h]
0x14009103f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140091044  nop
0x140091045  lea     r9, aLogimplWritest; "LogImpl::WriteStringToLogFile() - Faile"...
0x14009104c  lea     r8, [rbp+50h]
0x140091050  mov     edx, 8
0x140091055  mov     rcx, rdi
0x140091058  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14009105d  nop
0x14009105e  lea     rcx, [rbp+50h]
0x140091062  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140091067  nop
0x140091068  mov     rax, 0
0x140091072  add     rsp, 40h
0x140091076  pop     rdi
0x140091077  pop     rbp
0x140091078  pop     rbx
0x140091079  retn
```
