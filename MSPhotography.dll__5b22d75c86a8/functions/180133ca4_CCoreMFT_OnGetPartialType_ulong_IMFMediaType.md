# CCoreMFT::OnGetPartialType(ulong,IMFMediaType * *)

- ea: `0x180133ca4`
- end: `0x180133e2a`
- name: `?OnGetPartialType@CCoreMFT@@AEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180132640`
- `0x180132ac0`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x180133ca4`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180133d34`
- `MFPlat!MFCreateMediaType` at `0x180133d34`

## pseudocode

```c
__int64 __fastcall CCoreMFT::OnGetPartialType(CCoreMFT *this, __int64 a2, struct IMFMediaType **a3)
{
  __int64 v3; // rax
  HRESULT v6; // ebx
  __int64 v7; // rdx
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+38h] [rbp-30h] BYREF

  v3 = *(_QWORD *)this;
  ppMFType = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(CCoreMFT *, __int64, __int128 *))(v3 + 64))(this, a2, &v10);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_15;
    v7 = 125;
    goto LABEL_4;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  v6 = MFCreateMediaType(&ppMFType);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
           ppMFType,
           &MF_MT_MAJOR_TYPE,
           &MFMediaType_Video);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &v10);
      if ( v6 >= 0 )
      {
        *a3 = ppMFType;
        ppMFType = 0;
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 128;
        goto LABEL_4;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 127;
      goto LABEL_4;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v7 = 126;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  }
LABEL_15:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180133ca4  mov     [rsp+arg_18], rbx
0x180133ca9  push    rbp
0x180133caa  push    rsi
0x180133cab  push    rdi
0x180133cac  sub     rsp, 50h
0x180133cb0  mov     rax, cs:__security_cookie
0x180133cb7  xor     rax, rsp
0x180133cba  mov     [rsp+68h+var_20], rax
0x180133cbf  mov     rax, [rcx]
0x180133cc2  mov     rsi, r8
0x180133cc5  xorps   xmm0, xmm0
0x180133cc8  mov     [rsp+68h+ppMFType], 0
0x180133cd1  lea     r8, [rsp+68h+var_30]
0x180133cd6  mov     rdi, rcx
0x180133cd9  movups  [rsp+68h+var_30], xmm0
0x180133cde  mov     rax, [rax+40h]
0x180133ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133ce7  lea     rbp, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x180133cee  mov     ebx, eax
0x180133cf0  test    eax, eax
0x180133cf2  jns     short loc_180133D25
0x180133cf4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133cf9  cmp     al, 1
0x180133cfb  jb      loc_180133DD9
0x180133d01  mov     edx, 7Dh ; '}'
0x180133d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180133d0d  mov     r9, rdi
0x180133d10  mov     r8, rbp
0x180133d13  mov     [rsp+68h+var_48], ebx
0x180133d17  mov     rcx, [rcx+10h]
0x180133d1b  call    WPP_SF_qD
0x180133d20  jmp     loc_180133DD9
0x180133d25  lea     rcx, [rsp+68h+ppMFType]
0x180133d2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180133d2f  lea     rcx, [rsp+68h+ppMFType]; ppMFType
0x180133d34  call    cs:__imp_MFCreateMediaType
0x180133d3a  mov     ebx, eax
0x180133d3c  test    eax, eax
0x180133d3e  jns     short loc_180133D54
0x180133d40  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133d45  cmp     al, 1
0x180133d47  jb      loc_180133DD9
0x180133d4d  mov     edx, 7Eh ; '~'
0x180133d52  jmp     short loc_180133D06
0x180133d54  mov     rcx, [rsp+68h+ppMFType]
0x180133d59  lea     r8, MFMediaType_Video
0x180133d60  lea     rdx, MF_MT_MAJOR_TYPE
0x180133d67  mov     rax, [rcx]
0x180133d6a  mov     rax, [rax+0C0h]
0x180133d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d76  mov     ebx, eax
0x180133d78  test    eax, eax
0x180133d7a  jns     short loc_180133D8F
0x180133d7c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133d81  cmp     al, 1
0x180133d83  jb      short loc_180133DD9
0x180133d85  mov     edx, 7Fh
0x180133d8a  jmp     loc_180133D06
0x180133d8f  mov     rcx, [rsp+68h+ppMFType]
0x180133d94  lea     r8, [rsp+68h+var_30]
0x180133d99  lea     rdx, MF_MT_SUBTYPE
0x180133da0  mov     rax, [rcx]
0x180133da3  mov     rax, [rax+0C0h]
0x180133daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133daf  mov     ebx, eax
0x180133db1  test    eax, eax
0x180133db3  jns     short loc_180133DC8
0x180133db5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133dba  cmp     al, 1
0x180133dbc  jb      short loc_180133DD9
0x180133dbe  mov     edx, 80h
0x180133dc3  jmp     loc_180133D06
0x180133dc8  mov     rax, [rsp+68h+ppMFType]
0x180133dcd  mov     [rsi], rax
0x180133dd0  mov     [rsp+68h+ppMFType], 0
0x180133dd9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133dde  cmp     al, 20h ; ' '
0x180133de0  jb      short loc_180133E01
0x180133de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180133de9  mov     edx, 81h
0x180133dee  mov     r9, rdi
0x180133df1  mov     [rsp+68h+var_48], ebx
0x180133df5  mov     r8, rbp
0x180133df8  mov     rcx, [rcx+10h]
0x180133dfc  call    WPP_SF_qD
0x180133e01  lea     rcx, [rsp+68h+ppMFType]
0x180133e06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180133e0b  mov     eax, ebx
0x180133e0d  mov     rcx, [rsp+68h+var_20]
0x180133e12  xor     rcx, rsp; StackCookie
0x180133e15  call    __security_check_cookie
0x180133e1a  mov     rbx, [rsp+68h+arg_18]
0x180133e22  add     rsp, 50h
0x180133e26  pop     rdi
0x180133e27  pop     rsi
0x180133e28  pop     rbp
0x180133e29  retn
```
