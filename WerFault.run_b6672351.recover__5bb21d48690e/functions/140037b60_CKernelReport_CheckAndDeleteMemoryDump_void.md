# CKernelReport::CheckAndDeleteMemoryDump(void)

- ea: `0x140037b60`
- end: `0x140037ebd`
- name: `?CheckAndDeleteMemoryDump@CKernelReport@@AEAAXXZ`
- size: `861`
- prototype: `void __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14003bbd4`

## callees

- `0x140001150`
- `0x140002490`
- `0x140002748`
- `0x14000b580`
- `0x1400372dc`
- `0x140037b60`
- `0x14003e22c`
- `0x140046d00`
- `0x1400472e0`
- `0x1400474a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037d67`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140037c75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140037c75`

## string_xrefs

- `0x140037bfc`: `CKernelReport::CheckAndDeleteMemoryDump`

## pseudocode

```c
void __fastcall CKernelReport::CheckAndDeleteMemoryDump(CKernelReport *this)
{
  unsigned __int64 v1; // rsi
  int Settings; // eax
  unsigned __int64 *v3; // r8
  unsigned int v4; // ebx
  unsigned __int64 v5; // rdi
  int v6; // eax
  int v7; // r14d
  __int64 v8; // r9
  __int64 v9; // r8
  LPCWSTR v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // edx
  signed int LastError; // eax
  wchar_t *v15; // [rsp+20h] [rbp-E0h]
  const char *v16; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  void *v20; // [rsp+58h] [rbp-A8h]
  _WORD *v21; // [rsp+60h] [rbp-A0h]
  _WORD v22[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h]
  _WORD *v24; // [rsp+80h] [rbp-80h]
  _WORD v25[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  unsigned int v27; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v28; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v29; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t v31[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v32; // [rsp+F0h] [rbp-10h]
  __int64 v33; // [rsp+F8h] [rbp-8h]
  const char **v34; // [rsp+100h] [rbp+0h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  unsigned __int64 *v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  unsigned __int64 *v38; // [rsp+120h] [rbp+20h]
  __int64 v39; // [rsp+128h] [rbp+28h]
  unsigned __int64 *v40; // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  int *v42; // [rsp+140h] [rbp+40h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  char v44[16]; // [rsp+150h] [rbp+50h] BYREF
  LPCWSTR v45; // [rsp+160h] [rbp+60h]
  int v46; // [rsp+168h] [rbp+68h]
  int v47; // [rsp+16Ch] [rbp+6Ch]
  wchar_t *v48; // [rsp+170h] [rbp+70h]
  int v49; // [rsp+178h] [rbp+78h]
  int v50; // [rsp+17Ch] [rbp+7Ch]
  wil::details::in1diag4 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v26 = 5;
  v22[0] = 0;
  v20 = v22;
  v25[0] = 0;
  v21 = v22;
  v19 = 1;
  lpFileName = v25;
  v1 = 0;
  v27 = 0;
  v24 = v25;
  v17 = 0;
  Settings = CCrashControlSettings::LoadSettings((CCrashControlSettings *)&v19);
  if ( Settings >= 0 )
  {
    v4 = 1;
    v5 = v27;
    if ( lpFileName && *lpFileName && !HIDWORD(v26) && v27 )
    {
      v6 = QueryVolumeFreeSpace(lpFileName, &v17, v3);
      v1 = v17;
      v7 = v6;
      if ( v6 >= 0 && v17 < v5 )
      {
        if ( DeleteFileW(lpFileName) )
        {
          v31[0] = 0;
          if ( (unsigned int)v5 <= 0x400 )
            v8 = 1;
          else
            v8 = (unsigned int)v5 >> 10;
          StringCchPrintfW(v31, 0x20u, L"%u", v8);
          if ( (Microsoft_Windows_WER_SystemErrorReportingEnableBits & 2) != 0 )
          {
            v10 = lpFileName;
            v11 = -1;
            if ( lpFileName )
            {
              v12 = -1;
              do
                ++v12;
              while ( lpFileName[v12] );
              v13 = 2 * v12 + 2;
            }
            else
            {
              v10 = L"NULL";
              v13 = 10;
            }
            v45 = v10;
            v46 = v13;
            v47 = 0;
            do
              ++v11;
            while ( v31[v11] );
            v50 = 0;
            v49 = 2 * v11 + 2;
            v48 = v31;
            McGenEventWrite_EventWriteTransfer(
              S_Microsoft_Windows_WER_SystemErrorReporting_Context,
              EventDeletingDumpFile,
              v9,
              3,
              v44);
          }
          SystemErrorReportingTelemetry(0x400003FAu, 4u, lpFileName, v31, 0);
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      v7 = 1;
    }
    if ( (unsigned int)dword_14007E000 > 5
      && (qword_14007E010 & 0x400000000000LL) != 0
      && (qword_14007E018 & 0x400000000000LL) == qword_14007E018 )
    {
      v42 = &v18;
      v18 = v7;
      LOBYTE(v16) = HIDWORD(v26) != 0;
      v39 = 8;
      v37 = 8;
      v40 = &v17;
      v33 = 8;
      v38 = &v28;
      LODWORD(v17) = v4;
      v36 = &v29;
      v34 = &v16;
      v32 = &v30;
      LODWORD(v15) = 8;
      v28 = v1;
      v29 = v5;
      v30 = 0x1000000;
      v43 = 4;
      v41 = 4;
      v35 = 1;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, byte_140073303, 0, 0, v15, v31);
    }
  }
  else
  {
    LODWORD(v15) = Settings;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xBCC,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::CheckAndDeleteMemoryDump",
      (wil::details *)v15,
      (int)"Failed to load settings",
      v16);
  }
  if ( lpFileName != v25 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( v20 != v22 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x140037b60  push    rbp
0x140037b62  push    rbx
0x140037b63  push    rsi
0x140037b64  push    rdi
0x140037b65  push    r12
0x140037b67  push    r14
0x140037b69  push    r15
0x140037b6b  lea     rbp, [rsp-90h]
0x140037b73  sub     rsp, 190h
0x140037b7a  mov     rax, cs:__security_cookie
0x140037b81  xor     rax, rsp
0x140037b84  mov     [rbp+0C0h+var_40], rax
0x140037b8b  xor     r15d, r15d
0x140037b8e  mov     [rbp+0C0h+var_128], 5
0x140037b96  lea     rax, [rsp+1C0h+var_158]
0x140037b9b  mov     [rsp+1C0h+var_158], r15w
0x140037ba1  mov     [rsp+1C0h+var_168], rax
0x140037ba6  lea     rcx, [rsp+1C0h+var_170]; this
0x140037bab  lea     rax, [rsp+1C0h+var_158]
0x140037bb0  mov     [rbp+0C0h+var_138], r15w
0x140037bb5  mov     [rsp+1C0h+var_160], rax
0x140037bba  lea     r12d, [r15+1]
0x140037bbe  lea     rax, [rbp+0C0h+var_138]
0x140037bc2  mov     [rsp+1C0h+var_170], r12
0x140037bc7  mov     [rsp+1C0h+lpFileName], rax
0x140037bcc  mov     esi, r15d
0x140037bcf  lea     rax, [rbp+0C0h+var_138]
0x140037bd3  mov     [rbp+0C0h+var_120], r15d
0x140037bd7  mov     [rbp+0C0h+var_140], rax
0x140037bdb  mov     [rsp+1C0h+var_188], r15
0x140037be0  call    ?LoadSettings@CCrashControlSettings@@QEAAJXZ; CCrashControlSettings::LoadSettings(void)
0x140037be5  test    eax, eax
0x140037be7  jns     short loc_140037C1D
0x140037be9  mov     rcx, [rbp+0C8h]; this
0x140037bf0  lea     rdx, aFailedToLoadSe; "Failed to load settings"
0x140037bf7  mov     qword ptr [rsp+1C0h+var_198], rdx; int
0x140037bfc  lea     r9, aCkernelreportC; "CKernelReport::CheckAndDeleteMemoryDump"
0x140037c03  mov     edx, 0BCCh; void *
0x140037c08  mov     dword ptr [rsp+1C0h+var_1A0], eax; wil::details *
0x140037c0c  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140037c13  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140037c18  jmp     loc_140037E66
0x140037c1d  mov     rcx, [rsp+1C0h+lpFileName]; Src
0x140037c22  mov     ebx, r12d
0x140037c25  mov     edi, [rbp+0C0h+var_120]
0x140037c28  test    rcx, rcx
0x140037c2b  jz      loc_140037D84
0x140037c31  cmp     [rcx], r15w
0x140037c35  jz      loc_140037D84
0x140037c3b  cmp     dword ptr [rbp+0C0h+var_128+4], r15d
0x140037c3f  jnz     loc_140037D84
0x140037c45  test    edi, edi
0x140037c47  jz      loc_140037D84
0x140037c4d  lea     rdx, [rsp+1C0h+var_188]; unsigned __int64 *
0x140037c52  call    ?QueryVolumeFreeSpace@@YAJPEB_WPEA_K1@Z; QueryVolumeFreeSpace(wchar_t const *,unsigned __int64 *,unsigned __int64 *)
0x140037c57  mov     rsi, [rsp+1C0h+var_188]
0x140037c5c  mov     r14d, eax
0x140037c5f  test    eax, eax
0x140037c61  js      loc_140037D87
0x140037c67  cmp     rsi, rdi
0x140037c6a  jnb     loc_140037D87
0x140037c70  mov     rcx, [rsp+1C0h+lpFileName]; lpFileName
0x140037c75  call    cs:__imp_DeleteFileW
0x140037c7c  nop     dword ptr [rax+rax+00h]
0x140037c81  test    eax, eax
0x140037c83  jz      loc_140037D67
0x140037c89  mov     [rbp+0C0h+var_F0], r15w
0x140037c8e  cmp     edi, 400h
0x140037c94  jbe     short loc_140037C9F
0x140037c96  mov     r9d, edi
0x140037c99  shr     r9d, 0Ah
0x140037c9d  jmp     short loc_140037CA2
0x140037c9f  mov     r9d, r12d
0x140037ca2  lea     r8, aU; "%u"
0x140037ca9  mov     edx, 20h ; ' '; unsigned __int64
0x140037cae  lea     rcx, [rbp+0C0h+var_F0]; wchar_t *
0x140037cb2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140037cb7  test    cs:Microsoft_Windows_WER_SystemErrorReportingEnableBits, 2
0x140037cbe  jz      loc_140037D45
0x140037cc4  mov     rcx, [rsp+1C0h+lpFileName]
0x140037cc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x140037ccd  test    rcx, rcx
0x140037cd0  jz      short loc_140037CE8
0x140037cd2  mov     rdx, rax
0x140037cd5  inc     rdx
0x140037cd8  cmp     [rcx+rdx*2], r15w
0x140037cdd  jnz     short loc_140037CD5
0x140037cdf  lea     edx, ds:2[rdx*2]
0x140037ce6  jmp     short loc_140037CF4
0x140037ce8  lea     rcx, aNull_1; "NULL"
0x140037cef  mov     edx, 0Ah
0x140037cf4  mov     [rbp+0C0h+var_60], rcx
0x140037cf8  lea     rcx, [rbp+0C0h+var_F0]
0x140037cfc  mov     [rbp+0C0h+var_58], edx
0x140037cff  mov     [rbp+0C0h+var_54], r15d
0x140037d03  inc     rax
0x140037d06  cmp     [rcx+rax*2], r15w
0x140037d0b  jnz     short loc_140037D03
0x140037d0d  lea     eax, ds:2[rax*2]
0x140037d14  mov     [rbp+0C0h+var_44], r15d
0x140037d18  lea     rcx, [rbp+0C0h+var_F0]
0x140037d1c  mov     [rbp+0C0h+var_48], eax
0x140037d1f  lea     rax, [rbp+0C0h+var_70]
0x140037d23  mov     [rbp+0C0h+var_50], rcx
0x140037d27  mov     r9d, 3
0x140037d2d  mov     [rsp+1C0h+var_1A0], rax
0x140037d32  lea     rdx, EventDeletingDumpFile
0x140037d39  lea     rcx, S_Microsoft_Windows_WER_SystemErrorReporting_Context
0x140037d40  call    McGenEventWrite_EventWriteTransfer
0x140037d45  mov     r8, [rsp+1C0h+lpFileName]; wchar_t *
0x140037d4a  lea     r9, [rbp+0C0h+var_F0]; wchar_t *
0x140037d4e  mov     edx, 4; unsigned __int16
0x140037d53  mov     [rsp+1C0h+var_1A0], r15; wchar_t *
0x140037d58  mov     ecx, 400003FAh; unsigned int
0x140037d5d  call    ?SystemErrorReportingTelemetry@@YAXKGPEB_W00@Z; SystemErrorReportingTelemetry(ulong,ushort,wchar_t const *,wchar_t const *,wchar_t const *)
0x140037d62  mov     ebx, r15d
0x140037d65  jmp     short loc_140037D87
0x140037d67  call    cs:__imp_GetLastError
0x140037d6e  nop     dword ptr [rax+rax+00h]
0x140037d73  mov     ebx, eax
0x140037d75  test    eax, eax
0x140037d77  jle     short loc_140037D87
0x140037d79  movzx   ebx, ax
0x140037d7c  or      ebx, 80070000h
0x140037d82  jmp     short loc_140037D87
0x140037d84  mov     r14d, r12d
0x140037d87  mov     eax, cs:dword_14007E000
0x140037d8d  cmp     eax, 5
0x140037d90  jbe     loc_140037E66
0x140037d96  mov     rcx, cs:qword_14007E018
0x140037d9d  mov     rdx, 400000000000h
0x140037da7  mov     rax, cs:qword_14007E010
0x140037dae  test    rdx, rax
0x140037db1  jz      loc_140037E66
0x140037db7  mov     rax, rcx
0x140037dba  and     rax, rdx
0x140037dbd  cmp     rax, rcx
0x140037dc0  jnz     loc_140037E66
0x140037dc6  cmp     dword ptr [rbp+0C0h+var_128+4], r15d
0x140037dca  lea     rax, [rsp+1C0h+var_180]
0x140037dcf  mov     [rbp+0C0h+var_80], rax
0x140037dd3  lea     rdx, byte_140073303
0x140037dda  mov     ecx, 8
0x140037ddf  mov     [rsp+1C0h+var_180], r14d
0x140037de4  setnz   byte ptr [rsp+1C0h+var_190]
0x140037de9  mov     [rbp+0C0h+var_98], rcx
0x140037ded  lea     rax, [rsp+1C0h+var_188]
0x140037df2  mov     [rbp+0C0h+var_A8], rcx
0x140037df6  mov     [rbp+0C0h+var_90], rax
0x140037dfa  xor     r9d, r9d
0x140037dfd  lea     rax, [rbp+0C0h+var_110]
0x140037e01  mov     [rbp+0C0h+var_C8], rcx
0x140037e05  mov     [rbp+0C0h+var_A0], rax
0x140037e09  xor     r8d, r8d
0x140037e0c  lea     rax, [rbp+0C0h+var_108]
0x140037e10  mov     dword ptr [rsp+1C0h+var_188], ebx
0x140037e14  mov     [rbp+0C0h+var_B0], rax
0x140037e18  lea     rax, [rsp+1C0h+var_190]
0x140037e1d  mov     [rbp+0C0h+var_C0], rax
0x140037e21  lea     rax, [rbp+0C0h+var_100]
0x140037e25  mov     [rbp+0C0h+var_D0], rax
0x140037e29  lea     rax, [rbp+0C0h+var_F0]
0x140037e2d  mov     qword ptr [rsp+1C0h+var_198], rax
0x140037e32  mov     dword ptr [rsp+1C0h+var_1A0], ecx
0x140037e36  lea     rcx, dword_14007E000
0x140037e3d  mov     [rbp+0C0h+var_110], rsi
0x140037e41  mov     [rbp+0C0h+var_108], rdi
0x140037e45  mov     [rbp+0C0h+var_100], 1000000h
0x140037e4d  mov     [rbp+0C0h+var_78], 4
0x140037e55  mov     [rbp+0C0h+var_88], 4
0x140037e5d  mov     [rbp+0C0h+var_B8], r12
0x140037e61  call    _tlgWriteTransfer_EventWriteTransfer
0x140037e66  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x140037e6b  lea     rax, [rbp+0C0h+var_138]
0x140037e6f  cmp     rcx, rax
0x140037e72  jz      short loc_140037E80
0x140037e74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140037e7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140037e80  mov     rcx, [rsp+1C0h+var_168]; void *
0x140037e85  lea     rax, [rsp+1C0h+var_158]
0x140037e8a  cmp     rcx, rax
0x140037e8d  jz      short loc_140037E9B
0x140037e8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140037e96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140037e9b  mov     rcx, [rbp+0C0h+var_40]
0x140037ea2  xor     rcx, rsp; StackCookie
0x140037ea5  call    __security_check_cookie
0x140037eaa  add     rsp, 190h
0x140037eb1  pop     r15
0x140037eb3  pop     r14
0x140037eb5  pop     r12
0x140037eb7  pop     rdi
0x140037eb8  pop     rsi
0x140037eb9  pop     rbx
0x140037eba  pop     rbp
0x140037ebb  retn
```
