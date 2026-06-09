# CCoreMFT::OnSetOutputType(IMFMediaType *)

- ea: `0x180134440`
- end: `0x180134508`
- name: `?OnSetOutputType@CCoreMFT@@AEAAJPEAUIMFMediaType@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, struct IMFMediaType *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801340f0`
- `0x180134ef0`

## callees

- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x180134440`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18013446d`
- `MFPlat!MFCreateMediaType` at `0x18013446d`

## pseudocode

```c
__int64 __fastcall CCoreMFT::OnSetOutputType(CCoreMFT *this, struct IMFMediaType *a2)
{
  IMFMediaType **v2; // rsi
  char *v4; // rcx
  HRESULT v6; // ebx
  __int64 v7; // rdx

  v2 = (IMFMediaType **)((char *)this + 120);
  v4 = (char *)this + 120;
  if ( !a2 )
  {
    v6 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4);
    goto LABEL_10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4);
  v6 = MFCreateMediaType(v2);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_10;
    v7 = 145;
    goto LABEL_9;
  }
  v6 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a2->lpVtbl->CopyAllItems)(a2, *v2);
  if ( v6 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v7 = 146;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  }
LABEL_10:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180134440  push    rbx
0x180134442  push    rsi
0x180134443  push    rdi
0x180134444  push    r14
0x180134446  sub     rsp, 38h
0x18013444a  lea     rsi, [rcx+78h]
0x18013444e  mov     rdi, rcx
0x180134451  mov     rcx, rsi
0x180134454  mov     r14, rdx
0x180134457  test    rdx, rdx
0x18013445a  jnz     short loc_180134465
0x18013445c  xor     ebx, ebx
0x18013445e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180134463  jmp     short loc_1801344D0
0x180134465  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18013446a  mov     rcx, rsi; ppMFType
0x18013446d  call    cs:__imp_MFCreateMediaType
0x180134473  mov     ebx, eax
0x180134475  test    eax, eax
0x180134477  jns     short loc_180134489
0x180134479  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013447e  cmp     al, 1
0x180134480  jb      short loc_1801344D0
0x180134482  mov     edx, 91h
0x180134487  jmp     short loc_1801344B2
0x180134489  mov     rax, [r14]
0x18013448c  mov     rcx, r14
0x18013448f  mov     rdx, [rsi]
0x180134492  mov     rax, [rax+100h]
0x180134499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013449e  mov     ebx, eax
0x1801344a0  test    eax, eax
0x1801344a2  jns     short loc_1801344D0
0x1801344a4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801344a9  cmp     al, 1
0x1801344ab  jb      short loc_1801344D0
0x1801344ad  mov     edx, 92h
0x1801344b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801344b9  lea     r8, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x1801344c0  mov     r9, rdi
0x1801344c3  mov     [rsp+58h+var_38], ebx
0x1801344c7  mov     rcx, [rcx+10h]
0x1801344cb  call    WPP_SF_qD
0x1801344d0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801344d5  cmp     al, 20h ; ' '
0x1801344d7  jb      short loc_1801344FC
0x1801344d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801344e0  lea     r8, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x1801344e7  mov     edx, 93h
0x1801344ec  mov     [rsp+58h+var_38], ebx
0x1801344f0  mov     r9, rdi
0x1801344f3  mov     rcx, [rcx+10h]
0x1801344f7  call    WPP_SF_qD
0x1801344fc  mov     eax, ebx
0x1801344fe  add     rsp, 38h
0x180134502  pop     r14
0x180134504  pop     rdi
0x180134505  pop     rsi
0x180134506  pop     rbx
0x180134507  retn
```
