# CContainerMasks::StaticData::~StaticData(void)

- ea: `0x18000d624`
- end: `0x18000d659`
- name: `??1StaticData@CContainerMasks@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CContainerMasks::StaticData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027240`

## callees

- `0x18000d624`
- `0x18000d6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d64d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d64d`

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
0x18000d624  mov     [rsp+arg_0], rbx
0x18000d629  push    rdi
0x18000d62a  sub     rsp, 20h
0x18000d62e  cmp     byte ptr [rcx+70h], 0
0x18000d632  mov     rdi, rcx
0x18000d635  jnz     short loc_18000D649
0x18000d637  mov     rcx, rdi
0x18000d63a  mov     rbx, [rsp+28h+arg_0]
0x18000d63f  add     rsp, 20h
0x18000d643  pop     rdi
0x18000d644  jmp     ?RemoveAll@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::RemoveAll(void)
0x18000d649  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000d64d  call    cs:__imp_DeleteCriticalSection
0x18000d653  mov     byte ptr [rdi+70h], 0
0x18000d657  jmp     short loc_18000D637
```
