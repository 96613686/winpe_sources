# GetMaxConnections

- ea: `0x14000c4a4`
- end: `0x14000c554`
- name: `GetMaxConnections`
- size: `176`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c078`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x14000b854`
- `0x14000c4a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4f7`

## string_xrefs

- `0x14000c4d3`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`
- `0x14000c51b`: `UevFilter.GetMaxConnections: Max connections not configured, using default value\n`

## pseudocode

```c
__int64 __fastcall GetMaxConnections(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  DestinationString = 0;
  v6 = 0;
  DbgTrace(2, "UevFilter.GetMaxConnections: Entry\n", a3);
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\UEV\\Agent\\Configuration");
  RtlInitUnicodeString(&v6, L"MaxProcessEventConnections");
  if ( (int)ReadRegistryDword(&DestinationString, &v6, &v8) >= 0 )
  {
    v4 = v8;
  }
  else
  {
    DbgTrace(2, "UevFilter.GetMaxConnections: Max connections not configured, using default value\n", v3);
    v4 = 2048;
  }
  DbgTraceFrmt(2u, "UevFilter.GetMaxConnections: Exit, maxConnections = %d\n", v4);
  return v4;
}

```

## disassembly

```asm
0x14000c4a4  push    rbx
0x14000c4a6  sub     rsp, 40h
0x14000c4aa  xorps   xmm0, xmm0
0x14000c4ad  mov     [rsp+48h+arg_0], 0
0x14000c4b5  xorps   xmm1, xmm1
0x14000c4b8  lea     rdx, aUevfilterGetma_1; "UevFilter.GetMaxConnections: Entry\n"
0x14000c4bf  mov     ecx, 2
0x14000c4c4  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14000c4c9  movups  xmmword ptr [rsp+48h+var_28.Length], xmm1
0x14000c4ce  call    DbgTrace
0x14000c4d3  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14000c4da  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000c4df  call    cs:__imp_RtlInitUnicodeString
0x14000c4e6  nop     dword ptr [rax+rax+00h]
0x14000c4eb  lea     rdx, aMaxprocesseven; "MaxProcessEventConnections"
0x14000c4f2  lea     rcx, [rsp+48h+var_28]; DestinationString
0x14000c4f7  call    cs:__imp_RtlInitUnicodeString
0x14000c4fe  nop     dword ptr [rax+rax+00h]
0x14000c503  lea     r8, [rsp+48h+arg_0]
0x14000c508  lea     rdx, [rsp+48h+var_28]
0x14000c50d  lea     rcx, [rsp+48h+DestinationString]
0x14000c512  call    ReadRegistryDword
0x14000c517  test    eax, eax
0x14000c519  jns     short loc_14000C533
0x14000c51b  lea     rdx, aUevfilterGetma_0; "UevFilter.GetMaxConnections: Max connec"...
0x14000c522  mov     ecx, 2
0x14000c527  call    DbgTrace
0x14000c52c  mov     ebx, 800h
0x14000c531  jmp     short loc_14000C537
0x14000c533  mov     ebx, [rsp+48h+arg_0]
0x14000c537  mov     r8d, ebx
0x14000c53a  lea     rdx, aUevfilterGetma; "UevFilter.GetMaxConnections: Exit, maxC"...
0x14000c541  mov     ecx, 2
0x14000c546  call    DbgTraceFrmt
0x14000c54b  mov     eax, ebx
0x14000c54d  add     rsp, 40h
0x14000c551  pop     rbx
0x14000c552  retn
```
