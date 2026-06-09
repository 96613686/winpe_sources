# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180021790`
- end: `0x180021b6c`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `988`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180021790`
- `0x180022710`
- `0x180024e88`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f6c`
- `0x1800278f0`
- `0x180027910`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800218d9`
- `msvcrt!wcscpy_s` at `0x1800218d9`
- `KERNEL32!ReadFile` at `0x180021833`
- `KERNEL32!ReadFile` at `0x1800219d0`
- `KERNEL32!ReadFile` at `0x180021833`
- `KERNEL32!ReadFile` at `0x1800219d0`
- `KERNEL32!GetFileSize` at `0x1800218e9`
- `KERNEL32!GetFileSize` at `0x1800218e9`
- `KERNEL32!CloseHandle` at `0x180021b44`
- `KERNEL32!CloseHandle` at `0x180021b44`
- `KERNEL32!CreateFileW` at `0x1800217ea`
- `KERNEL32!CreateFileW` at `0x1800217ea`
- `KERNEL32!SetFilePointer` at `0x1800219a9`
- `KERNEL32!SetFilePointer` at `0x1800219a9`
- `bcrypt!BCryptHashData` at `0x180021919`
- `bcrypt!BCryptHashData` at `0x18002193a`
- `bcrypt!BCryptHashData` at `0x18002195b`
- `bcrypt!BCryptHashData` at `0x18002197c`
- `bcrypt!BCryptHashData` at `0x180021a38`
- `bcrypt!BCryptHashData` at `0x180021919`
- `bcrypt!BCryptHashData` at `0x18002193a`
- `bcrypt!BCryptHashData` at `0x18002195b`
- `bcrypt!BCryptHashData` at `0x18002197c`
- `bcrypt!BCryptHashData` at `0x180021a38`
- `bcrypt!BCryptFinishHash` at `0x180021a77`
- `bcrypt!BCryptFinishHash` at `0x180021a77`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HANDLE FileW; // rax
  void *v10; // r12
  LPCWSTR v12; // rax
  _DWORD *v13; // r15
  unsigned __int64 v14; // rcx
  rsize_t v15; // rdx
  _QWORD *v16; // r14
  DWORD FileSize; // eax
  LONG v18; // esi
  int i; // ecx
  size_t v20; // rsi
  __int64 v21; // rcx
  int v22; // ebx
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead[2]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  int Buffer; // [rsp+80h] [rbp-80h] BYREF
  char v31; // [rsp+84h] [rbp-7Ch]
  char v32; // [rsp+85h] [rbp-7Bh]
  char v33; // [rsp+86h] [rbp-7Ah]
  UCHAR pbInput[2]; // [rsp+92h] [rbp-6Eh] BYREF
  UCHAR v35[8]; // [rsp+94h] [rbp-6Ch] BYREF
  LONG lDistanceToMove; // [rsp+9Ch] [rbp-64h]
  UCHAR v37[6]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v38; // [rsp+AAh] [rbp-56h]
  unsigned __int16 v39; // [rsp+ACh] [rbp-54h]
  __int16 v40; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[2]; // [rsp+C2h] [rbp-3Eh] BYREF
  int v42; // [rsp+C4h] [rbp-3Ch]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int128 v44; // [rsp+D8h] [rbp-28h]
  _DWORD *v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+110h] [rbp+10h]
  int v47; // [rsp+114h] [rbp+14h]
  UCHAR v48[4]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v49; // [rsp+124h] [rbp+24h]
  unsigned int v50; // [rsp+128h] [rbp+28h]
  unsigned int v51; // [rsp+12Ch] [rbp+2Ch]
  unsigned int v52; // [rsp+130h] [rbp+30h]
  unsigned int v53; // [rsp+134h] [rbp+34h]
  unsigned int v54; // [rsp+138h] [rbp+38h]
  unsigned int v55; // [rsp+13Ch] [rbp+3Ch]

  FileW = CreateFileW(*a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  *(_QWORD *)NumberOfBytesRead = FileW;
  sub_180024E88(&hObject, NumberOfBytesRead);
  NumberOfBytesRead[0] = 0;
  if ( !ReadFile(v10, &Buffer, 0x34u, NumberOfBytesRead, 0)
    || NumberOfBytesRead[0] != 52
    || Buffer != 1179403647
    || v31 != 1
    || v32 != 1
    || v33 != 1
    || v38 != 32 )
  {
    v22 = -2147467259;
    goto LABEL_44;
  }
  v12 = *a2;
  v23[0] = 0;
  std::vector<char>::_Construct_n(v27, 2 * (*((_DWORD *)v12 - 4) + 32 * (unsigned int)v39) + 94, v23);
  v13 = Block;
  v14 = (unsigned __int64)v39 << 6;
  v15 = (unsigned __int16)(*(*a2 - 8) + 1);
  v16 = (char *)Block + 28;
  *((_WORD *)Block + 13) = v15;
  wcscpy_s((wchar_t *)((char *)v16 + v14), v15, *a2);
  *v13 = 0;
  FileSize = GetFileSize(v10, 0);
  v13[1] = FileSize;
  if ( FileSize != -1 )
  {
    *((_WORD *)v13 + 12) = v39;
    if ( *(_BYTE *)a3 )
    {
      if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), (PUCHAR)&Buffer, 0x10u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      if ( *(_BYTE *)a3 )
      {
        if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), pbInput, 2u, 0) < 0 )
          *(_BYTE *)a3 = 0;
        if ( *(_BYTE *)a3 )
        {
          if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), v35, 4u, 0) < 0 )
            *(_BYTE *)a3 = 0;
          if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), v37, 4u, 0) < 0 )
            *(_BYTE *)a3 = 0;
        }
      }
    }
    v18 = lDistanceToMove;
    for ( i = lDistanceToMove + v38 * v39; v18 != i; i = lDistanceToMove + v38 * v39 )
    {
      if ( SetFilePointer(v10, v18, 0, 0) == -1
        || !ReadFile(v10, v48, 0x20u, NumberOfBytesRead, 0)
        || NumberOfBytesRead[0] != 32 )
      {
        goto LABEL_41;
      }
      *v16 = *(unsigned int *)v48;
      v16[2] = v49;
      v16[3] = v50;
      v16[4] = v51;
      v16[5] = v52;
      v16[6] = v53;
      v16[1] = v54;
      v16[7] = v55;
      v16 += 8;
      if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), v48, 0x20u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      v18 += v38;
    }
    if ( *(_BYTE *)a3 )
    {
      if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), *(PUCHAR *)(a3 + 32), *(_DWORD *)(a3 + 40), 0) >= 0 )
      {
        if ( *(_BYTE *)a3 )
        {
          v20 = 16;
          if ( *(_DWORD *)(a3 + 40) <= 0x10u )
            v20 = *(unsigned int *)(a3 + 40);
          memcpy_0(v13 + 2, *(const void **)(a3 + 32), v20);
          if ( v20 == 16 )
          {
            memset_0(v41, 0, 0x56u);
            v21 = *(_QWORD *)(a1 + 16);
            v40 = 4;
            v43 = a4;
            v46 = v29 - (_DWORD)v13;
            v47 = a5;
            v44 = ElfImageGuid;
            v42 = 0;
            v45 = v13;
            v22 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 192LL))(
                    v21,
                    &v40,
                    0,
                    0);
            if ( v22 >= 0 )
              v22 = 0;
            goto LABEL_42;
          }
        }
      }
      else
      {
        *(_BYTE *)a3 = 0;
      }
    }
  }
LABEL_41:
  v22 = -2147467259;
LABEL_42:
  operator delete(v13);
LABEL_44:
  if ( v26 )
    CloseHandle(hObject);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180021790  push    rbp
0x180021792  push    rbx
0x180021793  push    rsi
0x180021794  push    rdi
0x180021795  push    r12
0x180021797  push    r13
0x180021799  push    r14
0x18002179b  push    r15
0x18002179d  lea     rbp, [rsp-58h]
0x1800217a2  sub     rsp, 158h
0x1800217a9  mov     rax, cs:__security_cookie
0x1800217b0  xor     rax, rsp
0x1800217b3  mov     [rbp+90h+var_50], rax
0x1800217b7  mov     rsi, rdx
0x1800217ba  xor     r14d, r14d
0x1800217bd  mov     rbx, r9
0x1800217c0  mov     [rsp+190h+hTemplateFile], r14; hTemplateFile
0x1800217c5  mov     rdi, r8
0x1800217c8  mov     [rsp+190h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800217d0  mov     r13, rcx
0x1800217d3  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x1800217db  mov     rcx, [rsi]; lpFileName
0x1800217de  lea     r8d, [r14+7]; dwShareMode
0x1800217e2  xor     r9d, r9d; lpSecurityAttributes
0x1800217e5  mov     edx, 80000000h; dwDesiredAccess
0x1800217ea  call    cs:__imp_CreateFileW
0x1800217f0  mov     r12, rax
0x1800217f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800217f7  jnz     short loc_180021803
0x1800217f9  mov     eax, 80004005h
0x1800217fe  jmp     loc_180021B4C
0x180021803  lea     rdx, [rsp+190h+NumberOfBytesRead]
0x180021808  mov     qword ptr [rsp+190h+NumberOfBytesRead], r12
0x18002180d  lea     rcx, [rsp+190h+hObject]
0x180021812  call    sub_180024E88
0x180021817  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002181c  mov     [rsp+190h+NumberOfBytesRead], r14d
0x180021821  mov     r8d, 34h ; '4'; nNumberOfBytesToRead
0x180021827  mov     qword ptr [rsp+190h+dwCreationDisposition], r14; lpOverlapped
0x18002182c  lea     rdx, [rbp+90h+Buffer]; lpBuffer
0x180021830  mov     rcx, r12; hFile
0x180021833  call    cs:__imp_ReadFile
0x180021839  test    eax, eax
0x18002183b  jz      loc_180021B31
0x180021841  cmp     [rsp+190h+NumberOfBytesRead], 34h ; '4'
0x180021846  jnz     loc_180021B31
0x18002184c  mov     eax, [rbp+90h+Buffer]
0x18002184f  cmp     eax, cs:dword_18002D690
0x180021855  jnz     loc_180021B31
0x18002185b  cmp     [rbp+90h+var_10C], 1
0x18002185f  jnz     loc_180021B31
0x180021865  cmp     [rbp+90h+var_10B], 1
0x180021869  jnz     loc_180021B31
0x18002186f  cmp     [rbp+90h+var_10A], 1
0x180021873  jnz     loc_180021B31
0x180021879  mov     eax, 20h ; ' '
0x18002187e  cmp     ax, [rbp+90h+var_E6]
0x180021882  jnz     loc_180021B31
0x180021888  movzx   ecx, [rbp+90h+var_E4]
0x18002188c  lea     r8, [rsp+190h+var_150]
0x180021891  mov     rax, [rsi]
0x180021894  shl     ecx, 5
0x180021897  mov     [rsp+190h+var_150], r14b
0x18002189c  add     ecx, [rax-10h]
0x18002189f  lea     edx, ds:5Eh[rcx*2]
0x1800218a6  lea     rcx, [rsp+190h+var_130]
0x1800218ab  call    ?_Construct_n@?$vector@DV?$allocator@D@std@@@std@@QEAAX_KAEBD@Z; std::vector<char>::_Construct_n(unsigned __int64,char const &)
0x1800218b0  mov     rax, [rsi]
0x1800218b3  movzx   ecx, [rbp+90h+var_E4]
0x1800218b7  mov     r15, [rsp+190h+Block]
0x1800218bc  shl     rcx, 6
0x1800218c0  movzx   edx, word ptr [rax-10h]
0x1800218c4  inc     dx
0x1800218c7  movzx   edx, dx; SizeInWords
0x1800218ca  lea     r14, [r15+1Ch]
0x1800218ce  mov     [r15+1Ah], dx
0x1800218d3  add     rcx, r14; Destination
0x1800218d6  mov     r8, [rsi]; Source
0x1800218d9  call    cs:__imp_wcscpy_s
0x1800218df  xor     esi, esi
0x1800218e1  xor     edx, edx; lpFileSizeHigh
0x1800218e3  mov     rcx, r12; hFile
0x1800218e6  mov     [r15], esi
0x1800218e9  call    cs:__imp_GetFileSize
0x1800218ef  mov     [r15+4], eax
0x1800218f3  cmp     eax, 0FFFFFFFFh
0x1800218f6  jz      loc_180021B22
0x1800218fc  movzx   eax, [rbp+90h+var_E4]
0x180021900  mov     [r15+18h], ax
0x180021905  cmp     [rdi], sil
0x180021908  jz      short loc_180021989
0x18002190a  mov     rcx, [rdi+10h]; hHash
0x18002190e  lea     r8d, [rsi+10h]; cbInput
0x180021912  xor     r9d, r9d; dwFlags
0x180021915  lea     rdx, [rbp+90h+Buffer]; pbInput
0x180021919  call    cs:__imp_BCryptHashData
0x18002191f  test    eax, eax
0x180021921  jns     short loc_180021926
0x180021923  mov     [rdi], sil
0x180021926  cmp     [rdi], sil
0x180021929  jz      short loc_180021989
0x18002192b  mov     rcx, [rdi+10h]; hHash
0x18002192f  lea     rdx, [rbp+90h+pbInput]; pbInput
0x180021933  xor     r9d, r9d; dwFlags
0x180021936  lea     r8d, [r9+2]; cbInput
0x18002193a  call    cs:__imp_BCryptHashData
0x180021940  test    eax, eax
0x180021942  jns     short loc_180021947
0x180021944  mov     [rdi], sil
0x180021947  cmp     [rdi], sil
0x18002194a  jz      short loc_180021989
0x18002194c  mov     rcx, [rdi+10h]; hHash
0x180021950  lea     rdx, [rbp+90h+var_FC]; pbInput
0x180021954  xor     r9d, r9d; dwFlags
0x180021957  lea     r8d, [r9+4]; cbInput
0x18002195b  call    cs:__imp_BCryptHashData
0x180021961  test    eax, eax
0x180021963  jns     short loc_180021968
0x180021965  mov     [rdi], sil
0x180021968  cmp     [rdi], sil
0x18002196b  jz      short loc_180021989
0x18002196d  mov     rcx, [rdi+10h]; hHash
0x180021971  lea     rdx, [rbp+90h+var_EC]; pbInput
0x180021975  xor     r9d, r9d; dwFlags
0x180021978  lea     r8d, [r9+4]; cbInput
0x18002197c  call    cs:__imp_BCryptHashData
0x180021982  test    eax, eax
0x180021984  jns     short loc_180021989
0x180021986  mov     [rdi], sil
0x180021989  movzx   ecx, [rbp+90h+var_E4]
0x18002198d  movzx   eax, [rbp+90h+var_E6]
0x180021991  mov     esi, [rbp+90h+lDistanceToMove]
0x180021994  imul    ecx, eax
0x180021997  add     ecx, esi
0x180021999  jmp     loc_180021A55
0x18002199e  xor     r9d, r9d; dwMoveMethod
0x1800219a1  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800219a4  mov     edx, esi; lDistanceToMove
0x1800219a6  mov     rcx, r12; hFile
0x1800219a9  call    cs:__imp_SetFilePointer
0x1800219af  cmp     eax, 0FFFFFFFFh
0x1800219b2  jz      loc_180021B20
0x1800219b8  and     qword ptr [rsp+190h+dwCreationDisposition], 0
0x1800219be  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800219c3  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x1800219c9  lea     rdx, [rbp+90h+var_70]; lpBuffer
0x1800219cd  mov     rcx, r12; hFile
0x1800219d0  call    cs:__imp_ReadFile
0x1800219d6  test    eax, eax
0x1800219d8  jz      loc_180021B20
0x1800219de  cmp     [rsp+190h+NumberOfBytesRead], 20h ; ' '
0x1800219e3  jnz     loc_180021B20
0x1800219e9  mov     eax, dword ptr [rbp+90h+var_70]
0x1800219ec  mov     [r14], rax
0x1800219ef  mov     eax, [rbp+90h+var_6C]
0x1800219f2  mov     [r14+10h], rax
0x1800219f6  mov     eax, [rbp+90h+var_68]
0x1800219f9  mov     [r14+18h], rax
0x1800219fd  mov     eax, [rbp+90h+var_64]
0x180021a00  mov     [r14+20h], rax
0x180021a04  mov     eax, [rbp+90h+var_60]
0x180021a07  mov     [r14+28h], rax
0x180021a0b  mov     eax, [rbp+90h+var_5C]
0x180021a0e  mov     [r14+30h], rax
0x180021a12  mov     eax, [rbp+90h+var_58]
0x180021a15  mov     [r14+8], rax
0x180021a19  mov     eax, [rbp+90h+var_54]
0x180021a1c  mov     [r14+38h], rax
0x180021a20  add     r14, 40h ; '@'
0x180021a24  cmp     byte ptr [rdi], 0
0x180021a27  jz      short loc_180021A45
0x180021a29  mov     rcx, [rdi+10h]; hHash
0x180021a2d  lea     rdx, [rbp+90h+var_70]; pbInput
0x180021a31  xor     r9d, r9d; dwFlags
0x180021a34  lea     r8d, [r9+20h]; cbInput
0x180021a38  call    cs:__imp_BCryptHashData
0x180021a3e  test    eax, eax
0x180021a40  jns     short loc_180021A45
0x180021a42  mov     byte ptr [rdi], 0
0x180021a45  movzx   eax, [rbp+90h+var_E6]
0x180021a49  movzx   ecx, [rbp+90h+var_E4]
0x180021a4d  add     esi, eax
0x180021a4f  imul    ecx, eax
0x180021a52  add     ecx, [rbp+90h+lDistanceToMove]
0x180021a55  cmp     esi, ecx
0x180021a57  jnz     loc_18002199E
0x180021a5d  xor     esi, esi
0x180021a5f  cmp     [rdi], sil
0x180021a62  jz      loc_180021B22
0x180021a68  mov     r8d, [rdi+28h]; cbOutput
0x180021a6c  xor     r9d, r9d; dwFlags
0x180021a6f  mov     rdx, [rdi+20h]; pbOutput
0x180021a73  mov     rcx, [rdi+10h]; hHash
0x180021a77  call    cs:__imp_BCryptFinishHash
0x180021a7d  test    eax, eax
0x180021a7f  jns     short loc_180021A89
0x180021a81  mov     [rdi], sil
0x180021a84  jmp     loc_180021B22
0x180021a89  cmp     [rdi], sil
0x180021a8c  jz      loc_180021B22
0x180021a92  cmp     dword ptr [rdi+28h], 10h
0x180021a96  mov     esi, 10h
0x180021a9b  ja      short loc_180021AA0
0x180021a9d  mov     esi, [rdi+28h]
0x180021aa0  mov     rdx, [rdi+20h]; Src
0x180021aa4  lea     rcx, [r15+8]; void *
0x180021aa8  mov     r8, rsi; Size
0x180021aab  call    memcpy_0
0x180021ab0  cmp     rsi, 10h
0x180021ab4  jnz     short loc_180021B20
0x180021ab6  xor     edx, edx; Val
0x180021ab8  lea     r8d, [rsi+46h]; Size
0x180021abc  lea     rcx, [rbp+90h+var_CE]; void *
0x180021ac0  call    memset_0
0x180021ac5  movups  xmm0, cs:ElfImageGuid
0x180021acc  mov     rcx, [r13+10h]
0x180021ad0  lea     eax, [rsi-0Ch]
0x180021ad3  mov     [rbp+90h+var_D0], ax
0x180021ad7  lea     rdx, [rbp+90h+var_D0]
0x180021adb  mov     eax, [rsp+190h+var_120]
0x180021adf  xor     esi, esi
0x180021ae1  sub     eax, r15d
0x180021ae4  mov     [rbp+90h+var_C0], rbx
0x180021ae8  mov     [rbp+90h+var_80], eax
0x180021aeb  xor     r9d, r9d
0x180021aee  mov     eax, [rbp+90h+arg_20]
0x180021af4  xor     r8d, r8d
0x180021af7  mov     [rbp+90h+var_7C], eax
0x180021afa  movdqu  [rbp+90h+var_B8], xmm0
0x180021aff  mov     [rbp+90h+var_CC], esi
0x180021b02  mov     [rbp+90h+var_88], r15
0x180021b06  mov     rax, [rcx]
0x180021b09  mov     rax, [rax+0C0h]
0x180021b10  call    cs:__guard_dispatch_icall_fptr
0x180021b16  mov     ebx, eax
0x180021b18  test    eax, eax
0x180021b1a  js      short loc_180021B27
0x180021b1c  mov     ebx, esi
0x180021b1e  jmp     short loc_180021B27
0x180021b20  xor     esi, esi
0x180021b22  mov     ebx, 80004005h
0x180021b27  mov     rcx, r15; Block
0x180021b2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021b2f  jmp     short loc_180021B38
0x180021b31  mov     ebx, 80004005h
0x180021b36  xor     esi, esi
0x180021b38  cmp     [rsp+190h+var_138], sil
0x180021b3d  jz      short loc_180021B4A
0x180021b3f  mov     rcx, [rsp+190h+hObject]; hObject
0x180021b44  call    cs:__imp_CloseHandle
0x180021b4a  mov     eax, ebx
0x180021b4c  mov     rcx, [rbp+90h+var_50]
0x180021b50  xor     rcx, rsp; StackCookie
0x180021b53  call    __security_check_cookie
0x180021b58  add     rsp, 158h
0x180021b5f  pop     r15
0x180021b61  pop     r14
0x180021b63  pop     r13
0x180021b65  pop     r12
0x180021b67  pop     rdi
0x180021b68  pop     rsi
0x180021b69  pop     rbx
0x180021b6a  pop     rbp
0x180021b6b  retn
```
