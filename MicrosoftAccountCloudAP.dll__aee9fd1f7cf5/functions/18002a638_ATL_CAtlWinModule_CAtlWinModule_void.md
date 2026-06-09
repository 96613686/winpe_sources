# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002a638`
- end: `0x18002a672`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800318e0`

## callees

- `0x18002a638`
- `0x18002a7ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a658`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a658`

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
0x18002a638  push    rbx
0x18002a63a  sub     rsp, 20h
0x18002a63e  mov     rbx, rcx
0x18002a641  test    rcx, rcx
0x18002a644  jz      short loc_18002A664
0x18002a646  cmp     dword ptr [rcx], 48h ; 'H'
0x18002a649  jnz     short loc_18002A664
0x18002a64b  add     rcx, 38h ; '8'
0x18002a64f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002a654  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a658  call    cs:__imp_DeleteCriticalSection
0x18002a65e  mov     dword ptr [rbx], 0
0x18002a664  lea     rcx, [rbx+38h]
0x18002a668  add     rsp, 20h
0x18002a66c  pop     rbx
0x18002a66d  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
