# _CDPComDedupedDevice::GetTargets_::_1_::catch$11

- ea: `0x180066108`
- end: `0x18006616b`
- name: `_CDPComDedupedDevice::GetTargets_::_1_::catch$11`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002b840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066115`

## string_xrefs

- `0x18006613f`: `.\cdpcomdedupeddevice.cpp`
- `0x180066146`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failure getting targets."}`

## pseudocode

```c
void __fastcall __noreturn CDPComDedupedDevice::GetTargets_::_1_::catch_11(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 200) = v3;
  *(_DWORD *)(a2 + 192) = 210;
  cdp::CatchAllToHR<char const (&)[26],int,unsigned __int64>(
    a2 + 184,
    (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                  "Failure getting targets.\"}",
    (unsigned int)".\\cdpcomdedupeddevice.cpp",
    a2 + 192,
    a2 + 200);
}

```

## disassembly

```asm
0x180066108  mov     [rsp+arg_8], rdx
0x18006610d  push    rbp
0x18006610e  sub     rsp, 30h
0x180066112  mov     rbp, rdx
0x180066115  call    cs:__imp_GetCurrentThreadId
0x18006611b  mov     [rbp+0C8h], rax
0x180066122  mov     dword ptr [rbp+0C0h], 0D2h
0x18006612c  lea     rax, [rbp+0C8h]
0x180066133  mov     [rsp+38h+var_18], rax
0x180066138  lea     r9, [rbp+0C0h]
0x18006613f  lea     r8, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180066146  lea     rdx, aHr0x08xExcepti; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18006614d  lea     rcx, [rbp+0B8h]
0x180066154  call    ??$CatchAllToHR@AEAY0BK@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0BK@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[26],int,unsigned __int64>(long &,char const *,char const (&)[26],int &&,unsigned __int64 &&)
0x18006615a  mov     rax, 0
0x180066164  add     rsp, 30h
0x180066168  pop     rbp
0x180066169  retn
```
