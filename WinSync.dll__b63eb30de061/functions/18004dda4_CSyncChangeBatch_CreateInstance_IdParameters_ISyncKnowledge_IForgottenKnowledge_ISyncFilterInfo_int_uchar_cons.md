# CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)

- ea: `0x18004dda4`
- end: `0x18004e175`
- name: `?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct IdParameters *this, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncFilterInfo *, int, unsigned __int8 *, int, void **)`
- caller_count: `7`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180021cbc`
- `0x18002b230`
- `0x18002b570`
- `0x18002b960`
- `0x18002bac0`
- `0x18002bd30`
- `0x18003d348`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002d180`
- `0x18002d1c8`
- `0x18004beec`
- `0x18004dda4`
- `0x1800520c0`
- `0x1800539c4`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x18004de18`: `CSyncChangeBatch_CreateInstance`
- `0x18004e137`: `CSyncChangeBatch_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch_CreateInstance(
        struct IdParameters *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge *a3,
        struct ISyncFilterInfo *a4,
        int a5,
        unsigned __int8 *a6,
        int a7,
        void **a8)
{
  unsigned __int8 *v8; // rax
  void **v10; // rcx
  PVOID *v13; // r10
  int Parameters; // ebx
  _QWORD *v15; // rdi
  struct IForgottenKnowledgeVtbl *lpVtbl; // rax
  void *v17; // rax
  CSyncChangeBatch *v18; // rax
  CSyncChangeBatch *v19; // rsi
  __int64 v21; // [rsp+40h] [rbp-81h] BYREF
  __int64 v22; // [rsp+48h] [rbp-79h] BYREF
  __int64 v23; // [rsp+50h] [rbp-71h] BYREF
  struct ISyncFilterInfo *v24; // [rsp+58h] [rbp-69h]
  unsigned __int8 *v25; // [rsp+60h] [rbp-61h]
  void **v26; // [rsp+68h] [rbp-59h]
  struct _ID_PARAMETERS v27; // [rsp+70h] [rbp-51h] BYREF
  struct _ID_PARAMETERS v28; // [rsp+90h] [rbp-31h] BYREF

  v8 = a6;
  v10 = a8;
  v26 = a8;
  v24 = a4;
  v25 = a6;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      114,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch_CreateInstance");
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v8 = v25;
    a4 = v24;
    v10 = v26;
  }
  Parameters = -2147467261;
  if ( this )
  {
    if ( v10 )
    {
      Parameters = -2147024809;
      if ( (!a5 || !a7) && (!a4 || !a7) && (!v8 || a5) )
      {
        v21 = 0;
        v28.dwSize = 28;
        v27.dwSize = 28;
        memset(&v27.replicaId, 0, 24);
        memset(&v28.replicaId, 0, 24);
        Parameters = IdParameters::GetParameters(this, &v27);
        if ( Parameters >= 0 )
        {
          if ( !a2 )
            goto LABEL_46;
          Parameters = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                         a2,
                         &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8,
                         &v21);
          if ( Parameters < 0 )
            goto LABEL_38;
          Parameters = (*(__int64 (__fastcall **)(__int64, struct _ID_PARAMETERS *))(*(_QWORD *)v21 + 216LL))(v21, &v28);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v21 = 0;
          if ( Parameters < 0 )
            goto LABEL_38;
          if ( (unsigned int)IdParameters::EqualParameters(&v27, &v28) )
          {
LABEL_46:
            if ( !a3 )
              goto LABEL_23;
            Parameters = ((__int64 (__fastcall *)(struct IForgottenKnowledge *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
                           a3,
                           &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8,
                           &v21);
            if ( Parameters < 0 )
              goto LABEL_38;
            Parameters = (*(__int64 (__fastcall **)(__int64, struct _ID_PARAMETERS *))(*(_QWORD *)v21 + 216LL))(
                           v21,
                           &v28);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            v21 = 0;
            if ( Parameters < 0 )
              goto LABEL_38;
            if ( (unsigned int)IdParameters::EqualParameters(&v27, &v28) )
            {
LABEL_23:
              Parameters = -2147024882;
              v15 = SeAlloc(0x28u);
              if ( v15 )
              {
                v15[2] = 0;
                *v15 = &CollectionManager<CSyncChangeUnitWrapper>::`vftable';
                *((_DWORD *)v15 + 2) = 1;
                v15[3] = 0;
                *((_DWORD *)v15 + 8) = 0;
                _InterlockedIncrement(&g_cRefThisDll);
                v23 = 0;
                if ( !a3
                  || (lpVtbl = a3->lpVtbl,
                      v22 = 0,
                      Parameters = ((__int64 (__fastcall *)(struct IForgottenKnowledge *, __int64 *))lpVtbl->Clone)(
                                     a3,
                                     &v22),
                      Parameters >= 0)
                  && (Parameters = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
                                     v22,
                                     &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
                                     &v23),
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22),
                      Parameters >= 0) )
                {
                  v17 = SeAlloc(0x108u);
                  if ( v17
                    && (v18 = (CSyncChangeBatch *)CSyncChangeBatch::CSyncChangeBatch(
                                                    (_DWORD)v17,
                                                    (_DWORD)this,
                                                    (_DWORD)v15,
                                                    (_DWORD)a2,
                                                    v23,
                                                    (__int64)v24,
                                                    a5,
                                                    a7),
                        (v19 = v18) != 0) )
                  {
                    Parameters = CSyncChangeBatch::Init(v18);
                    if ( Parameters >= 0 )
                    {
                      if ( !a5
                        || (Parameters = CSyncChangeBatch::SetClosedLowerBoundForFullEnumeration(v19, v25),
                            Parameters >= 0) )
                      {
                        (*(void (__fastcall **)(CSyncChangeBatch *))(*(_QWORD *)v19 + 8LL))(v19);
                        *v26 = v19;
                      }
                    }
                    (*(void (__fastcall **)(CSyncChangeBatch *))(*(_QWORD *)v19 + 16LL))(v19);
                  }
                  else
                  {
                    Parameters = -2147024882;
                  }
                }
                if ( v23 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
              }
              goto LABEL_38;
            }
          }
          Parameters = -2147217408;
LABEL_38:
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v13[2],
      115,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch_CreateInstance",
      Parameters);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x18004dda4  push    rbp
0x18004dda6  push    rbx
0x18004dda7  push    rsi
0x18004dda8  push    rdi
0x18004dda9  push    r12
0x18004ddab  push    r13
0x18004ddad  push    r14
0x18004ddaf  push    r15
0x18004ddb1  lea     rbp, [rsp-7]
0x18004ddb6  sub     rsp, 0C8h
0x18004ddbd  mov     rax, cs:__security_cookie
0x18004ddc4  xor     rax, rsp
0x18004ddc7  mov     [rbp+3Fh+var_50], rax
0x18004ddcb  mov     rax, [rbp+3Fh+arg_28]
0x18004ddcf  mov     r13, rcx
0x18004ddd2  mov     rcx, [rbp+3Fh+arg_38]
0x18004ddd9  mov     rsi, r8
0x18004dddc  mov     r14d, [rbp+3Fh+arg_20]
0x18004dde0  mov     r15, rdx
0x18004dde3  mov     r12d, [rbp+3Fh+arg_30]
0x18004dde7  mov     [rbp+3Fh+var_98], rcx
0x18004ddeb  mov     [rbp+3Fh+var_A8], r9
0x18004ddef  mov     [rbp+3Fh+var_A0], rax
0x18004ddf3  mov     r10, cs:WPP_GLOBAL_Control
0x18004ddfa  lea     rdx, WPP_GLOBAL_Control
0x18004de01  cmp     r10, rdx
0x18004de04  jz      short loc_18004DE43
0x18004de06  test    byte ptr [r10+1Ch], 10h
0x18004de0b  jz      short loc_18004DE43
0x18004de0d  cmp     byte ptr [r10+19h], 5
0x18004de12  jb      short loc_18004DE43
0x18004de14  mov     rcx, [r10+10h]
0x18004de18  lea     r9, aCsyncchangebat_28; "CSyncChangeBatch_CreateInstance"
0x18004de1f  mov     edx, 72h ; 'r'
0x18004de24  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18004de2b  call    WPP_SF_s
0x18004de30  mov     r10, cs:WPP_GLOBAL_Control
0x18004de37  mov     rax, [rbp+3Fh+var_A0]
0x18004de3b  mov     r9, [rbp+3Fh+var_A8]
0x18004de3f  mov     rcx, [rbp+3Fh+var_98]
0x18004de43  xor     edi, edi
0x18004de45  mov     ebx, 80004003h
0x18004de4a  test    r13, r13
0x18004de4d  jz      loc_18004E119
0x18004de53  test    rcx, rcx
0x18004de56  jz      loc_18004E119
0x18004de5c  mov     ebx, 80070057h
0x18004de61  test    r14d, r14d
0x18004de64  jz      short loc_18004DE6F
0x18004de66  test    r12d, r12d
0x18004de69  jnz     loc_18004E119
0x18004de6f  test    r9, r9
0x18004de72  jz      short loc_18004DE7D
0x18004de74  test    r12d, r12d
0x18004de77  jnz     loc_18004E119
0x18004de7d  test    rax, rax
0x18004de80  jz      short loc_18004DE8B
0x18004de82  test    r14d, r14d
0x18004de85  jz      loc_18004E119
0x18004de8b  mov     eax, 1Ch
0x18004de90  mov     [rsp+100h+var_C0], rdi
0x18004de95  xorps   xmm0, xmm0
0x18004de98  mov     [rbp+3Fh+var_70.dwSize], eax
0x18004de9b  xorps   xmm1, xmm1
0x18004de9e  mov     [rbp+3Fh+var_90.dwSize], eax
0x18004dea1  lea     rdx, [rbp+3Fh+var_90]; struct _ID_PARAMETERS *
0x18004dea5  mov     qword ptr [rbp+3Fh+var_90.changeUnitId.fIsVariable], rdi
0x18004dea9  mov     rcx, r13; this
0x18004deac  mov     qword ptr [rbp+3Fh+var_70.changeUnitId.fIsVariable], rdi
0x18004deb0  movdqu  xmmword ptr [rbp+3Fh+var_90.replicaId.fIsVariable], xmm0
0x18004deb5  movdqu  xmmword ptr [rbp+3Fh+var_70.replicaId.fIsVariable], xmm1
0x18004deba  call    ?GetParameters@IdParameters@@QEAAJPEAU_ID_PARAMETERS@@@Z; IdParameters::GetParameters(_ID_PARAMETERS *)
0x18004debf  mov     ebx, eax
0x18004dec1  test    eax, eax
0x18004dec3  js      loc_18004E119
0x18004dec9  test    r15, r15
0x18004decc  jz      short loc_18004DF45
0x18004dece  mov     rax, [r15]
0x18004ded1  lea     r8, [rsp+100h+var_C0]
0x18004ded6  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x18004dedd  mov     rcx, r15
0x18004dee0  mov     rax, [rax]
0x18004dee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dee8  mov     ebx, eax
0x18004deea  test    eax, eax
0x18004deec  js      loc_18004E112
0x18004def2  mov     rcx, [rsp+100h+var_C0]
0x18004def7  lea     rdx, [rbp+3Fh+var_70]
0x18004defb  mov     rax, [rcx]
0x18004defe  mov     rax, [rax+0D8h]
0x18004df05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df0a  mov     rcx, [rsp+100h+var_C0]
0x18004df0f  mov     ebx, eax
0x18004df11  mov     rax, [rcx]
0x18004df14  mov     rax, [rax+10h]
0x18004df18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df1d  mov     [rsp+100h+var_C0], rdi
0x18004df22  test    ebx, ebx
0x18004df24  js      loc_18004E112
0x18004df2a  lea     rdx, [rbp+3Fh+var_70]; struct _ID_PARAMETERS *
0x18004df2e  lea     rcx, [rbp+3Fh+var_90]; struct _ID_PARAMETERS *
0x18004df32  call    ?EqualParameters@IdParameters@@SAHPEBU_ID_PARAMETERS@@0@Z; IdParameters::EqualParameters(_ID_PARAMETERS const *,_ID_PARAMETERS const *)
0x18004df37  test    eax, eax
0x18004df39  jnz     short loc_18004DF45
0x18004df3b  mov     ebx, 80041000h
0x18004df40  jmp     loc_18004E112
0x18004df45  test    rsi, rsi
0x18004df48  jz      short loc_18004DFB7
0x18004df4a  mov     rax, [rsi]
0x18004df4d  lea     r8, [rsp+100h+var_C0]
0x18004df52  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x18004df59  mov     rcx, rsi
0x18004df5c  mov     rax, [rax]
0x18004df5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df64  mov     ebx, eax
0x18004df66  test    eax, eax
0x18004df68  js      loc_18004E112
0x18004df6e  mov     rcx, [rsp+100h+var_C0]
0x18004df73  lea     rdx, [rbp+3Fh+var_70]
0x18004df77  mov     rax, [rcx]
0x18004df7a  mov     rax, [rax+0D8h]
0x18004df81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df86  mov     rcx, [rsp+100h+var_C0]
0x18004df8b  mov     ebx, eax
0x18004df8d  mov     rax, [rcx]
0x18004df90  mov     rax, [rax+10h]
0x18004df94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df99  mov     [rsp+100h+var_C0], rdi
0x18004df9e  test    ebx, ebx
0x18004dfa0  js      loc_18004E112
0x18004dfa6  lea     rdx, [rbp+3Fh+var_70]; struct _ID_PARAMETERS *
0x18004dfaa  lea     rcx, [rbp+3Fh+var_90]; struct _ID_PARAMETERS *
0x18004dfae  call    ?EqualParameters@IdParameters@@SAHPEBU_ID_PARAMETERS@@0@Z; IdParameters::EqualParameters(_ID_PARAMETERS const *,_ID_PARAMETERS const *)
0x18004dfb3  test    eax, eax
0x18004dfb5  jz      short loc_18004DF3B
0x18004dfb7  mov     ecx, 28h ; '('; unsigned __int64
0x18004dfbc  mov     ebx, 8007000Eh
0x18004dfc1  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004dfc6  xor     ecx, ecx
0x18004dfc8  mov     rdi, rax
0x18004dfcb  test    rax, rax
0x18004dfce  jz      loc_18004E112
0x18004dfd4  lea     rax, ??_7?$CollectionManager@VCSyncChangeUnitWrapper@@@@6B@; const CollectionManager<CSyncChangeUnitWrapper>::`vftable'
0x18004dfdb  mov     [rdi+10h], rcx
0x18004dfdf  mov     [rdi], rax
0x18004dfe2  mov     dword ptr [rdi+8], 1
0x18004dfe9  mov     [rdi+18h], rcx
0x18004dfed  mov     [rdi+20h], ecx
0x18004dff0  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x18004dff7  mov     [rbp+3Fh+var_B0], rcx
0x18004dffb  test    rsi, rsi
0x18004dffe  jz      short loc_18004E055
0x18004e000  mov     rax, [rsi]
0x18004e003  lea     rdx, [rbp+3Fh+var_B8]
0x18004e007  mov     [rbp+3Fh+var_B8], rcx
0x18004e00b  mov     rcx, rsi
0x18004e00e  mov     rax, [rax+50h]
0x18004e012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e017  mov     ebx, eax
0x18004e019  test    eax, eax
0x18004e01b  js      loc_18004E0EE
0x18004e021  mov     rcx, [rbp+3Fh+var_B8]
0x18004e025  lea     r8, [rbp+3Fh+var_B0]
0x18004e029  lea     rdx, _GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2
0x18004e030  mov     rax, [rcx]
0x18004e033  mov     rax, [rax]
0x18004e036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e03b  mov     rcx, [rbp+3Fh+var_B8]
0x18004e03f  mov     ebx, eax
0x18004e041  mov     rax, [rcx]
0x18004e044  mov     rax, [rax+10h]
0x18004e048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e04d  test    ebx, ebx
0x18004e04f  js      loc_18004E0EE
0x18004e055  mov     ecx, 108h; unsigned __int64
0x18004e05a  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004e05f  test    rax, rax
0x18004e062  jz      loc_18004E0E9
0x18004e068  mov     rcx, [rbp+3Fh+var_A8]
0x18004e06c  mov     r9, r15
0x18004e06f  mov     [rsp+100h+var_C8], r12d
0x18004e074  mov     r8, rdi
0x18004e077  mov     [rsp+100h+var_D0], r14d
0x18004e07c  mov     rdx, r13
0x18004e07f  mov     [rsp+100h+var_D8], rcx
0x18004e084  mov     rcx, [rbp+3Fh+var_B0]
0x18004e088  mov     [rsp+100h+var_E0], rcx
0x18004e08d  mov     rcx, rax
0x18004e090  call    ??0CSyncChangeBatch@@QEAA@PEAVIdParameters@@PEAV?$CollectionManager@VCSyncChange@@@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HH@Z; CSyncChangeBatch::CSyncChangeBatch(IdParameters *,CollectionManager<CSyncChange> *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,int)
0x18004e095  mov     rsi, rax
0x18004e098  test    rax, rax
0x18004e09b  jz      short loc_18004E0E9
0x18004e09d  mov     rcx, rax; this
0x18004e0a0  call    ?Init@CSyncChangeBatch@@QEAAJXZ; CSyncChangeBatch::Init(void)
0x18004e0a5  mov     ebx, eax
0x18004e0a7  test    eax, eax
0x18004e0a9  js      short loc_18004E0D8
0x18004e0ab  test    r14d, r14d
0x18004e0ae  jz      short loc_18004E0C2
0x18004e0b0  mov     rdx, [rbp+3Fh+var_A0]; unsigned __int8 *
0x18004e0b4  mov     rcx, rsi; this
0x18004e0b7  call    ?SetClosedLowerBoundForFullEnumeration@CSyncChangeBatch@@QEAAJPEBE@Z; CSyncChangeBatch::SetClosedLowerBoundForFullEnumeration(uchar const *)
0x18004e0bc  mov     ebx, eax
0x18004e0be  test    eax, eax
0x18004e0c0  js      short loc_18004E0D8
0x18004e0c2  mov     rax, [rsi]
0x18004e0c5  mov     rcx, rsi
0x18004e0c8  mov     rax, [rax+8]
0x18004e0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0d1  mov     rax, [rbp+3Fh+var_98]
0x18004e0d5  mov     [rax], rsi
0x18004e0d8  mov     rax, [rsi]
0x18004e0db  mov     rcx, rsi
0x18004e0de  mov     rax, [rax+10h]
0x18004e0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0e7  jmp     short loc_18004E0EE
0x18004e0e9  mov     ebx, 8007000Eh
0x18004e0ee  mov     rcx, [rbp+3Fh+var_B0]
0x18004e0f2  test    rcx, rcx
0x18004e0f5  jz      short loc_18004E103
0x18004e0f7  mov     rax, [rcx]
0x18004e0fa  mov     rax, [rax+10h]
0x18004e0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e103  mov     rax, [rdi]
0x18004e106  mov     rcx, rdi
0x18004e109  mov     rax, [rax+10h]
0x18004e10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e112  mov     r10, cs:WPP_GLOBAL_Control
0x18004e119  lea     rax, WPP_GLOBAL_Control
0x18004e120  cmp     r10, rax
0x18004e123  jz      short loc_18004E153
0x18004e125  test    byte ptr [r10+1Ch], 10h
0x18004e12a  jz      short loc_18004E153
0x18004e12c  cmp     byte ptr [r10+19h], 5
0x18004e131  jb      short loc_18004E153
0x18004e133  mov     rcx, [r10+10h]
0x18004e137  lea     r9, aCsyncchangebat_28; "CSyncChangeBatch_CreateInstance"
0x18004e13e  mov     edx, 73h ; 's'
0x18004e143  mov     dword ptr [rsp+100h+var_E0], ebx
0x18004e147  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18004e14e  call    WPP_SF_sD
0x18004e153  mov     eax, ebx
0x18004e155  mov     rcx, [rbp+3Fh+var_50]
0x18004e159  xor     rcx, rsp; StackCookie
0x18004e15c  call    __security_check_cookie
0x18004e161  add     rsp, 0C8h
0x18004e168  pop     r15
0x18004e16a  pop     r14
0x18004e16c  pop     r13
0x18004e16e  pop     r12
0x18004e170  pop     rdi
0x18004e171  pop     rsi
0x18004e172  pop     rbx
0x18004e173  pop     rbp
0x18004e174  retn
```
