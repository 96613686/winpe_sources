# HPGLFillPath

- ea: `0x1800641a0`
- end: `0x1800642c9`
- name: `HPGLFillPath`
- size: `297`
- prototype: `__int64 __fastcall(__int64, struct _PATHOBJ *, struct _CLIPOBJ *, __int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180039f24`
- `0x1800465b4`
- `0x180049d00`
- `0x1800641a0`
- `0x180066cbc`
- `0x180067d58`
- `0x180068a8c`
- `0x18006b184`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18006429d`
- `KERNEL32!SetLastError` at `0x18006429d`

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
  _OWORD v13[3]; // [rsp+40h] [rbp-78h] BYREF

  memset(v13, 0, 44);
  if ( a1 && (v10 = *(_QWORD *)(a1 + 16), *(_QWORD *)(v10 + 8)) )
  {
    if ( a3 && a3->iDComplexity == 3 )
      return 0;
    v11 = 1;
    BChangeAndTrackObjectType(*(_QWORD *)(a1 + 16), 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v10, a6)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v10, a3)
      || !(unsigned int)CreateHPGLPenBrush(v10, (__int64)v13, a5, a4, a7, 1, 0)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v10, a2, 0, (struct _HPGLMARKER *)v13)
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
0x1800641a0  push    rbx
0x1800641a2  push    rbp
0x1800641a3  push    rsi
0x1800641a4  push    rdi
0x1800641a5  push    r14
0x1800641a7  push    r15
0x1800641a9  sub     rsp, 88h
0x1800641b0  mov     rax, cs:__security_cookie
0x1800641b7  xor     rax, rsp
0x1800641ba  mov     [rsp+0B8h+var_48], rax
0x1800641bf  mov     r15, [rsp+0B8h+arg_20]
0x1800641c7  xorps   xmm0, xmm0
0x1800641ca  xor     eax, eax
0x1800641cc  mov     r14, r9
0x1800641cf  mov     rsi, r8
0x1800641d2  mov     rbp, rdx
0x1800641d5  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x1800641da  movups  xmmword ptr [rsp+0B8h+var_68+0Ch], xmm0
0x1800641df  movups  [rsp+0B8h+var_78], xmm0
0x1800641e4  test    rcx, rcx
0x1800641e7  jz      loc_180064298
0x1800641ed  mov     rdi, [rcx+10h]
0x1800641f1  cmp     [rdi+8], rax
0x1800641f5  jz      loc_180064298
0x1800641fb  test    r8, r8
0x1800641fe  jz      short loc_18006420B
0x180064200  cmp     byte ptr [r8+14h], 3
0x180064205  jz      loc_180064292
0x18006420b  mov     ebx, 1
0x180064210  mov     rcx, rdi
0x180064213  mov     edx, ebx
0x180064215  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x18006421a  mov     edx, [rsp+0B8h+arg_28]; unsigned int
0x180064221  mov     rcx, rdi; struct _DEVOBJ *
0x180064224  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x180064229  test    eax, eax
0x18006422b  jz      short loc_180064292
0x18006422d  mov     rdx, rsi; struct _CLIPOBJ *
0x180064230  mov     rcx, rdi; struct _DEVOBJ *
0x180064233  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x180064238  test    eax, eax
0x18006423a  jz      short loc_180064292
0x18006423c  mov     eax, [rsp+0B8h+arg_30]
0x180064243  lea     rdx, [rsp+0B8h+var_78]
0x180064248  mov     [rsp+0B8h+var_88], 0
0x180064250  mov     r9, r14
0x180064253  mov     [rsp+0B8h+var_90], ebx
0x180064257  mov     r8, r15
0x18006425a  mov     rcx, rdi
0x18006425d  mov     [rsp+0B8h+var_98], eax
0x180064261  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x180064266  test    eax, eax
0x180064268  jz      short loc_180064292
0x18006426a  lea     r9, [rsp+0B8h+var_78]; struct _HPGLMARKER *
0x18006426f  xor     r8d, r8d; struct _HPGLMARKER *
0x180064272  mov     rdx, rbp; struct _PATHOBJ *
0x180064275  mov     rcx, rdi; struct _DEVOBJ *
0x180064278  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x18006427d  test    eax, eax
0x18006427f  jz      short loc_180064292
0x180064281  xor     r8d, r8d
0x180064284  mov     edx, ebx
0x180064286  mov     rcx, rdi
0x180064289  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x18006428e  test    eax, eax
0x180064290  jnz     short loc_180064294
0x180064292  xor     ebx, ebx
0x180064294  mov     eax, ebx
0x180064296  jmp     short loc_1800642AB
0x180064298  mov     ecx, 0Dh; dwErrCode
0x18006429d  call    cs:__imp_SetLastError
0x1800642a4  nop     dword ptr [rax+rax+00h]
0x1800642a9  xor     eax, eax
0x1800642ab  mov     rcx, [rsp+0B8h+var_48]
0x1800642b0  xor     rcx, rsp; StackCookie
0x1800642b3  call    __security_check_cookie
0x1800642b8  add     rsp, 88h
0x1800642bf  pop     r15
0x1800642c1  pop     r14
0x1800642c3  pop     rdi
0x1800642c4  pop     rsi
0x1800642c5  pop     rbp
0x1800642c6  pop     rbx
0x1800642c7  retn
```
