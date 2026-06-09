# std::shared_ptr<AppMon::AppPortEntry>::operator=(std::shared_ptr<AppMon::AppPortEntry> const &)

- ea: `0x18000894c`
- end: `0x180008987`
- name: `??4?$shared_ptr@VAppPortEntry@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800064d4`
- `0x1800066cc`
- `0x18000691c`
- `0x180008a94`
- `0x180008d9c`
- `0x18000a1d8`
- `0x18000a758`
- `0x18000b990`
- `0x18000e560`

## callees

- `0x18000798c`
- `0x18000894c`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<AppMon::AppPortEntry>::operator=(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v4 = a2[1];
  *a1 = *a2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x18000894c  push    rbx
0x18000894e  sub     rsp, 20h
0x180008952  mov     rax, [rdx+8]
0x180008956  mov     rbx, rcx
0x180008959  test    rax, rax
0x18000895c  jz      short loc_180008962
0x18000895e  lock inc dword ptr [rax+8]
0x180008962  mov     rax, [rdx]
0x180008965  mov     r8, [rdx+8]
0x180008969  mov     [rcx], rax
0x18000896c  mov     rcx, [rcx+8]; this
0x180008970  mov     [rbx+8], r8
0x180008974  test    rcx, rcx
0x180008977  jz      short loc_18000897E
0x180008979  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000897e  mov     rax, rbx
0x180008981  add     rsp, 20h
0x180008985  pop     rbx
0x180008986  retn
```
