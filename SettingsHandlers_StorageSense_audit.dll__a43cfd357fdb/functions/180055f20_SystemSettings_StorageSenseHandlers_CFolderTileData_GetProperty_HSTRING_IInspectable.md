# SystemSettings::StorageSenseHandlers::CFolderTileData::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180055f20`
- end: `0x1800562d8`
- name: `?GetProperty@CFolderTileData@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `952`
- prototype: `int(SystemSettings::StorageSenseHandlers::CFolderTileData *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x180001998`
- `0x180019eb4`
- `0x180019ff0`
- `0x18001f688`
- `0x18001fe08`
- `0x18002adf4`
- `0x18002bad4`
- `0x18003d408`
- `0x18003dbc4`
- `0x180043f48`
- `0x180055f20`
- `0x18005b5fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055ffa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055ffa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180055faa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180055faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180055f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180055f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005628a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005628a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18005602a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18005602a`

## string_xrefs

- `0x180056056`: `SystemSettings_StorageSense_Root_Path_Friendly_Name`
- `0x1800561b7`: `%SystemRoot%\system32\imageres.dll,-113`
- `0x18005619f`: `%SystemRoot%\system32\imageres.dll,-112`
- `0x1800561ab`: `%SystemRoot%\system32\imageres.dll,-189`
- `0x1800561c3`: `%SystemRoot%\system32\imageres.dll,-108`
- `0x1800561cf`: `%SystemRoot%\system32\imageres.dll,-3`
- `0x180056193`: `%SystemRoot%\system32\imageres.dll,-181`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CFolderTileData::GetProperty(
        SystemSettings::StorageSenseHandlers::CFolderTileData *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  int v6; // edi
  const unsigned __int16 *v7; // r8
  __int64 v8; // r14
  __int64 v9; // r15
  size_t v10; // r15
  unsigned __int16 *v11; // r14
  PCWSTR v12; // rax
  const unsigned __int16 *v13; // r8
  const WCHAR *StringRawBuffer; // rax
  BOOL IsRootW; // eax
  HSTRING v16; // rcx
  unsigned __int16 **v17; // rax
  unsigned __int16 *v18; // rcx
  int String; // eax
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  double v23; // xmm0_8
  __int64 v24; // rax
  double v25; // xmm1_8
  double v26; // xmm0_8
  double v27; // xmm1_8
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // r8
  const unsigned __int16 *v30; // r8
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  const unsigned __int16 *v36; // r8
  int v37; // ecx
  unsigned int v38; // eax
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  const struct _tlgProvider_t *v43; // rax
  int v44; // ebx
  int v45; // r8d
  int v46; // r9d
  unsigned __int16 *v48; // [rsp+80h] [rbp+18h] BYREF
  PCWSTR v49; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = -2147024809;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E270, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E308, v7) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
      IsRootW = PathIsRootW(StringRawBuffer);
      v16 = (HSTRING)*((_QWORD *)this + 32);
      if ( !IsRootW )
      {
        String = SystemSettings::DataModel::PropValueHelper::CreateString(v16, a3);
        goto LABEL_55;
      }
      v48 = 0;
      v17 = (unsigned __int16 **)WindowsGetStringRawBuffer(v16, 0);
      v6 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
             (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Root_Path_Friendly_Name",
             (const unsigned __int16 *)&v48,
             v17);
      if ( v6 < 0 )
        goto LABEL_56;
      v18 = v48;
      goto LABEL_11;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E340, v13) )
    {
      v21 = *((_QWORD *)this + 33);
      v22 = *((_QWORD *)this + 34);
      if ( v22 < 0 )
      {
        v24 = *((_QWORD *)this + 34) & 1LL | (*((_QWORD *)this + 34) >> 1);
        v23 = (double)(int)v24 + (double)(int)v24;
      }
      else
      {
        v23 = (double)(int)v22;
      }
      v25 = (double)(int)v21 / v23;
      v26 = DOUBLE_1_0;
      v27 = v25 * 100.0;
      if ( v27 >= 1.0 || v21 <= 0 )
        v26 = fmin(100.0, v27);
      String = SystemSettings::DataModel::PropValueHelper::CreateDouble(v26, a3);
      goto LABEL_55;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E410, v20) )
    {
      v18 = (unsigned __int16 *)((char *)this + 286);
      goto LABEL_11;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E3E8, v28) )
    {
      v18 = (unsigned __int16 *)((char *)this + 414);
      goto LABEL_11;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C20, v29) )
    {
      if ( !IsDesktopSKU() )
      {
        v18 = (unsigned __int16 *)&unk_18010E638;
        goto LABEL_11;
      }
      v31 = *((_DWORD *)this + 70);
      if ( !v31 )
        goto LABEL_38;
      v32 = v31 - 2;
      if ( !v32 )
      {
        v18 = L"%SystemRoot%\\system32\\imageres.dll,-108";
        goto LABEL_11;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v18 = L"%SystemRoot%\\system32\\imageres.dll,-113";
        goto LABEL_11;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        v18 = L"%SystemRoot%\\system32\\imageres.dll,-189";
        goto LABEL_11;
      }
      v35 = v34 - 5;
      if ( !v35 )
      {
        v18 = L"%SystemRoot%\\system32\\imageres.dll,-112";
        goto LABEL_11;
      }
      if ( v35 != 3 )
      {
LABEL_38:
        v18 = L"%SystemRoot%\\system32\\imageres.dll,-3";
        goto LABEL_11;
      }
      v18 = L"%SystemRoot%\\system32\\imageres.dll,-181";
LABEL_11:
      String = SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
LABEL_55:
      v6 = String;
      goto LABEL_56;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010CD50, v30) )
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010E610, v36) )
        goto LABEL_56;
      String = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 284), a3);
      goto LABEL_55;
    }
    v37 = *((_DWORD *)this + 70);
    if ( v37 )
    {
      v38 = 2;
      v39 = v37 - 2;
      if ( !v39 )
      {
        v38 = 4;
        goto LABEL_52;
      }
      v40 = v39 - 1;
      if ( !v40 )
      {
        v38 = 3;
        goto LABEL_52;
      }
      v41 = v40 - 1;
      if ( !v41 )
      {
        v38 = 5;
        goto LABEL_52;
      }
      v42 = v41 - 5;
      if ( !v42 )
      {
LABEL_52:
        String = SystemSettings::DataModel::PropValueHelper::CreateUInt32(v38, a3);
        goto LABEL_55;
      }
      if ( v42 == 3 )
      {
        v38 = 6;
        goto LABEL_52;
      }
    }
    v38 = 13;
    goto LABEL_52;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)this + v9 + 143) );
  do
    ++v8;
  while ( *((_WORD *)this + v8 + 207) );
  v10 = 2 * ((unsigned int)v9 + (_DWORD)v8 + WindowsGetStringLen(*((HSTRING *)this + 32))) + 10;
  v11 = (unsigned __int16 *)malloc(v10);
  if ( v11 )
  {
    v12 = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
    StringCbPrintfW(v11, (unsigned int)v10, L"%ls. %ls. %ls", v12, (char *)this + 286, (char *)this + 414);
    v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v11, a3);
    free(v11);
  }
LABEL_56:
  v43 = SettingsHandlersStorageSenseLogging::Provider();
  v44 = (int)v43;
  if ( *(_DWORD *)v43 > 3u )
  {
    LODWORD(v48) = v6;
    v49 = WindowsGetStringRawBuffer((HSTRING)a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v44,
      (unsigned int)&unk_180150B54,
      v45,
      v46,
      (__int64)&v49,
      (__int64)&v48);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180055f20  mov     [rsp+arg_0], rbx
0x180055f25  push    rbp
0x180055f26  push    rsi
0x180055f27  push    rdi
0x180055f28  push    r12
0x180055f2a  push    r13
0x180055f2c  push    r14
0x180055f2e  push    r15
0x180055f30  sub     rsp, 30h
0x180055f34  mov     rbp, rdx
0x180055f37  mov     rbx, rcx
0x180055f3a  xor     r14d, r14d
0x180055f3d  lea     rdx, stru_18010E270; HSTRING
0x180055f44  mov     rcx, rbp; this
0x180055f47  mov     [r8], r14
0x180055f4a  mov     rsi, r8
0x180055f4d  mov     edi, 80070057h
0x180055f52  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180055f57  test    al, al
0x180055f59  jz      loc_180056005
0x180055f5f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180055f63  lea     r12, [rbx+11Eh]
0x180055f6a  mov     r15, r14
0x180055f6d  lea     r13, [rbx+19Eh]
0x180055f74  xor     eax, eax
0x180055f76  inc     r15
0x180055f79  cmp     [r12+r15*2], ax
0x180055f7e  jnz     short loc_180055F76
0x180055f80  inc     r14
0x180055f83  cmp     [r13+r14*2+0], ax
0x180055f89  jnz     short loc_180055F80
0x180055f8b  mov     rcx, [rbx+100h]; string
0x180055f92  call    cs:__imp_WindowsGetStringLen
0x180055f98  add     eax, r14d
0x180055f9b  add     eax, r15d
0x180055f9e  lea     eax, ds:0Ah[rax*2]
0x180055fa5  mov     ecx, eax; Size
0x180055fa7  mov     r15d, eax
0x180055faa  call    cs:__imp_malloc
0x180055fb0  mov     r14, rax
0x180055fb3  test    rax, rax
0x180055fb6  jz      loc_18005626F
0x180055fbc  mov     rcx, [rbx+100h]; string
0x180055fc3  xor     edx, edx; length
0x180055fc5  call    cs:__imp_WindowsGetStringRawBuffer
0x180055fcb  mov     [rsp+68h+var_40], r13
0x180055fd0  lea     r8, aLsLsLs; "%ls. %ls. %ls"
0x180055fd7  mov     r9, rax
0x180055fda  mov     [rsp+68h+var_48], r12
0x180055fdf  mov     edx, r15d; unsigned __int64
0x180055fe2  mov     rcx, r14; unsigned __int16 *
0x180055fe5  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055fea  mov     rdx, rsi; struct IInspectable **
0x180055fed  mov     rcx, r14; unsigned __int16 *
0x180055ff0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180055ff5  mov     rcx, r14; Block
0x180055ff8  mov     edi, eax
0x180055ffa  call    cs:__imp_free
0x180056000  jmp     loc_18005626F
0x180056005  lea     rdx, stru_18010E308; HSTRING
0x18005600c  mov     rcx, rbp; this
0x18005600f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180056014  test    al, al
0x180056016  jz      short loc_18005608E
0x180056018  mov     rcx, [rbx+100h]; string
0x18005601f  xor     edx, edx; length
0x180056021  call    cs:__imp_WindowsGetStringRawBuffer
0x180056027  mov     rcx, rax; pszPath
0x18005602a  call    cs:__imp_PathIsRootW
0x180056030  mov     rcx, [rbx+100h]; HSTRING
0x180056037  test    eax, eax
0x180056039  jz      short loc_180056081
0x18005603b  xor     edx, edx; length
0x18005603d  mov     [rsp+68h+arg_10], r14
0x180056045  call    cs:__imp_WindowsGetStringRawBuffer
0x18005604b  mov     r8, rax; unsigned __int16 **
0x18005604e  lea     rdx, [rsp+68h+arg_10]; unsigned __int16 *
0x180056056  lea     rcx, aSystemsettings_170; "SystemSettings_StorageSense_Root_Path_F"...
0x18005605d  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180056062  mov     edi, eax
0x180056064  test    eax, eax
0x180056066  js      loc_18005626F
0x18005606c  mov     rcx, [rsp+68h+arg_10]; unsigned __int16 *
0x180056074  mov     rdx, rsi; struct IInspectable **
0x180056077  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18005607c  jmp     loc_18005626D
0x180056081  mov     rdx, rsi; struct IInspectable **
0x180056084  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180056089  jmp     loc_18005626D
0x18005608e  lea     rdx, stru_18010E340; HSTRING
0x180056095  mov     rcx, rbp; this
0x180056098  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005609d  test    al, al
0x18005609f  jz      short loc_180056112
0x1800560a1  mov     rdx, [rbx+108h]
0x1800560a8  xorps   xmm1, xmm1
0x1800560ab  mov     rcx, [rbx+110h]
0x1800560b2  xorps   xmm0, xmm0
0x1800560b5  cvtsi2sd xmm1, rdx
0x1800560ba  test    rcx, rcx
0x1800560bd  js      short loc_1800560C6
0x1800560bf  cvtsi2sd xmm0, rcx
0x1800560c4  jmp     short loc_1800560DB
0x1800560c6  mov     rax, rcx
0x1800560c9  and     ecx, 1
0x1800560cc  shr     rax, 1
0x1800560cf  or      rax, rcx
0x1800560d2  cvtsi2sd xmm0, rax
0x1800560d7  addsd   xmm0, xmm0
0x1800560db  movsd   xmm2, cs:__real@4059000000000000
0x1800560e3  divsd   xmm1, xmm0
0x1800560e7  movsd   xmm0, cs:__real@3ff0000000000000
0x1800560ef  mulsd   xmm1, xmm2
0x1800560f3  comisd  xmm0, xmm1
0x1800560f7  jbe     short loc_1800560FE
0x1800560f9  test    rdx, rdx
0x1800560fc  jg      short loc_180056105
0x1800560fe  movaps  xmm0, xmm2
0x180056101  minsd   xmm0, xmm1; double
0x180056105  mov     rdx, rsi; struct IInspectable **
0x180056108  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18005610d  jmp     loc_18005626D
0x180056112  lea     rdx, stru_18010E410; HSTRING
0x180056119  mov     rcx, rbp; this
0x18005611c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180056121  test    al, al
0x180056123  jz      short loc_180056131
0x180056125  lea     rcx, [rbx+11Eh]
0x18005612c  jmp     loc_180056074
0x180056131  lea     rdx, stru_18010E3E8; HSTRING
0x180056138  mov     rcx, rbp; this
0x18005613b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180056140  test    al, al
0x180056142  jz      short loc_180056150
0x180056144  lea     rcx, [rbx+19Eh]
0x18005614b  jmp     loc_180056074
0x180056150  lea     rdx, stru_180108C20; HSTRING
0x180056157  mov     rcx, rbp; this
0x18005615a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005615f  test    al, al
0x180056161  jz      loc_1800561E7
0x180056167  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x18005616c  test    al, al
0x18005616e  jz      short loc_1800561DB
0x180056170  mov     ecx, [rbx+118h]
0x180056176  test    ecx, ecx
0x180056178  jz      short loc_1800561CF
0x18005617a  sub     ecx, 2
0x18005617d  jz      short loc_1800561C3
0x18005617f  sub     ecx, 1
0x180056182  jz      short loc_1800561B7
0x180056184  sub     ecx, 1
0x180056187  jz      short loc_1800561AB
0x180056189  sub     ecx, 5
0x18005618c  jz      short loc_18005619F
0x18005618e  cmp     ecx, 3
0x180056191  jnz     short loc_1800561CF
0x180056193  lea     rcx, aSystemrootSyst_6; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x18005619a  jmp     loc_180056074
0x18005619f  lea     rcx, aSystemrootSyst_5; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x1800561a6  jmp     loc_180056074
0x1800561ab  lea     rcx, aSystemrootSyst_4; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x1800561b2  jmp     loc_180056074
0x1800561b7  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x1800561be  jmp     loc_180056074
0x1800561c3  lea     rcx, aSystemrootSyst_7; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x1800561ca  jmp     loc_180056074
0x1800561cf  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\system32\\imageres.dll,-3"
0x1800561d6  jmp     loc_180056074
0x1800561db  lea     rcx, unk_18010E638
0x1800561e2  jmp     loc_180056074
0x1800561e7  lea     rdx, stru_18010CD50; HSTRING
0x1800561ee  mov     rcx, rbp; this
0x1800561f1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800561f6  test    al, al
0x1800561f8  jz      short loc_18005624C
0x1800561fa  mov     ecx, [rbx+118h]
0x180056200  test    ecx, ecx
0x180056202  jz      short loc_18005623B
0x180056204  mov     eax, 2
0x180056209  sub     ecx, eax
0x18005620b  jz      short loc_180056234
0x18005620d  sub     ecx, 1
0x180056210  jz      short loc_18005622D
0x180056212  sub     ecx, 1
0x180056215  jz      short loc_180056226
0x180056217  sub     ecx, 5
0x18005621a  jz      short loc_180056240
0x18005621c  cmp     ecx, 3
0x18005621f  jnz     short loc_18005623B
0x180056221  lea     eax, [rcx+3]
0x180056224  jmp     short loc_180056240
0x180056226  mov     eax, 5
0x18005622b  jmp     short loc_180056240
0x18005622d  mov     eax, 3
0x180056232  jmp     short loc_180056240
0x180056234  mov     eax, 4
0x180056239  jmp     short loc_180056240
0x18005623b  mov     eax, 0Dh
0x180056240  mov     rdx, rsi; struct IInspectable **
0x180056243  mov     ecx, eax; unsigned int
0x180056245  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18005624a  jmp     short loc_18005626D
0x18005624c  lea     rdx, stru_18010E610; HSTRING
0x180056253  mov     rcx, rbp; this
0x180056256  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18005625b  test    al, al
0x18005625d  jz      short loc_18005626F
0x18005625f  mov     cl, [rbx+11Ch]; unsigned __int8
0x180056265  mov     rdx, rsi; struct IInspectable **
0x180056268  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18005626d  mov     edi, eax
0x18005626f  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x180056274  mov     rbx, rax
0x180056277  mov     ecx, [rax]
0x180056279  cmp     ecx, 3
0x18005627c  jbe     short loc_1800562C1
0x18005627e  xor     edx, edx; length
0x180056280  mov     dword ptr [rsp+68h+arg_10], edi
0x180056287  mov     rcx, rbp; string
0x18005628a  call    cs:__imp_WindowsGetStringRawBuffer
0x180056290  mov     [rsp+68h+arg_18], rax
0x180056298  lea     rdx, unk_180150B54
0x18005629f  lea     rax, [rsp+68h+arg_10]
0x1800562a7  mov     rcx, rbx
0x1800562aa  mov     [rsp+68h+var_40], rax
0x1800562af  lea     rax, [rsp+68h+arg_18]
0x1800562b7  mov     [rsp+68h+var_48], rax
0x1800562bc  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800562c1  mov     rbx, [rsp+68h+arg_0]
0x1800562c6  mov     eax, edi
0x1800562c8  add     rsp, 30h
0x1800562cc  pop     r15
0x1800562ce  pop     r14
0x1800562d0  pop     r13
0x1800562d2  pop     r12
0x1800562d4  pop     rdi
0x1800562d5  pop     rsi
0x1800562d6  pop     rbp
0x1800562d7  retn
```
