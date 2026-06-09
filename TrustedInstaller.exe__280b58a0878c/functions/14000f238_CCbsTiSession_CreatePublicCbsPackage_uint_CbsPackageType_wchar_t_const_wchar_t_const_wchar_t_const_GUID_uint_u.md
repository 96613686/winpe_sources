# CCbsTiSession::CreatePublicCbsPackage(uint,_CbsPackageType,wchar_t const *,wchar_t const *,wchar_t const *,_GUID,uint,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,IUnknown * *)

- ea: `0x14000f238`
- end: `0x14000f45e`
- name: `?CreatePublicCbsPackage@CCbsTiSession@@QEAAJIW4_CbsPackageType@@PEB_W11U_GUID@@IIQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUIUnknown@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct CCbsTiSession *, unsigned int, int, const wchar_t *, __int64, wchar_t *, struct _GUID *, unsigned int, int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000f1d4`
- `0x14000f484`

## callees

- `0x140002070`
- `0x1400023e0`
- `0x14000f020`
- `0x14000f238`
- `0x1400130e0`
- `0x1400139cc`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x14000f38f`: `Failed to create internal CBS package`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::CreatePublicCbsPackage(
        struct CCbsTiSession *a1,
        unsigned int a2,
        int a3,
        const wchar_t *a4,
        __int64 a5,
        wchar_t *a6,
        struct _GUID *a7,
        unsigned int a8,
        int a9,
        __int64 a10,
        int a11,
        __int64 a12)
{
  unsigned int v15; // ebx
  CCbsTiPackage *v16; // rax
  CCbsTiPackage *v17; // rdi
  int v18; // eax
  int v19; // eax
  CCbsTiPackage *v20; // rcx
  char *v21; // rcx
  struct _GUID v24; // [rsp+70h] [rbp-31h] BYREF
  struct _GUID v25; // [rsp+80h] [rbp-21h] BYREF
  struct ICbsPackage *v26; // [rsp+90h] [rbp-11h] BYREF

  *(_QWORD *)&v24.Data1 = a5;
  v26 = 0;
  if ( !a12 )
  {
    v15 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: ppPackage.");
    goto LABEL_15;
  }
  v16 = (CCbsTiPackage *)operator new(0x60u);
  if ( v16 )
  {
    v17 = CCbsTiPackage::CCbsTiPackage(v16, a1);
    if ( v17 )
    {
      if ( a3 == 3 )
      {
        v24 = *a7;
        v18 = CCbsTiPackage::Initialize(v17, a4, 0, a6, &v24, a8);
        v15 = v18;
        if ( v18 < 0 )
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v18, 1, "Failed to initialize TiPackage.");
          goto LABEL_13;
        }
      }
      else
      {
        v25 = *a7;
        v19 = CCbsTiSession::CreateInternalCbsPackage(
                a1,
                a2,
                a6,
                &v25,
                a8,
                a3,
                a4,
                *(_QWORD *)&v24.Data1,
                a9,
                a10,
                a11,
                &v26);
        v15 = v19;
        if ( v19 < 0 )
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v19, 1, "Failed to create internal CBS package");
LABEL_13:
          v21 = (char *)v17 + *(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
          goto LABEL_15;
        }
        v25 = GUID_NULL;
        CCbsTiPackage::Initialize(v17, 0, v26, 0, &v25, 0);
      }
      v20 = (CCbsTiPackage *)((char *)v17 + *(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8);
      v15 = (**(__int64 (__fastcall ***)(CCbsTiPackage *, GUID *, __int64))v20)(
              v20,
              &GUID_00000000_0000_0000_c000_000000000046,
              a12);
      goto LABEL_13;
    }
  }
  v15 = -2147024882;
  CBSWdsLogLight(0x4000000, 2147942414LL, 1, "Failed to allocate new Ti Package");
LABEL_15:
  if ( v26 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v26 + 16LL))(v26);
  return v15;
}

```

## disassembly

```asm
0x14000f238  push    rbp
0x14000f23a  push    rbx
0x14000f23b  push    rsi
0x14000f23c  push    rdi
0x14000f23d  push    r12
0x14000f23f  push    r13
0x14000f241  push    r14
0x14000f243  push    r15
0x14000f245  lea     rbp, [rsp-7]
0x14000f24a  sub     rsp, 0A8h
0x14000f251  mov     rax, cs:__security_cookie
0x14000f258  xor     rax, rsp
0x14000f25b  mov     [rbp+3Fh+var_48], rax
0x14000f25f  mov     rax, [rbp+3Fh+arg_20]
0x14000f263  mov     r14, r9
0x14000f266  mov     r15, [rbp+3Fh+arg_28]
0x14000f26a  mov     ebx, r8d
0x14000f26d  mov     r12, [rbp+3Fh+arg_30]
0x14000f271  mov     rsi, rcx
0x14000f274  mov     r13, [rbp+3Fh+arg_58]
0x14000f27b  mov     qword ptr [rbp+3Fh+var_70.Data1], rax
0x14000f27f  mov     rax, [rbp+3Fh+arg_48]
0x14000f286  mov     [rbp+3Fh+var_78], rax
0x14000f28a  mov     [rbp+3Fh+var_80], edx
0x14000f28d  mov     [rbp+3Fh+var_50], 0
0x14000f295  test    r13, r13
0x14000f298  jnz     short loc_14000F2AB
0x14000f29a  mov     ebx, 80004003h
0x14000f29f  lea     r9, aInvalidArgumen_26; "Invalid argument: ppPackage."
0x14000f2a6  jmp     loc_14000F415
0x14000f2ab  mov     ecx, 60h ; '`'; Size
0x14000f2b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f2b5  test    rax, rax
0x14000f2b8  jz      loc_14000F409
0x14000f2be  mov     rdx, rsi; struct CCbsTiSession *
0x14000f2c1  mov     rcx, rax; this
0x14000f2c4  call    ??0CCbsTiPackage@@QEAA@PEAVCCbsTiSession@@@Z; CCbsTiPackage::CCbsTiPackage(CCbsTiSession *)
0x14000f2c9  mov     rdi, rax
0x14000f2cc  test    rax, rax
0x14000f2cf  jz      loc_14000F409
0x14000f2d5  movaps  xmm0, xmmword ptr [r12]
0x14000f2da  cmp     ebx, 3
0x14000f2dd  jnz     short loc_14000F330
0x14000f2df  mov     eax, [rbp+3Fh+arg_38]
0x14000f2e5  mov     r9, r15; wchar_t *
0x14000f2e8  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14000f2ec  xor     r8d, r8d; struct ICbsPackage *
0x14000f2ef  lea     rax, [rbp+3Fh+var_70]
0x14000f2f3  movdqa  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x14000f2f8  mov     rdx, r14; wchar_t *
0x14000f2fb  mov     [rsp+0E0h+var_C0], rax; struct _GUID *
0x14000f300  mov     rcx, rdi; this
0x14000f303  call    ?Initialize@CCbsTiPackage@@QEAAJPEB_WPEAUICbsPackage@@0U_GUID@@I@Z; CCbsTiPackage::Initialize(wchar_t const *,ICbsPackage *,wchar_t const *,_GUID,uint)
0x14000f308  mov     ebx, eax
0x14000f30a  test    eax, eax
0x14000f30c  jns     loc_14000F3C6
0x14000f312  lea     r9, aFailedToInitia_8; "Failed to initialize TiPackage."
0x14000f319  mov     r8d, 1
0x14000f31f  mov     edx, eax
0x14000f321  mov     ecx, 4000000h
0x14000f326  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f32b  jmp     loc_14000F3EC
0x14000f330  mov     edx, [rbp+3Fh+var_80]
0x14000f333  lea     rax, [rbp+3Fh+var_50]
0x14000f337  mov     [rsp+0E0h+var_88], rax
0x14000f33c  lea     r9, [rbp+3Fh+var_60]
0x14000f340  mov     eax, [rbp+3Fh+arg_50]
0x14000f346  mov     r8, r15
0x14000f349  mov     [rsp+0E0h+var_90], eax
0x14000f34d  mov     rcx, rsi
0x14000f350  mov     rax, [rbp+3Fh+var_78]
0x14000f354  mov     [rsp+0E0h+var_98], rax
0x14000f359  mov     eax, [rbp+3Fh+arg_40]
0x14000f35f  mov     [rsp+0E0h+var_A0], eax
0x14000f363  mov     rax, qword ptr [rbp+3Fh+var_70.Data1]
0x14000f367  mov     [rsp+0E0h+var_A8], rax
0x14000f36c  mov     eax, [rbp+3Fh+arg_38]
0x14000f372  mov     [rsp+0E0h+var_B0], r14
0x14000f377  mov     [rsp+0E0h+var_B8], ebx
0x14000f37b  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14000f37f  movdqa  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x14000f384  call    ?CreateInternalCbsPackage@CCbsTiSession@@QEAAJIPEB_WU_GUID@@IW4_CbsPackageType@@00IQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUICbsPackage@@@Z; CCbsTiSession::CreateInternalCbsPackage(uint,wchar_t const *,_GUID,uint,_CbsPackageType,wchar_t const *,wchar_t const *,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,ICbsPackage * *)
0x14000f389  mov     ebx, eax
0x14000f38b  test    eax, eax
0x14000f38d  jns     short loc_14000F398
0x14000f38f  lea     r9, aFailedToCreate_8; "Failed to create internal CBS package"
0x14000f396  jmp     short loc_14000F319
0x14000f398  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000f39f  mov     r8, [rbp+3Fh+var_50]; struct ICbsPackage *
0x14000f3a3  lea     rax, [rbp+3Fh+var_60]
0x14000f3a7  mov     [rsp+0E0h+var_B8], 0; unsigned int
0x14000f3af  xor     r9d, r9d; wchar_t *
0x14000f3b2  xor     edx, edx; wchar_t *
0x14000f3b4  mov     [rsp+0E0h+var_C0], rax; struct _GUID *
0x14000f3b9  mov     rcx, rdi; this
0x14000f3bc  movdqu  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x14000f3c1  call    ?Initialize@CCbsTiPackage@@QEAAJPEB_WPEAUICbsPackage@@0U_GUID@@I@Z; CCbsTiPackage::Initialize(wchar_t const *,ICbsPackage *,wchar_t const *,_GUID,uint)
0x14000f3c6  mov     rax, [rdi+8]
0x14000f3ca  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000f3d1  mov     r8, r13
0x14000f3d4  movsxd  rcx, dword ptr [rax+4]
0x14000f3d8  add     rcx, 8
0x14000f3dc  add     rcx, rdi
0x14000f3df  mov     rax, [rcx]
0x14000f3e2  mov     rax, [rax]
0x14000f3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3ea  mov     ebx, eax
0x14000f3ec  mov     rax, [rdi+8]
0x14000f3f0  movsxd  rcx, dword ptr [rax+4]
0x14000f3f4  add     rcx, 8
0x14000f3f8  add     rcx, rdi
0x14000f3fb  mov     rax, [rcx]
0x14000f3fe  mov     rax, [rax+10h]
0x14000f402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f407  jmp     short loc_14000F427
0x14000f409  mov     ebx, 8007000Eh
0x14000f40e  lea     r9, aFailedToAlloca_2; "Failed to allocate new Ti Package"
0x14000f415  mov     r8d, 1
0x14000f41b  mov     edx, ebx
0x14000f41d  mov     ecx, 4000000h
0x14000f422  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f427  mov     rcx, [rbp+3Fh+var_50]
0x14000f42b  test    rcx, rcx
0x14000f42e  jz      short loc_14000F43C
0x14000f430  mov     rax, [rcx]
0x14000f433  mov     rax, [rax+10h]
0x14000f437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f43c  mov     eax, ebx
0x14000f43e  mov     rcx, [rbp+3Fh+var_48]
0x14000f442  xor     rcx, rsp; StackCookie
0x14000f445  call    __security_check_cookie
0x14000f44a  add     rsp, 0A8h
0x14000f451  pop     r15
0x14000f453  pop     r14
0x14000f455  pop     r13
0x14000f457  pop     r12
0x14000f459  pop     rdi
0x14000f45a  pop     rsi
0x14000f45b  pop     rbx
0x14000f45c  pop     rbp
0x14000f45d  retn
```
