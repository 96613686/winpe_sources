# ??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ

- ea: `0x180007ea0`
- end: `0x180007ec3`
- name: `??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ`
- size: `35`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e0ac`

## callees

- `0x180007ea0`
- `0x1800162bc`

## pseudocode

```c
BOOL __fastcall `winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>>'::`2'::shared_type::~shared_type(
        void **a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = WINRT_IMPL_CloseHandle(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007ea0  push    rbx
0x180007ea2  sub     rsp, 20h
0x180007ea6  mov     rbx, rcx
0x180007ea9  mov     rcx, [rcx]; hObject
0x180007eac  test    rcx, rcx
0x180007eaf  jz      short loc_180007EBD
0x180007eb1  call    WINRT_IMPL_CloseHandle
0x180007eb6  mov     qword ptr [rbx], 0
0x180007ebd  add     rsp, 20h
0x180007ec1  pop     rbx
0x180007ec2  retn
```
