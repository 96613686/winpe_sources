# RdpWorkItemManager::Initialize(void)

- ea: `0x1800b4ec0`
- end: `0x1800b4f85`
- name: `?Initialize@RdpWorkItemManager@@EEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(RdpWorkItemManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b5378`

## callees

- `0x180089010`
- `0x1800b4ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4f77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4f77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4ef7`

## string_xrefs

- `0x1800b4eed`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800b4f15`: `LowCompressionTextRatio`
- `0x1800b4f39`: `TextLabelCompressionRatio`
- `0x1800b4f5d`: `ImageLabelCompressionRatio`

## pseudocode

```c
__int64 __fastcall RdpWorkItemManager::Initialize(RdpWorkItemManager *this)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 5) |= 2u;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          0,
          0x20019u,
          &hKey) )
  {
    ReadRegUINT(hKey, L"LowCompressionTextRatio", 1u, 0x64u, (unsigned int *)this + 26);
    ReadRegUINT(hKey, L"TextLabelCompressionRatio", 1u, 0x64u, (unsigned int *)this + 27);
    ReadRegUINT(hKey, L"ImageLabelCompressionRatio", 1u, 0x64u, (unsigned int *)this + 28);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800b4ec0  push    rbx
0x1800b4ec2  sub     rsp, 30h
0x1800b4ec6  or      dword ptr [rcx+14h], 2
0x1800b4eca  lea     rax, [rsp+38h+hKey]
0x1800b4ecf  mov     rbx, rcx
0x1800b4ed2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800b4ed7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4ede  mov     [rsp+38h+hKey], 0
0x1800b4ee7  mov     r9d, 20019h; samDesired
0x1800b4eed  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x1800b4ef4  xor     r8d, r8d; ulOptions
0x1800b4ef7  call    cs:__imp_RegOpenKeyExW
0x1800b4efd  test    eax, eax
0x1800b4eff  jnz     short loc_1800B4F6D
0x1800b4f01  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800b4f06  lea     rax, [rbx+68h]
0x1800b4f0a  mov     r9d, 64h ; 'd'; unsigned int
0x1800b4f10  mov     [rsp+38h+phkResult], rax; unsigned int *
0x1800b4f15  lea     rdx, aLowcompression; "LowCompressionTextRatio"
0x1800b4f1c  lea     r8d, [r9-63h]; unsigned int
0x1800b4f20  call    ?ReadRegUINT@@YAJPEAUHKEY__@@PEAGIIPEAI@Z; ReadRegUINT(HKEY__ *,ushort *,uint,uint,uint *)
0x1800b4f25  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800b4f2a  lea     rax, [rbx+6Ch]
0x1800b4f2e  mov     r9d, 64h ; 'd'; unsigned int
0x1800b4f34  mov     [rsp+38h+phkResult], rax; unsigned int *
0x1800b4f39  lea     rdx, aTextlabelcompr; "TextLabelCompressionRatio"
0x1800b4f40  lea     r8d, [r9-63h]; unsigned int
0x1800b4f44  call    ?ReadRegUINT@@YAJPEAUHKEY__@@PEAGIIPEAI@Z; ReadRegUINT(HKEY__ *,ushort *,uint,uint,uint *)
0x1800b4f49  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800b4f4e  lea     rax, [rbx+70h]
0x1800b4f52  mov     r9d, 64h ; 'd'; unsigned int
0x1800b4f58  mov     [rsp+38h+phkResult], rax; unsigned int *
0x1800b4f5d  lea     rdx, aImagelabelcomp; "ImageLabelCompressionRatio"
0x1800b4f64  lea     r8d, [r9-63h]; unsigned int
0x1800b4f68  call    ?ReadRegUINT@@YAJPEAUHKEY__@@PEAGIIPEAI@Z; ReadRegUINT(HKEY__ *,ushort *,uint,uint,uint *)
0x1800b4f6d  mov     rcx, [rsp+38h+hKey]; hKey
0x1800b4f72  test    rcx, rcx
0x1800b4f75  jz      short loc_1800B4F7D
0x1800b4f77  call    cs:__imp_RegCloseKey
0x1800b4f7d  xor     eax, eax
0x1800b4f7f  add     rsp, 30h
0x1800b4f83  pop     rbx
0x1800b4f84  retn
```
