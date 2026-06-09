# RdVhd::Util::CVhdHelper::OpenVhd(ushort const *,RdVhd::Util::CVhdHelper::VhdAccessMask::Mask,void * *,CPathString *)

- ea: `0x180018cac`
- end: `0x180018f86`
- name: `?OpenVhd@CVhdHelper@Util@RdVhd@@IEBAJPEBGW4Mask@VhdAccessMask@123@PEAPEAXPEAVCPathString@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180048b68`
- `0x18004908c`

## callees

- `0x180004db0`
- `0x180018cac`
- `0x180019b38`
- `0x180043df0`
- `0x1800488e4`
- `0x180048b28`
- `0x18004b0a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018e6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018e81`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018e6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018e81`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180018e5a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180018e5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f5c`
- `VirtDisk!OpenVirtualDisk` at `0x180018ec6`
- `VirtDisk!OpenVirtualDisk` at `0x180018ec6`

## string_xrefs

- `0x180018d33`: `szVhdFilePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::OpenVhd(
        RdVhd::Util::CVhdHelper *a1,
        const unsigned __int16 *a2,
        int a3,
        HANDLE *a4,
        __int64 a5)
{
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  signed int v11; // ebx
  __int64 v12; // rsi
  RdVhd::Uvhd::CUvhdDiskManager *v13; // rcx
  __int64 v14; // rdx
  int v15; // edi
  int v16; // edi
  VIRTUAL_DISK_ACCESS_MASK v17; // ebx
  BOOL v18; // edi
  wchar_t *v19; // r15
  const WCHAR *v20; // rax
  struct _VIRTUAL_STORAGE_TYPE *v21; // rcx
  signed int v22; // eax
  void **v24; // [rsp+30h] [rbp-30h] BYREF
  int v25; // [rsp+38h] [rbp-28h]
  __int64 v26; // [rsp+3Ch] [rbp-24h]
  int v27; // [rsp+44h] [rbp-1Ch]
  __int64 v28; // [rsp+48h] [rbp-18h]
  int v29; // [rsp+50h] [rbp-10h]
  HANDLE hObject; // [rsp+90h] [rbp+30h] BYREF

  v26 = 128;
  hObject = (HANDLE)-1LL;
  v24 = &CPathString::`vftable';
  v28 = 0;
  v27 = 0;
  v29 = 0x8000000;
  v25 = 0;
  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 123;
    v10 = L"szVhdFilePath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v10);
LABEL_7:
    v11 = -2147024809;
    goto LABEL_49;
  }
  if ( !a4 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 124;
    v10 = L"phVhd";
    goto LABEL_6;
  }
  v12 = a5;
  if ( a5 )
  {
    *(_DWORD *)(a5 + 16) = 0;
    *(_DWORD *)(v12 + 8) = 0;
  }
  v11 = RdVhd::Util::CVhdHelper::TranslateLoopbackPath(a1, a2, (struct CPathString *)&v24);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 125;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, (unsigned int)v11);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v15 = a3 - 1;
  if ( !v15 )
  {
    v17 = VIRTUAL_DISK_ACCESS_ALL;
LABEL_31:
    v18 = 1;
    *a4 = (HANDLE)-1LL;
    v19 = wcsrchr(a2, 0x2Eu);
    if ( (unsigned int)_o__wcsicmp(v19, L".vhdx") )
      v18 = _o__wcsicmp(v19, L".avhdx") == 0;
    v20 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v24);
    v21 = (struct _VIRTUAL_STORAGE_TYPE *)qword_180084820;
    if ( !v18 )
      v21 = &VirtualStorageType;
    v22 = OpenVirtualDisk(v21, v20, v17, OPEN_VIRTUAL_DISK_FLAG_NONE, 0, &hObject);
    v11 = v22;
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    if ( v11 >= 0 )
    {
      if ( v12 && (v11 = CBaseStringT<unsigned short>::Set<unsigned short>(v12, &v24), v11 < 0) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 128;
          goto LABEL_20;
        }
      }
      else
      {
        *a4 = hObject;
        hObject = (HANDLE)-1LL;
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 127;
        goto LABEL_20;
      }
    }
    goto LABEL_49;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v17 = VIRTUAL_DISK_ACCESS_DETACH;
    goto LABEL_31;
  }
  if ( v16 == 1 )
  {
    v17 = VIRTUAL_DISK_ACCESS_GET_INFO;
    goto LABEL_31;
  }
  v11 = -2147024809;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 126;
    goto LABEL_20;
  }
LABEL_49:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  CPathString::~CPathString((CPathString *)&v24);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018cac  mov     [rsp-28h+arg_8], rbx
0x180018cb1  mov     [rsp-28h+arg_10], rsi
0x180018cb6  mov     [rsp-28h+hObject], rcx
0x180018cbb  push    rbp
0x180018cbc  push    rdi
0x180018cbd  push    r13
0x180018cbf  push    r14
0x180018cc1  push    r15
0x180018cc3  mov     rbp, rsp
0x180018cc6  sub     rsp, 60h
0x180018cca  or      r13, 0FFFFFFFFFFFFFFFFh
0x180018cce  mov     [rbp+var_24], 80h
0x180018cd6  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180018cdd  mov     [rbp+hObject], r13
0x180018ce1  mov     [rbp+var_30], rax
0x180018ce5  mov     r14, r9
0x180018ce8  mov     edi, r8d
0x180018ceb  mov     [rbp+var_18], 0
0x180018cf3  mov     r15, rdx
0x180018cf6  mov     [rbp+var_1C], 0
0x180018cfd  mov     [rbp+var_10], 8000000h
0x180018d04  mov     [rbp+var_28], 0
0x180018d0b  test    rdx, rdx
0x180018d0e  jnz     short loc_180018D54
0x180018d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d17  lea     rax, WPP_GLOBAL_Control
0x180018d1e  cmp     rcx, rax
0x180018d21  jz      short loc_180018D4A
0x180018d23  test    byte ptr [rcx+1Ch], 1
0x180018d27  jz      short loc_180018D4A
0x180018d29  cmp     byte ptr [rcx+19h], 2
0x180018d2d  jb      short loc_180018D4A
0x180018d2f  lea     edx, [r15+7Bh]
0x180018d33  lea     r9, aSzvhdfilepath; "szVhdFilePath"
0x180018d3a  mov     rcx, [rcx+10h]
0x180018d3e  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180018d45  call    WPP_SF_S
0x180018d4a  mov     ebx, 80070057h
0x180018d4f  jmp     loc_180018F53
0x180018d54  test    r14, r14
0x180018d57  jnz     short loc_180018D85
0x180018d59  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180018d60  lea     rax, WPP_GLOBAL_Control
0x180018d67  cmp     rcx, rax
0x180018d6a  jz      short loc_180018D4A
0x180018d6c  test    byte ptr [rcx+1Ch], 1
0x180018d70  jz      short loc_180018D4A
0x180018d72  cmp     byte ptr [rcx+19h], 2
0x180018d76  jb      short loc_180018D4A
0x180018d78  lea     edx, [r14+7Ch]; unsigned __int16 *
0x180018d7c  lea     r9, aPhvhd; "phVhd"
0x180018d83  jmp     short loc_180018D3A
0x180018d85  mov     rsi, [rbp+arg_20]
0x180018d89  test    rsi, rsi
0x180018d8c  jz      short loc_180018D9C
0x180018d8e  mov     dword ptr [rsi+10h], 0
0x180018d95  mov     dword ptr [rsi+8], 0
0x180018d9c  lea     r8, [rbp+var_30]; struct CPathString *
0x180018da0  call    ?TranslateLoopbackPath@CVhdHelper@Util@RdVhd@@QEBAJPEBGPEAVCPathString@@@Z; RdVhd::Util::CVhdHelper::TranslateLoopbackPath(ushort const *,CPathString *)
0x180018da5  mov     ebx, eax
0x180018da7  test    eax, eax
0x180018da9  jns     short loc_180018DF3
0x180018dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180018db2  lea     rax, WPP_GLOBAL_Control
0x180018db9  cmp     rcx, rax
0x180018dbc  jz      loc_180018F53
0x180018dc2  test    byte ptr [rcx+1Ch], 1
0x180018dc6  jz      loc_180018F53
0x180018dcc  cmp     byte ptr [rcx+19h], 2
0x180018dd0  jb      loc_180018F53
0x180018dd6  mov     edx, 7Dh ; '}'
0x180018ddb  mov     rcx, [rcx+10h]
0x180018ddf  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180018de6  mov     r9d, ebx
0x180018de9  call    WPP_SF_d
0x180018dee  jmp     loc_180018F53
0x180018df3  sub     edi, 1
0x180018df6  jz      short loc_180018E47
0x180018df8  sub     edi, 1
0x180018dfb  jz      short loc_180018E40
0x180018dfd  cmp     edi, 1
0x180018e00  jz      short loc_180018E39
0x180018e02  mov     ebx, 80070057h
0x180018e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e0e  lea     rax, WPP_GLOBAL_Control
0x180018e15  cmp     rcx, rax
0x180018e18  jz      loc_180018F53
0x180018e1e  test    byte ptr [rcx+1Ch], 1
0x180018e22  jz      loc_180018F53
0x180018e28  cmp     byte ptr [rcx+19h], 2
0x180018e2c  jb      loc_180018F53
0x180018e32  mov     edx, 7Eh ; '~'
0x180018e37  jmp     short loc_180018DDB
0x180018e39  mov     ebx, 80000h
0x180018e3e  jmp     short loc_180018E4C
0x180018e40  mov     ebx, 40000h
0x180018e45  jmp     short loc_180018E4C
0x180018e47  mov     ebx, 3F0000h
0x180018e4c  mov     edi, 1
0x180018e51  mov     [r14], r13
0x180018e54  mov     rcx, r15; Str
0x180018e57  lea     edx, [rdi+2Dh]; Ch
0x180018e5a  call    cs:__imp_wcsrchr
0x180018e60  mov     rcx, rax
0x180018e63  lea     rdx, aVhdx; ".vhdx"
0x180018e6a  mov     r15, rax
0x180018e6d  call    cs:__imp__o__wcsicmp
0x180018e73  test    eax, eax
0x180018e75  jz      short loc_180018E8E
0x180018e77  lea     rdx, aAvhdx; ".avhdx"
0x180018e7e  mov     rcx, r15
0x180018e81  call    cs:__imp__o__wcsicmp
0x180018e87  xor     ecx, ecx
0x180018e89  test    eax, eax
0x180018e8b  cmovnz  edi, ecx
0x180018e8e  lea     rcx, [rbp+var_30]
0x180018e92  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018e97  lea     rdx, VirtualStorageType
0x180018e9e  test    edi, edi
0x180018ea0  lea     rcx, qword_180084820
0x180018ea7  mov     r8d, ebx; VirtualDiskAccessMask
0x180018eaa  cmovz   rcx, rdx; VirtualStorageType
0x180018eae  lea     rdx, [rbp+hObject]
0x180018eb2  mov     [rsp+60h+Handle], rdx; Handle
0x180018eb7  xor     r9d, r9d; Flags
0x180018eba  mov     rdx, rax; Path
0x180018ebd  mov     [rsp+60h+Parameters], 0; Parameters
0x180018ec6  call    cs:__imp_OpenVirtualDisk
0x180018ecc  mov     ebx, eax
0x180018ece  test    eax, eax
0x180018ed0  jle     short loc_180018EDB
0x180018ed2  movzx   ebx, ax
0x180018ed5  or      ebx, 80070000h
0x180018edb  test    ebx, ebx
0x180018edd  jns     short loc_180018F08
0x180018edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ee6  lea     rax, WPP_GLOBAL_Control
0x180018eed  cmp     rcx, rax
0x180018ef0  jz      short loc_180018F53
0x180018ef2  test    byte ptr [rcx+1Ch], 1
0x180018ef6  jz      short loc_180018F53
0x180018ef8  cmp     byte ptr [rcx+19h], 2
0x180018efc  jb      short loc_180018F53
0x180018efe  mov     edx, 7Fh
0x180018f03  jmp     loc_180018DDB
0x180018f08  test    rsi, rsi
0x180018f0b  jz      short loc_180018F48
0x180018f0d  lea     rdx, [rbp+var_30]
0x180018f11  mov     rcx, rsi
0x180018f14  call    ??$Set@G@?$CBaseStringT@G@@QEAAJAEBV0@@Z; CBaseStringT<ushort>::Set<ushort>(CBaseStringT<ushort> const &)
0x180018f19  mov     ebx, eax
0x180018f1b  test    eax, eax
0x180018f1d  jns     short loc_180018F48
0x180018f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f26  lea     rax, WPP_GLOBAL_Control
0x180018f2d  cmp     rcx, rax
0x180018f30  jz      short loc_180018F53
0x180018f32  test    byte ptr [rcx+1Ch], 1
0x180018f36  jz      short loc_180018F53
0x180018f38  cmp     byte ptr [rcx+19h], 2
0x180018f3c  jb      short loc_180018F53
0x180018f3e  mov     edx, 80h
0x180018f43  jmp     loc_180018DDB
0x180018f48  mov     rax, [rbp+hObject]
0x180018f4c  mov     [r14], rax
0x180018f4f  mov     [rbp+hObject], r13
0x180018f53  mov     rcx, [rbp+hObject]; hObject
0x180018f57  cmp     rcx, r13
0x180018f5a  jz      short loc_180018F62
0x180018f5c  call    cs:__imp_CloseHandle
0x180018f62  lea     rcx, [rbp+var_30]; this
0x180018f66  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018f6b  lea     r11, [rsp+60h+var_s0]
0x180018f70  mov     eax, ebx
0x180018f72  mov     rbx, [r11+38h]
0x180018f76  mov     rsi, [r11+40h]
0x180018f7a  mov     rsp, r11
0x180018f7d  pop     r15
0x180018f7f  pop     r14
0x180018f81  pop     r13
0x180018f83  pop     rdi
0x180018f84  pop     rbp
0x180018f85  retn
```
