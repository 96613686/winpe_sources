# Appx::Packaging::AppxFactoryInternalImpl::LookupCapabilityDisplayName(void *,ushort * *)

- ea: `0x1800c6110`
- end: `0x1800c642e`
- name: `?LookupCapabilityDisplayName@AppxFactoryInternalImpl@Packaging@Appx@@UEAAJPEAXPEAPEAG@Z`
- size: `798`
- prototype: `int(Appx::Packaging::AppxFactoryInternalImpl *__hidden this, void *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800133fc`
- `0x180026a60`
- `0x180046e28`
- `0x180078454`
- `0x180097278`
- `0x1800992a0`
- `0x1800c6110`
- `0x1800c6434`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6336`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6386`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c63a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6336`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6386`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c63a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c62ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c62ac`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800c62f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800c62f6`
- `ntdll!RtlIsCapabilitySid` at `0x1800c6238`
- `ntdll!RtlIsCapabilitySid` at `0x1800c6238`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800c6255`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800c6255`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800c6278`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800c6278`

## string_xrefs

- `0x1800c6318`: `onecore\printscan\appxpackaging\dll\lib\appxfactoryinternal.cpp`
- `0x1800c6368`: `onecore\printscan\appxpackaging\dll\lib\appxfactoryinternal.cpp`
- `0x1800c63d6`: `onecore\printscan\appxpackaging\dll\lib\appxfactoryinternal.cpp`
- `0x1800c63f7`: `onecore\printscan\appxpackaging\dll\lib\appxfactoryinternal.cpp`
- `0x1800c62a5`: `lsasrv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Appx::Packaging::AppxFactoryInternalImpl::LookupCapabilityDisplayName(
        Appx::Packaging::AppxFactoryInternalImpl *this,
        unsigned __int8 *a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  DWORD v7; // ecx
  __int64 i; // rax
  __int64 v9; // rsi
  Common *v10; // rcx
  HMODULE Library; // rdi
  DWORD v12; // eax
  Common *v13; // rcx
  unsigned int v14; // r8d
  int v15; // eax
  void *v16; // rdx
  unsigned __int16 *v17; // rax
  void *v18; // rdx
  void *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int HResultFromLastError; // eax
  int *lpBuffer; // [rsp+28h] [rbp-69h]
  int lpBuffera; // [rsp+28h] [rbp-69h]
  WCHAR Buffer[4]; // [rsp+48h] [rbp-49h] BYREF
  int v27; // [rsp+58h] [rbp-39h]
  DWORD dwMessageId[19]; // [rsp+5Ch] [rbp-35h]
  __int64 v29; // [rsp+A8h] [rbp+17h]
  int v30; // [rsp+B0h] [rbp+1Fh] BYREF
  unsigned __int8 *v31; // [rsp+C0h] [rbp+2Fh]
  int v32; // [rsp+C8h] [rbp+37h]
  int v33; // [rsp+CCh] [rbp+3Bh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v29 = -2;
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 200;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxfactoryinternal.cpp",
      (const char *)v5,
      (int)lpBuffer);
    return v5;
  }
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 201;
    goto LABEL_30;
  }
  v27 = 1;
  dwMessageId[0] = 8243;
  dwMessageId[1] = 2;
  dwMessageId[2] = 8244;
  dwMessageId[3] = 3;
  dwMessageId[4] = 8245;
  dwMessageId[5] = 4;
  dwMessageId[6] = 8246;
  dwMessageId[7] = 5;
  dwMessageId[8] = 8247;
  dwMessageId[9] = 6;
  dwMessageId[10] = 8248;
  dwMessageId[11] = 7;
  dwMessageId[12] = 8249;
  dwMessageId[13] = 8;
  dwMessageId[14] = 8251;
  dwMessageId[15] = 9;
  dwMessageId[16] = 8252;
  dwMessageId[17] = 10;
  dwMessageId[18] = 8253;
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
  {
    v31 = a2;
    v32 = 4 * a2[1] + 8;
    v33 = 0;
    lpBuffer = &v30;
    McGenEventWrite_EventWriteTransfer(this, EVENT_LOOKUP_CAPABILITY_DISPLAY_NAME_START, a3, 2);
  }
  if ( !(unsigned __int8)RtlIsCapabilitySid(a2) )
  {
    v6 = 231;
LABEL_29:
    v5 = -2147024809;
    goto LABEL_30;
  }
  if ( *GetSidSubAuthorityCount(a2) != 2 )
  {
    v6 = 236;
    goto LABEL_29;
  }
  v7 = *GetSidSubAuthority(a2, 1u);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0xA )
    {
      v6 = 271;
      goto LABEL_29;
    }
    v9 = (unsigned int)i;
    if ( v7 == dwMessageId[2 * i - 1] )
      break;
  }
  Library = LoadLibraryExW(L"lsasrv.dll", 0, 0x802u);
  if ( !Library )
  {
    HResultFromLastError = Common::GetHResultFromLastError(v10);
    v5 = HResultFromLastError;
    if ( HResultFromLastError < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxfactoryinternal.cpp",
        (const char *)(unsigned int)HResultFromLastError,
        (int)lpBuffer);
    return v5;
  }
  *(_QWORD *)Buffer = 0;
  v12 = FormatMessageW(0x9FFu, Library, dwMessageId[2 * v9], 0, Buffer, 0, 0);
  if ( !v12 )
  {
    v15 = Common::GetHResultFromLastError(v13);
    v5 = v15;
    if ( v15 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxfactoryinternal.cpp",
        (const char *)(unsigned int)v15,
        lpBuffera);
    Common::AutoHandleFreeHLocal(*(Common **)Buffer, v16);
    FreeLibrary(Library);
    return v5;
  }
  v17 = Common::AutoCoTaskMemStringAllocateAndCopy(*(Common **)Buffer, (const unsigned __int16 *)(v12 - 1), v14);
  *a3 = v17;
  if ( !v17 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxfactoryinternal.cpp",
      (const char *)0x8007000ELL,
      lpBuffera);
    Common::AutoHandleFreeHLocal(*(Common **)Buffer, v19);
    FreeLibrary(Library);
    return v5;
  }
  Common::AutoHandleFreeHLocal(*(Common **)Buffer, v18);
  FreeLibrary(Library);
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    McTemplateU0kd_EventWriteTransfer(v21, v20, a2);
  return 0;
}

```

## disassembly

```asm
0x1800c6110  mov     rax, rsp
0x1800c6113  push    rbp
0x1800c6114  push    rdi
0x1800c6115  push    r14
0x1800c6117  lea     rbp, [rax-5Fh]
0x1800c611b  sub     rsp, 0D0h
0x1800c6122  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800c612a  mov     [rax+8], rbx
0x1800c612e  mov     [rax+20h], rsi
0x1800c6132  mov     rax, cs:__security_cookie
0x1800c6139  xor     rax, rsp
0x1800c613c  mov     [rbp+57h+var_18], rax
0x1800c6140  mov     r14, r8
0x1800c6143  mov     rbx, rdx
0x1800c6146  test    rdx, rdx
0x1800c6149  jnz     short loc_1800C615A
0x1800c614b  mov     ebx, 80004003h
0x1800c6150  mov     edx, 0C8h
0x1800c6155  jmp     loc_1800C63F4
0x1800c615a  test    r14, r14
0x1800c615d  jnz     short loc_1800C616E
0x1800c615f  mov     ebx, 80004003h
0x1800c6164  mov     edx, 0C9h
0x1800c6169  jmp     loc_1800C63F4
0x1800c616e  mov     [rbp+57h+var_90], 1
0x1800c6175  mov     [rbp+57h+dwMessageId], 2033h
0x1800c617c  mov     edi, 2
0x1800c6181  mov     [rbp+57h+var_88], edi
0x1800c6184  mov     [rbp+57h+var_84], 2034h
0x1800c618b  mov     [rbp+57h+var_80], 3
0x1800c6192  mov     [rbp+57h+var_7C], 2035h
0x1800c6199  mov     [rbp+57h+var_78], 4
0x1800c61a0  mov     [rbp+57h+var_74], 2036h
0x1800c61a7  mov     [rbp+57h+var_70], 5
0x1800c61ae  mov     [rbp+57h+var_6C], 2037h
0x1800c61b5  mov     [rbp+57h+var_68], 6
0x1800c61bc  mov     [rbp+57h+var_64], 2038h
0x1800c61c3  mov     [rbp+57h+var_60], 7
0x1800c61ca  mov     [rbp+57h+var_5C], 2039h
0x1800c61d1  mov     [rbp+57h+var_58], 8
0x1800c61d8  mov     [rbp+57h+var_54], 203Bh
0x1800c61df  mov     [rbp+57h+var_50], 9
0x1800c61e6  mov     [rbp+57h+var_4C], 203Ch
0x1800c61ed  mov     [rbp+57h+var_48], 0Ah
0x1800c61f4  mov     [rbp+57h+var_44], 203Dh
0x1800c61fb  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x1800c6202  jz      short loc_1800C6235
0x1800c6204  mov     [rbp+57h+var_28], rbx
0x1800c6208  movzx   eax, byte ptr [rdx+1]
0x1800c620c  lea     eax, ds:8[rax*4]
0x1800c6213  mov     [rbp+57h+var_20], eax
0x1800c6216  mov     [rbp+57h+var_1C], 0
0x1800c621d  lea     rax, [rbp+57h+var_38]
0x1800c6221  mov     [rsp+0E0h+lpBuffer], rax; int
0x1800c6226  mov     r9d, edi
0x1800c6229  lea     rdx, EVENT_LOOKUP_CAPABILITY_DISPLAY_NAME_START
0x1800c6230  call    McGenEventWrite_EventWriteTransfer
0x1800c6235  mov     rcx, rbx
0x1800c6238  call    cs:__imp_RtlIsCapabilitySid
0x1800c623f  nop     dword ptr [rax+rax+00h]
0x1800c6244  test    al, al
0x1800c6246  jnz     short loc_1800C6252
0x1800c6248  mov     edx, 0E7h
0x1800c624d  jmp     loc_1800C63EF
0x1800c6252  mov     rcx, rbx; pSid
0x1800c6255  call    cs:__imp_GetSidSubAuthorityCount
0x1800c625c  nop     dword ptr [rax+rax+00h]
0x1800c6261  cmp     [rax], dil
0x1800c6264  jz      short loc_1800C6270
0x1800c6266  mov     edx, 0ECh
0x1800c626b  jmp     loc_1800C63EF
0x1800c6270  mov     edx, 1; nSubAuthority
0x1800c6275  mov     rcx, rbx; pSid
0x1800c6278  call    cs:__imp_GetSidSubAuthority
0x1800c627f  nop     dword ptr [rax+rax+00h]
0x1800c6284  mov     ecx, [rax]
0x1800c6286  xor     eax, eax
0x1800c6288  cmp     eax, 0Ah
0x1800c628b  jnb     loc_1800C63EA
0x1800c6291  mov     esi, eax
0x1800c6293  cmp     ecx, [rbp+rax*8+57h+var_90]
0x1800c6297  jz      short loc_1800C629D
0x1800c6299  inc     eax
0x1800c629b  jmp     short loc_1800C6288
0x1800c629d  xor     edx, edx; hFile
0x1800c629f  mov     r8d, 802h; dwFlags
0x1800c62a5  lea     rcx, aLsasrvDll; "lsasrv.dll"
0x1800c62ac  call    cs:__imp_LoadLibraryExW
0x1800c62b3  nop     dword ptr [rax+rax+00h]
0x1800c62b8  mov     rdi, rax
0x1800c62bb  test    rax, rax
0x1800c62be  jz      loc_1800C63C4
0x1800c62c4  mov     qword ptr [rbp+57h+Buffer], 0
0x1800c62cc  mov     [rsp+0E0h+Arguments], 0; Arguments
0x1800c62d5  mov     [rsp+0E0h+nSize], 0; nSize
0x1800c62dd  lea     rax, [rbp+57h+Buffer]
0x1800c62e1  mov     [rsp+0E0h+lpBuffer], rax; int
0x1800c62e6  xor     r9d, r9d; dwLanguageId
0x1800c62e9  mov     r8d, [rbp+rsi*8+57h+dwMessageId]; dwMessageId
0x1800c62ee  mov     rdx, rdi; lpSource
0x1800c62f1  mov     ecx, 9FFh; dwFlags
0x1800c62f6  call    cs:__imp_FormatMessageW
0x1800c62fd  nop     dword ptr [rax+rax+00h]
0x1800c6302  test    eax, eax
0x1800c6304  jnz     short loc_1800C6348
0x1800c6306  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800c630b  mov     ebx, eax
0x1800c630d  test    eax, eax
0x1800c630f  jns     short loc_1800C6329
0x1800c6311  mov     rcx, [rbp+5Fh]; this
0x1800c6315  mov     r9d, eax; char *
0x1800c6318  lea     r8, aOnecorePrintsc_194; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c631f  mov     edx, 106h; void *
0x1800c6324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6329  mov     rcx, qword ptr [rbp+57h+Buffer]; this
0x1800c632d  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800c6332  nop
0x1800c6333  mov     rcx, rdi; hLibModule
0x1800c6336  call    cs:__imp_FreeLibrary
0x1800c633d  nop     dword ptr [rax+rax+00h]
0x1800c6342  nop
0x1800c6343  jmp     loc_1800C6407
0x1800c6348  lea     edx, [rax-1]; unsigned __int16 *
0x1800c634b  mov     rcx, qword ptr [rbp+57h+Buffer]; this
0x1800c634f  call    ?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z; Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint)
0x1800c6354  mov     [r14], rax
0x1800c6357  test    rax, rax
0x1800c635a  jnz     short loc_1800C6395
0x1800c635c  mov     rcx, [rbp+5Fh]; this
0x1800c6360  mov     ebx, 8007000Eh
0x1800c6365  mov     r9d, ebx; char *
0x1800c6368  lea     r8, aOnecorePrintsc_194; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c636f  mov     edx, 10Bh; void *
0x1800c6374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6379  mov     rcx, qword ptr [rbp+57h+Buffer]; this
0x1800c637d  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800c6382  nop
0x1800c6383  mov     rcx, rdi; hLibModule
0x1800c6386  call    cs:__imp_FreeLibrary
0x1800c638d  nop     dword ptr [rax+rax+00h]
0x1800c6392  nop
0x1800c6393  jmp     short loc_1800C6407
0x1800c6395  mov     rcx, qword ptr [rbp+57h+Buffer]; this
0x1800c6399  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800c639e  nop
0x1800c639f  mov     rcx, rdi; hLibModule
0x1800c63a2  call    cs:__imp_FreeLibrary
0x1800c63a9  nop     dword ptr [rax+rax+00h]
0x1800c63ae  nop
0x1800c63af  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x1800c63b6  jz      short loc_1800C63C0
0x1800c63b8  mov     r8, rbx
0x1800c63bb  call    McTemplateU0kd_EventWriteTransfer
0x1800c63c0  xor     eax, eax
0x1800c63c2  jmp     short loc_1800C6409
0x1800c63c4  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800c63c9  mov     ebx, eax
0x1800c63cb  test    eax, eax
0x1800c63cd  jns     short loc_1800C63E8
0x1800c63cf  mov     rcx, [rbp+5Fh]; this
0x1800c63d3  mov     r9d, eax; char *
0x1800c63d6  lea     r8, aOnecorePrintsc_194; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c63dd  mov     edx, 0F9h; void *
0x1800c63e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c63e7  nop
0x1800c63e8  jmp     short loc_1800C6407
0x1800c63ea  mov     edx, 10Fh; void *
0x1800c63ef  mov     ebx, 80070057h
0x1800c63f4  mov     r9d, ebx; char *
0x1800c63f7  lea     r8, aOnecorePrintsc_194; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c63fe  mov     rcx, [rbp+5Fh]; this
0x1800c6402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6407  mov     eax, ebx
0x1800c6409  mov     rcx, [rbp+57h+var_18]
0x1800c640d  xor     rcx, rsp; StackCookie
0x1800c6410  call    __security_check_cookie
0x1800c6415  lea     r11, [rsp+0E0h+var_10]
0x1800c641d  mov     rbx, [r11+20h]
0x1800c6421  mov     rsi, [r11+38h]
0x1800c6425  mov     rsp, r11
0x1800c6428  pop     r14
0x1800c642a  pop     rdi
0x1800c642b  pop     rbp
0x1800c642c  retn
```
