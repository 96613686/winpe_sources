# IThumbnailCache_RemoteGetThumbnail_Thunk

- ea: `0x180005dd0`
- end: `0x180005e39`
- name: `IThumbnailCache_RemoteGetThumbnail_Thunk`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall IThumbnailCache_RemoteGetThumbnail_Thunk(__int64 a1)
{
  __int64 *v1; // rdi
  _QWORD *v2; // r11
  _DWORD *v3; // r10
  _OWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 result; // rax

  v1 = *(__int64 **)(a1 + 136);
  v2 = (_QWORD *)v1[4];
  v3 = (_DWORD *)v1[5];
  v4 = (_OWORD *)v1[6];
  v5 = *v1;
  v6 = *((unsigned int *)v1 + 6);
  v7 = *((unsigned int *)v1 + 4);
  v8 = v1[1];
  *v2 = 0;
  *v3 = 0;
  *v4 = 0;
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *, _DWORD *, _OWORD *))(*(_QWORD *)v5 + 24LL))(
             v5,
             v8,
             v7,
             v6,
             v2,
             v3,
             v4);
  *((_DWORD *)v1 + 14) = result;
  return result;
}

```

## disassembly

```asm
0x180005dd0  mov     [rsp+arg_0], rbx
0x180005dd5  push    rdi
0x180005dd6  sub     rsp, 40h
0x180005dda  mov     rdi, [rcx+88h]
0x180005de1  xorps   xmm0, xmm0
0x180005de4  mov     r11, [rdi+20h]
0x180005de8  mov     r10, [rdi+28h]
0x180005dec  mov     rbx, [rdi+30h]
0x180005df0  mov     rcx, [rdi]
0x180005df3  mov     r9d, [rdi+18h]
0x180005df7  mov     r8d, [rdi+10h]
0x180005dfb  mov     rdx, [rdi+8]
0x180005dff  mov     qword ptr [r11], 0
0x180005e06  mov     dword ptr [r10], 0
0x180005e0d  movups  xmmword ptr [rbx], xmm0
0x180005e10  mov     rax, [rcx]
0x180005e13  mov     [rsp+48h+var_18], rbx
0x180005e18  mov     [rsp+48h+var_20], r10
0x180005e1d  mov     [rsp+48h+var_28], r11
0x180005e22  mov     rax, [rax+18h]
0x180005e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2b  mov     rbx, [rsp+48h+arg_0]
0x180005e30  mov     [rdi+38h], eax
0x180005e33  add     rsp, 40h
0x180005e37  pop     rdi
0x180005e38  retn
```
