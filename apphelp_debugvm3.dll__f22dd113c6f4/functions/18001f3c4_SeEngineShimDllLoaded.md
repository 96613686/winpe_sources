# SeEngineShimDllLoaded

- ea: `0x18001f3c4`
- end: `0x18001f492`
- name: `SeEngineShimDllLoaded`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002520`
- `0x18002f270`

## callees

- `0x180005b04`
- `0x18000f114`
- `0x18001f3c4`
- `0x180020a68`

## import_xrefs

- `ntdll!LdrFindEntryForAddress` at `0x18001f3ea`
- `ntdll!LdrFindEntryForAddress` at `0x18001f3ea`

## string_xrefs

- `0x18001f447`: `SeEngineShimDllLoaded`
- `0x18001f470`: `SeEngineShimDllLoaded`
- `0x18001f43a`: `Failed to add shim dll %S to module tracker`
- `0x18001f483`: `Failed to inform shim manager of shim dll load`

## pseudocode

```c
__int64 __fastcall SeEngineShimDllLoaded(__int64 a1, void *a2)
{
  __int64 v2; // rdi
  int EntryForAddress; // ebx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v2 = g_Engine;
  v5 = 0;
  EntryForAddress = LdrFindEntryForAddress(a2, (PLDR_DATA_TABLE_ENTRY *)&v5);
  if ( EntryForAddress < 0 )
  {
    AslLogCallPrintf(1, "SeEngineShimDllLoaded", 413, "Failed to find loader entry");
  }
  else
  {
    EntryForAddress = SeModuleTrackerModuleLoaded(0, *(_QWORD *)(v2 + 40), 3, v5);
    if ( EntryForAddress < 0 )
    {
      AslLogCallPrintf(
        1,
        "SeEngineShimDllLoaded",
        426,
        "Failed to add shim dll %S to module tracker",
        *(const wchar_t **)(v5 + 96));
    }
    else
    {
      EntryForAddress = SeShimManagerShimDllLoaded(*(unsigned __int64 **)(v2 + 16), v5);
      if ( EntryForAddress < 0 )
        AslLogCallPrintf(1, "SeEngineShimDllLoaded", 436, "Failed to inform shim manager of shim dll load");
      else
        return 0;
    }
  }
  return (unsigned int)EntryForAddress;
}

```

## disassembly

```asm
0x18001f3c4  mov     rax, rsp
0x18001f3c7  mov     [rax+10h], rbx
0x18001f3cb  mov     [rax+8], rcx
0x18001f3cf  push    rdi
0x18001f3d0  sub     rsp, 30h
0x18001f3d4  mov     rdi, cs:g_Engine
0x18001f3db  mov     rcx, rdx; Address
0x18001f3de  lea     rdx, [rax+8]; Module
0x18001f3e2  mov     qword ptr [rax+8], 0
0x18001f3ea  call    cs:__imp_LdrFindEntryForAddress
0x18001f3f0  mov     ebx, eax
0x18001f3f2  test    eax, eax
0x18001f3f4  js      short loc_18001F463
0x18001f3f6  mov     r9, [rsp+38h+arg_0]
0x18001f3fb  mov     r8d, 3
0x18001f401  mov     rdx, [rdi+28h]
0x18001f405  xor     ecx, ecx
0x18001f407  call    SeModuleTrackerModuleLoaded
0x18001f40c  mov     ebx, eax
0x18001f40e  test    eax, eax
0x18001f410  js      short loc_18001F435
0x18001f412  mov     rdx, [rsp+38h+arg_0]
0x18001f417  mov     rcx, [rdi+10h]
0x18001f41b  call    SeShimManagerShimDllLoaded
0x18001f420  mov     ebx, eax
0x18001f422  test    eax, eax
0x18001f424  js      short loc_18001F483
0x18001f426  xor     ebx, ebx
0x18001f428  mov     eax, ebx
0x18001f42a  mov     rbx, [rsp+38h+arg_8]
0x18001f42f  add     rsp, 30h
0x18001f433  pop     rdi
0x18001f434  retn
0x18001f435  mov     rax, [rsp+38h+arg_0]
0x18001f43a  lea     r9, aFailedToAddShi; "Failed to add shim dll %S to module tra"...
0x18001f441  mov     r8d, 1AAh
0x18001f447  lea     rdx, aSeengineshimdl; "SeEngineShimDllLoaded"
0x18001f44e  mov     rcx, [rax+60h]
0x18001f452  mov     [rsp+38h+var_18], rcx
0x18001f457  mov     ecx, 1
0x18001f45c  call    AslLogCallPrintf
0x18001f461  jmp     short loc_18001F428
0x18001f463  lea     r9, aFailedToFindLo; "Failed to find loader entry"
0x18001f46a  mov     r8d, 19Dh
0x18001f470  lea     rdx, aSeengineshimdl; "SeEngineShimDllLoaded"
0x18001f477  mov     ecx, 1
0x18001f47c  call    AslLogCallPrintf
0x18001f481  jmp     short loc_18001F428
0x18001f483  lea     r9, aFailedToInform; "Failed to inform shim manager of shim d"...
0x18001f48a  mov     r8d, 1B4h
0x18001f490  jmp     short loc_18001F470
```
