# DiagHubCommon::FileLogWriter::Write(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140009f00`
- end: `0x140009f66`
- name: `?Write@FileLogWriter@DiagHubCommon@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `102`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000993c`

## callees

- `0x140009f00`
- `0x14000cd94`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140009f5f`
- `KERNEL32!EnterCriticalSection` at `0x140009f21`
- `KERNEL32!EnterCriticalSection` at `0x140009f21`
- `MSVCP140!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x140009f46`
- `MSVCP140!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x140009f46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagHubCommon::FileLogWriter::Write(__int64 a1, _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // r8

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v5 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(a1 + 48, a2, v5);
  std::basic_ostream<unsigned short>::flush(a1 + 48);
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x140009f00  mov     [rsp+arg_8], rbx
0x140009f05  mov     [rsp+arg_10], rsi
0x140009f0a  push    rdi
0x140009f0b  sub     rsp, 20h
0x140009f0f  mov     rsi, rdx
0x140009f12  mov     rdi, rcx
0x140009f15  lea     rbx, [rcx+8]
0x140009f19  mov     [rsp+28h+arg_0], rbx
0x140009f1e  mov     rcx, rbx; lpCriticalSection
0x140009f21  call    cs:__imp_EnterCriticalSection
0x140009f27  nop
0x140009f28  mov     r8, [rsi+10h]
0x140009f2c  cmp     qword ptr [rsi+18h], 7
0x140009f31  jbe     short loc_140009F36
0x140009f33  mov     rsi, [rsi]
0x140009f36  mov     rdx, rsi
0x140009f39  lea     rcx, [rdi+30h]
0x140009f3d  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x140009f42  lea     rcx, [rdi+30h]
0x140009f46  call    cs:__imp_?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x140009f4c  nop
0x140009f4d  mov     rcx, rbx
0x140009f50  mov     rbx, [rsp+28h+arg_8]
0x140009f55  mov     rsi, [rsp+28h+arg_10]
0x140009f5a  add     rsp, 20h
0x140009f5e  pop     rdi
0x140009f5f  jmp     cs:__imp_LeaveCriticalSection
```
