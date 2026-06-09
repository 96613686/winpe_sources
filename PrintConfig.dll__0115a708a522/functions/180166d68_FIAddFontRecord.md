# FIAddFontRecord

- ea: `0x180166d68`
- end: `0x180167212`
- name: `FIAddFontRecord`
- size: `1194`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180125868`
- `0x1801267b4`

## callees

- `0x180003400`
- `0x18012a714`
- `0x18012aa28`
- `0x18012aaec`
- `0x180166d68`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180166e5b`
- `KERNEL32!WriteFile` at `0x180166f1d`
- `KERNEL32!WriteFile` at `0x1801670a4`
- `KERNEL32!WriteFile` at `0x1801670cf`
- `KERNEL32!WriteFile` at `0x180166e5b`
- `KERNEL32!WriteFile` at `0x180166f1d`
- `KERNEL32!WriteFile` at `0x1801670a4`
- `KERNEL32!WriteFile` at `0x1801670cf`
- `KERNEL32!LoadResource` at `0x18016700c`
- `KERNEL32!LoadResource` at `0x18016700c`
- `KERNEL32!SizeofResource` at `0x180167065`
- `KERNEL32!SizeofResource` at `0x180167065`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180166e91`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180166f64`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18016714c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801671d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180166e91`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180166f64`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18016714c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801671d4`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18016701b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18016701b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180166fea`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180166fea`

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
    v36 = FIWriteRawVar(v35, v34, *(_DWORD *)(a3 + 16));
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
0x180166d68  mov     [rsp-38h+arg_18], rbx
0x180166d6d  push    rbp
0x180166d6e  push    rsi
0x180166d6f  push    rdi
0x180166d70  push    r12
0x180166d72  push    r13
0x180166d74  push    r14
0x180166d76  push    r15
0x180166d78  mov     rbp, rsp
0x180166d7b  sub     rsp, 50h
0x180166d7f  mov     rax, cs:__security_cookie
0x180166d86  xor     rax, rsp
0x180166d89  mov     [rbp+var_8], rax
0x180166d8d  xor     r13d, r13d
0x180166d90  mov     r12d, edx
0x180166d93  mov     [rbp+NumberOfBytesWritten], r13d
0x180166d97  mov     r15, r8
0x180166d9a  mov     rsi, rcx
0x180166d9d  test    rcx, rcx
0x180166da0  jz      loc_1801671EB
0x180166da6  cmp     dword ptr [rcx], 666E7469h
0x180166dac  jnz     loc_1801671EB
0x180166db2  test    byte ptr [rcx+23Ch], 2
0x180166db9  jz      loc_1801671EB
0x180166dbf  mov     rax, [rcx+230h]
0x180166dc6  lea     r14, [r12+r12*8]
0x180166dca  mov     dword ptr [rax+r14*4], 43455246h
0x180166dd2  mov     rax, [rcx+230h]
0x180166dd9  mov     word ptr [rax+r14*4+4], 24h ; '$'
0x180166de1  mov     rax, [rcx+230h]
0x180166de8  mov     [rax+r14*4+6], r12w
0x180166dee  movzx   eax, word ptr [r8+60h]
0x180166df3  mov     rcx, [rcx+230h]
0x180166dfa  mov     [rcx+r14*4+8], ax
0x180166e00  mov     rax, [rsi+230h]
0x180166e07  mov     word ptr [rax+r14*4+0Ah], 46h ; 'F'
0x180166e0f  mov     rax, [rsi+230h]
0x180166e16  mov     dword ptr [rax+r14*4+0Ch], 4946544Eh
0x180166e1f  mov     rdx, [r8+68h]; lpBuffer
0x180166e23  or      r8, 0FFFFFFFFFFFFFFFFh
0x180166e27  mov     rcx, [rsi+230h]
0x180166e2e  mov     eax, [rsi+238h]
0x180166e34  mov     [rcx+r14*4+10h], eax
0x180166e39  inc     r8
0x180166e3c  cmp     [rdx+r8*2], r13w
0x180166e41  jnz     short loc_180166E39
0x180166e43  mov     rcx, [rsi+220h]; hFile
0x180166e4a  lea     r8d, ds:2[r8*2]; nNumberOfBytesToWrite
0x180166e52  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180166e56  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x180166e5b  call    cs:__imp_WriteFile
0x180166e62  nop     dword ptr [rax+rax+00h]
0x180166e67  test    eax, eax
0x180166e69  jz      loc_1801671EB
0x180166e6f  mov     edx, [rbp+NumberOfBytesWritten]
0x180166e72  xor     r9d, r9d; dwMoveMethod
0x180166e75  mov     rcx, [rsi+220h]; hFile
0x180166e7c  add     edx, 3
0x180166e7f  add     edx, [rsi+238h]
0x180166e85  xor     r8d, r8d; lpDistanceToMoveHigh
0x180166e88  and     edx, 0FFFFFFFCh; lDistanceToMove
0x180166e8b  mov     [rsi+238h], edx
0x180166e91  call    cs:__imp_SetFilePointer
0x180166e98  nop     dword ptr [rax+rax+00h]
0x180166e9d  lea     r9, [rbp+var_1C]; lpNumberOfBytesWritten
0x180166ea1  mov     [rbp+var_1C], r13d
0x180166ea5  mov     [rsi+238h], eax
0x180166eab  lea     rdx, [rbp+Buffer]; lpBuffer
0x180166eaf  mov     rax, [rsi+230h]
0x180166eb6  mov     dword ptr [rbp+Buffer], 49464944h
0x180166ebd  mov     word ptr [rbp+Buffer+6], r12w
0x180166ec2  mov     dword ptr [rbp+Buffer+0Ch], r13d
0x180166ec6  mov     [rax+r14*4+14h], r13d
0x180166ecb  mov     rcx, [rsi+230h]
0x180166ed2  mov     eax, [rsi+238h]
0x180166ed8  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x180166edd  mov     [rcx+r14*4+18h], eax
0x180166ee2  mov     ecx, 10h
0x180166ee7  mov     r8d, [r15+80h]
0x180166eee  add     r8d, [r15+70h]
0x180166ef2  add     r8d, [r15+50h]
0x180166ef6  add     r8d, [r15+40h]
0x180166efa  add     r8d, [r15+30h]
0x180166efe  mov     eax, [r15+20h]
0x180166f02  mov     rdi, [rsi+220h]
0x180166f09  add     eax, 3Ch ; '<'
0x180166f0c  add     r8d, eax
0x180166f0f  mov     word ptr [rbp+Buffer+4], cx
0x180166f13  mov     dword ptr [rbp+Buffer+8], r8d
0x180166f17  mov     r8d, ecx; nNumberOfBytesToWrite
0x180166f1a  mov     rcx, rdi; hFile
0x180166f1d  call    cs:__imp_WriteFile
0x180166f24  nop     dword ptr [rax+rax+00h]
0x180166f29  lea     rdx, [r15+18h]; struct _FI_DATA *
0x180166f2d  mov     rcx, rdi; void *
0x180166f30  call    ?iWriteFDH@@YAHPEAXPEBU_FI_DATA@@@Z; iWriteFDH(void *,_FI_DATA const *)
0x180166f35  lea     ecx, [rax+10h]
0x180166f38  mov     [rbp+NumberOfBytesWritten], ecx
0x180166f3b  test    ecx, ecx
0x180166f3d  jz      loc_1801671EB
0x180166f43  mov     edx, [rsi+238h]
0x180166f49  xor     r9d, r9d; dwMoveMethod
0x180166f4c  add     edx, 3
0x180166f4f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180166f52  add     edx, ecx
0x180166f54  mov     rcx, [rsi+220h]; hFile
0x180166f5b  and     edx, 0FFFFFFFCh; lDistanceToMove
0x180166f5e  mov     [rsi+238h], edx
0x180166f64  call    cs:__imp_SetFilePointer
0x180166f6b  nop     dword ptr [rax+rax+00h]
0x180166f70  mov     r8d, [rsi+250h]
0x180166f77  mov     ecx, r13d
0x180166f7a  mov     [rsi+238h], eax
0x180166f80  mov     r12d, 1
0x180166f86  test    r8d, r8d
0x180166f89  jz      short loc_180166FBD
0x180166f8b  mov     rax, [rsi+230h]
0x180166f92  mov     rdx, [rsi+248h]
0x180166f99  movzx   r9d, word ptr [rax+r14*4+8]
0x180166f9f  mov     eax, ecx
0x180166fa1  cmp     [rdx+rax*8], r9w
0x180166fa6  jz      short loc_180166FB9
0x180166fa8  add     ecx, r12d
0x180166fab  cmp     ecx, r8d
0x180166fae  jb      short loc_180166F9F
0x180166fb0  mov     rax, [rsi+230h]
0x180166fb7  jmp     short loc_180166FCC
0x180166fb9  mov     ecx, [rdx+rax*8+4]
0x180166fbd  mov     rax, [rsi+230h]
0x180166fc4  test    ecx, ecx
0x180166fc6  jnz     loc_18016716E
0x180166fcc  movzx   ecx, word ptr [rax+r14*4+8]
0x180166fd2  test    cx, cx
0x180166fd5  jle     loc_180167160
0x180166fdb  mov     edx, ecx; lpName
0x180166fdd  mov     r8d, 103h; lpType
0x180166fe3  mov     rcx, cs:ghInstance; hModule
0x180166fea  call    cs:__imp_FindResourceW
0x180166ff1  nop     dword ptr [rax+rax+00h]
0x180166ff6  mov     rbx, rax
0x180166ff9  test    rax, rax
0x180166ffc  jz      loc_1801671EB
0x180167002  mov     rcx, cs:ghInstance; hModule
0x180167009  mov     rdx, rax; hResInfo
0x18016700c  call    cs:__imp_LoadResource
0x180167013  nop     dword ptr [rax+rax+00h]
0x180167018  mov     rcx, rax; hResData
0x18016701b  call    cs:__imp_LockResource
0x180167022  nop     dword ptr [rax+rax+00h]
0x180167027  mov     rcx, [rsi+230h]
0x18016702e  mov     rdi, rax
0x180167031  test    rax, rax
0x180167034  jz      loc_180167167
0x18016703a  xorps   xmm0, xmm0
0x18016703d  mov     eax, 10h
0x180167042  movups  [rbp+Buffer], xmm0
0x180167046  mov     dword ptr [rbp+Buffer], 54544344h
0x18016704d  mov     rdx, rbx; hResInfo
0x180167050  mov     word ptr [rbp+Buffer+4], ax
0x180167054  movzx   ecx, word ptr [rcx+r14*4+8]
0x18016705a  mov     word ptr [rbp+Buffer+6], cx
0x18016705e  mov     rcx, cs:ghInstance; hModule
0x180167065  call    cs:__imp_SizeofResource
0x18016706c  nop     dword ptr [rax+rax+00h]
0x180167071  mov     rcx, [rsi+230h]
0x180167078  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18016707c  mov     dword ptr [rbp+Buffer+8], eax
0x18016707f  lea     rdx, [rbp+Buffer]; lpBuffer
0x180167083  mov     eax, [rsi+238h]
0x180167089  mov     r8d, 10h; nNumberOfBytesToWrite
0x18016708f  mov     dword ptr [rbp+Buffer+0Ch], r13d
0x180167093  mov     [rcx+r14*4+1Ch], eax
0x180167098  mov     rcx, [rsi+220h]; hFile
0x18016709f  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x1801670a4  call    cs:__imp_WriteFile
0x1801670ab  nop     dword ptr [rax+rax+00h]
0x1801670b0  test    eax, eax
0x1801670b2  jz      loc_1801671EB
0x1801670b8  mov     r8d, dword ptr [rbp+Buffer+8]; nNumberOfBytesToWrite
0x1801670bc  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801670c0  mov     rcx, [rsi+220h]; hFile
0x1801670c7  mov     rdx, rdi; lpBuffer
0x1801670ca  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x1801670cf  call    cs:__imp_WriteFile
0x1801670d6  nop     dword ptr [rax+rax+00h]
0x1801670db  test    eax, eax
0x1801670dd  jz      loc_1801671EB
0x1801670e3  mov     rax, [rsi+230h]
0x1801670ea  xor     r9d, r9d; dwMoveMethod
0x1801670ed  mov     edx, [rsi+250h]
0x1801670f3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801670f6  mov     rcx, [rsi+248h]
0x1801670fd  movzx   eax, word ptr [rax+r14*4+8]
0x180167103  mov     [rcx+rdx*8], ax
0x180167107  mov     edx, [rsi+250h]
0x18016710d  mov     eax, [rsi+238h]
0x180167113  mov     rcx, [rsi+248h]
0x18016711a  mov     [rcx+rdx*8+4], eax
0x18016711e  mov     rax, [rsi+228h]
0x180167125  add     [rsi+250h], r12d
0x18016712c  add     [rax+10h], r12d
0x180167130  mov     edx, [rbp+NumberOfBytesWritten]
0x180167133  mov     rcx, [rsi+220h]; hFile
0x18016713a  add     edx, 13h
0x18016713d  add     edx, [rsi+238h]
0x180167143  and     edx, 0FFFFFFFCh; lDistanceToMove
0x180167146  mov     [rsi+238h], edx
0x18016714c  call    cs:__imp_SetFilePointer
0x180167153  nop     dword ptr [rax+rax+00h]
0x180167158  mov     [rsi+238h], eax
0x18016715e  jmp     short loc_180167173
0x180167160  mov     rcx, [rsi+230h]
0x180167167  mov     [rcx+r14*4+1Ch], r13d
0x18016716c  jmp     short loc_180167173
0x18016716e  mov     [rax+r14*4+1Ch], ecx
0x180167173  mov     rcx, [rsi+230h]
0x18016717a  mov     eax, [rsi+238h]
0x180167180  mov     [rcx+r14*4+20h], eax
0x180167185  mov     rdx, [r15+8]; lpBuffer
0x180167189  mov     rcx, [rsi+220h]; hFile
0x180167190  test    rdx, rdx
0x180167193  jnz     short loc_1801671A3
0x180167195  lea     rdx, [r15+0A0h]; lpFileName
0x18016719c  call    FIWriteVar
0x1801671a1  jmp     short loc_1801671AC
0x1801671a3  mov     r8d, [r15+10h]
0x1801671a7  call    FIWriteRawVar
0x1801671ac  mov     [rbp+NumberOfBytesWritten], eax
0x1801671af  test    eax, eax
0x1801671b1  jz      short loc_1801671EB
0x1801671b3  mov     edx, [rsi+238h]
0x1801671b9  xor     r9d, r9d; dwMoveMethod
0x1801671bc  mov     rcx, [rsi+220h]; hFile
0x1801671c3  add     edx, 3
0x1801671c6  add     edx, eax
0x1801671c8  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801671cb  and     edx, 0FFFFFFFCh; lDistanceToMove
0x1801671ce  mov     [rsi+238h], edx
0x1801671d4  call    cs:__imp_SetFilePointer
0x1801671db  nop     dword ptr [rax+rax+00h]
0x1801671e0  mov     [rsi+238h], eax
0x1801671e6  mov     eax, r12d
0x1801671e9  jmp     short loc_1801671ED
0x1801671eb  xor     eax, eax
0x1801671ed  mov     rcx, [rbp+var_8]
0x1801671f1  xor     rcx, rsp; StackCookie
0x1801671f4  call    __security_check_cookie
0x1801671f9  mov     rbx, [rsp+50h+arg_18]
0x180167201  add     rsp, 50h
0x180167205  pop     r15
0x180167207  pop     r14
0x180167209  pop     r13
0x18016720b  pop     r12
0x18016720d  pop     rdi
0x18016720e  pop     rsi
0x18016720f  pop     rbp
0x180167210  retn
```
