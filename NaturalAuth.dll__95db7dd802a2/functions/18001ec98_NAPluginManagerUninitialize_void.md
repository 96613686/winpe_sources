# NAPluginManagerUninitialize(void)

- ea: `0x18001ec98`
- end: `0x18001edec`
- name: `?NAPluginManagerUninitialize@@YAXXZ`
- size: `340`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180008b20`
- `0x1800091c0`

## callees

- `0x18001d99c`
- `0x18001ec98`
- `0x18001f0c4`
- `0x180046010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ede5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ecae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ecae`
- `ntdll!RtlDeregisterWait` at `0x18001ed7d`
- `ntdll!RtlDeregisterWait` at `0x18001ed7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed9a`

## pseudocode

```c
void NAPluginManagerUninitialize(void)
{
  _QWORD *v0; // rbx
  __int64 v1; // rdi
  __int64 v2; // rbx
  _OWORD v3[3]; // [rsp+20h] [rbp-48h] BYREF

  RtlAcquireSRWLockExclusive(&stru_18005FAE0);
  v0 = (_QWORD *)qword_18005F9A8;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,PluginSignalInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(
    (__int64)&qword_18005F9A8,
    (__int64)&qword_18005F9A8,
    *(char **)(qword_18005F9A8 + 8));
  v0[1] = v0;
  *v0 = v0;
  v1 = 0;
  v0[2] = v0;
  v2 = 0;
  qword_18005F9B0 = 0;
  do
  {
    (*(void (__fastcall **)(_QWORD))((char *)&off_18005C000 + v2 + 8))(*(__int64 (__fastcall **)())((char *)&off_18005C000
                                                                                                  + v2
                                                                                                  + 80));
    *(_QWORD *)&v3[0] = 0xFFFFFFFFLL;
    ++v1;
    *(__int64 (__fastcall **)())((char *)&off_18005C000 + v2 + 80) = 0;
    v2 += 232;
    memset((char *)v3 + 8, 0, 40);
    *(_OWORD *)((char *)&off_18005C000 + v2 - 216) = v3[0];
    *(_OWORD *)((char *)&off_18005C000 + v2 - 200) = v3[1];
    *(_OWORD *)((char *)&off_18005C000 + v2 - 184) = v3[2];
    *(_OWORD *)((char *)&off_18005C000 + v2 - 168) = 0u;
  }
  while ( v1 != 6 );
  UnloadRegistryPlugins();
  if ( pvContext )
  {
    RtlDeregisterWait(pvContext);
    pvContext = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  byte_18005FC59 = 0;
  RtlReleaseSRWLockExclusive(&stru_18005FAE0);
}

```

## disassembly

```asm
0x18001ec98  mov     [rsp+arg_0], rbx
0x18001ec9d  mov     [rsp+arg_8], rbp
0x18001eca2  push    rdi
0x18001eca3  sub     rsp, 60h
0x18001eca7  lea     rcx, stru_18005FAE0
0x18001ecae  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001ecb4  mov     rbx, cs:qword_18005F9A8
0x18001ecbb  lea     rcx, qword_18005F9A8
0x18001ecc2  mov     rdx, rcx
0x18001ecc5  mov     r8, [rbx+8]
0x18001ecc9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,PluginSignalInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>> &,std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *> *)
0x18001ecce  mov     [rbx+8], rbx
0x18001ecd2  lea     rbp, off_18005C000
0x18001ecd9  mov     [rbx], rbx
0x18001ecdc  xor     edi, edi
0x18001ecde  mov     [rbx+10h], rbx
0x18001ece2  xor     ebx, ebx
0x18001ece4  mov     cs:qword_18005F9B0, 0
0x18001ecef  mov     rcx, [rbx+rbp+50h]
0x18001ecf4  mov     rax, [rbx+rbp+8]
0x18001ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecfe  xorps   xmm0, xmm0
0x18001ed01  mov     dword ptr [rsp+68h+var_48], 0FFFFFFFFh
0x18001ed09  xor     eax, eax
0x18001ed0b  inc     rdi
0x18001ed0e  mov     dword ptr [rsp+68h+var_48+4], eax
0x18001ed12  mov     [rsp+68h+var_10], rax
0x18001ed17  mov     [rbx+rbp+50h], rax
0x18001ed1c  lea     rbx, [rbx+0E8h]
0x18001ed23  movups  [rsp+68h+var_48+8], xmm0
0x18001ed28  movups  [rsp+68h+var_30], xmm0
0x18001ed2d  movups  xmm1, xmmword ptr [rsp+30h]
0x18001ed32  movups  [rsp+68h+var_20], xmm0
0x18001ed37  movups  xmm0, [rsp+68h+var_48]
0x18001ed3c  movups  xmmword ptr [rbx+rbp-0D8h], xmm0
0x18001ed44  movups  xmm0, [rsp+68h+var_30+8]
0x18001ed49  movups  xmmword ptr [rbx+rbp-0C8h], xmm1
0x18001ed51  movups  xmm1, [rsp+68h+var_20+8]
0x18001ed56  movups  xmmword ptr [rbx+rbp-0B8h], xmm0
0x18001ed5e  movups  xmmword ptr [rbx+rbp-0A8h], xmm1
0x18001ed66  cmp     rdi, 6
0x18001ed6a  jnz     short loc_18001ECEF
0x18001ed6c  call    UnloadRegistryPlugins
0x18001ed71  mov     rcx, cs:pvContext; hWaitHandle
0x18001ed78  test    rcx, rcx
0x18001ed7b  jz      short loc_18001ED8E
0x18001ed7d  call    cs:__imp_RtlDeregisterWait
0x18001ed83  mov     cs:pvContext, 0
0x18001ed8e  mov     rcx, cs:hKey; hKey
0x18001ed95  test    rcx, rcx
0x18001ed98  jz      short loc_18001EDAB
0x18001ed9a  call    cs:__imp_RegCloseKey
0x18001eda0  mov     cs:hKey, 0
0x18001edab  mov     rcx, cs:hObject; hObject
0x18001edb2  test    rcx, rcx
0x18001edb5  jz      short loc_18001EDC8
0x18001edb7  call    cs:__imp_CloseHandle
0x18001edbd  mov     cs:hObject, 0
0x18001edc8  lea     rcx, stru_18005FAE0
0x18001edcf  mov     cs:byte_18005FC59, 0
0x18001edd6  mov     rbx, [rsp+68h+arg_0]
0x18001eddb  mov     rbp, [rsp+68h+arg_8]
0x18001ede0  add     rsp, 60h
0x18001ede4  pop     rdi
0x18001ede5  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
