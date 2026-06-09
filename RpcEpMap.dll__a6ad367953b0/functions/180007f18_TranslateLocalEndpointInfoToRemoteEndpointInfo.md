# TranslateLocalEndpointInfoToRemoteEndpointInfo

- ea: `0x180007f18`
- end: `0x180007f89`
- name: `TranslateLocalEndpointInfoToRemoteEndpointInfo`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007600`
- `0x1800079b0`

## callees

- `0x180004dc0`
- `0x180007f18`

## pseudocode

```c
__int16 __fastcall TranslateLocalEndpointInfoToRemoteEndpointInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rax

  *(_BYTE *)a2 = *(_BYTE *)a1;
  *(_BYTE *)(a2 + 1) = *(_BYTE *)(a1 + 1);
  *(_BYTE *)(a2 + 2) = *(_BYTE *)(a1 + 2);
  *(_WORD *)(a2 + 4) = 0;
  v4 = (__int64)MIDL_user_allocate(0x1Du);
  *(_QWORD *)(a2 + 8) = v4;
  if ( v4 )
  {
    *(_OWORD *)v4 = *(_OWORD *)(a1 + 4);
    *(_OWORD *)(v4 + 12) = *(_OWORD *)(a1 + 16);
    *(_BYTE *)(*(_QWORD *)(a2 + 8) + 28LL) = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)(a2 + 8) + v4) );
    LOWORD(v4) = v4 + 1;
    *(_WORD *)(a2 + 4) = v4;
  }
  return v4;
}

```

## disassembly

```asm
0x180007f18  mov     [rsp+arg_0], rbx
0x180007f1d  push    rdi
0x180007f1e  sub     rsp, 20h
0x180007f22  mov     al, [rcx]
0x180007f24  mov     rdi, rcx
0x180007f27  mov     [rdx], al
0x180007f29  mov     rbx, rdx
0x180007f2c  mov     al, [rcx+1]
0x180007f2f  mov     [rdx+1], al
0x180007f32  mov     al, [rcx+2]
0x180007f35  mov     [rdx+2], al
0x180007f38  xor     eax, eax
0x180007f3a  mov     [rdx+4], ax
0x180007f3e  lea     ecx, [rax+1Dh]; size
0x180007f41  call    MIDL_user_allocate
0x180007f46  mov     [rbx+8], rax
0x180007f4a  test    rax, rax
0x180007f4d  jz      short loc_180007F7E
0x180007f4f  movups  xmm0, xmmword ptr [rdi+4]
0x180007f53  movups  xmmword ptr [rax], xmm0
0x180007f56  movups  xmm1, xmmword ptr [rdi+10h]
0x180007f5a  movups  xmmword ptr [rax+0Ch], xmm1
0x180007f5e  mov     rax, [rbx+8]
0x180007f62  mov     byte ptr [rax+1Ch], 0
0x180007f66  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007f6a  mov     rcx, [rbx+8]
0x180007f6e  inc     rax
0x180007f71  cmp     byte ptr [rcx+rax], 0
0x180007f75  jnz     short loc_180007F6E
0x180007f77  inc     ax
0x180007f7a  mov     [rbx+4], ax
0x180007f7e  mov     rbx, [rsp+28h+arg_0]
0x180007f83  add     rsp, 20h
0x180007f87  pop     rdi
0x180007f88  retn
```
