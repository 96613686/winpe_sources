# SIPolicyPmGetOsDataPartitionPolicyFolder

- ea: `0x180021608`
- end: `0x180021679`
- name: `SIPolicyPmGetOsDataPartitionPolicyFolder`
- size: `113`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020b44`
- `0x180021270`
- `0x1800220e0`
- `0x1800226d8`

## callees

- `0x180021608`
- `0x180022ca4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180021655`
- `ntdll!RtlInitUnicodeString` at `0x180021655`
- `ntdll!RtlFreeUnicodeString` at `0x180021666`
- `ntdll!RtlFreeUnicodeString` at `0x180021666`

## string_xrefs

- `0x180021622`: `\OSDataRoot\Windows\System32\CodeIntegrity`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetOsDataPartitionPolicyFolder(struct _UNICODE_STRING *a1, const UNICODE_STRING *a2)
{
  int v3; // edi
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v5.Length = 5636180;
  v5.Buffer = (PWSTR)L"\\OSDataRoot\\Windows\\System32\\CodeIntegrity";
  DestinationString = 0;
  v3 = SIPolicyBuildPath(&v5, a2, &DestinationString);
  if ( v3 >= 0 )
  {
    *a1 = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
    a1[1].Length = 257;
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021608  mov     r11, rsp
0x18002160b  mov     [r11+8], rbx
0x18002160f  push    rdi
0x180021610  sub     rsp, 40h
0x180021614  mov     rbx, rcx
0x180021617  mov     qword ptr [r11-28h], 560054h
0x18002161f  xorps   xmm0, xmm0
0x180021622  lea     rax, aOsdatarootWind; "\\OSDataRoot\\Windows\\System32\\CodeIn"...
0x180021629  lea     rcx, [r11-28h]; Source
0x18002162d  mov     [r11-20h], rax
0x180021631  lea     r8, [r11-18h]
0x180021635  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18002163a  call    SIPolicyBuildPath
0x18002163f  mov     edi, eax
0x180021641  test    eax, eax
0x180021643  js      short loc_180021661
0x180021645  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18002164a  xor     edx, edx; SourceString
0x18002164c  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180021651  movdqu  xmmword ptr [rbx], xmm0
0x180021655  call    cs:__imp_RtlInitUnicodeString
0x18002165b  mov     word ptr [rbx+10h], 101h
0x180021661  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x180021666  call    cs:__imp_RtlFreeUnicodeString
0x18002166c  mov     rbx, [rsp+48h+arg_0]
0x180021671  mov     eax, edi
0x180021673  add     rsp, 40h
0x180021677  pop     rdi
0x180021678  retn
```
