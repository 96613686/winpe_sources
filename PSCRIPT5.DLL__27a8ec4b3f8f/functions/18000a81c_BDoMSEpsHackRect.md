# BDoMSEpsHackRect

- ea: `0x18000a81c`
- end: `0x18000a9f7`
- name: `BDoMSEpsHackRect`
- size: `475`
- prototype: `__int64 __fastcall(__int64, __int64, PATHOBJ *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aa00`
- `0x18000ac50`
- `0x18000af70`

## callees

- `0x180001f20`
- `0x18000a81c`
- `0x1800170a0`
- `0x18001758c`
- `0x180017644`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18000a865`
- `GDI32!PATHOBJ_bEnum` at `0x18000a865`
- `GDI32!PATHOBJ_vEnumStart` at `0x18000a851`
- `GDI32!PATHOBJ_vEnumStart` at `0x18000a851`

## pseudocode

```c
__int64 __fastcall BDoMSEpsHackRect(__int64 a1, __int64 a2, PATHOBJ *a3)
{
  POINTFIX *pptfx; // rbx
  __int64 v7; // rdi
  __int64 v8; // r8
  PATHDATA ppd; // [rsp+40h] [rbp-78h] BYREF
  char v11[64]; // [rsp+50h] [rbp-68h] BYREF

  ppd = 0;
  PATHOBJ_vEnumStart(a3);
  if ( PATHOBJ_bEnum(a3, &ppd) )
    return 0;
  if ( ppd.count != 4 )
    return 0;
  if ( (ppd.flags & 0x19) != 9 )
    return 0;
  pptfx = ppd.pptfx;
  if ( !ppd.pptfx
    || ppd.pptfx->y != ppd.pptfx[1].y
    || ppd.pptfx[1].x != ppd.pptfx[2].x
    || ppd.pptfx[2].y != ppd.pptfx[3].y
    || ppd.pptfx[3].x != ppd.pptfx->x )
  {
    return 0;
  }
  OPSendOperator(a1, 0xFu);
  v7 = -1;
  if ( a2 && *(_BYTE *)(a2 + 20) == 1 )
  {
    OPSprintf(
      (__int64)v11,
      64,
      "%d %d %d %d ",
      *(_DWORD *)(a2 + 12) - *(_DWORD *)(a2 + 4),
      *(_DWORD *)(a2 + 16) - *(_DWORD *)(a2 + 8),
      *(_DWORD *)(a2 + 4),
      *(_DWORD *)(a2 + 8));
    v8 = -1;
    do
      ++v8;
    while ( v11[v8] );
    OPRawPortWrite(a1, v11, v8);
    OPRawPortWrite(a1, "CB ", 3u);
  }
  OPSprintf(
    (__int64)v11,
    64,
    "%d %d %d %d ",
    (pptfx->x - pptfx[1].x) >> 4,
    (pptfx[2].y - pptfx[1].y) >> 4,
    pptfx[1].x >> 4,
    pptfx[1].y >> 4);
  do
    ++v7;
  while ( v11[v7] );
  OPRawPortWrite(a1, v11, v7);
  OPRawPortWrite(a1, "B ", 2u);
  return 1;
}

```

## disassembly

```asm
0x18000a81c  mov     [rsp+arg_18], rbx
0x18000a821  push    rbp
0x18000a822  push    rsi
0x18000a823  push    rdi
0x18000a824  sub     rsp, 0A0h
0x18000a82b  mov     rax, cs:__security_cookie
0x18000a832  xor     rax, rsp
0x18000a835  mov     [rsp+0B8h+var_28], rax
0x18000a83d  mov     rbp, rcx
0x18000a840  xorps   xmm0, xmm0
0x18000a843  mov     rcx, r8; ppo
0x18000a846  mov     rbx, r8
0x18000a849  movups  xmmword ptr [rsp+0B8h+ppd.flags], xmm0
0x18000a84e  mov     rsi, rdx
0x18000a851  call    cs:__imp_PATHOBJ_vEnumStart
0x18000a858  nop     dword ptr [rax+rax+00h]
0x18000a85d  lea     rdx, [rsp+0B8h+ppd]; ppd
0x18000a862  mov     rcx, rbx; ppo
0x18000a865  call    cs:__imp_PATHOBJ_bEnum
0x18000a86c  nop     dword ptr [rax+rax+00h]
0x18000a871  test    eax, eax
0x18000a873  jnz     loc_18000A9D1
0x18000a879  cmp     [rsp+0B8h+ppd.count], 4
0x18000a87e  jnz     loc_18000A9D1
0x18000a884  mov     eax, [rsp+0B8h+ppd.flags]
0x18000a888  and     eax, 19h
0x18000a88b  cmp     al, 9
0x18000a88d  jnz     loc_18000A9D1
0x18000a893  mov     rbx, [rsp+0B8h+ppd.pptfx]
0x18000a898  test    rbx, rbx
0x18000a89b  jz      loc_18000A9D1
0x18000a8a1  mov     eax, [rbx+0Ch]
0x18000a8a4  cmp     [rbx+4], eax
0x18000a8a7  jnz     loc_18000A9D1
0x18000a8ad  mov     eax, [rbx+10h]
0x18000a8b0  cmp     [rbx+8], eax
0x18000a8b3  jnz     loc_18000A9D1
0x18000a8b9  mov     eax, [rbx+1Ch]
0x18000a8bc  cmp     [rbx+14h], eax
0x18000a8bf  jnz     loc_18000A9D1
0x18000a8c5  mov     eax, [rbx]
0x18000a8c7  cmp     [rbx+18h], eax
0x18000a8ca  jnz     loc_18000A9D1
0x18000a8d0  mov     edx, 0Fh
0x18000a8d5  mov     rcx, rbp
0x18000a8d8  call    OPSendOperator
0x18000a8dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a8e1  test    rsi, rsi
0x18000a8e4  jz      short loc_18000A952
0x18000a8e6  cmp     byte ptr [rsi+14h], 1
0x18000a8ea  jnz     short loc_18000A952
0x18000a8ec  mov     ecx, [rsi+4]
0x18000a8ef  lea     r8, aDDDD_0; "%d %d %d %d "
0x18000a8f6  mov     eax, [rsi+8]
0x18000a8f9  mov     edx, [rsi+10h]
0x18000a8fc  mov     r9d, [rsi+0Ch]
0x18000a900  sub     edx, eax
0x18000a902  mov     [rsp+0B8h+var_88], eax
0x18000a906  sub     r9d, ecx
0x18000a909  mov     [rsp+0B8h+var_90], ecx
0x18000a90d  lea     rcx, [rsp+0B8h+var_68]
0x18000a912  mov     [rsp+0B8h+var_98], edx
0x18000a916  lea     edx, [rdi+41h]
0x18000a919  call    OPSprintf
0x18000a91e  lea     rax, [rsp+0B8h+var_68]
0x18000a923  mov     r8, rdi
0x18000a926  inc     r8
0x18000a929  cmp     byte ptr [rax+r8], 0
0x18000a92e  jnz     short loc_18000A926
0x18000a930  lea     rdx, [rsp+0B8h+var_68]
0x18000a935  mov     rcx, rbp
0x18000a938  call    OPRawPortWrite
0x18000a93d  mov     r8d, 3
0x18000a943  lea     rdx, PSFRAG_msepsclip; "CB "
0x18000a94a  mov     rcx, rbp
0x18000a94d  call    OPRawPortWrite
0x18000a952  mov     ecx, [rbx+8]
0x18000a955  lea     r8, aDDDD_0; "%d %d %d %d "
0x18000a95c  mov     r10d, [rbx+0Ch]
0x18000a960  mov     edx, 40h ; '@'
0x18000a965  mov     eax, [rbx+14h]
0x18000a968  mov     r9d, [rbx]
0x18000a96b  sub     eax, [rbx+0Ch]
0x18000a96e  sub     r9d, [rbx+8]
0x18000a972  sar     ecx, 4
0x18000a975  sar     r10d, 4
0x18000a979  mov     [rsp+0B8h+var_88], r10d
0x18000a97e  mov     [rsp+0B8h+var_90], ecx
0x18000a982  lea     rcx, [rsp+0B8h+var_68]
0x18000a987  sar     eax, 4
0x18000a98a  sar     r9d, 4
0x18000a98e  mov     [rsp+0B8h+var_98], eax
0x18000a992  call    OPSprintf
0x18000a997  lea     rax, [rsp+0B8h+var_68]
0x18000a99c  inc     rdi
0x18000a99f  cmp     byte ptr [rax+rdi], 0
0x18000a9a3  jnz     short loc_18000A99C
0x18000a9a5  mov     r8d, edi
0x18000a9a8  lea     rdx, [rsp+0B8h+var_68]
0x18000a9ad  mov     rcx, rbp
0x18000a9b0  call    OPRawPortWrite
0x18000a9b5  mov     r8d, 2
0x18000a9bb  lea     rdx, PSFRAG_msepsrect; "B "
0x18000a9c2  mov     rcx, rbp
0x18000a9c5  call    OPRawPortWrite
0x18000a9ca  mov     eax, 1
0x18000a9cf  jmp     short loc_18000A9D3
0x18000a9d1  xor     eax, eax
0x18000a9d3  mov     rcx, [rsp+0B8h+var_28]
0x18000a9db  xor     rcx, rsp; StackCookie
0x18000a9de  call    __security_check_cookie
0x18000a9e3  mov     rbx, [rsp+0B8h+arg_18]
0x18000a9eb  add     rsp, 0A0h
0x18000a9f2  pop     rdi
0x18000a9f3  pop     rsi
0x18000a9f4  pop     rbp
0x18000a9f5  retn
```
