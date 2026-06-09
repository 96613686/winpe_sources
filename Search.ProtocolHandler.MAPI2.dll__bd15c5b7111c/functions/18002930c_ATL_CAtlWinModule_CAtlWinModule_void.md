# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002930c`
- end: `0x180029346`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003e3e0`

## callees

- `0x18002930c`
- `0x1800293fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002932c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002932c`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  if ( this && *(_DWORD *)this == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x18002930c  push    rbx
0x18002930e  sub     rsp, 20h
0x180029312  mov     rbx, rcx
0x180029315  test    rcx, rcx
0x180029318  jz      short loc_180029338
0x18002931a  cmp     dword ptr [rcx], 48h ; 'H'
0x18002931d  jnz     short loc_180029338
0x18002931f  add     rcx, 38h ; '8'
0x180029323  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180029328  lea     rcx, [rbx+8]; lpCriticalSection
0x18002932c  call    cs:__imp_DeleteCriticalSection
0x180029332  mov     dword ptr [rbx], 0
0x180029338  lea     rcx, [rbx+38h]
0x18002933c  add     rsp, 20h
0x180029340  pop     rbx
0x180029341  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
