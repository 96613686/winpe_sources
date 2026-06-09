# EdppPolicyUpdateRequired

- ea: `0x14002cc34`
- end: `0x14002ccd8`
- name: `EdppPolicyUpdateRequired`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002c9c4`

## callees

- `0x14002bf44`
- `0x14002cc34`
- `0x14002d130`
- `0x14002d18c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002cc46`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002cc46`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002ccab`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002ccab`

## pseudocode

```c
bool EdppPolicyUpdateRequired()
{
  char v0; // al
  int v1; // edi
  char v2; // si
  __int64 v3; // rcx
  char v4; // al
  int v5; // ebp
  char v6; // bl
  __int64 v7; // rdx

  ExAcquirePushLockExclusiveEx(&EdppRuntimeConfig, 0);
  v0 = EdpPluginConfigActive(byte_140019508, 0, (unsigned int)dword_140019530, (unsigned int)dword_140019534);
  v1 = dword_14001950C;
  v2 = v0;
  EdpFreePluginConfig(v3);
  EdpInitPluginRuntimeConfig();
  v4 = EdpPluginConfigActive(byte_140019508, 0, (unsigned int)dword_140019530, (unsigned int)dword_140019534);
  v5 = dword_14001950C;
  v6 = v4;
  ExReleasePushLockExclusiveEx(&EdppRuntimeConfig, v7);
  return v6 && v5 || v2 && v1;
}

```

## disassembly

```asm
0x14002cc34  push    rbx
0x14002cc36  push    rbp
0x14002cc37  push    rsi
0x14002cc38  push    rdi
0x14002cc39  sub     rsp, 28h
0x14002cc3d  xor     edx, edx
0x14002cc3f  lea     rcx, EdppRuntimeConfig
0x14002cc46  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002cc4d  nop     dword ptr [rax+rax+00h]
0x14002cc52  mov     r9d, cs:dword_140019534
0x14002cc59  lea     rbx, byte_140019508
0x14002cc60  mov     r8d, cs:dword_140019530
0x14002cc67  mov     rcx, rbx
0x14002cc6a  xor     edx, edx
0x14002cc6c  call    EdpPluginConfigActive
0x14002cc71  mov     edi, cs:dword_14001950C
0x14002cc77  mov     sil, al
0x14002cc7a  call    EdpFreePluginConfig
0x14002cc7f  call    EdpInitPluginRuntimeConfig
0x14002cc84  mov     r9d, cs:dword_140019534
0x14002cc8b  xor     edx, edx
0x14002cc8d  mov     r8d, cs:dword_140019530
0x14002cc94  mov     rcx, rbx
0x14002cc97  call    EdpPluginConfigActive
0x14002cc9c  mov     ebp, cs:dword_14001950C
0x14002cca2  lea     rcx, EdppRuntimeConfig
0x14002cca9  mov     bl, al
0x14002ccab  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002ccb2  nop     dword ptr [rax+rax+00h]
0x14002ccb7  test    bl, bl
0x14002ccb9  jz      short loc_14002CCBF
0x14002ccbb  test    ebp, ebp
0x14002ccbd  jnz     short loc_14002CCC8
0x14002ccbf  test    sil, sil
0x14002ccc2  jz      short loc_14002CCCC
0x14002ccc4  test    edi, edi
0x14002ccc6  jz      short loc_14002CCCC
0x14002ccc8  mov     al, 1
0x14002ccca  jmp     short loc_14002CCCE
0x14002cccc  xor     al, al
0x14002ccce  add     rsp, 28h
0x14002ccd2  pop     rdi
0x14002ccd3  pop     rsi
0x14002ccd4  pop     rbp
0x14002ccd5  pop     rbx
0x14002ccd6  retn
```
