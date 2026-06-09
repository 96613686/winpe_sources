# ATL::CComObject<ReceiveTextMessageTask>::Release(void)

- ea: `0x180008040`
- end: `0x1800080c1`
- name: `?Release@?$CComObject@VReceiveTextMessageTask@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008040`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ReceiveTextMessageTask>::Release(volatile signed __int32 *a1)
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
0x180008040  mov     [rsp+arg_0], rbx
0x180008045  push    rdi
0x180008046  sub     rsp, 20h
0x18000804a  mov     r8d, [rcx+8]
0x18000804e  mov     rbx, rcx
0x180008051  mov     ecx, 7FFFFFFFh
0x180008056  jmp     short loc_18000806A
0x180008058  lea     edx, [r8-1]
0x18000805c  mov     eax, r8d
0x18000805f  lock cmpxchg [rbx+8], edx
0x180008064  jz      short loc_18000806F
0x180008066  mov     r8d, [rbx+8]
0x18000806a  cmp     r8d, ecx
0x18000806d  jnz     short loc_180008058
0x18000806f  lea     edi, [r8-1]
0x180008073  test    edi, edi
0x180008075  jnz     short loc_1800080B4
0x180008077  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000807e  mov     rax, [rcx]
0x180008081  mov     rax, [rax+8]
0x180008085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808a  test    rbx, rbx
0x18000808d  jz      short loc_1800080A1
0x18000808f  mov     rax, [rbx]
0x180008092  lea     edx, [rdi+1]
0x180008095  mov     rcx, rbx
0x180008098  mov     rax, [rax+20h]
0x18000809c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800080a8  mov     rdx, [rcx]
0x1800080ab  mov     rax, [rdx+10h]
0x1800080af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b4  mov     rbx, [rsp+28h+arg_0]
0x1800080b9  mov     eax, edi
0x1800080bb  add     rsp, 20h
0x1800080bf  pop     rdi
0x1800080c0  retn
```
