# CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x180075c94`
- end: `0x180075cdc`
- name: `??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `72`
- prototype: `CAutoHKey *(CAutoHKey *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180075d04`

## callees

- `0x180075c94`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180075cb3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180075cb3`

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
0x180075c94  mov     [rsp+arg_0], rbx
0x180075c99  push    rdi
0x180075c9a  sub     rsp, 20h
0x180075c9e  mov     rax, r8
0x180075ca1  mov     r10, rdx
0x180075ca4  mov     rdi, rcx
0x180075ca7  mov     rdx, rax; lpSubKey
0x180075caa  mov     rcx, r10; hKey
0x180075cad  mov     r8, r9; phkResult
0x180075cb0  mov     rbx, r9
0x180075cb3  call    cs:__imp_RegCreateKeyW
0x180075cb9  test    eax, eax
0x180075cbb  jz      short loc_180075CC8
0x180075cbd  mov     qword ptr [rbx], 0
0x180075cc4  xor     eax, eax
0x180075cc6  jmp     short loc_180075CCB
0x180075cc8  mov     rax, [rbx]
0x180075ccb  mov     [rdi], rax
0x180075cce  mov     rax, rdi
0x180075cd1  mov     rbx, [rsp+28h+arg_0]
0x180075cd6  add     rsp, 20h
0x180075cda  pop     rdi
0x180075cdb  retn
```
