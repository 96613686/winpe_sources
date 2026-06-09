# ATL::CComAggObject<CMidi2BS2UMPTransform>::Release(void)

- ea: `0x180007320`
- end: `0x1800073a1`
- name: `?Release@?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007320`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2BS2UMPTransform>::Release(volatile signed __int32 *a1)
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
0x180007320  mov     [rsp+arg_0], rbx
0x180007325  push    rdi
0x180007326  sub     rsp, 20h
0x18000732a  mov     r8d, [rcx+8]
0x18000732e  mov     rbx, rcx
0x180007331  mov     ecx, 7FFFFFFFh
0x180007336  jmp     short loc_18000734A
0x180007338  lea     edx, [r8-1]
0x18000733c  mov     eax, r8d
0x18000733f  lock cmpxchg [rbx+8], edx
0x180007344  jz      short loc_18000734F
0x180007346  mov     r8d, [rbx+8]
0x18000734a  cmp     r8d, ecx
0x18000734d  jnz     short loc_180007338
0x18000734f  lea     edi, [r8-1]
0x180007353  test    edi, edi
0x180007355  jnz     short loc_180007394
0x180007357  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000735e  mov     rax, [rcx]
0x180007361  mov     rax, [rax+8]
0x180007365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736a  test    rbx, rbx
0x18000736d  jz      short loc_180007381
0x18000736f  mov     rax, [rbx]
0x180007372  lea     edx, [rdi+1]
0x180007375  mov     rcx, rbx
0x180007378  mov     rax, [rax+18h]
0x18000737c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007381  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007388  mov     rdx, [rcx]
0x18000738b  mov     rax, [rdx+10h]
0x18000738f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007394  mov     rbx, [rsp+28h+arg_0]
0x180007399  mov     eax, edi
0x18000739b  add     rsp, 20h
0x18000739f  pop     rdi
0x1800073a0  retn
```
