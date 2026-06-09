# VcommsCheck::~VcommsCheck(void)

- ea: `0x180017730`
- end: `0x1800177f3`
- name: `??1VcommsCheck@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(VcommsCheck *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017730`
- `0x1800838f0`
- `0x1800d7a60`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180017758`
- `KERNEL32!TlsGetValue` at `0x180017758`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800177ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800177e1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800177ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800177e1`
- `WS2_32!freeaddrinfo` at `0x18001776c`
- `WS2_32!freeaddrinfo` at `0x18001776c`
- `WS2_32!WSACleanup` at `0x18001774b`
- `WS2_32!WSACleanup` at `0x18001774b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VcommsCheck::~VcommsCheck(PADDRINFOA *this)
{
  VthreadContext *Value; // rax
  int *v3; // rcx
  int *v4; // rcx

  WSACleanup();
  Value = (VthreadContext *)TlsGetValue(dwTlsIndex);
  VthreadContext::release(Value);
  freeaddrinfo(this[2]);
  v3 = (int *)&this[1][-1].ai_addr + 1;
  if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 && v3 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v3);
    else
      free(v3);
  }
  v4 = (int *)&(*this)[-1].ai_addr + 1;
  if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 && v4 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v4);
    else
      free(v4);
  }
}

```

## disassembly

```asm
0x180017730  mov     [rsp+arg_0], rcx
0x180017735  push    rsi
0x180017736  sub     rsp, 30h
0x18001773a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180017743  mov     [rsp+38h+arg_10], rbx
0x180017748  mov     rbx, rcx
0x18001774b  call    cs:WSACleanup
0x180017751  nop
0x180017752  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180017758  call    cs:TlsGetValue
0x18001775e  nop
0x18001775f  mov     rcx, rax; this
0x180017762  call    ?release@VthreadContext@@QEAAXXZ; VthreadContext::release(void)
0x180017767  nop
0x180017768  mov     rcx, [rbx+10h]; pAddrInfo
0x18001776c  call    cs:freeaddrinfo
0x180017772  nop
0x180017773  lea     rax, [rbx+8]
0x180017777  mov     [rsp+38h+arg_8], rax
0x18001777c  mov     rcx, [rax]
0x18001777f  sub     rcx, 0Ch; void *
0x180017783  or      eax, 0FFFFFFFFh
0x180017786  lock xadd [rcx], eax
0x18001778a  lea     rsi, dword_1802AFD50
0x180017791  cmp     eax, 1
0x180017794  jnz     short loc_1800177B3
0x180017796  cmp     rcx, rsi
0x180017799  jz      short loc_1800177B3
0x18001779b  cmp     cs:dword_1802B0018, 0
0x1800177a2  jz      short loc_1800177AC
0x1800177a4  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800177a9  nop
0x1800177aa  jmp     short loc_1800177B3
0x1800177ac  call    cs:free
0x1800177b2  nop
0x1800177b3  mov     [rsp+38h+arg_0], rbx
0x1800177b8  mov     rcx, [rbx]
0x1800177bb  sub     rcx, 0Ch; void *
0x1800177bf  or      eax, 0FFFFFFFFh
0x1800177c2  lock xadd [rcx], eax
0x1800177c6  cmp     eax, 1
0x1800177c9  jnz     short loc_1800177E8
0x1800177cb  cmp     rcx, rsi
0x1800177ce  jz      short loc_1800177E8
0x1800177d0  cmp     cs:dword_1802B0018, 0
0x1800177d7  jz      short loc_1800177E1
0x1800177d9  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800177de  nop
0x1800177df  jmp     short loc_1800177E8
0x1800177e1  call    cs:free
0x1800177e7  nop
0x1800177e8  mov     rbx, [rsp+38h+arg_10]
0x1800177ed  add     rsp, 30h
0x1800177f1  pop     rsi
0x1800177f2  retn
```
