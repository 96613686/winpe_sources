# CNetworkItemFactory_CreateInstance(IUnknown * *)

- ea: `0x18000312c`
- end: `0x1800031ed`
- name: `?CNetworkItemFactory_CreateInstance@@YAJPEAPEAUIUnknown@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007150`

## callees

- `0x180002db0`
- `0x18000312c`
- `0x1800070c8`
- `0x18000a7a7`
- `0x18000b010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800031da`
- `KERNEL32!LeaveCriticalSection` at `0x1800031da`
- `KERNEL32!EnterCriticalSection` at `0x180003147`
- `KERNEL32!EnterCriticalSection` at `0x180003147`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory_CreateInstance(struct IUnknown **a1)
{
  CNetworkItemFactory *v2; // rax
  CNetworkItemFactory *v3; // rbx
  __int64 (__fastcall **v4)(CNetworkItemFactory *, GUID *, struct IUnknown **); // rcx
  unsigned int v5; // edi

  *a1 = 0;
  EnterCriticalSection(&g_lockDll);
  if ( g_pFactory )
  {
    v5 = (**(__int64 (__fastcall ***)(struct CNetworkItemFactory *, GUID *, struct IUnknown **))g_pFactory)(
           g_pFactory,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
  }
  else
  {
    v2 = (CNetworkItemFactory *)operator new(0x98u);
    v3 = v2;
    if ( v2 )
    {
      memset_0(v2, 0, 0x98u);
      CNetworkItemFactory::CNetworkItemFactory(v3);
      v4 = *(__int64 (__fastcall ***)(CNetworkItemFactory *, GUID *, struct IUnknown **))v3;
      g_pFactory = v3;
      v5 = (*v4)(v3, &GUID_00000000_0000_0000_c000_000000000046, a1);
      (*(void (__fastcall **)(CNetworkItemFactory *))(*(_QWORD *)v3 + 16LL))(v3);
    }
    else
    {
      v5 = -2147024882;
    }
  }
  LeaveCriticalSection(&g_lockDll);
  return v5;
}

```

## disassembly

```asm
0x18000312c  mov     [rsp+arg_0], rbx
0x180003131  push    rdi
0x180003132  sub     rsp, 20h
0x180003136  mov     rdi, rcx
0x180003139  mov     qword ptr [rcx], 0
0x180003140  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003147  call    cs:__imp_EnterCriticalSection
0x18000314d  mov     rcx, cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA; CNetworkItemFactory * g_pFactory
0x180003154  test    rcx, rcx
0x180003157  jnz     short loc_1800031BC
0x180003159  mov     ecx, 98h; unsigned __int64
0x18000315e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003163  mov     rbx, rax
0x180003166  test    rax, rax
0x180003169  jz      short loc_1800031B5
0x18000316b  xor     edx, edx; Val
0x18000316d  mov     r8d, 98h; Size
0x180003173  mov     rcx, rax; void *
0x180003176  call    memset_0
0x18000317b  mov     rcx, rbx; this
0x18000317e  call    ??0CNetworkItemFactory@@QEAA@XZ; CNetworkItemFactory::CNetworkItemFactory(void)
0x180003183  mov     rcx, [rbx]
0x180003186  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000318d  mov     r8, rdi
0x180003190  mov     cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA, rbx; CNetworkItemFactory * g_pFactory
0x180003197  mov     rax, [rcx]
0x18000319a  mov     rcx, rbx
0x18000319d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a2  mov     rcx, [rbx]
0x1800031a5  mov     edi, eax
0x1800031a7  mov     rax, [rcx+10h]
0x1800031ab  mov     rcx, rbx
0x1800031ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b3  jmp     short loc_1800031D3
0x1800031b5  mov     edi, 8007000Eh
0x1800031ba  jmp     short loc_1800031D3
0x1800031bc  mov     rax, [rcx]
0x1800031bf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800031c6  mov     r8, rdi
0x1800031c9  mov     rax, [rax]
0x1800031cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d1  mov     edi, eax
0x1800031d3  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800031da  call    cs:__imp_LeaveCriticalSection
0x1800031e0  mov     rbx, [rsp+28h+arg_0]
0x1800031e5  mov     eax, edi
0x1800031e7  add     rsp, 20h
0x1800031eb  pop     rdi
0x1800031ec  retn
```
