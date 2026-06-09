# BdeCfgFindBasicVolumeExtent(IVdsVolume *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180003390`
- end: `0x180003575`
- name: `?BdeCfgFindBasicVolumeExtent@@YAJPEAUIVdsVolume@@PEA_K1@Z`
- size: `485`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003f68`
- `0x1800101a0`

## callees

- `0x180003390`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000353c`
- `ole32!CoTaskMemFree` at `0x180003553`
- `ole32!CoTaskMemFree` at `0x18000353c`
- `ole32!CoTaskMemFree` at `0x180003553`

## pseudocode

```c
__int64 __fastcall BdeCfgFindBasicVolumeExtent(struct IVdsVolume *a1, unsigned __int64 *a2, unsigned __int64 *a3)
{
  struct IVdsVolumeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetProperties)(IVdsVolume *, VDS_VOLUME_PROP *); // rax
  int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  int v15; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v16; // [rsp+58h] [rbp-11h] BYREF
  __int128 v17; // [rsp+60h] [rbp-9h] BYREF
  __int128 v18; // [rsp+70h] [rbp+7h]
  __int128 v19; // [rsp+80h] [rbp+17h]
  LPVOID pv; // [rsp+90h] [rbp+27h]

  v16 = 0;
  v13 = 0;
  v14 = 0;
  v12 = 0;
  v15 = 0;
  v11 = 0;
  if ( !g_pService )
    return 3231711254LL;
  pv = 0;
  lpVtbl = a1->lpVtbl;
  v17 = 0;
  v18 = 0;
  GetProperties = lpVtbl->GetProperties;
  v19 = 0;
  v9 = ((__int64 (__fastcall *)(struct IVdsVolume *, __int128 *))GetProperties)(a1, &v17);
  if ( v9 >= 0 )
  {
    if ( (_DWORD)v18 == 10 )
    {
      v9 = ((__int64 (__fastcall *)(struct IVdsVolume *, __int64 *))a1->lpVtbl->QueryPlexes)(a1, &v12);
      if ( v9 < 0 )
        goto LABEL_14;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v12 + 24LL))(v12, 1, &v13, &v15);
      if ( v9 < 0 )
        goto LABEL_14;
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IVdsVolumePlex, &v14);
      if ( v9 < 0 )
        goto LABEL_14;
      v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v14 + 40LL))(v14, &v16, &v11);
      if ( v9 < 0 )
        goto LABEL_14;
      if ( v11 == 1 )
      {
        v10 = v16;
        if ( v16 )
        {
          *a2 = *((_QWORD *)v16 + 3);
          if ( a3 )
            *a3 = v10[4];
          goto LABEL_14;
        }
      }
    }
    v9 = -1063256055;
  }
LABEL_14:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v16 )
    CoTaskMemFree(v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003390  push    rbp
0x180003392  push    rbx
0x180003393  push    rsi
0x180003394  push    rdi
0x180003395  push    r14
0x180003397  lea     rbp, [rsp-37h]
0x18000339c  sub     rsp, 0A0h
0x1800033a3  mov     rax, cs:__security_cookie
0x1800033aa  xor     rax, rsp
0x1800033ad  mov     [rbp+57h+var_28], rax
0x1800033b1  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x1800033b9  mov     rsi, r8
0x1800033bc  mov     r14, rdx
0x1800033bf  mov     [rbp+57h+var_68], 0
0x1800033c7  mov     rdi, rcx
0x1800033ca  mov     [rbp+57h+var_80], 0
0x1800033d2  mov     [rbp+57h+var_78], 0
0x1800033da  mov     [rbp+57h+var_88], 0
0x1800033e2  mov     [rbp+57h+var_70], 0
0x1800033e9  mov     [rbp+57h+var_90], 0
0x1800033f0  jnz     short loc_1800033FC
0x1800033f2  mov     eax, 0C0A00016h
0x1800033f7  jmp     loc_18000355B
0x1800033fc  xor     eax, eax
0x1800033fe  lea     rdx, [rbp+57h+var_60]
0x180003402  xorps   xmm0, xmm0
0x180003405  mov     [rbp+57h+pv], rax
0x180003409  mov     rax, [rcx]
0x18000340c  movups  [rbp+57h+var_60], xmm0
0x180003410  movups  [rbp+57h+var_50], xmm0
0x180003414  mov     rax, [rax+18h]
0x180003418  movups  [rbp+57h+var_40], xmm0
0x18000341c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003421  mov     ebx, eax
0x180003423  test    eax, eax
0x180003425  js      loc_1800034DC
0x18000342b  cmp     dword ptr [rbp+57h+var_50], 0Ah
0x18000342f  jnz     loc_1800034D7
0x180003435  mov     rax, [rdi]
0x180003438  lea     rdx, [rbp+57h+var_88]
0x18000343c  mov     rcx, rdi
0x18000343f  mov     rax, [rax+28h]
0x180003443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003448  mov     ebx, eax
0x18000344a  test    eax, eax
0x18000344c  js      loc_1800034DC
0x180003452  mov     rcx, [rbp+57h+var_88]
0x180003456  lea     r9, [rbp+57h+var_70]
0x18000345a  lea     r8, [rbp+57h+var_80]
0x18000345e  mov     edx, 1
0x180003463  mov     rax, [rcx]
0x180003466  mov     rax, [rax+18h]
0x18000346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346f  mov     ebx, eax
0x180003471  test    eax, eax
0x180003473  js      short loc_1800034DC
0x180003475  mov     rcx, [rbp+57h+var_80]
0x180003479  lea     r8, [rbp+57h+var_78]
0x18000347d  lea     rdx, IID_IVdsVolumePlex
0x180003484  mov     rax, [rcx]
0x180003487  mov     rax, [rax]
0x18000348a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000348f  mov     ebx, eax
0x180003491  test    eax, eax
0x180003493  js      short loc_1800034DC
0x180003495  mov     rcx, [rbp+57h+var_78]
0x180003499  lea     r8, [rbp+57h+var_90]
0x18000349d  lea     rdx, [rbp+57h+var_68]
0x1800034a1  mov     rax, [rcx]
0x1800034a4  mov     rax, [rax+28h]
0x1800034a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ad  mov     ebx, eax
0x1800034af  test    eax, eax
0x1800034b1  js      short loc_1800034DC
0x1800034b3  cmp     [rbp+57h+var_90], 1
0x1800034b7  jnz     short loc_1800034D7
0x1800034b9  mov     rcx, [rbp+57h+var_68]
0x1800034bd  test    rcx, rcx
0x1800034c0  jz      short loc_1800034D7
0x1800034c2  mov     rax, [rcx+18h]
0x1800034c6  mov     [r14], rax
0x1800034c9  test    rsi, rsi
0x1800034cc  jz      short loc_1800034DC
0x1800034ce  mov     rax, [rcx+20h]
0x1800034d2  mov     [rsi], rax
0x1800034d5  jmp     short loc_1800034DC
0x1800034d7  mov     ebx, 0C0A00009h
0x1800034dc  mov     rcx, [rbp+57h+var_88]
0x1800034e0  test    rcx, rcx
0x1800034e3  jz      short loc_1800034F9
0x1800034e5  mov     rax, [rcx]
0x1800034e8  mov     rax, [rax+10h]
0x1800034ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f1  mov     [rbp+57h+var_88], 0
0x1800034f9  mov     rcx, [rbp+57h+var_80]
0x1800034fd  test    rcx, rcx
0x180003500  jz      short loc_180003516
0x180003502  mov     rax, [rcx]
0x180003505  mov     rax, [rax+10h]
0x180003509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350e  mov     [rbp+57h+var_80], 0
0x180003516  mov     rcx, [rbp+57h+var_78]
0x18000351a  test    rcx, rcx
0x18000351d  jz      short loc_180003533
0x18000351f  mov     rax, [rcx]
0x180003522  mov     rax, [rax+10h]
0x180003526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352b  mov     [rbp+57h+var_78], 0
0x180003533  mov     rcx, [rbp+57h+pv]; pv
0x180003537  test    rcx, rcx
0x18000353a  jz      short loc_18000354A
0x18000353c  call    cs:__imp_CoTaskMemFree
0x180003542  mov     [rbp+57h+pv], 0
0x18000354a  mov     rcx, [rbp+57h+var_68]; pv
0x18000354e  test    rcx, rcx
0x180003551  jz      short loc_180003559
0x180003553  call    cs:__imp_CoTaskMemFree
0x180003559  mov     eax, ebx
0x18000355b  mov     rcx, [rbp+57h+var_28]
0x18000355f  xor     rcx, rsp; StackCookie
0x180003562  call    __security_check_cookie
0x180003567  add     rsp, 0A0h
0x18000356e  pop     r14
0x180003570  pop     rdi
0x180003571  pop     rsi
0x180003572  pop     rbx
0x180003573  pop     rbp
0x180003574  retn
```
