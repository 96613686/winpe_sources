# std::_Packaged_state_void___cdecl(void)_::_Packaged_state_void___cdecl(void)__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____0_

- ea: `0x18000e9c0`
- end: `0x18000eaa8`
- name: `std::_Packaged_state_void___cdecl(void)_::_Packaged_state_void___cdecl(void)__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____0_`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eab0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e9f4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e9f4`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_void___cdecl_void__::_Packaged_state_void___cdecl_void___std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____0_(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rcx
  __int64 result; // rax

  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  v3 = (_QWORD *)(a1 + 16);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate(v3);
  *(_QWORD *)(a1 + 32) = 2;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 108) = 0;
  *(_DWORD *)(a1 + 104) = -1;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 128) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)a1 = &std::_Packaged_state<void (void)>::`vftable';
  *(_BYTE *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 188) = 0;
  *(_WORD *)(a1 + 192) = 0;
  *(_BYTE *)(a1 + 194) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 208) = &off_18001A7A8;
  *(_QWORD *)(a1 + 216) = *a2;
  result = a1;
  *(_QWORD *)(a1 + 264) = a1 + 208;
  return result;
}

```

## disassembly

```asm
0x18000e9c0  mov     [rsp+arg_0], rbx
0x18000e9c5  mov     [rsp+arg_8], rsi
0x18000e9ca  push    rdi
0x18000e9cb  sub     rsp, 20h
0x18000e9cf  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18000e9d6  mov     qword ptr [rcx+8], 1
0x18000e9de  mov     [rcx], rax
0x18000e9e1  mov     rdi, rcx
0x18000e9e4  add     rcx, 10h
0x18000e9e8  xor     esi, esi
0x18000e9ea  mov     rbx, rdx
0x18000e9ed  mov     [rcx], rsi
0x18000e9f0  mov     [rcx+8], rsi
0x18000e9f4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000e9fa  mov     qword ptr [rdi+20h], 2
0x18000ea02  lea     rcx, [rdi+0D0h]
0x18000ea09  xorps   xmm0, xmm0
0x18000ea0c  xor     eax, eax
0x18000ea0e  movups  xmmword ptr [rdi+38h], xmm0
0x18000ea12  movups  xmmword ptr [rdi+48h], xmm0
0x18000ea16  movups  xmmword ptr [rdi+58h], xmm0
0x18000ea1a  mov     [rdi+28h], rsi
0x18000ea1e  mov     [rdi+30h], rsi
0x18000ea22  mov     [rdi+6Ch], esi
0x18000ea25  mov     dword ptr [rdi+68h], 0FFFFFFFFh
0x18000ea2c  mov     [rdi+70h], rsi
0x18000ea30  mov     [rdi+78h], rsi
0x18000ea34  movups  xmmword ptr [rdi+80h], xmm0
0x18000ea3b  movups  xmmword ptr [rdi+90h], xmm0
0x18000ea42  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000ea49  mov     [rdi+0B0h], rax
0x18000ea50  lea     rax, ??_7?$_Packaged_state@$$A6AXXZ@std@@6B@; const std::_Packaged_state<void (void)>::`vftable'
0x18000ea57  mov     [rdi], rax
0x18000ea5a  lea     rax, off_18001A7A8
0x18000ea61  mov     [rdi+0B8h], sil
0x18000ea68  mov     [rdi+0BCh], esi
0x18000ea6e  mov     [rdi+0C0h], si
0x18000ea75  mov     [rdi+0C2h], sil
0x18000ea7c  mov     [rdi+0C8h], rsi
0x18000ea83  mov     [rcx+38h], rsi
0x18000ea87  mov     rsi, [rsp+28h+arg_8]
0x18000ea8c  mov     [rcx], rax
0x18000ea8f  mov     rax, [rbx]
0x18000ea92  mov     rbx, [rsp+28h+arg_0]
0x18000ea97  mov     [rcx+8], rax
0x18000ea9b  mov     rax, rdi
0x18000ea9e  mov     [rcx+38h], rcx
0x18000eaa2  add     rsp, 20h
0x18000eaa6  pop     rdi
0x18000eaa7  retn
```
