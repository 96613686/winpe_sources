# CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::AddRef(void)

- ea: `0x1800024b0`
- end: `0x180002513`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@UEAAKXZ`
- size: `99`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001fd8`
- `0x1800024b0`

## string_xrefs

- `0x1800024dd`: `CWinTaskClassFactoryT<class CTempSignedLicenseExchangeTaskHandler,1>::AddRef`
- `0x1800024f3`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::AddRef(__int64 a1)
{
  int v1; // ebx

  v1 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  if ( v1 <= 0 )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x35Au,
      "CWinTaskClassFactoryT<class CTempSignedLicenseExchangeTaskHandler,1>::AddRef",
      L"Assert (%s): %s",
      L"cRef > 0",
      L"Failed");
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800024b0  push    rbx
0x1800024b2  sub     rsp, 40h
0x1800024b6  mov     r10d, 1
0x1800024bc  mov     ebx, r10d
0x1800024bf  lock xadd [rcx+8], ebx
0x1800024c4  add     ebx, r10d
0x1800024c7  test    ebx, ebx
0x1800024c9  jg      short loc_18000250B
0x1800024cb  lea     rax, aFailed; "Failed"
0x1800024d2  mov     r8d, 35Ah; unsigned int
0x1800024d8  mov     [rsp+48h+var_18], rax
0x1800024dd  lea     r9, aCwintaskclassf_0; "CWinTaskClassFactoryT<class CTempSigned"...
0x1800024e4  lea     rax, aCref0; "cRef > 0"
0x1800024eb  mov     ecx, r10d; unsigned int
0x1800024ee  mov     [rsp+48h+var_20], rax
0x1800024f3  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x1800024fa  lea     rax, aAssertSS; "Assert (%s): %s"
0x180002501  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180002506  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000250b  mov     eax, ebx
0x18000250d  add     rsp, 40h
0x180002511  pop     rbx
0x180002512  retn
```
