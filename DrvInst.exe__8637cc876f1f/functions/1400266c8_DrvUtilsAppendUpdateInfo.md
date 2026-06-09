# DrvUtilsAppendUpdateInfo

- ea: `0x1400266c8`
- end: `0x14002683d`
- name: `DrvUtilsAppendUpdateInfo`
- size: `373`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x14001ae4c`
- `0x140026844`

## callees

- `0x140001b64`
- `0x140024e0c`
- `0x140025130`
- `0x1400266c8`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14002675f`
- `msvcrt!wcsrchr` at `0x14002675f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026825`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140026748`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140026748`
- `DEVRTL!DevRtlWriteTextLog` at `0x140026803`
- `DEVRTL!DevRtlWriteTextLog` at `0x140026803`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400266dc`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400266dc`
- `drvstore!DriverStoreOpenW` at `0x140026714`
- `drvstore!DriverStoreOpenW` at `0x140026714`
- `drvstore!DriverStoreClose` at `0x140026816`
- `drvstore!DriverStoreClose` at `0x140026816`

## string_xrefs

- `0x1400267d6`: `Driver package '%ws' does not install on this processor architecture. Error = 0x%08x`

## pseudocode

```c
_BOOL8 __fastcall DrvUtilsAppendUpdateInfo(__int64 a1, _DWORD *a2, WCHAR *a3)
{
  __int64 ThreadLogToken; // r14
  __int64 v7; // rdi
  DWORD LastError; // ebx
  DWORD FileAttributesW; // eax
  __int64 v10; // rdx
  wchar_t *v11; // rax
  __int64 v13[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h]

  ThreadLogToken = DevRtlGetThreadLogToken();
  *(_OWORD *)v13 = 0;
  v14 = 0;
  if ( !*a2 || !a2[17] )
  {
    LastError = 13;
    goto LABEL_24;
  }
  if ( a1 )
  {
    v7 = a1;
  }
  else
  {
    v7 = DriverStoreOpenW(0, 0, 0, 0);
    if ( !v7 )
    {
      LastError = GetLastError();
      goto LABEL_24;
    }
  }
  v13[0] = v7;
  v13[1] = (__int64)a2;
  v14 = 0;
  FileAttributesW = GetFileAttributesW(a3);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0
    || (v11 = wcsrchr(a3, 0x2Eu)) == 0
    || wcsicmp_0(v11, L".inf") )
  {
    LastError = DrvUtilsEnumDirectoryDriverPackages(a3, v10, v13);
    if ( LastError == 995 )
      LastError = HIDWORD(v14);
    goto LABEL_15;
  }
  LastError = 0;
  if ( !DrvUtilsAppendUpdateInfoCallback(a3, v13) )
  {
    LastError = HIDWORD(v14);
LABEL_15:
    if ( LastError )
    {
      if ( LastError == 1168 )
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          512,
          1,
          "Failed to locate '%ws' in driver store. Error = 0x%08x",
          a3,
          1168,
          v13[0],
          v13[1],
          v14);
      }
      else if ( LastError == 15632 )
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          512,
          2,
          "Driver package '%ws' does not install on this processor architecture. Error = 0x%08x",
          a3,
          15632,
          v13[0],
          v13[1],
          v14);
      }
      else
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          512,
          1,
          "Failed to get driver package info from '%ws'. Error = 0x%08x",
          a3,
          LastError,
          v13[0],
          v13[1],
          v14);
      }
    }
  }
  if ( !a1 )
    DriverStoreClose(v7);
LABEL_24:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1400266c8  push    rbx
0x1400266ca  push    rbp
0x1400266cb  push    rsi
0x1400266cc  push    rdi
0x1400266cd  push    r14
0x1400266cf  sub     rsp, 50h
0x1400266d3  mov     rsi, r8
0x1400266d6  mov     rbx, rdx
0x1400266d9  mov     rbp, rcx
0x1400266dc  call    cs:__imp_DevRtlGetThreadLogToken
0x1400266e2  mov     r14, rax
0x1400266e5  xorps   xmm0, xmm0
0x1400266e8  xor     eax, eax
0x1400266ea  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x1400266ef  mov     [rsp+78h+var_38], rax
0x1400266f4  cmp     [rbx], eax
0x1400266f6  jz      loc_14002681E
0x1400266fc  cmp     [rbx+44h], eax
0x1400266ff  jz      loc_14002681E
0x140026705  test    rbp, rbp
0x140026708  jnz     short loc_14002672F
0x14002670a  xor     r9d, r9d
0x14002670d  xor     r8d, r8d
0x140026710  xor     edx, edx
0x140026712  xor     ecx, ecx
0x140026714  call    cs:__imp_DriverStoreOpenW
0x14002671a  mov     rdi, rax
0x14002671d  test    rax, rax
0x140026720  jnz     short loc_140026732
0x140026722  call    cs:__imp_GetLastError
0x140026728  mov     ebx, eax
0x14002672a  jmp     loc_140026823
0x14002672f  mov     rdi, rbp
0x140026732  mov     rcx, rsi; lpFileName
0x140026735  mov     [rsp+78h+var_48], rdi
0x14002673a  mov     [rsp+78h+var_48+8], rbx
0x14002673f  mov     [rsp+78h+var_38], 0
0x140026748  call    cs:__imp_GetFileAttributesW
0x14002674e  cmp     eax, 0FFFFFFFFh
0x140026751  jz      short loc_140026757
0x140026753  test    al, 10h
0x140026755  jnz     short loc_140026796
0x140026757  mov     edx, 2Eh ; '.'; Ch
0x14002675c  mov     rcx, rsi; Str
0x14002675f  call    cs:__imp_wcsrchr
0x140026765  test    rax, rax
0x140026768  jz      short loc_140026796
0x14002676a  lea     rdx, aInf_1; ".inf"
0x140026771  mov     rcx, rax; String1
0x140026774  call    _wcsicmp_0
0x140026779  test    eax, eax
0x14002677b  jnz     short loc_140026796
0x14002677d  lea     rdx, [rsp+78h+var_48]; __int64
0x140026782  mov     rcx, rsi; unsigned __int16 *
0x140026785  xor     ebx, ebx
0x140026787  call    ?DrvUtilsAppendUpdateInfoCallback@@YAHPEBG_J@Z; DrvUtilsAppendUpdateInfoCallback(ushort const *,__int64)
0x14002678c  test    eax, eax
0x14002678e  jnz     short loc_140026809
0x140026790  mov     ebx, dword ptr [rsp+78h+var_38+4]
0x140026794  jmp     short loc_1400267AF
0x140026796  lea     r8, [rsp+78h+var_48]
0x14002679b  mov     rcx, rsi
0x14002679e  call    DrvUtilsEnumDirectoryDriverPackages
0x1400267a3  cmp     eax, 3E3h
0x1400267a8  mov     ebx, eax
0x1400267aa  cmovz   ebx, dword ptr [rsp+78h+var_38+4]
0x1400267af  test    ebx, ebx
0x1400267b1  jz      short loc_140026809
0x1400267b3  mov     eax, 490h
0x1400267b8  cmp     ebx, eax
0x1400267ba  jnz     short loc_1400267C9
0x1400267bc  mov     [rsp+78h+var_50], eax
0x1400267c0  lea     r9, aFailedToLocate; "Failed to locate '%ws' in driver store."...
0x1400267c7  jmp     short loc_1400267F0
0x1400267c9  mov     eax, 3D10h
0x1400267ce  cmp     ebx, eax
0x1400267d0  jnz     short loc_1400267E5
0x1400267d2  mov     [rsp+78h+var_50], eax
0x1400267d6  lea     r9, aDriverPackageW; "Driver package '%ws' does not install o"...
0x1400267dd  mov     r8d, 2
0x1400267e3  jmp     short loc_1400267F6
0x1400267e5  mov     [rsp+78h+var_50], ebx
0x1400267e9  lea     r9, aFailedToGetDri; "Failed to get driver package info from "...
0x1400267f0  mov     r8d, 1
0x1400267f6  mov     edx, 200h
0x1400267fb  mov     [rsp+78h+var_58], rsi
0x140026800  mov     rcx, r14
0x140026803  call    cs:__imp_DevRtlWriteTextLog
0x140026809  test    rdi, rdi
0x14002680c  jz      short loc_140026823
0x14002680e  test    rbp, rbp
0x140026811  jnz     short loc_140026823
0x140026813  mov     rcx, rdi
0x140026816  call    cs:__imp_DriverStoreClose
0x14002681c  jmp     short loc_140026823
0x14002681e  mov     ebx, 0Dh
0x140026823  mov     ecx, ebx; dwErrCode
0x140026825  call    cs:__imp_SetLastError
0x14002682b  xor     eax, eax
0x14002682d  test    ebx, ebx
0x14002682f  setz    al
0x140026832  add     rsp, 50h
0x140026836  pop     r14
0x140026838  pop     rdi
0x140026839  pop     rsi
0x14002683a  pop     rbp
0x14002683b  pop     rbx
0x14002683c  retn
```
