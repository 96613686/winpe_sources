# ATL::CComObject<sandbox::SandboxFactory>::Release(void)

- ea: `0x140006190`
- end: `0x140006211`
- name: `?Release@?$CComObject@VSandboxFactory@sandbox@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006190`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<sandbox::SandboxFactory>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140006190  mov     [rsp+arg_0], rbx
0x140006195  push    rdi
0x140006196  sub     rsp, 20h
0x14000619a  mov     r8d, [rcx+8]
0x14000619e  mov     rbx, rcx
0x1400061a1  mov     ecx, 7FFFFFFFh
0x1400061a6  jmp     short loc_1400061BA
0x1400061a8  lea     edx, [r8-1]
0x1400061ac  mov     eax, r8d
0x1400061af  lock cmpxchg [rbx+8], edx
0x1400061b4  jz      short loc_1400061BF
0x1400061b6  mov     r8d, [rbx+8]
0x1400061ba  cmp     r8d, ecx
0x1400061bd  jnz     short loc_1400061A8
0x1400061bf  lea     edi, [r8-1]
0x1400061c3  test    edi, edi
0x1400061c5  jnz     short loc_140006204
0x1400061c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400061ce  mov     rax, [rcx]
0x1400061d1  mov     rax, [rax+8]
0x1400061d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061da  test    rbx, rbx
0x1400061dd  jz      short loc_1400061F1
0x1400061df  mov     rax, [rbx]
0x1400061e2  lea     edx, [rdi+1]
0x1400061e5  mov     rcx, rbx
0x1400061e8  mov     rax, [rax+20h]
0x1400061ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400061f8  mov     rdx, [rcx]
0x1400061fb  mov     rax, [rdx+10h]
0x1400061ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006204  mov     rbx, [rsp+28h+arg_0]
0x140006209  mov     eax, edi
0x14000620b  add     rsp, 20h
0x14000620f  pop     rdi
0x140006210  retn
```
