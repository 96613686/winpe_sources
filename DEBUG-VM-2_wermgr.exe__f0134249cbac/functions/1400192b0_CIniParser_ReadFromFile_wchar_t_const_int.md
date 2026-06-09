# CIniParser::ReadFromFile(wchar_t const *,int)

- ea: `0x1400192b0`
- end: `0x140019820`
- name: `?ReadFromFile@CIniParser@@QEAAJPEB_WH@Z`
- size: `1392`
- prototype: `int(CIniParser *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1400058ec`

## callees

- `0x140003224`
- `0x140003254`
- `0x14000db44`
- `0x14000e318`
- `0x14000e340`
- `0x14000e3e0`
- `0x1400192b0`
- `0x140019c58`
- `0x140019e3c`
- `0x14001a028`
- `0x14001a084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400193ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400193ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400197d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400197d1`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400193a1`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400193a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140019327`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140019327`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400194c9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400194c9`

## pseudocode

```c
__int64 __fastcall CIniParser::ReadFromFile(CIniParser *this, const wchar_t *a2, unsigned int a3)
{
  char *FileW; // rdi
  signed int LastError; // eax
  signed int v7; // esi
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  signed int v14; // eax
  wchar_t *v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  wchar_t *v19; // rcx
  DWORD v20; // edx
  wchar_t *v21; // rsi
  __int64 v22; // r14
  const wchar_t *v23; // rcx
  __int64 v24; // r8
  wchar_t *v25; // r8
  unsigned int v26; // r11d
  char v27; // r14
  __int64 v28; // rax
  unsigned int v29; // r9d
  wchar_t *v30; // rsi
  unsigned __int16 *v31; // r10
  unsigned int v32; // ecx
  unsigned int v33; // eax
  bool v34; // cf
  bool v35; // zf
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *v39; // [rsp+50h] [rbp-39h] BYREF
  wchar_t *v40; // [rsp+58h] [rbp-31h] BYREF
  wchar_t *v41; // [rsp+60h] [rbp-29h] BYREF
  void *v42[2]; // [rsp+68h] [rbp-21h] BYREF
  _WORD v43[12]; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v44[2]; // [rsp+90h] [rbp+7h] BYREF
  char v45[64]; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v46; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v47; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v48; // [rsp+108h] [rbp+7Fh] BYREF

  v47 = a3;
  v48 = 0;
  v46 = 0;
  v39 = 0;
  v41 = 0;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  if ( a2 && *a2 )
  {
    CStringMap::clear(this);
    FileW = (char *)CreateFileW(a2, 1u, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v7);
      return (unsigned int)v7;
    }
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v7);
      goto LABEL_84;
    }
    if ( FileSize.QuadPart > 0x400000uLL )
    {
      v7 = -2147483637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DI(*((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_84;
    }
    if ( FileSize.LowPart )
    {
      v12 = (wchar_t *)operator new[](FileSize.LowPart, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v12;
      if ( v12 )
      {
        if ( ReadFile(FileW, v12, FileSize.LowPart, &NumberOfBytesRead, 0) )
        {
          v19 = v13;
          v20 = NumberOfBytesRead >> 1;
          v47 = NumberOfBytesRead >> 1;
          v40 = v13;
          if ( NumberOfBytesRead >> 1 && *v13 == 0xFEFF )
          {
            v19 = v13 + 1;
            --v20;
            v40 = v13 + 1;
            v47 = v20;
          }
          while ( 1 )
          {
            if ( !UtilGetNextKeyValueW(v19, v20, &v39, &v48, &v41, &v46, &v40, &v47) )
            {
              v7 = 0;
              goto LABEL_71;
            }
            v21 = v41;
            v22 = v46;
            if ( v48 == 12 )
            {
              v15 = v39;
              v23 = L"MetadataHash";
              v24 = 12;
              while ( *v15 == *v23 )
              {
                ++v15;
                ++v23;
                if ( !--v24 )
                {
                  v25 = &v41[v46];
                  v26 = 0;
                  v27 = 0;
                  while ( 1 )
                  {
                    if ( v21 >= v25 )
                      goto LABEL_54;
                    if ( *v21 != 9 && *v21 != 10 && *v21 != 11 && *v21 != 12 && *v21 != 13 && *v21 != 32 )
                      break;
                    ++v21;
                  }
                  if ( *v21 != 45 )
                  {
LABEL_54:
                    v28 = 0;
                    v29 = 0x7FFFFFFF;
                    goto LABEL_55;
                  }
                  v28 = 1;
                  v29 = 0x80000000;
LABEL_55:
                  v30 = &v21[v28];
                  v31 = v30;
                  if ( v30 >= v25 )
                    goto LABEL_72;
                  do
                  {
                    v32 = *v30 - 48;
                    if ( v32 >= 0xA )
                      break;
                    v33 = 10 * v26;
                    v15 = (wchar_t *)(10 * v26 + v32);
                    v34 = v26 < 0x19999999;
                    v35 = v26 == 429496729;
                    v26 = (unsigned int)v15;
                    ++v30;
                    v27 |= !v34 && !v35 || (unsigned int)v15 < v33;
                  }
                  while ( v30 < v25 );
                  if ( v30 == v31 )
                  {
LABEL_72:
                    v18 = 22;
                  }
                  else
                  {
                    if ( !v27 && v26 <= v29 )
                      goto LABEL_68;
                    v18 = 34;
                  }
                  v7 = -2147024809;
                  v16 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v17 = 29;
                    goto LABEL_37;
                  }
                  goto LABEL_71;
                }
              }
            }
            v42[0] = v43;
            v43[0] = 0;
            v42[1] = v43;
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     v42,
                                     v39,
                                     v48) )
              break;
            v44[0] = v21;
            v44[1] = v22;
            if ( !*(_QWORD *)CStringMap::insert_or_assign(this, v45, v42, v44) )
              break;
            if ( v42[0] != v43 )
              operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_68:
            v20 = v47;
            v19 = v40;
          }
          v7 = -2147024882;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
              2147942414LL);
          if ( v42[0] != v43 )
            operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
        }
        else
        {
          v14 = GetLastError();
          v7 = v14;
          if ( v14 > 0 )
            v7 = (unsigned __int16)v14 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 27;
            v18 = (unsigned int)v7;
LABEL_37:
            WPP_SF_d(v16[2], v17, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v18);
          }
        }
LABEL_71:
        operator delete(v13, (const struct std::nothrow_t *)v15);
        goto LABEL_84;
      }
      v7 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_84:
        CloseHandle(FileW);
        return (unsigned int)v7;
      }
      v10 = 26;
      v11 = 2147942414LL;
    }
    else
    {
      v7 = -2147024883;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_84;
      v10 = 25;
      v11 = 2147942413LL;
    }
    WPP_SF_d(v9[2], v10, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v11);
    goto LABEL_84;
  }
  v7 = -2147024809;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400192b0  mov     [rsp-8+arg_10], r8d
0x1400192b5  push    rbp
0x1400192b6  push    rbx
0x1400192b7  push    rsi
0x1400192b8  push    rdi
0x1400192b9  push    r12
0x1400192bb  push    r14
0x1400192bd  push    r15
0x1400192bf  lea     rbp, [rsp-27h]
0x1400192c4  sub     rsp, 0B0h
0x1400192cb  xor     r12d, r12d
0x1400192ce  mov     rbx, rdx
0x1400192d1  mov     [rbp+57h+arg_18], r12d
0x1400192d5  mov     r15, rcx
0x1400192d8  mov     [rbp+57h+arg_8], r12d
0x1400192dc  mov     [rbp+57h+var_90], r12
0x1400192e0  mov     [rbp+57h+var_80], r12
0x1400192e4  mov     [rbp+57h+NumberOfBytesRead], r12d
0x1400192e8  mov     qword ptr [rbp+57h+FileSize], r12
0x1400192ec  test    rdx, rdx
0x1400192ef  jz      loc_1400197D9
0x1400192f5  cmp     [rdx], r12w
0x1400192f9  jz      loc_1400197D9
0x1400192ff  call    ?clear@CStringMap@@QEAAXXZ; CStringMap::clear(void)
0x140019304  lea     edx, [r12+1]; dwDesiredAccess
0x140019309  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x14001930e  mov     r8d, edx; dwShareMode
0x140019311  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140019319  xor     r9d, r9d; lpSecurityAttributes
0x14001931c  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x140019324  mov     rcx, rbx; lpFileName
0x140019327  call    cs:__imp_CreateFileW
0x14001932d  mov     rdi, rax
0x140019330  inc     rax
0x140019333  cmp     rax, 1
0x140019337  ja      short loc_14001939A
0x140019339  call    cs:__imp_GetLastError
0x14001933f  mov     esi, eax
0x140019341  test    eax, eax
0x140019343  jle     short loc_14001934E
0x140019345  movzx   esi, ax
0x140019348  or      esi, 80070000h
0x14001934e  test    esi, esi
0x140019350  mov     eax, 80004005h
0x140019355  cmovns  esi, eax
0x140019358  mov     rcx, cs:WPP_GLOBAL_Control
0x14001935f  lea     rax, WPP_GLOBAL_Control
0x140019366  cmp     rcx, rax
0x140019369  jz      loc_14001980C
0x14001936f  test    byte ptr [rcx+1Ch], 1
0x140019373  jz      loc_14001980C
0x140019379  mov     rcx, [rcx+10h]
0x14001937d  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x140019384  mov     edx, 16h
0x140019389  mov     [rsp+0E0h+dwCreationDisposition], esi
0x14001938d  mov     r9, rbx
0x140019390  call    WPP_SF_SD
0x140019395  jmp     loc_14001980C
0x14001939a  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x14001939e  mov     rcx, rdi; hFile
0x1400193a1  call    cs:__imp_GetFileSizeEx
0x1400193a7  test    eax, eax
0x1400193a9  jnz     short loc_14001940C
0x1400193ab  call    cs:__imp_GetLastError
0x1400193b1  mov     esi, eax
0x1400193b3  test    eax, eax
0x1400193b5  jle     short loc_1400193C0
0x1400193b7  movzx   esi, ax
0x1400193ba  or      esi, 80070000h
0x1400193c0  test    esi, esi
0x1400193c2  mov     eax, 80004005h
0x1400193c7  cmovns  esi, eax
0x1400193ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193d1  lea     rax, WPP_GLOBAL_Control
0x1400193d8  cmp     rcx, rax
0x1400193db  jz      loc_1400197CE
0x1400193e1  test    byte ptr [rcx+1Ch], 1
0x1400193e5  jz      loc_1400197CE
0x1400193eb  mov     rcx, [rcx+10h]
0x1400193ef  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1400193f6  mov     edx, 17h
0x1400193fb  mov     [rsp+0E0h+dwCreationDisposition], esi
0x1400193ff  mov     r9, rbx
0x140019402  call    WPP_SF_SD
0x140019407  jmp     loc_1400197CE
0x14001940c  cmp     dword ptr [rbp+57h+FileSize+4], r12d
0x140019410  jnz     loc_14001979E
0x140019416  mov     eax, dword ptr [rbp+57h+FileSize]
0x140019419  cmp     eax, 400000h
0x14001941e  ja      loc_14001979E
0x140019424  test    eax, eax
0x140019426  jnz     short loc_14001945B
0x140019428  mov     esi, 8007000Dh
0x14001942d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019434  lea     rax, WPP_GLOBAL_Control
0x14001943b  cmp     rcx, rax
0x14001943e  jz      loc_1400197CE
0x140019444  test    byte ptr [rcx+1Ch], 1
0x140019448  jz      loc_1400197CE
0x14001944e  mov     edx, 19h
0x140019453  mov     r9d, 8007000Dh
0x140019459  jmp     short loc_1400194A1
0x14001945b  mov     rcx, rax; unsigned __int64
0x14001945e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019465  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001946a  mov     rbx, rax
0x14001946d  test    rax, rax
0x140019470  jnz     short loc_1400194B6
0x140019472  mov     esi, 8007000Eh
0x140019477  mov     rcx, cs:WPP_GLOBAL_Control
0x14001947e  lea     rax, WPP_GLOBAL_Control
0x140019485  cmp     rcx, rax
0x140019488  jz      loc_1400197CE
0x14001948e  test    byte ptr [rcx+1Ch], 1
0x140019492  jz      loc_1400197CE
0x140019498  lea     edx, [rbx+1Ah]
0x14001949b  mov     r9d, 8007000Eh
0x1400194a1  mov     rcx, [rcx+10h]
0x1400194a5  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1400194ac  call    WPP_SF_d
0x1400194b1  jmp     loc_1400197CE
0x1400194b6  mov     r8d, dword ptr [rbp+57h+FileSize]; nNumberOfBytesToRead
0x1400194ba  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400194be  mov     rdx, rbx; lpBuffer
0x1400194c1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r12; lpOverlapped
0x1400194c6  mov     rcx, rdi; hFile
0x1400194c9  call    cs:__imp_ReadFile
0x1400194cf  test    eax, eax
0x1400194d1  jnz     short loc_140019530
0x1400194d3  call    cs:__imp_GetLastError
0x1400194d9  mov     esi, eax
0x1400194db  test    eax, eax
0x1400194dd  jle     short loc_1400194E8
0x1400194df  movzx   esi, ax
0x1400194e2  or      esi, 80070000h
0x1400194e8  test    esi, esi
0x1400194ea  mov     eax, 80004005h
0x1400194ef  cmovns  esi, eax
0x1400194f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400194f9  lea     rax, WPP_GLOBAL_Control
0x140019500  cmp     rcx, rax
0x140019503  jz      loc_140019708
0x140019509  test    byte ptr [rcx+1Ch], 1
0x14001950d  jz      loc_140019708
0x140019513  mov     edx, 1Bh
0x140019518  mov     r9d, esi
0x14001951b  mov     rcx, [rcx+10h]
0x14001951f  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x140019526  call    WPP_SF_d
0x14001952b  jmp     loc_140019708
0x140019530  mov     edx, [rbp+57h+NumberOfBytesRead]
0x140019533  mov     rcx, rbx
0x140019536  shr     edx, 1
0x140019538  mov     [rbp+57h+arg_10], edx
0x14001953b  mov     [rbp+57h+var_88], rbx
0x14001953f  jz      loc_1400196CC
0x140019545  mov     eax, 0FEFFh
0x14001954a  cmp     [rbx], ax
0x14001954d  jnz     loc_1400196CC
0x140019553  lea     rcx, [rbx+2]
0x140019557  dec     edx
0x140019559  mov     [rbp+57h+var_88], rcx
0x14001955d  mov     [rbp+57h+arg_10], edx
0x140019560  jmp     loc_1400196CC
0x140019565  mov     r9d, [rbp+57h+arg_18]
0x140019569  mov     rsi, [rbp+57h+var_80]
0x14001956d  mov     r14d, [rbp+57h+arg_8]
0x140019571  cmp     r9, 0Ch
0x140019575  jnz     loc_14001965A
0x14001957b  mov     rdx, [rbp+57h+var_90]
0x14001957f  lea     rcx, aMetadatahash; "MetadataHash"
0x140019586  mov     r8d, r9d
0x140019589  movzx   eax, word ptr [rcx]
0x14001958c  cmp     [rdx], ax
0x14001958f  jnz     loc_14001965A
0x140019595  add     rdx, 2
0x140019599  add     rcx, 2
0x14001959d  sub     r8, 1
0x1400195a1  jnz     short loc_140019589
0x1400195a3  lea     r8, [rsi+r14*2]
0x1400195a7  mov     r11d, r12d
0x1400195aa  mov     r14b, r12b
0x1400195ad  jmp     short loc_1400195D4
0x1400195af  movzx   ecx, word ptr [rsi]
0x1400195b2  sub     ecx, 9
0x1400195b5  jz      short loc_1400195D0
0x1400195b7  sub     ecx, 1
0x1400195ba  jz      short loc_1400195D0
0x1400195bc  sub     ecx, 1
0x1400195bf  jz      short loc_1400195D0
0x1400195c1  sub     ecx, 1
0x1400195c4  jz      short loc_1400195D0
0x1400195c6  sub     ecx, 1
0x1400195c9  jz      short loc_1400195D0
0x1400195cb  cmp     ecx, 13h
0x1400195ce  jnz     short loc_140019647
0x1400195d0  add     rsi, 2
0x1400195d4  cmp     rsi, r8
0x1400195d7  jb      short loc_1400195AF
0x1400195d9  mov     rax, r12
0x1400195dc  mov     r9d, 7FFFFFFFh
0x1400195e2  add     rsi, rax
0x1400195e5  mov     r10, rsi
0x1400195e8  cmp     rsi, r8
0x1400195eb  jnb     loc_140019715
0x1400195f1  movzx   ecx, word ptr [rsi]
0x1400195f4  add     ecx, 0FFFFFFD0h
0x1400195f7  cmp     ecx, 0Ah
0x1400195fa  jnb     short loc_140019625
0x1400195fc  lea     eax, [r11+r11*4]
0x140019600  add     eax, eax
0x140019602  lea     edx, [rax+rcx]
0x140019605  cmp     edx, eax
0x140019607  setb    cl
0x14001960a  cmp     r11d, 19999999h
0x140019611  mov     r11d, edx
0x140019614  setnbe  al
0x140019617  add     rsi, 2
0x14001961b  or      cl, al
0x14001961d  or      r14b, cl
0x140019620  cmp     rsi, r8
0x140019623  jb      short loc_1400195F1
0x140019625  cmp     rsi, r10
0x140019628  jz      loc_140019715
0x14001962e  test    r14b, r14b
0x140019631  jnz     short loc_14001963C
0x140019633  cmp     r11d, r9d
0x140019636  jbe     loc_1400196C5
0x14001963c  mov     r9d, 22h ; '"'
0x140019642  jmp     loc_14001971B
0x140019647  cmp     word ptr [rsi], 2Dh ; '-'
0x14001964b  jnz     short loc_1400195D9
0x14001964d  mov     eax, 2
0x140019652  mov     r9d, 80000000h
0x140019658  jmp     short loc_1400195E2
0x14001965a  mov     rdx, [rbp+57h+var_90]
0x14001965e  lea     rax, [rbp+57h+var_68]
0x140019662  mov     [rbp+57h+var_78], rax
0x140019666  lea     rcx, [rbp+57h+var_78]
0x14001966a  lea     rax, [rbp+57h+var_68]
0x14001966e  mov     [rbp+57h+var_68], r12w
0x140019673  mov     r8, r9
0x140019676  mov     [rbp+57h+var_70], rax
0x14001967a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14001967f  test    al, al
0x140019681  jz      loc_140019743
0x140019687  lea     r9, [rbp+57h+var_50]
0x14001968b  mov     [rbp+57h+var_50], rsi
0x14001968f  lea     r8, [rbp+57h+var_78]
0x140019693  mov     [rbp+57h+var_48], r14
0x140019697  lea     rdx, [rbp+57h+var_40]
0x14001969b  mov     rcx, r15
0x14001969e  call    ?insert_or_assign@CStringMap@@QEAA?AU?$pair@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@utl@@_N@utl@@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z; CStringMap::insert_or_assign(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1400196a3  cmp     [rax], r12
0x1400196a6  jz      loc_140019743
0x1400196ac  mov     rcx, [rbp+57h+var_78]; void *
0x1400196b0  lea     rax, [rbp+57h+var_68]
0x1400196b4  cmp     rcx, rax
0x1400196b7  jz      short loc_1400196C5
0x1400196b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400196c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400196c5  mov     edx, [rbp+57h+arg_10]; unsigned int
0x1400196c8  mov     rcx, [rbp+57h+var_88]; wchar_t *
0x1400196cc  lea     rax, [rbp+57h+arg_10]
0x1400196d0  mov     [rsp+0E0h+var_A8], rax; unsigned int *
0x1400196d5  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x1400196d9  lea     rax, [rbp+57h+var_88]
0x1400196dd  mov     [rsp+0E0h+hTemplateFile], rax; wchar_t **
0x1400196e2  lea     r8, [rbp+57h+var_90]; wchar_t **
0x1400196e6  lea     rax, [rbp+57h+arg_8]
0x1400196ea  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; unsigned int *
0x1400196ef  lea     rax, [rbp+57h+var_80]
0x1400196f3  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; wchar_t **
0x1400196f8  call    ?UtilGetNextKeyValueW@@YA_NPEA_WKPEAPEA_WPEAK1212@Z; UtilGetNextKeyValueW(wchar_t *,ulong,wchar_t * *,ulong *,wchar_t * *,ulong *,wchar_t * *,ulong *)
0x1400196fd  test    al, al
0x1400196ff  jnz     loc_140019565
0x140019705  mov     esi, r12d
0x140019708  mov     rcx, rbx; void *
0x14001970b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019710  jmp     loc_1400197CE
0x140019715  mov     r9d, 16h
0x14001971b  mov     esi, 80070057h
0x140019720  mov     rcx, cs:WPP_GLOBAL_Control
0x140019727  lea     rax, WPP_GLOBAL_Control
0x14001972e  cmp     rcx, rax
0x140019731  jz      short loc_140019708
0x140019733  test    byte ptr [rcx+1Ch], 1
0x140019737  jz      short loc_140019708
0x140019739  mov     edx, 1Dh
0x14001973e  jmp     loc_14001951B
0x140019743  mov     esi, 8007000Eh
0x140019748  mov     rcx, cs:WPP_GLOBAL_Control
0x14001974f  lea     rax, WPP_GLOBAL_Control
0x140019756  cmp     rcx, rax
0x140019759  jz      short loc_14001977C
0x14001975b  test    byte ptr [rcx+1Ch], 1
0x14001975f  jz      short loc_14001977C
0x140019761  mov     rcx, [rcx+10h]
0x140019765  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x14001976c  mov     edx, 1Ch
  ... truncated ...
```
