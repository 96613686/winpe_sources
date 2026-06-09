# BfspOpenTemplateStore

- ea: `0x180050344`
- end: `0x180050408`
- name: `BfspOpenTemplateStore`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18004d7e4`

## callees

- `0x1800078b0`
- `0x180008724`
- `0x18004cdd4`
- `0x180050344`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800503bf`
- `ntdll!RtlInitUnicodeString` at `0x1800503bf`
- `bcd!BcdOpenStoreFromFile` at `0x1800503cd`
- `bcd!BcdOpenStoreFromFile` at `0x1800503cd`

## string_xrefs

- `0x180050366`: `\System32\config\BCD-Template`
- `0x1800503dc`: `Could not open the BCD template store. Status = [%x]`
- `0x1800503a9`: `Opening template from %ws.`

## pseudocode

```c
__int64 __fastcall BfspOpenTemplateStore(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  swprintf_s(Buffer, 0x104u, L"%s%s%s", qword_1800A4550, qword_1800A4570, L"\\System32\\config\\BCD-Template", 0, 0);
  BfspLogMessage(2, L"Opening template from %ws.", Buffer);
  RtlInitUnicodeString(&DestinationString, Buffer);
  v2 = BcdOpenStoreFromFile(&DestinationString, a1);
  v3 = v2;
  if ( v2 < 0 )
    BfspLogMessage(4, L"Could not open the BCD template store. Status = [%x]", (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x180050344  push    rbx
0x180050346  sub     rsp, 260h
0x18005034d  mov     rax, cs:__security_cookie
0x180050354  xor     rax, rsp
0x180050357  mov     [rsp+268h+var_18], rax
0x18005035f  mov     r9, cs:qword_1800A4550
0x180050366  lea     rax, aSystem32Config; "\\System32\\config\\BCD-Template"
0x18005036d  mov     [rsp+268h+var_240], rax
0x180050372  lea     r8, aSSS; "%s%s%s"
0x180050379  mov     rax, cs:qword_1800A4570
0x180050380  mov     rbx, rcx
0x180050383  xorps   xmm0, xmm0
0x180050386  mov     [rsp+268h+var_248], rax
0x18005038b  mov     edx, 104h; BufferCount
0x180050390  lea     rcx, [rsp+268h+Buffer]; Buffer
0x180050395  movups  xmmword ptr [rsp+268h+DestinationString.Length], xmm0
0x18005039a  call    swprintf_s
0x18005039f  lea     r8, [rsp+268h+Buffer]
0x1800503a4  mov     ecx, 2
0x1800503a9  lea     rdx, aOpeningTemplat; "Opening template from %ws."
0x1800503b0  call    BfspLogMessage
0x1800503b5  lea     rdx, [rsp+268h+Buffer]; SourceString
0x1800503ba  lea     rcx, [rsp+268h+DestinationString]; DestinationString
0x1800503bf  call    cs:__imp_RtlInitUnicodeString
0x1800503c5  mov     rdx, rbx
0x1800503c8  lea     rcx, [rsp+268h+DestinationString]
0x1800503cd  call    cs:__imp_BcdOpenStoreFromFile
0x1800503d3  mov     ebx, eax
0x1800503d5  test    eax, eax
0x1800503d7  jns     short loc_1800503ED
0x1800503d9  mov     r8d, eax
0x1800503dc  lea     rdx, aCouldNotOpenTh; "Could not open the BCD template store. "...
0x1800503e3  mov     ecx, 4
0x1800503e8  call    BfspLogMessage
0x1800503ed  mov     eax, ebx
0x1800503ef  mov     rcx, [rsp+268h+var_18]
0x1800503f7  xor     rcx, rsp; StackCookie
0x1800503fa  call    __security_check_cookie
0x1800503ff  add     rsp, 260h
0x180050406  pop     rbx
0x180050407  retn
```
