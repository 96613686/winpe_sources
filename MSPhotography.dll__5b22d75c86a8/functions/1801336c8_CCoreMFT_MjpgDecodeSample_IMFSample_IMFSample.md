# CCoreMFT::MjpgDecodeSample(IMFSample *,IMFSample * *)

- ea: `0x1801336c8`
- end: `0x1801339ac`
- name: `?MjpgDecodeSample@CCoreMFT@@IEAAJPEAUIMFSample@@PEAPEAU2@@Z`
- size: `740`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, struct IMFSample *, struct IMFSample **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010fb0`

## callees

- `0x180005660`
- `0x180009784`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x1801336c8`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180133976`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180133976`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1801337db`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1801337db`
- `MFPlat!MFCreateSample` at `0x180133806`
- `MFPlat!MFCreateSample` at `0x180133806`

## pseudocode

```c
__int64 __fastcall CCoreMFT::MjpgDecodeSample(CCoreMFT *this, struct IMFSample *a2, struct IMFSample **a3)
{
  HRESULT v6; // ebx
  int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  IMFSample *ppIMFSample[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+48h] [rbp-8h]
  int v14; // [rsp+90h] [rbp+40h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+98h] [rbp+48h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp+58h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  v14 = 0;
  v11 = 0;
  ppIMFSample[1] = 0;
  v13 = 0;
  ppIMFSample[0] = 0;
  ppBuffer = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v8 = 191;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v7);
    goto LABEL_33;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v8 = 192;
    goto LABEL_4;
  }
  *a3 = 0;
  if ( !*((_BYTE *)this + 209) )
  {
    v6 = -1072875850;
    goto LABEL_37;
  }
  if ( !*((_BYTE *)this + 210) )
    goto LABEL_24;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
  v6 = MFCreate2DMediaBuffer(*((_DWORD *)this + 20), *((_DWORD *)this + 21), MFVideoFormat_NV12.Data1, 0, &ppBuffer);
  if ( v6 >= 0 )
  {
    v6 = MFCreateSample(ppIMFSample);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_33;
      v9 = 195;
      goto LABEL_17;
    }
    v6 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample[0]->lpVtbl->AddBuffer)(
           ppIMFSample[0],
           ppBuffer);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_33;
      v9 = 196;
      goto LABEL_17;
    }
LABEL_24:
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 27) + 184LL))(
           *((_QWORD *)this + 27),
           0,
           0);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_33;
      v9 = 197;
      goto LABEL_17;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFSample *, _QWORD))(**((_QWORD **)this + 27) + 192LL))(
           *((_QWORD *)this + 27),
           0,
           a2,
           0);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_33;
      v9 = 198;
      goto LABEL_17;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *, int *))(**((_QWORD **)this + 27) + 200LL))(
           *((_QWORD *)this + 27),
           0,
           1,
           &v11,
           &v14);
    if ( v6 == -1072861838 )
    {
      v6 = 0;
    }
    else if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_33;
      v9 = 199;
      goto LABEL_17;
    }
    *a3 = ppIMFSample[0];
    ppIMFSample[0] = 0;
    goto LABEL_33;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 194;
LABEL_17:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  }
LABEL_33:
  if ( ppIMFSample[0] )
  {
    ((void (__fastcall *)(IMFSample *))ppIMFSample[0]->lpVtbl->Release)(ppIMFSample[0]);
    ppIMFSample[0] = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
LABEL_37:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801336c8  push    rbp
0x1801336ca  push    rbx
0x1801336cb  push    rsi
0x1801336cc  push    rdi
0x1801336cd  push    r12
0x1801336cf  push    r14
0x1801336d1  push    r15
0x1801336d3  mov     rbp, rsp
0x1801336d6  sub     rsp, 50h
0x1801336da  mov     r14, rdx
0x1801336dd  mov     rdi, rcx
0x1801336e0  lea     rdx, [rcx+120h]
0x1801336e7  mov     rsi, r8
0x1801336ea  lea     rcx, [rbp+SRWLock]
0x1801336ee  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1801336f3  xor     r15d, r15d
0x1801336f6  lea     r12, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x1801336fd  mov     [rbp+arg_0], r15d
0x180133701  mov     [rbp+var_20], r15
0x180133705  mov     [rbp+var_10], r15
0x180133709  mov     [rbp+var_8], r15
0x18013370d  mov     [rbp+ppIMFSample], r15
0x180133711  mov     [rbp+arg_8], r15
0x180133715  test    r14, r14
0x180133718  jnz     short loc_180133752
0x18013371a  mov     ecx, 80004003h
0x18013371f  mov     ebx, ecx
0x180133721  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133726  cmp     al, 1
0x180133728  jb      loc_18013393C
0x18013372e  mov     edx, 0BFh
0x180133733  mov     dword ptr [rsp+50h+ppBuffer], ecx
0x180133737  mov     rcx, cs:WPP_GLOBAL_Control
0x18013373e  mov     r9, rdi
0x180133741  mov     r8, r12
0x180133744  mov     rcx, [rcx+10h]
0x180133748  call    WPP_SF_qD
0x18013374d  jmp     loc_18013390A
0x180133752  test    rsi, rsi
0x180133755  jnz     short loc_180133772
0x180133757  mov     ecx, 80004003h
0x18013375c  mov     ebx, ecx
0x18013375e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133763  cmp     al, 1
0x180133765  jb      loc_18013393C
0x18013376b  mov     edx, 0C0h
0x180133770  jmp     short loc_180133733
0x180133772  mov     [rsi], r15
0x180133775  cmp     [rdi+0D1h], r15b
0x18013377c  jnz     short loc_180133788
0x18013377e  mov     ebx, 0C00D36B6h
0x180133783  jmp     loc_18013393C
0x180133788  cmp     [rdi+0D2h], r15b
0x18013378f  jz      loc_180133857
0x180133795  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013379a  cmp     al, 20h ; ' '
0x18013379c  jb      short loc_1801337B9
0x18013379e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801337a5  mov     edx, 0C1h
0x1801337aa  mov     r9, rdi
0x1801337ad  mov     r8, r12
0x1801337b0  mov     rcx, [rcx+10h]
0x1801337b4  call    WPP_SF_q
0x1801337b9  lea     rcx, [rbp+arg_8]
0x1801337bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801337c2  mov     r8d, cs:MFVideoFormat_NV12.Data1; dwFourCC
0x1801337c9  lea     rax, [rbp+arg_8]
0x1801337cd  mov     edx, [rdi+54h]; dwHeight
0x1801337d0  xor     r9d, r9d; fBottomUp
0x1801337d3  mov     ecx, [rdi+50h]; dwWidth
0x1801337d6  mov     [rsp+50h+ppBuffer], rax; ppBuffer
0x1801337db  call    cs:__imp_MFCreate2DMediaBuffer
0x1801337e1  mov     ebx, eax
0x1801337e3  test    eax, eax
0x1801337e5  jns     short loc_180133802
0x1801337e7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801337ec  cmp     al, 1
0x1801337ee  jb      loc_18013390A
0x1801337f4  mov     edx, 0C2h
0x1801337f9  mov     dword ptr [rsp+50h+ppBuffer], ebx
0x1801337fd  jmp     loc_180133737
0x180133802  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180133806  call    cs:__imp_MFCreateSample
0x18013380c  mov     ebx, eax
0x18013380e  test    eax, eax
0x180133810  jns     short loc_180133826
0x180133812  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133817  cmp     al, 1
0x180133819  jb      loc_18013390A
0x18013381f  mov     edx, 0C3h
0x180133824  jmp     short loc_1801337F9
0x180133826  mov     rcx, [rbp+ppIMFSample]
0x18013382a  mov     rdx, [rbp+arg_8]
0x18013382e  mov     rax, [rcx]
0x180133831  mov     rax, [rax+150h]
0x180133838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013383d  mov     ebx, eax
0x18013383f  test    eax, eax
0x180133841  jns     short loc_180133857
0x180133843  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133848  cmp     al, 1
0x18013384a  jb      loc_18013390A
0x180133850  mov     edx, 0C4h
0x180133855  jmp     short loc_1801337F9
0x180133857  mov     rcx, [rdi+0D8h]
0x18013385e  xor     r8d, r8d
0x180133861  xor     edx, edx
0x180133863  mov     rax, [rcx]
0x180133866  mov     rax, [rax+0B8h]
0x18013386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133872  mov     ebx, eax
0x180133874  test    eax, eax
0x180133876  jns     short loc_18013388F
0x180133878  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013387d  cmp     al, 1
0x18013387f  jb      loc_18013390A
0x180133885  mov     edx, 0C5h
0x18013388a  jmp     loc_1801337F9
0x18013388f  mov     rcx, [rdi+0D8h]
0x180133896  xor     r9d, r9d
0x180133899  mov     r8, r14
0x18013389c  xor     edx, edx
0x18013389e  mov     rax, [rcx]
0x1801338a1  mov     rax, [rax+0C0h]
0x1801338a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801338ad  mov     ebx, eax
0x1801338af  test    eax, eax
0x1801338b1  jns     short loc_1801338C6
0x1801338b3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801338b8  cmp     al, 1
0x1801338ba  jb      short loc_18013390A
0x1801338bc  mov     edx, 0C6h
0x1801338c1  jmp     loc_1801337F9
0x1801338c6  mov     rcx, [rdi+0D8h]
0x1801338cd  lea     rdx, [rbp+arg_0]
0x1801338d1  mov     [rsp+50h+ppBuffer], rdx
0x1801338d6  lea     r9, [rbp+var_20]
0x1801338da  xor     edx, edx
0x1801338dc  mov     rax, [rcx]
0x1801338df  lea     r8d, [rdx+1]
0x1801338e3  mov     rax, [rax+0C8h]
0x1801338ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801338ef  mov     ebx, eax
0x1801338f1  cmp     eax, 0C00D6D72h
0x1801338f6  jnz     loc_18013398D
0x1801338fc  mov     ebx, r15d
0x1801338ff  mov     rax, [rbp+ppIMFSample]
0x180133903  mov     [rsi], rax
0x180133906  mov     [rbp+ppIMFSample], r15
0x18013390a  mov     rcx, [rbp+ppIMFSample]
0x18013390e  test    rcx, rcx
0x180133911  jz      short loc_180133923
0x180133913  mov     rax, [rcx]
0x180133916  mov     rax, [rax+10h]
0x18013391a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013391f  mov     [rbp+ppIMFSample], r15
0x180133923  mov     rcx, [rbp+var_8]
0x180133927  test    rcx, rcx
0x18013392a  jz      short loc_18013393C
0x18013392c  mov     rax, [rcx]
0x18013392f  mov     rax, [rax+10h]
0x180133933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133938  mov     [rbp+var_8], r15
0x18013393c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133941  cmp     al, 20h ; ' '
0x180133943  jb      short loc_180133964
0x180133945  mov     rcx, cs:WPP_GLOBAL_Control
0x18013394c  mov     edx, 0C8h
0x180133951  mov     r9, rdi
0x180133954  mov     dword ptr [rsp+50h+ppBuffer], ebx
0x180133958  mov     r8, r12
0x18013395b  mov     rcx, [rcx+10h]
0x18013395f  call    WPP_SF_qD
0x180133964  lea     rcx, [rbp+arg_8]
0x180133968  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18013396d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180133971  test    rcx, rcx
0x180133974  jz      short loc_18013397C
0x180133976  call    cs:__imp_ReleaseSRWLockExclusive
0x18013397c  mov     eax, ebx
0x18013397e  add     rsp, 50h
0x180133982  pop     r15
0x180133984  pop     r14
0x180133986  pop     r12
0x180133988  pop     rdi
0x180133989  pop     rsi
0x18013398a  pop     rbx
0x18013398b  pop     rbp
0x18013398c  retn
0x18013398d  test    ebx, ebx
0x18013398f  jns     loc_1801338FF
0x180133995  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013399a  cmp     al, 1
0x18013399c  jb      loc_18013390A
0x1801339a2  mov     edx, 0C7h
0x1801339a7  jmp     loc_1801337F9
```
