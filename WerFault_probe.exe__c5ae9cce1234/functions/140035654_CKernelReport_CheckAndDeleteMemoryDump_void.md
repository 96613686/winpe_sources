# CKernelReport::CheckAndDeleteMemoryDump(void)

- ea: `0x140035654`
- end: `0x1400359a4`
- name: `?CheckAndDeleteMemoryDump@CKernelReport@@AEAAXXZ`
- size: `848`
- prototype: `void __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140039614`

## callees

- `0x14000113c`
- `0x140002470`
- `0x140002728`
- `0x14000b540`
- `0x140034d9c`
- `0x140035654`
- `0x14003b970`
- `0x140043d54`
- `0x1400442d4`
- `0x140044484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035855`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140035769`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140035769`

## string_xrefs

- `0x1400356f0`: `CKernelReport::CheckAndDeleteMemoryDump`

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
              &S_Microsoft_Windows_WER_SystemErrorReporting_Context,
              &EventDeletingDumpFile,
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
    if ( (unsigned int)dword_14007A000 > 5
      && (qword_14007A010 & 0x400000000000LL) != 0
      && (qword_14007A018 & 0x400000000000LL) == qword_14007A018 )
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
      v28 = v1;
      v29 = v5;
      v30 = 0x1000000;
      v43 = 4;
      v41 = 4;
      v35 = 1;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &unk_14006F36B, 0, 0, 8, v31);
    }
  }
  else
  {
    LODWORD(v15) = Settings;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xB56,
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
0x140035654  push    rbp
0x140035656  push    rbx
0x140035657  push    rsi
0x140035658  push    rdi
0x140035659  push    r12
0x14003565b  push    r14
0x14003565d  push    r15
0x14003565f  lea     rbp, [rsp-90h]
0x140035667  sub     rsp, 190h
0x14003566e  mov     rax, cs:__security_cookie
0x140035675  xor     rax, rsp
0x140035678  mov     [rbp+0C0h+var_40], rax
0x14003567f  xor     r15d, r15d
0x140035682  mov     [rbp+0C0h+var_128], 5
0x14003568a  lea     rax, [rsp+1C0h+var_158]
0x14003568f  mov     [rsp+1C0h+var_158], r15w
0x140035695  mov     [rsp+1C0h+var_168], rax
0x14003569a  lea     rcx, [rsp+1C0h+var_170]; this
0x14003569f  lea     rax, [rsp+1C0h+var_158]
0x1400356a4  mov     [rbp+0C0h+var_138], r15w
0x1400356a9  mov     [rsp+1C0h+var_160], rax
0x1400356ae  lea     r12d, [r15+1]
0x1400356b2  lea     rax, [rbp+0C0h+var_138]
0x1400356b6  mov     [rsp+1C0h+var_170], r12
0x1400356bb  mov     [rsp+1C0h+lpFileName], rax
0x1400356c0  mov     esi, r15d
0x1400356c3  lea     rax, [rbp+0C0h+var_138]
0x1400356c7  mov     [rbp+0C0h+var_120], r15d
0x1400356cb  mov     [rbp+0C0h+var_140], rax
0x1400356cf  mov     [rsp+1C0h+var_188], r15
0x1400356d4  call    ?LoadSettings@CCrashControlSettings@@QEAAJXZ; CCrashControlSettings::LoadSettings(void)
0x1400356d9  test    eax, eax
0x1400356db  jns     short loc_140035711
0x1400356dd  mov     rcx, [rbp+0C8h]; this
0x1400356e4  lea     rdx, aFailedToLoadSe; "Failed to load settings"
0x1400356eb  mov     qword ptr [rsp+1C0h+var_198], rdx; int
0x1400356f0  lea     r9, aCkernelreportC; "CKernelReport::CheckAndDeleteMemoryDump"
0x1400356f7  mov     edx, 0B56h; void *
0x1400356fc  mov     dword ptr [rsp+1C0h+var_1A0], eax; wil::details *
0x140035700  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035707  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003570c  jmp     loc_14003594E
0x140035711  mov     rcx, [rsp+1C0h+lpFileName]; Src
0x140035716  mov     ebx, r12d
0x140035719  mov     edi, [rbp+0C0h+var_120]
0x14003571c  test    rcx, rcx
0x14003571f  jz      loc_14003586C
0x140035725  cmp     [rcx], r15w
0x140035729  jz      loc_14003586C
0x14003572f  cmp     dword ptr [rbp+0C0h+var_128+4], r15d
0x140035733  jnz     loc_14003586C
0x140035739  test    edi, edi
0x14003573b  jz      loc_14003586C
0x140035741  lea     rdx, [rsp+1C0h+var_188]; unsigned __int64 *
0x140035746  call    ?QueryVolumeFreeSpace@@YAJPEB_WPEA_K1@Z; QueryVolumeFreeSpace(wchar_t const *,unsigned __int64 *,unsigned __int64 *)
0x14003574b  mov     rsi, [rsp+1C0h+var_188]
0x140035750  mov     r14d, eax
0x140035753  test    eax, eax
0x140035755  js      loc_14003586F
0x14003575b  cmp     rsi, rdi
0x14003575e  jnb     loc_14003586F
0x140035764  mov     rcx, [rsp+1C0h+lpFileName]; lpFileName
0x140035769  call    cs:__imp_DeleteFileW
0x14003576f  test    eax, eax
0x140035771  jz      loc_140035855
0x140035777  mov     [rbp+0C0h+var_F0], r15w
0x14003577c  cmp     edi, 400h
0x140035782  jbe     short loc_14003578D
0x140035784  mov     r9d, edi
0x140035787  shr     r9d, 0Ah
0x14003578b  jmp     short loc_140035790
0x14003578d  mov     r9d, r12d
0x140035790  lea     r8, aU; "%u"
0x140035797  mov     edx, 20h ; ' '; unsigned __int64
0x14003579c  lea     rcx, [rbp+0C0h+var_F0]; wchar_t *
0x1400357a0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400357a5  test    cs:Microsoft_Windows_WER_SystemErrorReportingEnableBits, 2
0x1400357ac  jz      loc_140035833
0x1400357b2  mov     rcx, [rsp+1C0h+lpFileName]
0x1400357b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400357bb  test    rcx, rcx
0x1400357be  jz      short loc_1400357D6
0x1400357c0  mov     rdx, rax
0x1400357c3  inc     rdx
0x1400357c6  cmp     [rcx+rdx*2], r15w
0x1400357cb  jnz     short loc_1400357C3
0x1400357cd  lea     edx, ds:2[rdx*2]
0x1400357d4  jmp     short loc_1400357E2
0x1400357d6  lea     rcx, aNull_1; "NULL"
0x1400357dd  mov     edx, 0Ah
0x1400357e2  mov     [rbp+0C0h+var_60], rcx
0x1400357e6  lea     rcx, [rbp+0C0h+var_F0]
0x1400357ea  mov     [rbp+0C0h+var_58], edx
0x1400357ed  mov     [rbp+0C0h+var_54], r15d
0x1400357f1  inc     rax
0x1400357f4  cmp     [rcx+rax*2], r15w
0x1400357f9  jnz     short loc_1400357F1
0x1400357fb  lea     eax, ds:2[rax*2]
0x140035802  mov     [rbp+0C0h+var_44], r15d
0x140035806  lea     rcx, [rbp+0C0h+var_F0]
0x14003580a  mov     [rbp+0C0h+var_48], eax
0x14003580d  lea     rax, [rbp+0C0h+var_70]
0x140035811  mov     [rbp+0C0h+var_50], rcx
0x140035815  mov     r9d, 3
0x14003581b  mov     [rsp+1C0h+var_1A0], rax
0x140035820  lea     rdx, EventDeletingDumpFile
0x140035827  lea     rcx, S_Microsoft_Windows_WER_SystemErrorReporting_Context
0x14003582e  call    McGenEventWrite_EventWriteTransfer
0x140035833  mov     r8, [rsp+1C0h+lpFileName]; wchar_t *
0x140035838  lea     r9, [rbp+0C0h+var_F0]; wchar_t *
0x14003583c  mov     edx, 4; unsigned __int16
0x140035841  mov     [rsp+1C0h+var_1A0], r15; wchar_t *
0x140035846  mov     ecx, 400003FAh; unsigned int
0x14003584b  call    ?SystemErrorReportingTelemetry@@YAXKGPEB_W00@Z; SystemErrorReportingTelemetry(ulong,ushort,wchar_t const *,wchar_t const *,wchar_t const *)
0x140035850  mov     ebx, r15d
0x140035853  jmp     short loc_14003586F
0x140035855  call    cs:__imp_GetLastError
0x14003585b  mov     ebx, eax
0x14003585d  test    eax, eax
0x14003585f  jle     short loc_14003586F
0x140035861  movzx   ebx, ax
0x140035864  or      ebx, 80070000h
0x14003586a  jmp     short loc_14003586F
0x14003586c  mov     r14d, r12d
0x14003586f  mov     eax, cs:dword_14007A000
0x140035875  cmp     eax, 5
0x140035878  jbe     loc_14003594E
0x14003587e  mov     rcx, cs:qword_14007A018
0x140035885  mov     rdx, 400000000000h
0x14003588f  mov     rax, cs:qword_14007A010
0x140035896  test    rdx, rax
0x140035899  jz      loc_14003594E
0x14003589f  mov     rax, rcx
0x1400358a2  and     rax, rdx
0x1400358a5  cmp     rax, rcx
0x1400358a8  jnz     loc_14003594E
0x1400358ae  cmp     dword ptr [rbp+0C0h+var_128+4], r15d
0x1400358b2  lea     rax, [rsp+1C0h+var_180]
0x1400358b7  mov     [rbp+0C0h+var_80], rax
0x1400358bb  lea     rdx, unk_14006F36B
0x1400358c2  mov     ecx, 8
0x1400358c7  mov     [rsp+1C0h+var_180], r14d
0x1400358cc  setnz   byte ptr [rsp+1C0h+var_190]
0x1400358d1  mov     [rbp+0C0h+var_98], rcx
0x1400358d5  lea     rax, [rsp+1C0h+var_188]
0x1400358da  mov     [rbp+0C0h+var_A8], rcx
0x1400358de  mov     [rbp+0C0h+var_90], rax
0x1400358e2  xor     r9d, r9d
0x1400358e5  lea     rax, [rbp+0C0h+var_110]
0x1400358e9  mov     [rbp+0C0h+var_C8], rcx
0x1400358ed  mov     [rbp+0C0h+var_A0], rax
0x1400358f1  xor     r8d, r8d
0x1400358f4  lea     rax, [rbp+0C0h+var_108]
0x1400358f8  mov     dword ptr [rsp+1C0h+var_188], ebx
0x1400358fc  mov     [rbp+0C0h+var_B0], rax
0x140035900  lea     rax, [rsp+1C0h+var_190]
0x140035905  mov     [rbp+0C0h+var_C0], rax
0x140035909  lea     rax, [rbp+0C0h+var_100]
0x14003590d  mov     [rbp+0C0h+var_D0], rax
0x140035911  lea     rax, [rbp+0C0h+var_F0]
0x140035915  mov     qword ptr [rsp+1C0h+var_198], rax
0x14003591a  mov     dword ptr [rsp+1C0h+var_1A0], ecx
0x14003591e  lea     rcx, dword_14007A000
0x140035925  mov     [rbp+0C0h+var_110], rsi
0x140035929  mov     [rbp+0C0h+var_108], rdi
0x14003592d  mov     [rbp+0C0h+var_100], 1000000h
0x140035935  mov     [rbp+0C0h+var_78], 4
0x14003593d  mov     [rbp+0C0h+var_88], 4
0x140035945  mov     [rbp+0C0h+var_B8], r12
0x140035949  call    _tlgWriteTransfer_EventWriteTransfer
0x14003594e  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x140035953  lea     rax, [rbp+0C0h+var_138]
0x140035957  cmp     rcx, rax
0x14003595a  jz      short loc_140035968
0x14003595c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035963  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140035968  mov     rcx, [rsp+1C0h+var_168]; void *
0x14003596d  lea     rax, [rsp+1C0h+var_158]
0x140035972  cmp     rcx, rax
0x140035975  jz      short loc_140035983
0x140035977  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003597e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140035983  mov     rcx, [rbp+0C0h+var_40]
0x14003598a  xor     rcx, rsp; StackCookie
0x14003598d  call    __security_check_cookie
0x140035992  add     rsp, 190h
0x140035999  pop     r15
0x14003599b  pop     r14
0x14003599d  pop     r12
0x14003599f  pop     rdi
0x1400359a0  pop     rsi
0x1400359a1  pop     rbx
0x1400359a2  pop     rbp
0x1400359a3  retn
```
