# _wsopen_nolock

- ea: `0x1400766e0`
- end: `0x140076af3`
- name: `_wsopen_nolock`
- size: `1043`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140075f74`
- `0x140076590`

## callees

- `0x14005af8c`
- `0x14005afd8`
- `0x14005affc`
- `0x14007025c`
- `0x140073c18`
- `0x140073d00`
- `0x140073e40`
- `0x140076038`
- `0x1400762b8`
- `0x1400764cc`
- `0x1400766e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400767f6`
- `KERNEL32!CreateFileW` at `0x140076854`
- `KERNEL32!CreateFileW` at `0x140076a74`
- `KERNEL32!CreateFileW` at `0x1400767f6`
- `KERNEL32!CreateFileW` at `0x140076854`
- `KERNEL32!CreateFileW` at `0x140076a74`
- `KERNEL32!CloseHandle` at `0x1400768d9`
- `KERNEL32!CloseHandle` at `0x140076a3f`
- `KERNEL32!CloseHandle` at `0x1400768d9`
- `KERNEL32!CloseHandle` at `0x140076a3f`
- `KERNEL32!GetLastError` at `0x140076884`
- `KERNEL32!GetLastError` at `0x1400768a6`
- `KERNEL32!GetLastError` at `0x140076a83`
- `KERNEL32!GetLastError` at `0x140076884`
- `KERNEL32!GetLastError` at `0x1400768a6`
- `KERNEL32!GetLastError` at `0x140076a83`
- `KERNEL32!GetFileType` at `0x14007689c`
- `KERNEL32!GetFileType` at `0x14007689c`

## pseudocode

```c
__int64 __fastcall wsopen_nolock(
        _DWORD *a1,
        unsigned int *a2,
        const WCHAR *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v10; // rax
  __m128i v11; // xmm0
  __int64 v12; // r14
  unsigned int v14; // eax
  __m128i v15; // xmm0
  int v16; // r15^4
  __int64 dwFlagsAndAttributes; // r15
  HANDLE v18; // r13
  int v19; // ebx
  DWORD v20; // ebx
  DWORD LastError; // eax
  DWORD FileType; // eax
  __int64 v23; // rbx
  __int8 v24; // r14
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  HANDLE v32; // rdx
  DWORD v33; // eax
  char v34[4]; // [rsp+48h] [rbp-81h] BYREF
  DWORD dwCreationDisposition; // [rsp+4Ch] [rbp-7Dh]
  __m128i v36; // [rsp+50h] [rbp-79h]
  __int64 v37; // [rsp+60h] [rbp-69h]
  char v38; // [rsp+68h] [rbp-61h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-59h] BYREF
  __int64 v40; // [rsp+88h] [rbp-41h]
  DWORD v41[2]; // [rsp+90h] [rbp-39h]
  DWORD dwShareMode[4]; // [rsp+98h] [rbp-31h]
  __m128i v43; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-11h]
  char v45[32]; // [rsp+C8h] [rbp-1h] BYREF

  v10 = decode_options(v45, a4, a5, a6);
  v11 = *(__m128i *)v10;
  v12 = HIDWORD(*(_QWORD *)(v10 + 8));
  v40 = *(_QWORD *)(v10 + 16);
  v37 = v40;
  *(_QWORD *)dwShareMode = v12;
  v43 = v11;
  v36 = v11;
  if ( (_DWORD)v12 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    return (unsigned int)*errno();
  }
  v14 = alloc_osfhnd();
  *a2 = v14;
  if ( v14 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    *errno() = 24;
    return (unsigned int)*errno();
  }
  v15 = v43;
  v16 = HIDWORD(v37);
  *a1 = 1;
  dwFlagsAndAttributes = (unsigned int)v37 | v16;
  SecurityAttributes.bInheritHandle = (a4 & 0x80) == 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)v41 = dwFlagsAndAttributes;
  dwCreationDisposition = _mm_cvtsi128_si32(_mm_srli_si128(v15, 8));
  v18 = CreateFileW(a3, v15.m128i_u32[1], v12, &SecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( v18 == (HANDLE)-1LL )
  {
    v19 = _mm_cvtsi128_si32(_mm_srli_si128(v43, 4));
    if ( (v19 & 0xC0000000) != 0xC0000000
      || (a4 & 1) == 0
      || (v20 = v19 & 0x7FFFFFFF,
          v36.m128i_i32[1] = v20,
          v18 = CreateFileW(a3, v20, v12, &SecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, 0),
          v18 == (HANDLE)-1LL) )
    {
      *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
      LastError = GetLastError();
      _acrt_errno_map_os_error(LastError);
      return (unsigned int)*errno();
    }
  }
  else
  {
    v20 = v36.m128i_u32[1];
  }
  FileType = GetFileType(v18);
  if ( !FileType )
  {
    v23 = GetLastError();
    _acrt_errno_map_os_error(v23);
    *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
    CloseHandle(v18);
    if ( !(_DWORD)v23 )
      *errno() = 13;
    return (unsigned int)*errno();
  }
  v24 = v36.m128i_i8[0];
  if ( FileType == 2 )
  {
    v24 = v36.m128i_i8[0] | 0x40;
  }
  else if ( FileType == 3 )
  {
    v24 = v36.m128i_i8[0] | 8;
  }
  _acrt_lowio_set_os_handle(*a2, v18);
  v25 = (__int64)(int)*a2 >> 6;
  v26 = *a2 & 0x3F;
  v38 = v24 | 1;
  v36.m128i_i8[0] = v24 | 1;
  *(_BYTE *)(_pioinfo[v25] + 72 * v26 + 56) = v24 | 1;
  *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 57) = 0;
  if ( (a4 & 2) != 0 )
  {
    v27 = truncate_ctrl_z_if_present(*a2);
    if ( v27 )
    {
      v28 = *a2;
LABEL_22:
      close_nolock(v28);
      return v27;
    }
  }
  v29 = *a2;
  v43 = v36;
  v34[0] = 0;
  v44 = v40;
  v27 = configure_text_mode(v29, &v43, a4, v34);
  v30 = (int)*a2;
  if ( v27 )
  {
    v28 = (unsigned int)v30;
    goto LABEL_22;
  }
  *(_BYTE *)(_pioinfo[v30 >> 6] + 72 * (v30 & 0x3F) + 57) = v34[0];
  v31 = (int)*a2;
  *(_BYTE *)(_pioinfo[v31 >> 6] + 72 * (v31 & 0x3F) + 61) ^= (*(_BYTE *)(_pioinfo[v31 >> 6] + 72 * (v31 & 0x3F) + 61)
                                                            ^ BYTE2(a4))
                                                           & 1;
  if ( (v38 & 0x48) == 0 && (a4 & 8) != 0 )
    *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) |= 0x20u;
  if ( (v20 & 0xC0000000) == 0xC0000000 && (a4 & 1) != 0 )
  {
    CloseHandle(v18);
    v36.m128i_i32[1] = v20 & 0x7FFFFFFF;
    v32 = CreateFileW(a3, v20 & 0x7FFFFFFF, dwShareMode[0], &SecurityAttributes, dwCreationDisposition, v41[0], 0);
    if ( v32 == (HANDLE)-1LL )
    {
      v33 = GetLastError();
      _acrt_errno_map_os_error(v33);
      *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
      free_osfhnd(*a2);
      return (unsigned int)*errno();
    }
    *(_QWORD *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 40) = v32;
  }
  return 0;
}

```

## disassembly

```asm
0x1400766e0  mov     rax, rsp
0x1400766e3  mov     [rax+8], rbx
0x1400766e7  mov     [rax+10h], rsi
0x1400766eb  mov     [rax+20h], rdi
0x1400766ef  mov     [rax+18h], r8
0x1400766f3  push    rbp
0x1400766f4  push    r12
0x1400766f6  push    r13
0x1400766f8  push    r14
0x1400766fa  push    r15
0x1400766fc  lea     rbp, [rax-47h]
0x140076700  sub     rsp, 0E0h
0x140076707  mov     r12d, r9d
0x14007670a  mov     rbx, r8
0x14007670d  mov     r9d, [rbp+3Fh+arg_28]
0x140076711  mov     rdi, rdx
0x140076714  mov     r8d, [rbp+3Fh+arg_20]
0x140076718  mov     rsi, rcx
0x14007671b  mov     edx, r12d
0x14007671e  lea     rcx, [rbp+3Fh+var_40]
0x140076722  call    decode_options
0x140076727  movups  xmm0, xmmword ptr [rax]
0x14007672a  mov     r14, [rax+8]
0x14007672e  movsd   xmm1, qword ptr [rax+10h]
0x140076733  shr     r14, 20h
0x140076737  movsd   [rbp+3Fh+var_80], xmm1
0x14007673c  movsd   [rbp+3Fh+var_A8], xmm1
0x140076741  mov     qword ptr [rbp+3Fh+dwShareMode], r14
0x140076745  movups  [rbp+3Fh+var_60], xmm0
0x140076749  movups  [rbp+3Fh+var_B8], xmm0
0x14007674d  cmp     r14d, 0FFFFFFFFh
0x140076751  jnz     short loc_14007676B
0x140076753  call    __doserrno
0x140076758  xor     esi, esi
0x14007675a  mov     [rax], esi
0x14007675c  or      dword ptr [rdi], 0FFFFFFFFh
0x14007675f  call    _errno
0x140076764  mov     eax, [rax]
0x140076766  jmp     loc_140076AD2
0x14007676b  call    _alloc_osfhnd
0x140076770  mov     [rdi], eax
0x140076772  cmp     eax, 0FFFFFFFFh
0x140076775  jnz     short loc_140076790
0x140076777  call    __doserrno
0x14007677c  xor     esi, esi
0x14007677e  mov     [rax], esi
0x140076780  or      dword ptr [rdi], 0FFFFFFFFh
0x140076783  call    _errno
0x140076788  mov     dword ptr [rax], 18h
0x14007678e  jmp     short loc_14007675F
0x140076790  movups  xmm0, [rbp+3Fh+var_60]
0x140076794  mov     r15, [rbp+3Fh+var_A8]
0x140076798  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x14007679c  mov     eax, r12d
0x14007679f  mov     dword ptr [rsi], 1
0x1400767a5  shr     eax, 7
0x1400767a8  xor     esi, esi
0x1400767aa  movq    rdx, xmm0
0x1400767af  shr     r15, 20h
0x1400767b3  or      r15d, dword ptr [rbp+3Fh+var_A8]
0x1400767b7  not     eax
0x1400767b9  psrldq  xmm0, 8
0x1400767be  and     eax, 1
0x1400767c1  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x1400767c6  mov     r8d, r14d; dwShareMode
0x1400767c9  shr     rdx, 20h; dwDesiredAccess
0x1400767cd  mov     rcx, rbx; lpFileName
0x1400767d0  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1400767d5  mov     [rbp+3Fh+SecurityAttributes.bInheritHandle], eax
0x1400767d8  mov     qword ptr [rbp+3Fh+SecurityAttributes.nLength], 18h
0x1400767e0  mov     dword ptr [rbp+3Fh+SecurityAttributes+14h], esi
0x1400767e3  mov     [rbp+3Fh+SecurityAttributes.lpSecurityDescriptor], rsi
0x1400767e7  mov     qword ptr [rbp+3Fh+var_78], r15
0x1400767eb  movd    [rbp+3Fh+var_BC], xmm0
0x1400767f0  movd    [rsp+100h+dwCreationDisposition], xmm0; dwCreationDisposition
0x1400767f6  call    cs:__imp_CreateFileW
0x1400767fc  mov     r13, rax
0x1400767ff  mov     ecx, 0C0000000h
0x140076804  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140076808  jnz     loc_140076896
0x14007680e  movups  xmm0, [rbp+3Fh+var_60]
0x140076812  psrldq  xmm0, 4
0x140076817  movd    ebx, xmm0
0x14007681b  mov     eax, ebx
0x14007681d  and     eax, ecx
0x14007681f  cmp     eax, ecx
0x140076821  jnz     short loc_140076863
0x140076823  test    r12b, 1
0x140076827  jz      short loc_140076863
0x140076829  mov     eax, [rbp+3Fh+var_BC]
0x14007682c  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x140076830  mov     rcx, [rbp+3Fh+lpFileName]; lpFileName
0x140076834  btr     ebx, 1Fh
0x140076838  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x14007683d  mov     r8d, r14d; dwShareMode
0x140076840  mov     dword ptr [rbp+3Fh+var_B8+4], ebx
0x140076843  mov     rdx, qword ptr [rbp+3Fh+var_B8]
0x140076847  shr     rdx, 20h; dwDesiredAccess
0x14007684b  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x140076850  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x140076854  call    cs:__imp_CreateFileW
0x14007685a  mov     r13, rax
0x14007685d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140076861  jnz     short loc_140076899
0x140076863  movsxd  rcx, dword ptr [rdi]
0x140076866  lea     r15, __pioinfo
0x14007686d  mov     rax, rcx
0x140076870  and     ecx, 3Fh
0x140076873  sar     rax, 6
0x140076877  lea     rcx, [rcx+rcx*8]
0x14007687b  mov     rax, [r15+rax*8]
0x14007687f  and     byte ptr [rax+rcx*8+38h], 0FEh
0x140076884  call    cs:__imp_GetLastError
0x14007688a  mov     ecx, eax
0x14007688c  call    __acrt_errno_map_os_error
0x140076891  jmp     loc_14007675F
0x140076896  mov     ebx, dword ptr [rbp+3Fh+var_B8+4]
0x140076899  mov     rcx, r13; hFile
0x14007689c  call    cs:__imp_GetFileType
0x1400768a2  test    eax, eax
0x1400768a4  jnz     short loc_1400768F7
0x1400768a6  call    cs:__imp_GetLastError
0x1400768ac  mov     ecx, eax
0x1400768ae  mov     ebx, eax
0x1400768b0  call    __acrt_errno_map_os_error
0x1400768b5  movsxd  rdx, dword ptr [rdi]
0x1400768b8  lea     r15, __pioinfo
0x1400768bf  mov     rcx, rdx
0x1400768c2  and     edx, 3Fh
0x1400768c5  sar     rcx, 6
0x1400768c9  lea     rdx, [rdx+rdx*8]
0x1400768cd  mov     rcx, [r15+rcx*8]
0x1400768d1  and     byte ptr [rcx+rdx*8+38h], 0FEh
0x1400768d6  mov     rcx, r13; hObject
0x1400768d9  call    cs:__imp_CloseHandle
0x1400768df  test    ebx, ebx
0x1400768e1  jnz     loc_14007675F
0x1400768e7  call    _errno
0x1400768ec  mov     dword ptr [rax], 0Dh
0x1400768f2  jmp     loc_14007675F
0x1400768f7  mov     r14b, byte ptr [rbp+3Fh+var_B8]
0x1400768fb  cmp     eax, 2
0x1400768fe  jnz     short loc_140076906
0x140076900  or      r14b, 40h
0x140076904  jmp     short loc_14007690F
0x140076906  cmp     eax, 3
0x140076909  jnz     short loc_14007690F
0x14007690b  or      r14b, 8
0x14007690f  mov     ecx, [rdi]
0x140076911  mov     rdx, r13
0x140076914  call    __acrt_lowio_set_os_handle
0x140076919  movsxd  rcx, dword ptr [rdi]
0x14007691c  lea     r15, __pioinfo
0x140076923  mov     rax, rcx
0x140076926  or      r14b, 1
0x14007692a  sar     rax, 6
0x14007692e  and     ecx, 3Fh
0x140076931  mov     [rbp+3Fh+var_A0], r14b
0x140076935  mov     byte ptr [rbp+3Fh+var_B8], r14b
0x140076939  mov     rax, [r15+rax*8]
0x14007693d  lea     rcx, [rcx+rcx*8]
0x140076941  mov     [rax+rcx*8+38h], r14b
0x140076946  movsxd  rcx, dword ptr [rdi]
0x140076949  mov     rax, rcx
0x14007694c  and     ecx, 3Fh
0x14007694f  sar     rax, 6
0x140076953  lea     rcx, [rcx+rcx*8]
0x140076957  mov     rax, [r15+rax*8]
0x14007695b  mov     [rax+rcx*8+39h], sil
0x140076960  test    r12b, 2
0x140076964  jz      short loc_140076983
0x140076966  mov     ecx, [rdi]
0x140076968  call    truncate_ctrl_z_if_present
0x14007696d  mov     r14d, eax
0x140076970  test    eax, eax
0x140076972  jz      short loc_140076983
0x140076974  mov     ecx, [rdi]
0x140076976  call    _close_nolock
0x14007697b  mov     eax, r14d
0x14007697e  jmp     loc_140076AD2
0x140076983  movups  xmm0, [rbp+3Fh+var_B8]
0x140076987  lea     r9, [rsp+100h+var_C0]
0x14007698c  mov     ecx, [rdi]
0x14007698e  movsd   xmm1, [rbp+3Fh+var_80]
0x140076993  lea     rdx, [rbp+3Fh+var_60]
0x140076997  mov     r8d, r12d
0x14007699a  movaps  [rbp+3Fh+var_60], xmm0
0x14007699e  mov     [rsp+100h+var_C0], sil
0x1400769a3  movsd   [rbp+3Fh+var_50], xmm1
0x1400769a8  call    configure_text_mode
0x1400769ad  mov     r14d, eax
0x1400769b0  movsxd  rax, dword ptr [rdi]
0x1400769b3  test    r14d, r14d
0x1400769b6  jz      short loc_1400769BC
0x1400769b8  mov     ecx, eax
0x1400769ba  jmp     short loc_140076976
0x1400769bc  mov     rcx, rax
0x1400769bf  and     eax, 3Fh
0x1400769c2  sar     rcx, 6
0x1400769c6  lea     rdx, [rax+rax*8]
0x1400769ca  mov     al, [rsp+100h+var_C0]
0x1400769ce  mov     rcx, [r15+rcx*8]
0x1400769d2  mov     [rcx+rdx*8+39h], al
0x1400769d6  movsxd  rcx, dword ptr [rdi]
0x1400769d9  mov     rax, rcx
0x1400769dc  and     ecx, 3Fh
0x1400769df  sar     rax, 6
0x1400769e3  lea     rdx, [rcx+rcx*8]
0x1400769e7  mov     rcx, [r15+rax*8]
0x1400769eb  mov     eax, r12d
0x1400769ee  shr     eax, 10h
0x1400769f1  xor     al, [rcx+rdx*8+3Dh]
0x1400769f5  and     al, 1
0x1400769f7  xor     [rcx+rdx*8+3Dh], al
0x1400769fb  test    [rbp+3Fh+var_A0], 48h
0x1400769ff  jnz     short loc_140076A21
0x140076a01  test    r12b, 8
0x140076a05  jz      short loc_140076A21
0x140076a07  movsxd  rcx, dword ptr [rdi]
0x140076a0a  mov     rax, rcx
0x140076a0d  and     ecx, 3Fh
0x140076a10  sar     rax, 6
0x140076a14  lea     rcx, [rcx+rcx*8]
0x140076a18  mov     rax, [r15+rax*8]
0x140076a1c  or      byte ptr [rax+rcx*8+38h], 20h
0x140076a21  mov     ecx, 0C0000000h
0x140076a26  mov     eax, ebx
0x140076a28  and     eax, ecx
0x140076a2a  cmp     eax, ecx
0x140076a2c  jnz     loc_140076AD0
0x140076a32  test    r12b, 1
0x140076a36  jz      loc_140076AD0
0x140076a3c  mov     rcx, r13; hObject
0x140076a3f  call    cs:__imp_CloseHandle
0x140076a45  mov     rax, qword ptr [rbp+3Fh+var_78]
0x140076a49  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x140076a4d  mov     r8d, [rbp+3Fh+dwShareMode]; dwShareMode
0x140076a51  btr     ebx, 1Fh
0x140076a55  mov     rcx, [rbp+3Fh+lpFileName]; lpFileName
0x140076a59  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x140076a5e  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140076a62  mov     eax, [rbp+3Fh+var_BC]
0x140076a65  mov     dword ptr [rbp+3Fh+var_B8+4], ebx
0x140076a68  mov     rdx, qword ptr [rbp+3Fh+var_B8]
0x140076a6c  shr     rdx, 20h; dwDesiredAccess
0x140076a70  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x140076a74  call    cs:__imp_CreateFileW
0x140076a7a  mov     rdx, rax
0x140076a7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140076a81  jnz     short loc_140076AB6
0x140076a83  call    cs:__imp_GetLastError
0x140076a89  mov     ecx, eax
0x140076a8b  call    __acrt_errno_map_os_error
0x140076a90  movsxd  rcx, dword ptr [rdi]
0x140076a93  mov     rax, rcx
0x140076a96  and     ecx, 3Fh
0x140076a99  sar     rax, 6
0x140076a9d  lea     rcx, [rcx+rcx*8]
0x140076aa1  mov     rax, [r15+rax*8]
0x140076aa5  and     byte ptr [rax+rcx*8+38h], 0FEh
0x140076aaa  mov     ecx, [rdi]
0x140076aac  call    _free_osfhnd
0x140076ab1  jmp     loc_14007675F
0x140076ab6  movsxd  rcx, dword ptr [rdi]
0x140076ab9  mov     rax, rcx
0x140076abc  sar     rax, 6
0x140076ac0  and     ecx, 3Fh
0x140076ac3  mov     rax, [r15+rax*8]
0x140076ac7  lea     rcx, [rcx+rcx*8]
0x140076acb  mov     [rax+rcx*8+28h], rdx
0x140076ad0  xor     eax, eax
0x140076ad2  lea     r11, [rsp+100h+var_20]
0x140076ada  mov     rbx, [r11+30h]
0x140076ade  mov     rsi, [r11+38h]
0x140076ae2  mov     rdi, [r11+48h]
0x140076ae6  mov     rsp, r11
0x140076ae9  pop     r15
0x140076aeb  pop     r14
0x140076aed  pop     r13
0x140076aef  pop     r12
0x140076af1  pop     rbp
0x140076af2  retn
```
