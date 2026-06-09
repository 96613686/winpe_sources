# CTSimpleArray<IUnknown *,4294967294,CTPolicyCoTaskMem<IUnknown *>,CSimpleArrayStandardCompareHelper<IUnknown *>,CSimpleArrayStandardMergeHelper<IUnknown *>>::RemoveAll(void)

- ea: `0x180015910`
- end: `0x18001594d`
- name: `?RemoveAll@?$CTSimpleArray@PEAUIUnknown@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIUnknown@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIUnknown@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIUnknown@@@@@@QEAAXXZ`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014f14`
- `0x180017580`

## callees

- `0x180015910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015925`

## pseudocode

```c
void __fastcall CTSimpleArray<IUnknown *,4294967294,CTPolicyCoTaskMem<IUnknown *>,CSimpleArrayStandardCompareHelper<IUnknown *>,CSimpleArrayStandardMergeHelper<IUnknown *>>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180015910  mov     [rsp+arg_0], rbx
0x180015915  push    rdi
0x180015916  sub     rsp, 20h
0x18001591a  mov     rbx, rcx
0x18001591d  mov     rcx, [rcx]; pv
0x180015920  test    rcx, rcx
0x180015923  jz      short loc_180015932
0x180015925  call    cs:__imp_CoTaskMemFree
0x18001592b  mov     qword ptr [rbx], 0
0x180015932  mov     qword ptr [rbx+8], 0
0x18001593a  mov     qword ptr [rbx+18h], 0
0x180015942  mov     rbx, [rsp+28h+arg_0]
0x180015947  add     rsp, 20h
0x18001594b  pop     rdi
0x18001594c  retn
```
