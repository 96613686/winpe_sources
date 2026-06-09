# ATL::CComObjectCached<CBrowserFactory>::Release(void)

- ea: `0x180005d00`
- end: `0x180005d8d`
- name: `?Release@?$CComObjectCached@VCBrowserFactory@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005d00`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180005d60`
- `msvcrt!free` at `0x180005d60`
- `KERNEL32!DeleteCriticalSection` at `0x180005d57`
- `KERNEL32!DeleteCriticalSection` at `0x180005d57`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CBrowserFactory>::Release(char *Block)
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
      free(Block);
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
0x180005d00  mov     [rsp+arg_0], rbx
0x180005d05  push    rdi
0x180005d06  sub     rsp, 20h
0x180005d0a  mov     rbx, rcx
0x180005d0d  mov     r8d, 7FFFFFFFh
0x180005d13  mov     ecx, [rcx+8]
0x180005d16  jmp     short loc_180005D27
0x180005d18  lea     edx, [rcx-1]
0x180005d1b  mov     eax, ecx
0x180005d1d  lock cmpxchg [rbx+8], edx
0x180005d22  jz      short loc_180005D2C
0x180005d24  mov     ecx, [rbx+8]
0x180005d27  cmp     ecx, r8d
0x180005d2a  jnz     short loc_180005D18
0x180005d2c  lea     edi, [rcx-1]
0x180005d2f  test    edi, edi
0x180005d31  jnz     short loc_180005D68
0x180005d33  test    rbx, rbx
0x180005d36  jz      short loc_180005D80
0x180005d38  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005d3f  mov     dword ptr [rbx+8], 0C0000001h
0x180005d46  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005d4a  mov     [rbx], rax
0x180005d4d  cmp     [rcx+28h], dil
0x180005d51  jz      short loc_180005D5D
0x180005d53  mov     [rcx+28h], dil
0x180005d57  call    cs:__imp_DeleteCriticalSection
0x180005d5d  mov     rcx, rbx; Block
0x180005d60  call    cs:__imp_free
0x180005d66  jmp     short loc_180005D80
0x180005d68  cmp     edi, 1
0x180005d6b  jnz     short loc_180005D80
0x180005d6d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d74  mov     rdx, [rcx]
0x180005d77  mov     rax, [rdx+10h]
0x180005d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d80  mov     rbx, [rsp+28h+arg_0]
0x180005d85  mov     eax, edi
0x180005d87  add     rsp, 20h
0x180005d8b  pop     rdi
0x180005d8c  retn
```
