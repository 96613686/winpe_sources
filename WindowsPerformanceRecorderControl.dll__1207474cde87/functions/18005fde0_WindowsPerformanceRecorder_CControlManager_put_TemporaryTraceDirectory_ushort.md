# WindowsPerformanceRecorder::CControlManager::put_TemporaryTraceDirectory(ushort *)

- ea: `0x18005fde0`
- end: `0x18005ff55`
- name: `?put_TemporaryTraceDirectory@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAG@Z`
- size: `373`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180008330`
- `0x1800102a0`
- `0x180016480`
- `0x18001c458`
- `0x18001c820`
- `0x1800234f0`
- `0x18002a6b4`
- `0x18005fde0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005fe36`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005fe36`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fe4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fef9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ff1d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fe4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005fef9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ff1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005fe86`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005fe86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18005fed4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18005fed4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18005fead`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18005fead`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::put_TemporaryTraceDirectory(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 *a2)
{
  __int64 result; // rax
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  LPCWSTR v6; // rdi
  DWORD FileAttributesW; // eax
  int v8; // edx
  WCHAR *v9; // rax
  WCHAR *v10; // rax
  ATL::CAtlException *v11; // [rsp+30h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp+18h] BYREF
  wchar_t *Path; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &Path,
      a2);
    if ( *((_DWORD *)Path - 4) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
      v4 = _wfullpath(0, Path, 0);
      v5 = v4;
      if ( v4 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, v4);
        v6 = lpFileName;
        FileAttributesW = GetFileAttributesW(lpFileName);
        v8 = FileAttributesW & 0x10;
        if ( FileAttributesW == -1 )
          v8 = 0;
        if ( v8 )
        {
          v9 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&lpFileName, *((unsigned int *)v6 - 4));
          PathRemoveBackslashW(v9);
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&lpFileName);
          v10 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(
                           &lpFileName,
                           (unsigned int)(*((_DWORD *)lpFileName - 4) + 1));
          PathAddBackslashW(v10);
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&lpFileName);
          ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 344, &lpFileName);
          free(v5);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
          result = 0;
        }
        else
        {
          free(v5);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
          result = 3310903300LL;
        }
      }
      else
      {
        free(0);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
        result = 2147500037LL;
      }
    }
    else
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
      result = 0;
    }
  }
  catch ( ATL::CAtlException *v11 )
  {
    return *(unsigned int *)v11;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Path,
    a2);
}

```

## disassembly

```asm
0x18005fde0  mov     rax, rsp
0x18005fde3  push    rdi
0x18005fde4  sub     rsp, 40h
0x18005fde8  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18005fdf0  mov     [rax+8], rbx
0x18005fdf4  mov     [rax+10h], rsi
0x18005fdf8  mov     rsi, rcx
0x18005fdfb  lea     rcx, [rax+20h]
0x18005fdff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005fe04  nop
0x18005fe05  mov     rax, [rsp+48h+Path]
0x18005fe0a  cmp     dword ptr [rax-10h], 0
0x18005fe0e  jnz     short loc_18005FE21
0x18005fe10  lea     rcx, [rsp+48h+Path]; this
0x18005fe15  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005fe1a  xor     eax, eax
0x18005fe1c  jmp     loc_18005FF44
0x18005fe21  lea     rcx, [rsp+48h+lpFileName]; void *
0x18005fe26  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005fe2b  nop
0x18005fe2c  xor     r8d, r8d; BufferCount
0x18005fe2f  mov     rdx, [rsp+48h+Path]; Path
0x18005fe34  xor     ecx, ecx; Buffer
0x18005fe36  call    cs:__imp__wfullpath
0x18005fe3c  mov     rbx, rax
0x18005fe3f  mov     [rsp+48h+var_20], rax
0x18005fe44  test    rax, rax
0x18005fe47  jnz     short loc_18005FE71
0x18005fe49  xor     ecx, ecx; Block
0x18005fe4b  call    cs:__imp_free
0x18005fe51  nop
0x18005fe52  lea     rcx, [rsp+48h+lpFileName]; this
0x18005fe57  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005fe5c  nop
0x18005fe5d  lea     rcx, [rsp+48h+Path]; this
0x18005fe62  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005fe67  mov     eax, 80004005h
0x18005fe6c  jmp     loc_18005FF44
0x18005fe71  mov     rdx, rbx
0x18005fe74  lea     rcx, [rsp+48h+lpFileName]
0x18005fe79  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18005fe7e  mov     rdi, [rsp+48h+lpFileName]
0x18005fe83  mov     rcx, rdi; lpFileName
0x18005fe86  call    cs:__imp_GetFileAttributesW
0x18005fe8c  mov     edx, eax
0x18005fe8e  and     edx, 10h
0x18005fe91  xor     ecx, ecx
0x18005fe93  cmp     eax, 0FFFFFFFFh
0x18005fe96  cmovz   edx, ecx
0x18005fe99  test    edx, edx
0x18005fe9b  jz      short loc_18005FF1A
0x18005fe9d  mov     edx, [rdi-10h]
0x18005fea0  lea     rcx, [rsp+48h+lpFileName]
0x18005fea5  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18005feaa  mov     rcx, rax; pszPath
0x18005fead  call    cs:__imp_PathRemoveBackslashW
0x18005feb3  lea     rcx, [rsp+48h+lpFileName]
0x18005feb8  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18005febd  mov     rax, [rsp+48h+lpFileName]
0x18005fec2  mov     edx, [rax-10h]
0x18005fec5  inc     edx
0x18005fec7  lea     rcx, [rsp+48h+lpFileName]
0x18005fecc  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18005fed1  mov     rcx, rax; pszPath
0x18005fed4  call    cs:__imp_PathAddBackslashW
0x18005feda  lea     rcx, [rsp+48h+lpFileName]
0x18005fedf  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18005fee4  lea     rcx, [rsi+158h]
0x18005feeb  lea     rdx, [rsp+48h+lpFileName]
0x18005fef0  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18005fef5  nop
0x18005fef6  mov     rcx, rbx; Block
0x18005fef9  call    cs:__imp_free
0x18005feff  nop
0x18005ff00  lea     rcx, [rsp+48h+lpFileName]; this
0x18005ff05  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005ff0a  nop
0x18005ff0b  lea     rcx, [rsp+48h+Path]; this
0x18005ff10  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005ff15  nop
0x18005ff16  xor     eax, eax
0x18005ff18  jmp     short loc_18005FF44
0x18005ff1a  mov     rcx, rbx; Block
0x18005ff1d  call    cs:__imp_free
0x18005ff23  nop
0x18005ff24  lea     rcx, [rsp+48h+lpFileName]; this
0x18005ff29  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005ff2e  nop
0x18005ff2f  lea     rcx, [rsp+48h+Path]; this
0x18005ff34  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005ff39  mov     eax, 0C5586004h
0x18005ff3e  jmp     short loc_18005FF44
0x18005ff40  mov     eax, dword ptr [rsp+48h+lpFileName]
0x18005ff44  mov     rbx, [rsp+48h+arg_0]
0x18005ff49  mov     rsi, [rsp+48h+arg_8]
0x18005ff4e  add     rsp, 40h
0x18005ff52  pop     rdi
0x18005ff53  retn
```
