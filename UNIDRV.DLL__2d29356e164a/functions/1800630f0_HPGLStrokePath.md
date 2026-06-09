# HPGLStrokePath

- ea: `0x1800630f0`
- end: `0x180063222`
- name: `HPGLStrokePath`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18003949c`
- `0x180045178`
- `0x1800487e0`
- `0x1800630f0`
- `0x180065588`
- `0x180066590`
- `0x180067284`
- `0x180069890`
- `0x180069a18`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800631f9`
- `KERNEL32!SetLastError` at `0x1800631f9`

## pseudocode

```c
__int64 __fastcall HPGLStrokePath(
        __int64 a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XFORMOBJ *a4,
        BRUSHOBJ *a5,
        __int64 a6,
        struct _LINEATTRS *a7,
        unsigned int a8)
{
  __int64 v8; // rbx
  unsigned int v12; // edi
  unsigned int v13; // r8d
  _OWORD v15[3]; // [rsp+40h] [rbp-88h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  memset(v15, 0, 44);
  if ( *(_QWORD *)(v8 + 8) )
  {
    v12 = 1;
    BChangeAndTrackObjectType(v8, 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v8, a8)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v8, a3, v13)
      || !(unsigned int)CreateHPGLPenBrush(v8, (__int64)v15, a6, a5, 0, 0, 0)
      || !(unsigned int)SelectLineAttrs((struct _DEVOBJ *)v8, a7, a4)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v8, a2, (struct _HPGLMARKER *)v15, 0)
      || !(unsigned int)HPGL_SelectTransparency(v8, 1, 0) )
    {
      return 0;
    }
    return v12;
  }
  else
  {
    SetLastError(0xDu);
    return 0;
  }
}

```

## disassembly

```asm
0x1800630f0  push    rbx
0x1800630f2  push    rbp
0x1800630f3  push    rsi
0x1800630f4  push    rdi
0x1800630f5  push    r12
0x1800630f7  push    r13
0x1800630f9  push    r14
0x1800630fb  push    r15
0x1800630fd  sub     rsp, 88h
0x180063104  mov     rax, cs:__security_cookie
0x18006310b  xor     rax, rsp
0x18006310e  mov     [rsp+0C8h+var_58], rax
0x180063113  mov     rbx, [rcx+10h]
0x180063117  xorps   xmm0, xmm0
0x18006311a  mov     r12, [rsp+0C8h+arg_20]
0x180063122  xor     eax, eax
0x180063124  mov     r13, [rsp+0C8h+arg_28]
0x18006312c  mov     rbp, r9
0x18006312f  mov     r14, [rsp+0C8h+arg_30]
0x180063137  mov     rsi, r8
0x18006313a  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x18006313f  mov     r15, rdx
0x180063142  movups  [rsp+0C8h+var_88], xmm0
0x180063147  movups  xmmword ptr [rsp+0C8h+var_78+0Ch], xmm0
0x18006314c  cmp     [rbx+8], rax
0x180063150  jz      loc_1800631F4
0x180063156  lea     edi, [rax+1]
0x180063159  mov     rcx, rbx
0x18006315c  mov     edx, edi
0x18006315e  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180063163  mov     edx, [rsp+0C8h+arg_38]; unsigned int
0x18006316a  mov     rcx, rbx; struct _DEVOBJ *
0x18006316d  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x180063172  test    eax, eax
0x180063174  jz      short loc_1800631EE
0x180063176  mov     rdx, rsi; struct _CLIPOBJ *
0x180063179  mov     rcx, rbx; struct _DEVOBJ *
0x18006317c  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x180063181  test    eax, eax
0x180063183  jz      short loc_1800631EE
0x180063185  mov     [rsp+0C8h+var_98], 0
0x18006318d  lea     rdx, [rsp+0C8h+var_88]
0x180063192  mov     [rsp+0C8h+var_A0], 0
0x18006319a  mov     r9, r12
0x18006319d  mov     r8, r13
0x1800631a0  mov     [rsp+0C8h+var_A8], 0
0x1800631a8  mov     rcx, rbx
0x1800631ab  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x1800631b0  test    eax, eax
0x1800631b2  jz      short loc_1800631EE
0x1800631b4  mov     r8, rbp; struct _XFORMOBJ *
0x1800631b7  mov     rdx, r14; struct _LINEATTRS *
0x1800631ba  mov     rcx, rbx; struct _DEVOBJ *
0x1800631bd  call    ?SelectLineAttrs@@YAHPEAU_DEVOBJ@@PEAU_LINEATTRS@@PEAU_XFORMOBJ@@@Z; SelectLineAttrs(_DEVOBJ *,_LINEATTRS *,_XFORMOBJ *)
0x1800631c2  test    eax, eax
0x1800631c4  jz      short loc_1800631EE
0x1800631c6  xor     r9d, r9d; struct _HPGLMARKER *
0x1800631c9  lea     r8, [rsp+0C8h+var_88]; struct _HPGLMARKER *
0x1800631ce  mov     rdx, r15; struct _PATHOBJ *
0x1800631d1  mov     rcx, rbx; struct _DEVOBJ *
0x1800631d4  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x1800631d9  test    eax, eax
0x1800631db  jz      short loc_1800631EE
0x1800631dd  xor     r8d, r8d
0x1800631e0  mov     edx, edi
0x1800631e2  mov     rcx, rbx
0x1800631e5  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x1800631ea  test    eax, eax
0x1800631ec  jnz     short loc_1800631F0
0x1800631ee  xor     edi, edi
0x1800631f0  mov     eax, edi
0x1800631f2  jmp     short loc_180063201
0x1800631f4  mov     ecx, 0Dh; dwErrCode
0x1800631f9  call    cs:__imp_SetLastError
0x1800631ff  xor     eax, eax
0x180063201  mov     rcx, [rsp+0C8h+var_58]
0x180063206  xor     rcx, rsp; StackCookie
0x180063209  call    __security_check_cookie
0x18006320e  add     rsp, 88h
0x180063215  pop     r15
0x180063217  pop     r14
0x180063219  pop     r13
0x18006321b  pop     r12
0x18006321d  pop     rdi
0x18006321e  pop     rsi
0x18006321f  pop     rbp
0x180063220  pop     rbx
0x180063221  retn
```
