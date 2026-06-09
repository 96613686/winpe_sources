# BiAdoptStore

- ea: `0x14001b1f4`
- end: `0x14001b34c`
- name: `BiAdoptStore`
- size: `344`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14001a964`

## callees

- `0x1400133e4`
- `0x14001adb8`
- `0x14001b1f4`
- `0x14001b4bc`
- `0x14001bb00`
- `0x14001c14c`
- `0x14001c3a8`
- `0x1400232c4`
- `0x140023e28`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001b33e`
- `ntdll!RtlFreeHeap` at `0x14001b33e`
- `ntdll!RtlInitUnicodeString` at `0x14001b245`
- `ntdll!RtlInitUnicodeString` at `0x14001b245`

## string_xrefs

- `0x14001b225`: `Failed to get system store path. Status: %x`
- `0x14001b267`: `Failed to open store from path. File: %ws Status: %x`

## pseudocode

```c
__int64 BiAdoptStore()
{
  int SystemStorePath; // eax
  int v1; // ebx
  __int64 v2; // r8
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF
  PCWSTR SourceString; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  SourceString = 0;
  DestinationString = 0;
  SystemStorePath = BcdGetSystemStorePath((wchar_t **)&SourceString);
  v1 = SystemStorePath;
  if ( SystemStorePath < 0 )
  {
    BiLogMessage(4, L"Failed to get system store path. Status: %x", (unsigned int)SystemStorePath);
    goto LABEL_20;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v3 = BiOpenStoreWithHash(&DestinationString, 0, v2, &v10);
  v1 = v3;
  if ( v3 < 0 )
  {
    BiLogMessage(4, L"Failed to open store from path. File: %ws Status: %x", DestinationString.Buffer, (unsigned int)v3);
    goto LABEL_18;
  }
  v4 = BiGetFirmwareType(0) - 1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
      {
        v1 = -1073741637;
LABEL_10:
        BiLogMessage(4, L"Failed clear firmware namespace. File: %ws Flags: 0x%x Status: %x", DestinationString.Buffer);
        goto LABEL_18;
      }
    }
    else
    {
      v1 = BiDeleteEfiNamespaceObjects(2);
      if ( v1 < 0 )
        goto LABEL_10;
    }
  }
  v1 = BcdMarkAsSystemStore(v10);
  if ( v1 >= 0 )
  {
    v6 = BiGetFirmwareType(0) - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( !v7 )
      {
        v1 = BiExportStoreToEfi(v10);
        goto LABEL_18;
      }
      if ( v7 != 1 )
      {
        v1 = -1073741637;
        goto LABEL_18;
      }
    }
    v1 = 0;
  }
LABEL_18:
  if ( v10 )
    BiCloseStore(v10, 2);
LABEL_20:
  if ( SourceString )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)SourceString);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001b1f4  mov     rax, rsp
0x14001b1f7  push    rbx
0x14001b1f8  sub     rsp, 40h
0x14001b1fc  xorps   xmm0, xmm0
0x14001b1ff  mov     qword ptr [rax+10h], 0
0x14001b207  lea     rcx, [rax+18h]
0x14001b20b  mov     qword ptr [rax+18h], 0
0x14001b213  movups  xmmword ptr [rax-18h], xmm0
0x14001b217  call    BcdGetSystemStorePath
0x14001b21c  mov     ebx, eax
0x14001b21e  test    eax, eax
0x14001b220  jns     short loc_14001B23B
0x14001b222  mov     r8d, eax
0x14001b225  lea     rdx, aFailedToGetSys_1; "Failed to get system store path. Status"...
0x14001b22c  mov     ecx, 4
0x14001b231  call    BiLogMessage
0x14001b236  jmp     loc_14001B322
0x14001b23b  mov     rdx, [rsp+48h+SourceString]; SourceString
0x14001b240  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001b245  call    cs:__imp_RtlInitUnicodeString
0x14001b24b  lea     r9, [rsp+48h+arg_8]
0x14001b250  xor     edx, edx
0x14001b252  lea     rcx, [rsp+48h+DestinationString]
0x14001b257  call    BiOpenStoreWithHash
0x14001b25c  mov     ebx, eax
0x14001b25e  test    eax, eax
0x14001b260  jns     short loc_14001B280
0x14001b262  mov     r8, [rsp+48h+DestinationString.Buffer]
0x14001b267  lea     rdx, aFailedToOpenSt; "Failed to open store from path. File: %"...
0x14001b26e  mov     r9d, eax
0x14001b271  mov     ecx, 4
0x14001b276  call    BiLogMessage
0x14001b27b  jmp     loc_14001B30B
0x14001b280  xor     ecx, ecx
0x14001b282  call    BiGetFirmwareType
0x14001b287  sub     eax, 1
0x14001b28a  jz      short loc_14001B2CE
0x14001b28c  sub     eax, 1
0x14001b28f  jz      short loc_14001B29D
0x14001b291  cmp     eax, 1
0x14001b294  jz      short loc_14001B2CE
0x14001b296  mov     ebx, 0C00000BBh
0x14001b29b  jmp     short loc_14001B2AD
0x14001b29d  mov     ecx, 2
0x14001b2a2  call    BiDeleteEfiNamespaceObjects
0x14001b2a7  mov     ebx, eax
0x14001b2a9  test    eax, eax
0x14001b2ab  jns     short loc_14001B2CE
0x14001b2ad  mov     r8, [rsp+48h+DestinationString.Buffer]
0x14001b2b2  lea     rdx, aFailedClearFir; "Failed clear firmware namespace. File: "...
0x14001b2b9  mov     r9d, 2
0x14001b2bf  mov     [rsp+48h+var_28], ebx
0x14001b2c3  lea     ecx, [r9+2]
0x14001b2c7  call    BiLogMessage
0x14001b2cc  jmp     short loc_14001B30B
0x14001b2ce  mov     rcx, [rsp+48h+arg_8]
0x14001b2d3  call    BcdMarkAsSystemStore
0x14001b2d8  mov     ebx, eax
0x14001b2da  test    eax, eax
0x14001b2dc  js      short loc_14001B30B
0x14001b2de  xor     ecx, ecx
0x14001b2e0  call    BiGetFirmwareType
0x14001b2e5  sub     eax, 1
0x14001b2e8  jz      short loc_14001B309
0x14001b2ea  sub     eax, 1
0x14001b2ed  jz      short loc_14001B2FB
0x14001b2ef  cmp     eax, 1
0x14001b2f2  jz      short loc_14001B309
0x14001b2f4  mov     ebx, 0C00000BBh
0x14001b2f9  jmp     short loc_14001B30B
0x14001b2fb  mov     rcx, [rsp+48h+arg_8]
0x14001b300  call    BiExportStoreToEfi
0x14001b305  mov     ebx, eax
0x14001b307  jmp     short loc_14001B30B
0x14001b309  xor     ebx, ebx
0x14001b30b  cmp     [rsp+48h+arg_8], 0
0x14001b311  jz      short loc_14001B322
0x14001b313  mov     rcx, [rsp+48h+arg_8]
0x14001b318  mov     edx, 2
0x14001b31d  call    BiCloseStore
0x14001b322  cmp     [rsp+48h+SourceString], 0
0x14001b328  jz      short loc_14001B344
0x14001b32a  mov     rcx, gs:60h
0x14001b333  xor     edx, edx; Flags
0x14001b335  mov     r8, [rsp+48h+SourceString]; P
0x14001b33a  mov     rcx, [rcx+30h]; HeapHandle
0x14001b33e  call    cs:__imp_RtlFreeHeap
0x14001b344  mov     eax, ebx
0x14001b346  add     rsp, 40h
0x14001b34a  pop     rbx
0x14001b34b  retn
```
