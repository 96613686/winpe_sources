# HPGLStrokeAndFillPath

- ea: `0x180064560`
- end: `0x180064715`
- name: `HPGLStrokeAndFillPath`
- size: `437`
- prototype: `__int64 __fastcall(__int64, struct _PATHOBJ *, struct _CLIPOBJ *, struct _XFORMOBJ *, __int64, struct _LINEATTRS *, __int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180039f24`
- `0x1800465b4`
- `0x180049d00`
- `0x180064560`
- `0x180066cbc`
- `0x180067d58`
- `0x180068a8c`
- `0x18006b184`
- `0x18006b310`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800646e6`
- `KERNEL32!SetLastError` at `0x1800646e6`

## pseudocode

```c
__int64 __fastcall HPGLStrokeAndFillPath(
        __int64 a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XFORMOBJ *a4,
        BRUSHOBJ *a5,
        struct _LINEATTRS *a6,
        BRUSHOBJ *a7,
        __int64 a8,
        unsigned int a9,
        unsigned int a10)
{
  __int64 v10; // rbx
  __int64 v13; // r15
  unsigned int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  __int64 v18; // r8
  _OWORD v21[3]; // [rsp+58h] [rbp-69h] BYREF
  _OWORD v22[3]; // [rsp+88h] [rbp-39h] BYREF

  v10 = *(_QWORD *)(a1 + 16);
  memset(v21, 0, 44);
  memset(v22, 0, 44);
  v13 = *(_QWORD *)(v10 + 8);
  if ( v13 )
  {
    v14 = 1;
    BChangeAndTrackObjectType(v10, 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v10, a9)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v10, a3)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v21, a8, a5, 0, 0, 1)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v22, a8, a7, a10, 1, 0)
      || !(unsigned int)SelectLineAttrs((struct _DEVOBJ *)v10, a6, a4)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v10, a2, (struct _HPGLMARKER *)v21, (struct _HPGLMARKER *)v22)
      || !(unsigned int)HPGL_SelectTransparency(v10, 1, 0) )
    {
      v14 = 0;
    }
    if ( DWORD2(v21[0]) )
    {
      v15 = *(_QWORD *)(v13 + 4408);
      v16 = (unsigned int)(DWORD2(v21[0]) - 1);
      v17 = (_DWORD *)(v15 + 4);
      if ( !*(_DWORD *)(v15 + 8) )
        v17 = *(_DWORD **)(v13 + 4408);
      if ( (unsigned int)v16 < *v17 )
      {
        v18 = *(_QWORD *)(v15 + 16);
        if ( v18 )
          *(_DWORD *)(v18 + 36 * v16 + 32) = 0;
      }
    }
    return v14;
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
0x180064560  push    rbp
0x180064562  push    rbx
0x180064563  push    rsi
0x180064564  push    rdi
0x180064565  push    r12
0x180064567  push    r13
0x180064569  push    r14
0x18006456b  push    r15
0x18006456d  lea     rbp, [rsp-7]
0x180064572  sub     rsp, 0C8h
0x180064579  mov     rax, cs:__security_cookie
0x180064580  xor     rax, rsp
0x180064583  mov     [rbp+3Fh+var_48], rax
0x180064587  mov     rax, [rbp+3Fh+arg_28]
0x18006458b  xorps   xmm0, xmm0
0x18006458e  mov     rbx, [rcx+10h]
0x180064592  xorps   xmm1, xmm1
0x180064595  mov     r13, [rbp+3Fh+arg_20]
0x180064599  mov     r12, r9
0x18006459c  mov     rsi, [rbp+3Fh+arg_38]
0x1800645a3  mov     r14, r8
0x1800645a6  mov     [rbp+3Fh+var_B8], rax
0x1800645aa  mov     rax, [rbp+3Fh+arg_30]
0x1800645ae  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x1800645b2  mov     [rsp+100h+var_C0], rax
0x1800645b7  xor     eax, eax
0x1800645b9  movups  xmmword ptr [rbp+3Fh+var_68], xmm1
0x1800645bd  mov     [rbp+3Fh+var_B0], rdx
0x1800645c1  movups  [rbp+3Fh+var_A8], xmm0
0x1800645c5  movups  xmmword ptr [rbp+3Fh+var_98+0Ch], xmm0
0x1800645c9  movups  [rbp+3Fh+var_78], xmm1
0x1800645cd  movups  xmmword ptr [rbp+3Fh+var_68+0Ch], xmm1
0x1800645d1  mov     r15, [rbx+8]
0x1800645d5  test    r15, r15
0x1800645d8  jz      loc_1800646E1
0x1800645de  lea     edi, [rax+1]
0x1800645e1  mov     rcx, rbx
0x1800645e4  mov     edx, edi
0x1800645e6  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x1800645eb  mov     edx, [rbp+3Fh+arg_40]; unsigned int
0x1800645f1  mov     rcx, rbx; struct _DEVOBJ *
0x1800645f4  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x1800645f9  test    eax, eax
0x1800645fb  jz      loc_1800646A4
0x180064601  mov     rdx, r14; struct _CLIPOBJ *
0x180064604  mov     rcx, rbx; struct _DEVOBJ *
0x180064607  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x18006460c  xor     r14d, r14d
0x18006460f  test    eax, eax
0x180064611  jz      loc_1800646A7
0x180064617  mov     [rsp+100h+var_D0], edi
0x18006461b  lea     rdx, [rbp+3Fh+var_A8]
0x18006461f  mov     [rsp+100h+var_D8], r14d
0x180064624  mov     r9, r13
0x180064627  mov     r8, rsi
0x18006462a  mov     [rsp+100h+var_E0], r14d
0x18006462f  mov     rcx, rbx
0x180064632  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180064637  test    eax, eax
0x180064639  jz      short loc_1800646A7
0x18006463b  mov     eax, [rbp+3Fh+arg_48]
0x180064641  lea     rdx, [rbp+3Fh+var_78]
0x180064645  mov     r9, [rsp+100h+var_C0]
0x18006464a  mov     r8, rsi
0x18006464d  mov     [rsp+100h+var_D0], r14d
0x180064652  mov     rcx, rbx
0x180064655  mov     [rsp+100h+var_D8], edi
0x180064659  mov     [rsp+100h+var_E0], eax
0x18006465d  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180064662  test    eax, eax
0x180064664  jz      short loc_1800646A7
0x180064666  mov     rdx, [rbp+3Fh+var_B8]; struct _LINEATTRS *
0x18006466a  mov     r8, r12; struct _XFORMOBJ *
0x18006466d  mov     rcx, rbx; struct _DEVOBJ *
0x180064670  call    ?SelectLineAttrs@@YAHPEAU_DEVOBJ@@PEAU_LINEATTRS@@PEAU_XFORMOBJ@@@Z; SelectLineAttrs(_DEVOBJ *,_LINEATTRS *,_XFORMOBJ *)
0x180064675  test    eax, eax
0x180064677  jz      short loc_1800646A7
0x180064679  mov     rdx, [rbp+3Fh+var_B0]; struct _PATHOBJ *
0x18006467d  lea     r9, [rbp+3Fh+var_78]; struct _HPGLMARKER *
0x180064681  lea     r8, [rbp+3Fh+var_A8]; struct _HPGLMARKER *
0x180064685  mov     rcx, rbx; struct _DEVOBJ *
0x180064688  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x18006468d  test    eax, eax
0x18006468f  jz      short loc_1800646A7
0x180064691  xor     r8d, r8d
0x180064694  mov     edx, edi
0x180064696  mov     rcx, rbx
0x180064699  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x18006469e  test    eax, eax
0x1800646a0  jz      short loc_1800646A7
0x1800646a2  jmp     short loc_1800646AA
0x1800646a4  xor     r14d, r14d
0x1800646a7  mov     edi, r14d
0x1800646aa  mov     ecx, dword ptr [rbp+3Fh+var_A8+8]
0x1800646ad  test    ecx, ecx
0x1800646af  jz      short loc_1800646DD
0x1800646b1  mov     rax, [r15+1138h]
0x1800646b8  lea     edx, [rcx-1]
0x1800646bb  cmp     [rax+8], r14d
0x1800646bf  lea     rcx, [rax+4]
0x1800646c3  cmovz   rcx, rax
0x1800646c7  cmp     edx, [rcx]
0x1800646c9  jnb     short loc_1800646DD
0x1800646cb  mov     r8, [rax+10h]
0x1800646cf  test    r8, r8
0x1800646d2  jz      short loc_1800646DD
0x1800646d4  lea     rdx, [rdx+rdx*8]
0x1800646d8  mov     [r8+rdx*4+20h], r14d
0x1800646dd  mov     eax, edi
0x1800646df  jmp     short loc_1800646F4
0x1800646e1  mov     ecx, 0Dh; dwErrCode
0x1800646e6  call    cs:__imp_SetLastError
0x1800646ed  nop     dword ptr [rax+rax+00h]
0x1800646f2  xor     eax, eax
0x1800646f4  mov     rcx, [rbp+3Fh+var_48]
0x1800646f8  xor     rcx, rsp; StackCookie
0x1800646fb  call    __security_check_cookie
0x180064700  add     rsp, 0C8h
0x180064707  pop     r15
0x180064709  pop     r14
0x18006470b  pop     r13
0x18006470d  pop     r12
0x18006470f  pop     rdi
0x180064710  pop     rsi
0x180064711  pop     rbx
0x180064712  pop     rbp
0x180064713  retn
```
