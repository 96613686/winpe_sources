# AhgGenomeGetPE

- ea: `0x18001123c`
- end: `0x180011638`
- name: `AhgGenomeGetPE`
- size: `1020`
- prototype: `__int64 __fastcall(const WCHAR *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010d10`

## callees

- `0x18001123c`
- `0x180011924`
- `0x1800119a0`
- `0x180015220`
- `0x180016280`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x18001143e`
- `KERNEL32!GetLocalTime` at `0x18001143e`
- `KERNEL32!GetLastError` at `0x180011309`
- `KERNEL32!GetLastError` at `0x180011366`
- `KERNEL32!GetLastError` at `0x1800113a7`
- `KERNEL32!GetLastError` at `0x180011309`
- `KERNEL32!GetLastError` at `0x180011366`
- `KERNEL32!GetLastError` at `0x1800113a7`
- `KERNEL32!CloseHandle` at `0x1800115f8`
- `KERNEL32!CloseHandle` at `0x180011607`
- `KERNEL32!CloseHandle` at `0x1800115f8`
- `KERNEL32!CloseHandle` at `0x180011607`
- `KERNEL32!CreateFileW` at `0x1800112f5`
- `KERNEL32!CreateFileW` at `0x1800112f5`
- `KERNEL32!UnmapViewOfFile` at `0x1800115ea`
- `KERNEL32!UnmapViewOfFile` at `0x1800115ea`
- `KERNEL32!CreateFileMappingW` at `0x180011350`
- `KERNEL32!CreateFileMappingW` at `0x180011350`
- `KERNEL32!MapViewOfFile` at `0x180011391`
- `KERNEL32!MapViewOfFile` at `0x180011391`

## string_xrefs

- `0x18001130f`: `Failed to open file [%d]`
- `0x1800115a4`: `Exception while reading PE [%d]`
- `0x18001140e`: `Failed to read PE [%d]`
- `0x18001157e`: `Failed to set data for attribute AHG_TAG_PE_NXCOMPAT`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetPE(const WCHAR *a1, void *a2)
{
  __int64 v3; // r14
  void *v4; // r12
  void *v5; // r15
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v8; // r9
  __int64 v9; // r8
  DWORD PeHeaderInfo; // edi
  void *v11; // rax
  HANDLE FileMappingW; // rax
  const char *v13; // r9
  __int64 v14; // r8
  unsigned int v16; // [rsp+40h] [rbp-98h] BYREF
  void *v17; // [rsp+48h] [rbp-90h]
  int v18; // [rsp+50h] [rbp-88h] BYREF
  int v19; // [rsp+54h] [rbp-84h] BYREF
  int v20; // [rsp+58h] [rbp-80h] BYREF
  int v21; // [rsp+5Ch] [rbp-7Ch] BYREF
  __int64 v22; // [rsp+60h] [rbp-78h] BYREF
  DWORD v23; // [rsp+68h] [rbp-70h]
  __int64 v24; // [rsp+78h] [rbp-60h]
  HANDLE v25; // [rsp+80h] [rbp-58h]
  void *v26; // [rsp+88h] [rbp-50h]
  void *v27; // [rsp+90h] [rbp-48h]
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-40h] BYREF

  v17 = a2;
  v27 = a2;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v16 = 0;
  SystemTime = 0;
  v3 = -1;
  v24 = -1;
  v4 = a2;
  v26 = a2;
  v5 = 0;
  v25 = 0;
  LODWORD(v22) = 0;
  if ( a2 )
    goto LABEL_10;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = (__int64)FileW;
  v24 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
    v5 = FileMappingW;
    v25 = FileMappingW;
    if ( !FileMappingW )
    {
      LastError = GetLastError();
      v8 = "Failed to map file [%d]";
      v9 = 425;
      goto LABEL_4;
    }
    v4 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v26 = v4;
    if ( !v4 )
    {
      PeHeaderInfo = GetLastError();
      AslLogCallPrintf(1, "AhgGenomeGetPE", 437, "Failed to map a view of file mapping [%d]");
      goto LABEL_9;
    }
LABEL_10:
    PeHeaderInfo = AhgGetPeHeaderInfo((int)&v18, (int)&v19, (int)&v20, (int)&v21, (__int64)&v22, v4);
    v23 = PeHeaderInfo;
    if ( PeHeaderInfo )
    {
      AslLogCallPrintf(2, "AhgGenomeGetPE", 451, "Failed to read PE [%d]");
      v11 = v17;
      goto LABEL_29;
    }
    GetLocalTime(&SystemTime);
    if ( (unsigned int)v18 < 0x7C8
      || v18 > (unsigned int)SystemTime.wYear
      || (unsigned int)AhgpSetAttribute(a1 + 340, 10, &v18) )
    {
      v16 = HIWORD(v19) + ((unsigned __int16)v19 << 16);
      if ( v16 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 348, 11, &v16) )
      {
        v16 = HIWORD(v20) + ((unsigned __int16)v20 << 16);
        if ( v16 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 356, 12, &v16) )
        {
          v16 = HIWORD(v21) + ((unsigned __int16)v21 << 16);
          if ( !v16 || (unsigned int)AhgpSetAttribute(a1 + 364, 13, &v16) )
          {
            if ( (unsigned int)AhgpSetAttribute(a1 + 372, 14, &v22) )
            {
              PeHeaderInfo = 0;
              goto LABEL_9;
            }
            v13 = "Failed to set data for attribute AHG_TAG_PE_NXCOMPAT";
            v14 = 521;
          }
          else
          {
            v13 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
            v14 = 511;
          }
        }
        else
        {
          v13 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
          v14 = 499;
        }
      }
      else
      {
        v13 = "Failed to set data for attribute AHG_TAG_PE_OS_VERSION";
        v14 = 487;
      }
    }
    else
    {
      v13 = "Failed to set data for attribute AHG_TAG_PE_TIME_DATE_STAMP_YEAR";
      v14 = 475;
    }
    PeHeaderInfo = 87;
    AslLogCallPrintf(1, "AhgGenomeGetPE", v14, v13);
LABEL_9:
    v11 = v17;
    goto LABEL_29;
  }
  LastError = GetLastError();
  v8 = "Failed to open file [%d]";
  v9 = 412;
LABEL_4:
  PeHeaderInfo = LastError;
  AslLogCallPrintf(1, "AhgGenomeGetPE", v9, v8);
  v11 = 0;
LABEL_29:
  if ( v4 && !v11 )
    UnmapViewOfFile(v4);
  if ( v5 )
    CloseHandle(v5);
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  return PeHeaderInfo;
}

```

## disassembly

```asm
0x18001123c  mov     r11, rsp
0x18001123f  mov     [r11+18h], rsi
0x180011243  push    rdi
0x180011244  push    r12
0x180011246  push    r13
0x180011248  push    r14
0x18001124a  push    r15
0x18001124c  sub     rsp, 0B0h
0x180011253  mov     rax, cs:__security_cookie
0x18001125a  xor     rax, rsp
0x18001125d  mov     [rsp+0D8h+var_30], rax
0x180011265  mov     [rsp+0D8h+var_90], rdx
0x18001126a  mov     r13, rcx
0x18001126d  mov     [rsp+0D8h+var_48], rdx
0x180011275  mov     [rsp+0D8h+var_88], 0
0x18001127d  mov     [rsp+0D8h+var_84], 0
0x180011285  mov     [rsp+0D8h+var_80], 0
0x18001128d  mov     [rsp+0D8h+var_7C], 0
0x180011295  mov     [rsp+0D8h+var_98], 0
0x18001129d  xorps   xmm0, xmm0
0x1800112a0  movups  xmmword ptr [r11-40h], xmm0
0x1800112a5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800112a9  mov     [rsp+0D8h+var_60], r14
0x1800112ae  mov     r12, rdx
0x1800112b1  mov     [rsp+0D8h+var_50], rdx
0x1800112b9  xor     r15d, r15d
0x1800112bc  mov     [rsp+0D8h+var_58], r15
0x1800112c4  mov     [r11-78h], r15d
0x1800112c8  lea     esi, [r14+2]
0x1800112cc  test    rdx, rdx
0x1800112cf  jnz     loc_1800113D8
0x1800112d5  mov     [rsp+0D8h+hTemplateFile], r15; hTemplateFile
0x1800112da  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800112e2  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800112ea  xor     r9d, r9d; lpSecurityAttributes
0x1800112ed  mov     r8d, esi; dwShareMode
0x1800112f0  mov     edx, 80000000h; dwDesiredAccess
0x1800112f5  call    cs:__imp_CreateFileW
0x1800112fb  mov     r14, rax
0x1800112fe  mov     [rsp+0D8h+var_60], rax
0x180011303  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011307  jnz     short loc_180011338
0x180011309  call    cs:__imp_GetLastError
0x18001130f  lea     r9, aFailedToOpenFi; "Failed to open file [%d]"
0x180011316  mov     r8d, 19Ch
0x18001131c  mov     [rsp+0D8h+dwCreationDisposition], eax
0x180011320  mov     edi, eax
0x180011322  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x180011329  mov     ecx, esi
0x18001132b  call    AslLogCallPrintf
0x180011330  mov     rax, r12
0x180011333  jmp     loc_1800115DD
0x180011338  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], r15; lpName
0x18001133d  mov     [rsp+0D8h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x180011342  xor     r9d, r9d; dwMaximumSizeHigh
0x180011345  xor     edx, edx; lpFileMappingAttributes
0x180011347  mov     r8d, 11000002h; flProtect
0x18001134d  mov     rcx, rax; hFile
0x180011350  call    cs:__imp_CreateFileMappingW
0x180011356  mov     r15, rax
0x180011359  mov     [rsp+0D8h+var_58], rax
0x180011361  test    rax, rax
0x180011364  jnz     short loc_18001137B
0x180011366  call    cs:__imp_GetLastError
0x18001136c  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x180011373  mov     r8d, 1A9h
0x180011379  jmp     short loc_18001131C
0x18001137b  mov     qword ptr [rsp+0D8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180011384  xor     r9d, r9d; dwFileOffsetLow
0x180011387  xor     r8d, r8d; dwFileOffsetHigh
0x18001138a  lea     edx, [r9+4]; dwDesiredAccess
0x18001138e  mov     rcx, rax; hFileMappingObject
0x180011391  call    cs:__imp_MapViewOfFile
0x180011397  mov     r12, rax
0x18001139a  mov     [rsp+0D8h+var_50], rax
0x1800113a2  test    rax, rax
0x1800113a5  jnz     short loc_1800113D8
0x1800113a7  call    cs:__imp_GetLastError
0x1800113ad  mov     edi, eax
0x1800113af  mov     [rsp+0D8h+dwCreationDisposition], eax
0x1800113b3  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x1800113ba  mov     r8d, 1B5h
0x1800113c0  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800113c7  mov     ecx, esi
0x1800113c9  call    AslLogCallPrintf
0x1800113ce  mov     rax, [rsp+0D8h+var_90]
0x1800113d3  jmp     loc_1800115DD
0x1800113d8  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], r12; BaseAddress
0x1800113dd  lea     rax, [rsp+0D8h+var_78]
0x1800113e2  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax; __int64
0x1800113e7  lea     r9, [rsp+0D8h+var_7C]; int
0x1800113ec  lea     r8, [rsp+0D8h+var_80]; int
0x1800113f1  lea     rdx, [rsp+0D8h+var_84]; int
0x1800113f6  lea     rcx, [rsp+0D8h+var_88]; int
0x1800113fb  call    AhgGetPeHeaderInfo
0x180011400  mov     edi, eax
0x180011402  mov     [rsp+0D8h+var_70], eax
0x180011406  test    eax, eax
0x180011408  jz      short loc_180011436
0x18001140a  mov     [rsp+0D8h+dwCreationDisposition], eax
0x18001140e  lea     r9, aFailedToReadPe; "Failed to read PE [%d]"
0x180011415  mov     r8d, 1C3h
0x18001141b  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x180011422  mov     ecx, 2
0x180011427  call    AslLogCallPrintf
0x18001142c  mov     rax, [rsp+0D8h+var_90]
0x180011431  jmp     loc_1800115DD
0x180011436  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18001143e  call    cs:__imp_GetLocalTime
0x180011444  cmp     [rsp+0D8h+var_88], 7C8h
0x18001144c  jb      short loc_18001149B
0x18001144e  movzx   eax, [rsp+0D8h+SystemTime.wYear]
0x180011456  cmp     [rsp+0D8h+var_88], eax
0x18001145a  ja      short loc_18001149B
0x18001145c  mov     edx, 0Ah
0x180011461  lea     rcx, [r13+2A8h]
0x180011468  lea     r8, [rsp+0D8h+var_88]
0x18001146d  call    AhgpSetAttribute
0x180011472  test    eax, eax
0x180011474  jnz     short loc_18001149B
0x180011476  lea     r9, aFailedToSetDat_1; "Failed to set data for attribute AHG_TA"...
0x18001147d  mov     r8d, 1DBh
0x180011483  mov     edi, 57h ; 'W'
0x180011488  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18001148f  mov     ecx, esi
0x180011491  call    AslLogCallPrintf
0x180011496  jmp     loc_1800113CE
0x18001149b  movzx   ecx, word ptr [rsp+0D8h+var_84]
0x1800114a0  shl     ecx, 10h
0x1800114a3  movzx   eax, word ptr [rsp+0D8h+var_84+2]
0x1800114a8  add     ecx, eax
0x1800114aa  mov     [rsp+0D8h+var_98], ecx
0x1800114ae  mov     edi, 10000h
0x1800114b3  cmp     ecx, edi
0x1800114b5  jbe     short loc_1800114E0
0x1800114b7  mov     edx, 0Bh
0x1800114bc  lea     rcx, [r13+2B8h]
0x1800114c3  lea     r8, [rsp+0D8h+var_98]
0x1800114c8  call    AhgpSetAttribute
0x1800114cd  test    eax, eax
0x1800114cf  jnz     short loc_1800114E0
0x1800114d1  lea     r9, aFailedToSetDat_3; "Failed to set data for attribute AHG_TA"...
0x1800114d8  mov     r8d, 1E7h
0x1800114de  jmp     short loc_180011483
0x1800114e0  movzx   ecx, word ptr [rsp+0D8h+var_80]
0x1800114e5  shl     ecx, 10h
0x1800114e8  movzx   eax, word ptr [rsp+0D8h+var_80+2]
0x1800114ed  add     ecx, eax
0x1800114ef  mov     [rsp+0D8h+var_98], ecx
0x1800114f3  cmp     ecx, edi
0x1800114f5  jbe     short loc_180011523
0x1800114f7  mov     edx, 0Ch
0x1800114fc  lea     rcx, [r13+2C8h]
0x180011503  lea     r8, [rsp+0D8h+var_98]
0x180011508  call    AhgpSetAttribute
0x18001150d  test    eax, eax
0x18001150f  jnz     short loc_180011523
0x180011511  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x180011518  mov     r8d, 1F3h
0x18001151e  jmp     loc_180011483
0x180011523  movzx   ecx, word ptr [rsp+0D8h+var_7C]
0x180011528  shl     ecx, 10h
0x18001152b  movzx   eax, word ptr [rsp+0D8h+var_7C+2]
0x180011530  add     ecx, eax
0x180011532  mov     [rsp+0D8h+var_98], ecx
0x180011536  jz      short loc_180011564
0x180011538  mov     edx, 0Dh
0x18001153d  lea     rcx, [r13+2D8h]
0x180011544  lea     r8, [rsp+0D8h+var_98]
0x180011549  call    AhgpSetAttribute
0x18001154e  test    eax, eax
0x180011550  jnz     short loc_180011564
0x180011552  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x180011559  mov     r8d, 1FFh
0x18001155f  jmp     loc_180011483
0x180011564  mov     edx, 0Eh
0x180011569  lea     rcx, [r13+2E8h]
0x180011570  lea     r8, [rsp+0D8h+var_78]
0x180011575  call    AhgpSetAttribute
0x18001157a  test    eax, eax
0x18001157c  jnz     short loc_180011590
0x18001157e  lea     r9, aFailedToSetDat_6; "Failed to set data for attribute AHG_TA"...
0x180011585  mov     r8d, 209h
0x18001158b  jmp     loc_180011483
0x180011590  xor     edi, edi
0x180011592  jmp     loc_1800113CE
0x180011597  mov     edi, 1Eh
0x18001159c  mov     [rsp+0D8h+var_70], edi
0x1800115a0  mov     [rsp+0D8h+dwCreationDisposition], edi
0x1800115a4  lea     r9, aExceptionWhile_0; "Exception while reading PE [%d]"
0x1800115ab  mov     r8d, 1C9h
0x1800115b1  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800115b8  lea     ecx, [rdi-1Dh]
0x1800115bb  call    AslLogCallPrintf
0x1800115c0  mov     r14, [rsp+0D8h+var_60]
0x1800115c5  mov     r15, [rsp+0D8h+var_58]
0x1800115cd  mov     r12, [rsp+0D8h+var_50]
0x1800115d5  mov     rax, [rsp+0D8h+var_48]
0x1800115dd  test    r12, r12
0x1800115e0  jz      short loc_1800115F0
0x1800115e2  test    rax, rax
0x1800115e5  jnz     short loc_1800115F0
0x1800115e7  mov     rcx, r12; lpBaseAddress
0x1800115ea  call    cs:__imp_UnmapViewOfFile
0x1800115f0  test    r15, r15
0x1800115f3  jz      short loc_1800115FE
0x1800115f5  mov     rcx, r15; hObject
0x1800115f8  call    cs:__imp_CloseHandle
0x1800115fe  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180011602  jz      short loc_18001160D
0x180011604  mov     rcx, r14; hObject
0x180011607  call    cs:__imp_CloseHandle
0x18001160d  mov     eax, edi
0x18001160f  mov     rcx, [rsp+0D8h+var_30]
0x180011617  xor     rcx, rsp; StackCookie
0x18001161a  call    __security_check_cookie
0x18001161f  mov     rsi, [rsp+0D8h+arg_10]
0x180011627  add     rsp, 0B0h
0x18001162e  pop     r15
0x180011630  pop     r14
0x180011632  pop     r13
0x180011634  pop     r12
0x180011636  pop     rdi
0x180011637  retn
0x1800166dc  push    rbp
0x1800166de  sub     rsp, 40h
0x1800166e2  mov     rbp, rdx
0x1800166e5  mov     [rbp+70h], rcx
0x1800166e9  mov     rax, [rbp+70h]
0x1800166ed  mov     rcx, [rax]
0x1800166f0  cmp     dword ptr [rcx], 0C0000006h
0x1800166f6  jz      short loc_180016710
0x1800166f8  mov     rax, [rbp+70h]
0x1800166fc  mov     rcx, [rax]
0x1800166ff  cmp     dword ptr [rcx], 0C0000005h
0x180016705  jz      short loc_180016710
0x180016707  mov     dword ptr [rbp+64h], 0
0x18001670e  jmp     short loc_180016717
0x180016710  mov     dword ptr [rbp+64h], 1
0x180016717  mov     eax, [rbp+64h]
0x18001671a  add     rsp, 40h
0x18001671e  pop     rbp
0x18001671f  retn
```
