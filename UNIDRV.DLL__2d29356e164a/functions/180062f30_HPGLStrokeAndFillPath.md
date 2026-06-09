# HPGLStrokeAndFillPath

- ea: `0x180062f30`
- end: `0x1800630de`
- name: `HPGLStrokeAndFillPath`
- size: `430`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18003949c`
- `0x180045178`
- `0x1800487e0`
- `0x180062f30`
- `0x180065588`
- `0x180066590`
- `0x180067284`
- `0x180069890`
- `0x180069a18`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800630b6`
- `KERNEL32!SetLastError` at `0x1800630b6`

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
  unsigned int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  __int64 v19; // r8
  _OWORD v22[3]; // [rsp+58h] [rbp-69h] BYREF
  _OWORD v23[3]; // [rsp+88h] [rbp-39h] BYREF

  v10 = *(_QWORD *)(a1 + 16);
  memset(v22, 0, 44);
  memset(v23, 0, 44);
  v13 = *(_QWORD *)(v10 + 8);
  if ( v13 )
  {
    v14 = 1;
    BChangeAndTrackObjectType(v10, 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v10, a9)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v10, a3, v15)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v22, a8, a5, 0, 0, 1)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v23, a8, a7, a10, 1, 0)
      || !(unsigned int)SelectLineAttrs((struct _DEVOBJ *)v10, a6, a4)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v10, a2, (struct _HPGLMARKER *)v22, (struct _HPGLMARKER *)v23)
      || !(unsigned int)HPGL_SelectTransparency(v10, 1, 0) )
    {
      v14 = 0;
    }
    if ( DWORD2(v22[0]) )
    {
      v16 = *(_QWORD *)(v13 + 4408);
      v17 = (unsigned int)(DWORD2(v22[0]) - 1);
      v18 = (_DWORD *)(v16 + 4);
      if ( !*(_DWORD *)(v16 + 8) )
        v18 = *(_DWORD **)(v13 + 4408);
      if ( (unsigned int)v17 < *v18 )
      {
        v19 = *(_QWORD *)(v16 + 16);
        if ( v19 )
          *(_DWORD *)(v19 + 36 * v17 + 32) = 0;
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
0x180062f30  push    rbp
0x180062f32  push    rbx
0x180062f33  push    rsi
0x180062f34  push    rdi
0x180062f35  push    r12
0x180062f37  push    r13
0x180062f39  push    r14
0x180062f3b  push    r15
0x180062f3d  lea     rbp, [rsp-7]
0x180062f42  sub     rsp, 0C8h
0x180062f49  mov     rax, cs:__security_cookie
0x180062f50  xor     rax, rsp
0x180062f53  mov     [rbp+3Fh+var_48], rax
0x180062f57  mov     rax, [rbp+3Fh+arg_28]
0x180062f5b  xorps   xmm0, xmm0
0x180062f5e  mov     rbx, [rcx+10h]
0x180062f62  xorps   xmm1, xmm1
0x180062f65  mov     r13, [rbp+3Fh+arg_20]
0x180062f69  mov     r12, r9
0x180062f6c  mov     rsi, [rbp+3Fh+arg_38]
0x180062f73  mov     r14, r8
0x180062f76  mov     [rbp+3Fh+var_B8], rax
0x180062f7a  mov     rax, [rbp+3Fh+arg_30]
0x180062f7e  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x180062f82  mov     [rsp+100h+var_C0], rax
0x180062f87  xor     eax, eax
0x180062f89  movups  xmmword ptr [rbp+3Fh+var_68], xmm1
0x180062f8d  mov     [rbp+3Fh+var_B0], rdx
0x180062f91  movups  [rbp+3Fh+var_A8], xmm0
0x180062f95  movups  xmmword ptr [rbp+3Fh+var_98+0Ch], xmm0
0x180062f99  movups  [rbp+3Fh+var_78], xmm1
0x180062f9d  movups  xmmword ptr [rbp+3Fh+var_68+0Ch], xmm1
0x180062fa1  mov     r15, [rbx+8]
0x180062fa5  test    r15, r15
0x180062fa8  jz      loc_1800630B1
0x180062fae  lea     edi, [rax+1]
0x180062fb1  mov     rcx, rbx
0x180062fb4  mov     edx, edi
0x180062fb6  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180062fbb  mov     edx, [rbp+3Fh+arg_40]; unsigned int
0x180062fc1  mov     rcx, rbx; struct _DEVOBJ *
0x180062fc4  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x180062fc9  test    eax, eax
0x180062fcb  jz      loc_180063074
0x180062fd1  mov     rdx, r14; struct _CLIPOBJ *
0x180062fd4  mov     rcx, rbx; struct _DEVOBJ *
0x180062fd7  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x180062fdc  xor     r14d, r14d
0x180062fdf  test    eax, eax
0x180062fe1  jz      loc_180063077
0x180062fe7  mov     [rsp+100h+var_D0], edi
0x180062feb  lea     rdx, [rbp+3Fh+var_A8]
0x180062fef  mov     [rsp+100h+var_D8], r14d
0x180062ff4  mov     r9, r13
0x180062ff7  mov     r8, rsi
0x180062ffa  mov     [rsp+100h+var_E0], r14d
0x180062fff  mov     rcx, rbx
0x180063002  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180063007  test    eax, eax
0x180063009  jz      short loc_180063077
0x18006300b  mov     eax, [rbp+3Fh+arg_48]
0x180063011  lea     rdx, [rbp+3Fh+var_78]
0x180063015  mov     r9, [rsp+100h+var_C0]
0x18006301a  mov     r8, rsi
0x18006301d  mov     [rsp+100h+var_D0], r14d
0x180063022  mov     rcx, rbx
0x180063025  mov     [rsp+100h+var_D8], edi
0x180063029  mov     [rsp+100h+var_E0], eax
0x18006302d  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180063032  test    eax, eax
0x180063034  jz      short loc_180063077
0x180063036  mov     rdx, [rbp+3Fh+var_B8]; struct _LINEATTRS *
0x18006303a  mov     r8, r12; struct _XFORMOBJ *
0x18006303d  mov     rcx, rbx; struct _DEVOBJ *
0x180063040  call    ?SelectLineAttrs@@YAHPEAU_DEVOBJ@@PEAU_LINEATTRS@@PEAU_XFORMOBJ@@@Z; SelectLineAttrs(_DEVOBJ *,_LINEATTRS *,_XFORMOBJ *)
0x180063045  test    eax, eax
0x180063047  jz      short loc_180063077
0x180063049  mov     rdx, [rbp+3Fh+var_B0]; struct _PATHOBJ *
0x18006304d  lea     r9, [rbp+3Fh+var_78]; struct _HPGLMARKER *
0x180063051  lea     r8, [rbp+3Fh+var_A8]; struct _HPGLMARKER *
0x180063055  mov     rcx, rbx; struct _DEVOBJ *
0x180063058  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x18006305d  test    eax, eax
0x18006305f  jz      short loc_180063077
0x180063061  xor     r8d, r8d
0x180063064  mov     edx, edi
0x180063066  mov     rcx, rbx
0x180063069  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x18006306e  test    eax, eax
0x180063070  jz      short loc_180063077
0x180063072  jmp     short loc_18006307A
0x180063074  xor     r14d, r14d
0x180063077  mov     edi, r14d
0x18006307a  mov     ecx, dword ptr [rbp+3Fh+var_A8+8]
0x18006307d  test    ecx, ecx
0x18006307f  jz      short loc_1800630AD
0x180063081  mov     rax, [r15+1138h]
0x180063088  lea     edx, [rcx-1]
0x18006308b  cmp     [rax+8], r14d
0x18006308f  lea     rcx, [rax+4]
0x180063093  cmovz   rcx, rax
0x180063097  cmp     edx, [rcx]
0x180063099  jnb     short loc_1800630AD
0x18006309b  mov     r8, [rax+10h]
0x18006309f  test    r8, r8
0x1800630a2  jz      short loc_1800630AD
0x1800630a4  lea     rdx, [rdx+rdx*8]
0x1800630a8  mov     [r8+rdx*4+20h], r14d
0x1800630ad  mov     eax, edi
0x1800630af  jmp     short loc_1800630BE
0x1800630b1  mov     ecx, 0Dh; dwErrCode
0x1800630b6  call    cs:__imp_SetLastError
0x1800630bc  xor     eax, eax
0x1800630be  mov     rcx, [rbp+3Fh+var_48]
0x1800630c2  xor     rcx, rsp; StackCookie
0x1800630c5  call    __security_check_cookie
0x1800630ca  add     rsp, 0C8h
0x1800630d1  pop     r15
0x1800630d3  pop     r14
0x1800630d5  pop     r13
0x1800630d7  pop     r12
0x1800630d9  pop     rdi
0x1800630da  pop     rsi
0x1800630db  pop     rbx
0x1800630dc  pop     rbp
0x1800630dd  retn
```
