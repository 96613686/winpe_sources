# IThumbnailCache_RemoteGetThumbnailByID_Thunk

- ea: `0x180005d70`
- end: `0x180005dc5`
- name: `IThumbnailCache_RemoteGetThumbnailByID_Thunk`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall IThumbnailCache_RemoteGetThumbnailByID_Thunk(__int64 a1)
{
  __int64 v1; // rbx
  _DWORD *v2; // rdx
  __int64 *v3; // rcx
  __int128 v4; // xmm0
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 result; // rax
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 136);
  v3 = *(__int64 **)v1;
  v4 = *(_OWORD *)*(_QWORD *)(v1 + 8);
  v5 = *(unsigned int *)(v1 + 16);
  v2 = *(_DWORD **)(v1 + 32);
  **(_QWORD **)(v1 + 24) = 0;
  *v2 = 0;
  v6 = *v3;
  v8 = v4;
  result = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v6 + 32))(v3, &v8, v5);
  *(_DWORD *)(v1 + 40) = result;
  return result;
}

```

## disassembly

```asm
0x180005d70  push    rbx
0x180005d72  sub     rsp, 40h
0x180005d76  mov     rbx, [rcx+88h]
0x180005d7d  mov     rax, [rbx+8]
0x180005d81  mov     rdx, [rbx+20h]
0x180005d85  mov     rcx, [rbx]
0x180005d88  mov     r9, [rbx+18h]
0x180005d8c  movups  xmm0, xmmword ptr [rax]
0x180005d8f  mov     r8d, [rbx+10h]
0x180005d93  mov     [rsp+48h+var_28], rdx
0x180005d98  mov     qword ptr [r9], 0
0x180005d9f  mov     dword ptr [rdx], 0
0x180005da5  lea     rdx, [rsp+48h+var_18]
0x180005daa  mov     rax, [rcx]
0x180005dad  movdqa  [rsp+48h+var_18], xmm0
0x180005db3  mov     rax, [rax+20h]
0x180005db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbc  mov     [rbx+28h], eax
0x180005dbf  add     rsp, 40h
0x180005dc3  pop     rbx
0x180005dc4  retn
```
