# CContainerMasks::StaticData::~StaticData(void)

- ea: `0x18000df14`
- end: `0x18000df4f`
- name: `??1StaticData@CContainerMasks@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CContainerMasks::StaticData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028530`

## callees

- `0x18000df14`
- `0x18000dfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df3d`

## pseudocode

```c
void __fastcall CContainerMasks::StaticData::~StaticData(CContainerMasks::StaticData *this)
{
  if ( *((_BYTE *)this + 112) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    *((_BYTE *)this + 112) = 0;
  }
  ATL::CAtlMap<_GUID,unsigned long,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned long>>::RemoveAll(this);
}

```

## disassembly

```asm
0x18000df14  mov     [rsp+arg_0], rbx
0x18000df19  push    rdi
0x18000df1a  sub     rsp, 20h
0x18000df1e  cmp     byte ptr [rcx+70h], 0
0x18000df22  mov     rdi, rcx
0x18000df25  jnz     short loc_18000DF39
0x18000df27  mov     rcx, rdi
0x18000df2a  mov     rbx, [rsp+28h+arg_0]
0x18000df2f  add     rsp, 20h
0x18000df33  pop     rdi
0x18000df34  jmp     ?RemoveAll@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::RemoveAll(void)
0x18000df39  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000df3d  call    cs:__imp_DeleteCriticalSection
0x18000df44  nop     dword ptr [rax+rax+00h]
0x18000df49  mov     byte ptr [rdi+70h], 0
0x18000df4d  jmp     short loc_18000DF27
```
