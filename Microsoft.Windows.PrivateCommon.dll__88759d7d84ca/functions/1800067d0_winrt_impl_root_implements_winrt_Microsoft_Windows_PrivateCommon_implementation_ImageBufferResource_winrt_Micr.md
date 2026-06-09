# winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)

- ea: `0x1800067d0`
- end: `0x180006850`
- name: `?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ`
- size: `128`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005cd0`
- `0x180005d60`
- `0x180005fe0`
- `0x1800062a0`
- `0x180006980`

## callees

- `0x1800067d0`
- `0x180007660`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006849`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006849`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(
        __int64 a1)
{
  signed __int64 v1; // rax
  unsigned int v2; // edx
  signed __int64 v3; // rtt
  volatile signed __int32 *v4; // rcx
  unsigned __int32 v5; // ebx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 < 0 )
  {
LABEL_4:
    v4 = (volatile signed __int32 *)(2 * v1);
    v5 = _InterlockedDecrement((volatile signed __int32 *)(2 * v1 + 24));
    if ( !v5 && _InterlockedExchangeAdd(v4 + 7, 0xFFFFFFFF) == 1 && v4 )
    {
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      operator delete((void *)v4);
    }
    return v5;
  }
  else
  {
    while ( 1 )
    {
      v2 = v1 - 1;
      v3 = v1;
      v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
      if ( v3 == v1 )
        return v2;
      if ( v1 < 0 )
        goto LABEL_4;
    }
  }
}

```

## disassembly

```asm
0x1800067d0  sub     rsp, 28h
0x1800067d4  mov     rax, [rcx+8]
0x1800067d8  test    rax, rax
0x1800067db  js      short loc_1800067F1
0x1800067dd  nop     dword ptr [rax]
0x1800067e0  lea     rdx, [rax-1]
0x1800067e4  lock cmpxchg [rcx+8], rdx
0x1800067ea  jz      short loc_18000683E
0x1800067ec  test    rax, rax
0x1800067ef  jns     short loc_1800067E0
0x1800067f1  mov     edx, 0FFFFFFFFh
0x1800067f6  mov     [rsp+28h+var_8], rbx
0x1800067fb  mov     ebx, edx
0x1800067fd  lea     rcx, [rax+rax]; void *
0x180006801  lock xadd [rcx+18h], ebx
0x180006806  sub     ebx, 1
0x180006809  jnz     short loc_180006832
0x18000680b  mov     eax, edx
0x18000680d  lock xadd [rcx+1Ch], eax
0x180006812  cmp     eax, 1
0x180006815  jnz     short loc_180006832
0x180006817  test    rcx, rcx
0x18000681a  jz      short loc_180006832
0x18000681c  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006824  sub     edx, eax
0x180006826  jnz     short loc_180006845
0x180006828  mov     edx, 20h ; ' '; unsigned __int64
0x18000682d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006832  mov     eax, ebx
0x180006834  mov     rbx, [rsp+28h+var_8]
0x180006839  add     rsp, 28h
0x18000683d  retn
0x18000683e  mov     eax, edx
0x180006840  add     rsp, 28h
0x180006844  retn
0x180006845  test    edx, edx
0x180006847  jns     short loc_180006828
0x180006849  call    cs:__imp_abort
```
