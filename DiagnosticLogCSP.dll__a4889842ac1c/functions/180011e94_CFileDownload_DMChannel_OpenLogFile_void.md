# CFileDownload_DMChannel::OpenLogFile(void * &)

- ea: `0x180011e94`
- end: `0x180012025`
- name: `?OpenLogFile@CFileDownload_DMChannel@@IEAAJAEAPEAX@Z`
- size: `401`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180011760`
- `0x180011be8`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x1800090b4`
- `0x18000dd98`
- `0x18000e054`
- `0x180010230`
- `0x180011c54`
- `0x180011e94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011f9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011f9d`

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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v14 = LogFileType;
    v12 = &String2;
    if ( v5 )
      v12 = v5;
    v15 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)&unk_18003FAC8,
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
0x180011e94  mov     [rsp-8+arg_10], rbx
0x180011e99  mov     [rsp-8+arg_18], rdi
0x180011e9e  push    rbp
0x180011e9f  push    r14
0x180011ea1  push    r15
0x180011ea3  lea     rbp, [rsp-790h]
0x180011eab  sub     rsp, 890h
0x180011eb2  mov     rax, cs:__security_cookie
0x180011eb9  xor     rax, rsp
0x180011ebc  mov     [rbp+7A0h+var_20], rax
0x180011ec3  xor     eax, eax
0x180011ec5  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180011ecc  mov     r15, rdx
0x180011ecf  mov     [rsp+8A0h+FileName], ax
0x180011ed4  mov     rdx, [rcx+18h]; unsigned __int16 *
0x180011ed8  lea     r8, [rsp+8A0h+var_858]; enum LogFileType *
0x180011edd  mov     dword ptr [rsp+8A0h+var_858], eax
0x180011ee1  mov     r14, rcx
0x180011ee4  mov     [rsp+8A0h+var_860], eax
0x180011ee8  xor     edi, edi
0x180011eea  call    ?GetLogFileType@CFileDownload_DMChannel@@IEAAJPEBGAEAW4LogFileType@@@Z; CFileDownload_DMChannel::GetLogFileType(ushort const *,LogFileType &)
0x180011eef  mov     ebx, eax
0x180011ef1  test    eax, eax
0x180011ef3  js      loc_180011FB9
0x180011ef9  cmp     dword ptr [rsp+8A0h+var_858], edi
0x180011efd  jnz     short loc_180011F4F
0x180011eff  mov     rdx, [r14+18h]; unsigned __int16 *
0x180011f03  lea     rcx, [rsp+8A0h+var_850]; this
0x180011f08  xorps   xmm0, xmm0
0x180011f0b  mov     [rsp+8A0h+var_840], rdi
0x180011f10  movdqu  [rsp+8A0h+var_850], xmm0
0x180011f16  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180011f1b  lea     rdx, [rsp+8A0h+var_860]; int *
0x180011f20  lea     rcx, [rsp+8A0h+var_850]; this
0x180011f25  call    ?GetTraceStatus@CEtwLogCollector@@QEAAJAEAJ@Z; CEtwLogCollector::GetTraceStatus(long &)
0x180011f2a  lea     rcx, [rsp+8A0h+var_850]; this
0x180011f2f  mov     ebx, eax
0x180011f31  test    eax, eax
0x180011f33  jns     short loc_180011F3C
0x180011f35  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180011f3a  jmp     short loc_180011FB9
0x180011f3c  cmp     [rsp+8A0h+var_860], 1
0x180011f41  jnz     short loc_180011F4A
0x180011f43  mov     ebx, 8007139Fh
0x180011f48  jmp     short loc_180011F35
0x180011f4a  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180011f4f  mov     r8, [r14+18h]
0x180011f53  lea     rcx, [rsp+8A0h+FileName]
0x180011f58  mov     edx, dword ptr [rsp+8A0h+var_858]
0x180011f5c  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x180011f61  mov     ebx, eax
0x180011f63  test    eax, eax
0x180011f65  js      short loc_180011FB9
0x180011f67  xor     eax, eax
0x180011f69  cmp     ax, [rsp+8A0h+FileName]
0x180011f6e  jz      short loc_180011FB4
0x180011f70  mov     [rsp+8A0h+hTemplateFile], rax; hTemplateFile
0x180011f75  lea     r8d, [rax+1]; dwShareMode
0x180011f79  mov     [rsp+8A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180011f81  lea     rcx, [rsp+8A0h+FileName]; lpFileName
0x180011f86  xor     r9d, r9d; lpSecurityAttributes
0x180011f89  mov     [rsp+8A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180011f91  mov     edx, 80000000h; dwDesiredAccess
0x180011f96  lea     rdi, [rsp+8A0h+FileName]
0x180011f9b  xor     ebx, ebx
0x180011f9d  call    cs:__imp_CreateFileW
0x180011fa3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011fa7  mov     [r15], rax
0x180011faa  mov     ecx, 80070002h
0x180011faf  cmovz   ebx, ecx
0x180011fb2  jmp     short loc_180011FB9
0x180011fb4  mov     ebx, 80004005h
0x180011fb9  mov     eax, cs:dword_180048E90
0x180011fbf  cmp     eax, 5
0x180011fc2  jbe     short loc_180011FFB
0x180011fc4  test    rdi, rdi
0x180011fc7  mov     [rsp+8A0h+var_860], ebx
0x180011fcb  lea     rax, String2
0x180011fd2  cmovnz  rax, rdi
0x180011fd6  lea     rdx, unk_18003FAC8
0x180011fdd  mov     [rsp+8A0h+var_858], rax
0x180011fe2  lea     rax, [rsp+8A0h+var_860]
0x180011fe7  mov     qword ptr [rsp+8A0h+dwFlagsAndAttributes], rax
0x180011fec  lea     rax, [rsp+8A0h+var_858]
0x180011ff1  mov     qword ptr [rsp+8A0h+dwCreationDisposition], rax
0x180011ff6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180011ffb  mov     eax, ebx
0x180011ffd  mov     rcx, [rbp+7A0h+var_20]
0x180012004  xor     rcx, rsp; StackCookie
0x180012007  call    __security_check_cookie
0x18001200c  lea     r11, [rsp+8A0h+var_10]
0x180012014  mov     rbx, [r11+30h]
0x180012018  mov     rdi, [r11+38h]
0x18001201c  mov     rsp, r11
0x18001201f  pop     r15
0x180012021  pop     r14
0x180012023  pop     rbp
0x180012024  retn
```
