# BEnumerateClipPathAndDraw(_DEVOBJ *,_CLIPOBJ *,_RECTL *)

- ea: `0x180064860`
- end: `0x180064966`
- name: `?BEnumerateClipPathAndDraw@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _CLIPOBJ *, struct _RECTL *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006496c`

## callees

- `0x180046790`
- `0x180049d00`
- `0x180064860`
- `0x180064a78`
- `0x180066dc0`
- `0x1800686dc`

## import_xrefs

- `GDI32!CLIPOBJ_bEnum` at `0x1800648da`
- `GDI32!CLIPOBJ_bEnum` at `0x1800648da`
- `GDI32!CLIPOBJ_cEnumStart` at `0x1800648c1`
- `GDI32!CLIPOBJ_cEnumStart` at `0x1800648c1`

## pseudocode

```c
__int64 __fastcall BEnumerateClipPathAndDraw(struct _DEVOBJ *a1, struct _CLIPOBJ *a2, struct _RECTL *a3)
{
  unsigned int v6; // edi
  int DeviceResolution; // r12d
  int v8; // esi
  int v9; // ebx
  struct _RECTL *v10; // rdx
  struct _RECTL *v11; // rdx
  struct _RECTL v13; // [rsp+30h] [rbp-68h] BYREF
  ULONG pul[4]; // [rsp+40h] [rbp-58h] BYREF
  int v15; // [rsp+50h] [rbp-48h]

  v15 = 0;
  *(_OWORD *)pul = 0;
  v6 = 1;
  v13 = 0;
  DeviceResolution = HPGL_GetDeviceResolution(a1);
  if ( a2 )
  {
    CLIPOBJ_cEnumStart(a2, 1, 0, 0, 0x100u);
    while ( 1 )
    {
      v8 = CLIPOBJ_bEnum(a2, 0x14u, pul);
      if ( v8 == -1 )
        return 0;
      v9 = 0;
      if ( pul[0] )
      {
        while ( 1 )
        {
          v10 = (struct _RECTL *)&pul[4 * v9 + 1];
          if ( DeviceResolution <= 300 )
            break;
          if ( (unsigned int)BRectanglesIntersect(a3, v10, &v13) )
          {
            v11 = &v13;
LABEL_9:
            HPGL_DrawRectangle(a1, v11);
          }
          if ( ++v9 >= pul[0] )
            goto LABEL_11;
        }
        HPGL_SetClippingRegion(a1, v10);
        v11 = a3;
        goto LABEL_9;
      }
LABEL_11:
      if ( !v8 )
        return v6;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180064860  push    rbx
0x180064862  push    rbp
0x180064863  push    rsi
0x180064864  push    rdi
0x180064865  push    r12
0x180064867  push    r14
0x180064869  push    r15
0x18006486b  sub     rsp, 60h
0x18006486f  mov     rax, cs:__security_cookie
0x180064876  xor     rax, rsp
0x180064879  mov     [rsp+98h+var_40], rax
0x18006487e  xor     eax, eax
0x180064880  xorps   xmm0, xmm0
0x180064883  mov     r15, r8
0x180064886  mov     [rsp+98h+var_48], eax
0x18006488a  mov     r14, rdx
0x18006488d  mov     rbp, rcx
0x180064890  movups  xmmword ptr [rsp+98h+pul], xmm0
0x180064895  lea     edi, [rax+1]
0x180064898  movups  xmmword ptr [rsp+98h+var_68.left], xmm0
0x18006489d  call    ?HPGL_GetDeviceResolution@@YAKPEAU_DEVOBJ@@@Z; HPGL_GetDeviceResolution(_DEVOBJ *)
0x1800648a2  mov     r12d, eax
0x1800648a5  test    r14, r14
0x1800648a8  jz      loc_180064947
0x1800648ae  xor     r9d, r9d; iDirection
0x1800648b1  mov     [rsp+98h+cLimit], 100h; cLimit
0x1800648b9  xor     r8d, r8d; iType
0x1800648bc  mov     edx, edi; bAll
0x1800648be  mov     rcx, r14; pco
0x1800648c1  call    cs:__imp_CLIPOBJ_cEnumStart
0x1800648c8  nop     dword ptr [rax+rax+00h]
0x1800648cd  lea     r8, [rsp+98h+pul]; pul
0x1800648d2  mov     edx, 14h; cj
0x1800648d7  mov     rcx, r14; pco
0x1800648da  call    cs:__imp_CLIPOBJ_bEnum
0x1800648e1  nop     dword ptr [rax+rax+00h]
0x1800648e6  mov     esi, eax
0x1800648e8  cmp     eax, 0FFFFFFFFh
0x1800648eb  jz      short loc_180064945
0x1800648ed  xor     ebx, ebx
0x1800648ef  cmp     [rsp+98h+pul], ebx
0x1800648f3  jbe     short loc_18006493F
0x1800648f5  mov     eax, ebx
0x1800648f7  lea     rdx, [rsp+98h+pul+4]
0x1800648fc  shl     rax, 4
0x180064900  add     rdx, rax; struct _RECTL *
0x180064903  cmp     r12d, 12Ch
0x18006490a  jle     short loc_180064924
0x18006490c  lea     r8, [rsp+98h+var_68]; struct _RECTL *
0x180064911  mov     rcx, r15; struct _RECTL *
0x180064914  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x180064919  test    eax, eax
0x18006491b  jz      short loc_180064937
0x18006491d  lea     rdx, [rsp+98h+var_68]
0x180064922  jmp     short loc_18006492F
0x180064924  mov     rcx, rbp; struct _DEVOBJ *
0x180064927  call    ?HPGL_SetClippingRegion@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@I@Z; HPGL_SetClippingRegion(_DEVOBJ *,_RECTL *,uint)
0x18006492c  mov     rdx, r15; struct _RECTL *
0x18006492f  mov     rcx, rbp; struct _DEVOBJ *
0x180064932  call    ?HPGL_DrawRectangle@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@@Z; HPGL_DrawRectangle(_DEVOBJ *,_RECTL *)
0x180064937  add     ebx, edi
0x180064939  cmp     ebx, [rsp+98h+pul]
0x18006493d  jb      short loc_1800648F5
0x18006493f  test    esi, esi
0x180064941  jnz     short loc_1800648CD
0x180064943  jmp     short loc_180064947
0x180064945  xor     edi, edi
0x180064947  mov     eax, edi
0x180064949  mov     rcx, [rsp+98h+var_40]
0x18006494e  xor     rcx, rsp; StackCookie
0x180064951  call    __security_check_cookie
0x180064956  add     rsp, 60h
0x18006495a  pop     r15
0x18006495c  pop     r14
0x18006495e  pop     r12
0x180064960  pop     rdi
0x180064961  pop     rsi
0x180064962  pop     rbp
0x180064963  pop     rbx
0x180064964  retn
```
