# SdbpShouldMapSdbToKernelMemory

- ea: `0x14002e270`
- end: `0x14002e3b0`
- name: `SdbpShouldMapSdbToKernelMemory`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140042ad4`

## callees

- `0x140004469`
- `0x14000479c`
- `0x14002e270`
- `0x14003e364`
- `0x140046048`
- `0x140046440`
- `0x140046660`

## string_xrefs

- `0x14002e28c`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14002e32d`: `AslRegistryGetKey failed to open appcompat key [%x]`
- `0x14002e2e4`: `AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]`
- `0x14002e374`: `AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]`

## pseudocode

```c
bool SdbpShouldMapSdbToKernelMemory()
{
  int Key; // eax
  char v1; // bl
  __int64 v2; // r8
  int UInt32; // eax
  int v4; // ecx
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // ebx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF

  Handle = 0;
  v10 = 0;
  if ( (unsigned int)Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline() )
  {
    Key = AslRegistryGetKey(&Handle, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, 1);
    if ( Key < 0 )
    {
      v1 = 1;
      v2 = 2415;
LABEL_12:
      AslLogCallPrintf(
        1,
        "SdbpShouldMapSdbToKernelMemory",
        v2,
        "AslRegistryGetKey failed to open appcompat key [%x]",
        Key);
      return v1;
    }
    UInt32 = AslRegistryGetUInt32(&v10, Handle, L"DisableKernelMemoryMap");
    if ( UInt32 >= 0 )
    {
      v5 = v10;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)UInt32) )
        AslLogCallPrintf(
          1,
          "SdbpShouldMapSdbToKernelMemory",
          2420,
          "AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]",
          v4);
      v5 = 0;
    }
    ZwClose_0(Handle);
    return v5 == 0;
  }
  else
  {
    Key = AslRegistryGetKey(&Handle, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, 1);
    if ( Key < 0 )
    {
      v1 = 0;
      v2 = 2436;
      goto LABEL_12;
    }
    v6 = AslRegistryGetUInt32(&v10, Handle, L"EnableKernelMemoryMap");
    if ( v6 >= 0 )
    {
      v8 = v10;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)v6) )
        AslLogCallPrintf(
          1,
          "SdbpShouldMapSdbToKernelMemory",
          2441,
          "AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]",
          v7);
      v8 = 0;
    }
    ZwClose_0(Handle);
    return v8 != 0;
  }
}

```

## disassembly

```asm
0x14002e270  push    rbx
0x14002e272  sub     rsp, 30h
0x14002e276  mov     [rsp+38h+Handle], 0
0x14002e27f  mov     [rsp+38h+arg_0], 0
0x14002e287  call    Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline
0x14002e28c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002e293  mov     r9d, 1
0x14002e299  lea     rcx, [rsp+38h+Handle]
0x14002e29e  mov     r8d, 80000100h
0x14002e2a4  test    eax, eax
0x14002e2a6  jz      short loc_14002E31C
0x14002e2a8  call    AslRegistryGetKey
0x14002e2ad  test    eax, eax
0x14002e2af  jns     short loc_14002E2BB
0x14002e2b1  mov     bl, 1
0x14002e2b3  mov     r8d, 96Fh
0x14002e2b9  jmp     short loc_14002E32D
0x14002e2bb  mov     rdx, [rsp+38h+Handle]
0x14002e2c0  lea     r8, aDisablekernelm; "DisableKernelMemoryMap"
0x14002e2c7  lea     rcx, [rsp+38h+arg_0]
0x14002e2cc  call    AslRegistryGetUInt32
0x14002e2d1  mov     ecx, eax
0x14002e2d3  test    eax, eax
0x14002e2d5  jns     short loc_14002E304
0x14002e2d7  call    AslFileNotFound
0x14002e2dc  test    eax, eax
0x14002e2de  jnz     short loc_14002E300
0x14002e2e0  mov     [rsp+38h+var_18], ecx
0x14002e2e4  lea     r9, aAslregistryget_6; "AslRegistryGetUInt32 failed to read Dis"...
0x14002e2eb  lea     ecx, [rax+1]
0x14002e2ee  mov     r8d, 974h
0x14002e2f4  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x14002e2fb  call    AslLogCallPrintf
0x14002e300  xor     ebx, ebx
0x14002e302  jmp     short loc_14002E308
0x14002e304  mov     ebx, [rsp+38h+arg_0]
0x14002e308  mov     rcx, [rsp+38h+Handle]; Handle
0x14002e30d  call    ZwClose_0
0x14002e312  test    ebx, ebx
0x14002e314  setz    bl
0x14002e317  jmp     loc_14002E3A7
0x14002e31c  call    AslRegistryGetKey
0x14002e321  test    eax, eax
0x14002e323  jns     short loc_14002E34B
0x14002e325  xor     bl, bl
0x14002e327  mov     r8d, 984h
0x14002e32d  lea     r9, aAslregistryget; "AslRegistryGetKey failed to open appcom"...
0x14002e334  mov     [rsp+38h+var_18], eax
0x14002e338  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x14002e33f  mov     ecx, 1
0x14002e344  call    AslLogCallPrintf
0x14002e349  jmp     short loc_14002E3A7
0x14002e34b  mov     rdx, [rsp+38h+Handle]
0x14002e350  lea     r8, aEnablekernelme; "EnableKernelMemoryMap"
0x14002e357  lea     rcx, [rsp+38h+arg_0]
0x14002e35c  call    AslRegistryGetUInt32
0x14002e361  mov     ecx, eax
0x14002e363  test    eax, eax
0x14002e365  jns     short loc_14002E394
0x14002e367  call    AslFileNotFound
0x14002e36c  test    eax, eax
0x14002e36e  jnz     short loc_14002E390
0x14002e370  mov     [rsp+38h+var_18], ecx
0x14002e374  lea     r9, aAslregistryget_10; "AslRegistryGetUInt32 failed to read Ena"...
0x14002e37b  lea     ecx, [rax+1]
0x14002e37e  mov     r8d, 989h
0x14002e384  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x14002e38b  call    AslLogCallPrintf
0x14002e390  xor     ebx, ebx
0x14002e392  jmp     short loc_14002E398
0x14002e394  mov     ebx, [rsp+38h+arg_0]
0x14002e398  mov     rcx, [rsp+38h+Handle]; Handle
0x14002e39d  call    ZwClose_0
0x14002e3a2  test    ebx, ebx
0x14002e3a4  setnz   bl
0x14002e3a7  mov     al, bl
0x14002e3a9  add     rsp, 30h
0x14002e3ad  pop     rbx
0x14002e3ae  retn
```
