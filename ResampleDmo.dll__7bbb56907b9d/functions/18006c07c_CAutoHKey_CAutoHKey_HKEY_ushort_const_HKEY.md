# CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18006c07c`
- end: `0x18006c0c4`
- name: `??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `72`
- prototype: `CAutoHKey *(CAutoHKey *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18006c224`

## callees

- `0x18006c07c`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006c09b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006c09b`

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
0x18006c07c  mov     [rsp+arg_0], rbx
0x18006c081  push    rdi
0x18006c082  sub     rsp, 20h
0x18006c086  mov     rax, r8
0x18006c089  mov     r10, rdx
0x18006c08c  mov     rdi, rcx
0x18006c08f  mov     rdx, rax; lpSubKey
0x18006c092  mov     rcx, r10; hKey
0x18006c095  mov     r8, r9; phkResult
0x18006c098  mov     rbx, r9
0x18006c09b  call    cs:__imp_RegCreateKeyW
0x18006c0a1  test    eax, eax
0x18006c0a3  jz      short loc_18006C0B0
0x18006c0a5  mov     qword ptr [rbx], 0
0x18006c0ac  xor     eax, eax
0x18006c0ae  jmp     short loc_18006C0B3
0x18006c0b0  mov     rax, [rbx]
0x18006c0b3  mov     [rdi], rax
0x18006c0b6  mov     rax, rdi
0x18006c0b9  mov     rbx, [rsp+28h+arg_0]
0x18006c0be  add     rsp, 20h
0x18006c0c2  pop     rdi
0x18006c0c3  retn
```
