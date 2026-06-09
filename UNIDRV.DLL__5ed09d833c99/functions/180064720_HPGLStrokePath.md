# HPGLStrokePath

- ea: `0x180064720`
- end: `0x180064859`
- name: `HPGLStrokePath`
- size: `313`
- prototype: `__int64 __fastcall(__int64, struct _PATHOBJ *, struct _CLIPOBJ *, struct _XFORMOBJ *, __int64, __int64, struct _LINEATTRS *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180039f24`
- `0x1800465b4`
- `0x180049d00`
- `0x180064720`
- `0x180066cbc`
- `0x180067d58`
- `0x180068a8c`
- `0x18006b184`
- `0x18006b310`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180064829`
- `KERNEL32!SetLastError` at `0x180064829`

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
  _OWORD v14[3]; // [rsp+40h] [rbp-88h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  memset(v14, 0, 44);
  if ( *(_QWORD *)(v8 + 8) )
  {
    v12 = 1;
    BChangeAndTrackObjectType(v8, 1);
    if ( !(unsigned int)SelectMix((struct _DEVOBJ *)v8, a8)
      || !(unsigned int)SelectClipEx((struct _DEVOBJ *)v8, a3)
      || !(unsigned int)CreateHPGLPenBrush(v8, (__int64)v14, a6, a5, 0, 0, 0)
      || !(unsigned int)SelectLineAttrs((struct _DEVOBJ *)v8, a7, a4)
      || !(unsigned int)MarkPath((struct _DEVOBJ *)v8, a2, (struct _HPGLMARKER *)v14, 0)
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
0x180064720  push    rbx
0x180064722  push    rbp
0x180064723  push    rsi
0x180064724  push    rdi
0x180064725  push    r12
0x180064727  push    r13
0x180064729  push    r14
0x18006472b  push    r15
0x18006472d  sub     rsp, 88h
0x180064734  mov     rax, cs:__security_cookie
0x18006473b  xor     rax, rsp
0x18006473e  mov     [rsp+0C8h+var_58], rax
0x180064743  mov     rbx, [rcx+10h]
0x180064747  xorps   xmm0, xmm0
0x18006474a  mov     r12, [rsp+0C8h+arg_20]
0x180064752  xor     eax, eax
0x180064754  mov     r13, [rsp+0C8h+arg_28]
0x18006475c  mov     rbp, r9
0x18006475f  mov     r14, [rsp+0C8h+arg_30]
0x180064767  mov     rsi, r8
0x18006476a  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x18006476f  mov     r15, rdx
0x180064772  movups  [rsp+0C8h+var_88], xmm0
0x180064777  movups  xmmword ptr [rsp+0C8h+var_78+0Ch], xmm0
0x18006477c  cmp     [rbx+8], rax
0x180064780  jz      loc_180064824
0x180064786  lea     edi, [rax+1]
0x180064789  mov     rcx, rbx
0x18006478c  mov     edx, edi
0x18006478e  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180064793  mov     edx, [rsp+0C8h+arg_38]; unsigned int
0x18006479a  mov     rcx, rbx; struct _DEVOBJ *
0x18006479d  call    ?SelectMix@@YAHPEAU_DEVOBJ@@K@Z; SelectMix(_DEVOBJ *,ulong)
0x1800647a2  test    eax, eax
0x1800647a4  jz      short loc_18006481E
0x1800647a6  mov     rdx, rsi; struct _CLIPOBJ *
0x1800647a9  mov     rcx, rbx; struct _DEVOBJ *
0x1800647ac  call    ?SelectClipEx@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@K@Z; SelectClipEx(_DEVOBJ *,_CLIPOBJ *,ulong)
0x1800647b1  test    eax, eax
0x1800647b3  jz      short loc_18006481E
0x1800647b5  mov     [rsp+0C8h+var_98], 0
0x1800647bd  lea     rdx, [rsp+0C8h+var_88]
0x1800647c2  mov     [rsp+0C8h+var_A0], 0
0x1800647ca  mov     r9, r12
0x1800647cd  mov     r8, r13
0x1800647d0  mov     [rsp+0C8h+var_A8], 0
0x1800647d8  mov     rcx, rbx
0x1800647db  call    ?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z; CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)
0x1800647e0  test    eax, eax
0x1800647e2  jz      short loc_18006481E
0x1800647e4  mov     r8, rbp; struct _XFORMOBJ *
0x1800647e7  mov     rdx, r14; struct _LINEATTRS *
0x1800647ea  mov     rcx, rbx; struct _DEVOBJ *
0x1800647ed  call    ?SelectLineAttrs@@YAHPEAU_DEVOBJ@@PEAU_LINEATTRS@@PEAU_XFORMOBJ@@@Z; SelectLineAttrs(_DEVOBJ *,_LINEATTRS *,_XFORMOBJ *)
0x1800647f2  test    eax, eax
0x1800647f4  jz      short loc_18006481E
0x1800647f6  xor     r9d, r9d; struct _HPGLMARKER *
0x1800647f9  lea     r8, [rsp+0C8h+var_88]; struct _HPGLMARKER *
0x1800647fe  mov     rdx, r15; struct _PATHOBJ *
0x180064801  mov     rcx, rbx; struct _DEVOBJ *
0x180064804  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x180064809  test    eax, eax
0x18006480b  jz      short loc_18006481E
0x18006480d  xor     r8d, r8d
0x180064810  mov     edx, edi
0x180064812  mov     rcx, rbx
0x180064815  call    ?HPGL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@E@Z; HPGL_SelectTransparency(_DEVOBJ *,ETransparency,uchar)
0x18006481a  test    eax, eax
0x18006481c  jnz     short loc_180064820
0x18006481e  xor     edi, edi
0x180064820  mov     eax, edi
0x180064822  jmp     short loc_180064837
0x180064824  mov     ecx, 0Dh; dwErrCode
0x180064829  call    cs:__imp_SetLastError
0x180064830  nop     dword ptr [rax+rax+00h]
0x180064835  xor     eax, eax
0x180064837  mov     rcx, [rsp+0C8h+var_58]
0x18006483c  xor     rcx, rsp; StackCookie
0x18006483f  call    __security_check_cookie
0x180064844  add     rsp, 88h
0x18006484b  pop     r15
0x18006484d  pop     r14
0x18006484f  pop     r13
0x180064851  pop     r12
0x180064853  pop     rdi
0x180064854  pop     rsi
0x180064855  pop     rbp
0x180064856  pop     rbx
0x180064857  retn
```
