# Windows::FileSystem::ReFs::DedupVolume::SaveCpuThrottle(ulong)

- ea: `0x140028bc0`
- end: `0x140028c41`
- name: `?SaveCpuThrottle@DedupVolume@ReFs@FileSystem@Windows@@CAKK@Z`
- size: `129`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14003c808`

## callees

- `0x140028bc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028c2c`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x140028be6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x140028be6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140028c19`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140028c19`

## string_xrefs

- `0x140028bdf`: `SYSTEM\CurrentControlSet\Services\refsdedupsvc\Parameters`

## pseudocode

```c
__int64 __fastcall Windows::FileSystem::ReFs::DedupVolume::SaveCpuThrottle(int a1)
{
  unsigned int v1; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  phkResult = 0;
  v1 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\refsdedupsvc\\Parameters", &phkResult);
  if ( !v1 )
  {
    v1 = RegSetKeyValueW(phkResult, 0, L"CpuPercentage", 4u, &Data, 4u);
    RegCloseKey(phkResult);
  }
  return v1;
}

```

## disassembly

```asm
0x140028bc0  push    rbx
0x140028bc2  sub     rsp, 30h
0x140028bc6  mov     [rsp+38h+Data], ecx
0x140028bca  lea     r8, [rsp+38h+phkResult]; phkResult
0x140028bcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140028bd6  mov     [rsp+38h+phkResult], 0
0x140028bdf  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\re"...
0x140028be6  call    cs:__imp_RegCreateKeyW
0x140028bed  nop     dword ptr [rax+rax+00h]
0x140028bf2  mov     ebx, eax
0x140028bf4  test    eax, eax
0x140028bf6  jnz     short loc_140028C38
0x140028bf8  mov     rcx, [rsp+38h+phkResult]; hKey
0x140028bfd  lea     r9d, [rax+4]; dwType
0x140028c01  lea     rax, [rsp+38h+Data]
0x140028c06  mov     [rsp+38h+cbData], r9d; cbData
0x140028c0b  lea     r8, ValueName; "CpuPercentage"
0x140028c12  mov     [rsp+38h+lpData], rax; lpData
0x140028c17  xor     edx, edx; lpSubKey
0x140028c19  call    cs:__imp_RegSetKeyValueW
0x140028c20  nop     dword ptr [rax+rax+00h]
0x140028c25  mov     rcx, [rsp+38h+phkResult]; hKey
0x140028c2a  mov     ebx, eax
0x140028c2c  call    cs:__imp_RegCloseKey
0x140028c33  nop     dword ptr [rax+rax+00h]
0x140028c38  mov     eax, ebx
0x140028c3a  add     rsp, 30h
0x140028c3e  pop     rbx
0x140028c3f  retn
```
