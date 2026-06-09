# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)

- ea: `0x18001234c`
- end: `0x1800123de`
- name: `??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ`
- size: `146`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012340`
- `0x1800123e4`
- `0x180012490`
- `0x180012504`
- `0x1800125c0`
- `0x180012628`
- `0x180012860`
- `0x1800128a0`
- `0x180012970`
- `0x180012a30`
- `0x180012aa0`
- `0x180012ae0`
- `0x180012b20`
- `0x180012b70`
- `0x180012bf0`
- `0x18001fae0`
- `0x18001fb30`
- `0x180025f80`

## callees

- `0x180002c74`
- `0x18001234c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800123c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800123d1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800123c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800123d1`

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
      abort();
    operator delete((void *)v3);
  }
LABEL_10:
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
}

```

## disassembly

```asm
0x18001234c  push    rbx
0x18001234e  sub     rsp, 20h
0x180012352  mov     rax, [rcx+8]
0x180012356  or      ebx, 0FFFFFFFFh
0x180012359  test    rax, rax
0x18001235c  js      short loc_18001236C
0x18001235e  lea     rdx, [rax-1]
0x180012362  lock cmpxchg [rcx+8], rdx
0x180012368  jnz     short loc_180012356
0x18001236a  jmp     short loc_1800123A7
0x18001236c  lea     rcx, [rax+rax]; void *
0x180012370  mov     eax, ebx
0x180012372  lock xadd [rcx+18h], eax
0x180012377  cmp     eax, 1
0x18001237a  jnz     short loc_1800123A7
0x18001237c  mov     eax, ebx
0x18001237e  lock xadd [rcx+1Ch], eax
0x180012383  cmp     eax, 1
0x180012386  jnz     short loc_1800123A7
0x180012388  test    rcx, rcx
0x18001238b  jz      short loc_1800123A7
0x18001238d  mov     eax, ebx
0x18001238f  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180012397  sub     eax, 1
0x18001239a  jnz     short loc_1800123BC
0x18001239c  nop
0x18001239d  mov     edx, 20h ; ' '; unsigned __int64
0x1800123a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800123a7  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800123af  sub     ebx, 1
0x1800123b2  jnz     short loc_1800123CD
0x1800123b4  nop
0x1800123b5  add     rsp, 20h
0x1800123b9  pop     rbx
0x1800123ba  retn
0x1800123bc  test    eax, eax
0x1800123be  jns     short loc_18001239D
0x1800123c0  call    cs:__imp_abort
0x1800123cd  test    ebx, ebx
0x1800123cf  jns     short loc_1800123B5
0x1800123d1  call    cs:__imp_abort
```
