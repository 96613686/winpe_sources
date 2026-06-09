# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180002ef0`
- end: `0x180002f2d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `61`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( v1 )
  {
    if ( v1 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  else if ( a1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180002ef0  push    rbx
0x180002ef2  sub     rsp, 20h
0x180002ef6  or      ebx, 0FFFFFFFFh
0x180002ef9  lock xadd [rcx+8], ebx
0x180002efe  sub     ebx, 1
0x180002f01  jnz     short loc_180002F13
0x180002f03  test    rcx, rcx
0x180002f06  jz      short loc_180002F25
0x180002f08  mov     rax, [rcx]
0x180002f0b  lea     edx, [rbx+1]
0x180002f0e  call    qword ptr [rax+28h]
0x180002f11  jmp     short loc_180002F25
0x180002f13  cmp     ebx, 1
0x180002f16  jnz     short loc_180002F25
0x180002f18  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002f1f  mov     rdx, [rcx]
0x180002f22  call    qword ptr [rdx+10h]
0x180002f25  mov     eax, ebx
0x180002f27  add     rsp, 20h
0x180002f2b  pop     rbx
0x180002f2c  retn
```
