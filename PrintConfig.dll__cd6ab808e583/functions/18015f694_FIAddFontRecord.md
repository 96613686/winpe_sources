# FIAddFontRecord

- ea: `0x18015f694`
- end: `0x18015faf5`
- name: `FIAddFontRecord`
- size: `1121`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801201d4`
- `0x180120f44`

## callees

- `0x1800032e0`
- `0x180124b0c`
- `0x180124e1c`
- `0x180124ed0`
- `0x18015f694`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18015f787`
- `KERNEL32!WriteFile` at `0x18015f83d`
- `KERNEL32!WriteFile` at `0x18015f9a0`
- `KERNEL32!WriteFile` at `0x18015f9c5`
- `KERNEL32!WriteFile` at `0x18015f787`
- `KERNEL32!WriteFile` at `0x18015f83d`
- `KERNEL32!WriteFile` at `0x18015f9a0`
- `KERNEL32!WriteFile` at `0x18015f9c5`
- `KERNEL32!LoadResource` at `0x18015f91a`
- `KERNEL32!LoadResource` at `0x18015f91a`
- `KERNEL32!SizeofResource` at `0x18015f967`
- `KERNEL32!SizeofResource` at `0x18015f967`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015f7b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015f87e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015fa3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015fabe`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015f7b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015f87e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015fa3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18015fabe`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18015f923`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18015f923`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18015f8fe`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18015f8fe`

## pseudocode

```c
__int64 __fastcall FIAddFontRecord(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r12
  __int64 v6; // r14
  _WORD *v7; // rdx
  __int64 v8; // r8
  void *v9; // rcx
  LONG v10; // edx
  DWORD v11; // eax
  __int64 v12; // rax
  int v13; // r8d
  void *v14; // rdi
  int v15; // eax
  void *v16; // rcx
  LONG v17; // edx
  DWORD v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rax
  HRSRC ResourceW; // rax
  HRSRC v24; // rbx
  HGLOBAL Resource; // rax
  const void *v26; // rax
  __int64 v27; // rcx
  const void *v28; // rdi
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  LONG v33; // edx
  const void *v34; // rdx
  void *v35; // rcx
  DWORD v36; // eax
  void *v37; // rcx
  LONG v38; // edx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-20h] BYREF
  DWORD v41; // [rsp+34h] [rbp-1Ch] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-18h] BYREF

  v3 = a2;
  NumberOfBytesWritten = 0;
  if ( !a1 )
    return 0;
  if ( *(_DWORD *)a1 != 1718514793 )
    return 0;
  if ( (*(_BYTE *)(a1 + 572) & 2) == 0 )
    return 0;
  v6 = 9LL * a2;
  strcpy((char *)(*(_QWORD *)(a1 + 560) + 36LL * a2), "FREC$");
  *(_WORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 6) = a2;
  *(_WORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 8) = *(_WORD *)(a3 + 96);
  *(_WORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 10) = 70;
  *(_DWORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 12) = 1229345870;
  v7 = *(_WORD **)(a3 + 104);
  v8 = -1;
  *(_DWORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 16) = *(_DWORD *)(a1 + 568);
  do
    ++v8;
  while ( v7[v8] );
  if ( !WriteFile(*(HANDLE *)(a1 + 544), v7, 2 * v8 + 2, &NumberOfBytesWritten, 0) )
    return 0;
  v9 = *(void **)(a1 + 544);
  v10 = (*(_DWORD *)(a1 + 568) + NumberOfBytesWritten + 3) & 0xFFFFFFFC;
  *(_DWORD *)(a1 + 568) = v10;
  v11 = SetFilePointer(v9, v10, 0, 0);
  v41 = 0;
  *(_DWORD *)(a1 + 568) = v11;
  v12 = *(_QWORD *)(a1 + 560);
  LODWORD(Buffer) = 1229343044;
  WORD3(Buffer) = v3;
  HIDWORD(Buffer) = 0;
  *(_DWORD *)(v12 + 36 * v3 + 20) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 560) + 36 * v3 + 24) = *(_DWORD *)(a1 + 568);
  v13 = *(_DWORD *)(a3 + 48)
      + *(_DWORD *)(a3 + 64)
      + *(_DWORD *)(a3 + 80)
      + *(_DWORD *)(a3 + 112)
      + *(_DWORD *)(a3 + 128);
  v14 = *(void **)(a1 + 544);
  LODWORD(v12) = *(_DWORD *)(a3 + 32) + 60;
  WORD2(Buffer) = 16;
  DWORD2(Buffer) = v12 + v13;
  WriteFile(v14, &Buffer, 0x10u, &v41, 0);
  v15 = iWriteFDH(v14, (const struct _FI_DATA *)(a3 + 24));
  NumberOfBytesWritten = v15 + 16;
  if ( v15 == -16 )
    return 0;
  v16 = *(void **)(a1 + 544);
  v17 = (v15 + 16 + *(_DWORD *)(a1 + 568) + 3) & 0xFFFFFFFC;
  *(_DWORD *)(a1 + 568) = v17;
  v18 = SetFilePointer(v16, v17, 0, 0);
  v19 = *(_DWORD *)(a1 + 592);
  v20 = 0;
  *(_DWORD *)(a1 + 568) = v18;
  if ( v19 )
  {
    v21 = *(_QWORD *)(a1 + 584);
    while ( *(_WORD *)(v21 + 8LL * v20) != *(_WORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 8) )
    {
      if ( ++v20 >= v19 )
      {
        v22 = *(_QWORD *)(a1 + 560);
        goto LABEL_15;
      }
    }
    v20 = *(_DWORD *)(v21 + 8LL * v20 + 4);
  }
  v22 = *(_QWORD *)(a1 + 560);
  if ( v20 )
  {
    *(_DWORD *)(v22 + 4 * v6 + 28) = v20;
  }
  else
  {
LABEL_15:
    if ( *(__int16 *)(v22 + 4 * v6 + 8) <= 0 )
    {
      v27 = *(_QWORD *)(a1 + 560);
    }
    else
    {
      ResourceW = FindResourceW(ghInstance, (LPCWSTR)*(unsigned __int16 *)(v22 + 4 * v6 + 8), (LPCWSTR)0x103);
      v24 = ResourceW;
      if ( !ResourceW )
        return 0;
      Resource = LoadResource(ghInstance, ResourceW);
      v26 = LockResource(Resource);
      v27 = *(_QWORD *)(a1 + 560);
      v28 = v26;
      if ( v26 )
      {
        Buffer = 0;
        LODWORD(Buffer) = 1414808388;
        WORD2(Buffer) = 16;
        WORD3(Buffer) = *(_WORD *)(v27 + 4 * v6 + 8);
        v29 = SizeofResource(ghInstance, v24);
        v30 = *(_QWORD *)(a1 + 560);
        *((_QWORD *)&Buffer + 1) = v29;
        *(_DWORD *)(v30 + 4 * v6 + 28) = *(_DWORD *)(a1 + 568);
        if ( !WriteFile(*(HANDLE *)(a1 + 544), &Buffer, 0x10u, &NumberOfBytesWritten, 0)
          || !WriteFile(*(HANDLE *)(a1 + 544), v28, DWORD2(Buffer), &NumberOfBytesWritten, 0) )
        {
          return 0;
        }
        *(_WORD *)(*(_QWORD *)(a1 + 584) + 8LL * *(unsigned int *)(a1 + 592)) = *(_WORD *)(*(_QWORD *)(a1 + 560)
                                                                                         + 4 * v6
                                                                                         + 8);
        *(_DWORD *)(*(_QWORD *)(a1 + 584) + 8LL * *(unsigned int *)(a1 + 592) + 4) = *(_DWORD *)(a1 + 568);
        v31 = *(_QWORD *)(a1 + 552);
        ++*(_DWORD *)(a1 + 592);
        ++*(_DWORD *)(v31 + 16);
        v32 = *(void **)(a1 + 544);
        v33 = (*(_DWORD *)(a1 + 568) + NumberOfBytesWritten + 19) & 0xFFFFFFFC;
        *(_DWORD *)(a1 + 568) = v33;
        *(_DWORD *)(a1 + 568) = SetFilePointer(v32, v33, 0, 0);
        goto LABEL_24;
      }
    }
    *(_DWORD *)(v27 + 4 * v6 + 28) = 0;
  }
LABEL_24:
  *(_DWORD *)(*(_QWORD *)(a1 + 560) + 4 * v6 + 32) = *(_DWORD *)(a1 + 568);
  v34 = *(const void **)(a3 + 8);
  v35 = *(void **)(a1 + 544);
  if ( v34 )
    v36 = FIWriteRawVar(v35, v34);
  else
    v36 = FIWriteVar(v35, (LPCWSTR)(a3 + 160));
  NumberOfBytesWritten = v36;
  if ( v36 )
  {
    v37 = *(void **)(a1 + 544);
    v38 = (v36 + *(_DWORD *)(a1 + 568) + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 568) = v38;
    *(_DWORD *)(a1 + 568) = SetFilePointer(v37, v38, 0, 0);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18015f694  mov     [rsp-38h+arg_18], rbx
0x18015f699  push    rbp
0x18015f69a  push    rsi
0x18015f69b  push    rdi
0x18015f69c  push    r12
0x18015f69e  push    r13
0x18015f6a0  push    r14
0x18015f6a2  push    r15
0x18015f6a4  mov     rbp, rsp
0x18015f6a7  sub     rsp, 50h
0x18015f6ab  mov     rax, cs:__security_cookie
0x18015f6b2  xor     rax, rsp
0x18015f6b5  mov     [rbp+var_8], rax
0x18015f6b9  xor     r13d, r13d
0x18015f6bc  mov     r12d, edx
0x18015f6bf  mov     [rbp+NumberOfBytesWritten], r13d
0x18015f6c3  mov     r15, r8
0x18015f6c6  mov     rsi, rcx
0x18015f6c9  test    rcx, rcx
0x18015f6cc  jz      loc_18015FACF
0x18015f6d2  cmp     dword ptr [rcx], 666E7469h
0x18015f6d8  jnz     loc_18015FACF
0x18015f6de  test    byte ptr [rcx+23Ch], 2
0x18015f6e5  jz      loc_18015FACF
0x18015f6eb  mov     rax, [rcx+230h]
0x18015f6f2  lea     r14, [r12+r12*8]
0x18015f6f6  mov     dword ptr [rax+r14*4], 43455246h
0x18015f6fe  mov     rax, [rcx+230h]
0x18015f705  mov     word ptr [rax+r14*4+4], 24h ; '$'
0x18015f70d  mov     rax, [rcx+230h]
0x18015f714  mov     [rax+r14*4+6], r12w
0x18015f71a  movzx   eax, word ptr [r8+60h]
0x18015f71f  mov     rcx, [rcx+230h]
0x18015f726  mov     [rcx+r14*4+8], ax
0x18015f72c  mov     rax, [rsi+230h]
0x18015f733  mov     word ptr [rax+r14*4+0Ah], 46h ; 'F'
0x18015f73b  mov     rax, [rsi+230h]
0x18015f742  mov     dword ptr [rax+r14*4+0Ch], 4946544Eh
0x18015f74b  mov     rdx, [r8+68h]; lpBuffer
0x18015f74f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18015f753  mov     rcx, [rsi+230h]
0x18015f75a  mov     eax, [rsi+238h]
0x18015f760  mov     [rcx+r14*4+10h], eax
0x18015f765  inc     r8
0x18015f768  cmp     [rdx+r8*2], r13w
0x18015f76d  jnz     short loc_18015F765
0x18015f76f  mov     rcx, [rsi+220h]; hFile
0x18015f776  lea     r8d, ds:2[r8*2]; nNumberOfBytesToWrite
0x18015f77e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18015f782  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x18015f787  call    cs:__imp_WriteFile
0x18015f78d  test    eax, eax
0x18015f78f  jz      loc_18015FACF
0x18015f795  mov     edx, [rbp+NumberOfBytesWritten]
0x18015f798  xor     r9d, r9d; dwMoveMethod
0x18015f79b  mov     rcx, [rsi+220h]; hFile
0x18015f7a2  add     edx, 3
0x18015f7a5  add     edx, [rsi+238h]
0x18015f7ab  xor     r8d, r8d; lpDistanceToMoveHigh
0x18015f7ae  and     edx, 0FFFFFFFCh; lDistanceToMove
0x18015f7b1  mov     [rsi+238h], edx
0x18015f7b7  call    cs:__imp_SetFilePointer
0x18015f7bd  lea     r9, [rbp+var_1C]; lpNumberOfBytesWritten
0x18015f7c1  mov     [rbp+var_1C], r13d
0x18015f7c5  mov     [rsi+238h], eax
0x18015f7cb  lea     rdx, [rbp+Buffer]; lpBuffer
0x18015f7cf  mov     rax, [rsi+230h]
0x18015f7d6  mov     dword ptr [rbp+Buffer], 49464944h
0x18015f7dd  mov     word ptr [rbp+Buffer+6], r12w
0x18015f7e2  mov     dword ptr [rbp+Buffer+0Ch], r13d
0x18015f7e6  mov     [rax+r14*4+14h], r13d
0x18015f7eb  mov     rcx, [rsi+230h]
0x18015f7f2  mov     eax, [rsi+238h]
0x18015f7f8  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x18015f7fd  mov     [rcx+r14*4+18h], eax
0x18015f802  mov     ecx, 10h
0x18015f807  mov     r8d, [r15+80h]
0x18015f80e  add     r8d, [r15+70h]
0x18015f812  add     r8d, [r15+50h]
0x18015f816  add     r8d, [r15+40h]
0x18015f81a  add     r8d, [r15+30h]
0x18015f81e  mov     eax, [r15+20h]
0x18015f822  mov     rdi, [rsi+220h]
0x18015f829  add     eax, 3Ch ; '<'
0x18015f82c  add     r8d, eax
0x18015f82f  mov     word ptr [rbp+Buffer+4], cx
0x18015f833  mov     dword ptr [rbp+Buffer+8], r8d
0x18015f837  mov     r8d, ecx; nNumberOfBytesToWrite
0x18015f83a  mov     rcx, rdi; hFile
0x18015f83d  call    cs:__imp_WriteFile
0x18015f843  lea     rdx, [r15+18h]; struct _FI_DATA *
0x18015f847  mov     rcx, rdi; void *
0x18015f84a  call    ?iWriteFDH@@YAHPEAXPEBU_FI_DATA@@@Z; iWriteFDH(void *,_FI_DATA const *)
0x18015f84f  lea     ecx, [rax+10h]
0x18015f852  mov     [rbp+NumberOfBytesWritten], ecx
0x18015f855  test    ecx, ecx
0x18015f857  jz      loc_18015FACF
0x18015f85d  mov     edx, [rsi+238h]
0x18015f863  xor     r9d, r9d; dwMoveMethod
0x18015f866  add     edx, 3
0x18015f869  xor     r8d, r8d; lpDistanceToMoveHigh
0x18015f86c  add     edx, ecx
0x18015f86e  mov     rcx, [rsi+220h]; hFile
0x18015f875  and     edx, 0FFFFFFFCh; lDistanceToMove
0x18015f878  mov     [rsi+238h], edx
0x18015f87e  call    cs:__imp_SetFilePointer
0x18015f884  mov     r8d, [rsi+250h]
0x18015f88b  mov     ecx, r13d
0x18015f88e  mov     [rsi+238h], eax
0x18015f894  mov     r12d, 1
0x18015f89a  test    r8d, r8d
0x18015f89d  jz      short loc_18015F8D1
0x18015f89f  mov     rax, [rsi+230h]
0x18015f8a6  mov     rdx, [rsi+248h]
0x18015f8ad  movzx   r9d, word ptr [rax+r14*4+8]
0x18015f8b3  mov     eax, ecx
0x18015f8b5  cmp     [rdx+rax*8], r9w
0x18015f8ba  jz      short loc_18015F8CD
0x18015f8bc  add     ecx, r12d
0x18015f8bf  cmp     ecx, r8d
0x18015f8c2  jb      short loc_18015F8B3
0x18015f8c4  mov     rax, [rsi+230h]
0x18015f8cb  jmp     short loc_18015F8E0
0x18015f8cd  mov     ecx, [rdx+rax*8+4]
0x18015f8d1  mov     rax, [rsi+230h]
0x18015f8d8  test    ecx, ecx
0x18015f8da  jnz     loc_18015FA58
0x18015f8e0  movzx   ecx, word ptr [rax+r14*4+8]
0x18015f8e6  test    cx, cx
0x18015f8e9  jle     loc_18015FA4A
0x18015f8ef  mov     edx, ecx; lpName
0x18015f8f1  mov     r8d, 103h; lpType
0x18015f8f7  mov     rcx, cs:ghInstance; hModule
0x18015f8fe  call    cs:__imp_FindResourceW
0x18015f904  mov     rbx, rax
0x18015f907  test    rax, rax
0x18015f90a  jz      loc_18015FACF
0x18015f910  mov     rcx, cs:ghInstance; hModule
0x18015f917  mov     rdx, rax; hResInfo
0x18015f91a  call    cs:__imp_LoadResource
0x18015f920  mov     rcx, rax; hResData
0x18015f923  call    cs:__imp_LockResource
0x18015f929  mov     rcx, [rsi+230h]
0x18015f930  mov     rdi, rax
0x18015f933  test    rax, rax
0x18015f936  jz      loc_18015FA51
0x18015f93c  xorps   xmm0, xmm0
0x18015f93f  mov     eax, 10h
0x18015f944  movups  [rbp+Buffer], xmm0
0x18015f948  mov     dword ptr [rbp+Buffer], 54544344h
0x18015f94f  mov     rdx, rbx; hResInfo
0x18015f952  mov     word ptr [rbp+Buffer+4], ax
0x18015f956  movzx   ecx, word ptr [rcx+r14*4+8]
0x18015f95c  mov     word ptr [rbp+Buffer+6], cx
0x18015f960  mov     rcx, cs:ghInstance; hModule
0x18015f967  call    cs:__imp_SizeofResource
0x18015f96d  mov     rcx, [rsi+230h]
0x18015f974  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18015f978  mov     dword ptr [rbp+Buffer+8], eax
0x18015f97b  lea     rdx, [rbp+Buffer]; lpBuffer
0x18015f97f  mov     eax, [rsi+238h]
0x18015f985  mov     r8d, 10h; nNumberOfBytesToWrite
0x18015f98b  mov     dword ptr [rbp+Buffer+0Ch], r13d
0x18015f98f  mov     [rcx+r14*4+1Ch], eax
0x18015f994  mov     rcx, [rsi+220h]; hFile
0x18015f99b  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x18015f9a0  call    cs:__imp_WriteFile
0x18015f9a6  test    eax, eax
0x18015f9a8  jz      loc_18015FACF
0x18015f9ae  mov     r8d, dword ptr [rbp+Buffer+8]; nNumberOfBytesToWrite
0x18015f9b2  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18015f9b6  mov     rcx, [rsi+220h]; hFile
0x18015f9bd  mov     rdx, rdi; lpBuffer
0x18015f9c0  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x18015f9c5  call    cs:__imp_WriteFile
0x18015f9cb  test    eax, eax
0x18015f9cd  jz      loc_18015FACF
0x18015f9d3  mov     rax, [rsi+230h]
0x18015f9da  xor     r9d, r9d; dwMoveMethod
0x18015f9dd  mov     edx, [rsi+250h]
0x18015f9e3  xor     r8d, r8d; lpDistanceToMoveHigh
0x18015f9e6  mov     rcx, [rsi+248h]
0x18015f9ed  movzx   eax, word ptr [rax+r14*4+8]
0x18015f9f3  mov     [rcx+rdx*8], ax
0x18015f9f7  mov     edx, [rsi+250h]
0x18015f9fd  mov     eax, [rsi+238h]
0x18015fa03  mov     rcx, [rsi+248h]
0x18015fa0a  mov     [rcx+rdx*8+4], eax
0x18015fa0e  mov     rax, [rsi+228h]
0x18015fa15  add     [rsi+250h], r12d
0x18015fa1c  add     [rax+10h], r12d
0x18015fa20  mov     edx, [rbp+NumberOfBytesWritten]
0x18015fa23  mov     rcx, [rsi+220h]; hFile
0x18015fa2a  add     edx, 13h
0x18015fa2d  add     edx, [rsi+238h]
0x18015fa33  and     edx, 0FFFFFFFCh; lDistanceToMove
0x18015fa36  mov     [rsi+238h], edx
0x18015fa3c  call    cs:__imp_SetFilePointer
0x18015fa42  mov     [rsi+238h], eax
0x18015fa48  jmp     short loc_18015FA5D
0x18015fa4a  mov     rcx, [rsi+230h]
0x18015fa51  mov     [rcx+r14*4+1Ch], r13d
0x18015fa56  jmp     short loc_18015FA5D
0x18015fa58  mov     [rax+r14*4+1Ch], ecx
0x18015fa5d  mov     rcx, [rsi+230h]
0x18015fa64  mov     eax, [rsi+238h]
0x18015fa6a  mov     [rcx+r14*4+20h], eax
0x18015fa6f  mov     rdx, [r15+8]; lpBuffer
0x18015fa73  mov     rcx, [rsi+220h]; hFile
0x18015fa7a  test    rdx, rdx
0x18015fa7d  jnz     short loc_18015FA8D
0x18015fa7f  lea     rdx, [r15+0A0h]; lpFileName
0x18015fa86  call    FIWriteVar
0x18015fa8b  jmp     short loc_18015FA96
0x18015fa8d  mov     r8d, [r15+10h]
0x18015fa91  call    FIWriteRawVar
0x18015fa96  mov     [rbp+NumberOfBytesWritten], eax
0x18015fa99  test    eax, eax
0x18015fa9b  jz      short loc_18015FACF
0x18015fa9d  mov     edx, [rsi+238h]
0x18015faa3  xor     r9d, r9d; dwMoveMethod
0x18015faa6  mov     rcx, [rsi+220h]; hFile
0x18015faad  add     edx, 3
0x18015fab0  add     edx, eax
0x18015fab2  xor     r8d, r8d; lpDistanceToMoveHigh
0x18015fab5  and     edx, 0FFFFFFFCh; lDistanceToMove
0x18015fab8  mov     [rsi+238h], edx
0x18015fabe  call    cs:__imp_SetFilePointer
0x18015fac4  mov     [rsi+238h], eax
0x18015faca  mov     eax, r12d
0x18015facd  jmp     short loc_18015FAD1
0x18015facf  xor     eax, eax
0x18015fad1  mov     rcx, [rbp+var_8]
0x18015fad5  xor     rcx, rsp; StackCookie
0x18015fad8  call    __security_check_cookie
0x18015fadd  mov     rbx, [rsp+50h+arg_18]
0x18015fae5  add     rsp, 50h
0x18015fae9  pop     r15
0x18015faeb  pop     r14
0x18015faed  pop     r13
0x18015faef  pop     r12
0x18015faf1  pop     rdi
0x18015faf2  pop     rsi
0x18015faf3  pop     rbp
0x18015faf4  retn
```
