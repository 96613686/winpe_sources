# std::_Lockit::_Lockit(int)

- ea: `0x180002394`
- end: `0x1800023d2`
- name: `??0_Lockit@std@@QEAA@H@Z`
- size: `62`
- prototype: `std::_Lockit *__fastcall(std::_Lockit *this, int)`
- caller_count: `50`
- callee_count: `3`
- tags: ``

## callers

- `0x18000259c`
- `0x18000264c`
- `0x1800028a0`
- `0x180002c3c`
- `0x180002d80`
- `0x180002ec4`
- `0x180003008`
- `0x18000314c`
- `0x180005efc`
- `0x180005fe8`
- `0x1800060cc`
- `0x1800095bc`
- `0x180009700`
- `0x180009844`
- `0x180009988`
- `0x180009acc`
- `0x180009c10`
- `0x180009d54`
- `0x180009e98`
- `0x180009fdc`
- `0x18000a120`
- `0x18000a264`
- `0x18000a3a8`
- `0x18000a4ec`
- `0x18000a630`
- `0x18000a774`
- `0x18000a8b8`
- `0x18000a9fc`
- `0x18000ab40`
- `0x18000ac84`
- `0x18000adc8`
- `0x18000af0c`
- `0x18000b050`
- `0x18000b194`
- `0x18000b2d8`
- `0x18000b41c`
- `0x18000b560`
- `0x180012c38`
- `0x180013898`
- `0x18001cc84`
- `0x18001cdc8`
- `0x18001cf0c`
- `0x18001d050`
- `0x18001d194`
- `0x18001d2d8`
- `0x18001d41c`
- `0x18001d560`
- `0x18001f4a0`
- `0x18003158c`
- `0x18003178c`

## callees

- `0x180002394`
- `0x180008668`
- `0x1800267ba`

## pseudocode

```c
std::_Lockit *__fastcall std::_Lockit::_Lockit(std::_Lockit *this, int a2)
{
  *(_DWORD *)this = a2;
  if ( a2 )
  {
    if ( a2 < 4 )
      Mtxlock((LPCRITICAL_SECTION)&qword_1800464F0[5 * a2]);
  }
  else
  {
    lock_0(12);
  }
  return this;
}

```

## disassembly

```asm
0x180002394  push    rbx
0x180002396  sub     rsp, 20h
0x18000239a  mov     [rcx], edx
0x18000239c  mov     rbx, rcx
0x18000239f  test    edx, edx
0x1800023a1  jnz     short loc_1800023AD
0x1800023a3  lea     ecx, [rdx+0Ch]
0x1800023a6  call    _lock_0
0x1800023ab  jmp     short loc_1800023C9
0x1800023ad  cmp     edx, 4
0x1800023b0  jge     short loc_1800023C9
0x1800023b2  movsxd  rax, edx
0x1800023b5  lea     rcx, [rax+rax*4]
0x1800023b9  lea     rax, qword_1800464F0
0x1800023c0  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800023c4  call    _Mtxlock
0x1800023c9  mov     rax, rbx
0x1800023cc  add     rsp, 20h
0x1800023d0  pop     rbx
0x1800023d1  retn
```
