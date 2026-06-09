# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800058d0`
- end: `0x18000595c`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x1800058d0`
- `0x180007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005927`
- `KERNEL32!DeleteCriticalSection` at `0x180005927`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] != (_BYTE)v3 )
      {
        Block[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x1800058d0  mov     [rsp+arg_0], rbx
0x1800058d5  push    rdi
0x1800058d6  sub     rsp, 20h
0x1800058da  mov     rbx, rcx
0x1800058dd  mov     r8d, 7FFFFFFFh
0x1800058e3  mov     ecx, [rcx+8]
0x1800058e6  jmp     short loc_1800058F7
0x1800058e8  lea     edx, [rcx-1]
0x1800058eb  mov     eax, ecx
0x1800058ed  lock cmpxchg [rbx+8], edx
0x1800058f2  jz      short loc_1800058FC
0x1800058f4  mov     ecx, [rbx+8]
0x1800058f7  cmp     ecx, r8d
0x1800058fa  jnz     short loc_1800058E8
0x1800058fc  lea     edi, [rcx-1]
0x1800058ff  test    edi, edi
0x180005901  jnz     short loc_180005937
0x180005903  test    rbx, rbx
0x180005906  jz      short loc_18000594F
0x180005908  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000590f  mov     dword ptr [rbx+8], 0C0000001h
0x180005916  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000591a  mov     [rbx], rax
0x18000591d  cmp     [rcx+28h], dil
0x180005921  jz      short loc_18000592D
0x180005923  mov     [rcx+28h], dil
0x180005927  call    cs:__imp_DeleteCriticalSection
0x18000592d  mov     rcx, rbx; Block
0x180005930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005935  jmp     short loc_18000594F
0x180005937  cmp     edi, 1
0x18000593a  jnz     short loc_18000594F
0x18000593c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005943  mov     rdx, [rcx]
0x180005946  mov     rax, [rdx+10h]
0x18000594a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594f  mov     rbx, [rsp+28h+arg_0]
0x180005954  mov     eax, edi
0x180005956  add     rsp, 20h
0x18000595a  pop     rdi
0x18000595b  retn
```
