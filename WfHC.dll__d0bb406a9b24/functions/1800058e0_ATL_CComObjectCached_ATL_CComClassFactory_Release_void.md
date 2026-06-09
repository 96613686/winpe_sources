# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800058e0`
- end: `0x180005988`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `168`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800058e0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005950`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005950`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005947`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005947`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(_DWORD *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  for ( i = a1[2]; i != 0x7FFFFFFF; i = a1[2] )
  {
    if ( i == _InterlockedCompareExchange(a1 + 2, i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i != 1 )
  {
    if ( i == 2 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    return v3;
  }
  if ( !a1 )
    return v3;
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 4);
  if ( LOBYTE(v4[1].DebugInfo) != (_BYTE)v3 )
  {
    LOBYTE(v4[1].DebugInfo) = 0;
    DeleteCriticalSection(v4);
  }
  operator delete(a1);
  return v3;
}

```

## disassembly

```asm
0x1800058e0  mov     [rsp+arg_0], rbx
0x1800058e5  push    rdi
0x1800058e6  sub     rsp, 20h
0x1800058ea  mov     r8d, [rcx+8]
0x1800058ee  mov     rbx, rcx
0x1800058f1  cmp     r8d, 7FFFFFFFh
0x1800058f8  jz      short loc_18000591B
0x1800058fa  nop     word ptr [rax+rax+00h]
0x180005900  lea     edx, [r8-1]
0x180005904  mov     eax, r8d
0x180005907  lock cmpxchg [rcx+8], edx
0x18000590c  jz      short loc_18000591B
0x18000590e  mov     r8d, [rcx+8]
0x180005912  cmp     r8d, 7FFFFFFFh
0x180005919  jnz     short loc_180005900
0x18000591b  lea     edi, [r8-1]
0x18000591f  test    edi, edi
0x180005921  jnz     short loc_180005963
0x180005923  test    rbx, rbx
0x180005926  jz      short loc_18000597B
0x180005928  mov     dword ptr [rcx+8], 0C0000001h
0x18000592f  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005936  mov     [rcx], rax
0x180005939  add     rcx, 10h; lpCriticalSection
0x18000593d  cmp     [rcx+28h], dil
0x180005941  jz      short loc_18000594D
0x180005943  mov     [rcx+28h], dil
0x180005947  call    cs:__imp_DeleteCriticalSection
0x18000594d  mov     rcx, rbx
0x180005950  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005956  mov     eax, edi
0x180005958  mov     rbx, [rsp+28h+arg_0]
0x18000595d  add     rsp, 20h
0x180005961  pop     rdi
0x180005962  retn
0x180005963  cmp     edi, 1
0x180005966  jnz     short loc_18000597B
0x180005968  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000596f  mov     rax, [rcx]
0x180005972  mov     rax, [rax+10h]
0x180005976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597b  mov     rbx, [rsp+28h+arg_0]
0x180005980  mov     eax, edi
0x180005982  add     rsp, 20h
0x180005986  pop     rdi
0x180005987  retn
```
