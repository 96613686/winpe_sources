# _CDPComBeaconControl::EnsureBeaconControl_::_1_::catch$4

- ea: `0x180065d38`
- end: `0x180065d9b`
- name: `_CDPComBeaconControl::EnsureBeaconControl_::_1_::catch$4`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002b840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065d45`

## string_xrefs

- `0x180065d6f`: `.\cdpcombeaconcontrol.cpp`
- `0x180065d76`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failure creating beacon control."}`

## pseudocode

```c
void __fastcall __noreturn CDPComBeaconControl::EnsureBeaconControl_::_1_::catch_4(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 176) = v3;
  *(_DWORD *)(a2 + 168) = 51;
  cdp::CatchAllToHR<char const (&)[26],int,unsigned __int64>(
    a2 + 160,
    (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                  "Failure creating beacon control.\"}",
    (unsigned int)".\\cdpcombeaconcontrol.cpp",
    a2 + 168,
    a2 + 176);
}

```

## disassembly

```asm
0x180065d38  mov     [rsp+arg_8], rdx
0x180065d3d  push    rbp
0x180065d3e  sub     rsp, 30h
0x180065d42  mov     rbp, rdx
0x180065d45  call    cs:__imp_GetCurrentThreadId
0x180065d4b  mov     [rbp+0B0h], rax
0x180065d52  mov     dword ptr [rbp+0A8h], 33h ; '3'
0x180065d5c  lea     rax, [rbp+0B0h]
0x180065d63  mov     [rsp+38h+var_18], rax
0x180065d68  lea     r9, [rbp+0A8h]
0x180065d6f  lea     r8, aCdpcombeaconco; ".\\cdpcombeaconcontrol.cpp"
0x180065d76  lea     rdx, aHr0x08xExcepti_6; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180065d7d  lea     rcx, [rbp+0A0h]
0x180065d84  call    ??$CatchAllToHR@AEAY0BK@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0BK@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[26],int,unsigned __int64>(long &,char const *,char const (&)[26],int &&,unsigned __int64 &&)
0x180065d8a  mov     rax, 0
0x180065d94  add     rsp, 30h
0x180065d98  pop     rbp
0x180065d99  retn
```
