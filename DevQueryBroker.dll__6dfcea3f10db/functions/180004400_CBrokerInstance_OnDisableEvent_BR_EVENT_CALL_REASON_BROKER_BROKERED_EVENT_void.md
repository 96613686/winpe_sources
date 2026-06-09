# CBrokerInstance::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x180004400`
- end: `0x180004439`
- name: `?OnDisableEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003da4`
- `0x180004400`

## pseudocode

```c
__int64 __fastcall CBrokerInstance::OnDisableEvent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rcx

  for ( i = 0; (unsigned int)i < *(_DWORD *)a4; i = (unsigned int)(i + 1) )
  {
    v6 = *(struct _RTL_CRITICAL_SECTION **)(*(_QWORD *)(a4 + 8) + 8 * i);
    if ( v6 )
      CQuery::Stop(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180004400  mov     [rsp+arg_0], rbx
0x180004405  push    rdi
0x180004406  sub     rsp, 20h
0x18000440a  xor     ebx, ebx
0x18000440c  mov     rdi, r9
0x18000440f  cmp     [r9], ebx
0x180004412  jbe     short loc_18000442C
0x180004414  mov     rax, [rdi+8]
0x180004418  mov     rcx, [rax+rbx*8]; this
0x18000441c  test    rcx, rcx
0x18000441f  jz      short loc_180004426
0x180004421  call    ?Stop@CQuery@@QEAAXXZ; CQuery::Stop(void)
0x180004426  inc     ebx
0x180004428  cmp     ebx, [rdi]
0x18000442a  jb      short loc_180004414
0x18000442c  mov     rbx, [rsp+28h+arg_0]
0x180004431  xor     eax, eax
0x180004433  add     rsp, 20h
0x180004437  pop     rdi
0x180004438  retn
```
