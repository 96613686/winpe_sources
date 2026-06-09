# TranslateLocalCallTargetInfoToRemoteCallTargetInfo

- ea: `0x180007e10`
- end: `0x180007e85`
- name: `TranslateLocalCallTargetInfoToRemoteCallTargetInfo`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007600`
- `0x1800078a0`

## callees

- `0x180004dc0`
- `0x180007e10`

## pseudocode

```c
__int16 __fastcall TranslateLocalCallTargetInfoToRemoteCallTargetInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rax

  *(_BYTE *)a2 = *(_BYTE *)a1;
  *(_WORD *)(a2 + 2) = *(_WORD *)(a1 + 2);
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 4);
  *(_WORD *)(a2 + 8) = 0;
  v4 = (__int64)MIDL_user_allocate(0x19u);
  *(_QWORD *)(a2 + 16) = v4;
  if ( v4 )
  {
    *(_OWORD *)v4 = *(_OWORD *)(a1 + 8);
    *(_QWORD *)(v4 + 16) = *(_QWORD *)(a1 + 24);
    *(_BYTE *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)(a2 + 16) + v4) );
    LOWORD(v4) = v4 + 1;
    *(_WORD *)(a2 + 8) = v4;
  }
  return v4;
}

```

## disassembly

```asm
0x180007e10  mov     [rsp+arg_0], rbx
0x180007e15  push    rdi
0x180007e16  sub     rsp, 20h
0x180007e1a  mov     al, [rcx]
0x180007e1c  mov     rdi, rcx
0x180007e1f  mov     [rdx], al
0x180007e21  mov     rbx, rdx
0x180007e24  movzx   eax, word ptr [rcx+2]
0x180007e28  mov     [rdx+2], ax
0x180007e2c  mov     eax, [rcx+4]
0x180007e2f  mov     [rdx+4], eax
0x180007e32  xor     eax, eax
0x180007e34  mov     [rdx+8], ax
0x180007e38  lea     ecx, [rax+19h]; size
0x180007e3b  call    MIDL_user_allocate
0x180007e40  mov     [rbx+10h], rax
0x180007e44  test    rax, rax
0x180007e47  jz      short loc_180007E7A
0x180007e49  movups  xmm0, xmmword ptr [rdi+8]
0x180007e4d  movups  xmmword ptr [rax], xmm0
0x180007e50  movsd   xmm1, qword ptr [rdi+18h]
0x180007e55  movsd   qword ptr [rax+10h], xmm1
0x180007e5a  mov     rax, [rbx+10h]
0x180007e5e  mov     byte ptr [rax+18h], 0
0x180007e62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e66  mov     rcx, [rbx+10h]
0x180007e6a  inc     rax
0x180007e6d  cmp     byte ptr [rcx+rax], 0
0x180007e71  jnz     short loc_180007E6A
0x180007e73  inc     ax
0x180007e76  mov     [rbx+8], ax
0x180007e7a  mov     rbx, [rsp+28h+arg_0]
0x180007e7f  add     rsp, 20h
0x180007e83  pop     rdi
0x180007e84  retn
```
