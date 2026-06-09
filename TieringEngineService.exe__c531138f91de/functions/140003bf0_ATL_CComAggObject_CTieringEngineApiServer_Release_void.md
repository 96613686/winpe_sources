# ATL::CComAggObject<CTieringEngineApiServer>::Release(void)

- ea: `0x140003bf0`
- end: `0x140003c71`
- name: `?Release@?$CComAggObject@VCTieringEngineApiServer@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003bf0`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CTieringEngineApiServer>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140003bf0  mov     [rsp+arg_0], rbx
0x140003bf5  push    rdi
0x140003bf6  sub     rsp, 20h
0x140003bfa  mov     r8d, [rcx+8]
0x140003bfe  mov     rbx, rcx
0x140003c01  mov     ecx, 7FFFFFFFh
0x140003c06  jmp     short loc_140003C1A
0x140003c08  lea     edx, [r8-1]
0x140003c0c  mov     eax, r8d
0x140003c0f  lock cmpxchg [rbx+8], edx
0x140003c14  jz      short loc_140003C1F
0x140003c16  mov     r8d, [rbx+8]
0x140003c1a  cmp     r8d, ecx
0x140003c1d  jnz     short loc_140003C08
0x140003c1f  lea     edi, [r8-1]
0x140003c23  test    edi, edi
0x140003c25  jnz     short loc_140003C64
0x140003c27  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003c2e  mov     rax, [rcx]
0x140003c31  mov     rax, [rax+8]
0x140003c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c3a  test    rbx, rbx
0x140003c3d  jz      short loc_140003C51
0x140003c3f  mov     rax, [rbx]
0x140003c42  lea     edx, [rdi+1]
0x140003c45  mov     rcx, rbx
0x140003c48  mov     rax, [rax+18h]
0x140003c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c51  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003c58  mov     rdx, [rcx]
0x140003c5b  mov     rax, [rdx+10h]
0x140003c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c64  mov     rbx, [rsp+28h+arg_0]
0x140003c69  mov     eax, edi
0x140003c6b  add     rsp, 20h
0x140003c6f  pop     rdi
0x140003c70  retn
```
