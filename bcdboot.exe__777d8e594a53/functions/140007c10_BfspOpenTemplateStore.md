# BfspOpenTemplateStore

- ea: `0x140007c10`
- end: `0x140007cd6`
- name: `BfspOpenTemplateStore`
- size: `198`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140004080`

## callees

- `0x140007c10`
- `0x14000e628`
- `0x14001bb00`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140007c66`
- `msvcrt!swprintf_s` at `0x140007c66`
- `ntdll!RtlInitUnicodeString` at `0x140007c8c`
- `ntdll!RtlInitUnicodeString` at `0x140007c8c`

## string_xrefs

- `0x140007c32`: `\System32\config\BCD-Template`
- `0x140007c76`: `Opening template from %ws.`
- `0x140007caa`: `Could not open the BCD template store. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspOpenTemplateStore(__int64 a1)
{
  __int64 v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  swprintf_s(Buffer, 0x104u, L"%s%s%s", SourceString, qword_14003F930, L"\\System32\\config\\BCD-Template", 0, 0);
  BfspLogMessage(2, L"Opening template from %ws.", Buffer);
  RtlInitUnicodeString(&DestinationString, Buffer);
  v3 = BiOpenStoreWithHash(&DestinationString, 0, v2, a1);
  v4 = v3;
  if ( v3 < 0 )
    BfspLogMessage(4, L"Could not open the BCD template store. Status = [%x]", (unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x140007c10  push    rbx
0x140007c12  sub     rsp, 260h
0x140007c19  mov     rax, cs:__security_cookie
0x140007c20  xor     rax, rsp
0x140007c23  mov     [rsp+268h+var_18], rax
0x140007c2b  mov     r9, cs:SourceString
0x140007c32  lea     rax, aSystem32Config; "\\System32\\config\\BCD-Template"
0x140007c39  mov     [rsp+268h+var_240], rax
0x140007c3e  lea     r8, aSSS; "%s%s%s"
0x140007c45  mov     rax, cs:qword_14003F930
0x140007c4c  mov     rbx, rcx
0x140007c4f  xorps   xmm0, xmm0
0x140007c52  mov     [rsp+268h+var_248], rax
0x140007c57  mov     edx, 104h; BufferCount
0x140007c5c  lea     rcx, [rsp+268h+Buffer]; Buffer
0x140007c61  movups  xmmword ptr [rsp+268h+DestinationString.Length], xmm0
0x140007c66  call    cs:__imp_swprintf_s
0x140007c6c  lea     r8, [rsp+268h+Buffer]
0x140007c71  mov     ecx, 2
0x140007c76  lea     rdx, aOpeningTemplat; "Opening template from %ws."
0x140007c7d  call    BfspLogMessage
0x140007c82  lea     rdx, [rsp+268h+Buffer]; SourceString
0x140007c87  lea     rcx, [rsp+268h+DestinationString]; DestinationString
0x140007c8c  call    cs:__imp_RtlInitUnicodeString
0x140007c92  mov     r9, rbx
0x140007c95  lea     rcx, [rsp+268h+DestinationString]
0x140007c9a  xor     edx, edx
0x140007c9c  call    BiOpenStoreWithHash
0x140007ca1  mov     ebx, eax
0x140007ca3  test    eax, eax
0x140007ca5  jns     short loc_140007CBB
0x140007ca7  mov     r8d, eax
0x140007caa  lea     rdx, aCouldNotOpenTh; "Could not open the BCD template store. "...
0x140007cb1  mov     ecx, 4
0x140007cb6  call    BfspLogMessage
0x140007cbb  mov     eax, ebx
0x140007cbd  mov     rcx, [rsp+268h+var_18]
0x140007cc5  xor     rcx, rsp; StackCookie
0x140007cc8  call    __security_check_cookie
0x140007ccd  add     rsp, 260h
0x140007cd4  pop     rbx
0x140007cd5  retn
```
