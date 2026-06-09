# SIPolicyPmGetBootPartitionPolicyFolder

- ea: `0x180022404`
- end: `0x180022475`
- name: `SIPolicyPmGetBootPartitionPolicyFolder`
- size: `113`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020b44`
- `0x180020e20`
- `0x180021270`
- `0x1800226d8`

## callees

- `0x180022404`
- `0x180022ca4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180022451`
- `ntdll!RtlInitUnicodeString` at `0x180022451`
- `ntdll!RtlFreeUnicodeString` at `0x180022462`
- `ntdll!RtlFreeUnicodeString` at `0x180022462`

## string_xrefs

- `0x18002241e`: `\SystemRoot\System32\CodeIntegrity`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetBootPartitionPolicyFolder(struct _UNICODE_STRING *a1, const UNICODE_STRING *a2)
{
  int v3; // edi
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v5.Length = 4587588;
  v5.Buffer = L"\\SystemRoot\\System32\\CodeIntegrity";
  DestinationString = 0;
  v3 = SIPolicyBuildPath(&v5, a2, &DestinationString);
  if ( v3 >= 0 )
  {
    *a1 = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
    a1[1].Length = 1;
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022404  mov     r11, rsp
0x180022407  mov     [r11+8], rbx
0x18002240b  push    rdi
0x18002240c  sub     rsp, 40h
0x180022410  mov     rbx, rcx
0x180022413  mov     qword ptr [r11-28h], 460044h
0x18002241b  xorps   xmm0, xmm0
0x18002241e  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\System32\\CodeIntegrity"
0x180022425  lea     rcx, [r11-28h]; Source
0x180022429  mov     [r11-20h], rax
0x18002242d  lea     r8, [r11-18h]
0x180022431  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180022436  call    SIPolicyBuildPath
0x18002243b  mov     edi, eax
0x18002243d  test    eax, eax
0x18002243f  js      short loc_18002245D
0x180022441  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x180022446  xor     edx, edx; SourceString
0x180022448  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18002244d  movdqu  xmmword ptr [rbx], xmm0
0x180022451  call    cs:__imp_RtlInitUnicodeString
0x180022457  mov     word ptr [rbx+10h], 1
0x18002245d  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x180022462  call    cs:__imp_RtlFreeUnicodeString
0x180022468  mov     rbx, [rsp+48h+arg_0]
0x18002246d  mov     eax, edi
0x18002246f  add     rsp, 40h
0x180022473  pop     rdi
0x180022474  retn
```
