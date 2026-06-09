# Windows::Globalization::Spelling::CSpellCheckerFactoryLicense::VerifyLicenseKey(ushort *)

- ea: `0x180070214`
- end: `0x180070251`
- name: `?VerifyLicenseKey@CSpellCheckerFactoryLicense@Spelling@Globalization@Windows@@SAHPEAG@Z`
- size: `61`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18006f2c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007023b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007023b`
- `OLEAUT32!__imp_SysStringLen` at `0x18007021d`
- `OLEAUT32!__imp_SysStringLen` at `0x18007021d`

## pseudocode

```c
_BOOL8 __fastcall Windows::Globalization::Spelling::CSpellCheckerFactoryLicense::VerifyLicenseKey(OLECHAR *lpString1)
{
  UINT v2; // eax

  v2 = SysStringLen(lpString1);
  return CompareStringOrdinal(
           lpString1,
           v2,
           L"VVZOQ2VtUklTblppYldSc1kybENhRmt5VG14ak0wMW5ZbGM1YTFwWGQyZGFiVGw1U1VVMVRWSjNQVDA9",
           -1,
           0) == 2;
}

```

## disassembly

```asm
0x180070214  push    rbx
0x180070216  sub     rsp, 30h
0x18007021a  mov     rbx, rcx
0x18007021d  call    cs:__imp_SysStringLen
0x180070223  or      r9d, 0FFFFFFFFh; cchCount2
0x180070227  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18007022f  mov     edx, eax; cchCount1
0x180070231  lea     r8, String2; "VVZOQ2VtUklTblppYldSc1kybENhRmt5VG14ak0"...
0x180070238  mov     rcx, rbx; lpString1
0x18007023b  call    cs:__imp_CompareStringOrdinal
0x180070241  xor     ecx, ecx
0x180070243  cmp     eax, 2
0x180070246  setz    cl
0x180070249  mov     eax, ecx
0x18007024b  add     rsp, 30h
0x18007024f  pop     rbx
0x180070250  retn
```
