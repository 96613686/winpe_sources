# KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *)

- ea: `0x14001431c`
- end: `0x140014369`
- name: `??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@@Z`
- size: `77`
- prototype: `KerbIumClearKey *__fastcall(KerbIumClearKey *__hidden this, struct _KERB_ENCRYPTION_KEY *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140015590`
- `0x140015b90`
- `0x140016140`
- `0x1400175c0`
- `0x140017840`
- `0x140017a40`
- `0x140018340`
- `0x140018ff0`
- `0x140019210`
- `0x140019a00`
- `0x140019b50`
- `0x140019f00`

## callees

- `0x14001431c`
- `0x140014524`

## pseudocode

```c
KerbIumClearKey *__fastcall KerbIumClearKey::KerbIumClearKey(KerbIumClearKey *this, struct _KERB_ENCRYPTION_KEY *a2)
{
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  if ( a2 && *((_DWORD *)a2 + 2) == 3 )
  {
    KerbIumClearKey::Decrypt(this, a2);
    *((_DWORD *)this + 12) = *((_DWORD *)this + 10) >= 0;
  }
  else
  {
    *((_DWORD *)this + 10) = -1073741811;
  }
  return this;
}

```

## disassembly

```asm
0x14001431c  push    rbx
0x14001431e  sub     rsp, 20h
0x140014322  xor     eax, eax
0x140014324  xorps   xmm0, xmm0
0x140014327  mov     rbx, rcx
0x14001432a  movups  xmmword ptr [rcx], xmm0
0x14001432d  movups  xmmword ptr [rcx+10h], xmm0
0x140014331  mov     [rcx+20h], rax
0x140014335  mov     [rcx+28h], rax
0x140014339  mov     [rcx+30h], eax
0x14001433c  test    rdx, rdx
0x14001433f  jz      short loc_140014359
0x140014341  cmp     dword ptr [rdx+8], 3
0x140014345  jnz     short loc_140014359
0x140014347  call    ?Decrypt@KerbIumClearKey@@AEAAXPEAU_KERB_ENCRYPTION_KEY@@@Z; KerbIumClearKey::Decrypt(_KERB_ENCRYPTION_KEY *)
0x14001434c  mov     eax, [rbx+28h]
0x14001434f  not     eax
0x140014351  shr     eax, 1Fh
0x140014354  mov     [rbx+30h], eax
0x140014357  jmp     short loc_140014360
0x140014359  mov     dword ptr [rcx+28h], 0C000000Dh
0x140014360  mov     rax, rbx
0x140014363  add     rsp, 20h
0x140014367  pop     rbx
0x140014368  retn
```
