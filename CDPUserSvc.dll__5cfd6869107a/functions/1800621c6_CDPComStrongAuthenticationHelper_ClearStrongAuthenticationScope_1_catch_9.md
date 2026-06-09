# _CDPComStrongAuthenticationHelper::ClearStrongAuthenticationScope_::_1_::catch$9

- ea: `0x1800621c6`
- end: `0x180062226`
- name: `_CDPComStrongAuthenticationHelper::ClearStrongAuthenticationScope_::_1_::catch$9`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800621da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800621da`

## string_xrefs

- `0x1800621ff`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`
- `0x1800621f8`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
void __fastcall __noreturn CDPComStrongAuthenticationHelper::ClearStrongAuthenticationScope_::_1_::catch_9(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 48) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 52) = 122;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 48,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\cdpcomstrongauthenticationhelper.cpp",
    a2 + 52,
    a2 + 56);
}

```

## disassembly

```asm
0x1800621c6  mov     [rsp+arg_8], rdx
0x1800621cb  push    rbp
0x1800621cc  sub     rsp, 30h
0x1800621d0  mov     rbp, rdx
0x1800621d3  mov     dword ptr [rbp+30h], 8000FFFFh
0x1800621da  call    cs:__imp_GetCurrentThreadId
0x1800621e0  mov     [rbp+38h], rax
0x1800621e4  mov     dword ptr [rbp+34h], 7Ah ; 'z'
0x1800621eb  lea     rax, [rbp+38h]
0x1800621ef  mov     [rsp+38h+var_18], rax
0x1800621f4  lea     r9, [rbp+34h]
0x1800621f8  lea     r8, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800621ff  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180062206  lea     rcx, [rbp+30h]
0x18006220a  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18006220f  mov     eax, [rbp+30h]
0x180062212  mov     [rbp+34h], eax
0x180062215  mov     rax, 0
0x18006221f  add     rsp, 30h
0x180062223  pop     rbp
0x180062224  retn
```
