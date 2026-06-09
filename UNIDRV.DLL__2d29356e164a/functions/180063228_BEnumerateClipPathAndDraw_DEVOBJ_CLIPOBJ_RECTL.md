# BEnumerateClipPathAndDraw(_DEVOBJ *,_CLIPOBJ *,_RECTL *)

- ea: `0x180063228`
- end: `0x180063321`
- name: `?BEnumerateClipPathAndDraw@@YAHPEAU_DEVOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@@Z`
- size: `249`
- prototype: `int(struct _DEVOBJ *, struct _CLIPOBJ *, struct _RECTL *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180063328`

## callees

- `0x180045410`
- `0x1800487e0`
- `0x180063228`
- `0x18006342c`
- `0x180065684`
- `0x180066edc`

## import_xrefs

- `GDI32!CLIPOBJ_bEnum` at `0x18006329c`
- `GDI32!CLIPOBJ_bEnum` at `0x18006329c`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180063289`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180063289`

## pseudocode

```c
__int64 __fastcall BEnumerateClipPathAndDraw(struct _DEVOBJ *a1, struct _CLIPOBJ *a2, struct _RECTL *a3)
{
  unsigned int v6; // edi
  int DeviceResolution; // r12d
  int v8; // esi
  unsigned int v9; // r8d
  int v10; // ebx
  struct _RECTL *v11; // rdx
  struct _RECTL *v12; // rdx
  struct _RECTL v14; // [rsp+30h] [rbp-68h] BYREF
  ULONG pul[4]; // [rsp+40h] [rbp-58h] BYREF
  int v16; // [rsp+50h] [rbp-48h]

  v16 = 0;
  *(_OWORD *)pul = 0;
  v6 = 1;
  v14 = 0;
  DeviceResolution = HPGL_GetDeviceResolution(a1);
  if ( a2 )
  {
    CLIPOBJ_cEnumStart(a2, 1, 0, 0, 0x100u);
    while ( 1 )
    {
      v8 = CLIPOBJ_bEnum(a2, 0x14u, pul);
      if ( v8 == -1 )
        return 0;
      v10 = 0;
      if ( pul[0] )
      {
        while ( 1 )
        {
          v11 = (struct _RECTL *)&pul[4 * v10 + 1];
          if ( DeviceResolution <= 300 )
            break;
          if ( (unsigned int)BRectanglesIntersect(a3, v11, &v14) )
          {
            v12 = &v14;
LABEL_9:
            HPGL_DrawRectangle(a1, v12);
          }
          if ( ++v10 >= pul[0] )
            goto LABEL_11;
        }
        HPGL_SetClippingRegion(a1, v11, v9);
        v12 = a3;
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
0x180063228  push    rbx
0x18006322a  push    rbp
0x18006322b  push    rsi
0x18006322c  push    rdi
0x18006322d  push    r12
0x18006322f  push    r14
0x180063231  push    r15
0x180063233  sub     rsp, 60h
0x180063237  mov     rax, cs:__security_cookie
0x18006323e  xor     rax, rsp
0x180063241  mov     [rsp+98h+var_40], rax
0x180063246  xor     eax, eax
0x180063248  xorps   xmm0, xmm0
0x18006324b  mov     r15, r8
0x18006324e  mov     [rsp+98h+var_48], eax
0x180063252  mov     r14, rdx
0x180063255  mov     rbp, rcx
0x180063258  movups  xmmword ptr [rsp+98h+pul], xmm0
0x18006325d  lea     edi, [rax+1]
0x180063260  movups  xmmword ptr [rsp+98h+var_68.left], xmm0
0x180063265  call    ?HPGL_GetDeviceResolution@@YAKPEAU_DEVOBJ@@@Z; HPGL_GetDeviceResolution(_DEVOBJ *)
0x18006326a  mov     r12d, eax
0x18006326d  test    r14, r14
0x180063270  jz      loc_180063303
0x180063276  xor     r9d, r9d; iDirection
0x180063279  mov     [rsp+98h+cLimit], 100h; cLimit
0x180063281  xor     r8d, r8d; iType
0x180063284  mov     edx, edi; bAll
0x180063286  mov     rcx, r14; pco
0x180063289  call    cs:__imp_CLIPOBJ_cEnumStart
0x18006328f  lea     r8, [rsp+98h+pul]; pul
0x180063294  mov     edx, 14h; cj
0x180063299  mov     rcx, r14; pco
0x18006329c  call    cs:__imp_CLIPOBJ_bEnum
0x1800632a2  mov     esi, eax
0x1800632a4  cmp     eax, 0FFFFFFFFh
0x1800632a7  jz      short loc_180063301
0x1800632a9  xor     ebx, ebx
0x1800632ab  cmp     [rsp+98h+pul], ebx
0x1800632af  jbe     short loc_1800632FB
0x1800632b1  mov     eax, ebx
0x1800632b3  lea     rdx, [rsp+98h+pul+4]
0x1800632b8  shl     rax, 4
0x1800632bc  add     rdx, rax; struct _RECTL *
0x1800632bf  cmp     r12d, 12Ch
0x1800632c6  jle     short loc_1800632E0
0x1800632c8  lea     r8, [rsp+98h+var_68]; struct _RECTL *
0x1800632cd  mov     rcx, r15; struct _RECTL *
0x1800632d0  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x1800632d5  test    eax, eax
0x1800632d7  jz      short loc_1800632F3
0x1800632d9  lea     rdx, [rsp+98h+var_68]
0x1800632de  jmp     short loc_1800632EB
0x1800632e0  mov     rcx, rbp; struct _DEVOBJ *
0x1800632e3  call    ?HPGL_SetClippingRegion@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@I@Z; HPGL_SetClippingRegion(_DEVOBJ *,_RECTL *,uint)
0x1800632e8  mov     rdx, r15; struct _RECTL *
0x1800632eb  mov     rcx, rbp; struct _DEVOBJ *
0x1800632ee  call    ?HPGL_DrawRectangle@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@@Z; HPGL_DrawRectangle(_DEVOBJ *,_RECTL *)
0x1800632f3  add     ebx, edi
0x1800632f5  cmp     ebx, [rsp+98h+pul]
0x1800632f9  jb      short loc_1800632B1
0x1800632fb  test    esi, esi
0x1800632fd  jnz     short loc_18006328F
0x1800632ff  jmp     short loc_180063303
0x180063301  xor     edi, edi
0x180063303  mov     eax, edi
0x180063305  mov     rcx, [rsp+98h+var_40]
0x18006330a  xor     rcx, rsp; StackCookie
0x18006330d  call    __security_check_cookie
0x180063312  add     rsp, 60h
0x180063316  pop     r15
0x180063318  pop     r14
0x18006331a  pop     r12
0x18006331c  pop     rdi
0x18006331d  pop     rsi
0x18006331e  pop     rbp
0x18006331f  pop     rbx
0x180063320  retn
```
