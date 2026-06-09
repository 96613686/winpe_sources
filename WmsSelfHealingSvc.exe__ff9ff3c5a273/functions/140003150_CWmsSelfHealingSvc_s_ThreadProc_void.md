# CWmsSelfHealingSvc::s_ThreadProc(void *)

- ea: `0x140003150`
- end: `0x14000320f`
- name: `?s_ThreadProc@CWmsSelfHealingSvc@@CAKPEAX@Z`
- size: `191`
- prototype: `__int64 __fastcall(HANDLE *Parameter, __int64, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002c94`
- `0x140003150`
- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140003193`
- `KERNEL32!IsDebuggerPresent` at `0x140003193`

## string_xrefs

- `0x14000316c`: `CWmsSelfHealingSvc::s_ThreadProc`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::s_ThreadProc(
        HANDLE *Parameter,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  if ( !Parameter )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      528,
      L"CWmsSelfHealingSvc::s_ThreadProc",
      a4,
      L"pThis");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        528,
        L"CWmsSelfHealingSvc::s_ThreadProc",
        L"ASSERT",
        L"pThis");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        528,
        L"CWmsSelfHealingSvc::s_ThreadProc",
        L"ASSERT",
        L"pThis");
  }
  return CWmsSelfHealingSvc::ThreadProc(Parameter);
}

```

## disassembly

```asm
0x140003150  mov     [rsp+arg_0], rbx
0x140003155  mov     [rsp+arg_8], rbp
0x14000315a  push    r14
0x14000315c  sub     rsp, 40h
0x140003160  mov     rbx, rcx
0x140003163  test    rcx, rcx
0x140003166  jnz     loc_1400031F7
0x14000316c  lea     rbp, aCwmsselfhealin; "CWmsSelfHealingSvc::s_ThreadProc"
0x140003173  mov     edx, 210h; unsigned int
0x140003178  lea     r14, aPthis; "pThis"
0x14000317f  mov     r8, rbp; unsigned __int16 *
0x140003182  lea     rcx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140003189  mov     [rsp+48h+var_28], r14; unsigned __int16 *
0x14000318e  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140003193  call    cs:__imp_IsDebuggerPresent
0x140003199  test    eax, eax
0x14000319b  lea     rax, aAssert; "ASSERT"
0x1400031a2  jz      short loc_1400031D1
0x1400031a4  mov     [rsp+48h+var_18], r14
0x1400031a9  lea     r8, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400031b0  mov     [rsp+48h+var_20], rax
0x1400031b5  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400031bc  mov     r9d, 210h
0x1400031c2  mov     [rsp+48h+var_28], rbp
0x1400031c7  lea     ecx, [rbx+2]; unsigned __int8
0x1400031ca  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400031cf  jmp     short loc_1400031F7
0x1400031d1  mov     [rsp+48h+var_20], r14
0x1400031d6  lea     rdx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400031dd  mov     r9, rbp
0x1400031e0  mov     [rsp+48h+var_28], rax
0x1400031e5  mov     r8d, 210h
0x1400031eb  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400031f2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400031f7  mov     rcx, rbx; this
0x1400031fa  mov     rbx, [rsp+48h+arg_0]
0x1400031ff  mov     rbp, [rsp+48h+arg_8]
0x140003204  add     rsp, 40h
0x140003208  pop     r14
0x14000320a  jmp     ?ThreadProc@CWmsSelfHealingSvc@@AEAAJXZ; CWmsSelfHealingSvc::ThreadProc(void)
```
