# CCcs::Free(void)

- ea: `0x18005f224`
- end: `0x18005f2a3`
- name: `?Free@CCcs@@QEAAXXZ`
- size: `127`
- prototype: `void __fastcall(CCcs *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18005f170`
- `0x18005f6ec`

## callees

- `0x180023010`
- `0x18005f1f8`
- `0x18005f224`

## import_xrefs

- `USP10!ScriptFreeCache` at `0x18005f288`
- `USP10!ScriptFreeCache` at `0x18005f288`

## pseudocode

```c
void __fastcall CCcs::Free(CCcs *this)
{
  _DWORD *v1; // rdi

  *(_QWORD *)((char *)this + 28) = 0;
  v1 = (_DWORD *)((char *)this + 40);
  *((_DWORD *)this + 9) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((CCcs **)this + 6) == (CCcs *)((char *)this + 40) )
  {
    v1 = (_DWORD *)*((_QWORD *)this + 6);
  }
  else
  {
    CW32System::FreePv(*((void **)this + 6));
    *((_QWORD *)this + 6) = v1;
  }
  *v1 = 0;
  if ( *((_QWORD *)this + 9) )
    CCcs::DestroyFont(this);
  if ( *((_QWORD *)this + 10) && g_pusp )
    ScriptFreeCache((SCRIPT_CACHE *)this + 10);
  *((_BYTE *)this + 123) &= ~1u;
  *((_WORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x18005f224  mov     [rsp+arg_0], rbx
0x18005f229  push    rdi
0x18005f22a  sub     rsp, 20h
0x18005f22e  xor     eax, eax
0x18005f230  mov     qword ptr [rcx+1Ch], 0
0x18005f238  lea     rdi, [rcx+28h]
0x18005f23c  mov     [rcx+24h], eax
0x18005f23f  mov     rbx, rcx
0x18005f242  mov     [rcx+10h], rax
0x18005f246  mov     [rcx+18h], eax
0x18005f249  cmp     [rcx+30h], rdi
0x18005f24d  jz      short loc_18005F25E
0x18005f24f  mov     rcx, [rcx+30h]; lpMem
0x18005f253  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18005f258  mov     [rbx+30h], rdi
0x18005f25c  jmp     short loc_18005F262
0x18005f25e  mov     rdi, [rcx+30h]
0x18005f262  xor     eax, eax
0x18005f264  mov     [rdi], eax
0x18005f266  cmp     [rbx+48h], rax
0x18005f26a  jz      short loc_18005F274
0x18005f26c  mov     rcx, rbx; this
0x18005f26f  call    ?DestroyFont@CCcs@@AEAAXXZ; CCcs::DestroyFont(void)
0x18005f274  lea     rcx, [rbx+50h]; psc
0x18005f278  cmp     qword ptr [rcx], 0
0x18005f27c  jz      short loc_18005F28E
0x18005f27e  cmp     cs:?g_pusp@@3PEAVCUniscribe@@EA, 0; CUniscribe * g_pusp
0x18005f286  jz      short loc_18005F28E
0x18005f288  call    cs:__imp_ScriptFreeCache
0x18005f28e  and     byte ptr [rbx+7Bh], 0FEh
0x18005f292  xor     eax, eax
0x18005f294  mov     [rbx+0Ah], ax
0x18005f298  mov     rbx, [rsp+28h+arg_0]
0x18005f29d  add     rsp, 20h
0x18005f2a1  pop     rdi
0x18005f2a2  retn
```
