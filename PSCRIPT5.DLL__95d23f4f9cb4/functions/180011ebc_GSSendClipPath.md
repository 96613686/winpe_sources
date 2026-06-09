# GSSendClipPath

- ea: `0x180011ebc`
- end: `0x180011fcc`
- name: `GSSendClipPath`
- size: `272`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009524`
- `0x180011c50`
- `0x18001a404`

## callees

- `0x180011ebc`
- `0x180016940`
- `0x180016bdc`
- `0x180016e24`
- `0x1800195a4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011ef7`
- `KERNEL32!SetLastError` at `0x180011ef7`
- `GDI32!EngDeletePath` at `0x180011f3c`
- `GDI32!EngDeletePath` at `0x180011f3c`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180011f02`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180011f02`

## pseudocode

```c
_BOOL8 __fastcall GSSendClipPath(__int64 a1, CLIPOBJ *a2)
{
  PATHOBJ *Path; // rax
  PATHOBJ *v5; // rsi

  if ( a2->iDComplexity == 1 )
  {
    OPSendInt(a1, (unsigned int)a2->rclBounds.left);
    OPSendInt(a1, (unsigned int)a2->rclBounds.top);
    OPSendInt(a1, (unsigned int)(a2->rclBounds.right - a2->rclBounds.left));
    OPSendInt(a1, (unsigned int)(a2->rclBounds.bottom - a2->rclBounds.top));
    OPRawPortWrite(a1, "rc ", 3);
  }
  else
  {
    if ( a2->iDComplexity != 3 )
    {
      if ( !*(_DWORD *)(a1 + 3440) )
      {
        *(_DWORD *)(a1 + 3440) = 1;
        SetLastError(0x32u);
      }
      return 0;
    }
    Path = CLIPOBJ_ppoGetPath(a2);
    v5 = Path;
    if ( !Path )
    {
      *(_DWORD *)(a1 + 3440) = 1;
      return 0;
    }
    GBSendPath(a1, Path);
    OPSendOperator(a1, 33);
    EngDeletePath(v5);
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 752) + 92LL) = a2->iUniq;
  **(_DWORD **)(a1 + 752) &= ~4u;
  *(RECTL *)(*(_QWORD *)(a1 + 752) + 96LL) = a2->rclBounds;
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180011ebc  mov     [rsp+arg_0], rbx
0x180011ec1  mov     [rsp+arg_8], rsi
0x180011ec6  push    rdi
0x180011ec7  sub     rsp, 20h
0x180011ecb  mov     rbx, rcx
0x180011ece  mov     rdi, rdx
0x180011ed1  movzx   ecx, byte ptr [rdx+14h]
0x180011ed5  sub     ecx, 1
0x180011ed8  jz      short loc_180011F44
0x180011eda  cmp     ecx, 2
0x180011edd  jz      short loc_180011EFF
0x180011edf  cmp     dword ptr [rbx+0D70h], 0
0x180011ee6  jnz     short loc_180011F1A
0x180011ee8  mov     ecx, 32h ; '2'; dwErrCode
0x180011eed  mov     dword ptr [rbx+0D70h], 1
0x180011ef7  call    cs:__imp_SetLastError
0x180011efd  jmp     short loc_180011F1A
0x180011eff  mov     rcx, rdi; pco
0x180011f02  call    cs:__imp_CLIPOBJ_ppoGetPath
0x180011f08  mov     rsi, rax
0x180011f0b  test    rax, rax
0x180011f0e  jnz     short loc_180011F21
0x180011f10  mov     dword ptr [rbx+0D70h], 1
0x180011f1a  xor     eax, eax
0x180011f1c  jmp     loc_180011FBC
0x180011f21  mov     rdx, rsi
0x180011f24  mov     rcx, rbx
0x180011f27  call    GBSendPath
0x180011f2c  mov     edx, 21h ; '!'
0x180011f31  mov     rcx, rbx
0x180011f34  call    OPSendOperator
0x180011f39  mov     rcx, rsi; ppo
0x180011f3c  call    cs:__imp_EngDeletePath
0x180011f42  jmp     short loc_180011F8B
0x180011f44  mov     edx, [rdx+4]
0x180011f47  mov     rcx, rbx
0x180011f4a  call    OPSendInt
0x180011f4f  mov     edx, [rdi+8]
0x180011f52  mov     rcx, rbx
0x180011f55  call    OPSendInt
0x180011f5a  mov     edx, [rdi+0Ch]
0x180011f5d  mov     rcx, rbx
0x180011f60  sub     edx, [rdi+4]
0x180011f63  call    OPSendInt
0x180011f68  mov     edx, [rdi+10h]
0x180011f6b  mov     rcx, rbx
0x180011f6e  sub     edx, [rdi+8]
0x180011f71  call    OPSendInt
0x180011f76  mov     r8d, 3
0x180011f7c  lea     rdx, PSFRAG_rc; "rc "
0x180011f83  mov     rcx, rbx
0x180011f86  call    OPRawPortWrite
0x180011f8b  mov     eax, [rdi]
0x180011f8d  mov     rcx, [rbx+2F0h]
0x180011f94  mov     [rcx+5Ch], eax
0x180011f97  mov     rax, [rbx+2F0h]
0x180011f9e  and     dword ptr [rax], 0FFFFFFFBh
0x180011fa1  mov     rax, [rbx+2F0h]
0x180011fa8  movups  xmm0, xmmword ptr [rdi+4]
0x180011fac  movdqu  xmmword ptr [rax+60h], xmm0
0x180011fb1  xor     eax, eax
0x180011fb3  cmp     [rbx+0D70h], eax
0x180011fb9  setz    al
0x180011fbc  mov     rbx, [rsp+28h+arg_0]
0x180011fc1  mov     rsi, [rsp+28h+arg_8]
0x180011fc6  add     rsp, 20h
0x180011fca  pop     rdi
0x180011fcb  retn
```
