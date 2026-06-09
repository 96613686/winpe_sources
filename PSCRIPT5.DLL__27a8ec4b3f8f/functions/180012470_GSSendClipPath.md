# GSSendClipPath

- ea: `0x180012470`
- end: `0x180012593`
- name: `GSSendClipPath`
- size: `291`
- prototype: `_BOOL8 __fastcall(__int64, CLIPOBJ *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000982c`
- `0x180012200`
- `0x18001ad28`

## callees

- `0x180012470`
- `0x1800170a0`
- `0x180017340`
- `0x18001758c`
- `0x180019e10`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800124ab`
- `KERNEL32!SetLastError` at `0x1800124ab`
- `GDI32!EngDeletePath` at `0x1800124fc`
- `GDI32!EngDeletePath` at `0x1800124fc`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800124bc`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800124bc`

## pseudocode

```c
_BOOL8 __fastcall GSSendClipPath(__int64 a1, CLIPOBJ *a2)
{
  PATHOBJ *Path; // rax
  PATHOBJ *v5; // rsi

  if ( a2->iDComplexity == 1 )
  {
    OPSendInt(a1, a2->rclBounds.left);
    OPSendInt(a1, a2->rclBounds.top);
    OPSendInt(a1, a2->rclBounds.right - a2->rclBounds.left);
    OPSendInt(a1, a2->rclBounds.bottom - a2->rclBounds.top);
    OPRawPortWrite(a1, "rc ", 3u);
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
    OPSendOperator(a1, 0x21u);
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
0x180012470  mov     [rsp+arg_0], rbx
0x180012475  mov     [rsp+arg_8], rsi
0x18001247a  push    rdi
0x18001247b  sub     rsp, 20h
0x18001247f  mov     rbx, rcx
0x180012482  mov     rdi, rdx
0x180012485  movzx   ecx, byte ptr [rdx+14h]
0x180012489  sub     ecx, 1
0x18001248c  jz      short loc_18001250A
0x18001248e  cmp     ecx, 2
0x180012491  jz      short loc_1800124B9
0x180012493  cmp     dword ptr [rbx+0D70h], 0
0x18001249a  jnz     short loc_1800124DA
0x18001249c  mov     ecx, 32h ; '2'; dwErrCode
0x1800124a1  mov     dword ptr [rbx+0D70h], 1
0x1800124ab  call    cs:__imp_SetLastError
0x1800124b2  nop     dword ptr [rax+rax+00h]
0x1800124b7  jmp     short loc_1800124DA
0x1800124b9  mov     rcx, rdi; pco
0x1800124bc  call    cs:__imp_CLIPOBJ_ppoGetPath
0x1800124c3  nop     dword ptr [rax+rax+00h]
0x1800124c8  mov     rsi, rax
0x1800124cb  test    rax, rax
0x1800124ce  jnz     short loc_1800124E1
0x1800124d0  mov     dword ptr [rbx+0D70h], 1
0x1800124da  xor     eax, eax
0x1800124dc  jmp     loc_180012582
0x1800124e1  mov     rdx, rsi
0x1800124e4  mov     rcx, rbx
0x1800124e7  call    GBSendPath
0x1800124ec  mov     edx, 21h ; '!'
0x1800124f1  mov     rcx, rbx
0x1800124f4  call    OPSendOperator
0x1800124f9  mov     rcx, rsi; ppo
0x1800124fc  call    cs:__imp_EngDeletePath
0x180012503  nop     dword ptr [rax+rax+00h]
0x180012508  jmp     short loc_180012551
0x18001250a  mov     edx, [rdx+4]
0x18001250d  mov     rcx, rbx
0x180012510  call    OPSendInt
0x180012515  mov     edx, [rdi+8]
0x180012518  mov     rcx, rbx
0x18001251b  call    OPSendInt
0x180012520  mov     edx, [rdi+0Ch]
0x180012523  mov     rcx, rbx
0x180012526  sub     edx, [rdi+4]
0x180012529  call    OPSendInt
0x18001252e  mov     edx, [rdi+10h]
0x180012531  mov     rcx, rbx
0x180012534  sub     edx, [rdi+8]
0x180012537  call    OPSendInt
0x18001253c  mov     r8d, 3
0x180012542  lea     rdx, PSFRAG_rc; "rc "
0x180012549  mov     rcx, rbx
0x18001254c  call    OPRawPortWrite
0x180012551  mov     eax, [rdi]
0x180012553  mov     rcx, [rbx+2F0h]
0x18001255a  mov     [rcx+5Ch], eax
0x18001255d  mov     rax, [rbx+2F0h]
0x180012564  and     dword ptr [rax], 0FFFFFFFBh
0x180012567  mov     rax, [rbx+2F0h]
0x18001256e  movups  xmm0, xmmword ptr [rdi+4]
0x180012572  movdqu  xmmword ptr [rax+60h], xmm0
0x180012577  xor     eax, eax
0x180012579  cmp     [rbx+0D70h], eax
0x18001257f  setz    al
0x180012582  mov     rbx, [rsp+28h+arg_0]
0x180012587  mov     rsi, [rsp+28h+arg_8]
0x18001258c  add     rsp, 20h
0x180012590  pop     rdi
0x180012591  retn
```
