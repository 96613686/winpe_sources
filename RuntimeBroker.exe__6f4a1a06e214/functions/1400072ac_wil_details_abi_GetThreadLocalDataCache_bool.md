# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400072ac`
- end: `0x1400072fc`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007244`

## callees

- `0x1400072ac`
- `0x140007304`
- `0x14000843c`

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
0x1400072ac  mov     [rsp+arg_0], rbx
0x1400072b1  push    rdi
0x1400072b2  sub     rsp, 20h
0x1400072b6  xor     ebx, ebx
0x1400072b8  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400072bf  jz      short loc_1400072EE
0x1400072c1  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x1400072c6  mov     rdi, rax
0x1400072c9  test    rax, rax
0x1400072cc  jz      short loc_1400072EE
0x1400072ce  lea     rcx, [rax+8]
0x1400072d2  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x1400072d7  mov     rbx, rax
0x1400072da  test    rax, rax
0x1400072dd  jz      short loc_1400072EE
0x1400072df  cmp     qword ptr [rax+8], 0
0x1400072e4  jnz     short loc_1400072EE
0x1400072e6  lea     rcx, [rdi+4]
0x1400072ea  mov     [rax+8], rcx
0x1400072ee  mov     rax, rbx
0x1400072f1  mov     rbx, [rsp+28h+arg_0]
0x1400072f6  add     rsp, 20h
0x1400072fa  pop     rdi
0x1400072fb  retn
```
