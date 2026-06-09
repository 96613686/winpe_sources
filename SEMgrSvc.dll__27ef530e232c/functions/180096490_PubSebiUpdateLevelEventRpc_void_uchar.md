# PubSebiUpdateLevelEventRpc(void *,uchar)

- ea: `0x180096490`
- end: `0x1800965df`
- name: `?PubSebiUpdateLevelEventRpc@@YAJPEAXE@Z`
- size: `335`
- prototype: `__int64 __fastcall(void *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800904e0`
- `0x180090680`

## callees

- `0x180096404`
- `0x180096490`
- `0x180096758`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009654b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009654b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180096508`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800965ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180096508`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800965ad`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800964d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180096545`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800964d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180096545`
- `RPCRT4!NdrClientCall3` at `0x18009658a`
- `RPCRT4!NdrClientCall3` at `0x18009658a`

## pseudocode

```c
__int64 __fastcall PubSebiUpdateLevelEventRpc(_DWORD *a1, unsigned __int8 a2)
{
  int v2; // esi
  int RpcBindingHandle; // ebx
  signed int v5; // ecx
  __int64 v6; // rbx
  int v7; // eax
  bool v8; // zf
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  void *v13; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  v13 = 0;
  if ( !a1 )
  {
    LOWORD(RpcBindingHandle) = 87;
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  }
  RpcBindingHandle = PubSebiGetRpcBindingHandle(&v13);
  if ( !RpcBindingHandle )
  {
    RtlAcquireSRWLockExclusive(&qword_180132FC8);
    if ( (int)qword_180132FC0 <= 0 )
      goto LABEL_8;
    v5 = 0;
    while ( *(_DWORD **)(qword_180132FB0 + 8LL * v5) != a1 )
    {
      if ( ++v5 >= (int)qword_180132FC0 )
        goto LABEL_8;
    }
    if ( v5 == -1 )
    {
LABEL_8:
      v6 = 0;
    }
    else
    {
      if ( v5 < 0 || v5 >= (int)qword_180132FC0 )
      {
        ATL::_AtlRaiseException(v5, qword_180132FC0);
        JUMPOUT(0x1800965DELL);
      }
      v6 = *(_QWORD *)(qword_180132FB8 + 8LL * v5);
    }
    RtlReleaseSRWLockExclusive(&qword_180132FC8);
    if ( !v6 )
    {
      LOWORD(RpcBindingHandle) = 6;
      return (unsigned __int16)RpcBindingHandle | 0x80070000;
    }
    RtlAcquireSRWLockExclusive(a1);
    a1[2] = GetCurrentThreadId();
    v7 = a1[3];
    if ( (_BYTE)v2 )
    {
      v8 = v7 == 0;
    }
    else
    {
      if ( !v7 )
      {
        RpcBindingHandle = 50;
LABEL_25:
        RtlReleaseSRWLockExclusive(a1);
        a1[2] = 0;
        goto LABEL_26;
      }
      v8 = v7 == 1;
    }
    if ( !v8
      || (RpcBindingHandle = (unsigned int)NdrClientCall3(
                                             (MIDL_STUBLESS_PROXY_INFO *)&CSystemEventBrokerPublisher_ProxyInfo,
                                             1u,
                                             0,
                                             v13,
                                             v2,
                                             v6).Pointer) == 0 )
    {
      v9 = a1[3];
      v10 = v9 - 1;
      v11 = v9 + 1;
      if ( !(_BYTE)v2 )
        v11 = v10;
      RpcBindingHandle = 0;
      a1[3] = v11;
    }
    goto LABEL_25;
  }
LABEL_26:
  if ( RpcBindingHandle > 0 )
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  return (unsigned int)RpcBindingHandle;
}

```

## disassembly

```asm
0x180096490  mov     [rsp+arg_8], rbx
0x180096495  mov     [rsp+arg_10], rsi
0x18009649a  push    rdi
0x18009649b  sub     rsp, 30h
0x18009649f  movzx   esi, dl
0x1800964a2  mov     rdi, rcx
0x1800964a5  mov     [rsp+38h+arg_0], 0
0x1800964ae  test    rcx, rcx
0x1800964b1  jnz     short loc_1800964BB
0x1800964b3  lea     ebx, [rcx+57h]
0x1800964b6  jmp     loc_1800965BE
0x1800964bb  lea     rcx, [rsp+38h+arg_0]; void **
0x1800964c0  call    ?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z; PubSebiGetRpcBindingHandle(void * *)
0x1800964c5  mov     ebx, eax
0x1800964c7  test    eax, eax
0x1800964c9  jnz     loc_1800965BA
0x1800964cf  lea     rcx, qword_180132FC8
0x1800964d6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800964dc  mov     rdx, cs:qword_180132FC0; unsigned int
0x1800964e3  test    edx, edx
0x1800964e5  jle     short loc_1800964FF
0x1800964e7  mov     r8, cs:qword_180132FB0
0x1800964ee  xor     ecx, ecx; unsigned int
0x1800964f0  movsxd  rax, ecx
0x1800964f3  cmp     [r8+rax*8], rdi
0x1800964f7  jz      short loc_18009651D
0x1800964f9  inc     ecx
0x1800964fb  cmp     ecx, edx
0x1800964fd  jl      short loc_1800964F0
0x1800964ff  xor     ebx, ebx
0x180096501  lea     rcx, qword_180132FC8
0x180096508  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18009650e  test    rbx, rbx
0x180096511  jnz     short loc_180096542
0x180096513  mov     ebx, 6
0x180096518  jmp     loc_1800965BE
0x18009651d  cmp     ecx, 0FFFFFFFFh
0x180096520  jz      short loc_1800964FF
0x180096522  test    ecx, ecx
0x180096524  js      loc_1800965D9
0x18009652a  cmp     ecx, edx
0x18009652c  jge     loc_1800965D9
0x180096532  mov     rax, cs:qword_180132FB8
0x180096539  movsxd  rcx, ecx
0x18009653c  mov     rbx, [rax+rcx*8]
0x180096540  jmp     short loc_180096501
0x180096542  mov     rcx, rdi
0x180096545  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18009654b  call    cs:__imp_GetCurrentThreadId
0x180096551  mov     [rdi+8], eax
0x180096554  mov     eax, [rdi+0Ch]
0x180096557  test    sil, sil
0x18009655a  jnz     short loc_18009656A
0x18009655c  test    eax, eax
0x18009655e  jnz     short loc_180096565
0x180096560  lea     ebx, [rax+32h]
0x180096563  jmp     short loc_1800965AA
0x180096565  cmp     eax, 1
0x180096568  jmp     short loc_18009656C
0x18009656a  test    eax, eax
0x18009656c  jnz     short loc_180096597
0x18009656e  mov     r9, [rsp+38h+arg_0]
0x180096573  lea     rcx, ?CSystemEventBrokerPublisher_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18009657a  xor     r8d, r8d; pReturnValue
0x18009657d  mov     [rsp+38h+var_10], rbx
0x180096582  mov     [rsp+38h+var_18], esi
0x180096586  lea     edx, [r8+1]; nProcNum
0x18009658a  call    cs:__imp_NdrClientCall3
0x180096590  mov     rbx, rax
0x180096593  test    eax, eax
0x180096595  jnz     short loc_1800965AA
0x180096597  mov     eax, [rdi+0Ch]
0x18009659a  lea     ecx, [rax-1]
0x18009659d  inc     eax
0x18009659f  test    sil, sil
0x1800965a2  cmovz   eax, ecx
0x1800965a5  xor     ebx, ebx
0x1800965a7  mov     [rdi+0Ch], eax
0x1800965aa  mov     rcx, rdi
0x1800965ad  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800965b3  mov     dword ptr [rdi+8], 0
0x1800965ba  test    ebx, ebx
0x1800965bc  jle     short loc_1800965C7
0x1800965be  movzx   ebx, bx
0x1800965c1  or      ebx, 80070000h
0x1800965c7  mov     rsi, [rsp+38h+arg_10]
0x1800965cc  mov     eax, ebx
0x1800965ce  mov     rbx, [rsp+38h+arg_8]
0x1800965d3  add     rsp, 30h
0x1800965d7  pop     rdi
0x1800965d8  retn
0x1800965d9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
