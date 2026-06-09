# winrt::com_ptr<IWICBitmapSource>::copy_ref(IWICBitmapSource *)

- ea: `0x18001c1b4`
- end: `0x18001c1f7`
- name: `?copy_ref@?$com_ptr@UIWICBitmapSource@@@winrt@@AEAAXPEAUIWICBitmapSource@@@Z`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b744`

## callees

- `0x18001c1b4`
- `0x18001c7b0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::com_ptr<IWICBitmapSource>::copy_ref(__int64 *a1, __int64 a2)
{
  __int64 result; // rax

  if ( *a1 != a2 )
  {
    if ( *a1 )
      result = winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1);
    *a1 = a2;
    if ( a2 )
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  }
  return result;
}

```

## disassembly

```asm
0x18001c1b4  mov     [rsp+arg_0], rbx
0x18001c1b9  push    rdi
0x18001c1ba  sub     rsp, 20h
0x18001c1be  mov     rbx, rdx
0x18001c1c1  mov     rdi, rcx
0x18001c1c4  cmp     [rcx], rdx
0x18001c1c7  jz      short loc_18001C1EC
0x18001c1c9  cmp     qword ptr [rcx], 0
0x18001c1cd  jz      short loc_18001C1D4
0x18001c1cf  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18001c1d4  mov     [rdi], rbx
0x18001c1d7  test    rbx, rbx
0x18001c1da  jz      short loc_18001C1EC
0x18001c1dc  mov     rax, [rbx]
0x18001c1df  mov     rcx, rbx
0x18001c1e2  mov     rax, [rax+8]
0x18001c1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1eb  nop
0x18001c1ec  mov     rbx, [rsp+28h+arg_0]
0x18001c1f1  add     rsp, 20h
0x18001c1f5  pop     rdi
0x18001c1f6  retn
```
