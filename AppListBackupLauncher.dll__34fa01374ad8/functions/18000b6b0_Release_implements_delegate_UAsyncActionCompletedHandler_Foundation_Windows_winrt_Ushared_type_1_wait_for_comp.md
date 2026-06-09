# ?Release@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x18000b6b0`
- end: `0x18000b71d`
- name: `?Release@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002738`
- `0x180002e94`
- `0x18000b6b0`
- `0x18000eb24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000b716`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000b716`

## pseudocode

```c
__int64 __fastcall _Release___implements_delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__UEAAIXZ(
        _QWORD *a1)
{
  unsigned int v2; // edi
  void *v3; // rcx

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 1));
  if ( !v2 && a1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    v3 = (void *)a1[2];
    if ( v3 )
    {
      WINRT_IMPL_CloseHandle(v3);
      a1[2] = 0;
    }
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b6b0  mov     [rsp+arg_0], rbx
0x18000b6b5  push    rdi
0x18000b6b6  sub     rsp, 20h
0x18000b6ba  mov     rbx, rcx
0x18000b6bd  add     rcx, 8; this
0x18000b6c1  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x18000b6c6  mov     edi, eax
0x18000b6c8  test    eax, eax
0x18000b6ca  jnz     short loc_18000B705
0x18000b6cc  test    rbx, rbx
0x18000b6cf  jz      short loc_18000B705
0x18000b6d1  or      edx, 0FFFFFFFFh
0x18000b6d4  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000b6dc  sub     edx, 1
0x18000b6df  jnz     short loc_18000B712
0x18000b6e1  nop
0x18000b6e2  mov     rcx, [rbx+10h]; hObject
0x18000b6e6  test    rcx, rcx
0x18000b6e9  jz      short loc_18000B6F8
0x18000b6eb  call    WINRT_IMPL_CloseHandle
0x18000b6f0  mov     qword ptr [rbx+10h], 0
0x18000b6f8  mov     edx, 20h ; ' '; unsigned __int64
0x18000b6fd  mov     rcx, rbx; void *
0x18000b700  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b705  mov     rbx, [rsp+28h+arg_0]
0x18000b70a  mov     eax, edi
0x18000b70c  add     rsp, 20h
0x18000b710  pop     rdi
0x18000b711  retn
0x18000b712  test    edx, edx
0x18000b714  jns     short loc_18000B6E2
0x18000b716  call    cs:__imp_abort
```
