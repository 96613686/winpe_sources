# CFileDownload_DMChannel::OpenLogFile(void * &)

- ea: `0x180012840`
- end: `0x1800129db`
- name: `?OpenLogFile@CFileDownload_DMChannel@@IEAAJAEAPEAX@Z`
- size: `411`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001209c`
- `0x180012570`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x1800092f8`
- `0x18000e470`
- `0x18000e744`
- `0x180010a7c`
- `0x1800125e8`
- `0x180012840`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001294c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001294c`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::OpenLogFile(CFileDownload_DMChannel *this, void **a2)
{
  const unsigned __int16 *v3; // rdx
  WCHAR *v5; // rdi
  int v6; // ecx
  int LogFileType; // ebx
  int v8; // r8d
  int v9; // r9d
  const unsigned __int16 *v10; // rdx
  HANDLE FileW; // rax
  const WCHAR *v12; // rax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  WCHAR FileName[1032]; // [rsp+70h] [rbp-90h] BYREF

  *a2 = (void *)-1LL;
  FileName[0] = 0;
  v3 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  LODWORD(v15) = 0;
  v14 = 0;
  v5 = 0;
  LogFileType = CFileDownload_DMChannel::GetLogFileType(this, v3, (enum LogFileType *)&v15);
  if ( LogFileType >= 0 )
  {
    if ( !(_DWORD)v15 )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 3);
      v17 = 0;
      v16 = 0;
      CEtwLogCollector::Open((CEtwLogCollector *)&v16, v10);
      LogFileType = CEtwLogCollector::GetTraceStatus((CEtwLogCollector *)&v16, &v14);
      if ( LogFileType < 0 )
      {
LABEL_4:
        CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v16);
        goto LABEL_14;
      }
      if ( v14 == 1 )
      {
        LogFileType = -2147019873;
        goto LABEL_4;
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v16);
    }
    LogFileType = CLogFileMgr::Initialize(FileName, (unsigned int)v15, *((_QWORD *)this + 3));
    if ( LogFileType >= 0 )
    {
      if ( FileName[0] )
      {
        v5 = FileName;
        LogFileType = 0;
        FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        *a2 = FileW;
        v6 = -2147024894;
        if ( FileW == (HANDLE)-1LL )
          LogFileType = -2147024894;
      }
      else
      {
        LogFileType = -2147467259;
      }
    }
  }
LABEL_14:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v14 = LogFileType;
    v12 = &String2;
    if ( v5 )
      v12 = v5;
    v15 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)&unk_180041AC8,
      v8,
      v9,
      (__int64)&v15,
      (__int64)&v14);
  }
  return (unsigned int)LogFileType;
}

```

## disassembly

```asm
0x180012840  mov     [rsp-8+arg_10], rbx
0x180012845  mov     [rsp-8+arg_18], rdi
0x18001284a  push    rbp
0x18001284b  push    r14
0x18001284d  push    r15
0x18001284f  lea     rbp, [rsp-790h]
0x180012857  sub     rsp, 890h
0x18001285e  mov     rax, cs:__security_cookie
0x180012865  xor     rax, rsp
0x180012868  mov     [rbp+7A0h+var_20], rax
0x18001286f  xor     eax, eax
0x180012871  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180012878  mov     r15, rdx
0x18001287b  mov     [rsp+8A0h+FileName], ax
0x180012880  mov     rdx, [rcx+18h]; unsigned __int16 *
0x180012884  lea     r8, [rsp+8A0h+var_858]; enum LogFileType *
0x180012889  mov     dword ptr [rsp+8A0h+var_858], eax
0x18001288d  mov     r14, rcx
0x180012890  mov     [rsp+8A0h+var_860], eax
0x180012894  xor     edi, edi
0x180012896  call    ?GetLogFileType@CFileDownload_DMChannel@@IEAAJPEBGAEAW4LogFileType@@@Z; CFileDownload_DMChannel::GetLogFileType(ushort const *,LogFileType &)
0x18001289b  mov     ebx, eax
0x18001289d  test    eax, eax
0x18001289f  js      loc_18001296E
0x1800128a5  cmp     dword ptr [rsp+8A0h+var_858], edi
0x1800128a9  jnz     short loc_1800128FE
0x1800128ab  mov     rdx, [r14+18h]; unsigned __int16 *
0x1800128af  lea     rcx, [rsp+8A0h+var_850]; this
0x1800128b4  xorps   xmm0, xmm0
0x1800128b7  mov     [rsp+8A0h+var_840], rdi
0x1800128bc  movdqu  [rsp+8A0h+var_850], xmm0
0x1800128c2  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x1800128c7  lea     rdx, [rsp+8A0h+var_860]; int *
0x1800128cc  lea     rcx, [rsp+8A0h+var_850]; this
0x1800128d1  call    ?GetTraceStatus@CEtwLogCollector@@QEAAJAEAJ@Z; CEtwLogCollector::GetTraceStatus(long &)
0x1800128d6  lea     rcx, [rsp+8A0h+var_850]; this
0x1800128db  mov     ebx, eax
0x1800128dd  test    eax, eax
0x1800128df  jns     short loc_1800128EB
0x1800128e1  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x1800128e6  jmp     loc_18001296E
0x1800128eb  cmp     [rsp+8A0h+var_860], 1
0x1800128f0  jnz     short loc_1800128F9
0x1800128f2  mov     ebx, 8007139Fh
0x1800128f7  jmp     short loc_1800128E1
0x1800128f9  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x1800128fe  mov     r8, [r14+18h]
0x180012902  lea     rcx, [rsp+8A0h+FileName]
0x180012907  mov     edx, dword ptr [rsp+8A0h+var_858]
0x18001290b  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x180012910  mov     ebx, eax
0x180012912  test    eax, eax
0x180012914  js      short loc_18001296E
0x180012916  xor     eax, eax
0x180012918  cmp     ax, [rsp+8A0h+FileName]
0x18001291d  jz      short loc_180012969
0x18001291f  mov     [rsp+8A0h+hTemplateFile], rax; hTemplateFile
0x180012924  lea     r8d, [rax+1]; dwShareMode
0x180012928  mov     [rsp+8A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180012930  lea     rcx, [rsp+8A0h+FileName]; lpFileName
0x180012935  xor     r9d, r9d; lpSecurityAttributes
0x180012938  mov     [rsp+8A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180012940  mov     edx, 80000000h; dwDesiredAccess
0x180012945  lea     rdi, [rsp+8A0h+FileName]
0x18001294a  xor     ebx, ebx
0x18001294c  call    cs:__imp_CreateFileW
0x180012953  nop     dword ptr [rax+rax+00h]
0x180012958  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001295c  mov     [r15], rax
0x18001295f  mov     ecx, 80070002h
0x180012964  cmovz   ebx, ecx
0x180012967  jmp     short loc_18001296E
0x180012969  mov     ebx, 80004005h
0x18001296e  mov     eax, cs:dword_18004AE90
0x180012974  cmp     eax, 5
0x180012977  jbe     short loc_1800129B0
0x180012979  test    rdi, rdi
0x18001297c  mov     [rsp+8A0h+var_860], ebx
0x180012980  lea     rax, String2
0x180012987  cmovnz  rax, rdi
0x18001298b  lea     rdx, unk_180041AC8
0x180012992  mov     [rsp+8A0h+var_858], rax
0x180012997  lea     rax, [rsp+8A0h+var_860]
0x18001299c  mov     qword ptr [rsp+8A0h+dwFlagsAndAttributes], rax
0x1800129a1  lea     rax, [rsp+8A0h+var_858]
0x1800129a6  mov     qword ptr [rsp+8A0h+dwCreationDisposition], rax
0x1800129ab  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800129b0  mov     eax, ebx
0x1800129b2  mov     rcx, [rbp+7A0h+var_20]
0x1800129b9  xor     rcx, rsp; StackCookie
0x1800129bc  call    __security_check_cookie
0x1800129c1  lea     r11, [rsp+8A0h+var_10]
0x1800129c9  mov     rbx, [r11+30h]
0x1800129cd  mov     rdi, [r11+38h]
0x1800129d1  mov     rsp, r11
0x1800129d4  pop     r15
0x1800129d6  pop     r14
0x1800129d8  pop     rbp
0x1800129d9  retn
```
