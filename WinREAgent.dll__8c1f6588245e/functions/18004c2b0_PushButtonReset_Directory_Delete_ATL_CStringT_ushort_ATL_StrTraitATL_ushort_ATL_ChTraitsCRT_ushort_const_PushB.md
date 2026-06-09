# PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)

- ea: `0x18004c2b0`
- end: `0x18004c410`
- name: `?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64 *, const WCHAR *)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180006de8`
- `0x180009c7c`
- `0x180018820`
- `0x18001ed24`
- `0x180021590`
- `0x18002a880`
- `0x1800308cc`
- `0x18004c034`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180037344`
- `0x18004c2b0`
- `0x18004d404`
- `0x180065870`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004c341`
- `KERNEL32!GetLastError` at `0x18004c341`

## string_xrefs

- `0x18004c35b`: `Failed to delete directory [%s]`
- `0x18004c376`: `PbrDeleteDirectory`
- `0x18004c3be`: `PushButtonReset::Directory::Delete`
- `0x18004c399`: `Not all files could be deleted from [%s]`
- `0x18004c3d8`: `Failed to recursively delete [%s]`

## pseudocode

```c
__int64 __fastcall PushButtonReset::Directory::Delete(__int64 *a1, const WCHAR *a2)
{
  __int64 v3; // rdx
  signed int Canonical; // edi
  __int64 v5; // r8
  LPCWSTR v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  signed int LastError; // eax
  int v11; // [rsp+20h] [rbp-48h]
  const wchar_t *v12; // [rsp+28h] [rbp-40h]
  __int64 v13; // [rsp+30h] [rbp-38h]
  _QWORD v14[4]; // [rsp+40h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp+10h] BYREF

  lpFileName = a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
  v6 = lpFileName;
  if ( Canonical >= 0 )
  {
    memset(v14, 0, 24);
    if ( (unsigned int)DeletePathEx(lpFileName, v3, v5, (__int64)v14) )
    {
      Canonical = 0;
      goto LABEL_13;
    }
    LastError = GetLastError();
    Canonical = LastError;
    if ( LastError > 0 )
      Canonical = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Canonical,
      "PbrDeleteDirectory",
      "base\\reset\\util\\src\\filesystem.cpp",
      3061,
      L"Failed to delete directory [%s]",
      v6);
    if ( Canonical == -2147024751 )
    {
      v13 = *a1;
      v12 = L"Not all files could be deleted from [%s]";
      v11 = 3089;
      v7 = 2147942545LL;
      v8 = 1;
      goto LABEL_9;
    }
    if ( Canonical >= 0 )
      goto LABEL_13;
    v13 = *a1;
    v12 = L"Failed to recursively delete [%s]";
    v11 = 3094;
  }
  else
  {
    v13 = *a1;
    v12 = L"Failed to get canonical form for [%s]";
    v11 = 3082;
  }
  v7 = (unsigned int)Canonical;
  v8 = 2;
LABEL_9:
  PushButtonReset::Logging::TraceErr(
    v8,
    v7,
    "PushButtonReset::Directory::Delete",
    "base\\reset\\util\\src\\filesystem.cpp",
    v11,
    v12,
    v13);
LABEL_13:
  ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
  return (unsigned int)Canonical;
}

```

## disassembly

```asm
0x18004c2b0  mov     rax, rsp
0x18004c2b3  mov     [rax+8], rbx
0x18004c2b7  mov     [rax+18h], rsi
0x18004c2bb  mov     [rax+10h], rdx
0x18004c2bf  push    rdi
0x18004c2c0  sub     rsp, 60h
0x18004c2c4  mov     rsi, rcx
0x18004c2c7  lea     rcx, [rax+10h]
0x18004c2cb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004c2d0  nop
0x18004c2d1  lea     rdx, [rsp+68h+lpFileName]
0x18004c2d6  mov     rcx, rsi
0x18004c2d9  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004c2de  mov     edi, eax
0x18004c2e0  mov     rbx, [rsp+68h+lpFileName]
0x18004c2e5  test    eax, eax
0x18004c2e7  jns     short loc_18004C311
0x18004c2e9  mov     rcx, [rsi]
0x18004c2ec  mov     [rsp+68h+var_38], rcx
0x18004c2f1  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004c2f8  mov     [rsp+68h+var_40], rax
0x18004c2fd  mov     [rsp+68h+var_48], 0C0Ah
0x18004c305  mov     edx, edi
0x18004c307  mov     ecx, 2
0x18004c30c  jmp     loc_18004C3B7
0x18004c311  mov     [rsp+68h+var_28], 0
0x18004c31a  mov     [rsp+68h+var_20], 0
0x18004c323  mov     [rsp+68h+var_18], 0
0x18004c32c  lea     r9, [rsp+68h+var_28]
0x18004c331  mov     rcx, rbx; lpFileName
0x18004c334  call    DeletePathEx
0x18004c339  test    eax, eax
0x18004c33b  jnz     loc_18004C3F1
0x18004c341  call    cs:__imp_GetLastError
0x18004c347  mov     edi, eax
0x18004c349  test    eax, eax
0x18004c34b  jle     short loc_18004C356
0x18004c34d  movzx   edi, ax
0x18004c350  or      edi, 80070000h
0x18004c356  mov     [rsp+68h+var_38], rbx
0x18004c35b  lea     rax, aFailedToDelete_4; "Failed to delete directory [%s]"
0x18004c362  mov     [rsp+68h+var_40], rax
0x18004c367  mov     [rsp+68h+var_48], 0BF5h
0x18004c36f  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c376  lea     r8, aPbrdeletedirec; "PbrDeleteDirectory"
0x18004c37d  mov     edx, edi
0x18004c37f  mov     ecx, 2
0x18004c384  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c389  cmp     edi, 80070091h
0x18004c38f  jnz     short loc_18004C3CC
0x18004c391  mov     rax, [rsi]
0x18004c394  mov     [rsp+68h+var_38], rax
0x18004c399  lea     rax, aNotAllFilesCou; "Not all files could be deleted from [%s"...
0x18004c3a0  mov     [rsp+68h+var_40], rax
0x18004c3a5  mov     [rsp+68h+var_48], 0C11h
0x18004c3ad  mov     edx, 80070091h
0x18004c3b2  mov     ecx, 1
0x18004c3b7  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c3be  lea     r8, aPushbuttonrese_101; "PushButtonReset::Directory::Delete"
0x18004c3c5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c3ca  jmp     short loc_18004C3F3
0x18004c3cc  test    edi, edi
0x18004c3ce  jns     short loc_18004C3F3
0x18004c3d0  mov     rax, [rsi]
0x18004c3d3  mov     [rsp+68h+var_38], rax
0x18004c3d8  lea     rax, aFailedToRecurs; "Failed to recursively delete [%s]"
0x18004c3df  mov     [rsp+68h+var_40], rax
0x18004c3e4  mov     [rsp+68h+var_48], 0C16h
0x18004c3ec  jmp     loc_18004C305
0x18004c3f1  xor     edi, edi
0x18004c3f3  lea     rcx, [rbx-18h]; this
0x18004c3f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004c3fc  mov     eax, edi
0x18004c3fe  lea     r11, [rsp+68h+var_8]
0x18004c403  mov     rbx, [r11+10h]
0x18004c407  mov     rsi, [r11+20h]
0x18004c40b  mov     rsp, r11
0x18004c40e  pop     rdi
0x18004c40f  retn
```
