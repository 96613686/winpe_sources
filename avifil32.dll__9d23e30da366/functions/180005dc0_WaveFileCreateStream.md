# WaveFileCreateStream

- ea: `0x180005dc0`
- end: `0x180005e1f`
- name: `WaveFileCreateStream`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005dc0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall WaveFileCreateStream(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax

  v3 = a1 - 8;
  if ( *(_QWORD *)(a1 - 8 + 280) || *a3 != 1935963489 )
    return 2147762277LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(a1 - 8);
  *(_DWORD *)(v3 + 288) = 0;
  result = 0;
  *(_QWORD *)(v3 + 280) = 0;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x180005dc0  mov     [rsp+arg_0], rbx
0x180005dc5  push    rdi
0x180005dc6  sub     rsp, 20h
0x180005dca  lea     rbx, [rcx-8]
0x180005dce  mov     rdi, rdx
0x180005dd1  cmp     qword ptr [rbx+118h], 0
0x180005dd9  jnz     short loc_180005E0F
0x180005ddb  cmp     dword ptr [r8], 73647561h
0x180005de2  jnz     short loc_180005E0F
0x180005de4  mov     rax, [rbx]
0x180005de7  mov     rcx, rbx
0x180005dea  mov     rax, [rax+8]
0x180005dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df3  mov     dword ptr [rbx+120h], 0
0x180005dfd  xor     eax, eax
0x180005dff  mov     qword ptr [rbx+118h], 0
0x180005e0a  mov     [rdi], rbx
0x180005e0d  jmp     short loc_180005E14
0x180005e0f  mov     eax, 80044065h
0x180005e14  mov     rbx, [rsp+28h+arg_0]
0x180005e19  add     rsp, 20h
0x180005e1d  pop     rdi
0x180005e1e  retn
```
