# CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::Release(void)

- ea: `0x180002c00`
- end: `0x180002c7d`
- name: `?Release@?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@UEAAKXZ`
- size: `125`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001fd8`
- `0x180002c00`
- `0x18000d010`

## string_xrefs

- `0x180002c28`: `CWinTaskClassFactoryT<class CTempSignedLicenseExchangeTaskHandler,1>::Release`
- `0x180002c40`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::Release(volatile signed __int32 *a1)
{
  int v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( v1 >= 0 )
  {
    if ( !v1 && a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  }
  else
  {
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x365u,
      "CWinTaskClassFactoryT<class CTempSignedLicenseExchangeTaskHandler,1>::Release",
      (wchar_t *)L"Assert (%s): %s",
      L"cRef >= 0",
      L"Failed");
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002c00  push    rbx
0x180002c02  sub     rsp, 40h
0x180002c06  mov     r8, rcx
0x180002c09  or      ebx, 0FFFFFFFFh
0x180002c0c  lock xadd [rcx+8], ebx
0x180002c11  sub     ebx, 1
0x180002c14  jns     short loc_180002C5A
0x180002c16  lea     rax, aFailed; "Failed"
0x180002c1d  mov     r8d, 365h; unsigned int
0x180002c23  mov     [rsp+48h+var_18], rax
0x180002c28  lea     r9, aCwintaskclassf; "CWinTaskClassFactoryT<class CTempSigned"...
0x180002c2f  lea     rax, aCref0_0; "cRef >= 0"
0x180002c36  mov     ecx, 1; unsigned int
0x180002c3b  mov     [rsp+48h+var_20], rax
0x180002c40  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x180002c47  lea     rax, aAssertSS; "Assert (%s): %s"
0x180002c4e  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180002c53  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180002c58  jmp     short loc_180002C75
0x180002c5a  test    ebx, ebx
0x180002c5c  jnz     short loc_180002C75
0x180002c5e  test    r8, r8
0x180002c61  jz      short loc_180002C75
0x180002c63  mov     rcx, [rcx]
0x180002c66  lea     edx, [rbx+1]
0x180002c69  mov     rax, [rcx+28h]
0x180002c6d  mov     rcx, r8
0x180002c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c75  mov     eax, ebx
0x180002c77  add     rsp, 40h
0x180002c7b  pop     rbx
0x180002c7c  retn
```
