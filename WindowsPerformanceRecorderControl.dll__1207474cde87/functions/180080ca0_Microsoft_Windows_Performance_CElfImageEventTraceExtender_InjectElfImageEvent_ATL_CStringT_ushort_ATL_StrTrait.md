# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180080ca0`
- end: `0x180081081`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `993`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180030904`
- `0x18004ece0`
- `0x18004f964`
- `0x1800804fc`
- `0x180080c70`
- `0x180080ca0`
- `0x180082d30`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180080e04`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180080e04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008105a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081074`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008105a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081074`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180080d3e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180080ee3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180080d3e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180080ee3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180080cfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180080cfa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180080eb9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180080eb9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180080e17`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180080e17`
- `bcrypt!BCryptFinishHash` at `0x180080f73`
- `bcrypt!BCryptFinishHash` at `0x180080f73`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HANDLE FileW; // rsi
  LPCWSTR v10; // rax
  int v11; // ecx
  __int64 v12; // r12
  _QWORD *v13; // r14
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  DWORD FileSize; // eax
  LONG v17; // r8d
  LONG v18; // r15d
  unsigned __int16 v19; // dx
  int v20; // ebx
  size_t v22; // r14
  __int64 v23; // rcx
  _BYTE v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int128 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  LONG lDistanceToMove[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v30[16]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+90h] [rbp-70h]
  __int16 v32; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[2]; // [rsp+A2h] [rbp-5Eh] BYREF
  int v34; // [rsp+A4h] [rbp-5Ch]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  int v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F4h] [rbp-Ch]
  unsigned __int8 v40[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v41; // [rsp+110h] [rbp+10h]

  FileW = CreateFileW(*a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  NumberOfBytesRead = 0;
  v31 = 0;
  Buffer = 0;
  *(_OWORD *)lDistanceToMove = 0;
  *(_OWORD *)v30 = 0;
  if ( !ReadFile(FileW, &Buffer, 0x34u, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != 52
    || memcmp_0(&Buffer, &qword_18009E048, 4u)
    || WORD2(Buffer) != 257
    || BYTE6(Buffer) != 1
    || *(_WORD *)&v30[10] != 32 )
  {
LABEL_20:
    CloseHandle(FileW);
    return 2147500037LL;
  }
  v10 = *a2;
  v24[0] = 0;
  v11 = *((_DWORD *)v10 - 4) + 32 * *(unsigned __int16 *)&v30[12];
  v26 = 0;
  v27 = 0;
  std::vector<char>::_Construct_n<char const &>(&v26, (unsigned int)(2 * v11 + 94), v24);
  v12 = v26;
  v13 = (_QWORD *)(v26 + 28);
  v14 = (unsigned __int16)(*(*a2 - 8) + 1);
  v15 = v26 + 28 + ((unsigned __int64)*(unsigned __int16 *)&v30[12] << 6);
  *(_WORD *)(v26 + 26) = v14;
  _o_wcscpy_s(v15, v14, *a2);
  *(_DWORD *)v12 = 0;
  FileSize = GetFileSize(FileW, 0);
  *(_DWORD *)(v12 + 4) = FileSize;
  if ( FileSize == -1 )
    goto LABEL_19;
  *(_WORD *)(v12 + 24) = *(_WORD *)&v30[12];
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)&Buffer,
    0x10u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)lDistanceToMove + 2,
    2u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)&lDistanceToMove[1],
    4u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    &v30[4],
    4u);
  v17 = lDistanceToMove[3];
  v18 = lDistanceToMove[3];
  v19 = *(_WORD *)&v30[10];
  while ( v18 != v17 + v19 * *(unsigned __int16 *)&v30[12] )
  {
    *(_OWORD *)v40 = 0;
    v41 = 0;
    if ( SetFilePointer(FileW, v18, 0, 0) == -1
      || !ReadFile(FileW, v40, 0x20u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 32 )
    {
      v20 = -2147467259;
LABEL_27:
      std::vector<char>::_Tidy(&v26);
      CloseHandle(FileW);
      return (unsigned int)v20;
    }
    *v13 = *(unsigned int *)v40;
    v13[2] = *(unsigned int *)&v40[4];
    v13[3] = *(unsigned int *)&v40[8];
    v13[4] = *(unsigned int *)&v40[12];
    v13[5] = (unsigned int)v41;
    v13[6] = DWORD1(v41);
    v13[1] = DWORD2(v41);
    v13[7] = HIDWORD(v41);
    v13 += 8;
    Microsoft::Windows::Performance::CryptographicHasher::Hash(
      (Microsoft::Windows::Performance::CryptographicHasher *)a3,
      v40,
      0x20u);
    v19 = *(_WORD *)&v30[10];
    v17 = lDistanceToMove[3];
    v18 += *(unsigned __int16 *)&v30[10];
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_19;
  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), *(PUCHAR *)(a3 + 32), *(_DWORD *)(a3 + 40), 0) < 0 )
  {
    *(_BYTE *)a3 = 0;
    goto LABEL_19;
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_19;
  v22 = 16;
  if ( *(_DWORD *)(a3 + 40) <= 0x10u )
    v22 = *(unsigned int *)(a3 + 40);
  memcpy_0((void *)(v12 + 8), *(const void **)(a3 + 32), v22);
  if ( v22 != 16 )
  {
LABEL_19:
    std::vector<char>::_Tidy(&v26);
    goto LABEL_20;
  }
  memset_0(v33, 0, 0x56u);
  v32 = 4;
  v37 = v26;
  v23 = *(_QWORD *)(a1 + 16);
  v38 = DWORD2(v26) - v26;
  v39 = a5;
  v35 = a4;
  v36 = ElfImageGuid;
  v34 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD))(*(_QWORD *)v23 + 192LL))(v23, &v32, 0, 0);
  if ( v20 < 0 )
    goto LABEL_27;
  std::vector<char>::_Tidy(&v26);
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x180080ca0  push    rbp
0x180080ca2  push    rbx
0x180080ca3  push    rsi
0x180080ca4  push    rdi
0x180080ca5  push    r12
0x180080ca7  push    r13
0x180080ca9  push    r14
0x180080cab  push    r15
0x180080cad  lea     rbp, [rsp-38h]
0x180080cb2  sub     rsp, 138h
0x180080cb9  mov     rax, cs:__security_cookie
0x180080cc0  xor     rax, rsp
0x180080cc3  mov     [rbp+70h+var_50], rax
0x180080cc7  mov     r15, rdx
0x180080cca  xor     r14d, r14d
0x180080ccd  mov     rbx, r9
0x180080cd0  mov     [rsp+170h+hTemplateFile], r14; hTemplateFile
0x180080cd5  mov     rdi, r8
0x180080cd8  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180080ce0  mov     r13, rcx
0x180080ce3  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x180080ceb  mov     rcx, [r15]; lpFileName
0x180080cee  lea     r8d, [r14+7]; dwShareMode
0x180080cf2  xor     r9d, r9d; lpSecurityAttributes
0x180080cf5  mov     edx, 80000000h; dwDesiredAccess
0x180080cfa  call    cs:__imp_CreateFileW
0x180080d00  mov     rsi, rax
0x180080d03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180080d07  jz      loc_180080F93
0x180080d0d  xorps   xmm0, xmm0
0x180080d10  mov     [rsp+170h+NumberOfBytesRead], r14d
0x180080d15  xor     eax, eax
0x180080d17  mov     qword ptr [rsp+170h+dwCreationDisposition], r14; lpOverlapped
0x180080d1c  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180080d21  mov     [rbp+70h+var_E0], eax
0x180080d24  lea     r8d, [r14+34h]; nNumberOfBytesToRead
0x180080d28  mov     rcx, rsi; hFile
0x180080d2b  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x180080d30  movups  [rsp+170h+Buffer], xmm0
0x180080d35  movups  xmmword ptr [rsp+170h+lDistanceToMove], xmm0
0x180080d3a  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x180080d3e  call    cs:__imp_ReadFile
0x180080d44  test    eax, eax
0x180080d46  jz      loc_180080F8A
0x180080d4c  cmp     [rsp+170h+NumberOfBytesRead], 34h ; '4'
0x180080d51  jnz     loc_180080F8A
0x180080d57  lea     r8d, [r14+4]; Size
0x180080d5b  lea     rdx, qword_18009E048; Buf2
0x180080d62  lea     rcx, [rsp+170h+Buffer]; Buf1
0x180080d67  call    memcmp_0
0x180080d6c  test    eax, eax
0x180080d6e  jnz     loc_180080F8A
0x180080d74  cmp     byte ptr [rsp+170h+Buffer+4], 1
0x180080d79  jnz     loc_180080F8A
0x180080d7f  cmp     byte ptr [rsp+170h+Buffer+5], 1
0x180080d84  jnz     loc_180080F8A
0x180080d8a  cmp     byte ptr [rsp+170h+Buffer+6], 1
0x180080d8f  jnz     loc_180080F8A
0x180080d95  lea     eax, [r14+20h]
0x180080d99  cmp     ax, word ptr [rbp+70h+var_F0+0Ah]
0x180080d9d  jnz     loc_180080F8A
0x180080da3  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180080da7  lea     r8, [rsp+170h+var_130]
0x180080dac  mov     rax, [r15]
0x180080daf  xorps   xmm0, xmm0
0x180080db2  shl     ecx, 5
0x180080db5  mov     [rsp+170h+var_130], r14b
0x180080dba  add     ecx, [rax-10h]
0x180080dbd  movdqu  [rsp+170h+var_128], xmm0
0x180080dc3  mov     [rsp+170h+var_118], r14
0x180080dc8  lea     edx, ds:5Eh[rcx*2]
0x180080dcf  lea     rcx, [rsp+170h+var_128]
0x180080dd4  call    ??$_Construct_n@AEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBD@Z; std::vector<char>::_Construct_n<char const &>(unsigned __int64,char const &)
0x180080dd9  mov     rax, [r15]
0x180080ddc  mov     r12, qword ptr [rsp+170h+var_128]
0x180080de1  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180080de5  shl     rcx, 6
0x180080de9  movzx   edx, word ptr [rax-10h]
0x180080ded  inc     dx
0x180080df0  lea     r14, [r12+1Ch]
0x180080df5  movzx   edx, dx
0x180080df8  add     rcx, r14
0x180080dfb  mov     [r12+1Ah], dx
0x180080e01  mov     r8, [r15]
0x180080e04  call    cs:__imp__o_wcscpy_s
0x180080e0a  xor     edx, edx; lpFileSizeHigh
0x180080e0c  mov     dword ptr [r12], 0
0x180080e14  mov     rcx, rsi; hFile
0x180080e17  call    cs:__imp_GetFileSize
0x180080e1d  mov     [r12+4], eax
0x180080e22  cmp     eax, 0FFFFFFFFh
0x180080e25  jz      loc_180080F80
0x180080e2b  movzx   eax, word ptr [rbp+70h+var_F0+0Ch]
0x180080e2f  lea     rdx, [rsp+170h+Buffer]; unsigned __int8 *
0x180080e34  mov     r8d, 10h; unsigned int
0x180080e3a  mov     [r12+18h], ax
0x180080e40  mov     rcx, rdi; this
0x180080e43  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180080e48  mov     r8d, 2; unsigned int
0x180080e4e  lea     rdx, [rsp+170h+lDistanceToMove+2]; unsigned __int8 *
0x180080e53  mov     rcx, rdi; this
0x180080e56  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180080e5b  mov     r15d, 4
0x180080e61  lea     rdx, [rsp+170h+lDistanceToMove+4]; unsigned __int8 *
0x180080e66  mov     r8d, r15d; unsigned int
0x180080e69  mov     rcx, rdi; this
0x180080e6c  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180080e71  mov     r8d, r15d; unsigned int
0x180080e74  lea     rdx, [rbp+70h+var_F0+4]; unsigned __int8 *
0x180080e78  mov     rcx, rdi; this
0x180080e7b  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180080e80  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180080e85  mov     r15d, r8d
0x180080e88  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180080e8c  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180080e90  movzx   eax, dx
0x180080e93  imul    ecx, eax
0x180080e96  add     ecx, r8d
0x180080e99  cmp     r15d, ecx
0x180080e9c  jz      loc_180080F5C
0x180080ea2  xorps   xmm0, xmm0
0x180080ea5  xor     r9d, r9d; dwMoveMethod
0x180080ea8  xor     r8d, r8d; lpDistanceToMoveHigh
0x180080eab  mov     edx, r15d; lDistanceToMove
0x180080eae  mov     rcx, rsi; hFile
0x180080eb1  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x180080eb5  movups  [rbp+70h+var_60], xmm0
0x180080eb9  call    cs:__imp_SetFilePointer
0x180080ebf  cmp     eax, 0FFFFFFFFh
0x180080ec2  jz      loc_180080F52
0x180080ec8  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180080ecd  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x180080ed6  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x180080edc  lea     rdx, [rbp+70h+var_70]; lpBuffer
0x180080ee0  mov     rcx, rsi; hFile
0x180080ee3  call    cs:__imp_ReadFile
0x180080ee9  test    eax, eax
0x180080eeb  jz      short loc_180080F52
0x180080eed  cmp     [rsp+170h+NumberOfBytesRead], 20h ; ' '
0x180080ef2  jnz     short loc_180080F52
0x180080ef4  mov     eax, dword ptr [rbp+70h+var_70]
0x180080ef7  lea     rdx, [rbp+70h+var_70]; unsigned __int8 *
0x180080efb  mov     [r14], rax
0x180080efe  mov     r8d, 20h ; ' '; unsigned int
0x180080f04  mov     eax, dword ptr [rbp+70h+var_70+4]
0x180080f07  mov     rcx, rdi; this
0x180080f0a  mov     [r14+10h], rax
0x180080f0e  mov     eax, dword ptr [rbp+70h+var_70+8]
0x180080f11  mov     [r14+18h], rax
0x180080f15  mov     eax, dword ptr [rbp+70h+var_70+0Ch]
0x180080f18  mov     [r14+20h], rax
0x180080f1c  mov     eax, dword ptr [rbp+70h+var_60]
0x180080f1f  mov     [r14+28h], rax
0x180080f23  mov     eax, dword ptr [rbp+70h+var_60+4]
0x180080f26  mov     [r14+30h], rax
0x180080f2a  mov     eax, dword ptr [rbp+70h+var_60+8]
0x180080f2d  mov     [r14+8], rax
0x180080f31  mov     eax, dword ptr [rbp+70h+var_60+0Ch]
0x180080f34  mov     [r14+38h], rax
0x180080f38  add     r14, 40h ; '@'
0x180080f3c  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180080f41  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180080f45  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180080f4a  add     r15d, edx
0x180080f4d  jmp     loc_180080E8C
0x180080f52  mov     ebx, 80004005h
0x180080f57  jmp     loc_18008104D
0x180080f5c  xor     r15d, r15d
0x180080f5f  cmp     [rdi], r15b
0x180080f62  jz      short loc_180080F80
0x180080f64  mov     r8d, [rdi+28h]; cbOutput
0x180080f68  xor     r9d, r9d; dwFlags
0x180080f6b  mov     rdx, [rdi+20h]; pbOutput
0x180080f6f  mov     rcx, [rdi+10h]; hHash
0x180080f73  call    cs:__imp_BCryptFinishHash
0x180080f79  test    eax, eax
0x180080f7b  jns     short loc_180080FB8
0x180080f7d  mov     [rdi], r15b
0x180080f80  lea     rcx, [rsp+170h+var_128]
0x180080f85  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180080f8a  mov     rcx, rsi; hObject
0x180080f8d  call    cs:__imp_CloseHandle
0x180080f93  mov     eax, 80004005h
0x180080f98  mov     rcx, [rbp+70h+var_50]
0x180080f9c  xor     rcx, rsp; StackCookie
0x180080f9f  call    __security_check_cookie
0x180080fa4  add     rsp, 138h
0x180080fab  pop     r15
0x180080fad  pop     r14
0x180080faf  pop     r13
0x180080fb1  pop     r12
0x180080fb3  pop     rdi
0x180080fb4  pop     rsi
0x180080fb5  pop     rbx
0x180080fb6  pop     rbp
0x180080fb7  retn
0x180080fb8  cmp     [rdi], r15b
0x180080fbb  jz      short loc_180080F80
0x180080fbd  cmp     dword ptr [rdi+28h], 10h
0x180080fc1  mov     r14d, 10h
0x180080fc7  ja      short loc_180080FCD
0x180080fc9  mov     r14d, [rdi+28h]
0x180080fcd  mov     rdx, [rdi+20h]; Src
0x180080fd1  lea     rcx, [r12+8]; void *
0x180080fd6  mov     r8, r14; Size
0x180080fd9  call    memcpy_0
0x180080fde  cmp     r14, 10h
0x180080fe2  jnz     short loc_180080F80
0x180080fe4  xor     edx, edx; Val
0x180080fe6  lea     r8d, [r14+46h]; Size
0x180080fea  lea     rcx, [rbp+70h+var_CE]; void *
0x180080fee  call    memset_0
0x180080ff3  mov     rcx, qword ptr [rsp+170h+var_128]
0x180080ff8  lea     eax, [r14-0Ch]
0x180080ffc  movups  xmm0, cs:ElfImageGuid
0x180081003  mov     [rbp+70h+var_D0], ax
0x180081007  lea     rdx, [rbp+70h+var_D0]
0x18008100b  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18008100f  xor     r9d, r9d
0x180081012  sub     eax, ecx
0x180081014  mov     [rbp+70h+var_88], rcx
0x180081018  mov     rcx, [r13+10h]
0x18008101c  xor     r8d, r8d
0x18008101f  mov     [rbp+70h+var_80], eax
0x180081022  mov     eax, [rbp+70h+arg_20]
0x180081028  mov     [rbp+70h+var_7C], eax
0x18008102b  mov     [rbp+70h+var_C0], rbx
0x18008102f  movdqu  [rbp+70h+var_B8], xmm0
0x180081034  mov     [rbp+70h+var_CC], r15d
0x180081038  mov     rax, [rcx]
0x18008103b  mov     rax, [rax+0C0h]
0x180081042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081047  mov     ebx, eax
0x180081049  test    eax, eax
0x18008104b  jns     short loc_180081067
0x18008104d  lea     rcx, [rsp+170h+var_128]
0x180081052  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180081057  mov     rcx, rsi; hObject
0x18008105a  call    cs:__imp_CloseHandle
0x180081060  mov     eax, ebx
0x180081062  jmp     loc_180080F98
0x180081067  lea     rcx, [rsp+170h+var_128]
0x18008106c  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180081071  mov     rcx, rsi; hObject
0x180081074  call    cs:__imp_CloseHandle
0x18008107a  xor     eax, eax
0x18008107c  jmp     loc_180080F98
```
