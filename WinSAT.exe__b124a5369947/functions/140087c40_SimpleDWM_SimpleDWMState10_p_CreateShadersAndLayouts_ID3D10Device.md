# SimpleDWM::SimpleDWMState10::p_CreateShadersAndLayouts(ID3D10Device *)

- ea: `0x140087c40`
- end: `0x1400884d9`
- name: `?p_CreateShadersAndLayouts@SimpleDWMState10@SimpleDWM@@QEAAJPEAUID3D10Device@@@Z`
- size: `2201`
- prototype: `__int64 __fastcall(SimpleDWM::SimpleDWMState10 *__hidden this, struct ID3D10Device *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140087420`

## callees

- `0x14000449c`
- `0x140005f4c`
- `0x140016d04`
- `0x140017af0`
- `0x14002c00c`
- `0x14003f698`
- `0x14003fa8c`
- `0x14007fa4c`
- `0x140087c40`
- `0x14011a010`

## import_xrefs

- `KERNEL32!FindResourceW` at `0x140087c73`
- `KERNEL32!FindResourceW` at `0x140087c73`
- `KERNEL32!LoadResource` at `0x140087cc5`
- `KERNEL32!LoadResource` at `0x140087cc5`
- `KERNEL32!LockResource` at `0x140087cf7`
- `KERNEL32!LockResource` at `0x140087cf7`
- `KERNEL32!GetLastError` at `0x140087c81`
- `KERNEL32!GetLastError` at `0x140087ca2`
- `KERNEL32!GetLastError` at `0x140087cd3`
- `KERNEL32!GetLastError` at `0x140087d05`
- `KERNEL32!GetLastError` at `0x140087c81`
- `KERNEL32!GetLastError` at `0x140087ca2`
- `KERNEL32!GetLastError` at `0x140087cd3`
- `KERNEL32!GetLastError` at `0x140087d05`
- `KERNEL32!SizeofResource` at `0x140087cec`
- `KERNEL32!SizeofResource` at `0x140087cec`
- `d3d10_1!D3D10CompileShader` at `0x140087d6a`
- `d3d10_1!D3D10CompileShader` at `0x140087f58`
- `d3d10_1!D3D10CompileShader` at `0x1400880a8`
- `d3d10_1!D3D10CompileShader` at `0x1400881aa`
- `d3d10_1!D3D10CompileShader` at `0x1400882d3`
- `d3d10_1!D3D10CompileShader` at `0x140087d6a`
- `d3d10_1!D3D10CompileShader` at `0x140087f58`
- `d3d10_1!D3D10CompileShader` at `0x1400880a8`
- `d3d10_1!D3D10CompileShader` at `0x1400881aa`
- `d3d10_1!D3D10CompileShader` at `0x1400882d3`

## string_xrefs

- `0x140087d89`: `Failed calling D3D10CompileShader.`
- `0x140087f7a`: `Failed calling D3D10CompileShader.`
- `0x1400882f2`: `Failed calling D3D10CompileShader.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SimpleDWM::SimpleDWMState10::p_CreateShadersAndLayouts(
        SimpleDWM::SimpleDWMState10 *this,
        struct ID3D10Device *a2)
{
  HRSRC ResourceW; // rax
  HRSRC v5; // rbx
  signed int LastError; // eax
  int v7; // ebx
  HGLOBAL Resource; // rdi
  SIZE_T v9; // rbx
  const CHAR *v10; // r15
  SIZE_T v11; // r12
  unsigned __int16 v12; // dx
  __int64 v13; // rcx
  HRESULT (__stdcall *CreateVertexShader)(ID3D10Device *, const void *, SIZE_T, ID3D10VertexShader **); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int16 v17; // dx
  __int64 v18; // rcx
  HRESULT (__stdcall *CreateInputLayout)(ID3D10Device *, const D3D10_INPUT_ELEMENT_DESC *, UINT, const void *, SIZE_T, ID3D10InputLayout **); // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  HRESULT (__stdcall *CreatePixelShader)(ID3D10Device *, const void *, SIZE_T, ID3D10PixelShader **); // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  HRESULT (__stdcall *v27)(ID3D10Device *, const void *, SIZE_T, ID3D10PixelShader **); // rdi
  __int64 v28; // rbx
  __int64 v29; // rax
  HRESULT (__stdcall *v30)(ID3D10Device *, const void *, SIZE_T, ID3D10VertexShader **); // rdi
  __int64 v31; // rbx
  __int64 v32; // rax
  HRESULT (__stdcall *v33)(ID3D10Device *, const void *, SIZE_T, ID3D10PixelShader **); // rdi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rax
  char pInclude; // [rsp+20h] [rbp-68h]
  ID3D10Blob *ppErrorMsgs; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v43[8]; // [rsp+58h] [rbp-30h] BYREF
  int v44; // [rsp+A0h] [rbp+18h]
  ID3D10Blob *ppShader; // [rsp+A8h] [rbp+20h] BYREF

  ppShader = 0;
  ppErrorMsgs = 0;
  ResourceW = FindResourceW(0, (LPCWSTR)0xC9, (LPCWSTR)0xA);
  v5 = ResourceW;
  if ( ResourceW
    && (Resource = LoadResource(0, ResourceW)) != 0
    && (v9 = SizeofResource(0, v5), (v10 = (const CHAR *)LockResource(Resource)) != 0) )
  {
    v11 = v9;
    v7 = D3D10CompileShader(
           v10,
           v9,
           0,
           0,
           0,
           "SimpleVertexShader",
           "vs_4_0",
           *((_DWORD *)this + 97),
           &ppShader,
           &ppErrorMsgs);
    v44 = v7;
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1525,
        (unsigned int)v7,
        L"Failed calling D3D10CompileShader.",
        &qword_14012B318);
      v13 = 222;
LABEL_8:
      D3DCommon::ERR((D3DCommon *)v13, v12);
LABEL_52:
      if ( ppErrorMsgs && D3DCommon::g_phStdOut )
      {
        try
        {
          v36 = ((__int64 (*)(void))ppErrorMsgs->lpVtbl->GetBufferSize)();
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v43,
            v36);
          v37 = ((__int64 (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->GetBufferSize)(ppErrorMsgs);
          v38 = ((__int64 (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->GetBufferPointer)(ppErrorMsgs);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::transcode_from(
            v43,
            v38,
            v37);
          v39 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  D3DCommon::g_phStdOut + 240,
                  v43);
          std::endl(v39);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v43);
        }
        catch ( std::bad_alloc )
        {
          v7 = v44;
          goto LABEL_54;
        }
        catch ( ... )
        {
          v7 = v44;
          goto LABEL_54;
        }
      }
      goto LABEL_54;
    }
    CreateVertexShader = a2->lpVtbl->CreateVertexShader;
    v15 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v16 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, __int64, __int64, char *))CreateVertexShader)(
           a2,
           v16,
           v15,
           (char *)this + 504);
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1534,
        (unsigned int)v7,
        L"Failed creating vertex shader.",
        &qword_14012B318);
      v18 = 226;
LABEL_11:
      D3DCommon::ERR((D3DCommon *)v18, v17);
      goto LABEL_54;
    }
    CreateInputLayout = a2->lpVtbl->CreateInputLayout;
    v20 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v21 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, char **, __int64, __int64, __int64, char *))CreateInputLayout)(
           a2,
           &off_14011D7E0,
           3,
           v21,
           v20,
           (char *)this + 544);
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1561,
        (unsigned int)v7,
        L"Failed creating input layout.",
        &qword_14012B318);
      goto LABEL_54;
    }
    if ( ppShader )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
      ppShader = 0;
    }
    if ( ppErrorMsgs )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
      ppErrorMsgs = 0;
    }
    v7 = D3D10CompileShader(
           v10,
           v11,
           0,
           0,
           0,
           "SimplePixelShader",
           "ps_4_0",
           *((_DWORD *)this + 97),
           &ppShader,
           &ppErrorMsgs);
    v44 = v7;
    if ( v7 < 0 )
    {
      v22 = 1583;
LABEL_20:
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        v22,
        (unsigned int)v7,
        L"Failed calling D3D10CompileShader.",
        &qword_14012B318);
      v13 = 221;
      goto LABEL_8;
    }
    CreatePixelShader = a2->lpVtbl->CreatePixelShader;
    v24 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v25 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, __int64, __int64, char *))CreatePixelShader)(
           a2,
           v25,
           v24,
           (char *)this + 520);
    if ( v7 < 0 )
    {
      v26 = 1592;
LABEL_23:
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        v26,
        (unsigned int)v7,
        L"Failed creating pixel shader.",
        &qword_14012B318);
      v18 = 225;
      goto LABEL_11;
    }
    if ( ppShader )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
      ppShader = 0;
    }
    if ( ppErrorMsgs )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
      ppErrorMsgs = 0;
    }
    v7 = D3D10CompileShader(
           v10,
           v11,
           0,
           0,
           0,
           "RTPixelShader",
           "ps_4_0",
           *((_DWORD *)this + 97),
           &ppShader,
           &ppErrorMsgs);
    v44 = v7;
    if ( v7 < 0 )
    {
      v22 = 1613;
      goto LABEL_20;
    }
    v27 = a2->lpVtbl->CreatePixelShader;
    v28 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v29 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, __int64, __int64, char *))v27)(
           a2,
           v29,
           v28,
           (char *)this + 536);
    if ( v7 < 0 )
    {
      v26 = 1622;
      goto LABEL_23;
    }
    if ( ppShader )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
      ppShader = 0;
    }
    if ( ppErrorMsgs )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
      ppErrorMsgs = 0;
    }
    v7 = D3D10CompileShader(
           v10,
           v11,
           0,
           0,
           0,
           "GlassVertexShader",
           "vs_4_0",
           *((_DWORD *)this + 97),
           &ppShader,
           &ppErrorMsgs);
    v44 = v7;
    if ( v7 < 0 )
    {
      v13 = 224;
      goto LABEL_8;
    }
    v30 = a2->lpVtbl->CreateVertexShader;
    v31 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v32 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, __int64, __int64, char *))v30)(
           a2,
           v32,
           v31,
           (char *)this + 512);
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1651,
        (unsigned int)v7,
        L"Failed creating vertex shader.",
        &qword_14012B318);
      v18 = 228;
      goto LABEL_11;
    }
    if ( ppShader )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
      ppShader = 0;
    }
    if ( ppErrorMsgs )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
      ppErrorMsgs = 0;
    }
    v7 = D3D10CompileShader(
           v10,
           v11,
           0,
           0,
           0,
           "GlassPixelShader",
           "ps_4_0",
           *((_DWORD *)this + 97),
           &ppShader,
           &ppErrorMsgs);
    v44 = v7;
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1672,
        (unsigned int)v7,
        L"Failed calling D3D10CompileShader.",
        &qword_14012B318);
      v13 = 223;
      goto LABEL_8;
    }
    v33 = a2->lpVtbl->CreatePixelShader;
    v34 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferSize)(ppShader);
    v35 = ((__int64 (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->GetBufferPointer)(ppShader);
    v7 = ((__int64 (__fastcall *)(struct ID3D10Device *, __int64, __int64, char *))v33)(
           a2,
           v35,
           v34,
           (char *)this + 528);
    v44 = v7;
    if ( v7 < 0 )
    {
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        1681,
        (unsigned int)v7,
        L"Failed creating pixel shader.",
        &qword_14012B318);
      v18 = 227;
      goto LABEL_11;
    }
    if ( ppShader )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
      ppShader = 0;
    }
    if ( ppErrorMsgs )
    {
      ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
      ppErrorMsgs = 0;
      goto LABEL_52;
    }
  }
  else
  {
    GetLastError();
    Record_Win32Error_w("base\\winsat\\d3d\\simpledwmdx10.cpp", pInclude);
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_54:
  if ( ppShader )
  {
    ((void (__fastcall *)(ID3D10Blob *))ppShader->lpVtbl->Release)(ppShader);
    ppShader = 0;
  }
  if ( ppErrorMsgs )
    ((void (__fastcall *)(ID3D10Blob *))ppErrorMsgs->lpVtbl->Release)(ppErrorMsgs);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140087c40  mov     rax, rsp
0x140087c43  mov     [rax+8], rbx
0x140087c47  mov     [rax+10h], rsi
0x140087c4b  push    rdi
0x140087c4c  push    r12
0x140087c4e  push    r13
0x140087c50  push    r14
0x140087c52  push    r15
0x140087c54  sub     rsp, 60h
0x140087c58  mov     r13, rdx
0x140087c5b  mov     r14, rcx
0x140087c5e  xor     esi, esi
0x140087c60  mov     [rax+20h], rsi
0x140087c64  mov     [rax-38h], rsi
0x140087c68  mov     edx, 0C9h; lpName
0x140087c6d  xor     ecx, ecx; hModule
0x140087c6f  lea     r8d, [rsi+0Ah]; lpType
0x140087c73  call    cs:__imp_FindResourceW
0x140087c79  mov     rbx, rax
0x140087c7c  test    rax, rax
0x140087c7f  jnz     short loc_140087CC0
0x140087c81  call    cs:__imp_GetLastError
0x140087c87  lea     r9, aFailedFindingR; "Failed finding resource."
0x140087c8e  mov     edx, 5D4h
0x140087c93  mov     r8d, eax
0x140087c96  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140087c9d  call    Record_Win32Error_w
0x140087ca2  call    cs:__imp_GetLastError
0x140087ca8  mov     ebx, eax
0x140087caa  test    eax, eax
0x140087cac  jle     loc_140088486
0x140087cb2  movzx   ebx, ax
0x140087cb5  or      ebx, 80070000h
0x140087cbb  jmp     loc_140088486
0x140087cc0  mov     rdx, rbx; hResInfo
0x140087cc3  xor     ecx, ecx; hModule
0x140087cc5  call    cs:__imp_LoadResource
0x140087ccb  mov     rdi, rax
0x140087cce  test    rax, rax
0x140087cd1  jnz     short loc_140087CE7
0x140087cd3  call    cs:__imp_GetLastError
0x140087cd9  lea     r9, aFailedLoadingR; "Failed loading resource."
0x140087ce0  mov     edx, 5DBh
0x140087ce5  jmp     short loc_140087C93
0x140087ce7  mov     rdx, rbx; hResInfo
0x140087cea  xor     ecx, ecx; hModule
0x140087cec  call    cs:__imp_SizeofResource
0x140087cf2  mov     ebx, eax
0x140087cf4  mov     rcx, rdi; hResData
0x140087cf7  call    cs:__imp_LockResource
0x140087cfd  mov     r15, rax
0x140087d00  test    rax, rax
0x140087d03  jnz     short loc_140087D1C
0x140087d05  call    cs:__imp_GetLastError
0x140087d0b  lea     r9, aFailedLockingR; "Failed locking resource."
0x140087d12  mov     edx, 5E3h
0x140087d17  jmp     loc_140087C93
0x140087d1c  mov     r12, rbx
0x140087d1f  lea     rax, [rsp+88h+var_38]
0x140087d24  mov     [rsp+88h+ppErrorMsgs], rax; ppErrorMsgs
0x140087d29  lea     rax, [rsp+88h+arg_18]
0x140087d31  mov     [rsp+88h+ppShader], rax; ppShader
0x140087d36  mov     eax, [r14+184h]
0x140087d3d  mov     [rsp+88h+Flags], eax; Flags
0x140087d41  lea     rax, pProfile; "vs_4_0"
0x140087d48  mov     [rsp+88h+pProfile], rax; pProfile
0x140087d4d  lea     rax, pFunctionName; "SimpleVertexShader"
0x140087d54  mov     [rsp+88h+pFunctionName], rax; pFunctionName
0x140087d59  mov     [rsp+88h+pInclude], rsi; pInclude
0x140087d5e  xor     r9d, r9d; pDefines
0x140087d61  xor     r8d, r8d; pFileName
0x140087d64  mov     rdx, rbx; SrcDataSize
0x140087d67  mov     rcx, r15; pSrcData
0x140087d6a  call    cs:__imp_D3D10CompileShader
0x140087d70  mov     ebx, eax
0x140087d72  mov     [rsp+88h+arg_10], eax
0x140087d79  test    eax, eax
0x140087d7b  jns     short loc_140087DB3
0x140087d7d  lea     rax, qword_14012B318
0x140087d84  mov     [rsp+88h+pInclude], rax
0x140087d89  lea     r9, aFailedCallingD_1; "Failed calling D3D10CompileShader."
0x140087d90  mov     r8d, ebx
0x140087d93  mov     edx, 5F5h
0x140087d98  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140087d9f  call    Record_FailingHresult_w
0x140087da4  mov     ecx, 0DEh; this
0x140087da9  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140087dae  jmp     loc_1400883E3
0x140087db3  mov     rax, [r13+0]
0x140087db7  mov     rdi, [rax+278h]
0x140087dbe  mov     rcx, [rsp+88h+arg_18]
0x140087dc6  mov     rax, [rcx]
0x140087dc9  mov     rax, [rax+20h]
0x140087dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087dd2  mov     rbx, rax
0x140087dd5  mov     rcx, [rsp+88h+arg_18]
0x140087ddd  mov     rdx, [rcx]
0x140087de0  mov     rax, [rdx+18h]
0x140087de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087de9  lea     r9, [r14+1F8h]
0x140087df0  mov     r8, rbx
0x140087df3  mov     rdx, rax
0x140087df6  mov     rcx, r13
0x140087df9  mov     rax, rdi
0x140087dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e01  mov     ebx, eax
0x140087e03  test    eax, eax
0x140087e05  jns     short loc_140087E3D
0x140087e07  lea     rax, qword_14012B318
0x140087e0e  mov     [rsp+88h+pInclude], rax
0x140087e13  lea     r9, aFailedCreating_8; "Failed creating vertex shader."
0x140087e1a  mov     r8d, ebx
0x140087e1d  mov     edx, 5FEh
0x140087e22  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140087e29  call    Record_FailingHresult_w
0x140087e2e  mov     ecx, 0E2h; this
0x140087e33  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140087e38  jmp     loc_140088486
0x140087e3d  mov     rax, [r13+0]
0x140087e41  mov     rdi, [rax+270h]
0x140087e48  mov     rcx, [rsp+88h+arg_18]
0x140087e50  mov     rax, [rcx]
0x140087e53  mov     rax, [rax+20h]
0x140087e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e5c  mov     rbx, rax
0x140087e5f  mov     rcx, [rsp+88h+arg_18]
0x140087e67  mov     rdx, [rcx]
0x140087e6a  mov     rax, [rdx+18h]
0x140087e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e73  lea     rcx, [r14+220h]
0x140087e7a  mov     [rsp+88h+pFunctionName], rcx
0x140087e7f  mov     [rsp+88h+pInclude], rbx
0x140087e84  mov     r9, rax
0x140087e87  mov     r8d, 3
0x140087e8d  lea     rdx, off_14011D7E0; "POSITION"
0x140087e94  mov     rcx, r13
0x140087e97  mov     rax, rdi
0x140087e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e9f  mov     ebx, eax
0x140087ea1  test    eax, eax
0x140087ea3  jns     short loc_140087ED1
0x140087ea5  lea     rax, qword_14012B318
0x140087eac  mov     [rsp+88h+pInclude], rax
0x140087eb1  lea     r9, aFailedCreating_6; "Failed creating input layout."
0x140087eb8  mov     r8d, ebx
0x140087ebb  mov     edx, 619h
0x140087ec0  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140087ec7  call    Record_FailingHresult_w
0x140087ecc  jmp     loc_140088486
0x140087ed1  mov     rcx, [rsp+88h+arg_18]
0x140087ed9  test    rcx, rcx
0x140087edc  jz      short loc_140087EF2
0x140087ede  mov     rax, [rcx]
0x140087ee1  mov     rax, [rax+10h]
0x140087ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087eea  mov     [rsp+88h+arg_18], rsi
0x140087ef2  mov     rcx, [rsp+88h+var_38]
0x140087ef7  test    rcx, rcx
0x140087efa  jz      short loc_140087F0D
0x140087efc  mov     rax, [rcx]
0x140087eff  mov     rax, [rax+10h]
0x140087f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087f08  mov     [rsp+88h+var_38], rsi
0x140087f0d  lea     rax, [rsp+88h+var_38]
0x140087f12  mov     [rsp+88h+ppErrorMsgs], rax; ppErrorMsgs
0x140087f17  lea     rax, [rsp+88h+arg_18]
0x140087f1f  mov     [rsp+88h+ppShader], rax; ppShader
0x140087f24  mov     eax, [r14+184h]
0x140087f2b  mov     [rsp+88h+Flags], eax; Flags
0x140087f2f  lea     rax, aPs40; "ps_4_0"
0x140087f36  mov     [rsp+88h+pProfile], rax; pProfile
0x140087f3b  lea     rax, aSimplepixelsha; "SimplePixelShader"
0x140087f42  mov     [rsp+88h+pFunctionName], rax; pFunctionName
0x140087f47  mov     [rsp+88h+pInclude], rsi; pInclude
0x140087f4c  xor     r9d, r9d; pDefines
0x140087f4f  xor     r8d, r8d; pFileName
0x140087f52  mov     rdx, r12; SrcDataSize
0x140087f55  mov     rcx, r15; pSrcData
0x140087f58  call    cs:__imp_D3D10CompileShader
0x140087f5e  mov     ebx, eax
0x140087f60  mov     [rsp+88h+arg_10], eax
0x140087f67  test    eax, eax
0x140087f69  jns     short loc_140087F9C
0x140087f6b  mov     edx, 62Fh
0x140087f70  lea     rax, qword_14012B318
0x140087f77  mov     r8d, ebx
0x140087f7a  lea     r9, aFailedCallingD_1; "Failed calling D3D10CompileShader."
0x140087f81  mov     [rsp+88h+pInclude], rax
0x140087f86  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140087f8d  call    Record_FailingHresult_w
0x140087f92  mov     ecx, 0DDh
0x140087f97  jmp     loc_140087DA9
0x140087f9c  mov     rax, [r13+0]
0x140087fa0  mov     rdi, [rax+290h]
0x140087fa7  mov     rcx, [rsp+88h+arg_18]
0x140087faf  mov     rax, [rcx]
0x140087fb2  mov     rax, [rax+20h]
0x140087fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087fbb  mov     rbx, rax
0x140087fbe  mov     rcx, [rsp+88h+arg_18]
0x140087fc6  mov     rdx, [rcx]
0x140087fc9  mov     rax, [rdx+18h]
0x140087fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087fd2  lea     r9, [r14+208h]
0x140087fd9  mov     r8, rbx
0x140087fdc  mov     rdx, rax
0x140087fdf  mov     rcx, r13
0x140087fe2  mov     rax, rdi
0x140087fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087fea  mov     ebx, eax
0x140087fec  test    eax, eax
0x140087fee  jns     short loc_140088021
0x140087ff0  mov     edx, 638h
0x140087ff5  lea     rax, qword_14012B318
0x140087ffc  mov     r8d, ebx
0x140087fff  lea     r9, aFailedCreating_7; "Failed creating pixel shader."
0x140088006  mov     [rsp+88h+pInclude], rax
0x14008800b  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x140088012  call    Record_FailingHresult_w
0x140088017  mov     ecx, 0E1h
0x14008801c  jmp     loc_140087E33
0x140088021  mov     rcx, [rsp+88h+arg_18]
0x140088029  test    rcx, rcx
0x14008802c  jz      short loc_140088042
0x14008802e  mov     rax, [rcx]
0x140088031  mov     rax, [rax+10h]
0x140088035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008803a  mov     [rsp+88h+arg_18], rsi
0x140088042  mov     rcx, [rsp+88h+var_38]
0x140088047  test    rcx, rcx
0x14008804a  jz      short loc_14008805D
0x14008804c  mov     rax, [rcx]
0x14008804f  mov     rax, [rax+10h]
0x140088053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088058  mov     [rsp+88h+var_38], rsi
0x14008805d  lea     rax, [rsp+88h+var_38]
0x140088062  mov     [rsp+88h+ppErrorMsgs], rax; ppErrorMsgs
0x140088067  lea     rax, [rsp+88h+arg_18]
0x14008806f  mov     [rsp+88h+ppShader], rax; ppShader
0x140088074  mov     eax, [r14+184h]
0x14008807b  mov     [rsp+88h+Flags], eax; Flags
0x14008807f  lea     rax, aPs40; "ps_4_0"
0x140088086  mov     [rsp+88h+pProfile], rax; pProfile
0x14008808b  lea     rax, aRtpixelshader; "RTPixelShader"
0x140088092  mov     [rsp+88h+pFunctionName], rax; pFunctionName
0x140088097  mov     [rsp+88h+pInclude], rsi; pInclude
0x14008809c  xor     r9d, r9d; pDefines
0x14008809f  xor     r8d, r8d; pFileName
0x1400880a2  mov     rdx, r12; SrcDataSize
0x1400880a5  mov     rcx, r15; pSrcData
0x1400880a8  call    cs:__imp_D3D10CompileShader
0x1400880ae  mov     ebx, eax
0x1400880b0  mov     [rsp+88h+arg_10], eax
0x1400880b7  test    eax, eax
0x1400880b9  jns     short loc_1400880C5
0x1400880bb  mov     edx, 64Dh
0x1400880c0  jmp     loc_140087F70
0x1400880c5  mov     rax, [r13+0]
0x1400880c9  mov     rdi, [rax+290h]
0x1400880d0  mov     rcx, [rsp+88h+arg_18]
0x1400880d8  mov     rax, [rcx]
0x1400880db  mov     rax, [rax+20h]
0x1400880df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400880e4  mov     rbx, rax
0x1400880e7  mov     rcx, [rsp+88h+arg_18]
0x1400880ef  mov     rdx, [rcx]
0x1400880f2  mov     rax, [rdx+18h]
0x1400880f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400880fb  lea     r9, [r14+218h]
0x140088102  mov     r8, rbx
0x140088105  mov     rdx, rax
0x140088108  mov     rcx, r13
0x14008810b  mov     rax, rdi
0x14008810e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088113  mov     ebx, eax
0x140088115  test    eax, eax
0x140088117  jns     short loc_140088123
0x140088119  mov     edx, 656h
0x14008811e  jmp     loc_140087FF5
0x140088123  mov     rcx, [rsp+88h+arg_18]
0x14008812b  test    rcx, rcx
0x14008812e  jz      short loc_140088144
0x140088130  mov     rax, [rcx]
0x140088133  mov     rax, [rax+10h]
0x140088137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008813c  mov     [rsp+88h+arg_18], rsi
0x140088144  mov     rcx, [rsp+88h+var_38]
0x140088149  test    rcx, rcx
0x14008814c  jz      short loc_14008815F
0x14008814e  mov     rax, [rcx]
0x140088151  mov     rax, [rax+10h]
0x140088155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008815a  mov     [rsp+88h+var_38], rsi
0x14008815f  lea     rax, [rsp+88h+var_38]
0x140088164  mov     [rsp+88h+ppErrorMsgs], rax; ppErrorMsgs
0x140088169  lea     rax, [rsp+88h+arg_18]
0x140088171  mov     [rsp+88h+ppShader], rax; ppShader
0x140088176  mov     eax, [r14+184h]
0x14008817d  mov     [rsp+88h+Flags], eax; Flags
0x140088181  lea     rax, pProfile; "vs_4_0"
  ... truncated ...
```
