# NavigationTreeBase::NavigationTreeBase(ConfigNameTablePair *)

- ea: `0x1800042ec`
- end: `0x180004318`
- name: `??0NavigationTreeBase@@QEAA@PEAVConfigNameTablePair@@@Z`
- size: `44`
- prototype: `NavigationTreeBase *__fastcall(NavigationTreeBase *__hidden this, struct ConfigNameTablePair *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004164`
- `0x180005b24`
- `0x1800098a0`
- `0x18001069c`

## callees

- `0x1800042ec`

## pseudocode

```c
NavigationTreeBase *__fastcall NavigationTreeBase::NavigationTreeBase(
        NavigationTreeBase *this,
        struct ConfigNameTablePair *a2)
{
  *(_QWORD *)this = &InvasivePtrObject::`vftable';
  *(_QWORD *)this = &NavigationTreeBase::`vftable';
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  return this;
}

```

## disassembly

```asm
0x1800042ec  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x1800042f3  mov     [rcx], rax
0x1800042f6  lea     rax, ??_7NavigationTreeBase@@6B@; const NavigationTreeBase::`vftable'
0x1800042fd  mov     [rcx], rax
0x180004300  mov     dword ptr [rcx+8], 1
0x180004307  mov     [rcx+10h], rdx
0x18000430b  test    rdx, rdx
0x18000430e  jz      short loc_180004314
0x180004310  lock inc dword ptr [rdx+8]
0x180004314  mov     rax, rcx
0x180004317  retn
```
