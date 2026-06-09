# CTypeLib2::SaveAllChanges(void)

- ea: `0x180030f50`
- end: `0x1800314a7`
- name: `?SaveAllChanges@CTypeLib2@@UEAAJXZ`
- size: `1367`
- prototype: `__int64 __fastcall(CTypeLib2 *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops`

## callees

- `0x180013634`
- `0x180014730`
- `0x1800179dc`
- `0x1800238a8`
- `0x180027ed0`
- `0x180030f50`
- `0x1800314b0`
- `0x180031818`
- `0x180031884`
- `0x180031e20`
- `0x180039bf8`
- `0x180048788`
- `0x1800487d0`
- `0x180049378`
- `0x1800494e4`
- `0x18004d900`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x18003147b`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x18003147b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003146c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003146c`

## pseudocode

```c
int __fastcall CTypeLib2::SaveAllChanges(CTypeLib2 *this)
{
  __int16 v2; // cx
  __int16 v3; // bp
  int v4; // r13d
  __int64 i; // rdi
  __int64 v6; // rdx
  _BYTE *v7; // rax
  int result; // eax
  int v9; // esi
  char *v10; // rdi
  _QWORD *v11; // r12
  bool v12; // zf
  unsigned int v13; // eax
  HEAP *v14; // rcx
  __int64 j; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // esi
  unsigned int v21; // r8d
  void *v22; // rdx
  unsigned int v23; // eax
  struct HEAP *v24; // rsi
  unsigned int *v25; // r9
  HEAP *v26; // rcx
  __int64 k; // rbp
  __int64 v28; // rdx
  OLECHAR *v29; // rbx
  UINT v30; // eax
  CTypeInfo2 *v31[2]; // [rsp+40h] [rbp-178h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-168h] BYREF

  v2 = *((_WORD *)this + 198);
  v3 = v2 & 3;
  if ( (v2 & 3) == *((_DWORD *)this + 167) )
  {
    v3 = 1;
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *((_WORD *)this + 198) = v2 ^ (*((_WORD *)this + 334) ^ v2) & 3;
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 102); i = (unsigned int)(i + 1) )
  {
    v6 = *(unsigned int *)(*((_QWORD *)this + 58) + 4 * i);
    if ( (unsigned int)v6 < *((_DWORD *)this + 7) )
      v7 = (_BYTE *)(*((_QWORD *)this + 5) + v6);
    else
      v7 = 0;
    if ( (*v7 & 0x20) == 0 || v4 )
    {
      v31[0] = 0;
      result = CTypeLib2::GetTypeInfoOfInfoDef((CTypeLib2 *)((char *)this - 8), v6, v31);
      if ( result < 0 )
        return result;
      v9 = CTypeInfo2::SysSpecificLayOut(v31[0], (enum tagSYSKIND)(*((_WORD *)this + 198) & 3));
      CTypeInfo2::Release(v31[0]);
      if ( v9 < 0 )
        return v9;
    }
  }
  v10 = (char *)this - 8;
  v11 = (_QWORD *)((char *)this + 472);
  v12 = *((_QWORD *)this + 59) == 0;
  *((_DWORD *)this + 166) = *((_WORD *)this + 198) & 3;
  if ( !v12 )
    return -2147024891;
  result = OpenFileLockBytes(1, *((unsigned __int16 **)this + 64), (struct ILockBytes **)this + 59);
  if ( result >= 0 )
  {
    v13 = *((_DWORD *)this + 102);
    *((_QWORD *)this + 62) = 0;
    if ( !v13
      || (v9 = HEAP::Map64To32(
                 (CTypeLib2 *)((char *)this + 640),
                 (CTypeLib2 *)((char *)this - 8),
                 (CTypeLib2 *)((char *)this + 24),
                 *((unsigned int **)this + 58),
                 v13),
          v9 >= 0) )
    {
      *((_DWORD *)this + 160) = *((_DWORD *)this + 6);
      *((_DWORD *)this + 163) = *((_DWORD *)this + 9);
      if ( (int)CTypeLib2::WriteLibHeader((CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 640), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 120), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 144), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 96), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 48), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 72), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 168), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 192), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 216), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 240), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 264), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 288), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 312), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 336), (CTypeLib2 *)((char *)this - 8)) < 0
        || HEAP::WriteHeap((CTypeLib2 *)((char *)this + 360), (CTypeLib2 *)((char *)this - 8)) < 0 )
      {
        goto LABEL_55;
      }
      for ( j = 0; (unsigned int)j < *((_DWORD *)this + 102); j = (unsigned int)(j + 1) )
      {
        v16 = *(unsigned int *)(*((_QWORD *)this + 58) + 4 * j);
        if ( (unsigned int)v16 < *((_DWORD *)this + 161) )
          v17 = *((_QWORD *)this + 82) + v16;
        else
          v17 = 0;
        v18 = *(unsigned int *)(*((_QWORD *)this + 84) + 4 * j);
        if ( (unsigned int)v18 < *((_DWORD *)this + 7) )
          v19 = *((_QWORD *)this + 5) + v18;
        else
          v19 = 0;
        if ( ElemInfoTable32Bit::Write(
               (ElemInfoTable32Bit *)(v17 + 4),
               (CTypeLib2 *)((char *)this - 8),
               (struct ElemInfoTable *)(v19 + 8)) < 0 )
          goto LABEL_55;
      }
      if ( (v20 = *((_DWORD *)v10 + 126), (int)CTypeLib2::WriteSeek((CTypeLib2 *)((char *)this - 8), 0) < 0)
        || (int)CTypeLib2::WriteLibHeader((CTypeLib2 *)((char *)this - 8)) < 0
        || (int)HEAP::Trim((CTypeLib2 *)((char *)this + 640)) < 0
        || (v21 = *((_DWORD *)this + 161)) != 0
        && (v22 = (void *)*((_QWORD *)this + 82),
            *((_DWORD *)this + 160) = *((_DWORD *)v10 + 126),
            (int)CTypeLib2::WriteBytes((CTypeLib2 *)((char *)this - 8), v22, v21) < 0)
        || (int)CTypeLib2::WriteSeek((CTypeLib2 *)((char *)this - 8), v20) < 0 )
      {
LABEL_55:
        v24 = (CTypeLib2 *)((char *)this + 24);
      }
      else
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
        v23 = *((_DWORD *)this + 102);
        v24 = (CTypeLib2 *)((char *)this + 24);
        v25 = (unsigned int *)*((_QWORD *)this + 58);
        *v11 = 0;
        if ( HEAP::UnMap64To32(v26, (CTypeLib2 *)((char *)this - 8), (CTypeLib2 *)((char *)this + 24), v25, v23) >= 0 )
        {
          if ( v4 )
          {
            *((_WORD *)this + 198) = v3 | *((_WORD *)v10 + 202) & 0xFFFC;
            CTypeLib2::MarkAllForReLayout((CTypeLib2 *)((char *)this - 8));
          }
          return 0;
        }
      }
      v9 = HEAP::UnMap64To32(
             v14,
             (CTypeLib2 *)((char *)this - 8),
             v24,
             *((unsigned int **)this + 58),
             *((_DWORD *)v10 + 104));
    }
    if ( v4 )
    {
      *((_WORD *)this + 198) &= 0xFFFCu;
      *((_WORD *)this + 198) |= v3;
      for ( k = 0; (unsigned int)k < *((_DWORD *)this + 102); k = (unsigned int)(k + 1) )
      {
        v28 = *((_QWORD *)this + 58);
        v31[0] = 0;
        result = CTypeLib2::GetTypeInfoOfInfoDef((CTypeLib2 *)((char *)this - 8), *(_DWORD *)(v28 + 4 * k), v31);
        if ( result < 0 )
          return result;
        v9 = CTypeInfo2::SysSpecificLayOut(v31[0], (enum tagSYSKIND)(*((_WORD *)this + 198) & 3));
        CTypeInfo2::Release(v31[0]);
        if ( v9 < 0 )
          return v9;
      }
      *((_DWORD *)this + 166) = *((_WORD *)this + 198) & 3;
    }
    if ( *v11 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
      *v11 = 0;
    }
    v29 = (OLECHAR *)*((_QWORD *)this + 64);
    MultiByteStr[259] = 0;
    v30 = SysStringLen(v29);
    if ( WideCharToMultiByte(0, 0, v29, v30 + 1, MultiByteStr, 259, 0, 0) )
      remove(MultiByteStr);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180030f50  push    rbx
0x180030f52  push    rbp
0x180030f53  push    rsi
0x180030f54  push    rdi
0x180030f55  push    r12
0x180030f57  push    r13
0x180030f59  push    r14
0x180030f5b  push    r15
0x180030f5d  sub     rsp, 178h
0x180030f64  mov     rax, cs:__security_cookie
0x180030f6b  xor     rax, rsp
0x180030f6e  mov     [rsp+1B8h+var_58], rax
0x180030f76  mov     rbx, rcx
0x180030f79  mov     r15d, 3
0x180030f7f  movzx   ecx, word ptr [rcx+18Ch]
0x180030f86  mov     ebp, ecx
0x180030f88  and     ebp, r15d
0x180030f8b  lea     r14d, [r15-2]
0x180030f8f  cmp     ebp, [rbx+29Ch]
0x180030f95  jz      short loc_180030FB4
0x180030f97  movzx   eax, cx
0x180030f9a  mov     r13d, r14d
0x180030f9d  xor     ax, [rbx+29Ch]
0x180030fa4  and     ax, r15w
0x180030fa8  xor     ax, cx
0x180030fab  mov     [rbx+18Ch], ax
0x180030fb2  jmp     short loc_180030FBA
0x180030fb4  mov     ebp, r14d
0x180030fb7  xor     r13d, r13d
0x180030fba  xor     edi, edi
0x180030fbc  cmp     edi, [rbx+198h]
0x180030fc2  jnb     short loc_180031034
0x180030fc4  mov     rax, [rbx+1D0h]
0x180030fcb  mov     edx, [rax+rdi*4]; unsigned int
0x180030fce  cmp     edx, [rbx+1Ch]
0x180030fd1  jb      short loc_180030FD7
0x180030fd3  xor     eax, eax
0x180030fd5  jmp     short loc_180030FDE
0x180030fd7  mov     rax, rdx
0x180030fda  add     rax, [rbx+28h]
0x180030fde  test    byte ptr [rax], 20h
0x180030fe1  jz      short loc_180030FE8
0x180030fe3  test    r13d, r13d
0x180030fe6  jz      short loc_18003102F
0x180030fe8  lea     rcx, [rbx-8]; this
0x180030fec  mov     [rsp+1B8h+var_178], 0
0x180030ff5  lea     r8, [rsp+1B8h+var_178]; struct CTypeInfo2 **
0x180030ffa  call    ?GetTypeInfoOfInfoDef@CTypeLib2@@QEAAJKPEAPEAVCTypeInfo2@@@Z; CTypeLib2::GetTypeInfoOfInfoDef(ulong,CTypeInfo2 * *)
0x180030fff  test    eax, eax
0x180031001  js      loc_180031483
0x180031007  movzx   edx, word ptr [rbx+18Ch]
0x18003100e  mov     rcx, [rsp+1B8h+var_178]; this
0x180031013  and     edx, r15d; enum tagSYSKIND
0x180031016  call    ?SysSpecificLayOut@CTypeInfo2@@QEAAJW4tagSYSKIND@@@Z; CTypeInfo2::SysSpecificLayOut(tagSYSKIND)
0x18003101b  mov     rcx, [rsp+1B8h+var_178]; this
0x180031020  mov     esi, eax
0x180031022  call    ?Release@CTypeInfo2@@UEAAKXZ; CTypeInfo2::Release(void)
0x180031027  test    esi, esi
0x180031029  js      loc_180031481
0x18003102f  add     edi, r14d
0x180031032  jmp     short loc_180030FBC
0x180031034  lea     rdi, [rbx-8]
0x180031038  movzx   eax, word ptr [rdi+194h]
0x18003103f  lea     r12, [rbx+1D8h]
0x180031046  and     eax, r15d
0x180031049  cmp     qword ptr [r12], 0
0x18003104e  mov     [rbx+298h], eax
0x180031054  jz      short loc_180031060
0x180031056  mov     eax, 80070005h
0x18003105b  jmp     loc_180031483
0x180031060  mov     rdx, [rbx+200h]; unsigned __int16 *
0x180031067  mov     r8, r12; struct ILockBytes **
0x18003106a  mov     ecx, r14d; int
0x18003106d  call    ?OpenFileLockBytes@@YAJHPEAGPEAPEAUILockBytes@@@Z; OpenFileLockBytes(int,ushort *,ILockBytes * *)
0x180031072  test    eax, eax
0x180031074  js      loc_180031483
0x18003107a  mov     eax, [rbx+198h]
0x180031080  mov     qword ptr [rbx+1F0h], 0
0x18003108b  test    eax, eax
0x18003108d  jz      short loc_1800310B7
0x18003108f  mov     r9, [rbx+1D0h]; unsigned int *
0x180031096  lea     r8, [rbx+18h]; struct HEAP *
0x18003109a  lea     rcx, [rbx+280h]; this
0x1800310a1  mov     dword ptr [rsp+1B8h+lpMultiByteStr], eax; unsigned int
0x1800310a5  mov     rdx, rdi; struct CTypeLib2 *
0x1800310a8  call    ?Map64To32@HEAP@@QEAAJPEAVCTypeLib2@@PEAV1@PEAKK@Z; HEAP::Map64To32(CTypeLib2 *,HEAP *,ulong *,ulong)
0x1800310ad  mov     esi, eax
0x1800310af  test    eax, eax
0x1800310b1  js      loc_18003137E
0x1800310b7  mov     eax, [rbx+18h]
0x1800310ba  lea     r15, [rbx+280h]
0x1800310c1  mov     [r15], eax
0x1800310c4  mov     rcx, rdi; this
0x1800310c7  mov     eax, [rbx+24h]
0x1800310ca  mov     [rbx+28Ch], eax
0x1800310d0  call    ?WriteLibHeader@CTypeLib2@@QEAAJXZ; CTypeLib2::WriteLibHeader(void)
0x1800310d5  test    eax, eax
0x1800310d7  js      loc_180031356
0x1800310dd  mov     rdx, rdi; struct CTypeLib2 *
0x1800310e0  mov     rcx, r15; this
0x1800310e3  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800310e8  test    eax, eax
0x1800310ea  js      loc_180031356
0x1800310f0  lea     rcx, [rbx+78h]; this
0x1800310f4  mov     rdx, rdi; struct CTypeLib2 *
0x1800310f7  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800310fc  test    eax, eax
0x1800310fe  js      loc_180031356
0x180031104  lea     rcx, [rbx+90h]; this
0x18003110b  mov     rdx, rdi; struct CTypeLib2 *
0x18003110e  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x180031113  test    eax, eax
0x180031115  js      loc_180031356
0x18003111b  lea     rcx, [rbx+60h]; this
0x18003111f  mov     rdx, rdi; struct CTypeLib2 *
0x180031122  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x180031127  test    eax, eax
0x180031129  js      loc_180031356
0x18003112f  lea     rcx, [rbx+30h]; this
0x180031133  mov     rdx, rdi; struct CTypeLib2 *
0x180031136  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x18003113b  test    eax, eax
0x18003113d  js      loc_180031356
0x180031143  lea     rcx, [rbx+48h]; this
0x180031147  mov     rdx, rdi; struct CTypeLib2 *
0x18003114a  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x18003114f  test    eax, eax
0x180031151  js      loc_180031356
0x180031157  lea     rcx, [rbx+0A8h]; this
0x18003115e  mov     rdx, rdi; struct CTypeLib2 *
0x180031161  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x180031166  test    eax, eax
0x180031168  js      loc_180031356
0x18003116e  lea     rcx, [rbx+0C0h]; this
0x180031175  mov     rdx, rdi; struct CTypeLib2 *
0x180031178  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x18003117d  test    eax, eax
0x18003117f  js      loc_180031356
0x180031185  lea     rcx, [rbx+0D8h]; this
0x18003118c  mov     rdx, rdi; struct CTypeLib2 *
0x18003118f  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x180031194  test    eax, eax
0x180031196  js      loc_180031356
0x18003119c  lea     rcx, [rbx+0F0h]; this
0x1800311a3  mov     rdx, rdi; struct CTypeLib2 *
0x1800311a6  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800311ab  test    eax, eax
0x1800311ad  js      loc_180031356
0x1800311b3  lea     rcx, [rbx+108h]; this
0x1800311ba  mov     rdx, rdi; struct CTypeLib2 *
0x1800311bd  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800311c2  test    eax, eax
0x1800311c4  js      loc_180031356
0x1800311ca  lea     rcx, [rbx+120h]; this
0x1800311d1  mov     rdx, rdi; struct CTypeLib2 *
0x1800311d4  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800311d9  test    eax, eax
0x1800311db  js      loc_180031356
0x1800311e1  lea     rcx, [rbx+138h]; this
0x1800311e8  mov     rdx, rdi; struct CTypeLib2 *
0x1800311eb  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x1800311f0  test    eax, eax
0x1800311f2  js      loc_180031356
0x1800311f8  lea     rcx, [rbx+150h]; this
0x1800311ff  mov     rdx, rdi; struct CTypeLib2 *
0x180031202  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x180031207  test    eax, eax
0x180031209  js      loc_180031356
0x18003120f  lea     rcx, [rbx+168h]; this
0x180031216  mov     rdx, rdi; struct CTypeLib2 *
0x180031219  call    ?WriteHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z; HEAP::WriteHeap(CTypeLib2 *)
0x18003121e  test    eax, eax
0x180031220  js      loc_180031356
0x180031226  xor     esi, esi
0x180031228  cmp     esi, [rbx+198h]
0x18003122e  jnb     short loc_180031285
0x180031230  mov     rax, [rbx+1D0h]
0x180031237  mov     ecx, [rax+rsi*4]
0x18003123a  cmp     ecx, [rbx+284h]
0x180031240  jb      short loc_180031246
0x180031242  xor     ecx, ecx
0x180031244  jmp     short loc_18003124D
0x180031246  add     rcx, [rbx+290h]
0x18003124d  mov     rax, [rbx+2A0h]
0x180031254  mov     edx, [rax+rsi*4]
0x180031257  cmp     edx, [rbx+1Ch]
0x18003125a  jb      short loc_180031261
0x18003125c  xor     r8d, r8d
0x18003125f  jmp     short loc_180031268
0x180031261  mov     r8, rdx
0x180031264  add     r8, [rbx+28h]
0x180031268  add     r8, 8; struct ElemInfoTable *
0x18003126c  add     rcx, 4; this
0x180031270  mov     rdx, rdi; struct CTypeLib2 *
0x180031273  call    ?Write@ElemInfoTable32Bit@@QEAAJPEAVCTypeLib2@@PEAVElemInfoTable@@@Z; ElemInfoTable32Bit::Write(CTypeLib2 *,ElemInfoTable *)
0x180031278  test    eax, eax
0x18003127a  js      loc_180031356
0x180031280  add     esi, r14d
0x180031283  jmp     short loc_180031228
0x180031285  mov     esi, [rdi+1F8h]
0x18003128b  xor     edx, edx; unsigned int
0x18003128d  mov     rcx, rdi; this
0x180031290  call    ?WriteSeek@CTypeLib2@@QEAAJK@Z; CTypeLib2::WriteSeek(ulong)
0x180031295  test    eax, eax
0x180031297  js      loc_180031356
0x18003129d  mov     rcx, rdi; this
0x1800312a0  call    ?WriteLibHeader@CTypeLib2@@QEAAJXZ; CTypeLib2::WriteLibHeader(void)
0x1800312a5  test    eax, eax
0x1800312a7  js      loc_180031356
0x1800312ad  mov     rcx, r15; this
0x1800312b0  call    ?Trim@HEAP@@AEAAJXZ; HEAP::Trim(void)
0x1800312b5  test    eax, eax
0x1800312b7  js      loc_180031356
0x1800312bd  mov     r8d, [r15+4]; unsigned int
0x1800312c1  test    r8d, r8d
0x1800312c4  jz      short loc_1800312DF
0x1800312c6  mov     eax, [rdi+1F8h]
0x1800312cc  mov     rcx, rdi; this
0x1800312cf  mov     rdx, [r15+10h]; void *
0x1800312d3  mov     [r15], eax
0x1800312d6  call    ?WriteBytes@CTypeLib2@@QEAAJPEAXK@Z; CTypeLib2::WriteBytes(void *,ulong)
0x1800312db  test    eax, eax
0x1800312dd  js      short loc_180031356
0x1800312df  mov     edx, esi; unsigned int
0x1800312e1  mov     rcx, rdi; this
0x1800312e4  call    ?WriteSeek@CTypeLib2@@QEAAJK@Z; CTypeLib2::WriteSeek(ulong)
0x1800312e9  test    eax, eax
0x1800312eb  js      short loc_180031356
0x1800312ed  mov     rcx, [r12]
0x1800312f1  mov     rax, [rcx]
0x1800312f4  mov     rax, [rax+10h]
0x1800312f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312fd  mov     eax, [rbx+198h]
0x180031303  lea     rsi, [rbx+18h]
0x180031307  mov     r9, [rbx+1D0h]; unsigned int *
0x18003130e  mov     r8, rsi; struct HEAP *
0x180031311  mov     rdx, rdi; struct CTypeLib2 *
0x180031314  mov     qword ptr [r12], 0
0x18003131c  mov     dword ptr [rsp+1B8h+lpMultiByteStr], eax; unsigned int
0x180031320  call    ?UnMap64To32@HEAP@@QEAAJPEAVCTypeLib2@@PEAV1@PEAKK@Z; HEAP::UnMap64To32(CTypeLib2 *,HEAP *,ulong *,ulong)
0x180031325  test    eax, eax
0x180031327  js      short loc_18003135A
0x180031329  test    r13d, r13d
0x18003132c  jz      short loc_18003134F
0x18003132e  movzx   eax, word ptr [rdi+194h]
0x180031335  mov     ecx, 0FFFCh
0x18003133a  and     ax, cx
0x18003133d  mov     rcx, rdi; this
0x180031340  or      ax, bp
0x180031343  mov     [rbx+18Ch], ax
0x18003134a  call    ?MarkAllForReLayout@CTypeLib2@@AEAAXXZ; CTypeLib2::MarkAllForReLayout(void)
0x18003134f  xor     eax, eax
0x180031351  jmp     loc_180031483
0x180031356  lea     rsi, [rbx+18h]
0x18003135a  mov     eax, [rdi+1A0h]
0x180031360  mov     r8, rsi; struct HEAP *
0x180031363  mov     r9, [rbx+1D0h]; unsigned int *
0x18003136a  mov     rdx, rdi; struct CTypeLib2 *
0x18003136d  mov     dword ptr [rsp+1B8h+lpMultiByteStr], eax; unsigned int
0x180031371  call    ?UnMap64To32@HEAP@@QEAAJPEAVCTypeLib2@@PEAV1@PEAKK@Z; HEAP::UnMap64To32(CTypeLib2 *,HEAP *,ulong *,ulong)
0x180031376  mov     esi, eax
0x180031378  mov     r15d, 3
0x18003137e  test    r13d, r13d
0x180031381  jz      loc_180031409
0x180031387  mov     ecx, 0FFFCh
0x18003138c  and     [rbx+18Ch], cx
0x180031393  or      [rbx+18Ch], bp
0x18003139a  xor     ebp, ebp
0x18003139c  cmp     ebp, [rbx+198h]
0x1800313a2  jnb     short loc_1800313F9
0x1800313a4  mov     rdx, [rbx+1D0h]
0x1800313ab  lea     r8, [rsp+1B8h+var_178]; struct CTypeInfo2 **
0x1800313b0  mov     rcx, rdi; this
0x1800313b3  mov     [rsp+1B8h+var_178], 0
0x1800313bc  mov     edx, [rdx+rbp*4]; unsigned int
0x1800313bf  call    ?GetTypeInfoOfInfoDef@CTypeLib2@@QEAAJKPEAPEAVCTypeInfo2@@@Z; CTypeLib2::GetTypeInfoOfInfoDef(ulong,CTypeInfo2 * *)
0x1800313c4  test    eax, eax
0x1800313c6  js      loc_180031483
0x1800313cc  movzx   edx, word ptr [rbx+18Ch]
0x1800313d3  mov     rcx, [rsp+1B8h+var_178]; this
0x1800313d8  and     edx, r15d; enum tagSYSKIND
0x1800313db  call    ?SysSpecificLayOut@CTypeInfo2@@QEAAJW4tagSYSKIND@@@Z; CTypeInfo2::SysSpecificLayOut(tagSYSKIND)
0x1800313e0  mov     rcx, [rsp+1B8h+var_178]; this
0x1800313e5  mov     esi, eax
0x1800313e7  call    ?Release@CTypeInfo2@@UEAAKXZ; CTypeInfo2::Release(void)
0x1800313ec  test    esi, esi
0x1800313ee  js      loc_180031481
0x1800313f4  add     ebp, r14d
0x1800313f7  jmp     short loc_18003139C
0x1800313f9  movzx   eax, word ptr [rbx+18Ch]
0x180031400  and     eax, r15d
0x180031403  mov     [rbx+298h], eax
0x180031409  mov     rcx, [r12]
0x18003140d  test    rcx, rcx
0x180031410  jz      short loc_180031426
0x180031412  mov     rax, [rcx]
0x180031415  mov     rax, [rax+10h]
0x180031419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003141e  mov     qword ptr [r12], 0
0x180031426  mov     rbx, [rbx+200h]
  ... truncated ...
```
