# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180014b34`
- end: `0x180014b84`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800143b0`

## callees

- `0x1800148b0`
- `0x1800149f0`
- `0x180014b34`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 Shared; // rax
  __int64 v3; // rdi
  __int64 Local; // rax

  v1 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(this);
    v3 = Shared;
    if ( Shared )
    {
      Local = wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(Shared + 8);
      v1 = Local;
      if ( Local )
      {
        if ( !*(_QWORD *)(Local + 8) )
          *(_QWORD *)(Local + 8) = v3 + 4;
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x180014b34  mov     [rsp+arg_0], rbx
0x180014b39  push    rdi
0x180014b3a  sub     rsp, 20h
0x180014b3e  xor     ebx, ebx
0x180014b40  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180014b47  jz      short loc_180014B76
0x180014b49  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x180014b4e  mov     rdi, rax
0x180014b51  test    rax, rax
0x180014b54  jz      short loc_180014B76
0x180014b56  lea     rcx, [rax+8]
0x180014b5a  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x180014b5f  mov     rbx, rax
0x180014b62  test    rax, rax
0x180014b65  jz      short loc_180014B76
0x180014b67  cmp     qword ptr [rax+8], 0
0x180014b6c  jnz     short loc_180014B76
0x180014b6e  lea     rcx, [rdi+4]
0x180014b72  mov     [rax+8], rcx
0x180014b76  mov     rax, rbx
0x180014b79  mov     rbx, [rsp+28h+arg_0]
0x180014b7e  add     rsp, 20h
0x180014b82  pop     rdi
0x180014b83  retn
```
