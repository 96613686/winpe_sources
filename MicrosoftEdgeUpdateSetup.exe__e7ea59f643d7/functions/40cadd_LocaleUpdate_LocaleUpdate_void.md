# _LocaleUpdate::~_LocaleUpdate(void)

- ea: `0x40cadd`
- end: `0x40caed`
- name: `??1_LocaleUpdate@@QAE@XZ`
- size: `16`
- prototype: `void __thiscall(_LocaleUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x41b29e`

## callees

- `0x40cadd`

## pseudocode

```c
void __thiscall _LocaleUpdate::~_LocaleUpdate(_LocaleUpdate *this)
{
  if ( *((_BYTE *)this + 12) )
    *(_DWORD *)(*(_DWORD *)this + 848) &= ~2u;
}

```

## disassembly

```asm
0x40cadd  cmp     byte ptr [ecx+0Ch], 0
0x40cae1  jz      short locret_40CAEC
0x40cae3  mov     eax, [ecx]
0x40cae5  and     dword ptr [eax+350h], 0FFFFFFFDh
0x40caec  retn
```
