# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180004ac0`
- end: `0x180004b4d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ac0`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004b20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004b20`
- `KERNEL32!DeleteCriticalSection` at `0x180004b17`
- `KERNEL32!DeleteCriticalSection` at `0x180004b17`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
      if ( a1[56] != (_BYTE)v3 )
      {
        a1[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
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
0x180004ac0  mov     [rsp+arg_0], rbx
0x180004ac5  push    rdi
0x180004ac6  sub     rsp, 20h
0x180004aca  mov     rbx, rcx
0x180004acd  mov     r8d, 7FFFFFFFh
0x180004ad3  mov     ecx, [rcx+8]
0x180004ad6  jmp     short loc_180004AE7
0x180004ad8  lea     edx, [rcx-1]
0x180004adb  mov     eax, ecx
0x180004add  lock cmpxchg [rbx+8], edx
0x180004ae2  jz      short loc_180004AEC
0x180004ae4  mov     ecx, [rbx+8]
0x180004ae7  cmp     ecx, r8d
0x180004aea  jnz     short loc_180004AD8
0x180004aec  lea     edi, [rcx-1]
0x180004aef  test    edi, edi
0x180004af1  jnz     short loc_180004B28
0x180004af3  test    rbx, rbx
0x180004af6  jz      short loc_180004B40
0x180004af8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004aff  mov     dword ptr [rbx+8], 0C0000001h
0x180004b06  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004b0a  mov     [rbx], rax
0x180004b0d  cmp     [rcx+28h], dil
0x180004b11  jz      short loc_180004B1D
0x180004b13  mov     [rcx+28h], dil
0x180004b17  call    cs:__imp_DeleteCriticalSection
0x180004b1d  mov     rcx, rbx
0x180004b20  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004b26  jmp     short loc_180004B40
0x180004b28  cmp     edi, 1
0x180004b2b  jnz     short loc_180004B40
0x180004b2d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b34  mov     rdx, [rcx]
0x180004b37  mov     rax, [rdx+10h]
0x180004b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b40  mov     rbx, [rsp+28h+arg_0]
0x180004b45  mov     eax, edi
0x180004b47  add     rsp, 20h
0x180004b4b  pop     rdi
0x180004b4c  retn
```
