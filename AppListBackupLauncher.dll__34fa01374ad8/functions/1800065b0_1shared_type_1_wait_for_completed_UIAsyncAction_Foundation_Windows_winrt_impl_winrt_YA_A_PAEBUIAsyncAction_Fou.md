# ??1shared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@2@I@Z@QEAA@XZ

- ea: `0x1800065b0`
- end: `0x1800065d3`
- name: `??1shared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@2@I@Z@QEAA@XZ`
- size: `35`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001043b`

## callees

- `0x180002e94`
- `0x1800065b0`

## pseudocode

```c
BOOL __fastcall `winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>'::`2'::shared_type::~shared_type(
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
0x1800065b0  push    rbx
0x1800065b2  sub     rsp, 20h
0x1800065b6  mov     rbx, rcx
0x1800065b9  mov     rcx, [rcx]; hObject
0x1800065bc  test    rcx, rcx
0x1800065bf  jz      short loc_1800065CD
0x1800065c1  call    WINRT_IMPL_CloseHandle
0x1800065c6  mov     qword ptr [rbx], 0
0x1800065cd  add     rsp, 20h
0x1800065d1  pop     rbx
0x1800065d2  retn
```
