# Csl::ExpandDiskPartition(ulong,unsigned __int64 &)

- ea: `0x180024218`
- end: `0x180024635`
- name: `?ExpandDiskPartition@Csl@@YAJKAEA_K@Z`
- size: `1053`
- prototype: `__int64 __fastcall(Csl *this, _QWORD *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18002463c`

## callees

- `0x180002140`
- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x180007b2c`
- `0x180007b4c`
- `0x1800095f8`
- `0x18000ab38`
- `0x18000af30`
- `0x180024218`
- `0x18003619c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002438b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002438b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024418`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024486`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024530`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024418`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024486`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024530`

## pseudocode

```c
__int64 __fastcall Csl::ExpandDiskPartition(Csl *this, _QWORD *a2, unsigned __int64 *a3)
{
  int v4; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  HANDLE FileW; // rbx
  const char *v9; // r9
  const char *v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rdx
  unsigned int v15; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  void *v19; // [rsp+48h] [rbp-B8h]
  char *v20; // [rsp+50h] [rbp-B0h]
  _WORD v21[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v23[8]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD InBuffer[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h]
  _DWORD OutBuffer[6]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-48h]
  __int64 v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+168h] [rbp+68h]
  __int64 v30; // [rsp+170h] [rbp+70h]
  int v31; // [rsp+178h] [rbp+78h]
  _BYTE Buf1[112]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v19 = v21;
  v20 = (char *)v21;
  v21[0] = 0;
  v4 = Csl::UlongToString((int)this);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
LABEL_3:
    if ( v19 != v21 )
      operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  lpFileName[0] = v23;
  lpFileName[1] = v23;
  v23[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)lpFileName,
          L"\\\\.\\PHYSICALDRIVE",
          0x11u) )
  {
    v7 = 818;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( lpFileName[0] != v23 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v19 != v21 )
      operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          (__int64)lpFileName,
          v19,
          (v20 - (_BYTE *)v19) >> 1) )
  {
    v7 = 819;
    goto LABEL_10;
  }
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x33E,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
                  v9);
    if ( lpFileName[0] != v23 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_3;
  }
  BytesReturned = 0;
  if ( !DeviceIoControl(FileW, 0x70140u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v11 = 843;
LABEL_20:
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
            v10);
LABEL_40:
    v15 = v12;
    if ( FileW )
      CloseHandle(FileW);
    if ( lpFileName[0] != v23 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v19 != v21 )
      operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
    return v15;
  }
  memset_0(OutBuffer, 0, 0x150u);
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, OutBuffer, 0x150u, &BytesReturned, 0) )
  {
    v11 = 863;
    goto LABEL_20;
  }
  if ( OutBuffer[0] != 1 || OutBuffer[1] != 2 )
  {
    v14 = 874;
    goto LABEL_39;
  }
  if ( memcmp_0(Buf1, &PARTITION_BASIC_DATA_GUID, 0x10u) )
  {
    v14 = 880;
LABEL_39:
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
            (const char *)0x57,
            dwCreationDispositiona);
    goto LABEL_40;
  }
  v13 = v30;
  if ( v30 + v29 < v27 + v28 )
  {
    InBuffer[1] = 0;
    InBuffer[0] = v31;
    v25 = v27 + v28 - (v30 + v29);
    if ( !DeviceIoControl(FileW, 0x7C0D0u, InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
    {
      v11 = 911;
      goto LABEL_20;
    }
    v13 += v25;
  }
  *a2 = v13;
  if ( FileW )
    CloseHandle(FileW);
  if ( lpFileName[0] != v23 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v19 != v21 )
    operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180024218  mov     [rsp-8+arg_10], rbx
0x18002421d  push    rbp
0x18002421e  push    rsi
0x18002421f  push    rdi
0x180024220  lea     rbp, [rsp-100h]
0x180024228  sub     rsp, 200h
0x18002422f  mov     rax, cs:__security_cookie
0x180024236  xor     rax, rsp
0x180024239  mov     [rbp+110h+var_20], rax
0x180024240  lea     rax, [rsp+210h+var_1B8]
0x180024245  mov     rsi, rdx
0x180024248  mov     [rsp+210h+var_1C8], rax
0x18002424d  lea     rdx, [rsp+210h+var_1C8]
0x180024252  lea     rax, [rsp+210h+var_1B8]
0x180024257  mov     [rsp+210h+var_1C0], rax
0x18002425c  xor     eax, eax
0x18002425e  mov     [rsp+210h+var_1B8], ax
0x180024263  call    ?UlongToString@Csl@@YAJKAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::UlongToString(ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180024268  mov     ebx, eax
0x18002426a  test    eax, eax
0x18002426c  jns     short loc_1800242AB
0x18002426e  mov     rcx, [rbp+118h]; this
0x180024275  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002427c  mov     r9d, eax; char *
0x18002427f  mov     edx, 32Fh; void *
0x180024284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024289  mov     rcx, [rsp+210h+var_1C8]; void *
0x18002428e  lea     rax, [rsp+210h+var_1B8]
0x180024293  cmp     rcx, rax
0x180024296  jz      short loc_1800242A4
0x180024298  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002429f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800242a4  mov     eax, ebx
0x1800242a6  jmp     loc_180024612
0x1800242ab  lea     rax, [rsp+210h+var_198]
0x1800242b0  mov     [rsp+210h+lpFileName], rax
0x1800242b5  lea     rdx, aPhysicaldrive; "\\\\.\\PHYSICALDRIVE"
0x1800242bc  lea     rax, [rsp+210h+var_198]
0x1800242c1  mov     [rsp+210h+var_1A0], rax
0x1800242c6  lea     rcx, [rsp+210h+lpFileName]
0x1800242cb  xor     eax, eax
0x1800242cd  mov     [rsp+210h+var_198], ax
0x1800242d2  lea     r8d, [rax+11h]
0x1800242d6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800242db  test    al, al
0x1800242dd  jnz     short loc_1800242E6
0x1800242df  mov     edx, 332h
0x1800242e4  jmp     short loc_180024309
0x1800242e6  mov     r8, [rsp+210h+var_1C0]
0x1800242eb  lea     rcx, [rsp+210h+lpFileName]
0x1800242f0  mov     rdx, [rsp+210h+var_1C8]
0x1800242f5  sub     r8, rdx
0x1800242f8  sar     r8, 1
0x1800242fb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180024300  test    al, al
0x180024302  jnz     short loc_180024362
0x180024304  mov     edx, 333h; void *
0x180024309  mov     rcx, [rbp+118h]; this
0x180024310  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024317  mov     r9d, 8007000Eh; char *
0x18002431d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024322  mov     rcx, [rsp+210h+lpFileName]; void *
0x180024327  lea     rax, [rsp+210h+var_198]
0x18002432c  cmp     rcx, rax
0x18002432f  jz      short loc_18002433D
0x180024331  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024338  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002433d  mov     rcx, [rsp+210h+var_1C8]; void *
0x180024342  lea     rax, [rsp+210h+var_1B8]
0x180024347  cmp     rcx, rax
0x18002434a  jz      short loc_180024358
0x18002434c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024353  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024358  mov     eax, 8007000Eh
0x18002435d  jmp     loc_180024612
0x180024362  mov     rcx, [rsp+210h+lpFileName]; lpFileName
0x180024367  mov     r8d, 3; dwShareMode
0x18002436d  mov     [rsp+210h+hTemplateFile], 0; hTemplateFile
0x180024376  xor     r9d, r9d; lpSecurityAttributes
0x180024379  mov     [rsp+210h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x180024381  mov     edx, 0C0000000h; dwDesiredAccess
0x180024386  mov     [rsp+210h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002438b  call    cs:__imp_CreateFileW
0x180024392  nop     dword ptr [rax+rax+00h]
0x180024397  mov     rbx, rax
0x18002439a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002439e  jnz     short loc_1800243DE
0x1800243a0  mov     rcx, [rbp+118h]; this
0x1800243a7  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800243ae  mov     edx, 33Eh; void *
0x1800243b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800243b8  mov     rcx, [rsp+210h+lpFileName]; void *
0x1800243bd  mov     ebx, eax
0x1800243bf  lea     rax, [rsp+210h+var_198]
0x1800243c4  cmp     rcx, rax
0x1800243c7  jz      loc_180024289
0x1800243cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800243d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800243d9  jmp     loc_180024289
0x1800243de  mov     [rsp+210h+lpOverlapped], 0; lpOverlapped
0x1800243e7  lea     rax, [rsp+210h+BytesReturned]
0x1800243ec  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x1800243f1  xor     r9d, r9d; nInBufferSize
0x1800243f4  mov     [rsp+210h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800243fc  xor     r8d, r8d; lpInBuffer
0x1800243ff  mov     edx, 70140h; dwIoControlCode
0x180024404  mov     qword ptr [rsp+210h+dwCreationDisposition], 0; lpOutBuffer
0x18002440d  mov     rcx, rbx; hDevice
0x180024410  mov     [rsp+210h+BytesReturned], 0
0x180024418  call    cs:__imp_DeviceIoControl
0x18002441f  nop     dword ptr [rax+rax+00h]
0x180024424  test    eax, eax
0x180024426  jnz     short loc_180024445
0x180024428  mov     edx, 34Bh; void *
0x18002442d  mov     rcx, [rbp+118h]; this
0x180024434  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002443b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024440  jmp     loc_1800245C4
0x180024445  mov     edi, 150h
0x18002444a  lea     rcx, [rbp+110h+OutBuffer]; void *
0x18002444e  mov     r8d, edi; Size
0x180024451  xor     edx, edx; Val
0x180024453  call    memset_0
0x180024458  mov     [rsp+210h+lpOverlapped], 0; lpOverlapped
0x180024461  lea     rax, [rsp+210h+BytesReturned]
0x180024466  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x18002446b  xor     r9d, r9d; nInBufferSize
0x18002446e  lea     rax, [rbp+110h+OutBuffer]
0x180024472  mov     [rsp+210h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180024476  xor     r8d, r8d; lpInBuffer
0x180024479  mov     qword ptr [rsp+210h+dwCreationDisposition], rax; unsigned int
0x18002447e  mov     edx, 70050h; dwIoControlCode
0x180024483  mov     rcx, rbx; hDevice
0x180024486  call    cs:__imp_DeviceIoControl
0x18002448d  nop     dword ptr [rax+rax+00h]
0x180024492  test    eax, eax
0x180024494  jnz     short loc_18002449D
0x180024496  mov     edx, 35Fh
0x18002449b  jmp     short loc_18002442D
0x18002449d  cmp     [rbp+110h+OutBuffer], 1
0x1800244a1  jnz     loc_1800245A6
0x1800244a7  cmp     [rbp+110h+var_16C], 2
0x1800244ab  jnz     loc_1800245A6
0x1800244b1  mov     r8d, 10h; Size
0x1800244b7  lea     rdx, PARTITION_BASIC_DATA_GUID; Buf2
0x1800244be  lea     rcx, [rbp+110h+Buf1]; Buf1
0x1800244c5  call    memcmp_0
0x1800244ca  test    eax, eax
0x1800244cc  jnz     loc_18002459F
0x1800244d2  mov     rdi, [rbp+110h+var_A0]
0x1800244d6  mov     r8, [rbp+110h+var_A8]
0x1800244da  mov     rdx, [rbp+110h+var_150]
0x1800244de  add     r8, rdi
0x1800244e1  add     rdx, [rbp+110h+var_158]
0x1800244e5  cmp     r8, rdx
0x1800244e8  jge     short loc_18002454E
0x1800244ea  sub     rdx, r8
0x1800244ed  mov     [rbp+110h+var_184], eax
0x1800244f0  mov     eax, [rbp+110h+var_98]
0x1800244f3  lea     r8, [rbp+110h+InBuffer]; lpInBuffer
0x1800244f7  mov     [rsp+210h+lpOverlapped], 0; lpOverlapped
0x180024500  mov     r9d, 10h; nInBufferSize
0x180024506  mov     [rbp+110h+InBuffer], eax
0x180024509  mov     rcx, rbx; hDevice
0x18002450c  lea     rax, [rsp+210h+BytesReturned]
0x180024511  mov     [rbp+110h+var_180], rdx
0x180024515  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x18002451a  mov     edx, 7C0D0h; dwIoControlCode
0x18002451f  mov     [rsp+210h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180024527  mov     qword ptr [rsp+210h+dwCreationDisposition], 0; lpOutBuffer
0x180024530  call    cs:__imp_DeviceIoControl
0x180024537  nop     dword ptr [rax+rax+00h]
0x18002453c  test    eax, eax
0x18002453e  jnz     short loc_18002454A
0x180024540  mov     edx, 38Fh
0x180024545  jmp     loc_18002442D
0x18002454a  add     rdi, [rbp+110h+var_180]
0x18002454e  mov     [rsi], rdi
0x180024551  test    rbx, rbx
0x180024554  jz      short loc_180024565
0x180024556  mov     rcx, rbx; hObject
0x180024559  call    cs:__imp_CloseHandle
0x180024560  nop     dword ptr [rax+rax+00h]
0x180024565  mov     rcx, [rsp+210h+lpFileName]; void *
0x18002456a  lea     rax, [rsp+210h+var_198]
0x18002456f  cmp     rcx, rax
0x180024572  jz      short loc_180024580
0x180024574  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002457b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024580  mov     rcx, [rsp+210h+var_1C8]; void *
0x180024585  lea     rax, [rsp+210h+var_1B8]
0x18002458a  cmp     rcx, rax
0x18002458d  jz      short loc_18002459B
0x18002458f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024596  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002459b  xor     eax, eax
0x18002459d  jmp     short loc_180024612
0x18002459f  mov     edx, 370h
0x1800245a4  jmp     short loc_1800245AB
0x1800245a6  mov     edx, 36Ah; void *
0x1800245ab  mov     rcx, [rbp+118h]; this
0x1800245b2  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800245b9  mov     r9d, 57h ; 'W'; char *
0x1800245bf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800245c4  mov     edi, eax
0x1800245c6  test    rbx, rbx
0x1800245c9  jz      short loc_1800245DA
0x1800245cb  mov     rcx, rbx; hObject
0x1800245ce  call    cs:__imp_CloseHandle
0x1800245d5  nop     dword ptr [rax+rax+00h]
0x1800245da  mov     rcx, [rsp+210h+lpFileName]; void *
0x1800245df  lea     rax, [rsp+210h+var_198]
0x1800245e4  cmp     rcx, rax
0x1800245e7  jz      short loc_1800245F5
0x1800245e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800245f5  mov     rcx, [rsp+210h+var_1C8]; void *
0x1800245fa  lea     rax, [rsp+210h+var_1B8]
0x1800245ff  cmp     rcx, rax
0x180024602  jz      short loc_180024610
0x180024604  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002460b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024610  mov     eax, edi
0x180024612  mov     rcx, [rbp+110h+var_20]
0x180024619  xor     rcx, rsp; StackCookie
0x18002461c  call    __security_check_cookie
0x180024621  mov     rbx, [rsp+210h+arg_10]
0x180024629  add     rsp, 200h
0x180024630  pop     rdi
0x180024631  pop     rsi
0x180024632  pop     rbp
0x180024633  retn
```
