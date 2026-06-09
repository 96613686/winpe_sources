# CMFTtoDMOImpl<CMFTtoDMO>::MFTProcessInput(ulong,IMFSample *,ulong)

- ea: `0x180004a20`
- end: `0x180004d0e`
- name: `?MFTProcessInput@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@UEAAJKPEAUIMFSample@@K@Z`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004a20`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004cbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004cbb`

## string_xrefs

- `0x180004c42`: `MFCreateMediaTypeFromRepresentation`
- `0x180004c5f`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`
- `0x180004cae`: `MFPLAT.DLL`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTProcessInput(__int64 a1, unsigned int a2, __int64 *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int v10; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v14; // rax
  unsigned int i; // ecx
  __int64 v16; // rax
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  __int64 v18; // [rsp+48h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-20h] BYREF
  int v21; // [rsp+90h] [rbp+18h] BYREF

  v17 = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a3 )
  {
    v6 = -2147467261;
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    Library = *(HMODULE *)(a1 + 8);
    if ( Library != (HMODULE)-1LL )
    {
      if ( Library || (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) != 0) )
      {
        ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation");
        *(_QWORD *)(a1 + 16) = ProcAddress;
        if ( ProcAddress )
        {
          v14 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer");
          *(_QWORD *)(a1 + 24) = v14;
          if ( v14 )
            goto LABEL_3;
        }
      }
      *(_QWORD *)(a1 + 8) = -1;
    }
    v6 = -2147467259;
    goto LABEL_16;
  }
LABEL_3:
  if ( !*(_BYTE *)(a1 + 42) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 144LL))(a1 + 48);
    if ( v6 < 0 )
      goto LABEL_16;
    *(_BYTE *)(a1 + 42) = 1;
  }
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a3 + 280))(a3, &v19);
  if ( v6 == -1072875832 )
  {
    v7 = 0;
    v19 = 0;
  }
  else
  {
    v7 = 2;
    if ( v6 < 0 )
      goto LABEL_16;
  }
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a3 + 296))(a3, &v18);
  if ( v6 == -1072875831 )
  {
    v18 = 0;
  }
  else
  {
    if ( v6 < 0 )
      goto LABEL_16;
    v7 |= 4u;
  }
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a3 + 328))(a3, &v17);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, __int64 *))(a1 + 24))(a3, v17, 0, &v20);
    if ( v6 >= 0 )
    {
      v8 = *a3;
      v21 = 0;
      if ( (*(int (__fastcall **)(__int64 *, const GUID *, int *))(v8 + 56))(a3, &MFSampleExtension_CleanPoint, &v21) >= 0
        && v21 )
      {
        v7 |= 1u;
      }
      v9 = *a3;
      v21 = 0;
      if ( (*(int (__fastcall **)(__int64 *, const GUID *, int *))(v9 + 56))(a3, &MFSampleExtension_Discontinuity, &v21) >= 0
        && v21 )
      {
        v7 |= 8u;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 + 48) + 168LL))(
             a1 + 48,
             a2,
             v20,
             v7,
             v19,
             v18);
    }
  }
LABEL_16:
  v10 = 0;
  if ( v6 != 1 )
    v10 = v6;
  if ( v17 )
  {
    (*(void (**)(void))(*(_QWORD *)v17 + 16LL))();
    v17 = 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v10 )
  {
    for ( i = 0; i < 6; ++i )
    {
      v16 = (int)i;
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v16]) == v10 )
        return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v16]);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180004a20  mov     rax, rsp
0x180004a23  push    rbx
0x180004a24  push    r14
0x180004a26  sub     rsp, 68h
0x180004a2a  xor     r14d, r14d
0x180004a2d  mov     [rax+8], rbp
0x180004a31  mov     [rax+10h], rsi
0x180004a35  mov     rbx, r8
0x180004a38  mov     [rax-38h], r14
0x180004a3c  mov     ebp, edx
0x180004a3e  mov     [rax-20h], r14
0x180004a42  mov     rsi, rcx
0x180004a45  mov     [rax-30h], r14
0x180004a49  mov     [rax-28h], r14
0x180004a4d  test    r8, r8
0x180004a50  jz      loc_180004CA2
0x180004a56  cmp     [rcx+10h], r14
0x180004a5a  jz      loc_180004C2F
0x180004a60  cmp     [rsi+2Ah], r14b
0x180004a64  jz      loc_180004CE0
0x180004a6a  mov     rax, [rbx]
0x180004a6d  lea     rdx, [rsp+78h+var_28]
0x180004a72  mov     rcx, rbx
0x180004a75  mov     [rsp+78h+var_18], rdi
0x180004a7a  mov     rax, [rax+118h]
0x180004a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a86  cmp     eax, 0C00D36C8h
0x180004a8b  jz      loc_180004C02
0x180004a91  mov     edi, 2
0x180004a96  test    eax, eax
0x180004a98  js      loc_180004BA1
0x180004a9e  mov     rax, [rbx]
0x180004aa1  lea     rdx, [rsp+78h+var_30]
0x180004aa6  mov     rcx, rbx
0x180004aa9  mov     rax, [rax+128h]
0x180004ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab5  cmp     eax, 0C00D36C9h
0x180004aba  jz      loc_180004C0F
0x180004ac0  test    eax, eax
0x180004ac2  js      loc_180004BA1
0x180004ac8  or      edi, 4
0x180004acb  mov     rax, [rbx]
0x180004ace  lea     rdx, [rsp+78h+var_38]
0x180004ad3  mov     rcx, rbx
0x180004ad6  mov     rax, [rax+148h]
0x180004add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae2  test    eax, eax
0x180004ae4  js      loc_180004BA1
0x180004aea  mov     rdx, [rsp+78h+var_38]
0x180004aef  lea     r9, [rsp+78h+var_20]
0x180004af4  mov     rax, [rsi+18h]
0x180004af8  xor     r8d, r8d
0x180004afb  mov     rcx, rbx
0x180004afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b03  test    eax, eax
0x180004b05  js      loc_180004BA1
0x180004b0b  mov     rax, [rbx]
0x180004b0e  lea     r8, [rsp+78h+arg_10]
0x180004b16  lea     rdx, MFSampleExtension_CleanPoint
0x180004b1d  mov     [rsp+78h+arg_10], r14d
0x180004b25  mov     rcx, rbx
0x180004b28  mov     rax, [rax+38h]
0x180004b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b31  test    eax, eax
0x180004b33  js      short loc_180004B42
0x180004b35  cmp     [rsp+78h+arg_10], r14d
0x180004b3d  jbe     short loc_180004B42
0x180004b3f  or      edi, 1
0x180004b42  mov     rax, [rbx]
0x180004b45  lea     r8, [rsp+78h+arg_10]
0x180004b4d  lea     rdx, MFSampleExtension_Discontinuity
0x180004b54  mov     [rsp+78h+arg_10], r14d
0x180004b5c  mov     rcx, rbx
0x180004b5f  mov     rax, [rax+38h]
0x180004b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b68  test    eax, eax
0x180004b6a  jns     loc_180004C19
0x180004b70  mov     rdx, [rsp+78h+var_30]
0x180004b75  lea     rcx, [rsi+30h]
0x180004b79  mov     rax, [rcx]
0x180004b7c  mov     r9d, edi
0x180004b7f  mov     r8, [rsp+78h+var_20]
0x180004b84  mov     [rsp+78h+var_50], rdx
0x180004b89  mov     rdx, [rsp+78h+var_28]
0x180004b8e  mov     rax, [rax+0A8h]
0x180004b95  mov     [rsp+78h+var_58], rdx
0x180004b9a  mov     edx, ebp
0x180004b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba1  mov     rdi, [rsp+78h+var_18]
0x180004ba6  mov     rcx, [rsp+78h+var_38]
0x180004bab  cmp     eax, 1
0x180004bae  mov     rsi, [rsp+78h+arg_8]
0x180004bb6  mov     ebx, r14d
0x180004bb9  mov     rbp, [rsp+78h+arg_0]
0x180004bc1  cmovnz  ebx, eax
0x180004bc4  test    rcx, rcx
0x180004bc7  jz      short loc_180004BDA
0x180004bc9  mov     rax, [rcx]
0x180004bcc  mov     rax, [rax+10h]
0x180004bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd5  mov     [rsp+78h+var_38], r14
0x180004bda  mov     rcx, [rsp+78h+var_20]
0x180004bdf  test    rcx, rcx
0x180004be2  jz      short loc_180004BF0
0x180004be4  mov     rax, [rcx]
0x180004be7  mov     rax, [rax+10h]
0x180004beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf0  test    ebx, ebx
0x180004bf2  jnz     loc_180004C7B
0x180004bf8  mov     eax, ebx
0x180004bfa  add     rsp, 68h
0x180004bfe  pop     r14
0x180004c00  pop     rbx
0x180004c01  retn
0x180004c02  mov     edi, r14d
0x180004c05  mov     [rsp+78h+var_28], r14
0x180004c0a  jmp     loc_180004A9E
0x180004c0f  mov     [rsp+78h+var_30], r14
0x180004c14  jmp     loc_180004ACB
0x180004c19  cmp     [rsp+78h+arg_10], r14d
0x180004c21  jbe     loc_180004B70
0x180004c27  or      edi, 8
0x180004c2a  jmp     loc_180004B70
0x180004c2f  mov     rax, [rcx+8]
0x180004c33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004c37  jz      loc_180004CD6
0x180004c3d  test    rax, rax
0x180004c40  jz      short loc_180004CAC
0x180004c42  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x180004c49  mov     rcx, rax; hModule
0x180004c4c  call    cs:__imp_GetProcAddress
0x180004c52  mov     [rsi+10h], rax
0x180004c56  test    rax, rax
0x180004c59  jz      short loc_180004CCE
0x180004c5b  mov     rcx, [rsi+8]; hModule
0x180004c5f  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x180004c66  call    cs:__imp_GetProcAddress
0x180004c6c  mov     [rsi+18h], rax
0x180004c70  test    rax, rax
0x180004c73  jnz     loc_180004A60
0x180004c79  jmp     short loc_180004CCE
0x180004c7b  mov     ecx, r14d
0x180004c7e  lea     rdx, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180004c85  cmp     ecx, 6
0x180004c88  jnb     loc_180004BF8
0x180004c8e  movsxd  rax, ecx
0x180004c91  lea     rax, ds:0[rax*8]
0x180004c99  cmp     [rax+rdx], ebx
0x180004c9c  jz      short loc_180004D05
0x180004c9e  inc     ecx
0x180004ca0  jmp     short loc_180004C85
0x180004ca2  mov     eax, 80004003h
0x180004ca7  jmp     loc_180004BA6
0x180004cac  xor     edx, edx; hFile
0x180004cae  lea     rcx, LibFileName; "MFPLAT.DLL"
0x180004cb5  mov     r8d, 800h; dwFlags
0x180004cbb  call    cs:__imp_LoadLibraryExA
0x180004cc1  mov     [rsi+8], rax
0x180004cc5  test    rax, rax
0x180004cc8  jnz     loc_180004C42
0x180004cce  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x180004cd6  mov     eax, 80004005h
0x180004cdb  jmp     loc_180004BA6
0x180004ce0  mov     rax, [rsi+30h]
0x180004ce4  lea     rcx, [rsi+30h]
0x180004ce8  mov     rax, [rax+90h]
0x180004cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf4  test    eax, eax
0x180004cf6  js      loc_180004BA6
0x180004cfc  mov     byte ptr [rsi+2Ah], 1
0x180004d00  jmp     loc_180004A6A
0x180004d05  mov     eax, [rax+rdx+4]
0x180004d09  jmp     loc_180004BFA
```
