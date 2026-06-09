# CRegistry::CRegistry(void)

- ea: `0x140011be0`
- end: `0x140011c35`
- name: `??0CRegistry@@QEAA@XZ`
- size: `85`
- prototype: `CRegistry *__fastcall(CRegistry *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f91c`
- `0x140012f60`
- `0x140013510`

## callees

- `0x140011be0`
- `0x140013b00`
- `0x140013b40`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this)
{
  *((_QWORD *)this + 3) = afxPchNil;
  *((_BYTE *)this + 36) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = 0;
  CRegistry::SetDefaultValues(this);
  if ( !CRegistry::s_fPlatformSet )
    CRegistry::s_fPlatformSet = CRegistry::SetPlatformID();
  return this;
}

```

## disassembly

```asm
0x140011be0  mov     [rsp+arg_0], rcx
0x140011be5  push    rbx
0x140011be6  sub     rsp, 20h
0x140011bea  mov     rbx, rcx
0x140011bed  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140011bf4  mov     [rcx+18h], rax
0x140011bf8  mov     byte ptr [rcx+24h], 0
0x140011bfc  mov     qword ptr [rcx+8], 0
0x140011c04  mov     qword ptr [rcx+10h], 0
0x140011c0c  mov     qword ptr [rcx], 0
0x140011c13  call    ?SetDefaultValues@CRegistry@@AEAAXXZ; CRegistry::SetDefaultValues(void)
0x140011c18  cmp     cs:?s_fPlatformSet@CRegistry@@0HA, 0; int CRegistry::s_fPlatformSet
0x140011c1f  jnz     short loc_140011C2C
0x140011c21  call    ?SetPlatformID@CRegistry@@CAHXZ; CRegistry::SetPlatformID(void)
0x140011c26  mov     cs:?s_fPlatformSet@CRegistry@@0HA, eax; int CRegistry::s_fPlatformSet
0x140011c2c  mov     rax, rbx
0x140011c2f  add     rsp, 20h
0x140011c33  pop     rbx
0x140011c34  retn
```
