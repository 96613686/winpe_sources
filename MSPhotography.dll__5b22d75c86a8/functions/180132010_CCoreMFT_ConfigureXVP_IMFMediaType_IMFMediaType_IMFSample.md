# CCoreMFT::ConfigureXVP(IMFMediaType *,IMFMediaType *,IMFSample *)

- ea: `0x180132010`
- end: `0x18013233d`
- name: `?ConfigureXVP@CCoreMFT@@IEAAJPEAUIMFMediaType@@0PEAUIMFSample@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, struct IMFMediaType *, struct IMFMediaType *, struct IMFSample *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fb0`
- `0x1800b00f0`

## callees

- `0x180009784`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x1800a75a0`
- `0x1801316bc`
- `0x180132010`
- `0x180133564`
- `0x18013541c`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180132324`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180132324`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18013216c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18013216c`

## string_xrefs

- `0x18013215e`: `Attempting to configure XVP to process DX buffers without a DXManager set`

## pseudocode

```c
__int64 __fastcall CCoreMFT::ConfigureXVP(
        CCoreMFT *this,
        struct IMFMediaType *a2,
        struct IMFMediaType *a3,
        struct IMFSample *a4)
{
  int v8; // edx
  int v9; // ebx
  __int64 v10; // rdx
  bool v11; // bp
  bool v13; // [rsp+60h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+10h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  *((_BYTE *)this + 232) = 0;
  if ( !a2 )
  {
    v9 = Windows::Media::Report((Windows::Media *)0x80004003LL, v8);
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_41;
    v10 = 201;
    goto LABEL_4;
  }
  if ( a3 )
  {
    if ( a4 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 30) + 184LL))(
             *((_QWORD *)this + 30),
             268435457,
             0);
      if ( v9 >= 0 )
      {
        v13 = 0;
        v9 = IsSampleDX(a4, &v13);
        if ( v9 >= 0 )
        {
          v11 = v13;
          if ( v13 )
          {
            if ( !*((_QWORD *)this + 20) )
            {
              v9 = -2147467261;
              RoOriginateErrorW(
                2147500035LL,
                73,
                L"Attempting to configure XVP to process DX buffers without a DXManager set");
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 206;
                goto LABEL_4;
              }
              goto LABEL_41;
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this);
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 30) + 184LL))(
                   *((_QWORD *)this + 30),
                   2,
                   *((_QWORD *)this + 20));
            if ( v9 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 208;
                goto LABEL_4;
              }
              goto LABEL_41;
            }
          }
          else
          {
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this);
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 30) + 184LL))(
                   *((_QWORD *)this + 30),
                   2);
            if ( v9 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 210;
                goto LABEL_4;
              }
              goto LABEL_41;
            }
          }
          v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType *, _QWORD))(**((_QWORD **)this + 30)
                                                                                        + 120LL))(
                 *((_QWORD *)this + 30),
                 0,
                 a2,
                 0);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType *, _QWORD))(**((_QWORD **)this + 30)
                                                                                          + 128LL))(
                   *((_QWORD *)this + 30),
                   0,
                   a3,
                   0);
            if ( v9 >= 0 )
            {
              v9 = CCoreMFT::SetXVPSampleAllocator(this, a3, v11);
              if ( v9 >= 0 )
              {
                Microsoft::WRL::ComPtr<IMFMediaType>::operator=((char *)this + 296, a3);
                *((_BYTE *)this + 232) = 1;
              }
              else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 213;
                goto LABEL_4;
              }
            }
            else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 212;
              goto LABEL_4;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 211;
            goto LABEL_4;
          }
          goto LABEL_41;
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 205;
          goto LABEL_4;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 204;
        goto LABEL_4;
      }
    }
    else
    {
      v9 = Windows::Media::Report((Windows::Media *)0x80004003LL, v8);
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 203;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v9 = Windows::Media::Report((Windows::Media *)0x80004003LL, v8);
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 202;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v9);
    }
  }
LABEL_41:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v9);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180132010  mov     [rsp+arg_10], rbx
0x180132015  push    rbp
0x180132016  push    rsi
0x180132017  push    rdi
0x180132018  push    r14
0x18013201a  push    r15
0x18013201c  sub     rsp, 30h
0x180132020  mov     r14, rdx
0x180132023  mov     rdi, rcx
0x180132026  lea     rdx, [rcx+120h]
0x18013202d  mov     rbp, r9
0x180132030  lea     rcx, [rsp+58h+SRWLock]
0x180132035  mov     rsi, r8
0x180132038  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18013203d  mov     byte ptr [rdi+0E8h], 0
0x180132044  lea     r15, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x18013204b  test    r14, r14
0x18013204e  jnz     short loc_18013208D
0x180132050  mov     ecx, 80004003h; this
0x180132055  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x18013205a  mov     ebx, eax
0x18013205c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180132061  cmp     al, 1
0x180132063  jb      loc_1801322F2
0x180132069  mov     edx, 0C9h
0x18013206e  mov     rcx, cs:WPP_GLOBAL_Control
0x180132075  mov     r9, rdi
0x180132078  mov     r8, r15
0x18013207b  mov     [rsp+58h+var_38], ebx
0x18013207f  mov     rcx, [rcx+10h]
0x180132083  call    WPP_SF_qD
0x180132088  jmp     loc_1801322F2
0x18013208d  test    rsi, rsi
0x180132090  jnz     short loc_1801320B2
0x180132092  mov     ecx, 80004003h; this
0x180132097  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x18013209c  mov     ebx, eax
0x18013209e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801320a3  cmp     al, 1
0x1801320a5  jb      loc_1801322F2
0x1801320ab  mov     edx, 0CAh
0x1801320b0  jmp     short loc_18013206E
0x1801320b2  test    rbp, rbp
0x1801320b5  jnz     short loc_1801320D7
0x1801320b7  mov     ecx, 80004003h; this
0x1801320bc  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1801320c1  mov     ebx, eax
0x1801320c3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801320c8  cmp     al, 1
0x1801320ca  jb      loc_1801322F2
0x1801320d0  mov     edx, 0CBh
0x1801320d5  jmp     short loc_18013206E
0x1801320d7  mov     rcx, [rdi+0F0h]
0x1801320de  xor     r8d, r8d
0x1801320e1  mov     edx, 10000001h
0x1801320e6  mov     rax, [rcx]
0x1801320e9  mov     rax, [rax+0B8h]
0x1801320f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801320f5  mov     ebx, eax
0x1801320f7  test    eax, eax
0x1801320f9  jns     short loc_180132112
0x1801320fb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180132100  cmp     al, 1
0x180132102  jb      loc_1801322F2
0x180132108  mov     edx, 0CCh
0x18013210d  jmp     loc_18013206E
0x180132112  lea     rdx, [rsp+58h+arg_0]; bool *
0x180132117  mov     [rsp+58h+arg_0], 0
0x18013211c  mov     rcx, rbp; struct IMFSample *
0x18013211f  call    ?IsSampleDX@@YAJPEAUIMFSample@@PEA_N@Z; IsSampleDX(IMFSample *,bool *)
0x180132124  mov     ebx, eax
0x180132126  test    eax, eax
0x180132128  jns     short loc_180132141
0x18013212a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013212f  cmp     al, 1
0x180132131  jb      loc_1801322F2
0x180132137  mov     edx, 0CDh
0x18013213c  jmp     loc_18013206E
0x180132141  mov     bpl, [rsp+58h+arg_0]
0x180132146  test    bpl, bpl
0x180132149  jz      loc_1801321EC
0x18013214f  cmp     qword ptr [rdi+0A0h], 0
0x180132157  jnz     short loc_180132189
0x180132159  mov     ebx, 80004003h
0x18013215e  lea     r8, aAttemptingToCo; "Attempting to configure XVP to process "...
0x180132165  mov     ecx, ebx
0x180132167  mov     edx, 49h ; 'I'
0x18013216c  call    cs:__imp_RoOriginateErrorW
0x180132172  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180132177  cmp     al, 1
0x180132179  jb      loc_1801322F2
0x18013217f  mov     edx, 0CEh
0x180132184  jmp     loc_18013206E
0x180132189  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013218e  cmp     al, 20h ; ' '
0x180132190  jb      short loc_1801321AD
0x180132192  mov     rcx, cs:WPP_GLOBAL_Control
0x180132199  mov     edx, 0CFh
0x18013219e  mov     r9, rdi
0x1801321a1  mov     r8, r15
0x1801321a4  mov     rcx, [rcx+10h]
0x1801321a8  call    WPP_SF_q
0x1801321ad  mov     rcx, [rdi+0F0h]
0x1801321b4  mov     edx, 2
0x1801321b9  mov     r8, [rdi+0A0h]
0x1801321c0  mov     rax, [rcx]
0x1801321c3  mov     rax, [rax+0B8h]
0x1801321ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801321cf  mov     ebx, eax
0x1801321d1  test    eax, eax
0x1801321d3  jns     short loc_18013224A
0x1801321d5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801321da  cmp     al, 1
0x1801321dc  jb      loc_1801322F2
0x1801321e2  mov     edx, 0D0h
0x1801321e7  jmp     loc_18013206E
0x1801321ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801321f1  cmp     al, 20h ; ' '
0x1801321f3  jb      short loc_180132210
0x1801321f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801321fc  mov     edx, 0D1h
0x180132201  mov     r9, rdi
0x180132204  mov     r8, r15
0x180132207  mov     rcx, [rcx+10h]
0x18013220b  call    WPP_SF_q
0x180132210  mov     rcx, [rdi+0F0h]
0x180132217  xor     r8d, r8d
0x18013221a  mov     rax, [rcx]
0x18013221d  lea     edx, [r8+2]
0x180132221  mov     rax, [rax+0B8h]
0x180132228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013222d  mov     ebx, eax
0x18013222f  test    eax, eax
0x180132231  jns     short loc_18013224A
0x180132233  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180132238  cmp     al, 1
0x18013223a  jb      loc_1801322F2
0x180132240  mov     edx, 0D2h
0x180132245  jmp     loc_18013206E
0x18013224a  mov     rcx, [rdi+0F0h]
0x180132251  xor     r9d, r9d
0x180132254  mov     r8, r14
0x180132257  xor     edx, edx
0x180132259  mov     rax, [rcx]
0x18013225c  mov     rax, [rax+78h]
0x180132260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132265  mov     ebx, eax
0x180132267  test    eax, eax
0x180132269  jns     short loc_18013227E
0x18013226b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180132270  cmp     al, 1
0x180132272  jb      short loc_1801322F2
0x180132274  mov     edx, 0D3h
0x180132279  jmp     loc_18013206E
0x18013227e  mov     rcx, [rdi+0F0h]
0x180132285  xor     r9d, r9d
0x180132288  mov     r8, rsi
0x18013228b  xor     edx, edx
0x18013228d  mov     rax, [rcx]
0x180132290  mov     rax, [rax+80h]
0x180132297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013229c  mov     ebx, eax
0x18013229e  test    eax, eax
0x1801322a0  jns     short loc_1801322B5
0x1801322a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801322a7  cmp     al, 1
0x1801322a9  jb      short loc_1801322F2
0x1801322ab  mov     edx, 0D4h
0x1801322b0  jmp     loc_18013206E
0x1801322b5  mov     r8b, bpl; bool
0x1801322b8  mov     rdx, rsi; struct IMFMediaType *
0x1801322bb  mov     rcx, rdi; this
0x1801322be  call    ?SetXVPSampleAllocator@CCoreMFT@@AEAAJPEAUIMFMediaType@@_N@Z; CCoreMFT::SetXVPSampleAllocator(IMFMediaType *,bool)
0x1801322c3  mov     ebx, eax
0x1801322c5  test    eax, eax
0x1801322c7  jns     short loc_1801322DC
0x1801322c9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801322ce  cmp     al, 1
0x1801322d0  jb      short loc_1801322F2
0x1801322d2  mov     edx, 0D5h
0x1801322d7  jmp     loc_18013206E
0x1801322dc  lea     rcx, [rdi+128h]
0x1801322e3  mov     rdx, rsi
0x1801322e6  call    ??4?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFMediaType@@@Z; Microsoft::WRL::ComPtr<IMFMediaType>::operator=(IMFMediaType *)
0x1801322eb  mov     byte ptr [rdi+0E8h], 1
0x1801322f2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801322f7  cmp     al, 20h ; ' '
0x1801322f9  jb      short loc_18013231A
0x1801322fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180132302  mov     edx, 0D6h
0x180132307  mov     r9, rdi
0x18013230a  mov     [rsp+58h+var_38], ebx
0x18013230e  mov     r8, r15
0x180132311  mov     rcx, [rcx+10h]
0x180132315  call    WPP_SF_qD
0x18013231a  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18013231f  test    rcx, rcx
0x180132322  jz      short loc_18013232A
0x180132324  call    cs:__imp_ReleaseSRWLockExclusive
0x18013232a  mov     eax, ebx
0x18013232c  mov     rbx, [rsp+58h+arg_10]
0x180132331  add     rsp, 30h
0x180132335  pop     r15
0x180132337  pop     r14
0x180132339  pop     rdi
0x18013233a  pop     rsi
0x18013233b  pop     rbp
0x18013233c  retn
```
