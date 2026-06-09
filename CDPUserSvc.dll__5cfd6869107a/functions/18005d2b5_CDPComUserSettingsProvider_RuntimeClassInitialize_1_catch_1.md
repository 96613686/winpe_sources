# _CDPComUserSettingsProvider::RuntimeClassInitialize_::_1_::catch$1

- ea: `0x18005d2b5`
- end: `0x18005d32d`
- name: `_CDPComUserSettingsProvider::RuntimeClassInitialize_::_1_::catch$1`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d2cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d2cc`

## string_xrefs

- `0x18005d2f6`: `..\cdpcomusersettingsprovider.cpp`
- `0x18005d2fd`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`

## pseudocode

```c
void __fastcall __noreturn CDPComUserSettingsProvider::RuntimeClassInitialize_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 160) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 176) = v3;
  *(_DWORD *)(a2 + 168) = 25;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 160,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\cdpcomusersettingsprovider.cpp",
    a2 + 168,
    a2 + 176);
}

```

## disassembly

```asm
0x18005d2b5  mov     [rsp+arg_8], rdx
0x18005d2ba  push    rbp
0x18005d2bb  sub     rsp, 30h
0x18005d2bf  mov     rbp, rdx
0x18005d2c2  mov     dword ptr [rbp+0A0h], 8000FFFFh
0x18005d2cc  call    cs:__imp_GetCurrentThreadId
0x18005d2d2  mov     [rbp+0B0h], rax
0x18005d2d9  mov     dword ptr [rbp+0A8h], 19h
0x18005d2e3  lea     rax, [rbp+0B0h]
0x18005d2ea  mov     [rsp+38h+var_18], rax
0x18005d2ef  lea     r9, [rbp+0A8h]
0x18005d2f6  lea     r8, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x18005d2fd  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005d304  lea     rcx, [rbp+0A0h]
0x18005d30b  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18005d310  mov     eax, [rbp+0A0h]
0x18005d316  mov     [rbp+0A0h], eax
0x18005d31c  mov     rax, 0
0x18005d326  add     rsp, 30h
0x18005d32a  pop     rbp
0x18005d32b  retn
```
