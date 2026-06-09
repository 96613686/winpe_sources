# TranslateLocalClientCallInfoToRemoteClientCallInfo

- ea: `0x180007e8c`
- end: `0x180007f11`
- name: `TranslateLocalClientCallInfoToRemoteClientCallInfo`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007600`
- `0x1800078a0`

## callees

- `0x180004dc0`
- `0x180007e8c`

## pseudocode

```c
__int16 __fastcall TranslateLocalClientCallInfoToRemoteClientCallInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rax

  *(_BYTE *)a2 = *(_BYTE *)a1;
  *(_WORD *)(a2 + 2) = *(_WORD *)(a1 + 2);
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 16);
  *(_WORD *)(a2 + 20) = 0;
  v4 = (__int64)MIDL_user_allocate(0xDu);
  *(_QWORD *)(a2 + 24) = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = *(_QWORD *)(a1 + 20);
    *(_DWORD *)(v4 + 8) = *(_DWORD *)(a1 + 28);
    *(_BYTE *)(*(_QWORD *)(a2 + 24) + 12LL) = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)(a2 + 24) + v4) );
    LOWORD(v4) = v4 + 1;
    *(_WORD *)(a2 + 20) = v4;
  }
  return v4;
}

```

## disassembly

```asm
0x180007e8c  mov     [rsp+arg_0], rbx
0x180007e91  push    rdi
0x180007e92  sub     rsp, 20h
0x180007e96  mov     al, [rcx]
0x180007e98  mov     rdi, rcx
0x180007e9b  mov     [rdx], al
0x180007e9d  mov     rbx, rdx
0x180007ea0  movzx   eax, word ptr [rcx+2]
0x180007ea4  mov     [rdx+2], ax
0x180007ea8  mov     eax, [rcx+4]
0x180007eab  mov     [rdx+4], eax
0x180007eae  mov     eax, [rcx+8]
0x180007eb1  mov     [rdx+8], eax
0x180007eb4  mov     eax, [rcx+0Ch]
0x180007eb7  mov     [rdx+0Ch], eax
0x180007eba  mov     eax, [rcx+10h]
0x180007ebd  mov     [rdx+10h], eax
0x180007ec0  xor     eax, eax
0x180007ec2  mov     [rdx+14h], ax
0x180007ec6  lea     ecx, [rax+0Dh]; size
0x180007ec9  call    MIDL_user_allocate
0x180007ece  mov     [rbx+18h], rax
0x180007ed2  test    rax, rax
0x180007ed5  jz      short loc_180007F06
0x180007ed7  movsd   xmm0, qword ptr [rdi+14h]
0x180007edc  movsd   qword ptr [rax], xmm0
0x180007ee0  mov     ecx, [rdi+1Ch]
0x180007ee3  mov     [rax+8], ecx
0x180007ee6  mov     rax, [rbx+18h]
0x180007eea  mov     byte ptr [rax+0Ch], 0
0x180007eee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007ef2  mov     rcx, [rbx+18h]
0x180007ef6  inc     rax
0x180007ef9  cmp     byte ptr [rcx+rax], 0
0x180007efd  jnz     short loc_180007EF6
0x180007eff  inc     ax
0x180007f02  mov     [rbx+14h], ax
0x180007f06  mov     rbx, [rsp+28h+arg_0]
0x180007f0b  add     rsp, 20h
0x180007f0f  pop     rdi
0x180007f10  retn
```
