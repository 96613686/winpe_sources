# COleControl::GetMetafileData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1800b5eb0`
- end: `0x1800b6086`
- name: `?GetMetafileData@COleControl@@IEAAHPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(COleControl *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800b8260`

## callees

- `0x180027210`
- `0x18004f2a0`
- `0x18004f360`
- `0x18004f790`
- `0x18005e3e0`
- `0x18005e6a0`
- `0x18009424c`
- `0x18009a310`
- `0x1800b5bf0`
- `0x1800b5db0`
- `0x1800b5eb0`
- `0x1800d1fe0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800b6039`
- `KERNEL32!GlobalFree` at `0x1800b6039`
- `KERNEL32!GlobalUnlock` at `0x1800b6062`
- `KERNEL32!GlobalUnlock` at `0x1800b6062`
- `KERNEL32!GlobalAlloc` at `0x1800b5fd9`
- `KERNEL32!GlobalAlloc` at `0x1800b5fd9`
- `KERNEL32!GlobalLock` at `0x1800b601f`
- `KERNEL32!GlobalLock` at `0x1800b601f`
- `GDI32!DeleteMetaFile` at `0x1800b5fea`
- `GDI32!DeleteMetaFile` at `0x1800b6030`
- `GDI32!DeleteMetaFile` at `0x1800b5fea`
- `GDI32!DeleteMetaFile` at `0x1800b6030`
- `GDI32!DeleteDC` at `0x1800b5fb8`
- `GDI32!DeleteDC` at `0x1800b5fb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COleControl::GetMetafileData(COleControl *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  HDC DC; // rsi
  unsigned int v7; // edi
  unsigned int v8; // ebx
  HMETAFILE v9; // rdi
  HBITMAP v10; // rax
  HBITMAP v11; // rbx
  _QWORD *v13; // rax
  int v14; // [rsp+20h] [rbp-50h] BYREF
  int v15[3]; // [rsp+24h] [rbp-4Ch] BYREF
  void **v16; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+38h] [rbp-38h]
  int v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  int v20; // [rsp+58h] [rbp-18h]
  int v21; // [rsp+5Ch] [rbp-14h]

  if ( (a2->tymed & 0x20) == 0 || a3->hBitmap )
    return 0;
  v17 = 0;
  v18 = 0;
  v16 = &CMetaFileDC::`vftable';
  if ( !(unsigned int)CMetaFileDC::Create((CMetaFileDC *)&v16, 0) )
    goto LABEL_7;
  DC = _AfxOleCreateDC(a2->ptd);
  CMetaFileDC::SetAttribDC((CMetaFileDC *)&v16, DC);
  v14 = 0;
  v15[0] = 0;
  COleControl::GetControlSize(this, &v14, v15);
  v19 = 0;
  v7 = v14;
  v20 = v14;
  v8 = v15[0];
  v21 = v15[0];
  CDC::SetMapMode((CDC *)&v16, 8);
  CDC::SetWindowOrg(&v16, v15, 0, 0);
  CDC::SetWindowExt(&v16, v15, v7, v8);
  COleControl::DrawMetafile(this, (struct CDC *)&v16, (struct CRect *)&v19);
  CMetaFileDC::SetAttribDC((CMetaFileDC *)&v16, 0);
  DeleteDC(DC);
  v9 = CMetaFileDC::Close((CMetaFileDC *)&v16);
  if ( !v9 )
  {
LABEL_7:
    CMetaFileDC::~CMetaFileDC((CMetaFileDC *)&v16);
    return 0;
  }
  v10 = (HBITMAP)GlobalAlloc(0x2000u, 0x18u);
  v11 = v10;
  if ( !v10 )
  {
    DeleteMetaFile(v9);
    goto LABEL_7;
  }
  v13 = GlobalLock(v10);
  if ( !v13 )
  {
    DeleteMetaFile(v9);
    GlobalFree(v11);
    goto LABEL_7;
  }
  *(_DWORD *)v13 = 8;
  v13[2] = v9;
  *((_DWORD *)v13 + 1) = *((_DWORD *)this + 56);
  *((_DWORD *)v13 + 2) = *((_DWORD *)this + 57);
  GlobalUnlock(v11);
  a3->hBitmap = v11;
  a3->tymed = 32;
  CMetaFileDC::~CMetaFileDC((CMetaFileDC *)&v16);
  return 1;
}

```

## disassembly

```asm
0x1800b5eb0  mov     [rsp-28h+arg_18], rbx
0x1800b5eb5  push    rbp
0x1800b5eb6  push    rsi
0x1800b5eb7  push    rdi
0x1800b5eb8  push    r14
0x1800b5eba  push    r15
0x1800b5ebc  mov     rbp, rsp
0x1800b5ebf  sub     rsp, 70h
0x1800b5ec3  mov     rax, cs:__security_cookie
0x1800b5eca  xor     rax, rsp
0x1800b5ecd  mov     [rbp+var_10], rax
0x1800b5ed1  mov     r14, r8
0x1800b5ed4  mov     rbx, rdx
0x1800b5ed7  mov     r15, rcx
0x1800b5eda  test    byte ptr [rdx+18h], 20h
0x1800b5ede  jz      loc_1800B5FFA
0x1800b5ee4  cmp     qword ptr [r8+8], 0
0x1800b5ee9  jnz     loc_1800B5FFA
0x1800b5eef  xorps   xmm0, xmm0
0x1800b5ef2  movdqu  [rbp+var_38], xmm0
0x1800b5ef7  mov     [rbp+var_28], 0
0x1800b5efe  lea     rax, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x1800b5f05  mov     [rbp+var_40], rax
0x1800b5f09  xor     edx, edx; pszFile
0x1800b5f0b  lea     rcx, [rbp+var_40]; this
0x1800b5f0f  call    ?Create@CMetaFileDC@@QEAAHPEBG@Z; CMetaFileDC::Create(ushort const *)
0x1800b5f14  test    eax, eax
0x1800b5f16  jz      loc_1800B5FF1
0x1800b5f1c  mov     rcx, [rbx+8]; struct tagDVTARGETDEVICE *
0x1800b5f20  call    ?_AfxOleCreateDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _AfxOleCreateDC(tagDVTARGETDEVICE *)
0x1800b5f25  mov     rsi, rax
0x1800b5f28  mov     rdx, rax; HDC
0x1800b5f2b  lea     rcx, [rbp+var_40]; this
0x1800b5f2f  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x1800b5f34  mov     [rbp+var_50], 0
0x1800b5f3b  mov     [rbp+var_4C], 0
0x1800b5f42  lea     r8, [rbp+var_4C]; int *
0x1800b5f46  lea     rdx, [rbp+var_50]; int *
0x1800b5f4a  mov     rcx, r15; this
0x1800b5f4d  call    ?GetControlSize@COleControl@@QEAAXPEAH0@Z; COleControl::GetControlSize(int *,int *)
0x1800b5f52  mov     [rbp+var_20], 0
0x1800b5f5a  mov     edi, [rbp+var_50]
0x1800b5f5d  mov     [rbp+var_18], edi
0x1800b5f60  mov     ebx, [rbp+var_4C]
0x1800b5f63  mov     [rbp+var_14], ebx
0x1800b5f66  mov     edx, 8; int
0x1800b5f6b  lea     rcx, [rbp+var_40]; this
0x1800b5f6f  call    ?SetMapMode@CDC@@UEAAHH@Z; CDC::SetMapMode(int)
0x1800b5f74  xor     r9d, r9d
0x1800b5f77  xor     r8d, r8d
0x1800b5f7a  lea     rdx, [rbp+var_4C]
0x1800b5f7e  lea     rcx, [rbp+var_40]
0x1800b5f82  call    ?SetWindowOrg@CDC@@QEAA?AVCPoint@@HH@Z; CDC::SetWindowOrg(int,int)
0x1800b5f87  mov     r9d, ebx
0x1800b5f8a  mov     r8d, edi
0x1800b5f8d  lea     rdx, [rbp+var_4C]
0x1800b5f91  lea     rcx, [rbp+var_40]
0x1800b5f95  call    ?SetWindowExt@CDC@@UEAA?AVCSize@@HH@Z; CDC::SetWindowExt(int,int)
0x1800b5f9a  lea     r8, [rbp+var_20]; struct CRect *
0x1800b5f9e  lea     rdx, [rbp+var_40]; struct CDC *
0x1800b5fa2  mov     rcx, r15; this
0x1800b5fa5  call    ?DrawMetafile@COleControl@@IEAAXPEAVCDC@@AEAVCRect@@@Z; COleControl::DrawMetafile(CDC *,CRect &)
0x1800b5faa  xor     edx, edx; HDC
0x1800b5fac  lea     rcx, [rbp+var_40]; this
0x1800b5fb0  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x1800b5fb5  mov     rcx, rsi; hdc
0x1800b5fb8  call    cs:__imp_DeleteDC
0x1800b5fbe  lea     rcx, [rbp+var_40]; this
0x1800b5fc2  call    ?Close@CMetaFileDC@@QEAAPEAUHMETAFILE__@@XZ; CMetaFileDC::Close(void)
0x1800b5fc7  mov     rdi, rax
0x1800b5fca  test    rax, rax
0x1800b5fcd  jz      short loc_1800B5FF1
0x1800b5fcf  mov     edx, 18h; dwBytes
0x1800b5fd4  mov     ecx, 2000h; uFlags
0x1800b5fd9  call    cs:__imp_GlobalAlloc
0x1800b5fdf  mov     rbx, rax
0x1800b5fe2  test    rax, rax
0x1800b5fe5  jnz     short loc_1800B601C
0x1800b5fe7  mov     rcx, rdi; hmf
0x1800b5fea  call    cs:__imp_DeleteMetaFile
0x1800b5ff0  nop
0x1800b5ff1  lea     rcx, [rbp+var_40]; this
0x1800b5ff5  call    ??1CMetaFileDC@@UEAA@XZ; CMetaFileDC::~CMetaFileDC(void)
0x1800b5ffa  xor     eax, eax
0x1800b5ffc  mov     rcx, [rbp+var_10]
0x1800b6000  xor     rcx, rsp; StackCookie
0x1800b6003  call    __security_check_cookie
0x1800b6008  mov     rbx, [rsp+70h+arg_18]
0x1800b6010  add     rsp, 70h
0x1800b6014  pop     r15
0x1800b6016  pop     r14
0x1800b6018  pop     rdi
0x1800b6019  pop     rsi
0x1800b601a  pop     rbp
0x1800b601b  retn
0x1800b601c  mov     rcx, rbx; hMem
0x1800b601f  call    cs:__imp_GlobalLock
0x1800b6025  mov     rcx, rax
0x1800b6028  test    rax, rax
0x1800b602b  jnz     short loc_1800B6041
0x1800b602d  mov     rcx, rdi; hmf
0x1800b6030  call    cs:__imp_DeleteMetaFile
0x1800b6036  mov     rcx, rbx; hMem
0x1800b6039  call    cs:__imp_GlobalFree
0x1800b603f  jmp     short loc_1800B5FF1
0x1800b6041  mov     dword ptr [rax], 8
0x1800b6047  mov     [rax+10h], rdi
0x1800b604b  mov     eax, [r15+0E0h]
0x1800b6052  mov     [rcx+4], eax
0x1800b6055  mov     eax, [r15+0E4h]
0x1800b605c  mov     [rcx+8], eax
0x1800b605f  mov     rcx, rbx; hMem
0x1800b6062  call    cs:__imp_GlobalUnlock
0x1800b6068  mov     [r14+8], rbx
0x1800b606c  mov     dword ptr [r14], 20h ; ' '
0x1800b6073  lea     rcx, [rbp+var_40]; this
0x1800b6077  call    ??1CMetaFileDC@@UEAA@XZ; CMetaFileDC::~CMetaFileDC(void)
0x1800b607c  mov     eax, 1
0x1800b6081  jmp     loc_1800B5FFC
```
