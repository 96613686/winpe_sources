# CTieredVolume::UpdateTierTraitsListFromFsctlResponse(_FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *)

- ea: `0x140016a44`
- end: `0x140016d0f`
- name: `?UpdateTierTraitsListFromFsctlResponse@CTieredVolume@@AEAAXPEAU_FSCTL_QUERY_STORAGE_CLASSES_OUTPUT@@@Z`
- size: `715`
- prototype: `void __fastcall(CTieredVolume *__hidden this, struct _FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x140016d18`

## callees

- `0x140001a00`
- `0x140001a18`
- `0x140004e44`
- `0x140014e28`
- `0x140016a44`
- `0x140017930`
- `0x140017e78`
- `0x1400181a0`

## import_xrefs

- `msvcrt!malloc` at `0x140016bed`
- `msvcrt!malloc` at `0x140016bed`

## pseudocode

```c
void __fastcall CTieredVolume::UpdateTierTraitsListFromFsctlResponse(
        CTieredVolume *this,
        struct _FSCTL_QUERY_STORAGE_CLASSES_OUTPUT *a2)
{
  int v4; // r13d
  int v5; // r15d
  __int64 v6; // rsi
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // edx
  __int64 v10; // r9
  _OWORD *v11; // rax
  _OWORD *v12; // rcx
  __int128 v13; // xmm1
  _QWORD *v14; // rcx
  int v15; // edx
  __int64 v16; // rsi
  unsigned __int64 v17; // rcx
  _QWORD *v18; // rax
  int v19; // r8d
  _QWORD *i; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int64 **v23; // rax

  ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll((__int64 *)this + 4);
  *((_WORD *)this + 80) = 0;
  if ( (*((_DWORD *)a2 + 2) & 0x20000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        144,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (char *)this + 672);
    }
  }
  else
  {
    v4 = 0;
    v5 = 0;
    if ( *((_DWORD *)a2 + 4) )
    {
      while ( 1 )
      {
        v6 = 1064LL * v5;
        if ( (*(_DWORD *)((_BYTE *)a2 + v6 + 1064) & 0x400000LL) == 0 )
          break;
LABEL_30:
        if ( (unsigned int)++v5 >= *((_DWORD *)a2 + 4) )
          goto LABEL_31;
      }
      v7 = operator new(0x214u);
      v8 = v7;
      if ( v7 )
        *v7 = 0;
      else
        v8 = 0;
      v9 = *(_DWORD *)((char *)a2 + v6 + 1084);
      *v8 = v9;
      v10 = 4;
      v11 = v8 + 1;
      v12 = (_OWORD *)((char *)a2 + v6 + 40);
      *(_OWORD *)(v8 + 129) = *(_OWORD *)((char *)a2 + v6 + 24);
      do
      {
        *v11 = *v12;
        v11[1] = v12[1];
        v11[2] = v12[2];
        v11[3] = v12[3];
        v11[4] = v12[4];
        v11[5] = v12[5];
        v11[6] = v12[6];
        v13 = v12[7];
        v12 += 8;
        v11[7] = v13;
        v11 += 8;
        --v10;
      }
      while ( v10 );
      *((_WORD *)v8 + 257) = 0;
      if ( v9 == 2 )
      {
        *((_BYTE *)this + 160) = 1;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_19;
        }
        v15 = 141;
      }
      else
      {
        *((_BYTE *)this + 161) = 1;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_19;
        }
        v15 = 142;
      }
      WPP_SF_Z_guid_(v14[2], v15, (_DWORD)v8 + 516, (_DWORD)this + 672, (__int64)(v8 + 129));
LABEL_19:
      v16 = *((_QWORD *)this + 5);
      if ( !*((_QWORD *)this + 8) )
      {
        v17 = *((unsigned int *)this + 18);
        if ( *((_DWORD *)this + 18) )
        {
          if ( 0xFFFFFFFFFFFFFFFFuLL / v17 < 0x18 )
            goto LABEL_40;
          v17 *= 24LL;
        }
        v18 = malloc(v17 + 8);
        if ( !v18 )
LABEL_40:
          ATL::AtlThrowImpl(-2147024882);
        *v18 = *((_QWORD *)this + 7);
        *((_QWORD *)this + 7) = v18;
        v19 = *((_DWORD *)this + 18) - 1;
        for ( i = &v18[2 * v19 + 1 + (unsigned int)v19]; v19 >= 0; --v19 )
        {
          *i = *((_QWORD *)this + 8);
          *((_QWORD *)this + 8) = i;
          i -= 3;
        }
      }
      v21 = (__int64 *)*((_QWORD *)this + 8);
      ++v4;
      v22 = *v21;
      v21[2] = (__int64)v8;
      *((_QWORD *)this + 8) = v22;
      v21[1] = v16;
      *v21 = 0;
      ++*((_QWORD *)this + 6);
      v23 = (__int64 **)*((_QWORD *)this + 5);
      if ( v23 )
        *v23 = v21;
      else
        *((_QWORD *)this + 4) = v21;
      *((_QWORD *)this + 5) = v21;
      operator delete(0);
      goto LABEL_30;
    }
LABEL_31:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        v4,
        (__int64)this + 672);
    }
  }
}

```

## disassembly

```asm
0x140016a44  push    rbx
0x140016a46  push    rbp
0x140016a47  push    rsi
0x140016a48  push    rdi
0x140016a49  push    r12
0x140016a4b  push    r13
0x140016a4d  push    r14
0x140016a4f  push    r15
0x140016a51  sub     rsp, 38h
0x140016a55  mov     rbx, rcx
0x140016a58  mov     r14, rdx
0x140016a5b  add     rcx, 20h ; ' '
0x140016a5f  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)
0x140016a64  xor     edi, edi
0x140016a66  lea     rbp, WPP_GLOBAL_Control
0x140016a6d  mov     [rbx+0A0h], di
0x140016a74  test    dword ptr [r14+8], 20000000h
0x140016a7c  jnz     loc_140016CBF
0x140016a82  mov     r13d, edi
0x140016a85  mov     r15d, edi
0x140016a88  cmp     [r14+10h], edi
0x140016a8c  jbe     loc_140016C81
0x140016a92  movsxd  rax, r15d
0x140016a95  imul    rsi, rax, 428h
0x140016a9c  mov     eax, [rsi+r14+428h]
0x140016aa4  bt      rax, 16h
0x140016aa9  jb      loc_140016C74
0x140016aaf  mov     ecx, 214h; Size
0x140016ab4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016ab9  mov     [rsp+78h+arg_0], rax
0x140016ac1  mov     rdi, rax
0x140016ac4  test    rax, rax
0x140016ac7  jz      short loc_140016AD1
0x140016ac9  mov     dword ptr [rax], 0
0x140016acf  jmp     short loc_140016AD3
0x140016ad1  xor     edi, edi
0x140016ad3  mov     edx, [rsi+r14+43Ch]
0x140016adb  lea     r8, [rdi+204h]
0x140016ae2  mov     [rdi], edx
0x140016ae4  lea     rcx, [r14+28h]
0x140016ae8  movups  xmm0, xmmword ptr [rsi+r14+18h]
0x140016aee  mov     r9d, 4
0x140016af4  lea     rax, [rdi+4]
0x140016af8  add     rcx, rsi
0x140016afb  movdqu  xmmword ptr [r8], xmm0
0x140016b00  lea     r10d, [r9+7Ch]
0x140016b04  movups  xmm0, xmmword ptr [rcx]
0x140016b07  movups  xmmword ptr [rax], xmm0
0x140016b0a  movups  xmm1, xmmword ptr [rcx+10h]
0x140016b0e  movups  xmmword ptr [rax+10h], xmm1
0x140016b12  movups  xmm0, xmmword ptr [rcx+20h]
0x140016b16  movups  xmmword ptr [rax+20h], xmm0
0x140016b1a  movups  xmm1, xmmword ptr [rcx+30h]
0x140016b1e  movups  xmmword ptr [rax+30h], xmm1
0x140016b22  movups  xmm0, xmmword ptr [rcx+40h]
0x140016b26  movups  xmmword ptr [rax+40h], xmm0
0x140016b2a  movups  xmm1, xmmword ptr [rcx+50h]
0x140016b2e  movups  xmmword ptr [rax+50h], xmm1
0x140016b32  movups  xmm0, xmmword ptr [rcx+60h]
0x140016b36  movups  xmmword ptr [rax+60h], xmm0
0x140016b3a  movups  xmm1, xmmword ptr [rcx+70h]
0x140016b3e  add     rcx, r10
0x140016b41  movups  xmmword ptr [rax+70h], xmm1
0x140016b45  add     rax, r10
0x140016b48  sub     r9, 1
0x140016b4c  jnz     short loc_140016B04
0x140016b4e  xor     eax, eax
0x140016b50  mov     [rdi+202h], ax
0x140016b57  cmp     edx, 2
0x140016b5a  jnz     short loc_140016B82
0x140016b5c  mov     byte ptr [rbx+0A0h], 1
0x140016b63  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b6a  cmp     rcx, rbp
0x140016b6d  jz      short loc_140016BBB
0x140016b6f  test    byte ptr [rcx+1Ch], 1
0x140016b73  jz      short loc_140016BBB
0x140016b75  cmp     byte ptr [rcx+19h], 4
0x140016b79  jb      short loc_140016BBB
0x140016b7b  mov     edx, 8Dh
0x140016b80  jmp     short loc_140016BA6
0x140016b82  mov     byte ptr [rbx+0A1h], 1
0x140016b89  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b90  cmp     rcx, rbp
0x140016b93  jz      short loc_140016BBB
0x140016b95  test    byte ptr [rcx+1Ch], 1
0x140016b99  jz      short loc_140016BBB
0x140016b9b  cmp     byte ptr [rcx+19h], 4
0x140016b9f  jb      short loc_140016BBB
0x140016ba1  mov     edx, 8Eh
0x140016ba6  mov     rcx, [rcx+10h]
0x140016baa  lea     r9, [rbx+2A0h]
0x140016bb1  mov     [rsp+78h+var_58], r8
0x140016bb6  call    WPP_SF_Z_guid_
0x140016bbb  cmp     qword ptr [rbx+40h], 0
0x140016bc0  mov     rsi, [rbx+28h]
0x140016bc4  jnz     short loc_140016C36
0x140016bc6  mov     ecx, [rbx+48h]
0x140016bc9  test    rcx, rcx
0x140016bcc  jz      short loc_140016BE9
0x140016bce  xor     edx, edx
0x140016bd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016bd4  div     rcx
0x140016bd7  cmp     rax, 18h
0x140016bdb  jb      loc_140016D04
0x140016be1  lea     rcx, [rcx+rcx*2]
0x140016be5  shl     rcx, 3
0x140016be9  add     rcx, 8; Size
0x140016bed  call    cs:__imp_malloc
0x140016bf3  test    rax, rax
0x140016bf6  jz      loc_140016D04
0x140016bfc  mov     rcx, [rbx+38h]
0x140016c00  mov     [rax], rcx
0x140016c03  mov     [rbx+38h], rax
0x140016c07  mov     r8d, [rbx+48h]
0x140016c0b  sub     r8d, 1
0x140016c0f  lea     rcx, ds:1[r8*2]
0x140016c17  lea     rcx, [rcx+r8]
0x140016c1b  lea     rcx, [rax+rcx*8]
0x140016c1f  js      short loc_140016C36
0x140016c21  mov     rax, [rbx+40h]
0x140016c25  mov     [rcx], rax
0x140016c28  mov     [rbx+40h], rcx
0x140016c2c  sub     rcx, 18h
0x140016c30  sub     r8d, 1
0x140016c34  jns     short loc_140016C21
0x140016c36  mov     rcx, [rbx+40h]
0x140016c3a  inc     r13d
0x140016c3d  mov     rax, [rcx]
0x140016c40  mov     [rcx+10h], rdi
0x140016c44  mov     [rbx+40h], rax
0x140016c48  mov     [rcx+8], rsi
0x140016c4c  mov     qword ptr [rcx], 0
0x140016c53  inc     qword ptr [rbx+30h]
0x140016c57  mov     rax, [rbx+28h]
0x140016c5b  test    rax, rax
0x140016c5e  jz      short loc_140016C65
0x140016c60  mov     [rax], rcx
0x140016c63  jmp     short loc_140016C69
0x140016c65  mov     [rbx+20h], rcx
0x140016c69  mov     [rbx+28h], rcx
0x140016c6d  xor     ecx, ecx; Block
0x140016c6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140016c74  inc     r15d
0x140016c77  cmp     r15d, [r14+10h]
0x140016c7b  jb      loc_140016A92
0x140016c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c88  cmp     rcx, rbp
0x140016c8b  jz      short loc_140016CF3
0x140016c8d  test    byte ptr [rcx+1Ch], 1
0x140016c91  jz      short loc_140016CF3
0x140016c93  cmp     byte ptr [rcx+19h], 4
0x140016c97  jb      short loc_140016CF3
0x140016c99  mov     rcx, [rcx+10h]
0x140016c9d  lea     rax, [rbx+2A0h]
0x140016ca4  mov     edx, 8Fh
0x140016ca9  mov     [rsp+78h+var_58], rax
0x140016cae  mov     r9d, r13d
0x140016cb1  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016cb8  call    WPP_SF_dZ
0x140016cbd  jmp     short loc_140016CF3
0x140016cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140016cc6  cmp     rcx, rbp
0x140016cc9  jz      short loc_140016CF3
0x140016ccb  test    byte ptr [rcx+1Ch], 1
0x140016ccf  jz      short loc_140016CF3
0x140016cd1  cmp     byte ptr [rcx+19h], 4
0x140016cd5  jb      short loc_140016CF3
0x140016cd7  mov     rcx, [rcx+10h]
0x140016cdb  lea     r9, [rbx+2A0h]
0x140016ce2  mov     edx, 90h
0x140016ce7  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016cee  call    WPP_SF_Z
0x140016cf3  add     rsp, 38h
0x140016cf7  pop     r15
0x140016cf9  pop     r14
0x140016cfb  pop     r13
0x140016cfd  pop     r12
0x140016cff  pop     rdi
0x140016d00  pop     rsi
0x140016d01  pop     rbp
0x140016d02  pop     rbx
0x140016d03  retn
0x140016d04  mov     ecx, 8007000Eh; int
0x140016d09  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
