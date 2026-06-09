# ATL::CComObject<MetadataPackageSource>::Release(void)

- ea: `0x180011cc0`
- end: `0x180011d41`
- name: `?Release@?$CComObject@VMetadataPackageSource@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011cc0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MetadataPackageSource>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 88LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180011cc0  mov     [rsp+arg_0], rbx
0x180011cc5  push    rdi
0x180011cc6  sub     rsp, 20h
0x180011cca  mov     r8d, [rcx+8]
0x180011cce  mov     rbx, rcx
0x180011cd1  mov     ecx, 7FFFFFFFh
0x180011cd6  jmp     short loc_180011CEA
0x180011cd8  lea     edx, [r8-1]
0x180011cdc  mov     eax, r8d
0x180011cdf  lock cmpxchg [rbx+8], edx
0x180011ce4  jz      short loc_180011CEF
0x180011ce6  mov     r8d, [rbx+8]
0x180011cea  cmp     r8d, ecx
0x180011ced  jnz     short loc_180011CD8
0x180011cef  lea     edi, [r8-1]
0x180011cf3  test    edi, edi
0x180011cf5  jnz     short loc_180011D34
0x180011cf7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011cfe  mov     rax, [rcx]
0x180011d01  mov     rax, [rax+8]
0x180011d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d0a  test    rbx, rbx
0x180011d0d  jz      short loc_180011D21
0x180011d0f  mov     rax, [rbx]
0x180011d12  lea     edx, [rdi+1]
0x180011d15  mov     rcx, rbx
0x180011d18  mov     rax, [rax+58h]
0x180011d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d21  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011d28  mov     rdx, [rcx]
0x180011d2b  mov     rax, [rdx+10h]
0x180011d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d34  mov     rbx, [rsp+28h+arg_0]
0x180011d39  mov     eax, edi
0x180011d3b  add     rsp, 20h
0x180011d3f  pop     rdi
0x180011d40  retn
```
