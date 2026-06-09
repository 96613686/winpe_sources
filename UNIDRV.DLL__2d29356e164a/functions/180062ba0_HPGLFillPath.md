# HPGLFillPath

- ea: `0x180062ba0`
- end: `0x180062cc2`
- name: `HPGLFillPath`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18003949c`
- `0x180045178`
- `0x1800487e0`
- `0x180062ba0`
- `0x180065588`
- `0x180066590`
- `0x180067284`
- `0x180069890`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180062c9d`
- `KERNEL32!SetLastError` at `0x180062c9d`

## pseudocode

```c
__int64 __fastcall HPGLFillPath(
        __int64 a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        BRUSHOBJ *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v10; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  _OWORD v14[3]; // [rsp+40h] [rbp-78h] BYREF

  memset(v14, 0, 44);
  if ( a1 && (v10 = *(_QWORD *)(a1 + 16), *(_QWORD *)(v10 + 8)) )
  {
    if ( a3 && a3->iDComplexity == 3 )
      return 0;
    v11 = 1;
    BChangeAndTrackObjectType(*(_QWORD *)(a1 + 16), 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v10, a6)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v10, a3, v12)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v14, a5, a4, a7, 1, 0)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v10, a2, 0, (struct _HPGLMARKER *)v14)
      || !(unsigned int)HPGL_SelectTransparency(v10, 1, 0) )
    {
      return 0;
    }
    return v11;
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
0x180062ba0  push    rbx
0x180062ba2  push    rbp
0x180062ba3  push    rsi
0x180062ba4  push    rdi
0x180062ba5  push    r14
0x180062ba7  push    r15
0x180062ba9  sub     rsp, 88h
0x180062bb0  mov     rax, cs:__security_cookie
0x180062bb7  xor     rax, rsp
0x180062bba  mov     [rsp+0B8h+var_48], rax
0x180062bbf  mov     r15, [rsp+0B8h+arg_20]
0x180062bc7  xorps   xmm0, xmm0
0x180062bca  xor     eax, eax
0x180062bcc  mov     r14, r9
0x180062bcf  mov     rsi, r8
0x180062bd2  mov     rbp, rdx
0x180062bd5  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x180062bda  movups  xmmword ptr [rsp+0B8h+var_68+0Ch], xmm0
0x180062bdf  movups  [rsp+0B8h+var_78], xmm0
0x180062be4  test    rcx, rcx
0x180062be7  jz      loc_180062C98
0x180062bed  mov     rdi, [rcx+10h]
0x180062bf1  cmp     [rdi+8], rax
0x180062bf5  jz      loc_180062C98
0x180062bfb  test    r8, r8
0x180062bfe  jz      short loc_180062C0B
0x180062c00  cmp     byte ptr [r8+14h], 3
0x180062c05  jz      loc_180062C92
0x180062c0b  mov     ebx, 1
0x180062c10  mov     rcx, rdi
0x180062c13  mov     edx, ebx
0x180062c15  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180062c1a  mov     edx, [rsp+0B8h+arg_28]; unsigned int
0x180062c21  mov     rcx, rdi; struct _DEVOBJ *
0x180062c24  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x180062c29  test    eax, eax
0x180062c2b  jz      short loc_180062C92
0x180062c2d  mov     rdx, rsi; struct _CLIPOBJ *
0x180062c30  mov     rcx, rdi; struct _DEVOBJ *
0x180062c33  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x180062c38  test    eax, eax
0x180062c3a  jz      short loc_180062C92
0x180062c3c  mov     eax, [rsp+0B8h+arg_30]
0x180062c43  lea     rdx, [rsp+0B8h+var_78]
0x180062c48  mov     [rsp+0B8h+var_88], 0
0x180062c50  mov     r9, r14
0x180062c53  mov     [rsp+0B8h+var_90], ebx
0x180062c57  mov     r8, r15
0x180062c5a  mov     rcx, rdi
0x180062c5d  mov     [rsp+0B8h+var_98], eax
0x180062c61  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180062c66  test    eax, eax
0x180062c68  jz      short loc_180062C92
0x180062c6a  lea     r9, [rsp+0B8h+var_78]; struct _HPGLMARKER *
0x180062c6f  xor     r8d, r8d; struct _HPGLMARKER *
0x180062c72  mov     rdx, rbp; struct _PATHOBJ *
0x180062c75  mov     rcx, rdi; struct _DEVOBJ *
0x180062c78  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x180062c7d  test    eax, eax
0x180062c7f  jz      short loc_180062C92
0x180062c81  xor     r8d, r8d
0x180062c84  mov     edx, ebx
0x180062c86  mov     rcx, rdi
0x180062c89  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x180062c8e  test    eax, eax
0x180062c90  jnz     short loc_180062C94
0x180062c92  xor     ebx, ebx
0x180062c94  mov     eax, ebx
0x180062c96  jmp     short loc_180062CA5
0x180062c98  mov     ecx, 0Dh; dwErrCode
0x180062c9d  call    cs:__imp_SetLastError
0x180062ca3  xor     eax, eax
0x180062ca5  mov     rcx, [rsp+0B8h+var_48]
0x180062caa  xor     rcx, rsp; StackCookie
0x180062cad  call    __security_check_cookie
0x180062cb2  add     rsp, 88h
0x180062cb9  pop     r15
0x180062cbb  pop     r14
0x180062cbd  pop     rdi
0x180062cbe  pop     rsi
0x180062cbf  pop     rbp
0x180062cc0  pop     rbx
0x180062cc1  retn
```
