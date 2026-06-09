# CBrokerInstance::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x180004440`
- end: `0x18000449e`
- name: `?OnEnableEvent@CBrokerInstance@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003d14`
- `0x180003da4`
- `0x180004440`

## pseudocode

```c
__int64 __fastcall CBrokerInstance::OnEnableEvent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  __int64 v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  unsigned int v8; // ebp
  __int64 i; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rcx

  v4 = 0;
  v6 = 0;
  do
  {
    if ( (unsigned int)v6 >= *(_DWORD *)a4 )
      break;
    v7 = *(struct _RTL_CRITICAL_SECTION **)(*(_QWORD *)(a4 + 8) + 8 * v6);
    if ( v7 )
      v4 = CQuery::Start(v7);
    v6 = (unsigned int)(v6 + 1);
  }
  while ( !v4 );
  if ( v4 )
  {
    v8 = v6 - 1;
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      v10 = *(struct _RTL_CRITICAL_SECTION **)(*(_QWORD *)(a4 + 8) + 8 * i);
      if ( v10 )
        CQuery::Stop(v10);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004440  push    rbx
0x180004442  push    rbp
0x180004443  push    rsi
0x180004444  push    rdi
0x180004445  sub     rsp, 28h
0x180004449  xor     edi, edi
0x18000444b  mov     rsi, r9
0x18000444e  xor     ebx, ebx
0x180004450  cmp     ebx, [rsi]
0x180004452  jnb     short loc_18000446E
0x180004454  mov     rax, [rsi+8]
0x180004458  mov     rcx, [rax+rbx*8]; this
0x18000445c  test    rcx, rcx
0x18000445f  jz      short loc_180004468
0x180004461  call    ?Start@CQuery@@QEAAJXZ; CQuery::Start(void)
0x180004466  mov     edi, eax
0x180004468  inc     ebx
0x18000446a  test    edi, edi
0x18000446c  jz      short loc_180004450
0x18000446e  test    edi, edi
0x180004470  jz      short loc_180004493
0x180004472  lea     ebp, [rbx-1]
0x180004475  xor     ebx, ebx
0x180004477  test    ebp, ebp
0x180004479  jz      short loc_180004493
0x18000447b  mov     rax, [rsi+8]
0x18000447f  mov     rcx, [rax+rbx*8]; this
0x180004483  test    rcx, rcx
0x180004486  jz      short loc_18000448D
0x180004488  call    ?Stop@CQuery@@QEAAXXZ; CQuery::Stop(void)
0x18000448d  inc     ebx
0x18000448f  cmp     ebx, ebp
0x180004491  jb      short loc_18000447B
0x180004493  mov     eax, edi
0x180004495  add     rsp, 28h
0x180004499  pop     rdi
0x18000449a  pop     rsi
0x18000449b  pop     rbp
0x18000449c  pop     rbx
0x18000449d  retn
```
