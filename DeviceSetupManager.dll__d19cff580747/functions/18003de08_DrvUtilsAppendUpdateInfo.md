# DrvUtilsAppendUpdateInfo

- ea: `0x18003de08`
- end: `0x18003df7d`
- name: `DrvUtilsAppendUpdateInfo`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18003b1f0`

## callees

- `0x18001b9d0`
- `0x18003cd90`
- `0x18003de08`
- `0x18003e41c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003de9f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003de9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de62`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003de88`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003de88`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x18003de1c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x18003de1c`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003df43`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003df43`
- `drvstore!DriverStoreClose` at `0x18003df56`
- `drvstore!DriverStoreClose` at `0x18003df56`
- `drvstore!DriverStoreOpenW` at `0x18003de54`
- `drvstore!DriverStoreOpenW` at `0x18003de54`

## string_xrefs

- `0x18003df16`: `Driver package '%ws' does not install on this processor architecture. Error = 0x%08x`

## pseudocode

```c
_BOOL8 __fastcall DrvUtilsAppendUpdateInfo(__int64 a1, _DWORD *a2, const WCHAR *a3)
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
    || wcsicmp(v11, L".inf") )
  {
    LastError = DrvUtilsEnumDirectoryDriverPackages(a3, v10, v13);
    if ( LastError == 995 )
      LastError = HIDWORD(v14);
    goto LABEL_15;
  }
  LastError = 0;
  if ( !(unsigned int)DrvUtilsAppendUpdateInfoCallback(a3, (__int64)v13) )
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
0x18003de08  push    rbx
0x18003de0a  push    rbp
0x18003de0b  push    rsi
0x18003de0c  push    rdi
0x18003de0d  push    r14
0x18003de0f  sub     rsp, 50h
0x18003de13  mov     rsi, r8
0x18003de16  mov     rbx, rdx
0x18003de19  mov     rbp, rcx
0x18003de1c  call    cs:__imp_DevRtlGetThreadLogToken
0x18003de22  mov     r14, rax
0x18003de25  xorps   xmm0, xmm0
0x18003de28  xor     eax, eax
0x18003de2a  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x18003de2f  mov     [rsp+78h+var_38], rax
0x18003de34  cmp     [rbx], eax
0x18003de36  jz      loc_18003DF5E
0x18003de3c  cmp     [rbx+44h], eax
0x18003de3f  jz      loc_18003DF5E
0x18003de45  test    rbp, rbp
0x18003de48  jnz     short loc_18003DE6F
0x18003de4a  xor     r9d, r9d
0x18003de4d  xor     r8d, r8d
0x18003de50  xor     edx, edx
0x18003de52  xor     ecx, ecx
0x18003de54  call    cs:__imp_DriverStoreOpenW
0x18003de5a  mov     rdi, rax
0x18003de5d  test    rax, rax
0x18003de60  jnz     short loc_18003DE72
0x18003de62  call    cs:__imp_GetLastError
0x18003de68  mov     ebx, eax
0x18003de6a  jmp     loc_18003DF63
0x18003de6f  mov     rdi, rbp
0x18003de72  mov     rcx, rsi; lpFileName
0x18003de75  mov     [rsp+78h+var_48], rdi
0x18003de7a  mov     [rsp+78h+var_48+8], rbx
0x18003de7f  mov     [rsp+78h+var_38], 0
0x18003de88  call    cs:__imp_GetFileAttributesW
0x18003de8e  cmp     eax, 0FFFFFFFFh
0x18003de91  jz      short loc_18003DE97
0x18003de93  test    al, 10h
0x18003de95  jnz     short loc_18003DED6
0x18003de97  mov     edx, 2Eh ; '.'; Ch
0x18003de9c  mov     rcx, rsi; Str
0x18003de9f  call    cs:__imp_wcsrchr
0x18003dea5  test    rax, rax
0x18003dea8  jz      short loc_18003DED6
0x18003deaa  lea     rdx, aInf_0; ".inf"
0x18003deb1  mov     rcx, rax; String1
0x18003deb4  call    _wcsicmp
0x18003deb9  test    eax, eax
0x18003debb  jnz     short loc_18003DED6
0x18003debd  lea     rdx, [rsp+78h+var_48]; __int64
0x18003dec2  mov     rcx, rsi; unsigned __int16 *
0x18003dec5  xor     ebx, ebx
0x18003dec7  call    ?DrvUtilsAppendUpdateInfoCallback@@YAHPEBG_J@Z; DrvUtilsAppendUpdateInfoCallback(ushort const *,__int64)
0x18003decc  test    eax, eax
0x18003dece  jnz     short loc_18003DF49
0x18003ded0  mov     ebx, dword ptr [rsp+78h+var_38+4]
0x18003ded4  jmp     short loc_18003DEEF
0x18003ded6  lea     r8, [rsp+78h+var_48]
0x18003dedb  mov     rcx, rsi
0x18003dede  call    DrvUtilsEnumDirectoryDriverPackages
0x18003dee3  cmp     eax, 3E3h
0x18003dee8  mov     ebx, eax
0x18003deea  cmovz   ebx, dword ptr [rsp+78h+var_38+4]
0x18003deef  test    ebx, ebx
0x18003def1  jz      short loc_18003DF49
0x18003def3  mov     eax, 490h
0x18003def8  cmp     ebx, eax
0x18003defa  jnz     short loc_18003DF09
0x18003defc  mov     [rsp+78h+var_50], eax
0x18003df00  lea     r9, aFailedToLocate_0; "Failed to locate '%ws' in driver store."...
0x18003df07  jmp     short loc_18003DF30
0x18003df09  mov     eax, 3D10h
0x18003df0e  cmp     ebx, eax
0x18003df10  jnz     short loc_18003DF25
0x18003df12  mov     [rsp+78h+var_50], eax
0x18003df16  lea     r9, aDriverPackageW; "Driver package '%ws' does not install o"...
0x18003df1d  mov     r8d, 2
0x18003df23  jmp     short loc_18003DF36
0x18003df25  mov     [rsp+78h+var_50], ebx
0x18003df29  lea     r9, aFailedToGetDri; "Failed to get driver package info from "...
0x18003df30  mov     r8d, 1
0x18003df36  mov     edx, 200h
0x18003df3b  mov     [rsp+78h+var_58], rsi
0x18003df40  mov     rcx, r14
0x18003df43  call    cs:__imp_DevRtlWriteTextLog
0x18003df49  test    rdi, rdi
0x18003df4c  jz      short loc_18003DF63
0x18003df4e  test    rbp, rbp
0x18003df51  jnz     short loc_18003DF63
0x18003df53  mov     rcx, rdi
0x18003df56  call    cs:__imp_DriverStoreClose
0x18003df5c  jmp     short loc_18003DF63
0x18003df5e  mov     ebx, 0Dh
0x18003df63  mov     ecx, ebx; dwErrCode
0x18003df65  call    cs:__imp_SetLastError
0x18003df6b  xor     eax, eax
0x18003df6d  test    ebx, ebx
0x18003df6f  setz    al
0x18003df72  add     rsp, 50h
0x18003df76  pop     r14
0x18003df78  pop     rdi
0x18003df79  pop     rsi
0x18003df7a  pop     rbp
0x18003df7b  pop     rbx
0x18003df7c  retn
```
