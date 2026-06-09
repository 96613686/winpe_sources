# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180001b20`
- end: `0x180001b4d`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001b20`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ++*(_DWORD *)(a1 + 8);
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x180001b20  push    rbx
0x180001b22  sub     rsp, 20h
0x180001b26  inc     dword ptr [rcx+8]
0x180001b29  mov     ebx, [rcx+8]
0x180001b2c  cmp     ebx, 2
0x180001b2f  jnz     short loc_180001B45
0x180001b31  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001b38  mov     rdx, [rcx]
0x180001b3b  mov     rax, [rdx+8]
0x180001b3f  call    cs:__guard_dispatch_icall_fptr
0x180001b45  mov     eax, ebx
0x180001b47  add     rsp, 20h
0x180001b4b  pop     rbx
0x180001b4c  retn
```
