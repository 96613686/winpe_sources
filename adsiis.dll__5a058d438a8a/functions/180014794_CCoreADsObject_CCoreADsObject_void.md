# CCoreADsObject::CCoreADsObject(void)

- ea: `0x180014794`
- end: `0x1800147d2`
- name: `??0CCoreADsObject@@QEAA@XZ`
- size: `62`
- prototype: `CCoreADsObject *__fastcall(CCoreADsObject *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d44`
- `0x180002950`
- `0x1800040b0`
- `0x18000816c`
- `0x180009068`
- `0x180009154`
- `0x18000978c`

## callees

- `0x180019504`

## pseudocode

```c
CCoreADsObject *__fastcall CCoreADsObject::CCoreADsObject(CCoreADsObject *this, struct WIN32_CRITSEC *a2)
{
  SERVER_CACHE::ReferenceGlobalCache((__int64)this, a2);
  *(_QWORD *)this = &CCoreADsObject::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  return this;
}

```

## disassembly

```asm
0x180014794  push    rbx
0x180014796  sub     rsp, 20h
0x18001479a  mov     rbx, rcx
0x18001479d  call    ?ReferenceGlobalCache@SERVER_CACHE@@SAXXZ; SERVER_CACHE::ReferenceGlobalCache(void)
0x1800147a2  lea     rax, ??_7CCoreADsObject@@6B@; const CCoreADsObject::`vftable'
0x1800147a9  mov     [rbx], rax
0x1800147ac  xor     eax, eax
0x1800147ae  mov     [rbx+8], eax
0x1800147b1  mov     [rbx+10h], rax
0x1800147b5  mov     [rbx+18h], rax
0x1800147b9  mov     [rbx+20h], rax
0x1800147bd  mov     [rbx+28h], rax
0x1800147c1  mov     [rbx+30h], rax
0x1800147c5  mov     [rbx+38h], rax
0x1800147c9  mov     rax, rbx
0x1800147cc  add     rsp, 20h
0x1800147d0  pop     rbx
0x1800147d1  retn
```
