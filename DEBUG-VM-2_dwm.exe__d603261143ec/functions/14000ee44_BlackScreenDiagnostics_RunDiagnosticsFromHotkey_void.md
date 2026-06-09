# BlackScreenDiagnostics::RunDiagnosticsFromHotkey(void)

- ea: `0x14000ee44`
- end: `0x14000eeeb`
- name: `?RunDiagnosticsFromHotkey@BlackScreenDiagnostics@@YAXXZ`
- size: `167`
- prototype: `void __fastcall(BlackScreenDiagnostics *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400038d4`
- `0x14000d840`

## callees

- `0x140005530`
- `0x14000e0d4`
- `0x14000ed0c`
- `0x14000ee44`
- `0x14000f2b4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x14000ee74`
- `RPCRT4!UuidCreate` at `0x14000ee74`
- `api-ms-win-core-util-l1-1-0!Beep` at `0x14000ee61`
- `api-ms-win-core-util-l1-1-0!Beep` at `0x14000ee61`

## pseudocode

```c
void __fastcall BlackScreenDiagnostics::RunDiagnosticsFromHotkey(BlackScreenDiagnostics *this)
{
  __int64 v1; // [rsp+20h] [rbp-38h] BYREF
  __int64 v2; // [rsp+28h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  Beep(0x1EEu, 0xC8u);
  Uuid = 0;
  UuidCreate(&Uuid);
  v2 = *(_QWORD *)std::chrono::steady_clock::now(&v1) - qword_140018650;
  std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,1000000000>,0>(
    &v1,
    &v2);
  if ( v1 < 30 )
  {
    BlackScreenDiagnostics::CBlackScreenDiagnosticReport::RunDiagnostics(0, 4, &Uuid);
  }
  else
  {
    BlackScreenDiagnostics::CBlackScreenDiagnosticReport::RunDiagnostics(0, 7, &Uuid);
    qword_140018650 = *(_QWORD *)std::chrono::steady_clock::now(&v1);
  }
}

```

## disassembly

```asm
0x14000ee44  sub     rsp, 58h
0x14000ee48  mov     rax, cs:__security_cookie
0x14000ee4f  xor     rax, rsp
0x14000ee52  mov     [rsp+58h+var_18], rax
0x14000ee57  mov     edx, 0C8h; dwDuration
0x14000ee5c  mov     ecx, 1EEh; dwFreq
0x14000ee61  call    cs:__imp_Beep
0x14000ee67  xorps   xmm0, xmm0
0x14000ee6a  lea     rcx, [rsp+58h+Uuid]; Uuid
0x14000ee6f  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x14000ee74  call    cs:__imp_UuidCreate
0x14000ee7a  lea     rcx, [rsp+58h+var_38]
0x14000ee7f  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14000ee84  lea     rdx, [rsp+58h+var_30]
0x14000ee89  mov     rcx, [rax]
0x14000ee8c  sub     rcx, cs:qword_140018650
0x14000ee93  mov     [rsp+58h+var_30], rcx
0x14000ee98  lea     rcx, [rsp+58h+var_38]
0x14000ee9d  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0DLJKMKAA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,1000000000>,0>(std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x14000eea2  xor     ecx, ecx
0x14000eea4  lea     r8, [rsp+58h+Uuid]
0x14000eea9  cmp     [rsp+58h+var_38], 1Eh
0x14000eeaf  jl      short loc_14000EECF
0x14000eeb1  lea     edx, [rcx+7]
0x14000eeb4  call    ?RunDiagnostics@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@SAXW4CallingSource@2@W4DiagnosticFlags@2@AEBU_GUID@@@Z; BlackScreenDiagnostics::CBlackScreenDiagnosticReport::RunDiagnostics(BlackScreenDiagnostics::CallingSource,BlackScreenDiagnostics::DiagnosticFlags,_GUID const &)
0x14000eeb9  lea     rcx, [rsp+58h+var_38]
0x14000eebe  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14000eec3  mov     rcx, [rax]
0x14000eec6  mov     cs:qword_140018650, rcx
0x14000eecd  jmp     short loc_14000EED9
0x14000eecf  mov     edx, 4
0x14000eed4  call    ?RunDiagnostics@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@SAXW4CallingSource@2@W4DiagnosticFlags@2@AEBU_GUID@@@Z; BlackScreenDiagnostics::CBlackScreenDiagnosticReport::RunDiagnostics(BlackScreenDiagnostics::CallingSource,BlackScreenDiagnostics::DiagnosticFlags,_GUID const &)
0x14000eed9  mov     rcx, [rsp+58h+var_18]
0x14000eede  xor     rcx, rsp; StackCookie
0x14000eee1  call    __security_check_cookie
0x14000eee6  add     rsp, 58h
0x14000eeea  retn
```
