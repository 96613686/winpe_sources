# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x180010ec0`
- end: `0x180010ef4`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002fd0`
- `0x180010b28`
- `0x180010ec0`

## pseudocode

```c
void *__fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`scalar deleting destructor'(
        void *a1,
        void *a2)
{
  char v2; // bl

  v2 = (char)a2;
  `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::~CompletionDelegate(
    (__int64)a1,
    a2);
  if ( (v2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010ec0  mov     [rsp+arg_0], rbx
0x180010ec5  push    rdi
0x180010ec6  sub     rsp, 20h
0x180010eca  mov     ebx, edx
0x180010ecc  mov     rdi, rcx
0x180010ecf  call    ??1CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAA@XZ; `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::~CompletionDelegate(void)
0x180010ed4  test    bl, 1
0x180010ed7  jz      short loc_180010EE6
0x180010ed9  mov     edx, 40h ; '@'; unsigned __int64
0x180010ede  mov     rcx, rdi; void *
0x180010ee1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010ee6  mov     rbx, [rsp+28h+arg_0]
0x180010eeb  mov     rax, rdi
0x180010eee  add     rsp, 20h
0x180010ef2  pop     rdi
0x180010ef3  retn
```
