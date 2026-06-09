# CMitigationClassFactory::~CMitigationClassFactory(void)

- ea: `0x180014f14`
- end: `0x180014f3d`
- name: `??1CMitigationClassFactory@@UEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CMitigationClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015060`

## callees

- `0x180015910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014f2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014f2a`

## pseudocode

```c
void __fastcall CMitigationClassFactory::~CMitigationClassFactory(CMitigationClassFactory *this)
{
  CTSimpleArray<IUnknown *,4294967294,CTPolicyCoTaskMem<IUnknown *>,CSimpleArrayStandardCompareHelper<IUnknown *>,CSimpleArrayStandardMergeHelper<IUnknown *>>::RemoveAll((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180014f14  push    rbx
0x180014f16  sub     rsp, 20h
0x180014f1a  mov     rbx, rcx
0x180014f1d  add     rcx, 58h ; 'X'
0x180014f21  call    ?RemoveAll@?$CTSimpleArray@PEAUIUnknown@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIUnknown@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIUnknown@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIUnknown@@@@@@QEAAXXZ; CTSimpleArray<IUnknown *,4294967294,CTPolicyCoTaskMem<IUnknown *>,CSimpleArrayStandardCompareHelper<IUnknown *>,CSimpleArrayStandardMergeHelper<IUnknown *>>::RemoveAll(void)
0x180014f26  lea     rcx, [rbx+30h]; lpCriticalSection
0x180014f2a  call    cs:__imp_DeleteCriticalSection
0x180014f30  mov     dword ptr [rbx+14h], 0C0000001h
0x180014f37  add     rsp, 20h
0x180014f3b  pop     rbx
0x180014f3c  retn
```
