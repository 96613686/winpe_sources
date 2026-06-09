# ATL::CComAggObject<CMigrationPlugin>::Release(void)

- ea: `0x180011e20`
- end: `0x180011ea1`
- name: `?Release@?$CComAggObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011e20`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMigrationPlugin>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180011e20  mov     [rsp+arg_0], rbx
0x180011e25  push    rdi
0x180011e26  sub     rsp, 20h
0x180011e2a  mov     r8d, [rcx+8]
0x180011e2e  mov     rbx, rcx
0x180011e31  mov     ecx, 7FFFFFFFh
0x180011e36  jmp     short loc_180011E4A
0x180011e38  lea     edx, [r8-1]
0x180011e3c  mov     eax, r8d
0x180011e3f  lock cmpxchg [rbx+8], edx
0x180011e44  jz      short loc_180011E4F
0x180011e46  mov     r8d, [rbx+8]
0x180011e4a  cmp     r8d, ecx
0x180011e4d  jnz     short loc_180011E38
0x180011e4f  lea     edi, [r8-1]
0x180011e53  test    edi, edi
0x180011e55  jnz     short loc_180011E94
0x180011e57  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011e5e  mov     rax, [rcx]
0x180011e61  mov     rax, [rax+8]
0x180011e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e6a  test    rbx, rbx
0x180011e6d  jz      short loc_180011E81
0x180011e6f  mov     rax, [rbx]
0x180011e72  lea     edx, [rdi+1]
0x180011e75  mov     rcx, rbx
0x180011e78  mov     rax, [rax+18h]
0x180011e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e81  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011e88  mov     rdx, [rcx]
0x180011e8b  mov     rax, [rdx+10h]
0x180011e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e94  mov     rbx, [rsp+28h+arg_0]
0x180011e99  mov     eax, edi
0x180011e9b  add     rsp, 20h
0x180011e9f  pop     rdi
0x180011ea0  retn
```
