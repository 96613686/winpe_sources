# XLOutput::Path(_PATHOBJ *,_DEVOBJ *)

- ea: `0x180013e00`
- end: `0x180014268`
- name: `?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(XLOutput *__hidden this, PATHOBJ *ppo, struct _DEVOBJ *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x18000edc0`
- `0x18001265c`
- `0x1800128c0`
- `0x180012cf0`
- `0x1800427a0`

## callees

- `0x180011dd0`
- `0x180011fc0`
- `0x180013e00`
- `0x180014270`
- `0x1800148e0`
- `0x18003235c`
- `0x180044ec4`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x180013e88`
- `GDI32!PATHOBJ_bEnum` at `0x180013e88`
- `GDI32!PATHOBJ_vEnumStart` at `0x180013e70`
- `GDI32!PATHOBJ_vEnumStart` at `0x180013e70`

## pseudocode

```c
__int64 __fastcall XLOutput::Path(XLOutput *this, PATHOBJ *ppo, struct _DEVOBJ *a3)
{
  PATHOBJ *v3; // r15
  __int64 v5; // rcx
  unsigned int v6; // esi
  BOOL v7; // eax
  signed int count; // edi
  BOOL v9; // ebp
  POINTFIX *pptfx; // r14
  unsigned int v11; // eax
  FIX v13; // r13d
  FIX v14; // esi
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  FIX v22; // r15d
  FIX v23; // r12d
  int v24; // esi
  __int16 v25; // dx
  __int16 v26; // r8
  FIX v27; // [rsp+20h] [rbp-58h]
  PATHDATA ppd; // [rsp+28h] [rbp-50h] BYREF
  int v31; // [rsp+98h] [rbp+20h]

  v3 = ppo;
  ppd = 0;
  if ( !ppo )
    return 2147549183LL;
  v5 = *((unsigned int *)this + 7);
  if ( (int)v5 + 1 >= (unsigned int)v5
    && (*((unsigned int *)this + 6) >= (unsigned __int64)(v5 + 8) || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u))
    && *((_QWORD *)this + 1) )
  {
    *(_BYTE *)(*((_QWORD *)this + 2))++ = -123;
    ++*((_DWORD *)this + 7);
  }
  v6 = 0;
  PATHOBJ_vEnumStart(v3);
  do
  {
    v7 = PATHOBJ_bEnum(v3, &ppd);
    count = ppd.count;
    v9 = v7;
    if ( ppd.count )
    {
      pptfx = ppd.pptfx;
      if ( (ppd.flags & 1) != 0 )
      {
        if ( !v6 )
        {
          v13 = ppd.pptfx->x >> 4;
          v14 = ppd.pptfx->y >> 4;
          v27 = v14;
          if ( (unsigned int)(v13 + 0x8000) > 0xFFFF || (unsigned int)(v14 + 0x8000) > 0xFFFF )
          {
            v22 = ppd.pptfx->y >> 4;
            v23 = ppd.pptfx->x >> 4;
            v24 = 1;
            while ( v23 || v22 )
            {
              v31 = v24;
              if ( v23 <= 0x7FFF )
              {
                if ( v23 >= -32768 )
                {
                  v25 = v23;
                  v23 = 0;
                }
                else
                {
                  v25 = 0x8000;
                  v23 += 0x8000;
                }
              }
              else
              {
                v25 = 0x7FFF;
                v23 -= 0x7FFF;
              }
              if ( v22 <= 0x7FFF )
              {
                if ( v22 >= -32768 )
                {
                  v26 = v22;
                  v22 = 0;
                }
                else
                {
                  v26 = 0x8000;
                  v22 += 0x8000;
                }
              }
              else
              {
                v26 = 0x7FFF;
                v22 -= 0x7FFF;
              }
              XLOutput::Send_sint16_xy(this, v25, v26);
              XLOutput::Send_attr_ubyte(this, 76);
              v24 = 0;
              XLWrite::WriteByte(this, (v31 == 0) + 107);
            }
            v3 = ppo;
            v14 = v27;
          }
          else
          {
            v15 = *((unsigned int *)this + 7);
            if ( (int)v15 + 1 >= (unsigned int)v15
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v15 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = -45;
              ++*((_DWORD *)this + 7);
            }
            v16 = *((_DWORD *)this + 7);
            if ( v16 + 2 >= v16
              && (*((_DWORD *)this + 6) >= v16 + 2 || !(unsigned int)XLWrite::IncreaseBuffer(this, 2u))
              && *((_QWORD *)this + 1) )
            {
              **((_WORD **)this + 2) = v13;
              *((_QWORD *)this + 2) += 2LL;
              *((_DWORD *)this + 7) += 2;
            }
            v17 = *((_DWORD *)this + 7);
            if ( v17 + 2 >= v17
              && (*((_DWORD *)this + 6) >= v17 + 2 || !(unsigned int)XLWrite::IncreaseBuffer(this, 2u))
              && *((_QWORD *)this + 1) )
            {
              **((_WORD **)this + 2) = v14;
              *((_QWORD *)this + 2) += 2LL;
              *((_DWORD *)this + 7) += 2;
            }
            v18 = *((unsigned int *)this + 7);
            if ( (int)v18 + 1 >= (unsigned int)v18
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v18 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = -8;
              ++*((_DWORD *)this + 7);
            }
            v19 = *((unsigned int *)this + 7);
            if ( (int)v19 + 1 >= (unsigned int)v19
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v19 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = 76;
              ++*((_DWORD *)this + 7);
            }
            v20 = *((unsigned int *)this + 7);
            if ( (int)v20 + 1 >= (unsigned int)v20
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v20 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = 107;
              ++*((_DWORD *)this + 7);
            }
          }
          *((_DWORD *)this + 73) = v14;
          v6 = 0;
          *((_DWORD *)this + 72) = v13;
        }
        ++pptfx;
        --count;
      }
      if ( count > 0 && !v6 )
      {
        if ( (ppd.flags & 0x10) != 0 )
          v11 = XLOutput::BezierPath(this, pptfx, count);
        else
          v11 = XLOutput::LinePath(this, pptfx, count);
        v6 = v11;
      }
      if ( (ppd.flags & 8) != 0 && !v6 )
      {
        v21 = *((unsigned int *)this + 7);
        if ( (int)v21 + 1 >= (unsigned int)v21
          && (*((unsigned int *)this + 6) >= (unsigned __int64)(v21 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer(this, 8u)) )
        {
          if ( *((_QWORD *)this + 1) )
          {
            *(_BYTE *)(*((_QWORD *)this + 2))++ = -124;
            ++*((_DWORD *)this + 7);
          }
        }
        v6 = 0;
      }
    }
    else
    {
      v6 = 1;
    }
  }
  while ( v9 );
  *((_QWORD *)a3 + 1) = *((_QWORD *)a3 + 522);
  return v6;
}

```

## disassembly

```asm
0x180013e00  mov     rax, rsp
0x180013e03  mov     [rax+18h], r8
0x180013e07  mov     [rax+10h], rdx
0x180013e0b  push    rbx
0x180013e0c  push    r15
0x180013e0e  sub     rsp, 68h
0x180013e12  xorps   xmm0, xmm0
0x180013e15  mov     r15, rdx
0x180013e18  mov     rbx, rcx
0x180013e1b  movups  xmmword ptr [rax-50h], xmm0
0x180013e1f  test    rdx, rdx
0x180013e22  jz      loc_1800140C1
0x180013e28  mov     ecx, [rcx+1Ch]
0x180013e2b  mov     [rax+8], rbp
0x180013e2f  mov     [rax-18h], rsi
0x180013e33  mov     [rax-20h], rdi
0x180013e37  mov     [rax-28h], r12
0x180013e3b  mov     [rax-38h], r14
0x180013e3f  lea     eax, [rcx+1]
0x180013e42  cmp     eax, ecx
0x180013e44  jb      short loc_180013E6B
0x180013e46  mov     eax, [rbx+18h]
0x180013e49  add     rcx, 8
0x180013e4d  cmp     rax, rcx
0x180013e50  jb      loc_180014150
0x180013e56  cmp     qword ptr [rbx+8], 0
0x180013e5b  jz      short loc_180013E6B
0x180013e5d  mov     rax, [rbx+10h]
0x180013e61  mov     byte ptr [rax], 85h
0x180013e64  inc     qword ptr [rbx+10h]
0x180013e68  inc     dword ptr [rbx+1Ch]
0x180013e6b  xor     esi, esi
0x180013e6d  mov     rcx, r15; ppo
0x180013e70  call    cs:__imp_PATHOBJ_vEnumStart
0x180013e76  mov     [rsp+78h+var_30], r13
0x180013e7b  nop     dword ptr [rax+rax+00h]
0x180013e80  lea     rdx, [rsp+78h+ppd]; ppd
0x180013e85  mov     rcx, r15; ppo
0x180013e88  call    cs:__imp_PATHOBJ_bEnum
0x180013e8e  mov     edi, [rsp+78h+ppd.count]
0x180013e92  mov     ebp, eax
0x180013e94  test    edi, edi
0x180013e96  jz      loc_18001416A
0x180013e9c  test    byte ptr [rsp+78h+ppd.flags], 1
0x180013ea1  mov     r14, [rsp+78h+ppd.pptfx]
0x180013ea6  jnz     short loc_180013F1B
0x180013ea8  test    edi, edi
0x180013eaa  jle     short loc_180013EC7
0x180013eac  test    esi, esi
0x180013eae  jnz     short loc_180013EC7
0x180013eb0  test    byte ptr [rsp+78h+ppd.flags], 10h
0x180013eb5  mov     r8d, edi; int
0x180013eb8  mov     rdx, r14; struct _POINTFIX *
0x180013ebb  mov     rcx, rbx; this
0x180013ebe  jz      short loc_180013F14
0x180013ec0  call    ?BezierPath@XLOutput@@QEAAJPEAU_POINTFIX@@J@Z; XLOutput::BezierPath(_POINTFIX *,long)
0x180013ec5  mov     esi, eax
0x180013ec7  test    byte ptr [rsp+78h+ppd.flags], 8
0x180013ecc  jnz     loc_180014083
0x180013ed2  test    ebp, ebp
0x180013ed4  jnz     short loc_180013E80
0x180013ed6  mov     r14, [rsp+78h+arg_10]
0x180013ede  mov     r13, [rsp+78h+var_30]
0x180013ee3  mov     r12, [rsp+78h+var_28]
0x180013ee8  mov     rdi, [rsp+78h+var_20]
0x180013eed  mov     rax, [r14+1050h]
0x180013ef4  mov     rbp, [rsp+78h+arg_0]
0x180013efc  mov     [r14+8], rax
0x180013f00  mov     eax, esi
0x180013f02  mov     rsi, [rsp+78h+var_18]
0x180013f07  mov     r14, [rsp+78h+var_38]
0x180013f0c  add     rsp, 68h
0x180013f10  pop     r15
0x180013f12  pop     rbx
0x180013f13  retn
0x180013f14  call    ?LinePath@XLOutput@@QEAAJPEAU_POINTFIX@@J@Z; XLOutput::LinePath(_POINTFIX *,long)
0x180013f19  jmp     short loc_180013EC5
0x180013f1b  test    esi, esi
0x180013f1d  jnz     loc_180014078
0x180013f23  mov     r13d, [r14]
0x180013f26  mov     esi, [r14+4]
0x180013f2a  sar     r13d, 4
0x180013f2e  sar     esi, 4
0x180013f31  mov     [rsp+78h+var_58], esi
0x180013f35  lea     eax, [r13+8000h]
0x180013f3c  cmp     eax, 0FFFFh
0x180013f41  ja      loc_1800141A8
0x180013f47  lea     eax, [rsi+8000h]
0x180013f4d  cmp     eax, 0FFFFh
0x180013f52  ja      loc_1800141A8
0x180013f58  mov     ecx, [rbx+1Ch]
0x180013f5b  lea     eax, [rcx+1]
0x180013f5e  cmp     eax, ecx
0x180013f60  jb      short loc_180013F87
0x180013f62  mov     eax, [rbx+18h]
0x180013f65  add     rcx, 8
0x180013f69  cmp     rax, rcx
0x180013f6c  jb      loc_1800140CE
0x180013f72  cmp     qword ptr [rbx+8], 0
0x180013f77  jz      short loc_180013F87
0x180013f79  mov     rax, [rbx+10h]
0x180013f7d  mov     byte ptr [rax], 0D3h
0x180013f80  inc     qword ptr [rbx+10h]
0x180013f84  inc     dword ptr [rbx+1Ch]
0x180013f87  mov     eax, [rbx+1Ch]
0x180013f8a  lea     ecx, [rax+2]
0x180013f8d  cmp     ecx, eax
0x180013f8f  jb      short loc_180013FB2
0x180013f91  cmp     [rbx+18h], ecx
0x180013f94  jb      loc_180014174
0x180013f9a  cmp     qword ptr [rbx+8], 0
0x180013f9f  jz      short loc_180013FB2
0x180013fa1  mov     rax, [rbx+10h]
0x180013fa5  mov     [rax], r13w
0x180013fa9  add     qword ptr [rbx+10h], 2
0x180013fae  add     dword ptr [rbx+1Ch], 2
0x180013fb2  mov     eax, [rbx+1Ch]
0x180013fb5  lea     ecx, [rax+2]
0x180013fb8  cmp     ecx, eax
0x180013fba  jb      short loc_180013FDC
0x180013fbc  cmp     [rbx+18h], ecx
0x180013fbf  jb      loc_18001418E
0x180013fc5  cmp     qword ptr [rbx+8], 0
0x180013fca  jz      short loc_180013FDC
0x180013fcc  mov     rax, [rbx+10h]
0x180013fd0  mov     [rax], si
0x180013fd3  add     qword ptr [rbx+10h], 2
0x180013fd8  add     dword ptr [rbx+1Ch], 2
0x180013fdc  mov     ecx, [rbx+1Ch]
0x180013fdf  lea     eax, [rcx+1]
0x180013fe2  cmp     eax, ecx
0x180013fe4  jb      short loc_18001400B
0x180013fe6  mov     eax, [rbx+18h]
0x180013fe9  add     rcx, 8
0x180013fed  cmp     rax, rcx
0x180013ff0  jb      loc_1800140E8
0x180013ff6  cmp     qword ptr [rbx+8], 0
0x180013ffb  jz      short loc_18001400B
0x180013ffd  mov     rax, [rbx+10h]
0x180014001  mov     byte ptr [rax], 0F8h
0x180014004  inc     qword ptr [rbx+10h]
0x180014008  inc     dword ptr [rbx+1Ch]
0x18001400b  mov     ecx, [rbx+1Ch]
0x18001400e  lea     eax, [rcx+1]
0x180014011  cmp     eax, ecx
0x180014013  jb      short loc_18001403A
0x180014015  mov     eax, [rbx+18h]
0x180014018  add     rcx, 8
0x18001401c  cmp     rax, rcx
0x18001401f  jb      loc_180014102
0x180014025  cmp     qword ptr [rbx+8], 0
0x18001402a  jz      short loc_18001403A
0x18001402c  mov     rax, [rbx+10h]
0x180014030  mov     byte ptr [rax], 4Ch ; 'L'
0x180014033  inc     qword ptr [rbx+10h]
0x180014037  inc     dword ptr [rbx+1Ch]
0x18001403a  mov     ecx, [rbx+1Ch]
0x18001403d  lea     eax, [rcx+1]
0x180014040  cmp     eax, ecx
0x180014042  jb      short loc_180014069
0x180014044  mov     eax, [rbx+18h]
0x180014047  add     rcx, 8
0x18001404b  cmp     rax, rcx
0x18001404e  jb      loc_18001411C
0x180014054  cmp     qword ptr [rbx+8], 0
0x180014059  jz      short loc_180014069
0x18001405b  mov     rax, [rbx+10h]
0x18001405f  mov     byte ptr [rax], 6Bh ; 'k'
0x180014062  inc     qword ptr [rbx+10h]
0x180014066  inc     dword ptr [rbx+1Ch]
0x180014069  mov     [rbx+124h], esi
0x18001406f  xor     esi, esi
0x180014071  mov     [rbx+120h], r13d
0x180014078  add     r14, 8
0x18001407c  dec     edi
0x18001407e  jmp     loc_180013EA8
0x180014083  test    esi, esi
0x180014085  jnz     loc_180013ED2
0x18001408b  mov     ecx, [rbx+1Ch]
0x18001408e  lea     eax, [rcx+1]
0x180014091  cmp     eax, ecx
0x180014093  jb      short loc_1800140BA
0x180014095  mov     eax, [rbx+18h]
0x180014098  add     rcx, 8
0x18001409c  cmp     rax, rcx
0x18001409f  jb      loc_180014136
0x1800140a5  cmp     qword ptr [rbx+8], 0
0x1800140aa  jz      short loc_1800140BA
0x1800140ac  mov     rax, [rbx+10h]
0x1800140b0  mov     byte ptr [rax], 84h
0x1800140b3  inc     qword ptr [rbx+10h]
0x1800140b7  inc     dword ptr [rbx+1Ch]
0x1800140ba  xor     esi, esi
0x1800140bc  jmp     loc_180013ED2
0x1800140c1  mov     eax, 8000FFFFh
0x1800140c6  add     rsp, 68h
0x1800140ca  pop     r15
0x1800140cc  pop     rbx
0x1800140cd  retn
0x1800140ce  mov     edx, 8; unsigned int
0x1800140d3  mov     rcx, rbx; this
0x1800140d6  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x1800140db  test    eax, eax
0x1800140dd  jnz     loc_180013F87
0x1800140e3  jmp     loc_180013F72
0x1800140e8  mov     edx, 8; unsigned int
0x1800140ed  mov     rcx, rbx; this
0x1800140f0  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x1800140f5  test    eax, eax
0x1800140f7  jnz     loc_18001400B
0x1800140fd  jmp     loc_180013FF6
0x180014102  mov     edx, 8; unsigned int
0x180014107  mov     rcx, rbx; this
0x18001410a  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x18001410f  test    eax, eax
0x180014111  jnz     loc_18001403A
0x180014117  jmp     loc_180014025
0x18001411c  mov     edx, 8; unsigned int
0x180014121  mov     rcx, rbx; this
0x180014124  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014129  test    eax, eax
0x18001412b  jnz     loc_180014069
0x180014131  jmp     loc_180014054
0x180014136  mov     edx, 8; unsigned int
0x18001413b  mov     rcx, rbx; this
0x18001413e  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014143  test    eax, eax
0x180014145  jnz     loc_1800140BA
0x18001414b  jmp     loc_1800140A5
0x180014150  mov     edx, 8; unsigned int
0x180014155  mov     rcx, rbx; this
0x180014158  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x18001415d  test    eax, eax
0x18001415f  jnz     loc_180013E6B
0x180014165  jmp     loc_180013E56
0x18001416a  mov     esi, 1
0x18001416f  jmp     loc_180013ED2
0x180014174  mov     edx, 2; unsigned int
0x180014179  mov     rcx, rbx; this
0x18001417c  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014181  test    eax, eax
0x180014183  jnz     loc_180013FB2
0x180014189  jmp     loc_180013F9A
0x18001418e  mov     edx, 2; unsigned int
0x180014193  mov     rcx, rbx; this
0x180014196  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x18001419b  test    eax, eax
0x18001419d  jnz     loc_180013FDC
0x1800141a3  jmp     loc_180013FC5
0x1800141a8  mov     r15d, esi
0x1800141ab  mov     r12d, r13d
0x1800141ae  mov     esi, 1
0x1800141b3  test    r12d, r12d
0x1800141b6  jnz     short loc_1800141CE
0x1800141b8  test    r15d, r15d
0x1800141bb  jnz     short loc_1800141CE
0x1800141bd  mov     r15, [rsp+78h+arg_8]
0x1800141c5  mov     esi, [rsp+78h+var_58]
0x1800141c9  jmp     loc_180014069
0x1800141ce  mov     [rsp+78h+arg_18], esi
0x1800141d5  cmp     r12d, 7FFFh
0x1800141dc  jle     short loc_1800141E8
0x1800141de  mov     edx, 7FFFh
0x1800141e3  sub     r12d, edx
0x1800141e6  jmp     short loc_180014205
0x1800141e8  cmp     r12d, 0FFFF8000h
0x1800141ef  jge     short loc_1800141FF
0x1800141f1  mov     edx, 0FFFF8000h
0x1800141f6  add     r12d, 8000h
0x1800141fd  jmp     short loc_180014205
0x1800141ff  mov     edx, r12d; __int16
0x180014202  xor     r12d, r12d
0x180014205  cmp     r15d, 7FFFh
0x18001420c  jle     short loc_180014219
0x18001420e  mov     r8d, 7FFFh
0x180014214  sub     r15d, r8d
0x180014217  jmp     short loc_180014237
0x180014219  cmp     r15d, 0FFFF8000h
0x180014220  jge     short loc_180014231
0x180014222  mov     r8d, 0FFFF8000h
0x180014228  add     r15d, 8000h
0x18001422f  jmp     short loc_180014237
0x180014231  mov     r8d, r15d; __int16
0x180014234  xor     r15d, r15d
0x180014237  mov     rcx, rbx; this
0x18001423a  call    ?Send_sint16_xy@XLOutput@@QEAAJFF@Z; XLOutput::Send_sint16_xy(short,short)
0x18001423f  mov     edx, 4Ch ; 'L'
0x180014244  mov     rcx, rbx
0x180014247  call    ?Send_attr_ubyte@XLOutput@@QEAAJW4Attribute@@@Z; XLOutput::Send_attr_ubyte(Attribute)
0x18001424c  xor     esi, esi
0x18001424e  mov     rcx, rbx; this
0x180014251  cmp     [rsp+78h+arg_18], esi
0x180014258  setz    dl
0x18001425b  add     dl, 6Bh ; 'k'; unsigned __int8
0x18001425e  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180014263  jmp     loc_1800141B3
```
