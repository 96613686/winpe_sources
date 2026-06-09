# DpspAttemptScenarioCompletion

- ea: `0x180001ff0`
- end: `0x180002088`
- name: `DpspAttemptScenarioCompletion`
- size: `152`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002090`
- `0x180002dc0`
- `0x180003830`

## callees

- `0x180001ff0`
- `0x1800057b0`
- `0x180009090`

## string_xrefs

- `0x180002016`: `DpspAttemptScenarioCompletion`
- `0x180002063`: `DpspAttemptScenarioCompletion`

## pseudocode

```c
__int64 __fastcall DpspAttemptScenarioCompletion(struct __SESSIONINFO **a1)
{
  __int64 result; // rax
  unsigned int v2; // ebx
  int Args; // [rsp+20h] [rbp-18h]
  char Argsa[4]; // [rsp+20h] [rbp-18h]

  if ( a1 )
  {
    result = DpspValidateSession(a1[101], (struct INSTANCEINFO *)a1);
    v2 = result;
    if ( (int)result < 0 )
    {
      *(_DWORD *)Argsa = (unsigned __int16)result;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (__int64)L"DpspAttemptScenarioCompletion",
        1364,
        (const wchar_t *)L"Error = %d",
        *(_DWORD *)Argsa);
      return v2;
    }
  }
  else
  {
    Args = 87;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (__int64)L"DpspAttemptScenarioCompletion",
      1354,
      (const wchar_t *)L"Error = %d",
      Args);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001ff0  sub     rsp, 38h
0x180001ff4  mov     [rsp+38h+arg_0], 0
0x180001ffc  test    rcx, rcx
0x180001fff  jnz     short loc_180002033
0x180002001  lea     r9, aErrorD; "Error = %d"
0x180002008  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180002010  mov     r8d, 54Ah; int
0x180002016  lea     rdx, aDpspattemptsce_0; "DpspAttemptScenarioCompletion"
0x18000201d  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002024  call    WdipTraceError
0x180002029  mov     eax, 80070057h
0x18000202e  add     rsp, 38h
0x180002032  retn
0x180002033  mov     r9d, edx
0x180002036  mov     [rsp+38h+var_8], rbx
0x18000203b  mov     rdx, rcx; struct INSTANCEINFO *
0x18000203e  lea     r8, [rsp+38h+arg_0]
0x180002043  mov     rcx, [rcx+328h]; struct __SESSIONINFO *
0x18000204a  call    DpspValidateSession
0x18000204f  mov     ebx, eax
0x180002051  test    eax, eax
0x180002053  jns     short loc_18000207E
0x180002055  movzx   ecx, bx
0x180002058  lea     r9, aErrorD; "Error = %d"
0x18000205f  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180002063  lea     rdx, aDpspattemptsce_0; "DpspAttemptScenarioCompletion"
0x18000206a  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002071  mov     r8d, 554h; int
0x180002077  call    WdipTraceError
0x18000207c  mov     eax, ebx
0x18000207e  mov     rbx, [rsp+38h+var_8]
0x180002083  add     rsp, 38h
0x180002087  retn
```
