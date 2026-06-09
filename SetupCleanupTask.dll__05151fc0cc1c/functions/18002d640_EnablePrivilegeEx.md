# EnablePrivilegeEx

- ea: `0x18002d640`
- end: `0x18002d695`
- name: `EnablePrivilegeEx`
- size: `85`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006838`
- `0x180012600`
- `0x180012b50`
- `0x18002d630`

## callees

- `0x18002d640`
- `0x18002d69c`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002d668`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002d668`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeEx(LPCWSTR lpName, DWORD a2, DWORD *a3)
{
  unsigned int v5; // ebx
  LUID v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v5 = 0;
  if ( LookupPrivilegeValueW(0, lpName, &v7) )
    return (unsigned int)EnablePrivilegeInternal(v7, a2, a3);
  return v5;
}

```

## disassembly

```asm
0x18002d640  mov     rax, rsp
0x18002d643  mov     [rax+8], rbx
0x18002d647  mov     [rax+10h], rsi
0x18002d64b  push    rdi
0x18002d64c  sub     rsp, 20h
0x18002d650  mov     esi, edx
0x18002d652  mov     qword ptr [rax+20h], 0
0x18002d65a  mov     rdx, rcx; lpName
0x18002d65d  mov     rdi, r8
0x18002d660  xor     ecx, ecx; lpSystemName
0x18002d662  lea     r8, [rax+20h]; lpLuid
0x18002d666  xor     ebx, ebx
0x18002d668  call    cs:__imp_LookupPrivilegeValueW
0x18002d66e  test    eax, eax
0x18002d670  jz      short loc_18002D683
0x18002d672  mov     rcx, [rsp+28h+arg_18]
0x18002d677  mov     r8, rdi
0x18002d67a  mov     edx, esi
0x18002d67c  call    EnablePrivilegeInternal
0x18002d681  mov     ebx, eax
0x18002d683  mov     rsi, [rsp+28h+arg_8]
0x18002d688  mov     eax, ebx
0x18002d68a  mov     rbx, [rsp+28h+arg_0]
0x18002d68f  add     rsp, 20h
0x18002d693  pop     rdi
0x18002d694  retn
```
