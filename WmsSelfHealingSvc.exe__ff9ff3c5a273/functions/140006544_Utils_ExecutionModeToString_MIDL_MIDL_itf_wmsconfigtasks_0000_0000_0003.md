# Utils::ExecutionModeToString(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003)

- ea: `0x140006544`
- end: `0x140006603`
- name: `?ExecutionModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@@Z`
- size: `191`
- prototype: `const unsigned __int16 *__fastcall(unsigned int, unsigned int, const struct Utils::SStringMap *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400024d4`
- `0x140002838`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x140006544`
- `0x14000660c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140006586`
- `KERNEL32!IsDebuggerPresent` at `0x140006586`

## string_xrefs

- `0x140006575`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`
- `0x14000659c`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`
- `0x1400065cb`: `termsrv\wms\src\common\srcutils\debughelpers.cpp`

## pseudocode

```c
const unsigned __int16 *__fastcall Utils::ExecutionModeToString(
        unsigned int a1,
        unsigned int a2,
        const struct Utils::SStringMap *a3,
        const unsigned __int16 *a4)
{
  if ( a1 >= 5 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp",
      0x432u,
      L"Utils::ExecutionModeToString",
      a4,
      L"eMode < ARRAYSIZE (s_rgStringMap)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp",
        1074,
        L"Utils::ExecutionModeToString",
        L"ASSERT",
        L"eMode < ARRAYSIZE (s_rgStringMap)");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\debughelpers.cpp",
        1074,
        L"Utils::ExecutionModeToString",
        L"ASSERT",
        L"eMode < ARRAYSIZE (s_rgStringMap)");
  }
  return Utils::StringTableHelper((Utils *)a1, a2, a3, (unsigned __int64)a4);
}

```

## disassembly

```asm
0x140006544  mov     [rsp+arg_0], rbx
0x140006549  mov     [rsp+arg_8], rbp
0x14000654e  push    r14
0x140006550  sub     rsp, 40h
0x140006554  mov     ebx, ecx
0x140006556  cmp     ecx, 5
0x140006559  jb      loc_1400065EC
0x14000655f  lea     rbp, aUtilsExecution; "Utils::ExecutionModeToString"
0x140006566  mov     edx, 432h; unsigned int
0x14000656b  lea     r14, aEmodeArraysize; "eMode < ARRAYSIZE (s_rgStringMap)"
0x140006572  mov     r8, rbp; unsigned __int16 *
0x140006575  lea     rcx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x14000657c  mov     [rsp+48h+var_28], r14; unsigned __int16 *
0x140006581  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140006586  call    cs:__imp_IsDebuggerPresent
0x14000658c  test    eax, eax
0x14000658e  lea     rax, aAssert; "ASSERT"
0x140006595  jz      short loc_1400065C6
0x140006597  mov     [rsp+48h+var_18], r14
0x14000659c  lea     r8, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x1400065a3  mov     [rsp+48h+var_20], rax
0x1400065a8  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400065af  mov     r9d, 432h
0x1400065b5  mov     [rsp+48h+var_28], rbp
0x1400065ba  mov     ecx, 2; unsigned __int8
0x1400065bf  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400065c4  jmp     short loc_1400065EC
0x1400065c6  mov     [rsp+48h+var_20], r14
0x1400065cb  lea     rdx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\de"...
0x1400065d2  mov     r9, rbp
0x1400065d5  mov     [rsp+48h+var_28], rax
0x1400065da  mov     r8d, 432h
0x1400065e0  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400065e7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400065ec  mov     ecx, ebx; this
0x1400065ee  mov     rbx, [rsp+48h+arg_0]
0x1400065f3  mov     rbp, [rsp+48h+arg_8]
0x1400065f8  add     rsp, 40h
0x1400065fc  pop     r14
0x1400065fe  jmp     ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
```
