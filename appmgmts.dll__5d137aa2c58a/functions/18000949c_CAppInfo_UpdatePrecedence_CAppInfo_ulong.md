# CAppInfo::UpdatePrecedence(CAppInfo *,ulong)

- ea: `0x18000949c`
- end: `0x18000957c`
- name: `?UpdatePrecedence@CAppInfo@@AEAAJPEAV1@K@Z`
- size: `224`
- prototype: `__int64 __fastcall(CAppInfo *__hidden this, struct CAppInfo *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800084d4`
- `0x180008724`

## callees

- `0x18000949c`
- `0x18000c53c`
- `0x18001b1a0`

## pseudocode

```c
__int64 __fastcall CAppInfo::UpdatePrecedence(CAppInfo *this, struct CAppInfo *a2, unsigned int a3)
{
  unsigned int v3; // edi
  int v7; // eax
  signed int v8; // eax
  __int64 v9; // rcx
  signed int *v10; // rdx

  v3 = 0;
  if ( !*((_DWORD *)this + 108) )
  {
    v7 = *((_DWORD *)a2 + 108);
    if ( !v7 )
      v7 = *((_DWORD *)a2 + 53) & 0x400;
    *((_DWORD *)this + 108) = v7;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 392LL) )
  {
    v8 = CConflictList::AddConflict((CAppInfo *)((char *)this + 256), a2, this, a3, 1);
    v3 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v9 + 392) )
      {
        v10 = *(signed int **)(v9 + 400);
        if ( v10 )
          *v10 = v8;
      }
      *(_DWORD *)(v9 + 392) = 0;
    }
    else
    {
      *((_DWORD *)a2 + 74) = 1;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC2Bu, *((_QWORD *)a2 + 5), *((_QWORD *)a2 + 9), *((_QWORD *)this + 5), *((_QWORD *)this + 9), a3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000949c  push    rbx
0x18000949e  push    rbp
0x18000949f  push    rsi
0x1800094a0  push    rdi
0x1800094a1  sub     rsp, 48h
0x1800094a5  xor     edi, edi
0x1800094a7  mov     ebp, r8d
0x1800094aa  mov     rsi, rdx
0x1800094ad  mov     rbx, rcx
0x1800094b0  cmp     [rcx+1B0h], edi
0x1800094b6  jnz     short loc_1800094D3
0x1800094b8  mov     eax, [rdx+1B0h]
0x1800094be  test    eax, eax
0x1800094c0  jnz     short loc_1800094CD
0x1800094c2  mov     eax, [rdx+0D4h]
0x1800094c8  and     eax, 400h
0x1800094cd  mov     [rcx+1B0h], eax
0x1800094d3  mov     rax, [rcx+10h]
0x1800094d7  cmp     [rax+188h], edi
0x1800094dd  jz      loc_180009571
0x1800094e3  add     rcx, 100h; this
0x1800094ea  mov     [rsp+68h+var_48], 1; int
0x1800094f2  mov     r9d, ebp; unsigned int
0x1800094f5  mov     r8, rbx; struct CAppInfo *
0x1800094f8  call    ?AddConflict@CConflictList@@QEAAJPEAVCAppInfo@@0KJ@Z; CConflictList::AddConflict(CAppInfo *,CAppInfo *,ulong,long)
0x1800094fd  mov     edi, eax
0x1800094ff  test    eax, eax
0x180009501  jnz     short loc_180009542
0x180009503  mov     dword ptr [rsi+128h], 1
0x18000950d  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180009513  jz      short loc_180009571
0x180009515  mov     rcx, [rbx+48h]
0x180009519  mov     edx, 0C2Bh; unsigned int
0x18000951e  mov     r9, [rsi+48h]
0x180009522  mov     r8, [rsi+28h]
0x180009526  mov     [rsp+68h+var_38], ebp
0x18000952a  mov     [rsp+68h+var_40], rcx
0x18000952f  mov     rcx, [rbx+28h]
0x180009533  mov     qword ptr [rsp+68h+var_48], rcx
0x180009538  lea     ecx, [rax+4]; unsigned int
0x18000953b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009540  jmp     short loc_180009571
0x180009542  jle     short loc_18000954C
0x180009544  movzx   eax, ax
0x180009547  or      eax, 80070000h
0x18000954c  mov     rcx, [rbx+10h]
0x180009550  cmp     dword ptr [rcx+188h], 0
0x180009557  jz      short loc_180009567
0x180009559  mov     rdx, [rcx+190h]
0x180009560  test    rdx, rdx
0x180009563  jz      short loc_180009567
0x180009565  mov     [rdx], eax
0x180009567  mov     dword ptr [rcx+188h], 0
0x180009571  mov     eax, edi
0x180009573  add     rsp, 48h
0x180009577  pop     rdi
0x180009578  pop     rsi
0x180009579  pop     rbp
0x18000957a  pop     rbx
0x18000957b  retn
```
