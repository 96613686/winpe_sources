# winrt::implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::Release(void)

- ea: `0x1800148fc`
- end: `0x18001498d`
- name: `?Release@?$implements@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@U13456@@winrt@@QEAAKXZ`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800149a0`
- `0x1800149c0`
- `0x1800149e0`
- `0x1800201d8`

## callees

- `0x180002cc0`
- `0x1800148fc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014986`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014986`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  unsigned __int32 v3; // ebx
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
    (*(void (__fastcall **)(volatile signed __int64 *))(*a1 + 8))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800148fc  mov     [rsp+arg_0], rbx
0x180014901  push    rdi
0x180014902  sub     rsp, 20h
0x180014906  mov     rax, [rcx+8]
0x18001490a  mov     rdi, rcx
0x18001490d  test    rax, rax
0x180014910  js      short loc_180014920
0x180014912  lea     rbx, [rax-1]
0x180014916  lock cmpxchg [rcx+8], rbx
0x18001491c  jnz     short loc_18001490D
0x18001491e  jmp     short loc_18001495B
0x180014920  or      edx, 0FFFFFFFFh
0x180014923  lea     rcx, [rax+rax]; void *
0x180014927  mov     ebx, edx
0x180014929  lock xadd [rcx+18h], ebx
0x18001492e  sub     ebx, 1
0x180014931  jnz     short loc_18001495B
0x180014933  mov     eax, edx
0x180014935  lock xadd [rcx+1Ch], eax
0x18001493a  cmp     eax, 1
0x18001493d  jnz     short loc_18001495B
0x18001493f  test    rcx, rcx
0x180014942  jz      short loc_18001495B
0x180014944  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001494c  sub     edx, eax
0x18001494e  jnz     short loc_180014982
0x180014950  nop
0x180014951  mov     edx, 20h ; ' '; unsigned __int64
0x180014956  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001495b  test    ebx, ebx
0x18001495d  jnz     short loc_180014975
0x18001495f  lea     edx, [rbx+1]
0x180014962  mov     [rdi+8], rdx
0x180014966  mov     rcx, [rdi]
0x180014969  mov     rax, [rcx+8]
0x18001496d  mov     rcx, rdi
0x180014970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014975  mov     eax, ebx
0x180014977  mov     rbx, [rsp+28h+arg_0]
0x18001497c  add     rsp, 20h
0x180014980  pop     rdi
0x180014981  retn
0x180014982  test    edx, edx
0x180014984  jns     short loc_180014951
0x180014986  call    cs:__imp_abort
```
