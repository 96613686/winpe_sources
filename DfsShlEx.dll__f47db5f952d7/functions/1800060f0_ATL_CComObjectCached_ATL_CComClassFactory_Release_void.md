# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800060f0`
- end: `0x18000617d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800060f0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006150`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006150`
- `KERNEL32!DeleteCriticalSection` at `0x180006147`
- `KERNEL32!DeleteCriticalSection` at `0x180006147`

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
0x1800060f0  mov     [rsp+arg_0], rbx
0x1800060f5  push    rdi
0x1800060f6  sub     rsp, 20h
0x1800060fa  mov     rbx, rcx
0x1800060fd  mov     r8d, 7FFFFFFFh
0x180006103  mov     ecx, [rcx+8]
0x180006106  jmp     short loc_180006117
0x180006108  lea     edx, [rcx-1]
0x18000610b  mov     eax, ecx
0x18000610d  lock cmpxchg [rbx+8], edx
0x180006112  jz      short loc_18000611C
0x180006114  mov     ecx, [rbx+8]
0x180006117  cmp     ecx, r8d
0x18000611a  jnz     short loc_180006108
0x18000611c  lea     edi, [rcx-1]
0x18000611f  test    edi, edi
0x180006121  jnz     short loc_180006158
0x180006123  test    rbx, rbx
0x180006126  jz      short loc_180006170
0x180006128  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000612f  mov     dword ptr [rbx+8], 0C0000001h
0x180006136  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000613a  mov     [rbx], rax
0x18000613d  cmp     [rcx+28h], dil
0x180006141  jz      short loc_18000614D
0x180006143  mov     [rcx+28h], dil
0x180006147  call    cs:__imp_DeleteCriticalSection
0x18000614d  mov     rcx, rbx
0x180006150  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006156  jmp     short loc_180006170
0x180006158  cmp     edi, 1
0x18000615b  jnz     short loc_180006170
0x18000615d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006164  mov     rdx, [rcx]
0x180006167  mov     rax, [rdx+10h]
0x18000616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006170  mov     rbx, [rsp+28h+arg_0]
0x180006175  mov     eax, edi
0x180006177  add     rsp, 20h
0x18000617b  pop     rdi
0x18000617c  retn
```
