# BDoMSEpsHackRect

- ea: `0x18000a488`
- end: `0x18000a656`
- name: `BDoMSEpsHackRect`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a660`
- `0x18000a8a0`
- `0x18000abb0`

## callees

- `0x180001ee0`
- `0x18000a488`
- `0x180016940`
- `0x180016e24`
- `0x180016edc`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18000a4cb`
- `GDI32!PATHOBJ_bEnum` at `0x18000a4cb`
- `GDI32!PATHOBJ_vEnumStart` at `0x18000a4bd`
- `GDI32!PATHOBJ_vEnumStart` at `0x18000a4bd`

## pseudocode

```c
__int64 __fastcall BDoMSEpsHackRect(__int64 a1, __int64 a2, PATHOBJ *a3)
{
  POINTFIX *pptfx; // rbx
  __int64 v7; // rdi
  __int64 v8; // r8
  PATHDATA ppd; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v11[64]; // [rsp+50h] [rbp-68h] BYREF

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
  OPSendOperator(a1, 15);
  v7 = -1;
  if ( a2 && *(_BYTE *)(a2 + 20) == 1 )
  {
    OPSprintf(
      v11,
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
    OPRawPortWrite(a1, "CB ", 3);
  }
  OPSprintf(
    v11,
    64,
    "%d %d %d %d ",
    (pptfx->x - pptfx[1].x) >> 4,
    (pptfx[2].y - pptfx[1].y) >> 4,
    pptfx[1].x >> 4,
    pptfx[1].y >> 4);
  do
    ++v7;
  while ( v11[v7] );
  OPRawPortWrite(a1, v11, (unsigned int)v7);
  OPRawPortWrite(a1, "B ", 2);
  return 1;
}

```

## disassembly

```asm
0x18000a488  mov     [rsp+arg_18], rbx
0x18000a48d  push    rbp
0x18000a48e  push    rsi
0x18000a48f  push    rdi
0x18000a490  sub     rsp, 0A0h
0x18000a497  mov     rax, cs:__security_cookie
0x18000a49e  xor     rax, rsp
0x18000a4a1  mov     [rsp+0B8h+var_28], rax
0x18000a4a9  mov     rbp, rcx
0x18000a4ac  xorps   xmm0, xmm0
0x18000a4af  mov     rcx, r8; ppo
0x18000a4b2  mov     rbx, r8
0x18000a4b5  movups  xmmword ptr [rsp+0B8h+ppd.flags], xmm0
0x18000a4ba  mov     rsi, rdx
0x18000a4bd  call    cs:__imp_PATHOBJ_vEnumStart
0x18000a4c3  lea     rdx, [rsp+0B8h+ppd]; ppd
0x18000a4c8  mov     rcx, rbx; ppo
0x18000a4cb  call    cs:__imp_PATHOBJ_bEnum
0x18000a4d1  test    eax, eax
0x18000a4d3  jnz     loc_18000A631
0x18000a4d9  cmp     [rsp+0B8h+ppd.count], 4
0x18000a4de  jnz     loc_18000A631
0x18000a4e4  mov     eax, [rsp+0B8h+ppd.flags]
0x18000a4e8  and     eax, 19h
0x18000a4eb  cmp     al, 9
0x18000a4ed  jnz     loc_18000A631
0x18000a4f3  mov     rbx, [rsp+0B8h+ppd.pptfx]
0x18000a4f8  test    rbx, rbx
0x18000a4fb  jz      loc_18000A631
0x18000a501  mov     eax, [rbx+0Ch]
0x18000a504  cmp     [rbx+4], eax
0x18000a507  jnz     loc_18000A631
0x18000a50d  mov     eax, [rbx+10h]
0x18000a510  cmp     [rbx+8], eax
0x18000a513  jnz     loc_18000A631
0x18000a519  mov     eax, [rbx+1Ch]
0x18000a51c  cmp     [rbx+14h], eax
0x18000a51f  jnz     loc_18000A631
0x18000a525  mov     eax, [rbx]
0x18000a527  cmp     [rbx+18h], eax
0x18000a52a  jnz     loc_18000A631
0x18000a530  mov     edx, 0Fh
0x18000a535  mov     rcx, rbp
0x18000a538  call    OPSendOperator
0x18000a53d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a541  test    rsi, rsi
0x18000a544  jz      short loc_18000A5B2
0x18000a546  cmp     byte ptr [rsi+14h], 1
0x18000a54a  jnz     short loc_18000A5B2
0x18000a54c  mov     ecx, [rsi+4]
0x18000a54f  lea     r8, aDDDD_0; "%d %d %d %d "
0x18000a556  mov     eax, [rsi+8]
0x18000a559  mov     edx, [rsi+10h]
0x18000a55c  mov     r9d, [rsi+0Ch]
0x18000a560  sub     edx, eax
0x18000a562  mov     [rsp+0B8h+var_88], eax
0x18000a566  sub     r9d, ecx
0x18000a569  mov     [rsp+0B8h+var_90], ecx
0x18000a56d  lea     rcx, [rsp+0B8h+var_68]
0x18000a572  mov     [rsp+0B8h+var_98], edx
0x18000a576  lea     edx, [rdi+41h]
0x18000a579  call    OPSprintf
0x18000a57e  lea     rax, [rsp+0B8h+var_68]
0x18000a583  mov     r8, rdi
0x18000a586  inc     r8
0x18000a589  cmp     byte ptr [rax+r8], 0
0x18000a58e  jnz     short loc_18000A586
0x18000a590  lea     rdx, [rsp+0B8h+var_68]
0x18000a595  mov     rcx, rbp
0x18000a598  call    OPRawPortWrite
0x18000a59d  mov     r8d, 3
0x18000a5a3  lea     rdx, PSFRAG_msepsclip; "CB "
0x18000a5aa  mov     rcx, rbp
0x18000a5ad  call    OPRawPortWrite
0x18000a5b2  mov     ecx, [rbx+8]
0x18000a5b5  lea     r8, aDDDD_0; "%d %d %d %d "
0x18000a5bc  mov     r10d, [rbx+0Ch]
0x18000a5c0  mov     edx, 40h ; '@'
0x18000a5c5  mov     eax, [rbx+14h]
0x18000a5c8  mov     r9d, [rbx]
0x18000a5cb  sub     eax, [rbx+0Ch]
0x18000a5ce  sub     r9d, [rbx+8]
0x18000a5d2  sar     ecx, 4
0x18000a5d5  sar     r10d, 4
0x18000a5d9  mov     [rsp+0B8h+var_88], r10d
0x18000a5de  mov     [rsp+0B8h+var_90], ecx
0x18000a5e2  lea     rcx, [rsp+0B8h+var_68]
0x18000a5e7  sar     eax, 4
0x18000a5ea  sar     r9d, 4
0x18000a5ee  mov     [rsp+0B8h+var_98], eax
0x18000a5f2  call    OPSprintf
0x18000a5f7  lea     rax, [rsp+0B8h+var_68]
0x18000a5fc  inc     rdi
0x18000a5ff  cmp     byte ptr [rax+rdi], 0
0x18000a603  jnz     short loc_18000A5FC
0x18000a605  mov     r8d, edi
0x18000a608  lea     rdx, [rsp+0B8h+var_68]
0x18000a60d  mov     rcx, rbp
0x18000a610  call    OPRawPortWrite
0x18000a615  mov     r8d, 2
0x18000a61b  lea     rdx, PSFRAG_msepsrect; "B "
0x18000a622  mov     rcx, rbp
0x18000a625  call    OPRawPortWrite
0x18000a62a  mov     eax, 1
0x18000a62f  jmp     short loc_18000A633
0x18000a631  xor     eax, eax
0x18000a633  mov     rcx, [rsp+0B8h+var_28]
0x18000a63b  xor     rcx, rsp; StackCookie
0x18000a63e  call    __security_check_cookie
0x18000a643  mov     rbx, [rsp+0B8h+arg_18]
0x18000a64b  add     rsp, 0A0h
0x18000a652  pop     rdi
0x18000a653  pop     rsi
0x18000a654  pop     rbp
0x18000a655  retn
```
