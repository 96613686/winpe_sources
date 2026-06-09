# std::_Lockit::~_Lockit(void)

- ea: `0x18000241c`
- end: `0x180002451`
- name: `??1_Lockit@std@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(std::_Lockit *__hidden this)`
- caller_count: `55`
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
- `0x180031a54`

## callees

- `0x18000241c`
- `0x180008678`
- `0x1800267c6`

## pseudocode

```c
void __fastcall std::_Lockit::~_Lockit(std::_Lockit *this)
{
  __int64 v1; // rax

  v1 = *(int *)this;
  if ( (_DWORD)v1 )
  {
    if ( (int)v1 < 4 )
      Mtxunlock((LPCRITICAL_SECTION)&qword_1800464F0[5 * v1]);
  }
  else
  {
    unlock_0(12);
  }
}

```

## disassembly

```asm
0x18000241c  sub     rsp, 28h
0x180002420  movsxd  rax, dword ptr [rcx]
0x180002423  test    eax, eax
0x180002425  jnz     short loc_180002433
0x180002427  lea     ecx, [rax+0Ch]
0x18000242a  add     rsp, 28h
0x18000242e  jmp     _unlock_0
0x180002433  cmp     eax, 4
0x180002436  jge     short loc_18000244C
0x180002438  lea     rcx, [rax+rax*4]
0x18000243c  lea     rax, qword_1800464F0
0x180002443  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180002447  call    _Mtxunlock
0x18000244c  add     rsp, 28h
0x180002450  retn
```
