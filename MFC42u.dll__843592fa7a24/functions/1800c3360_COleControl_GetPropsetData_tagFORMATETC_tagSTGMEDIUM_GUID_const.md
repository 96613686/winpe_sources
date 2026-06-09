# COleControl::GetPropsetData(tagFORMATETC *,tagSTGMEDIUM *,_GUID const &)

- ea: `0x1800c3360`
- end: `0x1800c3672`
- name: `?GetPropsetData@COleControl@@IEAAHPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@AEBU_GUID@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(COleControl *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b8260`

## callees

- `0x18000b3a0`
- `0x180019290`
- `0x1800c0b50`
- `0x1800c3360`
- `0x1800c3ab0`
- `0x1800c6800`
- `0x1800c6960`
- `0x1800c6a60`
- `0x1800c8020`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800c34f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800c34f7`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800c3408`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800c3408`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800c33ec`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800c33ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall COleControl::GetPropsetData(
        COleControl *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3,
        const struct _GUID *a4)
{
  struct tagSTGMEDIUM *v4; // r15
  struct tagSTGMEDIUM *v6; // rdi
  DWORD tymed; // r14d
  DWORD *p_tymed; // r12
  unsigned int v9; // ebx
  int v10; // esi
  IStorage *pstg; // rcx
  bool v12; // sf
  void (*Release)(void); // rax
  struct CPropertySection *v15; // r14
  _QWORD *v16; // rax
  HBITMAP v17; // rax
  IStorage *ppstgOpen; // [rsp+40h] [rbp-138h] BYREF
  struct IStream *pstm; // [rsp+48h] [rbp-130h] BYREF
  LPLOCKBYTES pplkbyt[2]; // [rsp+50h] [rbp-128h] BYREF
  struct _GUID v21; // [rsp+60h] [rbp-118h] BYREF
  struct tagSTGMEDIUM *v22; // [rsp+70h] [rbp-108h]
  DWORD *v23; // [rsp+80h] [rbp-F8h]
  void **v24; // [rsp+88h] [rbp-F0h] BYREF
  int v25; // [rsp+90h] [rbp-E8h]
  __int64 v26; // [rsp+94h] [rbp-E4h]
  struct CPropertySection *v27; // [rsp+A0h] [rbp-D8h]
  IStorage *v28; // [rsp+A8h] [rbp-D0h]
  int v29; // [rsp+B0h] [rbp-C8h]
  CException *v30; // [rsp+B8h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v32[4]; // [rsp+D0h] [rbp-A8h] BYREF
  int v33; // [rsp+D4h] [rbp-A4h]

  *(_QWORD *)&v21.Data1 = a4;
  v4 = a3;
  v6 = a3;
  v22 = a3;
  tymed = a3->tymed;
  p_tymed = &a2->tymed;
  v23 = &a2->tymed;
  if ( (a2->tymed & 0xC) == 0 )
    return 0;
  v9 = 0;
  ppstgOpen = 0;
  pstm = 0;
  v10 = 8;
  if ( (*(_BYTE *)p_tymed & 8) != 0 )
  {
    if ( tymed )
    {
      pstg = a3->pstg;
      ppstgOpen = pstg;
    }
    else
    {
      pplkbyt[0] = 0;
      if ( CreateILockBytesOnHGlobal(0, 1, pplkbyt) < 0 )
        return 0;
      v12 = StgCreateDocfileOnILockBytes(pplkbyt[0], 0x1012u, 0, &ppstgOpen) < 0;
      Release = (void (*)(void))pplkbyt[0]->lpVtbl->Release;
      if ( v12 )
      {
LABEL_11:
        Release();
        return 0;
      }
      Release();
      pstg = ppstgOpen;
    }
    if ( ((int (__fastcall *)(IStorage *, const unsigned __int16 *, __int64, _QWORD, _DWORD, struct IStream **))pstg->lpVtbl->CreateStream)(
           pstg,
           L"Contents",
           4114,
           0,
           0,
           &pstm) < 0 )
    {
      if ( !tymed )
      {
        Release = (void (*)(void))ppstgOpen->lpVtbl->Release;
        goto LABEL_11;
      }
      return 0;
    }
  }
  else if ( tymed )
  {
    pstm = a3->pstm;
  }
  else
  {
    pstm = _AfxCreateMemoryStream();
    if ( !pstm )
      return 0;
  }
  v31 = 0;
  (*(void (__fastcall **)(COleControl *, __int128 *))(*(_QWORD *)this + 424LL))(this, &v31);
  *(_OWORD *)pplkbyt = v31;
  CPropertySet::CPropertySet((CPropertySet *)v32, (struct _GUID *)pplkbyt);
  v33 = (unsigned __int16)GetVersion() | 0x20000;
  v21 = *(struct _GUID *)*(_QWORD *)&v21.Data1;
  v15 = CPropertySet::AddSection((CPropertySet *)v32, &v21);
  if ( !v15 )
    goto LABEL_21;
  v16 = (_QWORD *)COleControl::AmbientDisplayName(this, &v21);
  CString::operator=((char *)v15 + 136, *v16);
  CString::~CString((CString *)&v21);
  try
  {
    v26 = 0;
    v24 = &CPropsetPropExchange::`vftable';
    v27 = v15;
    v28 = ppstgOpen;
    v29 = 255;
    v25 = 0;
    LODWORD(pplkbyt[0]) = 0;
    (*(void (__fastcall **)(COleControl *, void ***))(*(_QWORD *)this + 392LL))(this, &v24);
    LODWORD(pplkbyt[0]) = 1;
  }
  catch ( CException *v30 )
  {
    CException::Delete(v30);
    v9 = 0;
    if ( !LODWORD(pplkbyt[0]) )
      goto LABEL_21;
    v10 = 8;
    v6 = v22;
    v4 = v22;
    p_tymed = v23;
  }
  if ( CPropertySet::WriteToStream((CPropertySet *)v32, pstm) != 1 )
  {
LABEL_21:
    if ( pstm )
      ((void (__fastcall *)(struct IStream *))pstm->lpVtbl->Release)(pstm);
    if ( ppstgOpen )
      ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    goto LABEL_29;
  }
  if ( (*(_BYTE *)p_tymed & 8) != 0 )
  {
    ((void (__fastcall *)(struct IStream *))pstm->lpVtbl->Release)(pstm);
    v17 = (HBITMAP)ppstgOpen;
  }
  else
  {
    v17 = (HBITMAP)pstm;
    v10 = 4;
  }
  v6->hBitmap = v17;
  v4->tymed = v10;
  v6->pUnkForRelease = 0;
  v9 = 1;
LABEL_29:
  CPropertySet::~CPropertySet((CPropertySet *)v32);
  return v9;
}

```

## disassembly

```asm
0x1800c3360  push    rbx
0x1800c3362  push    rsi
0x1800c3363  push    rdi
0x1800c3364  push    r12
0x1800c3366  push    r13
0x1800c3368  push    r14
0x1800c336a  push    r15
0x1800c336c  sub     rsp, 140h
0x1800c3373  mov     rax, cs:__security_cookie
0x1800c337a  xor     rax, rsp
0x1800c337d  mov     [rsp+178h+var_48], rax
0x1800c3385  mov     qword ptr [rsp+178h+var_118.Data1], r9
0x1800c338a  mov     r15, r8
0x1800c338d  mov     r13, rcx
0x1800c3390  mov     rdi, r8
0x1800c3393  mov     [rsp+178h+var_108], r8
0x1800c3398  mov     r14d, [r8]
0x1800c339b  lea     r12, [rdx+18h]
0x1800c339f  mov     [rsp+178h+var_F8], r12
0x1800c33a7  test    byte ptr [r12], 0Ch
0x1800c33ac  jz      loc_1800C346C
0x1800c33b2  xor     ebx, ebx
0x1800c33b4  mov     [rsp+178h+ppstgOpen], rbx
0x1800c33b9  mov     [rsp+178h+var_130], rbx
0x1800c33be  lea     esi, [rbx+8]
0x1800c33c1  test    [r12], sil
0x1800c33c5  jz      loc_1800C3491
0x1800c33cb  test    r14d, r14d
0x1800c33ce  jz      short loc_1800C33DB
0x1800c33d0  mov     rcx, [r8+8]
0x1800c33d4  mov     [rsp+178h+ppstgOpen], rcx
0x1800c33d9  jmp     short loc_1800C3428
0x1800c33db  mov     [rsp+178h+pplkbyt], rbx
0x1800c33e0  lea     r8, [rsp+178h+pplkbyt]; pplkbyt
0x1800c33e5  mov     edx, 1; fDeleteOnRelease
0x1800c33ea  xor     ecx, ecx; hGlobal
0x1800c33ec  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800c33f2  test    eax, eax
0x1800c33f4  js      short loc_1800C346C
0x1800c33f6  lea     r9, [rsp+178h+ppstgOpen]; ppstgOpen
0x1800c33fb  xor     r8d, r8d; reserved
0x1800c33fe  mov     edx, 1012h; grfMode
0x1800c3403  mov     rcx, [rsp+178h+pplkbyt]; plkbyt
0x1800c3408  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800c340e  mov     rcx, [rsp+178h+pplkbyt]
0x1800c3413  test    eax, eax
0x1800c3415  mov     rax, [rcx]
0x1800c3418  mov     rax, [rax+10h]
0x1800c341c  js      short loc_1800C3467
0x1800c341e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3423  mov     rcx, [rsp+178h+ppstgOpen]
0x1800c3428  mov     rax, [rcx]
0x1800c342b  lea     rdx, [rsp+178h+var_130]
0x1800c3430  mov     [rsp+178h+var_150], rdx
0x1800c3435  mov     [rsp+178h+var_158], ebx
0x1800c3439  xor     r9d, r9d
0x1800c343c  mov     r8d, 1012h
0x1800c3442  lea     rdx, aContents; "Contents"
0x1800c3449  mov     rax, [rax+18h]
0x1800c344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3452  test    eax, eax
0x1800c3454  jns     short loc_1800C34B0
0x1800c3456  test    r14d, r14d
0x1800c3459  jnz     short loc_1800C346C
0x1800c345b  mov     rcx, [rsp+178h+ppstgOpen]
0x1800c3460  mov     rax, [rcx]
0x1800c3463  mov     rax, [rax+10h]
0x1800c3467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c346c  xor     eax, eax
0x1800c346e  mov     rcx, [rsp+178h+var_48]
0x1800c3476  xor     rcx, rsp; StackCookie
0x1800c3479  call    __security_check_cookie
0x1800c347e  add     rsp, 140h
0x1800c3485  pop     r15
0x1800c3487  pop     r14
0x1800c3489  pop     r13
0x1800c348b  pop     r12
0x1800c348d  pop     rdi
0x1800c348e  pop     rsi
0x1800c348f  pop     rbx
0x1800c3490  retn
0x1800c3491  test    r14d, r14d
0x1800c3494  jz      short loc_1800C34A1
0x1800c3496  mov     rax, [r8+8]
0x1800c349a  mov     [rsp+178h+var_130], rax
0x1800c349f  jmp     short loc_1800C34B0
0x1800c34a1  call    ?_AfxCreateMemoryStream@@YAPEAUIStream@@XZ; _AfxCreateMemoryStream(void)
0x1800c34a6  mov     [rsp+178h+var_130], rax
0x1800c34ab  test    rax, rax
0x1800c34ae  jz      short loc_1800C346C
0x1800c34b0  xorps   xmm0, xmm0
0x1800c34b3  movups  [rsp+178h+var_B8], xmm0
0x1800c34bb  mov     rax, [r13+0]
0x1800c34bf  lea     rdx, [rsp+178h+var_B8]
0x1800c34c7  mov     rcx, r13
0x1800c34ca  mov     rax, [rax+1A8h]
0x1800c34d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c34d6  movaps  xmm0, [rsp+178h+var_B8]
0x1800c34de  movdqa  xmmword ptr [rsp+178h+pplkbyt], xmm0
0x1800c34e4  lea     rdx, [rsp+178h+pplkbyt]; struct _GUID
0x1800c34e9  lea     rcx, [rsp+178h+var_A8]; this
0x1800c34f1  call    ??0CPropertySet@@QEAA@U_GUID@@@Z; CPropertySet::CPropertySet(_GUID)
0x1800c34f6  nop
0x1800c34f7  call    cs:__imp_GetVersion
0x1800c34fd  movzx   ecx, ax
0x1800c3500  bts     ecx, 11h
0x1800c3504  mov     [rsp+178h+var_A4], ecx
0x1800c350b  mov     rax, qword ptr [rsp+178h+var_118.Data1]
0x1800c3510  movups  xmm0, xmmword ptr [rax]
0x1800c3513  movdqu  xmmword ptr [rsp+178h+var_118.Data1], xmm0
0x1800c3519  lea     rdx, [rsp+178h+var_118]; struct _GUID
0x1800c351e  lea     rcx, [rsp+178h+var_A8]; this
0x1800c3526  call    ?AddSection@CPropertySet@@QEAAPEAVCPropertySection@@U_GUID@@@Z; CPropertySet::AddSection(_GUID)
0x1800c352b  mov     r14, rax
0x1800c352e  test    rax, rax
0x1800c3531  jz      loc_1800C35F8
0x1800c3537  lea     rdx, [rsp+178h+var_118]
0x1800c353c  mov     rcx, r13
0x1800c353f  call    ?AmbientDisplayName@COleControl@@QEAA?AVCString@@XZ; COleControl::AmbientDisplayName(void)
0x1800c3544  nop
0x1800c3545  lea     rcx, [r14+88h]
0x1800c354c  mov     rdx, [rax]
0x1800c354f  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800c3554  nop
0x1800c3555  lea     rcx, [rsp+178h+var_118]; this
0x1800c355a  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c355f  mov     [rsp+178h+var_E4], rbx
0x1800c3567  lea     rax, ??_7CPropsetPropExchange@@6B@; const CPropsetPropExchange::`vftable'
0x1800c356e  mov     [rsp+178h+var_F0], rax
0x1800c3576  mov     [rsp+178h+var_D8], r14
0x1800c357e  mov     rax, [rsp+178h+ppstgOpen]
0x1800c3583  mov     [rsp+178h+var_D0], rax
0x1800c358b  mov     [rsp+178h+var_C8], 0FFh
0x1800c3596  mov     [rsp+178h+var_E8], ebx
0x1800c359d  mov     dword ptr [rsp+178h+pplkbyt], ebx
0x1800c35a1  mov     rax, [r13+0]
0x1800c35a5  lea     rdx, [rsp+178h+var_F0]
0x1800c35ad  mov     rcx, r13
0x1800c35b0  mov     rax, [rax+188h]
0x1800c35b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c35bc  mov     dword ptr [rsp+178h+pplkbyt], 1
0x1800c35c4  jmp     short loc_1800C35E1
0x1800c35c6  xor     ebx, ebx
0x1800c35c8  cmp     dword ptr [rsp+178h+pplkbyt], ebx
0x1800c35cc  jz      short loc_1800C35F8
0x1800c35ce  lea     esi, [rbx+8]
0x1800c35d1  mov     rdi, [rsp+178h+var_108]
0x1800c35d6  mov     r15, rdi
0x1800c35d9  mov     r12, [rsp+178h+var_F8]
0x1800c35e1  mov     rdx, [rsp+178h+var_130]; struct IStream *
0x1800c35e6  lea     rcx, [rsp+178h+var_A8]; this
0x1800c35ee  call    ?WriteToStream@CPropertySet@@QEAAHPEAUIStream@@@Z; CPropertySet::WriteToStream(IStream *)
0x1800c35f3  cmp     eax, 1
0x1800c35f6  jz      short loc_1800C3626
0x1800c35f8  mov     rcx, [rsp+178h+var_130]
0x1800c35fd  test    rcx, rcx
0x1800c3600  jz      short loc_1800C360E
0x1800c3602  mov     rax, [rcx]
0x1800c3605  mov     rax, [rax+10h]
0x1800c3609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c360e  mov     rcx, [rsp+178h+ppstgOpen]
0x1800c3613  test    rcx, rcx
0x1800c3616  jz      short loc_1800C365E
0x1800c3618  mov     rax, [rcx]
0x1800c361b  mov     rax, [rax+10h]
0x1800c361f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3624  jmp     short loc_1800C365E
0x1800c3626  test    [r12], sil
0x1800c362a  jz      short loc_1800C3644
0x1800c362c  mov     rcx, [rsp+178h+var_130]
0x1800c3631  mov     rax, [rcx]
0x1800c3634  mov     rax, [rax+10h]
0x1800c3638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c363d  mov     rax, [rsp+178h+ppstgOpen]
0x1800c3642  jmp     short loc_1800C364E
0x1800c3644  mov     rax, [rsp+178h+var_130]
0x1800c3649  mov     esi, 4
0x1800c364e  mov     [rdi+8], rax
0x1800c3652  mov     [r15], esi
0x1800c3655  mov     [rdi+10h], rbx
0x1800c3659  mov     ebx, 1
0x1800c365e  lea     rcx, [rsp+178h+var_A8]; this
0x1800c3666  call    ??1CPropertySet@@QEAA@XZ; CPropertySet::~CPropertySet(void)
0x1800c366b  mov     eax, ebx
0x1800c366d  jmp     loc_1800C346E
```
