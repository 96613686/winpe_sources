# AipGetPeImageVersionInfo

- ea: `0x180008be4`
- end: `0x18000922b`
- name: `AipGetPeImageVersionInfo`
- size: `1607`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000890c`

## callees

- `0x180002138`
- `0x180003fd4`
- `0x180008be4`
- `0x180009234`
- `0x1800093ac`
- `0x180009562`
- `0x1800095c0`

## import_xrefs

- `ntdll!NtClose` at `0x180008da5`
- `ntdll!NtClose` at `0x1800091f1`
- `ntdll!NtClose` at `0x180008da5`
- `ntdll!NtClose` at `0x1800091f1`
- `ntdll!LdrResSearchResource` at `0x180008e05`
- `ntdll!LdrResSearchResource` at `0x180008e05`
- `ntdll!NtCreateSection` at `0x180008d10`
- `ntdll!NtCreateSection` at `0x180008d10`
- `ntdll!NtUnmapViewOfSection` at `0x180008d90`
- `ntdll!NtUnmapViewOfSection` at `0x1800091de`
- `ntdll!NtUnmapViewOfSection` at `0x180008d90`
- `ntdll!NtUnmapViewOfSection` at `0x1800091de`
- `ntdll!NtMapViewOfSection` at `0x180008d52`
- `ntdll!NtMapViewOfSection` at `0x180008d52`

## pseudocode

```c
__int64 __fastcall AipGetPeImageVersionInfo(
        HANDLE FileHandle,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        _OWORD *a6,
        _OWORD *a7)
{
  __m128i v9; // xmm6
  NTSTATUS v10; // edi
  HANDLE v11; // r12
  _DWORD *v12; // rcx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // r15d
  unsigned __int64 v16; // rax
  wchar_t *v17; // r9
  __int64 v18; // rcx
  _WORD *v19; // rax
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  __int64 v24; // rax
  void *v25; // r13
  unsigned __int64 v26; // rax
  _WORD *v27; // rcx
  bool v28; // zf
  unsigned __int64 v29; // rsi
  void *v30; // rax
  __int64 v31; // rcx
  unsigned __int16 v32; // si
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-288h]
  unsigned __int64 v35; // [rsp+58h] [rbp-250h] BYREF
  unsigned __int16 *v36; // [rsp+60h] [rbp-248h] BYREF
  _DWORD *v37; // [rsp+68h] [rbp-240h]
  void *SectionHandle[2]; // [rsp+70h] [rbp-238h] BYREF
  ULONG_PTR ViewSize; // [rsp+80h] [rbp-228h] BYREF
  unsigned int v40; // [rsp+88h] [rbp-220h]
  unsigned __int64 v41; // [rsp+90h] [rbp-218h] BYREF
  unsigned __int16 *v42; // [rsp+98h] [rbp-210h] BYREF
  _DWORD *v43; // [rsp+A0h] [rbp-208h]
  wchar_t *v44; // [rsp+A8h] [rbp-200h]
  __int64 v45; // [rsp+B0h] [rbp-1F8h]
  void *Src; // [rsp+B8h] [rbp-1F0h] BYREF
  HANDLE Handle[3]; // [rsp+C0h] [rbp-1E8h]
  _WORD *v48; // [rsp+D8h] [rbp-1D0h]
  __int64 v49; // [rsp+E0h] [rbp-1C8h]
  wchar_t *v50; // [rsp+E8h] [rbp-1C0h]
  __int64 v51; // [rsp+F0h] [rbp-1B8h]
  __int64 v52; // [rsp+F8h] [rbp-1B0h]
  _WORD *v53; // [rsp+100h] [rbp-1A8h]
  unsigned __int64 v54; // [rsp+108h] [rbp-1A0h]
  _QWORD v55[2]; // [rsp+110h] [rbp-198h]
  struct _OBJECT_ATTRIBUTES v56; // [rsp+120h] [rbp-188h] BYREF
  _WORD v57[128]; // [rsp+150h] [rbp-158h] BYREF

  v37 = a4;
  v43 = a5;
  v9 = 0;
  *(_OWORD *)Handle = 0;
  v42 = 0;
  v36 = 0;
  v41 = 0;
  v35 = 0;
  Src = 0;
  v55[0] = a7;
  v55[1] = a6;
  *a7 = 0;
  *a6 = 0;
  memset(&v56, 0, sizeof(v56));
  *(_OWORD *)SectionHandle = 0;
  ViewSize = 0;
  if ( FileHandle )
  {
    *(_OWORD *)Handle = 0;
    v56.Length = 48;
    v56.RootDirectory = 0;
    v56.Attributes = 512;
    v56.ObjectName = 0;
    *(_OWORD *)&v56.SecurityDescriptor = 0;
    v10 = NtCreateSection(SectionHandle, 5u, &v56, 0, 2u, 0x8000000u, FileHandle);
    if ( v10 >= 0 )
    {
      v10 = NtMapViewOfSection(
              SectionHandle[0],
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &SectionHandle[1],
              0,
              0,
              0,
              &ViewSize,
              ViewUnmap,
              0,
              2u);
      if ( v10 >= 0 )
      {
        v9 = _mm_loadu_si128((const __m128i *)SectionHandle);
        *(__m128i *)Handle = v9;
        *(_OWORD *)SectionHandle = 0;
        ViewSize = 0;
      }
    }
    if ( v10 < 0 )
    {
      if ( SectionHandle[1] )
      {
        NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, SectionHandle[1]);
        SectionHandle[1] = 0;
      }
      if ( SectionHandle[0] )
        NtClose(SectionHandle[0]);
    }
  }
  else
  {
    v10 = -1073741811;
  }
  if ( v10 < 0 )
  {
    v11 = Handle[1];
    goto LABEL_73;
  }
  v11 = (HANDLE)_mm_srli_si128(v9, 8).m128i_u64[0];
  if ( (int)LdrResSearchResource(v11, qword_18000CA38, 3, 4624, &v42, &v41, 0, 0) < 0 )
    goto LABEL_70;
  if ( v41 < 0x5C )
    goto LABEL_70;
  v12 = v42;
  if ( *v42 > v41 || *((_DWORD *)v42 + 10) != -17890115 )
    goto LABEL_70;
  *a2 = *((_DWORD *)v42 + 12);
  *a3 = v12[13];
  *v37 = v12[14];
  *v43 = v12[15];
  v10 = AipQueryValue(v12, L"\\VarFileInfo\\Translation", &v36, &v35);
  if ( v10 < 0 )
    goto LABEL_73;
  if ( v35 < 4 || ((unsigned __int8)v36 & 1) != 0 )
  {
LABEL_70:
    v10 = -2;
  }
  else
  {
    SectionPageProtection[0] = v36[1];
    RtlStringCbPrintfW(v57, 256, L"\\StringFileInfo\\%04x%04x\\", *v36, *(_QWORD *)SectionPageProtection);
    v13 = (unsigned __int64)v57;
    v14 = -1;
    do
      v43 = (_DWORD *)++v14;
    while ( v57[v14] );
    v15 = 0;
    v40 = 0;
    while ( v15 < 2 )
    {
      v16 = (unsigned int)v14;
      if ( v16 >= 128 )
        _report_rangecheckfailure(v13);
      v57[v16] = 0;
      v17 = off_18000B3D0[v15];
      v36 = 0;
      v18 = 128;
      v49 = 128;
      v19 = v57;
      v48 = v57;
      while ( v18 && *v19 )
      {
        v48 = ++v19;
        v49 = --v18;
      }
      v20 = 0;
      if ( !v18 )
        v20 = -1073741811;
      if ( v20 < 0 )
        v36 = 0;
      else
        v36 = (unsigned __int16 *)(128 - v18);
      if ( v20 >= 0 )
      {
        v21 = 2147483646;
        v52 = 2147483646;
        v50 = v17;
        v22 = 128LL - (_QWORD)v36;
        v51 = 128LL - (_QWORD)v36;
        v23 = &v57[(_QWORD)v36];
        v44 = v23;
        v24 = 0;
        v45 = 0;
        while ( v22 )
        {
          if ( !v21 || !*v17 )
            goto LABEL_42;
          *v23++ = *v17;
          v44 = v23;
          v50 = ++v17;
          v51 = --v22;
          v52 = --v21;
          v45 = ++v24;
        }
        v44 = --v23;
        v45 = v24 - 1;
LABEL_42:
        *v23 = 0;
      }
      if ( (int)AipQueryValue(v42, v57, &Src, &v35) < 0 || (v13 = v35, v35 - 1 > 0xFFFE) )
      {
        v10 = 0;
      }
      else
      {
        v25 = Src;
        v26 = (2 * v35) >> 1;
        v13 = 0;
        v37 = 0;
        if ( Src && v26 <= 0x7FFFFFFF )
        {
          v54 = (2 * v35) >> 1;
          v27 = Src;
          v53 = Src;
          v10 = 0;
          while ( 1 )
          {
            v28 = v26 == 0;
            if ( !v26 )
              break;
            if ( !*v27 )
            {
              v28 = v26 == 0;
              break;
            }
            v53 = ++v27;
            v54 = --v26;
          }
          if ( v28 )
            v10 = -1073741811;
          if ( v10 < 0 )
            v37 = 0;
          else
            v37 = (_DWORD *)(((2 * v35) >> 1) - v26);
          v13 = (unsigned __int64)v37;
        }
        else
        {
          v10 = -1073741811;
        }
        if ( v10 < 0 )
          v35 = 0;
        else
          v35 = 2 * v13;
        if ( v10 >= 0 && v35 )
        {
          v29 = v35 + 2;
          v35 = v29;
          v30 = (void *)AiAlloc(v29);
          v31 = v55[v15];
          *(_QWORD *)(v31 + 8) = v30;
          if ( !v30 )
          {
            v10 = -1073741801;
            break;
          }
          v32 = v29 - 2;
          *(_WORD *)v31 = v32;
          *(_WORD *)(v31 + 2) = v32;
          memcpy_0(v30, v25, v32);
        }
        else
        {
          v10 = 0;
        }
      }
      v40 = ++v15;
      LODWORD(v14) = (_DWORD)v43;
    }
  }
LABEL_73:
  if ( v11 )
    NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v11);
  if ( Handle[0] )
    NtClose(Handle[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008be4  mov     r11, rsp
0x180008be7  push    rbx
0x180008be8  push    rsi
0x180008be9  push    rdi
0x180008bea  push    r12
0x180008bec  push    r13
0x180008bee  push    r14
0x180008bf0  push    r15
0x180008bf2  sub     rsp, 270h
0x180008bf9  movaps  xmmword ptr [r11-48h], xmm6
0x180008bfe  mov     rax, cs:__security_cookie
0x180008c05  xor     rax, rsp
0x180008c08  mov     [rsp+2A8h+var_58], rax
0x180008c10  mov     [rsp+2A8h+var_240], r9
0x180008c15  mov     r13, r8
0x180008c18  mov     r15, rdx
0x180008c1b  mov     rax, [rsp+2A8h+arg_20]
0x180008c23  mov     [rsp+2A8h+var_208], rax
0x180008c2b  mov     r10, [rsp+2A8h+arg_28]
0x180008c33  mov     rax, [rsp+2A8h+arg_30]
0x180008c3b  xorps   xmm6, xmm6
0x180008c3e  movups  xmmword ptr [rsp+2A8h+Handle], xmm6
0x180008c46  xor     ebx, ebx
0x180008c48  mov     [r11-210h], rbx
0x180008c4f  mov     [rsp+2A8h+var_248], rbx
0x180008c54  mov     [r11-218h], rbx
0x180008c5b  mov     [rsp+2A8h+var_250], rbx
0x180008c60  mov     [r11-1F0h], rbx
0x180008c67  mov     [r11-198h], rax
0x180008c6e  mov     [r11-190h], r10
0x180008c75  xorps   xmm0, xmm0
0x180008c78  movups  xmmword ptr [rax], xmm0
0x180008c7b  xorps   xmm1, xmm1
0x180008c7e  movups  xmmword ptr [r10], xmm1
0x180008c82  movups  [rsp+2A8h+var_188], xmm0
0x180008c8a  movups  [rsp+2A8h+var_178], xmm0
0x180008c92  movups  [rsp+2A8h+var_168], xmm0
0x180008c9a  movdqu  xmmword ptr [rsp+2A8h+SectionHandle], xmm1
0x180008ca0  mov     [r11-228h], rbx
0x180008ca7  lea     r14d, [rbx+2]
0x180008cab  test    rcx, rcx
0x180008cae  jz      loc_180008DB2
0x180008cb4  movups  xmmword ptr [rsp+2A8h+Handle], xmm6
0x180008cbc  mov     dword ptr [rsp+2A8h+var_188], 30h ; '0'
0x180008cc7  mov     [r11-180h], rbx
0x180008cce  mov     dword ptr [rsp+2A8h+var_178+8], 200h
0x180008cd9  mov     [r11-178h], rbx
0x180008ce0  xorps   xmm0, xmm0
0x180008ce3  movdqu  [rsp+2A8h+var_168], xmm0
0x180008cec  mov     [rsp+2A8h+FileHandle], rcx; FileHandle
0x180008cf1  mov     [rsp+2A8h+AllocationAttributes], 8000000h; AllocationAttributes
0x180008cf9  mov     [rsp+2A8h+SectionPageProtection], r14d; SectionPageProtection
0x180008cfe  xor     r9d, r9d; MaximumSize
0x180008d01  lea     r8, [r11-188h]; ObjectAttributes
0x180008d08  lea     edx, [rbx+5]; DesiredAccess
0x180008d0b  lea     rcx, [rsp+2A8h+SectionHandle]; SectionHandle
0x180008d10  call    cs:__imp_NtCreateSection
0x180008d16  mov     edi, eax
0x180008d18  test    eax, eax
0x180008d1a  js      short loc_180008D7E
0x180008d1c  mov     [rsp+2A8h+AccessProtection], r14d; AccessProtection
0x180008d21  mov     [rsp+2A8h+AllocationType], ebx; AllocationType
0x180008d25  mov     [rsp+2A8h+InheritDisposition], r14d; InheritDisposition
0x180008d2a  lea     rax, [rsp+2A8h+ViewSize]
0x180008d32  mov     [rsp+2A8h+FileHandle], rax; ViewSize
0x180008d37  mov     qword ptr [rsp+2A8h+AllocationAttributes], rbx; SectionOffset
0x180008d3c  mov     qword ptr [rsp+2A8h+SectionPageProtection], rbx; CommitSize
0x180008d41  xor     r9d, r9d; ZeroBits
0x180008d44  lea     r8, [rsp+2A8h+SectionHandle+8]; BaseAddress
0x180008d49  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180008d4d  mov     rcx, [rsp+2A8h+SectionHandle]; SectionHandle
0x180008d52  call    cs:__imp_NtMapViewOfSection
0x180008d58  mov     edi, eax
0x180008d5a  test    eax, eax
0x180008d5c  js      short loc_180008D7E
0x180008d5e  movdqu  xmm6, xmmword ptr [rsp+2A8h+SectionHandle]
0x180008d64  movups  xmmword ptr [rsp+2A8h+Handle], xmm6
0x180008d6c  xorps   xmm1, xmm1
0x180008d6f  xor     eax, eax
0x180008d71  movups  xmmword ptr [rsp+2A8h+SectionHandle], xmm1
0x180008d76  mov     [rsp+2A8h+ViewSize], rax
0x180008d7e  test    edi, edi
0x180008d80  jns     short loc_180008DAB
0x180008d82  mov     rdx, [rsp+2A8h+SectionHandle+8]; BaseAddress
0x180008d87  test    rdx, rdx
0x180008d8a  jz      short loc_180008D9B
0x180008d8c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180008d90  call    cs:__imp_NtUnmapViewOfSection
0x180008d96  mov     [rsp+2A8h+SectionHandle+8], rbx
0x180008d9b  mov     rcx, [rsp+2A8h+SectionHandle]; Handle
0x180008da0  test    rcx, rcx
0x180008da3  jz      short loc_180008DAB
0x180008da5  call    cs:__imp_NtClose
0x180008dab  mov     esi, 0C000000Dh
0x180008db0  jmp     short loc_180008DB9
0x180008db2  mov     esi, 0C000000Dh
0x180008db7  mov     edi, esi
0x180008db9  test    edi, edi
0x180008dbb  js      loc_1800091CA
0x180008dc1  mov     qword ptr [rsp+2A8h+InheritDisposition], rbx
0x180008dc6  mov     [rsp+2A8h+FileHandle], rbx
0x180008dcb  lea     rax, [rsp+2A8h+var_218]
0x180008dd3  mov     qword ptr [rsp+2A8h+AllocationAttributes], rax
0x180008dd8  lea     rax, [rsp+2A8h+var_210]
0x180008de0  mov     qword ptr [rsp+2A8h+SectionPageProtection], rax
0x180008de5  mov     r9d, 1210h
0x180008deb  mov     r8d, 3
0x180008df1  lea     rdx, qword_18000CA38
0x180008df8  psrldq  xmm6, 8
0x180008dfd  movq    r12, xmm6
0x180008e02  mov     rcx, r12
0x180008e05  call    cs:__imp_LdrResSearchResource
0x180008e0b  mov     [rsp+2A8h+var_258], eax
0x180008e0f  test    eax, eax
0x180008e11  js      loc_1800091AF
0x180008e17  cmp     [rsp+2A8h+var_218], 5Ch ; '\'
0x180008e20  jb      loc_1800091AF
0x180008e26  mov     rcx, [rsp+2A8h+var_210]
0x180008e2e  movzx   eax, word ptr [rcx]
0x180008e31  cmp     rax, [rsp+2A8h+var_218]
0x180008e39  ja      loc_1800091AF
0x180008e3f  cmp     dword ptr [rcx+28h], 0FEEF04BDh
0x180008e46  jnz     loc_1800091AF
0x180008e4c  mov     eax, [rcx+30h]
0x180008e4f  mov     [r15], eax
0x180008e52  mov     eax, [rcx+34h]
0x180008e55  mov     [r13+0], eax
0x180008e59  mov     eax, [rcx+38h]
0x180008e5c  mov     rdx, [rsp+2A8h+var_240]
0x180008e61  mov     [rdx], eax
0x180008e63  mov     eax, [rcx+3Ch]
0x180008e66  mov     rdx, [rsp+2A8h+var_208]
0x180008e6e  mov     [rdx], eax
0x180008e70  lea     r9, [rsp+2A8h+var_250]
0x180008e75  lea     r8, [rsp+2A8h+var_248]
0x180008e7a  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x180008e81  call    AipQueryValue
0x180008e86  mov     edi, eax
0x180008e88  mov     [rsp+2A8h+var_258], eax
0x180008e8c  test    eax, eax
0x180008e8e  js      loc_1800091B8
0x180008e94  cmp     [rsp+2A8h+var_250], 4
0x180008e9a  jb      loc_1800091AF
0x180008ea0  mov     rcx, [rsp+2A8h+var_248]
0x180008ea5  test    cl, 1
0x180008ea8  jnz     loc_1800091AF
0x180008eae  movzx   eax, word ptr [rcx+2]
0x180008eb2  movzx   r9d, word ptr [rcx]
0x180008eb6  mov     [rsp+2A8h+SectionPageProtection], eax
0x180008eba  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\"
0x180008ec1  mov     edx, 100h
0x180008ec6  lea     rcx, [rsp+2A8h+var_158]
0x180008ece  call    RtlStringCbPrintfW
0x180008ed3  lea     rcx, [rsp+2A8h+var_158]
0x180008edb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008edf  inc     rax
0x180008ee2  mov     [rsp+2A8h+var_208], rax
0x180008eea  cmp     [rcx+rax*2], bx
0x180008eee  jnz     short loc_180008EDF
0x180008ef0  mov     r15d, ebx
0x180008ef3  mov     [rsp+2A8h+var_220], ebx
0x180008efa  mov     r10d, 80h
0x180008f00  cmp     r15d, r14d
0x180008f03  jnb     loc_1800091B8
0x180008f09  mov     eax, eax
0x180008f0b  add     rax, rax
0x180008f0e  cmp     rax, 100h
0x180008f14  jnb     loc_180009224
0x180008f1a  mov     [rsp+rax+2A8h+var_158], bx
0x180008f22  mov     eax, r15d
0x180008f25  lea     r9, off_18000B3D0; "OriginalFileName"
0x180008f2c  mov     r9, [r9+rax*8]
0x180008f30  mov     [rsp+2A8h+var_248], rbx
0x180008f35  lea     r8, [rsp+2A8h+var_248]
0x180008f3a  mov     ecx, r10d
0x180008f3d  mov     [rsp+2A8h+var_1C8], rcx
0x180008f45  lea     rax, [rsp+2A8h+var_158]
0x180008f4d  mov     [rsp+2A8h+var_1D0], rax
0x180008f55  test    rcx, rcx
0x180008f58  jz      short loc_180008F77
0x180008f5a  cmp     [rax], bx
0x180008f5d  jz      short loc_180008F77
0x180008f5f  add     rax, r14
0x180008f62  mov     [rsp+2A8h+var_1D0], rax
0x180008f6a  dec     rcx
0x180008f6d  mov     [rsp+2A8h+var_1C8], rcx
0x180008f75  jmp     short loc_180008F55
0x180008f77  mov     edx, ebx
0x180008f79  test    rcx, rcx
0x180008f7c  cmovz   edx, esi
0x180008f7f  test    edx, edx
0x180008f81  js      short loc_180008F8E
0x180008f83  mov     rax, r10
0x180008f86  sub     rax, rcx
0x180008f89  mov     [r8], rax
0x180008f8c  jmp     short loc_180008F91
0x180008f8e  mov     [r8], rbx
0x180008f91  test    edx, edx
0x180008f93  js      loc_180009050
0x180008f99  mov     r8d, 7FFFFFFEh
0x180008f9f  mov     [rsp+2A8h+var_1B0], r8
0x180008fa7  mov     [rsp+2A8h+var_1C0], r9
0x180008faf  mov     rdx, r10
0x180008fb2  mov     rax, [rsp+2A8h+var_248]
0x180008fb7  sub     rdx, rax
0x180008fba  mov     [rsp+2A8h+var_1B8], rdx
0x180008fc2  lea     rcx, [rsp+2A8h+var_158]
0x180008fca  lea     rcx, [rcx+rax*2]
0x180008fce  mov     [rsp+2A8h+var_200], rcx
0x180008fd6  mov     rax, rbx
0x180008fd9  mov     [rsp+2A8h+var_1F8], rbx
0x180008fe1  test    rdx, rdx
0x180008fe4  jz      short loc_180009037
0x180008fe6  test    r8, r8
0x180008fe9  jz      short loc_180009032
0x180008feb  movzx   r10d, word ptr [r9]
0x180008fef  test    r10w, r10w
0x180008ff3  jz      short loc_180009032
0x180008ff5  mov     [rcx], r10w
0x180008ff9  add     rcx, r14
0x180008ffc  mov     [rsp+2A8h+var_200], rcx
0x180009004  add     r9, r14
0x180009007  mov     [rsp+2A8h+var_1C0], r9
0x18000900f  dec     rdx
0x180009012  mov     [rsp+2A8h+var_1B8], rdx
0x18000901a  dec     r8
0x18000901d  mov     [rsp+2A8h+var_1B0], r8
0x180009025  inc     rax
0x180009028  mov     [rsp+2A8h+var_1F8], rax
0x180009030  jmp     short loc_180008FE1
0x180009032  test    rdx, rdx
0x180009035  jnz     short loc_18000904D
0x180009037  sub     rcx, r14
0x18000903a  mov     [rsp+2A8h+var_200], rcx
0x180009042  dec     rax
0x180009045  mov     [rsp+2A8h+var_1F8], rax
0x18000904d  mov     [rcx], bx
0x180009050  lea     r9, [rsp+2A8h+var_250]
0x180009055  lea     r8, [rsp+2A8h+Src]
0x18000905d  lea     rdx, [rsp+2A8h+var_158]
0x180009065  mov     rcx, [rsp+2A8h+var_210]
0x18000906d  call    AipQueryValue
0x180009072  mov     [rsp+2A8h+var_258], eax
0x180009076  test    eax, eax
0x180009078  js      loc_18000918C
0x18000907e  mov     rcx, [rsp+2A8h+var_250]
0x180009083  lea     rax, [rcx-1]
0x180009087  cmp     rax, 0FFFEh
0x18000908d  ja      loc_18000918C
0x180009093  lea     r9, [rsp+2A8h+var_250]
0x180009098  mov     r13, [rsp+2A8h+Src]
0x1800090a0  lea     rax, [rcx+rcx]
0x1800090a4  shr     rax, 1
0x1800090a7  mov     rcx, rbx
0x1800090aa  mov     [rsp+2A8h+var_240], rbx
0x1800090af  test    r13, r13
0x1800090b2  jz      short loc_180009117
0x1800090b4  cmp     rax, 7FFFFFFFh
0x1800090ba  ja      short loc_180009117
0x1800090bc  lea     r8, [rsp+2A8h+var_240]
0x1800090c1  mov     [rsp+2A8h+var_1A0], rax
0x1800090c9  mov     rcx, r13
0x1800090cc  mov     [rsp+2A8h+var_1A8], rcx
0x1800090d4  mov     edi, ebx
0x1800090d6  mov     rdx, rax
0x1800090d9  test    rax, rax
0x1800090dc  jz      short loc_1800090FE
0x1800090de  cmp     [rcx], bx
0x1800090e1  jz      short loc_1800090FB
0x1800090e3  add     rcx, r14
0x1800090e6  mov     [rsp+2A8h+var_1A8], rcx
0x1800090ee  dec     rax
0x1800090f1  mov     [rsp+2A8h+var_1A0], rax
0x1800090f9  jmp     short loc_1800090D9
0x1800090fb  test    rax, rax
0x1800090fe  cmovz   edi, esi
0x180009101  test    edi, edi
0x180009103  js      short loc_18000910D
0x180009105  sub     rdx, rax
0x180009108  mov     [r8], rdx
0x18000910b  jmp     short loc_180009110
0x18000910d  mov     [r8], rbx
0x180009110  mov     rcx, [rsp+2A8h+var_240]
0x180009115  jmp     short loc_180009119
0x180009117  mov     edi, esi
0x180009119  test    edi, edi
0x18000911b  js      short loc_180009126
0x18000911d  lea     rax, [rcx+rcx]
0x180009121  mov     [r9], rax
0x180009124  jmp     short loc_180009129
0x180009126  mov     [r9], rbx
0x180009129  mov     [rsp+2A8h+var_258], edi
0x18000912d  test    edi, edi
0x18000912f  js      short loc_180009184
0x180009131  mov     rsi, [rsp+2A8h+var_250]
0x180009136  test    rsi, rsi
0x180009139  jz      short loc_180009184
0x18000913b  add     rsi, r14
0x18000913e  mov     [rsp+2A8h+var_250], rsi
0x180009143  mov     rcx, rsi
  ... truncated ...
```
