# TimerBrokerHelper::RemoveAllForApp(ushort const *)

- ea: `0x18007e488`
- end: `0x18007e58b`
- name: `?RemoveAllForApp@TimerBrokerHelper@@QEAAJPEBG@Z`
- size: `259`
- prototype: `__int64 __fastcall(TimerBrokerHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e470`
- `0x18008ee30`

## callees

- `0x18007e488`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e4f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e4f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e4c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e4c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e4ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e4ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e567`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e567`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e575`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e575`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007e544`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007e544`
- `OLEAUT32!__imp_SysFreeString` at `0x18007e556`
- `OLEAUT32!__imp_SysFreeString` at `0x18007e556`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18007e535`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18007e535`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x18007e52b`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x18007e52b`

## pseudocode

```c
__int64 __fastcall TimerBrokerHelper::RemoveAllForApp(TimerBrokerHelper *this, const unsigned __int16 *a2)
{
  _QWORD **v3; // r15
  int v5; // ebp
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  int v11; // eax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  OLECHAR *v15; // rcx
  HANDLE ProcessHeap; // rax

  v3 = (_QWORD **)((char *)this + 24);
  while ( 2 )
  {
    v5 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)this + 5);
    v6 = *v3;
    v7 = 0;
    while ( v6 != v3 )
    {
      v7 = v6;
      v11 = _o__wcsicmp(v6[47], a2);
      v12 = *v6;
      if ( !v11 )
      {
        if ( *(_QWORD **)(v12 + 8) != v6 || (v13 = (_QWORD *)v6[1], (_QWORD *)*v13 != v6) )
          __fastfail(3u);
        *v13 = v12;
        v5 = 1;
        *(_QWORD *)(v12 + 8) = v13;
        break;
      }
      v6 = (_QWORD *)*v6;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
    if ( v5 )
    {
      LOBYTE(v9) = 1;
      LOBYTE(v8) = 1;
      BiPtDisassociateWorkItemEx(v7 + 4, v8, v9);
      BiPtDeleteEvent(v7 + 8);
      v14 = v7[3];
      if ( v14 )
        RtlUnsubscribeWnfNotificationWaitForCompletion(v14);
      v15 = (OLECHAR *)v7[47];
      if ( v15 )
      {
        SysFreeString(v15);
        v7[47] = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
      _InterlockedDecrement((volatile signed __int32 *)this + 4);
      continue;
    }
    break;
  }
  return 0;
}

```

## disassembly

```asm
0x18007e488  mov     [rsp+arg_0], rbx
0x18007e48d  mov     [rsp+arg_8], rbp
0x18007e492  push    rsi
0x18007e493  push    rdi
0x18007e494  push    r12
0x18007e496  push    r14
0x18007e498  push    r15
0x18007e49a  sub     rsp, 20h
0x18007e49e  mov     r12, rdx
0x18007e4a1  lea     r15, [rcx+18h]
0x18007e4a5  mov     rsi, rcx
0x18007e4a8  lea     rcx, [rsi+28h]; SRWLock
0x18007e4ac  xor     ebp, ebp
0x18007e4ae  call    cs:__imp_AcquireSRWLockExclusive
0x18007e4b4  mov     rbx, [r15]
0x18007e4b7  xor     edi, edi
0x18007e4b9  cmp     rbx, r15
0x18007e4bc  jnz     short loc_18007E4E5
0x18007e4be  lea     rcx, [rsi+28h]; SRWLock
0x18007e4c2  call    cs:__imp_ReleaseSRWLockExclusive
0x18007e4c8  test    ebp, ebp
0x18007e4ca  jnz     short loc_18007E521
0x18007e4cc  mov     rbx, [rsp+48h+arg_0]
0x18007e4d1  xor     eax, eax
0x18007e4d3  mov     rbp, [rsp+48h+arg_8]
0x18007e4d8  add     rsp, 20h
0x18007e4dc  pop     r15
0x18007e4de  pop     r14
0x18007e4e0  pop     r12
0x18007e4e2  pop     rdi
0x18007e4e3  pop     rsi
0x18007e4e4  retn
0x18007e4e5  mov     rcx, [rbx+178h]
0x18007e4ec  mov     rdx, r12
0x18007e4ef  mov     rdi, rbx
0x18007e4f2  call    cs:__imp__o__wcsicmp
0x18007e4f8  mov     rcx, [rbx]
0x18007e4fb  test    eax, eax
0x18007e4fd  jz      short loc_18007E504
0x18007e4ff  mov     rbx, rcx
0x18007e502  jmp     short loc_18007E4B9
0x18007e504  cmp     [rcx+8], rbx
0x18007e508  jnz     short loc_18007E584
0x18007e50a  mov     rax, [rbx+8]
0x18007e50e  cmp     [rax], rbx
0x18007e511  jnz     short loc_18007E584
0x18007e513  mov     [rax], rcx
0x18007e516  mov     ebp, 1
0x18007e51b  mov     [rcx+8], rax
0x18007e51f  jmp     short loc_18007E4BE
0x18007e521  mov     r8b, 1
0x18007e524  lea     rcx, [rdi+20h]
0x18007e528  mov     dl, r8b
0x18007e52b  call    cs:__imp_BiPtDisassociateWorkItemEx
0x18007e531  lea     rcx, [rdi+40h]
0x18007e535  call    cs:__imp_BiPtDeleteEvent
0x18007e53b  mov     rcx, [rdi+18h]
0x18007e53f  test    rcx, rcx
0x18007e542  jz      short loc_18007E54A
0x18007e544  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18007e54a  mov     rcx, [rdi+178h]; bstrString
0x18007e551  test    rcx, rcx
0x18007e554  jz      short loc_18007E567
0x18007e556  call    cs:__imp_SysFreeString
0x18007e55c  mov     qword ptr [rdi+178h], 0
0x18007e567  call    cs:__imp_GetProcessHeap
0x18007e56d  mov     r8, rdi; lpMem
0x18007e570  xor     edx, edx; dwFlags
0x18007e572  mov     rcx, rax; hHeap
0x18007e575  call    cs:__imp_HeapFree
0x18007e57b  lock dec dword ptr [rsi+10h]
0x18007e57f  jmp     loc_18007E4A8
0x18007e584  mov     ecx, 3
0x18007e589  int     29h; Win8: RtlFailFast(ecx)
```
