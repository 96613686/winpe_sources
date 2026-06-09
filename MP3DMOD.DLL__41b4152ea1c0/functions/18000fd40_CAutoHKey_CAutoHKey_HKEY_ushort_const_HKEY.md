# CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18000fd40`
- end: `0x18000fd88`
- name: `??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `72`
- prototype: `CAutoHKey *(CAutoHKey *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ffb4`

## callees

- `0x18000fd40`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000fd5f`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000fd5f`

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
0x18000fd40  mov     [rsp+arg_0], rbx
0x18000fd45  push    rdi
0x18000fd46  sub     rsp, 20h
0x18000fd4a  mov     rax, r8
0x18000fd4d  mov     r10, rdx
0x18000fd50  mov     rdi, rcx
0x18000fd53  mov     rdx, rax; lpSubKey
0x18000fd56  mov     rcx, r10; hKey
0x18000fd59  mov     r8, r9; phkResult
0x18000fd5c  mov     rbx, r9
0x18000fd5f  call    cs:__imp_RegCreateKeyW
0x18000fd65  test    eax, eax
0x18000fd67  jz      short loc_18000FD74
0x18000fd69  mov     qword ptr [rbx], 0
0x18000fd70  xor     eax, eax
0x18000fd72  jmp     short loc_18000FD77
0x18000fd74  mov     rax, [rbx]
0x18000fd77  mov     [rdi], rax
0x18000fd7a  mov     rax, rdi
0x18000fd7d  mov     rbx, [rsp+28h+arg_0]
0x18000fd82  add     rsp, 20h
0x18000fd86  pop     rdi
0x18000fd87  retn
```
