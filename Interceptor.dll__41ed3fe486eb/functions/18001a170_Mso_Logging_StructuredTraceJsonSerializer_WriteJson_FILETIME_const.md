# Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_FILETIME const &)

- ea: `0x18001a170`
- end: `0x18001a1d4`
- name: `?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_FILETIME@@@Z`
- size: `100`
- prototype: `bool __fastcall(Mso::Logging::StructuredTraceJsonSerializer *__hidden this, FILETIME *lpFileTime)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016950`
- `0x180017f10`

## callees

- `0x18000ac10`
- `0x18001a170`
- `0x18001a3e0`
- `0x1800266e0`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x18001a19b`
- `KERNEL32!FileTimeToSystemTime` at `0x18001a19b`

## pseudocode

```c
bool __fastcall Mso::Logging::StructuredTraceJsonSerializer::WriteJson(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        FILETIME *lpFileTime)
{
  _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  SystemTime = 0;
  if ( FileTimeToSystemTime(lpFileTime, &SystemTime) )
    return Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, &SystemTime);
  MsoShipAssertTagProc(7463968);
  return 0;
}

```

## disassembly

```asm
0x18001a170  push    rbx
0x18001a172  sub     rsp, 40h
0x18001a176  mov     rax, cs:__security_cookie
0x18001a17d  xor     rax, rsp
0x18001a180  mov     [rsp+48h+var_18], rax
0x18001a185  mov     rax, rdx
0x18001a188  mov     rbx, rcx
0x18001a18b  xorps   xmm0, xmm0
0x18001a18e  lea     rdx, [rsp+48h+SystemTime]; lpSystemTime
0x18001a193  mov     rcx, rax; lpFileTime
0x18001a196  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x18001a19b  call    cs:__imp_FileTimeToSystemTime
0x18001a1a1  test    eax, eax
0x18001a1a3  jz      short loc_18001A1C5
0x18001a1a5  lea     rdx, [rsp+48h+SystemTime]; struct _SYSTEMTIME *
0x18001a1aa  mov     rcx, rbx; this
0x18001a1ad  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_SYSTEMTIME@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_SYSTEMTIME const &)
0x18001a1b2  mov     rcx, [rsp+48h+var_18]
0x18001a1b7  xor     rcx, rsp; StackCookie
0x18001a1ba  call    __security_check_cookie
0x18001a1bf  add     rsp, 40h
0x18001a1c3  pop     rbx
0x18001a1c4  retn
0x18001a1c5  mov     ecx, 71E420h
0x18001a1ca  call    MsoShipAssertTagProc
0x18001a1cf  xor     al, al
0x18001a1d1  jmp     short loc_18001A1B2
```
