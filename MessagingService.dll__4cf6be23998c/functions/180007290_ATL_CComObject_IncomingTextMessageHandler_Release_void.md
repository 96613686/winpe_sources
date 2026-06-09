# ATL::CComObject<IncomingTextMessageHandler>::Release(void)

- ea: `0x180007290`
- end: `0x180007311`
- name: `?Release@?$CComObject@VIncomingTextMessageHandler@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007290`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IncomingTextMessageHandler>::Release(volatile signed __int32 *a1)
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
0x180007290  mov     [rsp+arg_0], rbx
0x180007295  push    rdi
0x180007296  sub     rsp, 20h
0x18000729a  mov     r8d, [rcx+8]
0x18000729e  mov     rbx, rcx
0x1800072a1  mov     ecx, 7FFFFFFFh
0x1800072a6  jmp     short loc_1800072BA
0x1800072a8  lea     edx, [r8-1]
0x1800072ac  mov     eax, r8d
0x1800072af  lock cmpxchg [rbx+8], edx
0x1800072b4  jz      short loc_1800072BF
0x1800072b6  mov     r8d, [rbx+8]
0x1800072ba  cmp     r8d, ecx
0x1800072bd  jnz     short loc_1800072A8
0x1800072bf  lea     edi, [r8-1]
0x1800072c3  test    edi, edi
0x1800072c5  jnz     short loc_180007304
0x1800072c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800072ce  mov     rax, [rcx]
0x1800072d1  mov     rax, [rax+8]
0x1800072d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072da  test    rbx, rbx
0x1800072dd  jz      short loc_1800072F1
0x1800072df  mov     rax, [rbx]
0x1800072e2  lea     edx, [rdi+1]
0x1800072e5  mov     rcx, rbx
0x1800072e8  mov     rax, [rax+18h]
0x1800072ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800072f8  mov     rdx, [rcx]
0x1800072fb  mov     rax, [rdx+10h]
0x1800072ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007304  mov     rbx, [rsp+28h+arg_0]
0x180007309  mov     eax, edi
0x18000730b  add     rsp, 20h
0x18000730f  pop     rdi
0x180007310  retn
```
