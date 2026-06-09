# WxDevice::CheckUserModeServiceDetectionFileName(_UNICODE_STRING *)

- ea: `0x1400cb7cc`
- end: `0x1400cb818`
- name: `?CheckUserModeServiceDetectionFileName@WxDevice@@QEAA_NPEAU_UNICODE_STRING@@@Z`
- size: `76`
- prototype: `bool(WxDevice *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400cccb0`
- `0x1400ccd80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400cb7e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cb7e9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400cb800`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400cb800`

## pseudocode

```c
bool __fastcall WxDevice::CheckUserModeServiceDetectionFileName(const WCHAR *this, struct _UNICODE_STRING *a2)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, this + 2760);
  return RtlCompareUnicodeString(a2, &DestinationString, 1u) == 0;
}

```

## disassembly

```asm
0x1400cb7cc  push    rbx
0x1400cb7ce  sub     rsp, 30h
0x1400cb7d2  mov     rbx, rdx
0x1400cb7d5  xorps   xmm0, xmm0
0x1400cb7d8  lea     rdx, [rcx+1590h]; SourceString
0x1400cb7df  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400cb7e4  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400cb7e9  call    cs:__imp_RtlInitUnicodeString
0x1400cb7f0  nop     dword ptr [rax+rax+00h]
0x1400cb7f5  mov     r8b, 1; CaseInSensitive
0x1400cb7f8  lea     rdx, [rsp+38h+DestinationString]; String2
0x1400cb7fd  mov     rcx, rbx; String1
0x1400cb800  call    cs:__imp_RtlCompareUnicodeString
0x1400cb807  nop     dword ptr [rax+rax+00h]
0x1400cb80c  test    eax, eax
0x1400cb80e  setz    al
0x1400cb811  add     rsp, 30h
0x1400cb815  pop     rbx
0x1400cb816  retn
```
