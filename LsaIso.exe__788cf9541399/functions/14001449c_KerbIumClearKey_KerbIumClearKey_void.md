# KerbIumClearKey::~KerbIumClearKey(void)

- ea: `0x14001449c`
- end: `0x1400144bf`
- name: `??1KerbIumClearKey@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(KerbIumClearKey *__hidden this)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140015410`
- `0x140015590`
- `0x140015740`
- `0x1400158c0`
- `0x140015b90`
- `0x140016140`
- `0x140016310`
- `0x140016ac0`
- `0x140017450`
- `0x1400175c0`
- `0x140017840`
- `0x140017a40`
- `0x140018340`
- `0x1400186e0`
- `0x140018ff0`
- `0x140019210`
- `0x140019890`
- `0x140019a00`
- `0x140019b50`
- `0x140019dd0`
- `0x140019f00`

## callees

- `0x14001449c`

## import_xrefs

- `KerbClientShared!KerbClientFree` at `0x1400144b8`

## pseudocode

```c
void __fastcall KerbIumClearKey::~KerbIumClearKey(KerbIumClearKey *this)
{
  __int64 v1; // rdx
  _BYTE *v2; // rax

  v1 = *((unsigned int *)this + 4);
  v2 = (_BYTE *)*((_QWORD *)this + 3);
  if ( *((_DWORD *)this + 4) )
  {
    do
    {
      *v2++ = 0;
      --v1;
    }
    while ( v1 );
  }
  KerbClientFree(*((void **)this + 3));
}

```

## disassembly

```asm
0x14001449c  mov     edx, [rcx+10h]
0x14001449f  mov     rax, [rcx+18h]
0x1400144a3  test    rdx, rdx
0x1400144a6  jz      short loc_1400144B4
0x1400144a8  mov     byte ptr [rax], 0
0x1400144ab  inc     rax
0x1400144ae  sub     rdx, 1
0x1400144b2  jnz     short loc_1400144A8
0x1400144b4  mov     rcx, [rcx+18h]
0x1400144b8  jmp     cs:__imp_?KerbClientFree@@YAXPEAX@Z; KerbClientFree(void *)
```
