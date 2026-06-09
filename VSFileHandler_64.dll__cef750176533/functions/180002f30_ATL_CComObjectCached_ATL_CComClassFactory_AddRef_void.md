# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002f30`
- end: `0x180002f5c`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `44`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f30`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x180002f30  push    rbx
0x180002f32  sub     rsp, 20h
0x180002f36  mov     ebx, 1
0x180002f3b  lock xadd [rcx+8], ebx
0x180002f40  inc     ebx
0x180002f42  cmp     ebx, 2
0x180002f45  jnz     short loc_180002F54
0x180002f47  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002f4e  mov     rdx, [rcx]
0x180002f51  call    qword ptr [rdx+8]
0x180002f54  mov     eax, ebx
0x180002f56  add     rsp, 20h
0x180002f5a  pop     rbx
0x180002f5b  retn
```
