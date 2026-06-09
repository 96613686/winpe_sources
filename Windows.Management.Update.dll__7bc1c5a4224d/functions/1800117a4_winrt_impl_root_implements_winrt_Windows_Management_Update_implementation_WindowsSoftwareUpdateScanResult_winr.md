# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)

- ea: `0x1800117a4`
- end: `0x180011824`
- name: `??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: `void __fastcall(__int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180011798`
- `0x18001182c`
- `0x1800118d0`
- `0x180011940`
- `0x1800119f0`
- `0x180011a58`
- `0x180011c70`
- `0x180011cb0`
- `0x180011d80`
- `0x180011e40`
- `0x180011eb0`
- `0x180011ef0`
- `0x180011f30`
- `0x180011f80`
- `0x180012000`
- `0x18001e8a0`
- `0x18001e8f0`
- `0x180024bb0`

## callees

- `0x180002cc0`
- `0x1800117a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001181d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001181d`

## pseudocode

```c
void __fastcall winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(
        __int64 a1)
{
  signed __int64 v1; // rax
  signed __int64 v2; // rtt
  volatile signed __int32 *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
    if ( v2 == v1 )
      goto LABEL_10;
  }
  v3 = (volatile signed __int32 *)(2 * v1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(2 * v1 + 24), 0xFFFFFFFF) == 1
    && _InterlockedExchangeAdd(v3 + 7, 0xFFFFFFFF) == 1
    && v3 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      goto LABEL_11;
    operator delete((void *)v3, 0x20u);
  }
LABEL_10:
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
LABEL_11:
    abort();
}

```

## disassembly

```asm
0x1800117a4  push    rbx
0x1800117a6  sub     rsp, 20h
0x1800117aa  mov     rax, [rcx+8]
0x1800117ae  or      ebx, 0FFFFFFFFh
0x1800117b1  test    rax, rax
0x1800117b4  js      short loc_1800117C4
0x1800117b6  lea     rdx, [rax-1]
0x1800117ba  lock cmpxchg [rcx+8], rdx
0x1800117c0  jnz     short loc_1800117AE
0x1800117c2  jmp     short loc_180011805
0x1800117c4  lea     rcx, [rax+rax]; void *
0x1800117c8  mov     eax, ebx
0x1800117ca  lock xadd [rcx+18h], eax
0x1800117cf  cmp     eax, 1
0x1800117d2  jnz     short loc_180011805
0x1800117d4  mov     eax, ebx
0x1800117d6  lock xadd [rcx+1Ch], eax
0x1800117db  cmp     eax, 1
0x1800117de  jnz     short loc_180011805
0x1800117e0  test    rcx, rcx
0x1800117e3  jz      short loc_180011805
0x1800117e5  mov     eax, ebx
0x1800117e7  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800117ef  sub     eax, 1
0x1800117f2  jnz     short loc_1800117F7
0x1800117f4  nop
0x1800117f5  jmp     short loc_1800117FB
0x1800117f7  test    eax, eax
0x1800117f9  js      short loc_18001181D
0x1800117fb  mov     edx, 20h ; ' '; unsigned __int64
0x180011800  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011805  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001180d  sub     ebx, 1
0x180011810  jnz     short loc_180011819
0x180011812  nop
0x180011813  add     rsp, 20h
0x180011817  pop     rbx
0x180011818  retn
0x180011819  test    ebx, ebx
0x18001181b  jns     short loc_180011813
0x18001181d  call    cs:__imp_abort
```
