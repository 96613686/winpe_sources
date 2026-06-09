# SetClientConfig(int,wchar_t * *,sih::XTraceLogger &,sih::ClientConfig *)

- ea: `0x1400057e0`
- end: `0x140005a6c`
- name: `?SetClientConfig@@YAJHPEAPEA_WAEAVXTraceLogger@sih@@PEAUClientConfig@2@@Z`
- size: `652`
- prototype: `__int64 __fastcall(int, wchar_t **, struct sih::XTraceLogger *, struct sih::ClientConfig *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140005a74`

## callees

- `0x140002880`
- `0x1400052ec`
- `0x1400057e0`
- `0x140005eec`
- `0x140005f98`
- `0x140006804`
- `0x1400072b4`
- `0x1400073f0`
- `0x1400154b4`
- `0x14002387c`
- `0x140023b30`
- `0x140045dc0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1400058e4`
- `RPCRT4!UuidFromStringW` at `0x1400058e4`

## string_xrefs

- `0x1400058a9`: `UpdateId`
- `0x1400058bf`: `UpdateId is not provided.`
- `0x1400058f6`: `Convert strUpdate to actionID(GUID).`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
__int64 __fastcall SetClientConfig(int a1, wchar_t **a2, struct sih::XTraceLogger *a3, struct sih::ClientConfig *a4)
{
  int v6; // esi
  const char *v7; // rdx
  unsigned __int16 *v8; // rcx
  RPC_STATUS v9; // eax
  __int64 RebootUxTaskParamsFromRegistry; // rax
  void *v11; // rax
  _QWORD *v12; // rbx
  __int64 v14; // [rsp+20h] [rbp-89h]
  _BYTE v15[32]; // [rsp+48h] [rbp-61h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-41h] BYREF
  UUID Uuid; // [rsp+88h] [rbp-21h] BYREF
  RPC_WSTR StringUuid[4]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v19[32]; // [rsp+B8h] [rbp+Fh] BYREF

  v6 = ParseCmdLineArgs(a1, a2, a4);
  if ( v6 >= 0 )
  {
    if ( *(_DWORD *)a4 == 3 || ((*(_DWORD *)a4 - 2) & 0xFFFFFFFD) == 0 )
    {
      WUTrace(0, 0, 0x400000, 4, 0, L"IsSIHManagedRebootUXMode (%d)");
      Uuid = 0;
      sih::utils::GetRebootUxTaskParamsFromRegistry(StringUuid, L"UpdateId");
      if ( StringUuid[2] )
      {
        v8 = (unsigned __int16 *)StringUuid;
        if ( StringUuid[3] > (RPC_WSTR)7 )
          v8 = StringUuid[0];
        v9 = UuidFromStringW(v8, &Uuid);
        if ( v9 )
        {
          LODWORD(v14) = v9 | 0x80010000;
          WUTrace(0, 0, 0x400000, 1, v14, L"Convert strUpdate to actionID(GUID).");
        }
        else
        {
          *(UUID *)((char *)a4 + 40) = Uuid;
        }
      }
      else
      {
        WUTrace(0, 0, 0x400000, 1, 0, L"UpdateId is not provided.");
      }
      RebootUxTaskParamsFromRegistry = sih::utils::GetRebootUxTaskParamsFromRegistry(v19, L"Misc");
      std::wstring::operator=((char *)a4 + 56, RebootUxTaskParamsFromRegistry);
      std::wstring::~wstring(v19);
      if ( !*((_QWORD *)a4 + 9) )
        WUTrace(0, 0, 0x400000, 4, 0, L"strMisc is not provided");
      sih::utils::GetRebootUxTaskParamsFromRegistry(v19, L"CV");
      v11 = (void *)std::wstring::wstring(v15, v19);
      sih::utils::VerifyCV(Src, v11);
      v12 = (_QWORD *)((char *)a4 + 8);
      v12[2] = 0;
      if ( v12[3] > 0xFu )
        v12 = (_QWORD *)*v12;
      *(_BYTE *)v12 = 0;
      v6 = -2147024809;
      std::string::~string(Src);
      std::wstring::~wstring(v19);
      std::wstring::~wstring(StringUuid);
    }
    else if ( *((_QWORD *)a4 + 3) )
    {
      v7 = (char *)a4 + 8;
      if ( *((_QWORD *)a4 + 4) > 0xFu )
        v7 = *(const char **)v7;
      sih::XTraceLogger::SetCV(a3, v7);
    }
    else
    {
      WUTrace(0, 0, 0x400000, 4, 0, L"cV is not provided.");
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400057e0  push    rbp
0x1400057e2  push    rbx
0x1400057e3  push    rsi
0x1400057e4  push    r12
0x1400057e6  push    r15
0x1400057e8  lea     rbp, [rsp-37h]
0x1400057ed  sub     rsp, 0E0h
0x1400057f4  mov     rax, cs:__security_cookie
0x1400057fb  xor     rax, rsp
0x1400057fe  mov     [rbp+57h+var_28], rax
0x140005802  mov     rbx, r9
0x140005805  mov     r15, r8
0x140005808  mov     r8, r9; struct sih::ClientConfig *
0x14000580b  call    ?ParseCmdLineArgs@@YAJHPEAPEA_WPEAUClientConfig@sih@@@Z; ParseCmdLineArgs(int,wchar_t * *,sih::ClientConfig *)
0x140005810  mov     esi, eax
0x140005812  xor     r12d, r12d
0x140005815  test    eax, eax
0x140005817  js      loc_140005A4F
0x14000581d  mov     edx, [rbx]
0x14000581f  cmp     edx, 3
0x140005822  jz      short loc_14000587A
0x140005824  lea     ecx, [rdx-2]
0x140005827  test    ecx, 0FFFFFFFDh
0x14000582d  jz      short loc_14000587A
0x14000582f  cmp     [rbx+18h], r12
0x140005833  jnz     short loc_14000585F
0x140005835  lea     rax, aCvIsNotProvide; "cV is not provided."
0x14000583c  mov     [rsp+100h+var_D8], rax
0x140005841  mov     [rsp+100h+var_E0], r12
0x140005846  xor     edx, edx
0x140005848  xor     ecx, ecx
0x14000584a  lea     r9d, [r12+4]
0x14000584f  mov     r8d, 400000h
0x140005855  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000585a  jmp     loc_140005A4F
0x14000585f  lea     rdx, [rbx+8]
0x140005863  cmp     qword ptr [rdx+18h], 0Fh
0x140005868  jbe     short loc_14000586D
0x14000586a  mov     rdx, [rdx]; char *
0x14000586d  mov     rcx, r15; this
0x140005870  call    ?SetCV@XTraceLogger@sih@@QEAAJPEBD@Z; sih::XTraceLogger::SetCV(char const *)
0x140005875  jmp     loc_140005A4F
0x14000587a  mov     dword ptr [rsp+100h+var_D0], edx
0x14000587e  lea     rax, aIssihmanagedre; "IsSIHManagedRebootUXMode (%d)"
0x140005885  mov     [rsp+100h+var_D8], rax
0x14000588a  mov     [rsp+100h+var_E0], r12
0x14000588f  xor     edx, edx
0x140005891  xor     ecx, ecx
0x140005893  lea     r9d, [rdx+4]
0x140005897  mov     r8d, 400000h
0x14000589d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400058a2  xorps   xmm0, xmm0
0x1400058a5  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1400058a9  lea     rdx, aUpdateid; "UpdateId"
0x1400058b0  lea     rcx, [rbp+57h+StringUuid]
0x1400058b4  call    ?GetRebootUxTaskParamsFromRegistry@utils@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; sih::utils::GetRebootUxTaskParamsFromRegistry(wchar_t const *)
0x1400058b9  cmp     [rbp+57h+var_58], r12
0x1400058bd  jnz     short loc_1400058D2
0x1400058bf  lea     rax, aUpdateidIsNotP; "UpdateId is not provided."
0x1400058c6  mov     [rsp+100h+var_D8], rax
0x1400058cb  mov     [rsp+100h+var_E0], r12
0x1400058d0  jmp     short loc_140005906
0x1400058d2  lea     rcx, [rbp+57h+StringUuid]
0x1400058d6  cmp     [rbp+57h+var_50], 7
0x1400058db  cmova   rcx, [rbp+57h+StringUuid]; StringUuid
0x1400058e0  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1400058e4  call    cs:__imp_UuidFromStringW
0x1400058ea  test    eax, eax
0x1400058ec  jz      short loc_14000591B
0x1400058ee  mov     esi, eax
0x1400058f0  or      esi, 80010000h
0x1400058f6  lea     rax, aConvertStrupda; "Convert strUpdate to actionID(GUID)."
0x1400058fd  mov     [rsp+100h+var_D8], rax
0x140005902  mov     dword ptr [rsp+100h+var_E0], esi
0x140005906  xor     edx, edx
0x140005908  xor     ecx, ecx
0x14000590a  lea     r9d, [rdx+1]
0x14000590e  mov     r8d, 400000h
0x140005914  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005919  jmp     short loc_140005924
0x14000591b  movups  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x14000591f  movdqu  xmmword ptr [rbx+28h], xmm0
0x140005924  lea     rdx, aMisc; "Misc"
0x14000592b  lea     rcx, [rbp+57h+var_48]
0x14000592f  call    ?GetRebootUxTaskParamsFromRegistry@utils@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; sih::utils::GetRebootUxTaskParamsFromRegistry(wchar_t const *)
0x140005934  mov     rdx, rax
0x140005937  lea     rcx, [rbx+38h]
0x14000593b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140005940  lea     rcx, [rbp+57h+var_48]; void *
0x140005944  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005949  cmp     [rbx+48h], r12
0x14000594d  jnz     short loc_140005973
0x14000594f  lea     rax, aStrmiscIsNotPr; "strMisc is not provided"
0x140005956  mov     [rsp+100h+var_D8], rax
0x14000595b  mov     [rsp+100h+var_E0], r12
0x140005960  xor     edx, edx
0x140005962  xor     ecx, ecx
0x140005964  lea     r9d, [rdx+4]
0x140005968  mov     r8d, 400000h
0x14000596e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005973  mov     [rbp+57h+var_C0], r12b
0x140005977  lea     rdx, aCv_0; "CV"
0x14000597e  lea     rcx, [rbp+57h+var_48]
0x140005982  call    ?GetRebootUxTaskParamsFromRegistry@utils@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; sih::utils::GetRebootUxTaskParamsFromRegistry(wchar_t const *)
0x140005987  lea     rdx, [rbp+57h+var_48]
0x14000598b  lea     rcx, [rbp+57h+var_B8]
0x14000598f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140005994  mov     rdx, rax; void *
0x140005997  lea     r8, [rbp+57h+var_C0]
0x14000599b  lea     rcx, [rbp+57h+Src]; Src
0x14000599f  call    ?VerifyCV@utils@sih@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEA_N@Z; sih::utils::VerifyCV(std::wstring,bool *)
0x1400059a4  add     rbx, 8
0x1400059a8  cmp     [rbp+57h+var_C0], r12b
0x1400059ac  jz      short loc_140005A1E
0x1400059ae  lea     rax, [rbp+57h+Src]
0x1400059b2  cmp     rbx, rax
0x1400059b5  jz      short loc_1400059D1
0x1400059b7  lea     rdx, [rbp+57h+Src]
0x1400059bb  cmp     [rbp+57h+var_80], 0Fh
0x1400059c0  cmova   rdx, [rbp+57h+Src]; Src
0x1400059c5  mov     r8, [rbp+57h+Size]; Size
0x1400059c9  mov     rcx, rbx; void *
0x1400059cc  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1400059d1  mov     rax, rbx
0x1400059d4  cmp     qword ptr [rbx+18h], 0Fh
0x1400059d9  jbe     short loc_1400059DE
0x1400059db  mov     rax, [rbx]
0x1400059de  mov     [rsp+100h+var_D0], rax
0x1400059e3  lea     rax, aCvHs; "cV = %hs "
0x1400059ea  mov     [rsp+100h+var_D8], rax
0x1400059ef  mov     [rsp+100h+var_E0], r12
0x1400059f4  xor     edx, edx
0x1400059f6  xor     ecx, ecx
0x1400059f8  lea     r9d, [rdx+4]
0x1400059fc  mov     r8d, 400000h
0x140005a02  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005a07  cmp     qword ptr [rbx+18h], 0Fh
0x140005a0c  jbe     short loc_140005A11
0x140005a0e  mov     rbx, [rbx]
0x140005a11  mov     rdx, rbx; char *
0x140005a14  mov     rcx, r15; this
0x140005a17  call    ?SetCV@XTraceLogger@sih@@QEAAJPEBD@Z; sih::XTraceLogger::SetCV(char const *)
0x140005a1c  jmp     short loc_140005A34
0x140005a1e  mov     [rbx+10h], r12
0x140005a22  cmp     qword ptr [rbx+18h], 0Fh
0x140005a27  jbe     short loc_140005A2C
0x140005a29  mov     rbx, [rbx]
0x140005a2c  mov     [rbx], r12b
0x140005a2f  mov     esi, 80070057h
0x140005a34  lea     rcx, [rbp+57h+Src]
0x140005a38  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140005a3d  lea     rcx, [rbp+57h+var_48]; void *
0x140005a41  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005a46  lea     rcx, [rbp+57h+StringUuid]; void *
0x140005a4a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005a4f  mov     eax, esi
0x140005a51  mov     rcx, [rbp+57h+var_28]
0x140005a55  xor     rcx, rsp; StackCookie
0x140005a58  call    __security_check_cookie
0x140005a5d  add     rsp, 0E0h
0x140005a64  pop     r15
0x140005a66  pop     r12
0x140005a68  pop     rsi
0x140005a69  pop     rbx
0x140005a6a  pop     rbp
0x140005a6b  retn
```
