# CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18002e55c`
- end: `0x18002e5a4`
- name: `??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `72`
- prototype: `CAutoHKey *(CAutoHKey *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002e7d4`

## callees

- `0x18002e55c`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002e57b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002e57b`

## pseudocode

```c
CAutoHKey *__fastcall CAutoHKey::CAutoHKey(CAutoHKey *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  HKEY v6; // rax

  if ( RegCreateKeyW(a2, a3, a4) )
  {
    *a4 = 0;
    v6 = 0;
  }
  else
  {
    v6 = *a4;
  }
  *(_QWORD *)this = v6;
  return this;
}

```

## disassembly

```asm
0x18002e55c  mov     [rsp+arg_0], rbx
0x18002e561  push    rdi
0x18002e562  sub     rsp, 20h
0x18002e566  mov     rax, r8
0x18002e569  mov     r10, rdx
0x18002e56c  mov     rdi, rcx
0x18002e56f  mov     rdx, rax; lpSubKey
0x18002e572  mov     rcx, r10; hKey
0x18002e575  mov     r8, r9; phkResult
0x18002e578  mov     rbx, r9
0x18002e57b  call    cs:__imp_RegCreateKeyW
0x18002e581  test    eax, eax
0x18002e583  jz      short loc_18002E590
0x18002e585  mov     qword ptr [rbx], 0
0x18002e58c  xor     eax, eax
0x18002e58e  jmp     short loc_18002E593
0x18002e590  mov     rax, [rbx]
0x18002e593  mov     [rdi], rax
0x18002e596  mov     rax, rdi
0x18002e599  mov     rbx, [rsp+28h+arg_0]
0x18002e59e  add     rsp, 20h
0x18002e5a2  pop     rdi
0x18002e5a3  retn
```
