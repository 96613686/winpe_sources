# WriteRoamingData(ushort const *,ulong,ulong,ushort const *,FILETIMEEX *,FILETIMEEX *,FILETIMEEX *,int)

- ea: `0x18011a46c`
- end: `0x18011a8e2`
- name: `?WriteRoamingData@@YAJPEBGKK0PEATFILETIMEEX@@11H@Z`
- size: `1142`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, union FILETIMEEX *, union FILETIMEEX *, union FILETIMEEX *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c810`

## callees

- `0x180019ac4`
- `0x180025910`
- `0x180025980`
- `0x180027ec0`
- `0x1800701d0`
- `0x1800e0d10`
- `0x18011a46c`
- `0x18011a8e8`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801ab374`
- `0x1801abbac`
- `0x1801dc570`
- `0x1801e1790`
- `0x1801e21a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011a7e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011a7e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18011a829`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18011a829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011a860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011a89c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011a860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011a89c`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18011a566`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18011a566`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18011a5b4`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18011a5b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18011a6b8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18011a6b8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011a714`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011a714`

## pseudocode

```c
__int64 __fastcall WriteRoamingData(
        unsigned __int16 *a1,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        union FILETIMEEX *a5,
        union FILETIMEEX *a6,
        union FILETIMEEX *a7,
        int a8)
{
  WCHAR *v10; // rdi
  __int64 v11; // rbx
  signed int ProcessUserSID; // esi
  int LastError; // eax
  int v14; // edx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r15
  DWORD v18; // r12d
  WCHAR *Heap; // rax
  WCHAR *v20; // r14
  int v21; // eax
  int v22; // eax
  HANDLE FileW; // rax
  int v24; // eax
  int v25; // eax
  PSID pSourceSid; // [rsp+50h] [rbp-49h] BYREF
  int v28; // [rsp+58h] [rbp-41h]
  int v29; // [rsp+5Ch] [rbp-3Dh]
  WCHAR *v30; // [rsp+60h] [rbp-39h] BYREF
  int v31; // [rsp+6Ch] [rbp-2Dh]
  unsigned __int16 v32[2]; // [rsp+70h] [rbp-29h] BYREF
  DWORD nSize; // [rsp+74h] [rbp-25h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-21h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp-11h] BYREF

  v29 = a3;
  pSourceSid = 0;
  v28 = a2;
  lpFileName[0] = &Data;
  v10 = 0;
  lpFileName[1] = 0;
  v11 = -1;
  v30 = 0;
  nSize = 0;
  NumberOfBytesWritten = 0;
  *(_DWORD *)v32 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SDDSiii((_DWORD)a1, a2, a3, (_DWORD)a1, a2, a3, (__int64)a4, *(_QWORD *)a5, *(_QWORD *)a6, *(_QWORD *)a7);
  if ( !a1 || !*a1 )
  {
    ProcessUserSID = 1;
    goto LABEL_62;
  }
  ProcessUserSID = DetermineRoamingFilename(a1, (struct CWxString *)lpFileName, v32);
  if ( ProcessUserSID < 0 )
  {
    HIDWORD(pSourceSid) = 261;
    goto LABEL_62;
  }
  if ( !*(_DWORD *)v32 )
    goto LABEL_26;
  if ( a8 )
  {
    if ( !CreateHardLinkW(lpFileName[0], a1, 0) )
    {
      LastError = WxGetLastError();
      ProcessUserSID = LastError;
      if ( LastError > 0 )
        ProcessUserSID = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(pSourceSid) = 267;
      if ( ProcessUserSID >= 0 )
        ProcessUserSID = -2147418113;
      goto LABEL_62;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
      goto LABEL_26;
    v14 = 17;
    goto LABEL_25;
  }
  if ( CopyFileW(a1, lpFileName[0], 0) )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
      goto LABEL_26;
    v14 = 18;
LABEL_25:
    WPP_SF_SS(1036, v14, (unsigned int)&WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids, lpFileName[0], (__int64)a1);
LABEL_26:
    ProcessUserSID = ReplaceExtension((CWxString *)lpFileName);
    if ( ProcessUserSID >= 0 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a4[v17] );
      v18 = 2 * v17 + 150;
      v31 = 0;
      Heap = (WCHAR *)WxAllocateHeapEx(v16, v18);
      v20 = Heap;
      if ( Heap )
      {
        memset_0(Heap, 0, (unsigned int)(2 * v17 + 150));
        v10 = v20;
        v30 = v20;
        *(_DWORD *)v20 = 515902494;
        *((_DWORD *)v20 + 1) = 1966097;
        nSize = 16;
        if ( GetComputerNameW(v20 + 6, &nSize) )
        {
          ProcessUserSID = WxGetProcessUserSID((struct _SID **)&pSourceSid);
          if ( ProcessUserSID >= 0 )
          {
            if ( CopySid(0x44u, v20 + 22, pSourceSid) )
            {
              *((_DWORD *)v20 + 28) = v28;
              *((_DWORD *)v20 + 29) = v29;
              *((_QWORD *)v20 + 15) = *(_QWORD *)a5;
              *((_QWORD *)v20 + 16) = *(_QWORD *)a6;
              *((_QWORD *)v20 + 17) = *(_QWORD *)a7;
              *((_DWORD *)v20 + 36) = v17;
              ProcessUserSID = StringCchCopyW(v20 + 74, (unsigned int)(v17 + 1), a4);
              if ( ProcessUserSID >= 0 )
              {
                *((_DWORD *)v20 + 2) = crc32(0, v20, v18);
                FileW = CreateFileW(lpFileName[0], 0x40000000u, 0, 0, 2u, 0x2006u, 0);
                v11 = (__int64)FileW;
                if ( FileW == (HANDLE)-1LL )
                {
                  v24 = WxGetLastError();
                  ProcessUserSID = v24;
                  if ( v24 > 0 )
                    ProcessUserSID = (unsigned __int16)v24 | 0x80070000;
                  HIDWORD(pSourceSid) = 348;
                  if ( ProcessUserSID >= 0 )
                    ProcessUserSID = -2147418113;
                }
                else if ( WriteFile(FileW, v20, v18, &NumberOfBytesWritten, 0) )
                {
                  ProcessUserSID = 0;
                  CloseHandle((HANDLE)v11);
                  v11 = -1;
                }
                else
                {
                  v25 = WxGetLastError();
                  ProcessUserSID = v25;
                  if ( v25 > 0 )
                    ProcessUserSID = (unsigned __int16)v25 | 0x80070000;
                  HIDWORD(pSourceSid) = 349;
                  if ( ProcessUserSID >= 0 )
                    ProcessUserSID = -2147418113;
                }
              }
              else
              {
                HIDWORD(pSourceSid) = 329;
              }
            }
            else
            {
              v22 = WxGetLastError();
              ProcessUserSID = v22;
              if ( v22 > 0 )
                ProcessUserSID = (unsigned __int16)v22 | 0x80070000;
              HIDWORD(pSourceSid) = 316;
              if ( ProcessUserSID >= 0 )
                ProcessUserSID = -2147418113;
            }
          }
          else
          {
            HIDWORD(pSourceSid) = 313;
          }
        }
        else
        {
          v21 = WxGetLastError();
          ProcessUserSID = v21;
          if ( v21 > 0 )
            ProcessUserSID = (unsigned __int16)v21 | 0x80070000;
          HIDWORD(pSourceSid) = 310;
          if ( ProcessUserSID >= 0 )
            ProcessUserSID = -2147418113;
        }
      }
      else
      {
        v31 = 76;
        ProcessUserSID = -2147024882;
        HIDWORD(pSourceSid) = 299;
      }
    }
    else
    {
      HIDWORD(pSourceSid) = 291;
    }
    goto LABEL_62;
  }
  v15 = WxGetLastError();
  ProcessUserSID = v15;
  if ( v15 > 0 )
    ProcessUserSID = (unsigned __int16)v15 | 0x80070000;
  HIDWORD(pSourceSid) = 277;
  if ( ProcessUserSID >= 0 )
    ProcessUserSID = -2147418113;
LABEL_62:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 19, &WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids, (unsigned int)ProcessUserSID);
  if ( v11 != -1 )
    CloseHandle((HANDLE)v11);
  if ( v10 )
    WxFreeHeapEx(&v30);
  CWxString::_Release((CWxString *)lpFileName);
  return (unsigned int)ProcessUserSID;
}

```

## disassembly

```asm
0x18011a46c  mov     [rsp-8+arg_8], rbx
0x18011a471  push    rbp
0x18011a472  push    rsi
0x18011a473  push    rdi
0x18011a474  push    r12
0x18011a476  push    r13
0x18011a478  push    r14
0x18011a47a  push    r15
0x18011a47c  lea     rbp, [rsp-7]
0x18011a481  sub     rsp, 0A0h
0x18011a488  mov     rax, cs:__security_cookie
0x18011a48f  xor     rax, rsp
0x18011a492  mov     [rbp+37h+var_40], rax
0x18011a496  xor     r15d, r15d
0x18011a499  mov     [rbp+37h+var_74], r8d
0x18011a49d  lea     rax, Data
0x18011a4a4  mov     dword ptr [rbp+37h+pSourceSid+4], r15d
0x18011a4a8  mov     [rbp-49h], r15
0x18011a4ac  mov     r13, r9
0x18011a4af  mov     [rbp+37h+var_78], edx
0x18011a4b2  mov     r14, rcx
0x18011a4b5  mov     [rbp+37h+lpFileName], rax
0x18011a4b9  mov     edi, r15d
0x18011a4bc  mov     [rbp+37h+var_50], r15
0x18011a4c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011a4c4  mov     [rbp+37h+var_70], r15
0x18011a4c8  mov     [rbp+37h+nSize], r15d
0x18011a4cc  mov     [rbp+37h+NumberOfBytesWritten], r15d
0x18011a4d0  mov     dword ptr [rbp+37h+var_60], r15d
0x18011a4d4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011a4db  jz      short loc_18011A517
0x18011a4dd  mov     rax, [rbp+37h+arg_30]
0x18011a4e1  mov     rax, [rax]
0x18011a4e4  mov     [rsp+0D0h+var_88], rax
0x18011a4e9  mov     rax, [rbp+37h+arg_28]
0x18011a4ed  mov     rax, [rax]
0x18011a4f0  mov     [rsp+0D0h+var_90], rax
0x18011a4f5  mov     rax, [rbp+37h+arg_20]
0x18011a4f9  mov     rax, [rax]
0x18011a4fc  mov     [rsp+0D0h+var_98], rax
0x18011a501  mov     [rsp+0D0h+hTemplateFile], r9
0x18011a506  mov     r9, rcx
0x18011a509  mov     [rsp+0D0h+dwFlagsAndAttributes], r8d
0x18011a50e  mov     [rsp+0D0h+dwCreationDisposition], edx
0x18011a512  call    WPP_SF_SDDSiii
0x18011a517  test    r14, r14
0x18011a51a  jz      loc_18011A86C
0x18011a520  cmp     [r14], r15w
0x18011a524  jz      loc_18011A86C
0x18011a52a  lea     r8, [rbp+37h+var_60]; unsigned __int16 *
0x18011a52e  mov     rcx, r14; unsigned __int16 *
0x18011a531  lea     rdx, [rbp+37h+lpFileName]; struct CWxString *
0x18011a535  call    DetermineRoamingFilename
0x18011a53a  mov     esi, eax
0x18011a53c  test    eax, eax
0x18011a53e  jns     short loc_18011A54C
0x18011a540  mov     dword ptr [rbp+37h+pSourceSid+4], 105h
0x18011a547  jmp     loc_18011A871
0x18011a54c  cmp     dword ptr [rbp+37h+var_60], r15d
0x18011a550  jz      loc_18011A610
0x18011a556  cmp     [rbp+37h+arg_38], r15d
0x18011a55a  jz      short loc_18011A5AA
0x18011a55c  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x18011a560  xor     r8d, r8d; lpSecurityAttributes
0x18011a563  mov     rdx, r14; lpExistingFileName
0x18011a566  call    cs:__imp_CreateHardLinkW
0x18011a56c  test    eax, eax
0x18011a56e  jnz     short loc_18011A59A
0x18011a570  call    WxGetLastError
0x18011a575  mov     esi, eax
0x18011a577  test    eax, eax
0x18011a579  jle     short loc_18011A584
0x18011a57b  movzx   esi, ax
0x18011a57e  or      esi, 80070000h
0x18011a584  test    esi, esi
0x18011a586  mov     dword ptr [rbp+37h+pSourceSid+4], 10Bh
0x18011a58d  mov     eax, 8000FFFFh
0x18011a592  cmovns  esi, eax
0x18011a595  jmp     loc_18011A871
0x18011a59a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011a5a1  jz      short loc_18011A610
0x18011a5a3  mov     edx, 11h
0x18011a5a8  jmp     short loc_18011A5F6
0x18011a5aa  mov     rdx, [rbp+37h+lpFileName]; lpNewFileName
0x18011a5ae  xor     r8d, r8d; bFailIfExists
0x18011a5b1  mov     rcx, r14; lpExistingFileName
0x18011a5b4  call    cs:__imp_CopyFileW
0x18011a5ba  test    eax, eax
0x18011a5bc  jnz     short loc_18011A5E8
0x18011a5be  call    WxGetLastError
0x18011a5c3  mov     esi, eax
0x18011a5c5  test    eax, eax
0x18011a5c7  jle     short loc_18011A5D2
0x18011a5c9  movzx   esi, ax
0x18011a5cc  or      esi, 80070000h
0x18011a5d2  test    esi, esi
0x18011a5d4  mov     dword ptr [rbp+37h+pSourceSid+4], 115h
0x18011a5db  mov     eax, 8000FFFFh
0x18011a5e0  cmovns  esi, eax
0x18011a5e3  jmp     loc_18011A871
0x18011a5e8  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011a5ef  jz      short loc_18011A610
0x18011a5f1  mov     edx, 12h
0x18011a5f6  mov     r9, [rbp+37h+lpFileName]
0x18011a5fa  lea     r8, WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids
0x18011a601  mov     ecx, 40Ch
0x18011a606  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r14
0x18011a60b  call    WPP_SF_SS
0x18011a610  lea     r9, aDat_0; ".dat"
0x18011a617  mov     r8d, 7
0x18011a61d  lea     rdx, aCookie_5; ".cookie"
0x18011a624  lea     rcx, [rbp+37h+lpFileName]; this
0x18011a628  call    ReplaceExtension
0x18011a62d  mov     esi, eax
0x18011a62f  test    eax, eax
0x18011a631  jns     short loc_18011A63F
0x18011a633  mov     dword ptr [rbp+37h+pSourceSid+4], 123h
0x18011a63a  jmp     loc_18011A871
0x18011a63f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18011a643  xor     eax, eax
0x18011a645  inc     r15
0x18011a648  cmp     [r13+r15*2+0], ax
0x18011a64e  jnz     short loc_18011A645
0x18011a650  lea     r12d, ds:96h[r15*2]
0x18011a658  mov     [rbp+37h+var_64], eax
0x18011a65b  mov     edx, r12d
0x18011a65e  mov     esi, r12d
0x18011a661  call    WxAllocateHeapEx
0x18011a666  mov     r14, rax
0x18011a669  test    rax, rax
0x18011a66c  jnz     short loc_18011A686
0x18011a66e  mov     [rbp+37h+var_64], 4Ch ; 'L'
0x18011a675  mov     esi, 8007000Eh
0x18011a67a  mov     dword ptr [rbp+37h+pSourceSid+4], 12Bh
0x18011a681  jmp     loc_18011A871
0x18011a686  mov     r8, rsi; Size
0x18011a689  xor     edx, edx; Val
0x18011a68b  mov     rcx, r14; void *
0x18011a68e  call    memset_0
0x18011a693  mov     rdi, r14
0x18011a696  mov     [rbp+37h+var_70], r14
0x18011a69a  mov     dword ptr [r14], 1EC00C1Eh
0x18011a6a1  lea     rcx, [r14+0Ch]; lpBuffer
0x18011a6a5  mov     dword ptr [r14+4], 1E0011h
0x18011a6ad  lea     rdx, [rbp+37h+nSize]; nSize
0x18011a6b1  mov     [rbp+37h+nSize], 10h
0x18011a6b8  call    cs:__imp_GetComputerNameW
0x18011a6be  test    eax, eax
0x18011a6c0  jnz     short loc_18011A6EC
0x18011a6c2  call    WxGetLastError
0x18011a6c7  mov     esi, eax
0x18011a6c9  test    eax, eax
0x18011a6cb  jle     short loc_18011A6D6
0x18011a6cd  movzx   esi, ax
0x18011a6d0  or      esi, 80070000h
0x18011a6d6  test    esi, esi
0x18011a6d8  mov     dword ptr [rbp+37h+pSourceSid+4], 136h
0x18011a6df  mov     eax, 8000FFFFh
0x18011a6e4  cmovns  esi, eax
0x18011a6e7  jmp     loc_18011A871
0x18011a6ec  lea     rcx, [rbp+37h+pSourceSid]; struct _SID **
0x18011a6f0  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x18011a6f5  mov     esi, eax
0x18011a6f7  test    eax, eax
0x18011a6f9  jns     short loc_18011A707
0x18011a6fb  mov     dword ptr [rbp+37h+pSourceSid+4], 139h
0x18011a702  jmp     loc_18011A871
0x18011a707  mov     r8, [rbp+37h+pSourceSid]; pSourceSid
0x18011a70b  lea     rdx, [r14+2Ch]; pDestinationSid
0x18011a70f  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18011a714  call    cs:__imp_CopySid
0x18011a71a  test    eax, eax
0x18011a71c  jnz     short loc_18011A748
0x18011a71e  call    WxGetLastError
0x18011a723  mov     esi, eax
0x18011a725  test    eax, eax
0x18011a727  jle     short loc_18011A732
0x18011a729  movzx   esi, ax
0x18011a72c  or      esi, 80070000h
0x18011a732  test    esi, esi
0x18011a734  mov     dword ptr [rbp+37h+pSourceSid+4], 13Ch
0x18011a73b  mov     eax, 8000FFFFh
0x18011a740  cmovns  esi, eax
0x18011a743  jmp     loc_18011A871
0x18011a748  mov     eax, [rbp+37h+var_78]
0x18011a74b  lea     edx, [r15+1]; unsigned __int64
0x18011a74f  mov     [r14+70h], eax
0x18011a753  lea     rcx, [r14+94h]; unsigned __int16 *
0x18011a75a  mov     eax, [rbp+37h+var_74]
0x18011a75d  mov     r8, r13; unsigned __int16 *
0x18011a760  mov     [r14+74h], eax
0x18011a764  mov     rax, [rbp+37h+arg_20]
0x18011a768  mov     rax, [rax]
0x18011a76b  mov     [r14+78h], rax
0x18011a76f  mov     rax, [rbp+37h+arg_28]
0x18011a773  mov     rax, [rax]
0x18011a776  mov     [r14+80h], rax
0x18011a77d  mov     rax, [rbp+37h+arg_30]
0x18011a781  mov     rax, [rax]
0x18011a784  mov     [r14+88h], rax
0x18011a78b  mov     [r14+90h], r15d
0x18011a792  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18011a797  xor     r15d, r15d
0x18011a79a  mov     esi, eax
0x18011a79c  test    eax, eax
0x18011a79e  jns     short loc_18011A7AC
0x18011a7a0  mov     dword ptr [rbp+37h+pSourceSid+4], 149h
0x18011a7a7  jmp     loc_18011A871
0x18011a7ac  mov     r8d, r12d
0x18011a7af  mov     rdx, r14
0x18011a7b2  xor     ecx, ecx
0x18011a7b4  call    crc32
0x18011a7b9  mov     [r14+8], eax
0x18011a7bd  xor     r9d, r9d; lpSecurityAttributes
0x18011a7c0  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x18011a7c4  xor     r8d, r8d; dwShareMode
0x18011a7c7  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x18011a7cc  mov     edx, 40000000h; dwDesiredAccess
0x18011a7d1  mov     [rsp+0D0h+dwFlagsAndAttributes], 2006h; dwFlagsAndAttributes
0x18011a7d9  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18011a7e1  call    cs:__imp_CreateFileW
0x18011a7e7  mov     rbx, rax
0x18011a7ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011a7ee  jnz     short loc_18011A817
0x18011a7f0  call    WxGetLastError
0x18011a7f5  mov     esi, eax
0x18011a7f7  test    eax, eax
0x18011a7f9  jle     short loc_18011A804
0x18011a7fb  movzx   esi, ax
0x18011a7fe  or      esi, 80070000h
0x18011a804  test    esi, esi
0x18011a806  mov     dword ptr [rbp+37h+pSourceSid+4], 15Ch
0x18011a80d  mov     eax, 8000FFFFh
0x18011a812  cmovns  esi, eax
0x18011a815  jmp     short loc_18011A871
0x18011a817  lea     r9, [rbp+37h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18011a81b  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOverlapped
0x18011a820  mov     r8d, r12d; nNumberOfBytesToWrite
0x18011a823  mov     rdx, r14; lpBuffer
0x18011a826  mov     rcx, rbx; hFile
0x18011a829  call    cs:__imp_WriteFile
0x18011a82f  test    eax, eax
0x18011a831  jnz     short loc_18011A85A
0x18011a833  call    WxGetLastError
0x18011a838  mov     esi, eax
0x18011a83a  test    eax, eax
0x18011a83c  jle     short loc_18011A847
0x18011a83e  movzx   esi, ax
0x18011a841  or      esi, 80070000h
0x18011a847  test    esi, esi
0x18011a849  mov     dword ptr [rbp+37h+pSourceSid+4], 15Dh
0x18011a850  mov     eax, 8000FFFFh
0x18011a855  cmovns  esi, eax
0x18011a858  jmp     short loc_18011A871
0x18011a85a  mov     rcx, rbx; hObject
0x18011a85d  mov     esi, r15d
0x18011a860  call    cs:__imp_CloseHandle
0x18011a866  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011a86a  jmp     short loc_18011A871
0x18011a86c  mov     esi, 1
0x18011a871  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011a878  jz      short loc_18011A893
0x18011a87a  mov     edx, 13h
0x18011a87f  lea     r8, WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids
0x18011a886  mov     ecx, 40Ch
0x18011a88b  mov     r9d, esi
0x18011a88e  call    WPP_SF_d
0x18011a893  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18011a897  jz      short loc_18011A8A2
0x18011a899  mov     rcx, rbx; hObject
0x18011a89c  call    cs:__imp_CloseHandle
0x18011a8a2  test    rdi, rdi
0x18011a8a5  jz      short loc_18011A8B0
0x18011a8a7  lea     rcx, [rbp+37h+var_70]
0x18011a8ab  call    WxFreeHeapEx
0x18011a8b0  lea     rcx, [rbp+37h+lpFileName]; this
0x18011a8b4  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18011a8b9  mov     eax, esi
0x18011a8bb  mov     rcx, [rbp+37h+var_40]
0x18011a8bf  xor     rcx, rsp; StackCookie
0x18011a8c2  call    __security_check_cookie
0x18011a8c7  mov     rbx, [rsp+0D0h+arg_8]
0x18011a8cf  add     rsp, 0A0h
0x18011a8d6  pop     r15
0x18011a8d8  pop     r14
0x18011a8da  pop     r13
0x18011a8dc  pop     r12
0x18011a8de  pop     rdi
0x18011a8df  pop     rsi
0x18011a8e0  pop     rbp
0x18011a8e1  retn
```
