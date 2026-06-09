# UpdateNoLearnFlag

- ea: `0x18000a43c`
- end: `0x18000a511`
- name: `UpdateNoLearnFlag`
- size: `213`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180009250`

## callees

- `0x18000a43c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall UpdateNoLearnFlag(__int64 *a1)
{
  __int64 result; // rax
  unsigned int i; // ebx
  __int64 v4; // rax
  __int64 v5; // rcx
  _OWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+40h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp-10h]
  unsigned int v9; // [rsp+70h] [rbp+10h] BYREF
  __int64 v10; // [rsp+78h] [rbp+18h] BYREF

  v9 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a1 + 56))(a1, &v9);
  for ( i = 0; i < v9; ++i )
  {
    v4 = *a1;
    v10 = 0;
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v4 + 64))(a1, i, &v10);
    v5 = v10;
    if ( v10 )
    {
      memset(v6, 0, sizeof(v6));
      v7 = 0;
      v8 = 0;
      LODWORD(v6[0]) = 32;
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v10 + 40LL))(v10, v6);
      HIDWORD(v7) |= 0x200u;
      result = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v10 + 48LL))(v10, v6);
      v5 = v10;
    }
    if ( v5 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000a43c  mov     [rsp-8+arg_10], rbx
0x18000a441  mov     [rsp-8+arg_18], rdi
0x18000a446  push    rbp
0x18000a447  mov     rbp, rsp
0x18000a44a  sub     rsp, 60h
0x18000a44e  mov     rdi, rcx
0x18000a451  mov     [rbp+arg_0], 0
0x18000a458  mov     rax, [rcx]
0x18000a45b  lea     rdx, [rbp+arg_0]
0x18000a45f  mov     rax, [rax+38h]
0x18000a463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a468  xor     ebx, ebx
0x18000a46a  cmp     [rbp+arg_0], ebx
0x18000a46d  jbe     loc_18000A4FF
0x18000a473  mov     rax, [rdi]
0x18000a476  mov     [rbp+arg_8], 0
0x18000a47e  lea     r8, [rbp+arg_8]
0x18000a482  mov     edx, ebx
0x18000a484  mov     rcx, rdi
0x18000a487  mov     rax, [rax+40h]
0x18000a48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a490  mov     rcx, [rbp+arg_8]
0x18000a494  test    rcx, rcx
0x18000a497  jz      short loc_18000A4E2
0x18000a499  xorps   xmm0, xmm0
0x18000a49c  xor     eax, eax
0x18000a49e  movups  [rbp+var_40], xmm0
0x18000a4a2  movups  [rbp+var_30], xmm0
0x18000a4a6  movups  [rbp+var_20], xmm0
0x18000a4aa  mov     [rbp+var_10], rax
0x18000a4ae  mov     dword ptr [rbp+var_40], 20h ; ' '
0x18000a4b5  mov     rax, [rcx]
0x18000a4b8  lea     rdx, [rbp+var_40]
0x18000a4bc  mov     rax, [rax+28h]
0x18000a4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c5  bts     dword ptr [rbp+var_20+0Ch], 9
0x18000a4ca  mov     rcx, [rbp+arg_8]
0x18000a4ce  mov     rax, [rcx]
0x18000a4d1  lea     rdx, [rbp+var_40]
0x18000a4d5  mov     rax, [rax+30h]
0x18000a4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4de  mov     rcx, [rbp+arg_8]
0x18000a4e2  test    rcx, rcx
0x18000a4e5  jz      short loc_18000A4F4
0x18000a4e7  mov     rax, [rcx]
0x18000a4ea  mov     rax, [rax+10h]
0x18000a4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f3  nop
0x18000a4f4  inc     ebx
0x18000a4f6  cmp     ebx, [rbp+arg_0]
0x18000a4f9  jb      loc_18000A473
0x18000a4ff  lea     r11, [rsp+60h+var_s0]
0x18000a504  mov     rbx, [r11+20h]
0x18000a508  mov     rdi, [r11+28h]
0x18000a50c  mov     rsp, r11
0x18000a50f  pop     rbp
0x18000a510  retn
```
