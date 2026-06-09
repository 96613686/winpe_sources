# COleServerItem::GetMetafileData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18009ac50`
- end: `0x18009adff`
- name: `?GetMetafileData@COleServerItem@@MEAAHPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(COleServerItem *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18004f2a0`
- `0x18004f360`
- `0x18004f790`
- `0x18009424c`
- `0x18009a310`
- `0x18009ac50`
- `0x1800d7010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18009ad8a`
- `KERNEL32!GlobalFree` at `0x18009ad8a`
- `KERNEL32!GlobalUnlock` at `0x18009addb`
- `KERNEL32!GlobalUnlock` at `0x18009addb`
- `KERNEL32!GlobalAlloc` at `0x18009ad31`
- `KERNEL32!GlobalAlloc` at `0x18009ad31`
- `KERNEL32!GlobalLock` at `0x18009ad70`
- `KERNEL32!GlobalLock` at `0x18009ad70`
- `GDI32!DeleteMetaFile` at `0x18009ad42`
- `GDI32!DeleteMetaFile` at `0x18009ad81`
- `GDI32!DeleteMetaFile` at `0x18009ad42`
- `GDI32!DeleteMetaFile` at `0x18009ad81`
- `GDI32!DeleteDC` at `0x18009ad0c`
- `GDI32!DeleteDC` at `0x18009ad0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COleServerItem::GetMetafileData(
        COleServerItem *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  HDC DC; // rax
  HDC v7; // rdi
  int v8; // ebx
  HMETAFILE v9; // rsi
  HBITMAP v10; // rax
  HBITMAP v11; // rdi
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  int v15; // eax
  int v16; // eax
  void **v17; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+48h] [rbp-8h]
  __int64 v20; // [rsp+88h] [rbp+38h] BYREF

  if ( (a2->tymed & 0x20) == 0 || a3->hBitmap )
    return 0;
  v18 = 0;
  v19 = 0;
  v17 = &CMetaFileDC::`vftable';
  if ( !(unsigned int)CMetaFileDC::Create((CMetaFileDC *)&v17, 0) )
    goto LABEL_9;
  DC = _AfxOleCreateDC(a2->ptd);
  v7 = DC;
  if ( !DC
    || (CMetaFileDC::SetAttribDC((CMetaFileDC *)&v17, DC),
        v20 = 0,
        v8 = (*(__int64 (__fastcall **)(COleServerItem *, void ***, _QWORD, __int64 *))(*(_QWORD *)this + 200LL))(
               this,
               &v17,
               a2->dwAspect,
               &v20),
        CMetaFileDC::SetAttribDC((CMetaFileDC *)&v17, 0),
        DeleteDC(v7),
        !v8)
    || (v9 = CMetaFileDC::Close((CMetaFileDC *)&v17)) == 0 )
  {
LABEL_9:
    CMetaFileDC::~CMetaFileDC((CMetaFileDC *)&v17);
    return 0;
  }
  v10 = (HBITMAP)GlobalAlloc(0x2002u, 0x18u);
  v11 = v10;
  if ( !v10 )
  {
    DeleteMetaFile(v9);
    goto LABEL_9;
  }
  v13 = GlobalLock(v10);
  v14 = v13;
  if ( !v13 )
  {
    DeleteMetaFile(v9);
    GlobalFree(v11);
    goto LABEL_9;
  }
  *(_DWORD *)v13 = 8;
  v13[2] = v9;
  v15 = v20;
  if ( !v20 )
  {
    (*(void (__fastcall **)(COleServerItem *, _QWORD, __int64 *))(*(_QWORD *)this + 216LL))(this, a2->dwAspect, &v20);
    v15 = v20;
  }
  *((_DWORD *)v14 + 1) = v15;
  v16 = HIDWORD(v20);
  *((_DWORD *)v14 + 2) = HIDWORD(v20);
  if ( v16 < 0 )
    *((_DWORD *)v14 + 2) = -v16;
  GlobalUnlock(v11);
  a3->hBitmap = v11;
  a3->tymed = 32;
  CMetaFileDC::~CMetaFileDC((CMetaFileDC *)&v17);
  return 1;
}

```

## disassembly

```asm
0x18009ac50  mov     [rsp-28h+arg_0], rbx
0x18009ac55  mov     [rsp-28h+arg_10], rsi
0x18009ac5a  push    rbp
0x18009ac5b  push    rdi
0x18009ac5c  push    r12
0x18009ac5e  push    r14
0x18009ac60  push    r15
0x18009ac62  mov     rbp, rsp
0x18009ac65  sub     rsp, 50h
0x18009ac69  mov     r14, r8
0x18009ac6c  mov     r15, rdx
0x18009ac6f  mov     r12, rcx
0x18009ac72  test    byte ptr [rdx+18h], 20h
0x18009ac76  jz      loc_18009AD52
0x18009ac7c  cmp     qword ptr [r8+8], 0
0x18009ac81  jnz     loc_18009AD52
0x18009ac87  xorps   xmm0, xmm0
0x18009ac8a  movdqu  [rbp+var_18], xmm0
0x18009ac8f  mov     [rbp+var_8], 0
0x18009ac96  lea     rax, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x18009ac9d  mov     [rbp+var_20], rax
0x18009aca1  xor     edx, edx; pszFile
0x18009aca3  lea     rcx, [rbp+var_20]; this
0x18009aca7  call    ?Create@CMetaFileDC@@QEAAHPEBG@Z; CMetaFileDC::Create(ushort const *)
0x18009acac  test    eax, eax
0x18009acae  jz      loc_18009AD49
0x18009acb4  mov     rcx, [r15+8]; struct tagDVTARGETDEVICE *
0x18009acb8  call    ?_AfxOleCreateDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _AfxOleCreateDC(tagDVTARGETDEVICE *)
0x18009acbd  mov     rdi, rax
0x18009acc0  test    rax, rax
0x18009acc3  jz      loc_18009AD49
0x18009acc9  mov     rdx, rax; HDC
0x18009accc  lea     rcx, [rbp+var_20]; this
0x18009acd0  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x18009acd5  mov     [rbp+arg_8], 0
0x18009acdd  mov     rcx, [r12]
0x18009ace1  mov     rax, [rcx+0C8h]
0x18009ace8  lea     r9, [rbp+arg_8]
0x18009acec  mov     r8d, [r15+10h]
0x18009acf0  lea     rdx, [rbp+var_20]
0x18009acf4  mov     rcx, r12
0x18009acf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acfc  mov     ebx, eax
0x18009acfe  xor     edx, edx; HDC
0x18009ad00  lea     rcx, [rbp+var_20]; this
0x18009ad04  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x18009ad09  mov     rcx, rdi; hdc
0x18009ad0c  call    cs:__imp_DeleteDC
0x18009ad12  test    ebx, ebx
0x18009ad14  jz      short loc_18009AD49
0x18009ad16  lea     rcx, [rbp+var_20]; this
0x18009ad1a  call    ?Close@CMetaFileDC@@QEAAPEAUHMETAFILE__@@XZ; CMetaFileDC::Close(void)
0x18009ad1f  mov     rsi, rax
0x18009ad22  test    rax, rax
0x18009ad25  jz      short loc_18009AD49
0x18009ad27  mov     edx, 18h; dwBytes
0x18009ad2c  mov     ecx, 2002h; uFlags
0x18009ad31  call    cs:__imp_GlobalAlloc
0x18009ad37  mov     rdi, rax
0x18009ad3a  test    rax, rax
0x18009ad3d  jnz     short loc_18009AD6D
0x18009ad3f  mov     rcx, rsi; hmf
0x18009ad42  call    cs:__imp_DeleteMetaFile
0x18009ad48  nop
0x18009ad49  lea     rcx, [rbp+var_20]; this
0x18009ad4d  call    ??1CMetaFileDC@@UEAA@XZ; CMetaFileDC::~CMetaFileDC(void)
0x18009ad52  xor     eax, eax
0x18009ad54  lea     r11, [rsp+50h+var_s0]
0x18009ad59  mov     rbx, [r11+30h]
0x18009ad5d  mov     rsi, [r11+40h]
0x18009ad61  mov     rsp, r11
0x18009ad64  pop     r15
0x18009ad66  pop     r14
0x18009ad68  pop     r12
0x18009ad6a  pop     rdi
0x18009ad6b  pop     rbp
0x18009ad6c  retn
0x18009ad6d  mov     rcx, rdi; hMem
0x18009ad70  call    cs:__imp_GlobalLock
0x18009ad76  mov     rbx, rax
0x18009ad79  test    rax, rax
0x18009ad7c  jnz     short loc_18009AD92
0x18009ad7e  mov     rcx, rsi; hmf
0x18009ad81  call    cs:__imp_DeleteMetaFile
0x18009ad87  mov     rcx, rdi; hMem
0x18009ad8a  call    cs:__imp_GlobalFree
0x18009ad90  jmp     short loc_18009AD49
0x18009ad92  mov     dword ptr [rax], 8
0x18009ad98  mov     [rax+10h], rsi
0x18009ad9c  mov     eax, dword ptr [rbp+arg_8]
0x18009ad9f  test    eax, eax
0x18009ada1  jnz     short loc_18009ADC6
0x18009ada3  cmp     dword ptr [rbp+arg_8+4], eax
0x18009ada6  jnz     short loc_18009ADC6
0x18009ada8  mov     rax, [r12]
0x18009adac  lea     r8, [rbp+arg_8]
0x18009adb0  mov     edx, [r15+10h]
0x18009adb4  mov     rcx, r12
0x18009adb7  mov     rax, [rax+0D8h]
0x18009adbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adc3  mov     eax, dword ptr [rbp+arg_8]
0x18009adc6  mov     [rbx+4], eax
0x18009adc9  mov     eax, dword ptr [rbp+arg_8+4]
0x18009adcc  mov     [rbx+8], eax
0x18009adcf  test    eax, eax
0x18009add1  jns     short loc_18009ADD8
0x18009add3  neg     eax
0x18009add5  mov     [rbx+8], eax
0x18009add8  mov     rcx, rdi; hMem
0x18009addb  call    cs:__imp_GlobalUnlock
0x18009ade1  mov     [r14+8], rdi
0x18009ade5  mov     dword ptr [r14], 20h ; ' '
0x18009adec  lea     rcx, [rbp+var_20]; this
0x18009adf0  call    ??1CMetaFileDC@@UEAA@XZ; CMetaFileDC::~CMetaFileDC(void)
0x18009adf5  mov     eax, 1
0x18009adfa  jmp     loc_18009AD54
```
