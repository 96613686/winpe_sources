# Windows::Internal::StringReference::StringReference(ushort const (&)[48])

- ea: `0x1800141b8`
- end: `0x1800141fc`
- name: `??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[48])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d28`

## callees

- `0x1800141b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800141d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800141d4`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[48])
{
  if ( WindowsCreateStringReference(
         L"Windows.Devices.Geolocation.Geofencing.Geofence",
         0x2Fu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800141b8  push    rbx
0x1800141ba  sub     rsp, 20h
0x1800141be  mov     rbx, rcx
0x1800141c1  lea     r8, [rcx+8]; hstringHeader
0x1800141c5  mov     r9, rcx; string
0x1800141c8  mov     edx, 2Fh ; '/'; length
0x1800141cd  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geofencing_Geofence@@3QBGB; "Windows.Devices.Geolocation.Geofencing."...
0x1800141d4  call    cs:__imp_WindowsCreateStringReference
0x1800141da  test    eax, eax
0x1800141dc  jns     short loc_1800141F3
0x1800141de  xor     r9d, r9d; lpArguments
0x1800141e1  xor     r8d, r8d; nNumberOfArguments
0x1800141e4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800141e9  lea     edx, [r9+1]; dwExceptionFlags
0x1800141ed  call    cs:__imp_RaiseException
0x1800141f3  mov     rax, rbx
0x1800141f6  add     rsp, 20h
0x1800141fa  pop     rbx
0x1800141fb  retn
```
