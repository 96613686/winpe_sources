# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(void)

- ea: `0x180018260`
- end: `0x18001844a`
- name: `??1MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ`
- size: `490`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180018e84`
- `0x18001b7a0`
- `0x18002d630`
- `0x18003f16a`
- `0x18003f32c`

## callees

- `0x1800052fc`
- `0x180005374`
- `0x180018260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018443`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018443`

## pseudocode

```c
void __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *this)
{
  volatile signed __int32 *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // eax
  HANDLE v7; // rax
  volatile signed __int32 *v8; // rdi
  int v9; // eax
  HANDLE v10; // rax
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  HANDLE v13; // rax
  volatile signed __int32 *v14; // rdi
  int v15; // eax
  HANDLE v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // eax
  HANDLE v19; // rax
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  HANDLE v22; // rax
  volatile signed __int32 *v23; // rdi
  int v24; // esi
  HANDLE v25; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 9);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        goto LABEL_42;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    v6 = _InterlockedDecrement(v5 + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        goto LABEL_42;
    }
    else
    {
      v7 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
    }
    *((_QWORD *)this + 8) = 0;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v8 )
  {
    v9 = _InterlockedDecrement(v8 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        goto LABEL_42;
    }
    else
    {
      v10 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v10, 0, (LPVOID)v8);
    }
    *((_QWORD *)this + 6) = 0;
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_42;
    }
    else
    {
      v13 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v13, 0, (LPVOID)v11);
    }
    *((_QWORD *)this + 5) = 0;
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v14 )
  {
    v15 = _InterlockedDecrement(v14 + 6);
    if ( v15 )
    {
      if ( v15 < 0 )
        goto LABEL_42;
    }
    else
    {
      v16 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v16, 0, (LPVOID)v14);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v17 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v17 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        goto LABEL_42;
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    }
    *((_QWORD *)this + 3) = 0;
  }
  v20 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v20 )
  {
    v21 = _InterlockedDecrement(v20 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        goto LABEL_42;
    }
    else
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v20);
    }
    *((_QWORD *)this + 1) = 0;
  }
  v23 = *(volatile signed __int32 **)this;
  if ( !*(_QWORD *)this )
    return;
  v24 = _InterlockedDecrement(v23 + 6);
  if ( v24 )
  {
    if ( v24 >= 0 )
      goto LABEL_39;
LABEL_42:
    abort();
  }
  v25 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v25, 0, (LPVOID)v23);
LABEL_39:
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180018260  mov     [rsp+arg_0], rbx
0x180018265  mov     [rsp+arg_8], rsi
0x18001826a  push    rdi
0x18001826b  sub     rsp, 20h
0x18001826f  mov     rdi, [rcx+48h]
0x180018273  or      esi, 0FFFFFFFFh
0x180018276  mov     rbx, rcx
0x180018279  test    rdi, rdi
0x18001827c  jz      short loc_1800182AF
0x18001827e  mov     eax, esi
0x180018280  lock xadd [rdi+18h], eax
0x180018285  sub     eax, 1
0x180018288  jnz     short loc_18001829F
0x18001828a  nop
0x18001828b  call    WINRT_IMPL_GetProcessHeap
0x180018290  mov     rcx, rax; hHeap
0x180018293  mov     r8, rdi; lpMem
0x180018296  xor     edx, edx; dwFlags
0x180018298  call    WINRT_IMPL_HeapFree
0x18001829d  jmp     short loc_1800182A7
0x18001829f  test    eax, eax
0x1800182a1  js      loc_180018443
0x1800182a7  mov     qword ptr [rbx+48h], 0
0x1800182af  mov     rdi, [rbx+40h]
0x1800182b3  test    rdi, rdi
0x1800182b6  jz      short loc_1800182E9
0x1800182b8  mov     eax, esi
0x1800182ba  lock xadd [rdi+18h], eax
0x1800182bf  sub     eax, 1
0x1800182c2  jnz     short loc_1800182D9
0x1800182c4  nop
0x1800182c5  call    WINRT_IMPL_GetProcessHeap
0x1800182ca  mov     rcx, rax; hHeap
0x1800182cd  mov     r8, rdi; lpMem
0x1800182d0  xor     edx, edx; dwFlags
0x1800182d2  call    WINRT_IMPL_HeapFree
0x1800182d7  jmp     short loc_1800182E1
0x1800182d9  test    eax, eax
0x1800182db  js      loc_180018443
0x1800182e1  mov     qword ptr [rbx+40h], 0
0x1800182e9  mov     rdi, [rbx+30h]
0x1800182ed  test    rdi, rdi
0x1800182f0  jz      short loc_180018323
0x1800182f2  mov     eax, esi
0x1800182f4  lock xadd [rdi+18h], eax
0x1800182f9  sub     eax, 1
0x1800182fc  jnz     short loc_180018313
0x1800182fe  nop
0x1800182ff  call    WINRT_IMPL_GetProcessHeap
0x180018304  mov     rcx, rax; hHeap
0x180018307  mov     r8, rdi; lpMem
0x18001830a  xor     edx, edx; dwFlags
0x18001830c  call    WINRT_IMPL_HeapFree
0x180018311  jmp     short loc_18001831B
0x180018313  test    eax, eax
0x180018315  js      loc_180018443
0x18001831b  mov     qword ptr [rbx+30h], 0
0x180018323  mov     rdi, [rbx+28h]
0x180018327  test    rdi, rdi
0x18001832a  jz      short loc_18001835D
0x18001832c  mov     eax, esi
0x18001832e  lock xadd [rdi+18h], eax
0x180018333  sub     eax, 1
0x180018336  jnz     short loc_18001834D
0x180018338  nop
0x180018339  call    WINRT_IMPL_GetProcessHeap
0x18001833e  mov     rcx, rax; hHeap
0x180018341  mov     r8, rdi; lpMem
0x180018344  xor     edx, edx; dwFlags
0x180018346  call    WINRT_IMPL_HeapFree
0x18001834b  jmp     short loc_180018355
0x18001834d  test    eax, eax
0x18001834f  js      loc_180018443
0x180018355  mov     qword ptr [rbx+28h], 0
0x18001835d  mov     rdi, [rbx+20h]
0x180018361  test    rdi, rdi
0x180018364  jz      short loc_180018397
0x180018366  mov     eax, esi
0x180018368  lock xadd [rdi+18h], eax
0x18001836d  sub     eax, 1
0x180018370  jnz     short loc_180018387
0x180018372  nop
0x180018373  call    WINRT_IMPL_GetProcessHeap
0x180018378  mov     rcx, rax; hHeap
0x18001837b  mov     r8, rdi; lpMem
0x18001837e  xor     edx, edx; dwFlags
0x180018380  call    WINRT_IMPL_HeapFree
0x180018385  jmp     short loc_18001838F
0x180018387  test    eax, eax
0x180018389  js      loc_180018443
0x18001838f  mov     qword ptr [rbx+20h], 0
0x180018397  mov     rdi, [rbx+18h]
0x18001839b  test    rdi, rdi
0x18001839e  jz      short loc_1800183CD
0x1800183a0  mov     eax, esi
0x1800183a2  lock xadd [rdi+18h], eax
0x1800183a7  sub     eax, 1
0x1800183aa  jnz     short loc_1800183C1
0x1800183ac  nop
0x1800183ad  call    WINRT_IMPL_GetProcessHeap
0x1800183b2  mov     rcx, rax; hHeap
0x1800183b5  mov     r8, rdi; lpMem
0x1800183b8  xor     edx, edx; dwFlags
0x1800183ba  call    WINRT_IMPL_HeapFree
0x1800183bf  jmp     short loc_1800183C5
0x1800183c1  test    eax, eax
0x1800183c3  js      short loc_180018443
0x1800183c5  mov     qword ptr [rbx+18h], 0
0x1800183cd  mov     rdi, [rbx+8]
0x1800183d1  test    rdi, rdi
0x1800183d4  jz      short loc_180018403
0x1800183d6  mov     eax, esi
0x1800183d8  lock xadd [rdi+18h], eax
0x1800183dd  sub     eax, 1
0x1800183e0  jnz     short loc_1800183F7
0x1800183e2  nop
0x1800183e3  call    WINRT_IMPL_GetProcessHeap
0x1800183e8  mov     rcx, rax; hHeap
0x1800183eb  mov     r8, rdi; lpMem
0x1800183ee  xor     edx, edx; dwFlags
0x1800183f0  call    WINRT_IMPL_HeapFree
0x1800183f5  jmp     short loc_1800183FB
0x1800183f7  test    eax, eax
0x1800183f9  js      short loc_180018443
0x1800183fb  mov     qword ptr [rbx+8], 0
0x180018403  mov     rdi, [rbx]
0x180018406  test    rdi, rdi
0x180018409  jz      short loc_18001842F
0x18001840b  lock xadd [rdi+18h], esi
0x180018410  sub     esi, 1
0x180018413  jnz     short loc_18001843F
0x180018415  nop
0x180018416  call    WINRT_IMPL_GetProcessHeap
0x18001841b  mov     rcx, rax; hHeap
0x18001841e  mov     r8, rdi; lpMem
0x180018421  xor     edx, edx; dwFlags
0x180018423  call    WINRT_IMPL_HeapFree
0x180018428  mov     qword ptr [rbx], 0
0x18001842f  mov     rbx, [rsp+28h+arg_0]
0x180018434  mov     rsi, [rsp+28h+arg_8]
0x180018439  add     rsp, 20h
0x18001843d  pop     rdi
0x18001843e  retn
0x18001843f  test    esi, esi
0x180018441  jns     short loc_180018428
0x180018443  call    cs:__imp_abort
```
