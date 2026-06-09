# CALACDecMFT::Initialize(void)

- ea: `0x180002ec4`
- end: `0x18000323c`
- name: `?Initialize@CALACDecMFT@@QEAAJXZ`
- size: `888`
- prototype: `__int64 __fastcall(CALACDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800028a0`

## callees

- `0x180001104`
- `0x180002ec4`
- `0x180003e54`
- `0x180003f08`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180002f1b`
- `MFPlat!MFCreateMediaType` at `0x180002ff0`
- `MFPlat!MFCreateMediaType` at `0x1800030c2`
- `MFPlat!MFCreateMediaType` at `0x180002f1b`
- `MFPlat!MFCreateMediaType` at `0x180002ff0`
- `MFPlat!MFCreateMediaType` at `0x1800030c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CALACDecMFT::Initialize(CALACDecMFT *this)
{
  HRESULT inited; // ebx
  IMFMediaType *v3; // rcx
  IMFMediaType *v4; // rbx
  __int64 v5; // rcx
  IMFMediaType *v6; // rcx
  IMFMediaType *v7; // rbx
  __int64 v8; // rcx
  IMFMediaType *v9; // rcx
  IMFMediaType *v10; // rsi
  __int64 v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  int v14; // eax
  IMFMediaType *v15; // rcx
  IMFMediaType *ppMFType; // [rsp+40h] [rbp+20h] BYREF
  _QWORD *v18; // [rsp+48h] [rbp+28h]

  *((_DWORD *)this + 36) = 0;
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableInputTypeArray(this, 2u);
  if ( inited >= 0 )
  {
    v3 = ppMFType;
    if ( ppMFType )
    {
      ppMFType = 0;
      ((void (__fastcall *)(IMFMediaType *))v3->lpVtbl->Release)(v3);
    }
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Audio);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, void *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_ALAC);
        if ( inited >= 0 )
        {
          if ( *((_DWORD *)this + 2) )
          {
            v4 = ppMFType;
            v5 = **((_QWORD **)this + 2);
            if ( v5 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
              **((_QWORD **)this + 2) = 0;
            }
            **((_QWORD **)this + 2) = v4;
            (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 2) + 8LL))(**((_QWORD **)this + 2));
            *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) = 1;
          }
          v6 = ppMFType;
          if ( ppMFType )
          {
            ppMFType = 0;
            ((void (__fastcall *)(IMFMediaType *))v6->lpVtbl->Release)(v6);
          }
          inited = MFCreateMediaType(&ppMFType);
          if ( inited >= 0 )
          {
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                       ppMFType,
                       &MF_MT_MAJOR_TYPE,
                       &MFMediaType_Audio);
            if ( inited >= 0 )
            {
              inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const char *))ppMFType->lpVtbl->SetGUID)(
                         ppMFType,
                         &MF_MT_SUBTYPE,
                         "alac");
              if ( inited >= 0 )
              {
                if ( *((_DWORD *)this + 2) > 1u )
                {
                  v7 = ppMFType;
                  v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
                  if ( v8 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
                    *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) = 0;
                  }
                  *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) = v7;
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 16LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL));
                  *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) = 1;
                }
                v9 = ppMFType;
                if ( ppMFType )
                {
                  ppMFType = 0;
                  ((void (__fastcall *)(IMFMediaType *))v9->lpVtbl->Release)(v9);
                }
                inited = MFCreateMediaType(&ppMFType);
                if ( inited >= 0 )
                {
                  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                             ppMFType,
                             &MF_MT_MAJOR_TYPE,
                             &MFMediaType_Audio);
                  if ( inited >= 0 )
                  {
                    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                               ppMFType,
                               &MF_MT_SUBTYPE,
                               &MFAudioFormat_PCM);
                    if ( inited >= 0 )
                    {
                      inited = CMFTSimpleBase::_InitAvailableOutputTypeArray(this, 1u);
                      if ( inited >= 0 )
                      {
                        if ( *((_DWORD *)this + 6) )
                        {
                          v10 = ppMFType;
                          v11 = **((_QWORD **)this + 4);
                          if ( v11 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                            **((_QWORD **)this + 4) = 0;
                          }
                          **((_QWORD **)this + 4) = v10;
                          (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 4) + 8LL))(**((_QWORD **)this + 4));
                          *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 1;
                        }
                        v12 = operator new(0x40u);
                        v18 = v12;
                        if ( v12 )
                        {
                          v12[4] = 0;
                          v12[5] = 0;
                          v12[6] = 0;
                          v12[7] = 0;
                          *(_OWORD *)v12 = 0;
                          v12[2] = 0;
                        }
                        else
                        {
                          v12 = 0;
                        }
                        *((_QWORD *)this + 22) = v12;
                        v13 = operator new(0x18u);
                        if ( v13 )
                        {
                          *(_OWORD *)v13 = 0;
                          v13[2] = 0;
                        }
                        else
                        {
                          v13 = 0;
                        }
                        *((_QWORD *)this + 23) = v13;
                        if ( *((_QWORD *)this + 22) )
                        {
                          v14 = inited;
                          if ( !v13 )
                            v14 = -2147024882;
                          inited = v14;
                        }
                        else
                        {
                          inited = -2147024882;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v15 = ppMFType;
  if ( ppMFType )
  {
    ppMFType = 0;
    ((void (__fastcall *)(IMFMediaType *))v15->lpVtbl->Release)(v15);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180002ec4  mov     [rsp-18h+arg_10], rbx
0x180002ec9  mov     [rsp-18h+arg_18], rsi
0x180002ece  push    rbp
0x180002ecf  push    rdi
0x180002ed0  push    r14
0x180002ed2  mov     rbp, rsp
0x180002ed5  sub     rsp, 20h
0x180002ed9  mov     rdi, rcx
0x180002edc  xor     r14d, r14d
0x180002edf  mov     [rcx+90h], r14d
0x180002ee6  mov     [rbp+ppMFType], r14
0x180002eea  lea     edx, [r14+2]; unsigned int
0x180002eee  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x180002ef3  mov     ebx, eax
0x180002ef5  test    eax, eax
0x180002ef7  js      loc_18000320D
0x180002efd  mov     rcx, [rbp+ppMFType]
0x180002f01  test    rcx, rcx
0x180002f04  jz      short loc_180002F17
0x180002f06  mov     [rbp+ppMFType], r14
0x180002f0a  mov     rax, [rcx]
0x180002f0d  mov     rax, [rax+10h]
0x180002f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f16  nop
0x180002f17  lea     rcx, [rbp+ppMFType]; ppMFType
0x180002f1b  call    cs:__imp_MFCreateMediaType
0x180002f21  mov     ebx, eax
0x180002f23  test    eax, eax
0x180002f25  js      loc_18000320D
0x180002f2b  mov     rcx, [rbp+ppMFType]
0x180002f2f  mov     rax, [rcx]
0x180002f32  lea     rsi, MFMediaType_Audio
0x180002f39  mov     r8, rsi
0x180002f3c  lea     rdx, MF_MT_MAJOR_TYPE
0x180002f43  mov     rax, [rax+0C0h]
0x180002f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4f  mov     ebx, eax
0x180002f51  test    eax, eax
0x180002f53  js      loc_18000320D
0x180002f59  mov     rcx, [rbp+ppMFType]
0x180002f5d  mov     rax, [rcx]
0x180002f60  lea     r8, MFAudioFormat_ALAC
0x180002f67  lea     rdx, MF_MT_SUBTYPE
0x180002f6e  mov     rax, [rax+0C0h]
0x180002f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7a  mov     ebx, eax
0x180002f7c  test    eax, eax
0x180002f7e  js      loc_18000320D
0x180002f84  cmp     [rdi+8], r14d
0x180002f88  jbe     short loc_180002FD2
0x180002f8a  mov     rbx, [rbp+ppMFType]
0x180002f8e  mov     rax, [rdi+10h]
0x180002f92  mov     rcx, [rax]
0x180002f95  test    rcx, rcx
0x180002f98  jz      short loc_180002FAD
0x180002f9a  mov     rax, [rcx]
0x180002f9d  mov     rax, [rax+10h]
0x180002fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa6  mov     rax, [rdi+10h]
0x180002faa  mov     [rax], r14
0x180002fad  mov     rax, [rdi+10h]
0x180002fb1  mov     [rax], rbx
0x180002fb4  mov     rax, [rdi+10h]
0x180002fb8  mov     rcx, [rax]
0x180002fbb  mov     rax, [rcx]
0x180002fbe  mov     rax, [rax+8]
0x180002fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc7  mov     rax, [rdi+10h]
0x180002fcb  mov     dword ptr [rax+8], 1
0x180002fd2  mov     rcx, [rbp+ppMFType]
0x180002fd6  test    rcx, rcx
0x180002fd9  jz      short loc_180002FEC
0x180002fdb  mov     [rbp+ppMFType], r14
0x180002fdf  mov     rax, [rcx]
0x180002fe2  mov     rax, [rax+10h]
0x180002fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002feb  nop
0x180002fec  lea     rcx, [rbp+ppMFType]; ppMFType
0x180002ff0  call    cs:__imp_MFCreateMediaType
0x180002ff6  mov     ebx, eax
0x180002ff8  test    eax, eax
0x180002ffa  js      loc_18000320D
0x180003000  mov     rcx, [rbp+ppMFType]
0x180003004  mov     rax, [rcx]
0x180003007  mov     r8, rsi
0x18000300a  lea     rdx, MF_MT_MAJOR_TYPE
0x180003011  mov     rax, [rax+0C0h]
0x180003018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301d  mov     ebx, eax
0x18000301f  test    eax, eax
0x180003021  js      loc_18000320D
0x180003027  mov     rcx, [rbp+ppMFType]
0x18000302b  mov     rax, [rcx]
0x18000302e  lea     r8, MFAudioFormat_ALAC_Deprecated; "alac"
0x180003035  lea     rdx, MF_MT_SUBTYPE
0x18000303c  mov     rax, [rax+0C0h]
0x180003043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003048  mov     ebx, eax
0x18000304a  test    eax, eax
0x18000304c  js      loc_18000320D
0x180003052  cmp     dword ptr [rdi+8], 1
0x180003056  jbe     short loc_1800030A4
0x180003058  mov     rbx, [rbp+ppMFType]
0x18000305c  mov     rax, [rdi+10h]
0x180003060  mov     rcx, [rax+10h]
0x180003064  test    rcx, rcx
0x180003067  jz      short loc_18000307D
0x180003069  mov     rax, [rcx]
0x18000306c  mov     rax, [rax+10h]
0x180003070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003075  mov     rax, [rdi+10h]
0x180003079  mov     [rax+10h], r14
0x18000307d  mov     rax, [rdi+10h]
0x180003081  mov     [rax+10h], rbx
0x180003085  mov     rax, [rdi+10h]
0x180003089  mov     rcx, [rax+10h]
0x18000308d  mov     rax, [rcx]
0x180003090  mov     rax, [rax+8]
0x180003094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003099  mov     rax, [rdi+10h]
0x18000309d  mov     dword ptr [rax+18h], 1
0x1800030a4  mov     rcx, [rbp+ppMFType]
0x1800030a8  test    rcx, rcx
0x1800030ab  jz      short loc_1800030BE
0x1800030ad  mov     [rbp+ppMFType], r14
0x1800030b1  mov     rax, [rcx]
0x1800030b4  mov     rax, [rax+10h]
0x1800030b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bd  nop
0x1800030be  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800030c2  call    cs:__imp_MFCreateMediaType
0x1800030c8  mov     ebx, eax
0x1800030ca  test    eax, eax
0x1800030cc  js      loc_18000320D
0x1800030d2  mov     rcx, [rbp+ppMFType]
0x1800030d6  mov     rax, [rcx]
0x1800030d9  mov     r8, rsi
0x1800030dc  lea     rdx, MF_MT_MAJOR_TYPE
0x1800030e3  mov     rax, [rax+0C0h]
0x1800030ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ef  mov     ebx, eax
0x1800030f1  test    eax, eax
0x1800030f3  js      loc_18000320D
0x1800030f9  mov     rcx, [rbp+ppMFType]
0x1800030fd  mov     rax, [rcx]
0x180003100  lea     r8, MFAudioFormat_PCM
0x180003107  lea     rdx, MF_MT_SUBTYPE
0x18000310e  mov     rax, [rax+0C0h]
0x180003115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000311a  mov     ebx, eax
0x18000311c  test    eax, eax
0x18000311e  js      loc_18000320D
0x180003124  mov     edx, 1; unsigned int
0x180003129  mov     rcx, rdi; this
0x18000312c  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x180003131  mov     ebx, eax
0x180003133  test    eax, eax
0x180003135  js      loc_18000320D
0x18000313b  cmp     [rdi+18h], r14d
0x18000313f  jbe     short loc_180003189
0x180003141  mov     rsi, [rbp+ppMFType]
0x180003145  mov     rax, [rdi+20h]
0x180003149  mov     rcx, [rax]
0x18000314c  test    rcx, rcx
0x18000314f  jz      short loc_180003164
0x180003151  mov     rax, [rcx]
0x180003154  mov     rax, [rax+10h]
0x180003158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315d  mov     rax, [rdi+20h]
0x180003161  mov     [rax], r14
0x180003164  mov     rax, [rdi+20h]
0x180003168  mov     [rax], rsi
0x18000316b  mov     rax, [rdi+20h]
0x18000316f  mov     rcx, [rax]
0x180003172  mov     rax, [rcx]
0x180003175  mov     rax, [rax+8]
0x180003179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317e  mov     rax, [rdi+20h]
0x180003182  mov     dword ptr [rax+8], 1
0x180003189  mov     ecx, 40h ; '@'; Size
0x18000318e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003193  mov     [rbp+arg_8], rax
0x180003197  test    rax, rax
0x18000319a  jz      short loc_1800031BA
0x18000319c  mov     [rax+20h], r14
0x1800031a0  mov     [rax+28h], r14
0x1800031a4  mov     [rax+30h], r14
0x1800031a8  mov     [rax+38h], r14
0x1800031ac  xorps   xmm0, xmm0
0x1800031af  xor     ecx, ecx
0x1800031b1  movups  xmmword ptr [rax], xmm0
0x1800031b4  mov     [rax+10h], rcx
0x1800031b8  jmp     short loc_1800031BD
0x1800031ba  mov     rax, r14
0x1800031bd  mov     [rdi+0B0h], rax
0x1800031c4  mov     ecx, 18h; Size
0x1800031c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800031ce  mov     rcx, rax
0x1800031d1  test    rax, rax
0x1800031d4  jz      short loc_1800031E4
0x1800031d6  xorps   xmm0, xmm0
0x1800031d9  xor     eax, eax
0x1800031db  movups  xmmword ptr [rcx], xmm0
0x1800031de  mov     [rcx+10h], rax
0x1800031e2  jmp     short loc_1800031E7
0x1800031e4  mov     rcx, r14
0x1800031e7  mov     [rdi+0B8h], rcx
0x1800031ee  cmp     [rdi+0B0h], r14
0x1800031f5  jnz     short loc_1800031FE
0x1800031f7  mov     ebx, 8007000Eh
0x1800031fc  jmp     short loc_18000320D
0x1800031fe  mov     eax, ebx
0x180003200  mov     ebx, 8007000Eh
0x180003205  test    rcx, rcx
0x180003208  cmovz   eax, ebx
0x18000320b  mov     ebx, eax
0x18000320d  mov     rcx, [rbp+ppMFType]
0x180003211  test    rcx, rcx
0x180003214  jz      short loc_180003227
0x180003216  mov     [rbp+ppMFType], r14
0x18000321a  mov     rax, [rcx]
0x18000321d  mov     rax, [rax+10h]
0x180003221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003226  nop
0x180003227  mov     eax, ebx
0x180003229  mov     rbx, [rsp+20h+arg_10]
0x18000322e  mov     rsi, [rsp+20h+arg_18]
0x180003233  add     rsp, 20h
0x180003237  pop     r14
0x180003239  pop     rdi
0x18000323a  pop     rbp
0x18000323b  retn
```
