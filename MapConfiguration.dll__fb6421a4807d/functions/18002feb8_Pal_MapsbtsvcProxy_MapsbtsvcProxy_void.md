# Pal::MapsbtsvcProxy::~MapsbtsvcProxy(void)

- ea: `0x18002feb8`
- end: `0x18002fed5`
- name: `??1MapsbtsvcProxy@Pal@@EEAA@XZ`
- size: `29`
- prototype: `void __fastcall(Pal::MapsbtsvcProxy *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800303d0`
- `0x180042620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fece`

## pseudocode

```c
void __fastcall Pal::MapsbtsvcProxy::~MapsbtsvcProxy(Pal::MapsbtsvcProxy *this)
{
  *((_QWORD *)this + 6) = 0;
  *(_QWORD *)this = &Pal::MapsbtsvcProxy::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002feb8  lea     rax, ??_7MapsbtsvcProxy@Pal@@6B@; const Pal::MapsbtsvcProxy::`vftable'
0x18002febf  mov     qword ptr [rcx+30h], 0
0x18002fec7  mov     [rcx], rax
0x18002feca  add     rcx, 8
0x18002fece  jmp     cs:__imp_DeleteCriticalSection
```
