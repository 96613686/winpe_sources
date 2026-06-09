# _Broker::BrokerBase::CreateBrokeredEventEA_::_1_::catch$3

- ea: `0x18001d7a3`
- end: `0x18001d827`
- name: `_Broker::BrokerBase::CreateBrokeredEventEA_::_1_::catch$3`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e9f4`
- `0x1800165da`
- `0x18001d7a3`
- `0x18001e010`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18001d7d3`
- `ntdll!NtDeleteWnfStateName` at `0x18001d7d3`

## pseudocode

```c
void __fastcall __noreturn Broker::BrokerBase::CreateBrokeredEventEA_::_1_::catch_3(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rbx

  if ( *(_DWORD *)(a2 + 416) || *(_DWORD *)(a2 + 420) )
  {
    NtDeleteWnfStateName(a2 + 416);
    v3 = *(_QWORD **)(a2 + 160);
    v3[2] = 0;
  }
  else
  {
    v3 = *(_QWORD **)(a2 + 160);
  }
  if ( *(_BYTE *)(a2 + 96) )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)(a2 + 224) + 128LL))(
      *(unsigned int *)(a2 + 152),
      *(_QWORD *)(*(_QWORD *)(a2 + 224) + 8LL),
      v3,
      *(_QWORD *)(a2 + 104));
  if ( v3 )
    BciHeapFree(v3);
  throw;
}

```

## disassembly

```asm
0x18001d7a3  mov     [rsp+arg_8], rdx
0x18001d7a8  push    rbx
0x18001d7a9  push    rbp
0x18001d7aa  sub     rsp, 68h
0x18001d7ae  mov     rbp, rdx
0x18001d7b1  cmp     dword ptr [rbp+1A0h], 0
0x18001d7b8  jnz     short loc_18001D7CC
0x18001d7ba  cmp     dword ptr [rbp+1A4h], 0
0x18001d7c1  jnz     short loc_18001D7CC
0x18001d7c3  mov     rbx, [rbp+0A0h]
0x18001d7ca  jmp     short loc_18001D7E6
0x18001d7cc  lea     rcx, [rbp+1A0h]
0x18001d7d3  call    cs:__imp_NtDeleteWnfStateName
0x18001d7d9  mov     rbx, [rbp+0A0h]
0x18001d7e0  xor     eax, eax
0x18001d7e2  mov     [rbx+10h], rax
0x18001d7e6  cmp     byte ptr [rbp+60h], 0
0x18001d7ea  jz      short loc_18001D810
0x18001d7ec  mov     rdx, [rbp+0E0h]
0x18001d7f3  mov     rax, [rdx+80h]
0x18001d7fa  mov     r9, [rbp+68h]
0x18001d7fe  mov     r8, rbx
0x18001d801  mov     rdx, [rdx+8]
0x18001d805  mov     ecx, [rbp+98h]
0x18001d80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d810  test    rbx, rbx
0x18001d813  jz      short loc_18001D81D
0x18001d815  mov     rcx, rbx; void *
0x18001d818  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x18001d81d  xor     edx, edx; pThrowInfo
0x18001d81f  xor     ecx, ecx; pExceptionObject
0x18001d821  call    _CxxThrowException_0
```
