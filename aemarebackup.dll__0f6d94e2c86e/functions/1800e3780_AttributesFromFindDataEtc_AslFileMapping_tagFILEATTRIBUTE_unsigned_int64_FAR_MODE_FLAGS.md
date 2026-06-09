# _AttributesFromFindDataEtc(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e3780`
- end: `0x1800e3ca4`
- name: `?_AttributesFromFindDataEtc@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1316`
- prototype: `__int64 __fastcall(LPCWSTR **, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x180004ea0`
- `0x1800058fc`
- `0x180005914`
- `0x180005b90`
- `0x18004c020`
- `0x1800e3780`
- `0x1800e6144`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800e3862`
- `ntdll!RtlAllocateHeap` at `0x1800e3862`
- `ntdll!RtlFreeHeap` at `0x1800e38fb`
- `ntdll!RtlFreeHeap` at `0x1800e38fb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800e3c72`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800e3c72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e37e5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e37e5`

## string_xrefs

- `0x1800e3886`: `_SetFileAttributeValue`
- `0x1800e38d2`: `_SetFileAttributeValue`
- `0x1800e3a13`: `_SetFileAttributeValue`
- `0x1800e3b14`: `_SetFileAttributeValue`
- `0x1800e3c23`: `_SetFileAttributeValue`
- `0x1800e3a1a`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e3b1b`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e3c0e`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e38c0`: `Failed to copy attribute value (index %d) [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall _AttributesFromFindDataEtc(LPCWSTR **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HANDLE FirstFileW; // r12
  signed int LastError_0; // eax
  int v7; // edi
  __int64 v8; // r14
  wchar_t *Heap; // rax
  int v10; // eax
  void *v11; // r8
  __int64 v12; // r15
  int v13; // r10d
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  _WORD *v17; // r8
  _WORD *v18; // rcx
  int v19; // r10d
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  __int64 v22; // rdx
  _WORD *v23; // r8
  _WORD *v24; // rcx
  int v25; // esi
  unsigned __int16 *v26; // rax
  _WORD *v27; // rdi
  _WORD *v28; // r10
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v31[8]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v32; // [rsp+290h] [rbp+190h]
  __int64 v33; // [rsp+2A0h] [rbp+1A0h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 )
    return (unsigned int)-2147024809;
  FirstFileW = FindFirstFileW(**a1, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    v7 = dword_1801197A4;
    v8 = 260;
    if ( (unsigned int)dword_1801197A4 <= 2 )
    {
      *(_DWORD *)a2 = *(_DWORD *)FindFileData.cFileName;
    }
    else if ( dword_1801197A4 == 3 )
    {
      *(_QWORD *)a2 = *(_QWORD *)FindFileData.cFileName;
    }
    else
    {
      if ( dword_1801197A4 != 4 )
        goto LABEL_20;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
      *(_QWORD *)(a2 + 536) = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 0);
        goto LABEL_20;
      }
      v10 = o_wmemcpy_s_0(Heap, 0x105u, FindFileData.cFileName, 0x104u);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", 0, v10);
        v11 = *(void **)(a2 + 536);
        if ( v11 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
          *(_QWORD *)(a2 + 536) = 0;
        }
LABEL_20:
        *(_OWORD *)v31 = 0;
        v33 = 0;
        v32 = 0;
        v12 = 20;
        if ( _StringFromFileTime(&FindFileData.ftCreationTime, v31) < 0 )
          goto LABEL_35;
        v13 = dword_1801198DC;
        if ( (unsigned int)dword_1801198DC <= 2 )
        {
          *(_DWORD *)(a2 + 7072) = *(_DWORD *)v31;
        }
        else if ( dword_1801198DC == 3 )
        {
          *(_QWORD *)(a2 + 7072) = *(_QWORD *)v31;
        }
        else
        {
          if ( dword_1801198DC != 4 )
            goto LABEL_35;
          v14 = 20;
          v15 = v31;
          v16 = 260;
          v17 = (_WORD *)(a2 + 7072);
          do
          {
            if ( !v14 )
              break;
            if ( !*v15 )
              break;
            *v17++ = *v15++;
            --v14;
            --v16;
          }
          while ( v16 );
          v18 = v17 - 1;
          if ( v16 )
            v18 = v17;
          *v18 = 0;
          if ( !v16 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              13,
              -2147024774);
            goto LABEL_35;
          }
        }
        *(_DWORD *)(a2 + 7592) = 13;
        *(_DWORD *)(a2 + 7596) = v13;
        *(_DWORD *)(a2 + 7600) = 1;
LABEL_35:
        if ( _StringFromFileTime(&FindFileData.ftLastWriteTime, v31) < 0 )
          goto LABEL_50;
        v19 = dword_1801198F4;
        if ( (unsigned int)dword_1801198F4 <= 2 )
        {
          *(_DWORD *)(a2 + 7616) = *(_DWORD *)v31;
        }
        else if ( dword_1801198F4 == 3 )
        {
          *(_QWORD *)(a2 + 7616) = *(_QWORD *)v31;
        }
        else
        {
          if ( dword_1801198F4 != 4 )
            goto LABEL_50;
          v20 = 20;
          v21 = v31;
          v22 = 260;
          v23 = (_WORD *)(a2 + 7616);
          do
          {
            if ( !v20 )
              break;
            if ( !*v21 )
              break;
            *v23++ = *v21++;
            --v20;
            --v22;
          }
          while ( v22 );
          v24 = v23 - 1;
          if ( v22 )
            v24 = v23;
          *v24 = 0;
          if ( !v22 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              14,
              -2147024774);
            goto LABEL_50;
          }
        }
        *(_DWORD *)(a2 + 8136) = 14;
        *(_DWORD *)(a2 + 8140) = v19;
        *(_DWORD *)(a2 + 8144) = 1;
LABEL_50:
        if ( _StringFromFileTime(&FindFileData.ftLastAccessTime, v31) >= 0 )
        {
          v25 = dword_18011990C;
          if ( (unsigned int)dword_18011990C <= 2 )
          {
            *(_DWORD *)(a2 + 8160) = *(_DWORD *)v31;
            goto LABEL_64;
          }
          if ( dword_18011990C == 3 )
          {
            *(_QWORD *)(a2 + 8160) = *(_QWORD *)v31;
            goto LABEL_64;
          }
          if ( dword_18011990C == 4 )
          {
            v26 = v31;
            v27 = (_WORD *)(a2 + 8160);
            do
            {
              if ( !v12 )
                break;
              if ( !*v26 )
                break;
              *v27++ = *v26++;
              --v12;
              --v8;
            }
            while ( v8 );
            v28 = v27 - 1;
            if ( v8 )
              v28 = v27;
            *v28 = 0;
            if ( !v8 )
            {
              AslLogCallPrintf(
                1,
                "_SetFileAttributeValue",
                3178,
                "StringCbCopy failed to copy string attribute (index %d) [%x]",
                15,
                -2147024774);
              goto LABEL_65;
            }
LABEL_64:
            *(_DWORD *)(a2 + 8680) = 15;
            *(_DWORD *)(a2 + 8684) = v25;
            *(_DWORD *)(a2 + 8688) = 1;
          }
        }
LABEL_65:
        v4 = 0;
        FindClose(FirstFileW);
        return v4;
      }
      *(_WORD *)(*(_QWORD *)(a2 + 536) + 520LL) = 0;
      *(_WORD *)a2 = 0;
    }
    *(_DWORD *)(a2 + 520) = 0;
    *(_DWORD *)(a2 + 524) = v7;
    *(_DWORD *)(a2 + 528) = 1;
    goto LABEL_20;
  }
  LastError_0 = GetLastError_0();
  v4 = LastError_0;
  if ( LastError_0 > 0 )
    return (unsigned __int16)LastError_0 | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x1800e3780  mov     [rsp-8+arg_10], rbx
0x1800e3785  push    rbp
0x1800e3786  push    rsi
0x1800e3787  push    rdi
0x1800e3788  push    r12
0x1800e378a  push    r13
0x1800e378c  push    r14
0x1800e378e  push    r15
0x1800e3790  lea     rbp, [rsp-1B0h]
0x1800e3798  sub     rsp, 2B0h
0x1800e379f  mov     rax, cs:__security_cookie
0x1800e37a6  xor     rax, rsp
0x1800e37a9  mov     [rbp+1E0h+var_38], rax
0x1800e37b0  mov     rbx, rdx
0x1800e37b3  mov     rdi, rcx
0x1800e37b6  xor     edx, edx; Val
0x1800e37b8  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800e37bd  mov     r8d, 250h; Size
0x1800e37c3  call    memset_0
0x1800e37c8  xor     r13d, r13d
0x1800e37cb  test    rbx, rbx
0x1800e37ce  jnz     short loc_1800E37DA
0x1800e37d0  mov     ebx, 80070057h
0x1800e37d5  jmp     loc_1800E3C78
0x1800e37da  mov     rcx, [rdi]
0x1800e37dd  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800e37e2  mov     rcx, [rcx]; lpFileName
0x1800e37e5  call    cs:__imp_FindFirstFileW
0x1800e37eb  mov     r12, rax
0x1800e37ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e37f2  jnz     short loc_1800E3811
0x1800e37f4  call    GetLastError_0
0x1800e37f9  mov     ebx, eax
0x1800e37fb  test    eax, eax
0x1800e37fd  jle     loc_1800E3C78
0x1800e3803  movzx   ebx, ax
0x1800e3806  or      ebx, 80070000h
0x1800e380c  jmp     loc_1800E3C78
0x1800e3811  mov     edi, cs:dword_1801197A4
0x1800e3817  mov     esi, 1
0x1800e381c  mov     ecx, edi
0x1800e381e  mov     r14d, 104h
0x1800e3824  test    edi, edi
0x1800e3826  jz      loc_1800E3929
0x1800e382c  sub     ecx, esi
0x1800e382e  jz      loc_1800E3929
0x1800e3834  sub     ecx, esi
0x1800e3836  jz      loc_1800E3929
0x1800e383c  sub     ecx, esi
0x1800e383e  jz      loc_1800E391F
0x1800e3844  cmp     ecx, esi
0x1800e3846  jnz     loc_1800E3942
0x1800e384c  mov     rcx, gs:60h
0x1800e3855  lea     edx, [rsi+7]; Flags
0x1800e3858  mov     r8d, 20Ah; Size
0x1800e385e  mov     rcx, [rcx+30h]; HeapHandle
0x1800e3862  call    cs:__imp_RtlAllocateHeap
0x1800e3868  mov     [rbx+218h], rax
0x1800e386f  test    rax, rax
0x1800e3872  jnz     short loc_1800E3899
0x1800e3874  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e387b  mov     [rsp+2E0h+var_2C0], r13d
0x1800e3880  mov     r8d, 0C48h
0x1800e3886  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e388d  mov     ecx, esi
0x1800e388f  call    AslLogCallPrintf
0x1800e3894  jmp     loc_1800E3942
0x1800e3899  mov     r9, r14; N
0x1800e389c  lea     r8, [rsp+2E0h+FindFileData.cFileName]; S2
0x1800e38a1  mov     edx, 105h; N1
0x1800e38a6  mov     rcx, rax; S1
0x1800e38a9  call    _o_wmemcpy_s_0
0x1800e38ae  test    eax, eax
0x1800e38b0  jz      short loc_1800E390A
0x1800e38b2  jle     short loc_1800E38BC
0x1800e38b4  movzx   eax, ax
0x1800e38b7  or      eax, 80070000h
0x1800e38bc  mov     [rsp+2E0h+var_2B8], eax
0x1800e38c0  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e38c7  mov     r8d, 0C54h
0x1800e38cd  mov     [rsp+2E0h+var_2C0], r13d
0x1800e38d2  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e38d9  mov     ecx, esi
0x1800e38db  call    AslLogCallPrintf
0x1800e38e0  mov     r8, [rbx+218h]; P
0x1800e38e7  test    r8, r8
0x1800e38ea  jz      short loc_1800E3942
0x1800e38ec  mov     rcx, gs:60h
0x1800e38f5  xor     edx, edx; Flags
0x1800e38f7  mov     rcx, [rcx+30h]; HeapHandle
0x1800e38fb  call    cs:__imp_RtlFreeHeap
0x1800e3901  mov     [rbx+218h], r13
0x1800e3908  jmp     short loc_1800E3942
0x1800e390a  mov     rcx, [rbx+218h]
0x1800e3911  mov     [rcx+208h], r13w
0x1800e3919  mov     [rbx], r13w
0x1800e391d  jmp     short loc_1800E392F
0x1800e391f  mov     rax, qword ptr [rsp+2E0h+FindFileData.cFileName]
0x1800e3924  mov     [rbx], rax
0x1800e3927  jmp     short loc_1800E392F
0x1800e3929  mov     eax, dword ptr [rsp+2E0h+FindFileData.cFileName]
0x1800e392d  mov     [rbx], eax
0x1800e392f  mov     [rbx+208h], r13d
0x1800e3936  mov     [rbx+20Ch], edi
0x1800e393c  mov     [rbx+210h], esi
0x1800e3942  xorps   xmm0, xmm0
0x1800e3945  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800e394c  xor     eax, eax
0x1800e394e  lea     rcx, [rsp+2E0h+FindFileData.ftCreationTime]; struct _FILETIME *
0x1800e3953  movups  xmmword ptr [rbp+1E0h+var_60], xmm0
0x1800e395a  mov     [rbp+1E0h+var_40], rax
0x1800e3961  movups  [rbp+1E0h+var_50], xmm0
0x1800e3968  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800e396d  mov     edi, 0C6Ah
0x1800e3972  mov     r15d, 14h
0x1800e3978  test    eax, eax
0x1800e397a  js      loc_1800E3A68
0x1800e3980  mov     r10d, cs:dword_1801198DC
0x1800e3987  mov     ecx, r10d
0x1800e398a  test    r10d, r10d
0x1800e398d  jz      loc_1800E3A45
0x1800e3993  sub     ecx, esi
0x1800e3995  jz      loc_1800E3A45
0x1800e399b  sub     ecx, esi
0x1800e399d  jz      loc_1800E3A45
0x1800e39a3  sub     ecx, esi
0x1800e39a5  jz      loc_1800E3A35
0x1800e39ab  cmp     ecx, esi
0x1800e39ad  jnz     loc_1800E3A68
0x1800e39b3  mov     eax, r15d
0x1800e39b6  lea     rcx, [rbp+1E0h+var_60]
0x1800e39bd  mov     rdx, r14
0x1800e39c0  lea     r8, [rbx+1BA0h]
0x1800e39c7  test    rax, rax
0x1800e39ca  jz      short loc_1800E39EA
0x1800e39cc  movzx   r9d, word ptr [rcx]
0x1800e39d0  test    r9w, r9w
0x1800e39d4  jz      short loc_1800E39EA
0x1800e39d6  mov     [r8], r9w
0x1800e39da  add     rcx, 2
0x1800e39de  add     r8, 2
0x1800e39e2  sub     rax, rsi
0x1800e39e5  sub     rdx, rsi
0x1800e39e8  jnz     short loc_1800E39C7
0x1800e39ea  mov     rax, rdx
0x1800e39ed  lea     rcx, [r8-2]
0x1800e39f1  neg     rax
0x1800e39f4  sbb     r9d, r9d
0x1800e39f7  not     r9d
0x1800e39fa  and     r9d, 8007007Ah
0x1800e3a01  test    rdx, rdx
0x1800e3a04  cmovnz  rcx, r8
0x1800e3a08  mov     [rcx], r13w
0x1800e3a0c  jnz     short loc_1800E3A51
0x1800e3a0e  mov     [rsp+2E0h+var_2B8], r9d
0x1800e3a13  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e3a1a  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e3a21  mov     [rsp+2E0h+var_2C0], 0Dh
0x1800e3a29  mov     r8, rdi
0x1800e3a2c  mov     ecx, esi
0x1800e3a2e  call    AslLogCallPrintf
0x1800e3a33  jmp     short loc_1800E3A68
0x1800e3a35  mov     rax, qword ptr [rbp+1E0h+var_60]
0x1800e3a3c  mov     [rbx+1BA0h], rax
0x1800e3a43  jmp     short loc_1800E3A51
0x1800e3a45  mov     eax, dword ptr [rbp+1E0h+var_60]
0x1800e3a4b  mov     [rbx+1BA0h], eax
0x1800e3a51  mov     dword ptr [rbx+1DA8h], 0Dh
0x1800e3a5b  mov     [rbx+1DACh], r10d
0x1800e3a62  mov     [rbx+1DB0h], esi
0x1800e3a68  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800e3a6f  lea     rcx, [rsp+2E0h+FindFileData.ftLastWriteTime]; struct _FILETIME *
0x1800e3a74  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800e3a79  test    eax, eax
0x1800e3a7b  js      loc_1800E3B69
0x1800e3a81  mov     r10d, cs:dword_1801198F4
0x1800e3a88  mov     ecx, r10d
0x1800e3a8b  test    r10d, r10d
0x1800e3a8e  jz      loc_1800E3B46
0x1800e3a94  sub     ecx, esi
0x1800e3a96  jz      loc_1800E3B46
0x1800e3a9c  sub     ecx, esi
0x1800e3a9e  jz      loc_1800E3B46
0x1800e3aa4  sub     ecx, esi
0x1800e3aa6  jz      loc_1800E3B36
0x1800e3aac  cmp     ecx, esi
0x1800e3aae  jnz     loc_1800E3B69
0x1800e3ab4  mov     rax, r15
0x1800e3ab7  lea     rcx, [rbp+1E0h+var_60]
0x1800e3abe  mov     rdx, r14
0x1800e3ac1  lea     r8, [rbx+1DC0h]
0x1800e3ac8  test    rax, rax
0x1800e3acb  jz      short loc_1800E3AEB
0x1800e3acd  movzx   r9d, word ptr [rcx]
0x1800e3ad1  test    r9w, r9w
0x1800e3ad5  jz      short loc_1800E3AEB
0x1800e3ad7  mov     [r8], r9w
0x1800e3adb  add     rcx, 2
0x1800e3adf  add     r8, 2
0x1800e3ae3  sub     rax, rsi
0x1800e3ae6  sub     rdx, rsi
0x1800e3ae9  jnz     short loc_1800E3AC8
0x1800e3aeb  mov     rax, rdx
0x1800e3aee  lea     rcx, [r8-2]
0x1800e3af2  neg     rax
0x1800e3af5  sbb     r9d, r9d
0x1800e3af8  not     r9d
0x1800e3afb  and     r9d, 8007007Ah
0x1800e3b02  test    rdx, rdx
0x1800e3b05  cmovnz  rcx, r8
0x1800e3b09  mov     [rcx], r13w
0x1800e3b0d  jnz     short loc_1800E3B52
0x1800e3b0f  mov     [rsp+2E0h+var_2B8], r9d
0x1800e3b14  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e3b1b  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e3b22  mov     [rsp+2E0h+var_2C0], 0Eh
0x1800e3b2a  mov     r8, rdi
0x1800e3b2d  mov     ecx, esi
0x1800e3b2f  call    AslLogCallPrintf
0x1800e3b34  jmp     short loc_1800E3B69
0x1800e3b36  mov     rax, qword ptr [rbp+1E0h+var_60]
0x1800e3b3d  mov     [rbx+1DC0h], rax
0x1800e3b44  jmp     short loc_1800E3B52
0x1800e3b46  mov     eax, dword ptr [rbp+1E0h+var_60]
0x1800e3b4c  mov     [rbx+1DC0h], eax
0x1800e3b52  mov     dword ptr [rbx+1FC8h], 0Eh
0x1800e3b5c  mov     [rbx+1FCCh], r10d
0x1800e3b63  mov     [rbx+1FD0h], esi
0x1800e3b69  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800e3b70  lea     rcx, [rsp+2E0h+FindFileData.ftLastAccessTime]; struct _FILETIME *
0x1800e3b75  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800e3b7a  test    eax, eax
0x1800e3b7c  js      loc_1800E3C6C
0x1800e3b82  mov     esi, cs:dword_18011990C
0x1800e3b88  mov     ecx, esi
0x1800e3b8a  test    esi, esi
0x1800e3b8c  jz      loc_1800E3C46
0x1800e3b92  sub     ecx, 1
0x1800e3b95  jz      loc_1800E3C46
0x1800e3b9b  sub     ecx, 1
0x1800e3b9e  jz      loc_1800E3C46
0x1800e3ba4  sub     ecx, 1
0x1800e3ba7  jz      loc_1800E3C36
0x1800e3bad  cmp     ecx, 1
0x1800e3bb0  jnz     loc_1800E3C6C
0x1800e3bb6  lea     rax, [rbp+1E0h+var_60]
0x1800e3bbd  lea     rdi, [rbx+1FE0h]
0x1800e3bc4  test    r15, r15
0x1800e3bc7  jz      short loc_1800E3BE5
0x1800e3bc9  movzx   ecx, word ptr [rax]
0x1800e3bcc  test    cx, cx
0x1800e3bcf  jz      short loc_1800E3BE5
0x1800e3bd1  mov     [rdi], cx
0x1800e3bd4  add     rax, 2
0x1800e3bd8  add     rdi, 2
0x1800e3bdc  dec     r15
0x1800e3bdf  sub     r14, 1
0x1800e3be3  jnz     short loc_1800E3BC4
0x1800e3be5  mov     rax, r14
0x1800e3be8  lea     r10, [rdi-2]
0x1800e3bec  neg     rax
0x1800e3bef  sbb     r11d, r11d
0x1800e3bf2  not     r11d
0x1800e3bf5  and     r11d, 8007007Ah
0x1800e3bfc  test    r14, r14
0x1800e3bff  cmovnz  r10, rdi
0x1800e3c03  mov     [r10], r13w
0x1800e3c07  jnz     short loc_1800E3C52
0x1800e3c09  mov     [rsp+2E0h+var_2B8], r11d
0x1800e3c0e  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e3c15  mov     r8d, 0C6Ah
0x1800e3c1b  mov     [rsp+2E0h+var_2C0], 0Fh
0x1800e3c23  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e3c2a  mov     ecx, 1
0x1800e3c2f  call    AslLogCallPrintf
0x1800e3c34  jmp     short loc_1800E3C6C
0x1800e3c36  mov     rax, qword ptr [rbp+1E0h+var_60]
0x1800e3c3d  mov     [rbx+1FE0h], rax
0x1800e3c44  jmp     short loc_1800E3C52
0x1800e3c46  mov     eax, dword ptr [rbp+1E0h+var_60]
0x1800e3c4c  mov     [rbx+1FE0h], eax
0x1800e3c52  mov     dword ptr [rbx+21E8h], 0Fh
0x1800e3c5c  mov     [rbx+21ECh], esi
0x1800e3c62  mov     dword ptr [rbx+21F0h], 1
0x1800e3c6c  mov     ebx, r13d
0x1800e3c6f  mov     rcx, r12; hFindFile
0x1800e3c72  call    cs:__imp_FindClose
0x1800e3c78  mov     eax, ebx
0x1800e3c7a  mov     rcx, [rbp+1E0h+var_38]
0x1800e3c81  xor     rcx, rsp; StackCookie
0x1800e3c84  call    __security_check_cookie
0x1800e3c89  mov     rbx, [rsp+2E0h+arg_10]
0x1800e3c91  add     rsp, 2B0h
0x1800e3c98  pop     r15
0x1800e3c9a  pop     r14
0x1800e3c9c  pop     r13
0x1800e3c9e  pop     r12
0x1800e3ca0  pop     rdi
0x1800e3ca1  pop     rsi
0x1800e3ca2  pop     rbp
  ... truncated ...
```
