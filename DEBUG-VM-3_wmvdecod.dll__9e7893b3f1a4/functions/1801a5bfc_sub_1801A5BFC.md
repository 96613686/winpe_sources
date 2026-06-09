# sub_1801A5BFC

- ea: `0x1801a5bfc`
- end: `0x1801a5de1`
- name: `sub_1801A5BFC`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801a49f0`

## callees

- `0x180099e80`
- `0x180099e8c`
- `0x180099ee0`
- `0x1801a5bfc`
- `0x1801b52a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a5d1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a5d1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801a5cd3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801a5cd3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c5e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5cb4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c5e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5cb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a5da8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a5da8`

## pseudocode

```c
__int64 __fastcall sub_1801A5BFC(__int64 a1, int a2)
{
  LPCRITICAL_SECTION *v4; // rdi
  __int64 v5; // rax
  __int64 *v6; // rsi
  __int64 v7; // rax
  HANDLE EventW; // rax
  int i; // edi
  void *v10; // rax

  if ( a2 > 64 )
    return 4294967282LL;
  v4 = (LPCRITICAL_SECTION *)(a1 + 1864);
  *(_DWORD *)(a1 + 15448) = a2;
  *(_DWORD *)(a1 + 1872) = 0;
  if ( a1 != -1864 )
  {
    v5 = o_malloc(40);
    if ( v5 )
    {
      *(_OWORD *)v5 = 0;
      *(_OWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 32) = 0;
      *v4 = (LPCRITICAL_SECTION)v5;
      InitializeCriticalSection((LPCRITICAL_SECTION)v5);
    }
    else
    {
      *v4 = 0;
    }
  }
  if ( !*v4 )
    return 4294967294LL;
  _InterlockedExchange((volatile __int32 *)(a1 + 5940), 0);
  if ( !*v4 )
    return 4294967294LL;
  v6 = (__int64 *)(a1 + 5920);
  if ( a1 != -5920 )
  {
    v7 = o_malloc(40);
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      *(_OWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 32) = 0;
      *v6 = v7;
      InitializeCriticalSection((LPCRITICAL_SECTION)v7);
    }
    else
    {
      *v6 = 0;
    }
  }
  if ( !*v6 )
  {
    if ( *v4 )
    {
      DeleteCriticalSection(*v4);
      o_free(*v4);
      *v4 = 0;
    }
    return 4294967294LL;
  }
  *(_DWORD *)(a1 + 1848) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 1856) = EventW;
  if ( !EventW )
    return 4294967294LL;
  for ( i = 0; i < *(_DWORD *)(a1 + 15448); ++i )
  {
    v10 = (void *)sub_1801B52A8(a1 + 8, 262208);
    *(_QWORD *)(a1 + 8LL * i + 2136) = v10;
    if ( !v10 )
      return 4294967294LL;
    memset(v10, 0, 0x40040u);
    **(_QWORD **)(a1 + 8LL * i + 2136) = a1;
    *(_DWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 8LL) = i;
    *(_QWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 16LL) = CreateThread(
                                                             0,
                                                             0,
                                                             sub_18005CC80,
                                                             *(LPVOID *)(a1 + 8LL * i + 2136),
                                                             4u,
                                                             0);
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 16LL) )
      return 4294967294LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1801a5bfc  mov     [rsp+arg_0], rbx
0x1801a5c01  mov     [rsp+arg_8], rsi
0x1801a5c06  push    rdi
0x1801a5c07  sub     rsp, 30h
0x1801a5c0b  mov     rbx, rcx
0x1801a5c0e  cmp     edx, 40h ; '@'
0x1801a5c11  jle     short loc_1801A5C1D
0x1801a5c13  mov     eax, 0FFFFFFF2h
0x1801a5c18  jmp     loc_1801A5CF3
0x1801a5c1d  lea     rdi, [rcx+748h]
0x1801a5c24  mov     [rcx+3C58h], edx
0x1801a5c2a  mov     dword ptr [rcx+750h], 0
0x1801a5c34  test    rdi, rdi
0x1801a5c37  jz      short loc_1801A5C6F
0x1801a5c39  mov     ecx, 28h ; '('
0x1801a5c3e  call    _o_malloc
0x1801a5c43  test    rax, rax
0x1801a5c46  jz      short loc_1801A5C6C
0x1801a5c48  xorps   xmm0, xmm0
0x1801a5c4b  xor     ecx, ecx
0x1801a5c4d  movups  xmmword ptr [rax], xmm0
0x1801a5c50  movups  xmmword ptr [rax+10h], xmm0
0x1801a5c54  mov     [rax+20h], rcx
0x1801a5c58  mov     rcx, rax; lpCriticalSection
0x1801a5c5b  mov     [rdi], rax
0x1801a5c5e  call    cs:InitializeCriticalSection
0x1801a5c65  nop     dword ptr [rax+rax+00h]
0x1801a5c6a  jmp     short loc_1801A5C6F
0x1801a5c6c  mov     [rdi], rax
0x1801a5c6f  cmp     qword ptr [rdi], 0
0x1801a5c73  jz      short loc_1801A5CEE
0x1801a5c75  xor     eax, eax
0x1801a5c77  xchg    eax, [rbx+1734h]
0x1801a5c7d  cmp     qword ptr [rdi], 0
0x1801a5c81  jz      short loc_1801A5CEE
0x1801a5c83  lea     rsi, [rbx+1720h]
0x1801a5c8a  test    rsi, rsi
0x1801a5c8d  jz      short loc_1801A5CC5
0x1801a5c8f  mov     ecx, 28h ; '('
0x1801a5c94  call    _o_malloc
0x1801a5c99  test    rax, rax
0x1801a5c9c  jz      short loc_1801A5CC2
0x1801a5c9e  xorps   xmm0, xmm0
0x1801a5ca1  xor     ecx, ecx
0x1801a5ca3  movups  xmmword ptr [rax], xmm0
0x1801a5ca6  movups  xmmword ptr [rax+10h], xmm0
0x1801a5caa  mov     [rax+20h], rcx
0x1801a5cae  mov     rcx, rax; lpCriticalSection
0x1801a5cb1  mov     [rsi], rax
0x1801a5cb4  call    cs:InitializeCriticalSection
0x1801a5cbb  nop     dword ptr [rax+rax+00h]
0x1801a5cc0  jmp     short loc_1801A5CC5
0x1801a5cc2  mov     [rsi], rax
0x1801a5cc5  cmp     qword ptr [rsi], 0
0x1801a5cc9  jnz     short loc_1801A5D04
0x1801a5ccb  mov     rcx, [rdi]; lpCriticalSection
0x1801a5cce  test    rcx, rcx
0x1801a5cd1  jz      short loc_1801A5CEE
0x1801a5cd3  call    cs:DeleteCriticalSection
0x1801a5cda  nop     dword ptr [rax+rax+00h]
0x1801a5cdf  mov     rcx, [rdi]
0x1801a5ce2  call    _o_free
0x1801a5ce7  mov     qword ptr [rdi], 0
0x1801a5cee  mov     eax, 0FFFFFFFEh
0x1801a5cf3  mov     rbx, [rsp+38h+arg_0]
0x1801a5cf8  mov     rsi, [rsp+38h+arg_8]
0x1801a5cfd  add     rsp, 30h
0x1801a5d01  pop     rdi
0x1801a5d02  retn
0x1801a5d04  xor     r9d, r9d; lpName
0x1801a5d07  mov     dword ptr [rbx+738h], 0
0x1801a5d11  xor     r8d, r8d; bInitialState
0x1801a5d14  xor     ecx, ecx; lpEventAttributes
0x1801a5d16  lea     edx, [r9+1]; bManualReset
0x1801a5d1a  call    cs:CreateEventW
0x1801a5d21  nop     dword ptr [rax+rax+00h]
0x1801a5d26  mov     [rbx+740h], rax
0x1801a5d2d  test    rax, rax
0x1801a5d30  jz      short loc_1801A5CEE
0x1801a5d32  xor     edi, edi
0x1801a5d34  cmp     edi, [rbx+3C58h]
0x1801a5d3a  jge     loc_1801A5DDA
0x1801a5d40  lea     rcx, [rbx+8]
0x1801a5d44  mov     edx, 40040h
0x1801a5d49  call    sub_1801B52A8
0x1801a5d4e  movsxd  rsi, edi
0x1801a5d51  mov     [rbx+rsi*8+858h], rax
0x1801a5d59  test    rax, rax
0x1801a5d5c  jz      short loc_1801A5CEE
0x1801a5d5e  xor     edx, edx; Val
0x1801a5d60  mov     r8d, 40040h; Size
0x1801a5d66  mov     rcx, rax; void *
0x1801a5d69  call    memset
0x1801a5d6e  mov     rax, [rbx+rsi*8+858h]
0x1801a5d76  lea     r8, sub_18005CC80; lpStartAddress
0x1801a5d7d  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1801a5d86  xor     edx, edx; dwStackSize
0x1801a5d88  xor     ecx, ecx; lpThreadAttributes
0x1801a5d8a  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801a5d92  mov     [rax], rbx
0x1801a5d95  mov     rax, [rbx+rsi*8+858h]
0x1801a5d9d  mov     [rax+8], edi
0x1801a5da0  mov     r9, [rbx+rsi*8+858h]; lpParameter
0x1801a5da8  call    cs:CreateThread
0x1801a5daf  nop     dword ptr [rax+rax+00h]
0x1801a5db4  mov     rcx, [rbx+rsi*8+858h]
0x1801a5dbc  mov     [rcx+10h], rax
0x1801a5dc0  mov     rax, [rbx+rsi*8+858h]
0x1801a5dc8  cmp     qword ptr [rax+10h], 0
0x1801a5dcd  jz      loc_1801A5CEE
0x1801a5dd3  inc     edi
0x1801a5dd5  jmp     loc_1801A5D34
0x1801a5dda  xor     eax, eax
0x1801a5ddc  jmp     loc_1801A5CF3
```
