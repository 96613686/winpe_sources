# RoutingRegistryHelper::WriteAppletIdGroupAssetsRegKeys(HKEY__ *,ushort const *,_GUID const &,_AppletIdGroupAssetCollection const *)

- ea: `0x18003b6a0`
- end: `0x18003b9cb`
- name: `?WriteAppletIdGroupAssetsRegKeys@RoutingRegistryHelper@@CAJPEAUHKEY__@@PEBGAEBU_GUID@@PEBU_AppletIdGroupAssetCollection@@@Z`
- size: `811`
- prototype: `static int(HKEY, const unsigned __int16 *, const struct _GUID *, const struct _AppletIdGroupAssetCollection *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003bc1c`

## callees

- `0x1800049a0`
- `0x18000c944`
- `0x18000c964`
- `0x180013274`
- `0x180018aa0`
- `0x1800381e4`
- `0x180038884`
- `0x180038e30`
- `0x18003b6a0`
- `0x18003c35c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b768`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b8a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b8a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b97f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b97f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b8ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b8ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b807`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b807`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b84b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b84b`

## string_xrefs

- `0x18003b72d`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x18003b75c`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RoutingRegistryHelper::WriteAppletIdGroupAssetsRegKeys(
        HKEY a1,
        unsigned __int16 *a2,
        struct _GUID *a3,
        const struct _AppletIdGroupAssetCollection *a4)
{
  int AppletIdGroupAssetDataPath; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  wil **v9; // rcx
  __int64 v10; // r14
  __int64 v11; // r15
  WCHAR *StringRawBuffer; // r13
  const void *v13; // r12
  DWORD v14; // esi
  _QWORD *v15; // rdx
  __int64 v16; // r8
  const WCHAR *v17; // rcx
  HANDLE FileW; // rax
  const char *v19; // r9
  void *v20; // rbx
  int LastError; // esi
  const char *v22; // r9
  LSTATUS v23; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-89h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-89h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-89h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-89h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-51h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v32; // [rsp+70h] [rbp-39h]
  unsigned __int64 v33; // [rsp+78h] [rbp-31h]
  HKEY hKey; // [rsp+80h] [rbp-29h]
  _QWORD Src[4]; // [rsp+88h] [rbp-21h] BYREF
  wil *v36[2]; // [rsp+A8h] [rbp-1h] BYREF
  __m128i si128; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hKey = a1;
  *(_OWORD *)v36 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  AppletIdGroupAssetDataPath = RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(a2, a3, (__int64)v36);
  v7 = AppletIdGroupAssetDataPath;
  if ( AppletIdGroupAssetDataPath < 0 )
  {
    v8 = 989;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)(unsigned int)AppletIdGroupAssetDataPath,
      dwCreationDisposition);
    goto LABEL_34;
  }
  v9 = v36;
  if ( si128.m128i_i64[1] > 7uLL )
    v9 = (wil **)v36[0];
  AppletIdGroupAssetDataPath = wil::CreateDirectoryDeepNoThrow((const WCHAR *)v9, v6);
  v7 = AppletIdGroupAssetDataPath;
  if ( AppletIdGroupAssetDataPath < 0 )
  {
    v8 = 991;
    goto LABEL_7;
  }
  v10 = *((_QWORD *)a4 + 1);
  v11 = v10 + 24LL * *(unsigned int *)a4;
  if ( v10 == v11 )
  {
LABEL_33:
    v7 = 0;
    goto LABEL_34;
  }
  while ( 1 )
  {
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(*(HSTRING *)v10, 0);
    std::wstring::wstring(Src, v36);
    std::wstring::append(Src, (void *)L"\\");
    std::wstring::append(Src, StringRawBuffer);
    v13 = *(const void **)(v10 + 16);
    v14 = *(_DWORD *)(v10 + 8);
    v15 = Src;
    if ( Src[3] > 7u )
      v15 = (_QWORD *)Src[0];
    *(_OWORD *)lpFileName = 0;
    v32 = 0;
    v33 = 0;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    std::wstring::_Construct<1,unsigned short const *>(lpFileName, v15);
    v17 = (const WCHAR *)lpFileName;
    if ( v33 > 7 )
      v17 = lpFileName[0];
    FileW = CreateFileW(v17, 0x120116u, 0, 0, 2u, 0x80u, 0);
    v20 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x416,
                    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
                    v19);
      goto LABEL_26;
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, v13, v14, &NumberOfBytesWritten, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x41A,
                    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
                    v22);
      goto LABEL_19;
    }
    if ( NumberOfBytesWritten != v14 )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41B,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDispositiona);
LABEL_19:
      if ( v20 )
        CloseHandle(v20);
      goto LABEL_26;
    }
    if ( v20 )
      CloseHandle(v20);
    LastError = 0;
LABEL_26:
    std::wstring::~wstring(lpFileName);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E9,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationDispositiona);
      std::wstring::~wstring(Src);
      v7 = LastError;
      goto LABEL_34;
    }
    phkResult = 0;
    v23 = RegCreateKeyExW(hKey, StringRawBuffer, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    v7 = v23;
    if ( v23 > 0 )
      v7 = (unsigned __int16)v23 | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
      break;
    if ( phkResult )
      RegCloseKey(phkResult);
    std::wstring::~wstring(Src);
    v10 += 24;
    if ( v10 == v11 )
      goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43A,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
    (const char *)v7,
    dwCreationDispositionb);
  if ( phkResult )
    RegCloseKey(phkResult);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3EB,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
    (const char *)v7,
    dwCreationDispositionc);
  std::wstring::~wstring(Src);
LABEL_34:
  std::wstring::~wstring(v36);
  return v7;
}

```

## disassembly

```asm
0x18003b6a0  mov     [rsp-8+arg_18], rbx
0x18003b6a5  push    rbp
0x18003b6a6  push    rsi
0x18003b6a7  push    rdi
0x18003b6a8  push    r12
0x18003b6aa  push    r13
0x18003b6ac  push    r14
0x18003b6ae  push    r15
0x18003b6b0  lea     rbp, [rsp-27h]
0x18003b6b5  sub     rsp, 0D0h
0x18003b6bc  mov     rax, cs:__security_cookie
0x18003b6c3  xor     rax, rsp
0x18003b6c6  mov     [rbp+57h+var_38], rax
0x18003b6ca  mov     rdi, r9
0x18003b6cd  mov     r11, r8
0x18003b6d0  mov     r10, rdx
0x18003b6d3  mov     [rbp+57h+hKey], rcx
0x18003b6d7  xorps   xmm0, xmm0
0x18003b6da  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18003b6de  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003b6e6  movdqu  [rbp+57h+var_48], xmm1
0x18003b6eb  xor     r12d, r12d
0x18003b6ee  mov     word ptr [rbp+57h+var_58], r12w
0x18003b6f3  lea     r8, [rbp+57h+var_58]
0x18003b6f7  mov     rdx, r11; rguid
0x18003b6fa  mov     rcx, r10; void *
0x18003b6fd  call    ?GetAppletIdGroupAssetDataPath@RoutingRegistryHelper@@CAJPEBGAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(ushort const *,_GUID const &,std::wstring *)
0x18003b702  mov     ebx, eax
0x18003b704  test    eax, eax
0x18003b706  jns     short loc_18003B70F
0x18003b708  mov     edx, 3DDh
0x18003b70d  jmp     short loc_18003B72D
0x18003b70f  lea     rcx, [rbp+57h+var_58]
0x18003b713  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18003b718  cmova   rcx, [rbp+57h+var_58]; this
0x18003b71d  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003b722  mov     ebx, eax
0x18003b724  test    eax, eax
0x18003b726  jns     short loc_18003B745
0x18003b728  mov     edx, 3DFh; void *
0x18003b72d  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003b734  mov     r9d, eax; char *
0x18003b737  mov     rcx, [rbp+5Fh]; this
0x18003b73b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b740  jmp     loc_18003B930
0x18003b745  mov     r14, [rdi+8]
0x18003b749  mov     eax, [rdi]
0x18003b74b  lea     rcx, [rax+rax*2]
0x18003b74f  lea     r15, [r14+rcx*8]
0x18003b753  cmp     r14, r15
0x18003b756  jz      loc_18003B92D
0x18003b75c  lea     rdi, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003b763  xor     edx, edx; length
0x18003b765  mov     rcx, [r14]; string
0x18003b768  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b76e  mov     r13, rax
0x18003b771  lea     rdx, [rbp+57h+var_58]
0x18003b775  lea     rcx, [rbp+57h+Src]
0x18003b779  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003b77e  nop
0x18003b77f  lea     rdx, StringValue; "\\"
0x18003b786  lea     rcx, [rbp+57h+Src]; Src
0x18003b78a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003b78f  mov     rdx, r13; void *
0x18003b792  lea     rcx, [rbp+57h+Src]; Src
0x18003b796  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003b79b  mov     r12, [r14+10h]
0x18003b79f  mov     esi, [r14+8]
0x18003b7a3  lea     rdx, [rbp+57h+Src]
0x18003b7a7  cmp     [rbp+57h+var_60], 7
0x18003b7ac  cmova   rdx, [rbp+57h+Src]
0x18003b7b1  xorps   xmm0, xmm0
0x18003b7b4  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18003b7b8  xor     ebx, ebx
0x18003b7ba  mov     [rbp+57h+var_90], rbx
0x18003b7be  mov     [rbp+57h+var_88], rbx
0x18003b7c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b7c6  inc     r8
0x18003b7c9  cmp     [rdx+r8*2], bx
0x18003b7ce  jnz     short loc_18003B7C6
0x18003b7d0  lea     rcx, [rbp+57h+lpFileName]
0x18003b7d4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b7d9  lea     rcx, [rbp+57h+lpFileName]
0x18003b7dd  cmp     [rbp+57h+var_88], 7
0x18003b7e2  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18003b7e7  mov     [rsp+100h+hTemplateFile], rbx; hTemplateFile
0x18003b7ec  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003b7f4  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x18003b7fc  xor     r9d, r9d; lpSecurityAttributes
0x18003b7ff  xor     r8d, r8d; dwShareMode
0x18003b802  mov     edx, 120116h; dwDesiredAccess
0x18003b807  call    cs:__imp_CreateFileW
0x18003b80d  mov     rbx, rax
0x18003b810  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b814  jnz     short loc_18003B82E
0x18003b816  mov     rcx, [rbp+5Fh]; this
0x18003b81a  mov     r8, rdi; unsigned int
0x18003b81d  mov     edx, 416h; void *
0x18003b822  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b827  mov     esi, eax
0x18003b829  xor     r12d, r12d
0x18003b82c  jmp     short loc_18003B8AC
0x18003b82e  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18003b835  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; int
0x18003b83e  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003b842  mov     r8d, esi; nNumberOfBytesToWrite
0x18003b845  mov     rdx, r12; lpBuffer
0x18003b848  mov     rcx, rbx; hFile
0x18003b84b  call    cs:__imp_WriteFile
0x18003b851  xor     r12d, r12d
0x18003b854  test    eax, eax
0x18003b856  jnz     short loc_18003B87B
0x18003b858  mov     rcx, [rbp+5Fh]; this
0x18003b85c  mov     r8, rdi; unsigned int
0x18003b85f  mov     edx, 41Ah; void *
0x18003b864  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b869  mov     esi, eax
0x18003b86b  test    rbx, rbx
0x18003b86e  jz      short loc_18003B8AC
0x18003b870  mov     rcx, rbx; hObject
0x18003b873  call    cs:__imp_CloseHandle
0x18003b879  jmp     short loc_18003B8AC
0x18003b87b  cmp     [rbp+57h+NumberOfBytesWritten], esi
0x18003b87e  jz      short loc_18003B89B
0x18003b880  mov     rcx, [rbp+5Fh]; this
0x18003b884  mov     esi, 8000FFFFh
0x18003b889  mov     r9d, esi; char *
0x18003b88c  mov     r8, rdi; unsigned int
0x18003b88f  mov     edx, 41Bh; void *
0x18003b894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b899  jmp     short loc_18003B86B
0x18003b89b  test    rbx, rbx
0x18003b89e  jz      short loc_18003B8A9
0x18003b8a0  mov     rcx, rbx; hObject
0x18003b8a3  call    cs:__imp_CloseHandle
0x18003b8a9  mov     esi, r12d
0x18003b8ac  lea     rcx, [rbp+57h+lpFileName]
0x18003b8b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b8b5  test    esi, esi
0x18003b8b7  js      loc_18003B9A5
0x18003b8bd  mov     [rbp+57h+var_A8], r12
0x18003b8c1  mov     [rsp+100h+lpdwDisposition], r12; lpdwDisposition
0x18003b8c6  lea     rax, [rbp+57h+var_A8]
0x18003b8ca  mov     [rsp+100h+phkResult], rax; phkResult
0x18003b8cf  mov     [rsp+100h+hTemplateFile], r12; lpSecurityAttributes
0x18003b8d4  mov     [rsp+100h+dwFlagsAndAttributes], 2001Fh; samDesired
0x18003b8dc  mov     [rsp+100h+dwCreationDisposition], r12d; int
0x18003b8e1  xor     r9d, r9d; lpClass
0x18003b8e4  xor     r8d, r8d; Reserved
0x18003b8e7  mov     rdx, r13; lpSubKey
0x18003b8ea  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b8ee  call    cs:__imp_RegCreateKeyExW
0x18003b8f4  mov     ebx, eax
0x18003b8f6  test    eax, eax
0x18003b8f8  jle     short loc_18003B903
0x18003b8fa  movzx   ebx, ax
0x18003b8fd  or      ebx, 80070000h
0x18003b903  test    ebx, ebx
0x18003b905  js      short loc_18003B962
0x18003b907  mov     rcx, [rbp+57h+var_A8]; hKey
0x18003b90b  test    rcx, rcx
0x18003b90e  jz      short loc_18003B917
0x18003b910  call    cs:__imp_RegCloseKey
0x18003b916  nop
0x18003b917  lea     rcx, [rbp+57h+Src]
0x18003b91b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b920  add     r14, 18h
0x18003b924  cmp     r14, r15
0x18003b927  jnz     loc_18003B763
0x18003b92d  mov     ebx, r12d
0x18003b930  lea     rcx, [rbp+57h+var_58]
0x18003b934  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b939  mov     eax, ebx
0x18003b93b  mov     rcx, [rbp+57h+var_38]
0x18003b93f  xor     rcx, rsp; StackCookie
0x18003b942  call    __security_check_cookie
0x18003b947  mov     rbx, [rsp+100h+arg_18]
0x18003b94f  add     rsp, 0D0h
0x18003b956  pop     r15
0x18003b958  pop     r14
0x18003b95a  pop     r13
0x18003b95c  pop     r12
0x18003b95e  pop     rdi
0x18003b95f  pop     rsi
0x18003b960  pop     rbp
0x18003b961  retn
0x18003b962  mov     rcx, [rbp+5Fh]; this
0x18003b966  mov     r9d, ebx; char *
0x18003b969  mov     r8, rdi; unsigned int
0x18003b96c  mov     edx, 43Ah; void *
0x18003b971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b976  mov     rcx, [rbp+57h+var_A8]; hKey
0x18003b97a  test    rcx, rcx
0x18003b97d  jz      short loc_18003B985
0x18003b97f  call    cs:__imp_RegCloseKey
0x18003b985  mov     rcx, [rbp+5Fh]; this
0x18003b989  mov     r9d, ebx; char *
0x18003b98c  mov     r8, rdi; unsigned int
0x18003b98f  mov     edx, 3EBh; void *
0x18003b994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b999  nop
0x18003b99a  lea     rcx, [rbp+57h+Src]
0x18003b99e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b9a3  jmp     short loc_18003B930
0x18003b9a5  mov     rcx, [rbp+5Fh]; this
0x18003b9a9  mov     r9d, esi; char *
0x18003b9ac  mov     r8, rdi; unsigned int
0x18003b9af  mov     edx, 3E9h; void *
0x18003b9b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b9b9  nop
0x18003b9ba  lea     rcx, [rbp+57h+Src]
0x18003b9be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b9c3  mov     ebx, esi
0x18003b9c5  jmp     loc_18003B930
```
