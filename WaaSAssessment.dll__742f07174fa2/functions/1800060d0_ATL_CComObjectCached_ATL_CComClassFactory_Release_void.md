# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800060d0`
- end: `0x18000615d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800060d0`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006130`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006130`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006127`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006127`

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
0x1800060d0  mov     [rsp+arg_0], rbx
0x1800060d5  push    rdi
0x1800060d6  sub     rsp, 20h
0x1800060da  mov     rbx, rcx
0x1800060dd  mov     r8d, 7FFFFFFFh
0x1800060e3  mov     ecx, [rcx+8]
0x1800060e6  jmp     short loc_1800060F7
0x1800060e8  lea     edx, [rcx-1]
0x1800060eb  mov     eax, ecx
0x1800060ed  lock cmpxchg [rbx+8], edx
0x1800060f2  jz      short loc_1800060FC
0x1800060f4  mov     ecx, [rbx+8]
0x1800060f7  cmp     ecx, r8d
0x1800060fa  jnz     short loc_1800060E8
0x1800060fc  lea     edi, [rcx-1]
0x1800060ff  test    edi, edi
0x180006101  jnz     short loc_180006138
0x180006103  test    rbx, rbx
0x180006106  jz      short loc_180006150
0x180006108  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000610f  mov     dword ptr [rbx+8], 0C0000001h
0x180006116  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000611a  mov     [rbx], rax
0x18000611d  cmp     [rcx+28h], dil
0x180006121  jz      short loc_18000612D
0x180006123  mov     [rcx+28h], dil
0x180006127  call    cs:__imp_DeleteCriticalSection
0x18000612d  mov     rcx, rbx
0x180006130  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006136  jmp     short loc_180006150
0x180006138  cmp     edi, 1
0x18000613b  jnz     short loc_180006150
0x18000613d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006144  mov     rdx, [rcx]
0x180006147  mov     rax, [rdx+10h]
0x18000614b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006150  mov     rbx, [rsp+28h+arg_0]
0x180006155  mov     eax, edi
0x180006157  add     rsp, 20h
0x18000615b  pop     rdi
0x18000615c  retn
```
