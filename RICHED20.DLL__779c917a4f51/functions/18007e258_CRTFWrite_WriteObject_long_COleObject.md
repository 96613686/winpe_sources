# CRTFWrite::WriteObject(long,COleObject *)

- ea: `0x18007e258`
- end: `0x18007e5c4`
- name: `?WriteObject@CRTFWrite@@AEAAHJPEAVCOleObject@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, int, struct COleObject *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x180028064`

## callees

- `0x180028e40`
- `0x180029548`
- `0x18002a1e8`
- `0x180038bd0`
- `0x18004a8fc`
- `0x180054398`
- `0x18007d5a0`
- `0x18007d7bc`
- `0x18007da2c`
- `0x18007e0ac`
- `0x18007e258`
- `0x18007e5cc`
- `0x18007e6a0`
- `0x18008d624`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalSize` at `0x18007e2ee`
- `KERNEL32!GlobalSize` at `0x18007e2ee`
- `KERNEL32!GlobalLock` at `0x18007e2e1`
- `KERNEL32!GlobalLock` at `0x18007e2e1`
- `KERNEL32!GlobalUnlock` at `0x18007e363`
- `KERNEL32!GlobalUnlock` at `0x18007e58b`
- `KERNEL32!GlobalUnlock` at `0x18007e363`
- `KERNEL32!GlobalUnlock` at `0x18007e58b`
- `KERNEL32!GlobalHandle` at `0x18007e57f`
- `KERNEL32!GlobalHandle` at `0x18007e57f`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteObject(CRTFWrite *this, LONG a2, HGLOBAL *a3)
{
  CRTFWrite *v6; // rcx
  struct _reobject *v7; // rdx
  HGLOBAL v8; // r14
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  __int16 v12; // ax
  struct _reobject *v13; // rdx
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rbx
  struct _reobject *v16; // rdx
  HGLOBAL v17; // rbx
  _WORD v19[6]; // [rsp+20h] [rbp-89h] BYREF
  int v20; // [rsp+2Ch] [rbp-7Dh]
  int v21; // [rsp+30h] [rbp-79h]
  int v22; // [rsp+34h] [rbp-75h]
  int v23; // [rsp+38h] [rbp-71h]
  int v24; // [rsp+3Ch] [rbp-6Dh]
  __int16 v25; // [rsp+40h] [rbp-69h]
  __int16 v26; // [rsp+42h] [rbp-67h]
  unsigned __int16 *v27; // [rsp+58h] [rbp-51h]
  unsigned __int16 *v28; // [rsp+60h] [rbp-49h]
  HGLOBAL hMem; // [rsp+70h] [rbp-39h]
  int v30; // [rsp+78h] [rbp-31h]
  _reobject v31; // [rsp+80h] [rbp-29h] BYREF

  memset_0(v19, 0, 0x60u);
  memset_0(&v31, 0, sizeof(v31));
  v31.cbStruct = 72;
  v31.cp = a2;
  COleObject::GetObjectData((COleObject *)a3, &v31, 7u);
  CRTFWrite::GetRtfObject(v6, &v31, (struct _rtfobject *)v19);
  v8 = a3[15];
  if ( v8 )
  {
    v9 = a3[17];
    hMem = GlobalLock(a3[15]);
    v10 = GlobalSize(v8);
    v19[0] = 2;
    v30 = v10;
    v21 = (__int16)CW32System::MulDiv(v31.sizel.cx, 72, 127);
    v11 = (__int16)CW32System::MulDiv(v31.sizel.cy, 72, 127);
    v23 = *v9;
    v24 = v9[1];
    v25 = *((_WORD *)v9 + 4);
    v26 = *((_WORD *)v9 + 5);
    v12 = *((_WORD *)v9 + 6);
    v22 = v11;
    v19[4] = v12;
    CRTFWrite::WriteDib(this, v13, (struct _rtfobject *)v19);
    GlobalUnlock(hMem);
    if ( v31.pstg )
      ((void (__fastcall *)(LPSTORAGE))v31.pstg->lpVtbl->Release)(v31.pstg);
    if ( v31.polesite )
      ((void (__fastcall *)(LPOLECLIENTSITE))v31.polesite->lpVtbl->Release)(v31.polesite);
    if ( v31.poleobj )
      ((void (__fastcall *)(LPOLEOBJECT))v31.poleobj->lpVtbl->Release)(v31.poleobj);
  }
  else
  {
    if ( v19[0] && (unsigned int)(v19[0] - 1) >= 2 )
    {
      CRTFWrite::PutCtrlWord(this, 2, 134, 0);
      CRTFWrite::PutCtrlWord(this, 0, *((unsigned __int16 *)qword_180099F28 + v19[0]), 0);
      v14 = v27;
      if ( v27 )
      {
        CRTFWrite::PutCtrlWord(this, 3, 128, 0);
        CRTFWrite::WritePcData(this, v14, 0, 0);
        CRTFWrite::PutChar(this, 125);
      }
      v15 = v28;
      if ( v28 )
      {
        CRTFWrite::PutCtrlWord(this, 3, 139, 0);
        CRTFWrite::WritePcData(this, v15, 0, 0);
        CRTFWrite::PutChar(this, 125);
      }
      if ( v20 )
        CRTFWrite::PutCtrlWord(this, 0, 143, 0);
      CRTFWrite::WriteRtfObject(this, (struct _rtfobject *)v19, 0);
      CRTFWrite::PutCtrlWord(this, 3, 133, 0);
      CRTFWrite::Puts(this, qword_180099F48, 2);
      if ( (unsigned int)CRTFWrite::ObjectWriteToEditstream(this, &v31, (struct _rtfobject *)v19) )
      {
        CRTFWrite::PutChar(this, 125);
        CRTFWrite::PutCtrlWord(this, 2, 188, 0);
        CRTFWrite::WritePicture(this, v16, (struct _rtfobject *)v19);
      }
      else if ( !*((_DWORD *)this + 12) )
      {
        *((_DWORD *)this + 12) = 19;
      }
      CRTFWrite::PutChar(this, 125);
      CRTFWrite::PutChar(this, 125);
    }
    else
    {
      CRTFWrite::WritePicture(this, v7, (struct _rtfobject *)v19);
    }
    if ( v31.pstg )
      ((void (__fastcall *)(LPSTORAGE))v31.pstg->lpVtbl->Release)(v31.pstg);
    if ( v31.polesite )
      ((void (__fastcall *)(LPOLECLIENTSITE))v31.polesite->lpVtbl->Release)(v31.polesite);
    if ( v31.poleobj )
      ((void (__fastcall *)(LPOLEOBJECT))v31.poleobj->lpVtbl->Release)(v31.poleobj);
    if ( hMem )
    {
      v17 = GlobalHandle(hMem);
      GlobalUnlock(v17);
      CW32System::GlobalFree(v17);
    }
    if ( v27 )
      CW32System::CoTaskMemFree(v27);
  }
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x18007e258  push    rbp
0x18007e25a  push    rbx
0x18007e25b  push    rsi
0x18007e25c  push    rdi
0x18007e25d  push    r14
0x18007e25f  lea     rbp, [rsp-37h]
0x18007e264  sub     rsp, 0E0h
0x18007e26b  mov     rax, cs:__security_cookie
0x18007e272  xor     rax, rsp
0x18007e275  mov     [rbp+57h+var_30], rax
0x18007e279  mov     ebx, edx
0x18007e27b  mov     rsi, r8
0x18007e27e  xor     edx, edx; Val
0x18007e280  mov     rdi, rcx
0x18007e283  lea     rcx, [rsp+100h+var_E0]; void *
0x18007e288  lea     r8d, [rdx+60h]; Size
0x18007e28c  call    memset_0
0x18007e291  xor     edx, edx; Val
0x18007e293  lea     rcx, [rbp+57h+var_80]; void *
0x18007e297  lea     r8d, [rdx+48h]; Size
0x18007e29b  call    memset_0
0x18007e2a0  mov     r8d, 7; unsigned int
0x18007e2a6  mov     [rbp+57h+var_80.cbStruct], 48h ; 'H'
0x18007e2ad  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x18007e2b1  mov     [rbp+57h+var_80.cp], ebx
0x18007e2b4  mov     rcx, rsi; this
0x18007e2b7  call    ?GetObjectData@COleObject@@QEAAJPEAU_reobject@@K@Z; COleObject::GetObjectData(_reobject *,ulong)
0x18007e2bc  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e2c1  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x18007e2c5  call    ?GetRtfObject@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::GetRtfObject(_reobject &,_rtfobject &)
0x18007e2ca  mov     r14, [rsi+78h]
0x18007e2ce  test    r14, r14
0x18007e2d1  jz      loc_18007E3B1
0x18007e2d7  mov     rbx, [rsi+88h]
0x18007e2de  mov     rcx, r14; hMem
0x18007e2e1  call    cs:__imp_GlobalLock
0x18007e2e7  mov     rcx, r14; hMem
0x18007e2ea  mov     [rbp+57h+hMem], rax
0x18007e2ee  call    cs:__imp_GlobalSize
0x18007e2f4  mov     ecx, [rbp+57h+var_80.sizel.cx]; int
0x18007e2f7  mov     esi, 2
0x18007e2fc  mov     [rsp+100h+var_E0], si
0x18007e301  mov     esi, 7Fh
0x18007e306  mov     r8d, esi; int
0x18007e309  mov     [rbp+57h+var_88], eax
0x18007e30c  lea     edx, [rsi-37h]; int
0x18007e30f  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007e314  movsx   ecx, ax
0x18007e317  lea     edx, [rsi-37h]; int
0x18007e31a  mov     [rbp+57h+var_D0], ecx
0x18007e31d  mov     r8d, esi; int
0x18007e320  mov     ecx, [rbp+57h+var_80.sizel.cy]; int
0x18007e323  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007e328  movsx   ecx, ax
0x18007e32b  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e330  mov     eax, [rbx]
0x18007e332  mov     [rbp+57h+var_C8], eax
0x18007e335  mov     eax, [rbx+4]
0x18007e338  mov     [rbp+57h+var_C4], eax
0x18007e33b  movzx   eax, word ptr [rbx+8]
0x18007e33f  mov     [rbp+57h+var_C0], ax
0x18007e343  movzx   eax, word ptr [rbx+0Ah]
0x18007e347  mov     [rbp+57h+var_BE], ax
0x18007e34b  movzx   eax, word ptr [rbx+0Ch]
0x18007e34f  mov     [rbp+57h+var_CC], ecx
0x18007e352  mov     rcx, rdi; this
0x18007e355  mov     [rsp+100h+var_D8], ax
0x18007e35a  call    ?WriteDib@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WriteDib(_reobject &,_rtfobject &)
0x18007e35f  mov     rcx, [rbp+57h+hMem]; hMem
0x18007e363  call    cs:__imp_GlobalUnlock
0x18007e369  mov     rcx, [rbp+57h+var_80.pstg]
0x18007e36d  test    rcx, rcx
0x18007e370  jz      short loc_18007E37E
0x18007e372  mov     rax, [rcx]
0x18007e375  mov     rax, [rax+10h]
0x18007e379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e37e  mov     rcx, [rbp+57h+var_80.polesite]
0x18007e382  test    rcx, rcx
0x18007e385  jz      short loc_18007E393
0x18007e387  mov     rax, [rcx]
0x18007e38a  mov     rax, [rax+10h]
0x18007e38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e393  mov     rcx, [rbp+57h+var_80.poleobj]
0x18007e397  test    rcx, rcx
0x18007e39a  jz      loc_18007E5A7
0x18007e3a0  mov     rdx, [rcx]
0x18007e3a3  mov     rax, [rdx+10h]
0x18007e3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e3ac  jmp     loc_18007E5A7
0x18007e3b1  movsx   ecx, [rsp+100h+var_E0]
0x18007e3b6  test    ecx, ecx
0x18007e3b8  jz      loc_18007E52A
0x18007e3be  sub     ecx, 1
0x18007e3c1  jz      loc_18007E52A
0x18007e3c7  cmp     ecx, 1
0x18007e3ca  jz      loc_18007E52A
0x18007e3d0  xor     r9d, r9d; int
0x18007e3d3  mov     r8d, 86h; int
0x18007e3d9  mov     rcx, rdi; this
0x18007e3dc  lea     esi, [r9+2]
0x18007e3e0  mov     edx, esi; int
0x18007e3e2  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e3e7  movsx   rax, [rsp+100h+var_E0]
0x18007e3ed  lea     rcx, qword_180099F28
0x18007e3f4  xor     r9d, r9d; int
0x18007e3f7  xor     edx, edx; int
0x18007e3f9  movzx   r8d, word ptr [rcx+rax*2]; int
0x18007e3fe  mov     rcx, rdi; this
0x18007e401  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e406  mov     rbx, [rbp+57h+var_A8]
0x18007e40a  lea     r14d, [rsi+1]
0x18007e40e  test    rbx, rbx
0x18007e411  jz      short loc_18007E440
0x18007e413  xor     r9d, r9d; int
0x18007e416  lea     r8d, [rsi+7Eh]; int
0x18007e41a  mov     edx, r14d; int
0x18007e41d  mov     rcx, rdi; this
0x18007e420  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e425  xor     r9d, r9d; int
0x18007e428  xor     r8d, r8d; unsigned int
0x18007e42b  mov     rdx, rbx; unsigned __int16 *
0x18007e42e  mov     rcx, rdi; this
0x18007e431  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x18007e436  mov     dl, 7Dh ; '}'; char
0x18007e438  mov     rcx, rdi; this
0x18007e43b  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18007e440  mov     rbx, [rbp+57h+var_A0]
0x18007e444  test    rbx, rbx
0x18007e447  jz      short loc_18007E478
0x18007e449  xor     r9d, r9d; int
0x18007e44c  mov     r8d, 8Bh; int
0x18007e452  mov     edx, r14d; int
0x18007e455  mov     rcx, rdi; this
0x18007e458  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e45d  xor     r9d, r9d; int
0x18007e460  xor     r8d, r8d; unsigned int
0x18007e463  mov     rdx, rbx; unsigned __int16 *
0x18007e466  mov     rcx, rdi; this
0x18007e469  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x18007e46e  mov     dl, 7Dh ; '}'; char
0x18007e470  mov     rcx, rdi; this
0x18007e473  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18007e478  cmp     [rbp+57h+var_D4], 0
0x18007e47c  jz      short loc_18007E491
0x18007e47e  xor     r9d, r9d; int
0x18007e481  xor     edx, edx; int
0x18007e483  mov     r8d, 8Fh; int
0x18007e489  mov     rcx, rdi; this
0x18007e48c  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e491  xor     r8d, r8d; int
0x18007e494  lea     rdx, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e499  mov     rcx, rdi; this
0x18007e49c  call    ?WriteRtfObject@CRTFWrite@@AEAAHAEAU_rtfobject@@H@Z; CRTFWrite::WriteRtfObject(_rtfobject &,int)
0x18007e4a1  xor     r9d, r9d; int
0x18007e4a4  mov     r8d, 85h; int
0x18007e4aa  mov     edx, r14d; int
0x18007e4ad  mov     rcx, rdi; this
0x18007e4b0  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e4b5  mov     r8d, esi; int
0x18007e4b8  lea     rdx, qword_180099F48; Src
0x18007e4bf  mov     rcx, rdi; this
0x18007e4c2  call    ?Puts@CRTFWrite@@AEAAHPEBDJ@Z; CRTFWrite::Puts(char const *,long)
0x18007e4c7  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e4cc  mov     rcx, rdi; this
0x18007e4cf  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x18007e4d3  call    ?ObjectWriteToEditstream@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::ObjectWriteToEditstream(_reobject &,_rtfobject &)
0x18007e4d8  test    eax, eax
0x18007e4da  jnz     short loc_18007E4EA
0x18007e4dc  cmp     [rdi+30h], eax
0x18007e4df  jnz     short loc_18007E514
0x18007e4e1  mov     dword ptr [rdi+30h], 13h
0x18007e4e8  jmp     short loc_18007E514
0x18007e4ea  mov     dl, 7Dh ; '}'; char
0x18007e4ec  mov     rcx, rdi; this
0x18007e4ef  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18007e4f4  xor     r9d, r9d; int
0x18007e4f7  mov     r8d, 0BCh; int
0x18007e4fd  mov     edx, esi; int
0x18007e4ff  mov     rcx, rdi; this
0x18007e502  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18007e507  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e50c  mov     rcx, rdi; this
0x18007e50f  call    ?WritePicture@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WritePicture(_reobject &,_rtfobject &)
0x18007e514  mov     dl, 7Dh ; '}'; char
0x18007e516  mov     rcx, rdi; this
0x18007e519  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18007e51e  mov     dl, 7Dh ; '}'; char
0x18007e520  mov     rcx, rdi; this
0x18007e523  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18007e528  jmp     short loc_18007E537
0x18007e52a  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18007e52f  mov     rcx, rdi; this
0x18007e532  call    ?WritePicture@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WritePicture(_reobject &,_rtfobject &)
0x18007e537  mov     rcx, [rbp+57h+var_80.pstg]
0x18007e53b  test    rcx, rcx
0x18007e53e  jz      short loc_18007E54C
0x18007e540  mov     rax, [rcx]
0x18007e543  mov     rax, [rax+10h]
0x18007e547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e54c  mov     rcx, [rbp+57h+var_80.polesite]
0x18007e550  test    rcx, rcx
0x18007e553  jz      short loc_18007E561
0x18007e555  mov     rax, [rcx]
0x18007e558  mov     rax, [rax+10h]
0x18007e55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e561  mov     rcx, [rbp+57h+var_80.poleobj]
0x18007e565  test    rcx, rcx
0x18007e568  jz      short loc_18007E576
0x18007e56a  mov     rax, [rcx]
0x18007e56d  mov     rax, [rax+10h]
0x18007e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e576  mov     rcx, [rbp+57h+hMem]; pMem
0x18007e57a  test    rcx, rcx
0x18007e57d  jz      short loc_18007E599
0x18007e57f  call    cs:__imp_GlobalHandle
0x18007e585  mov     rcx, rax; hMem
0x18007e588  mov     rbx, rax
0x18007e58b  call    cs:__imp_GlobalUnlock
0x18007e591  mov     rcx, rbx; void *
0x18007e594  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007e599  mov     rcx, [rbp+57h+var_A8]; void *
0x18007e59d  test    rcx, rcx
0x18007e5a0  jz      short loc_18007E5A7
0x18007e5a2  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x18007e5a7  mov     eax, [rdi+30h]
0x18007e5aa  mov     rcx, [rbp+57h+var_30]
0x18007e5ae  xor     rcx, rsp; StackCookie
0x18007e5b1  call    __security_check_cookie
0x18007e5b6  add     rsp, 0E0h
0x18007e5bd  pop     r14
0x18007e5bf  pop     rdi
0x18007e5c0  pop     rsi
0x18007e5c1  pop     rbx
0x18007e5c2  pop     rbp
0x18007e5c3  retn
```
