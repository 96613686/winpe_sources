# _CDPComAccountProvider::RuntimeClassInitialize_::_1_::catch$1

- ea: `0x18005d3a3`
- end: `0x18005d41b`
- name: `_CDPComAccountProvider::RuntimeClassInitialize_::_1_::catch$1`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3ba`

## string_xrefs

- `0x18005d3e4`: `..\cdpcomaccountprovider.cpp`
- `0x18005d3eb`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`

## pseudocode

```c
void __fastcall __noreturn CDPComAccountProvider::RuntimeClassInitialize_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 160) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 176) = v3;
  *(_DWORD *)(a2 + 168) = 21;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 160,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\cdpcomaccountprovider.cpp",
    a2 + 168,
    a2 + 176);
}

```

## disassembly

```asm
0x18005d3a3  mov     [rsp+arg_8], rdx
0x18005d3a8  push    rbp
0x18005d3a9  sub     rsp, 30h
0x18005d3ad  mov     rbp, rdx
0x18005d3b0  mov     dword ptr [rbp+0A0h], 8000FFFFh
0x18005d3ba  call    cs:__imp_GetCurrentThreadId
0x18005d3c0  mov     [rbp+0B0h], rax
0x18005d3c7  mov     dword ptr [rbp+0A8h], 15h
0x18005d3d1  lea     rax, [rbp+0B0h]
0x18005d3d8  mov     [rsp+38h+var_18], rax
0x18005d3dd  lea     r9, [rbp+0A8h]
0x18005d3e4  lea     r8, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x18005d3eb  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005d3f2  lea     rcx, [rbp+0A0h]
0x18005d3f9  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18005d3fe  mov     eax, [rbp+0A0h]
0x18005d404  mov     [rbp+0A0h], eax
0x18005d40a  mov     rax, 0
0x18005d414  add     rsp, 30h
0x18005d418  pop     rbp
0x18005d419  retn
```
