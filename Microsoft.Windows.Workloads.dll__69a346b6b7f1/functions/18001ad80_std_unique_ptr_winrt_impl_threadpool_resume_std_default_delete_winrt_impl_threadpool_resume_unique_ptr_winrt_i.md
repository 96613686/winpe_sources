# std::unique_ptr<winrt::impl::threadpool_resume,std::default_delete<winrt::impl::threadpool_resume>>::~unique_ptr<winrt::impl::threadpool_resume,std::default_delete<winrt::impl::threadpool_resume>>(void)

- ea: `0x18001ad80`
- end: `0x18001adb4`
- name: `??1?$unique_ptr@Uthreadpool_resume@impl@winrt@@U?$default_delete@Uthreadpool_resume@impl@winrt@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e750`

## callees

- `0x1800040a0`
- `0x18001ad80`
- `0x18003509c`

## pseudocode

```c
void __fastcall std::unique_ptr<winrt::impl::threadpool_resume>::~unique_ptr<winrt::impl::threadpool_resume>(
        _QWORD *a1)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)*a1;
  if ( *a1 )
  {
    if ( *v1 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(*a1);
    operator delete(v1, 0x18u);
  }
}

```

## disassembly

```asm
0x18001ad80  push    rbx
0x18001ad82  sub     rsp, 20h
0x18001ad86  mov     rbx, [rcx]
0x18001ad89  test    rbx, rbx
0x18001ad8c  jz      short loc_18001ADAE
0x18001ad8e  cmp     qword ptr [rbx], 0
0x18001ad92  jz      short loc_18001AD9C
0x18001ad94  mov     rcx, rbx
0x18001ad97  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ad9c  mov     edx, 18h; unsigned __int64
0x18001ada1  mov     rcx, rbx; void *
0x18001ada4  add     rsp, 20h
0x18001ada8  pop     rbx
0x18001ada9  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001adae  add     rsp, 20h
0x18001adb2  pop     rbx
0x18001adb3  retn
```
