# winrt::implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::Release(void)

- ea: `0x1800154cc`
- end: `0x180015569`
- name: `?Release@?$implements@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@U13456@@winrt@@QEAAKXZ`
- size: `157`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180015570`
- `0x180015590`
- `0x1800155b0`
- `0x1800214d0`

## callees

- `0x180002c74`
- `0x1800154cc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001555c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001555c`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  unsigned __int32 v3; // edi
  signed __int64 v4; // rtt
  volatile signed __int32 *v5; // rcx

  v1 = *((_QWORD *)a1 + 1);
  while ( v1 >= 0 )
  {
    v3 = v1 - 1;
    v4 = v1;
    v1 = _InterlockedCompareExchange64(a1 + 1, v1 - 1, v1);
    if ( v4 == v1 )
      goto LABEL_10;
  }
  v5 = (volatile signed __int32 *)(2 * v1);
  v3 = _InterlockedDecrement((volatile signed __int32 *)(2 * v1 + 24));
  if ( !v3 && _InterlockedExchangeAdd(v5 + 7, 0xFFFFFFFF) == 1 && v5 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete((void *)v5);
  }
LABEL_10:
  if ( !v3 )
  {
    *((_QWORD *)a1 + 1) = 1;
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *))(*a1 + 8))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800154cc  mov     [rsp+arg_0], rbx
0x1800154d1  push    rdi
0x1800154d2  sub     rsp, 20h
0x1800154d6  mov     rax, [rcx+8]
0x1800154da  mov     rbx, rcx
0x1800154dd  test    rax, rax
0x1800154e0  js      short loc_1800154F0
0x1800154e2  lea     rdi, [rax-1]
0x1800154e6  lock cmpxchg [rcx+8], rdi
0x1800154ec  jnz     short loc_1800154DD
0x1800154ee  jmp     short loc_18001552B
0x1800154f0  or      edx, 0FFFFFFFFh
0x1800154f3  lea     rcx, [rax+rax]; void *
0x1800154f7  mov     edi, edx
0x1800154f9  lock xadd [rcx+18h], edi
0x1800154fe  sub     edi, 1
0x180015501  jnz     short loc_18001552B
0x180015503  mov     eax, edx
0x180015505  lock xadd [rcx+1Ch], eax
0x18001550a  cmp     eax, 1
0x18001550d  jnz     short loc_18001552B
0x18001550f  test    rcx, rcx
0x180015512  jz      short loc_18001552B
0x180015514  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001551c  sub     edx, eax
0x18001551e  jnz     short loc_180015558
0x180015520  nop
0x180015521  mov     edx, 20h ; ' '; unsigned __int64
0x180015526  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001552b  test    edi, edi
0x18001552d  jnz     short loc_18001554A
0x18001552f  lea     edx, [rdi+1]
0x180015532  mov     [rbx+8], rdx
0x180015536  test    rbx, rbx
0x180015539  jz      short loc_18001554A
0x18001553b  mov     rcx, [rbx]
0x18001553e  mov     rax, [rcx+8]
0x180015542  mov     rcx, rbx
0x180015545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554a  mov     rbx, [rsp+28h+arg_0]
0x18001554f  mov     eax, edi
0x180015551  add     rsp, 20h
0x180015555  pop     rdi
0x180015556  retn
0x180015558  test    edx, edx
0x18001555a  jns     short loc_180015521
0x18001555c  call    cs:__imp_abort
```
