# CPubCacheBackingStore::DeleteHashFile(ushort const *,bool *,bool *)

- ea: `0x180057548`
- end: `0x1800576a5`
- name: `?DeleteHashFile@CPubCacheBackingStore@@QEAAKPEBGPEA_N1@Z`
- size: `349`
- prototype: `unsigned int(CPubCacheBackingStore *__hidden this, const unsigned __int16 *, bool *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008c6d0`

## callees

- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x180057548`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005761e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005761e`
- `KERNEL32!CloseHandle` at `0x18005766f`
- `KERNEL32!CloseHandle` at `0x18005766f`
- `KERNEL32!CreateFileW` at `0x1800575b8`
- `KERNEL32!CreateFileW` at `0x1800575b8`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180057614`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180057614`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::DeleteHashFile(
        CPubCacheBackingStore *this,
        const unsigned __int16 *a2,
        bool *a3,
        bool *a4)
{
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  DWORD v9; // ebx
  _BYTE v11[24]; // [rsp+40h] [rbp-78h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp-60h] BYREF

  InCritSec::InCritSec((InCritSec *)v11, (CPubCacheBackingStore *)((char *)this + 40), 1);
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x4000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 5 )
    {
      *a3 = 1;
    }
    else if ( LastError != 2 )
    {
      goto LABEL_17;
    }
    v9 = 0;
  }
  else
  {
    v9 = 0;
    if ( a4 )
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        *a4 = FileInformation.nNumberOfLinks <= 1;
      }
      else
      {
        v9 = GetLastError();
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 182, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v9);
        }
      }
    }
    CloseHandle(FileW);
  }
LABEL_17:
  InCritSec::~InCritSec((InCritSec *)v11);
  return v9;
}

```

## disassembly

```asm
0x180057548  mov     [rsp+arg_0], rbx
0x18005754d  push    rsi
0x18005754e  push    rdi
0x18005754f  push    r14
0x180057551  sub     rsp, 0A0h
0x180057558  mov     rax, cs:__security_cookie
0x18005755f  xor     rax, rsp
0x180057562  mov     [rsp+0B8h+var_28], rax
0x18005756a  mov     rbx, rdx
0x18005756d  mov     r14, r8
0x180057570  lea     rdx, [rcx+28h]; struct CritSec *
0x180057574  mov     r8b, 1; bool
0x180057577  lea     rcx, [rsp+0B8h+var_78]; this
0x18005757c  mov     rdi, r9
0x18005757f  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180057584  mov     byte ptr [r14], 0
0x180057588  test    rdi, rdi
0x18005758b  jz      short loc_180057590
0x18005758d  mov     byte ptr [rdi], 0
0x180057590  xor     r9d, r9d; lpSecurityAttributes
0x180057593  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x18005759c  mov     [rsp+0B8h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x1800575a4  mov     edx, 80000000h; dwDesiredAccess
0x1800575a9  mov     rcx, rbx; lpFileName
0x1800575ac  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800575b4  lea     r8d, [r9+7]; dwShareMode
0x1800575b8  call    cs:__imp_CreateFileW
0x1800575be  mov     rsi, rax
0x1800575c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800575c5  jnz     short loc_1800575EA
0x1800575c7  call    cs:__imp_GetLastError
0x1800575cd  mov     ebx, eax
0x1800575cf  cmp     eax, 5
0x1800575d2  jnz     short loc_1800575DF
0x1800575d4  mov     byte ptr [r14], 1
0x1800575d8  xor     ebx, ebx
0x1800575da  jmp     loc_180057675
0x1800575df  cmp     eax, 2
0x1800575e2  jnz     loc_180057675
0x1800575e8  jmp     short loc_1800575D8
0x1800575ea  xor     ebx, ebx
0x1800575ec  test    rdi, rdi
0x1800575ef  jz      short loc_18005766C
0x1800575f1  xorps   xmm0, xmm0
0x1800575f4  lea     rdx, [rsp+0B8h+FileInformation]; lpFileInformation
0x1800575f9  xor     eax, eax
0x1800575fb  mov     rcx, rsi; hFile
0x1800575fe  movups  xmmword ptr [rsp+0B8h+FileInformation.dwFileAttributes], xmm0
0x180057603  mov     [rsp+0B8h+FileInformation.nFileIndexLow], eax
0x18005760a  movups  xmmword ptr [rsp+0B8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18005760f  movups  xmmword ptr [rsp+0B8h+FileInformation.nFileSizeHigh], xmm0
0x180057614  call    cs:__imp_GetFileInformationByHandle
0x18005761a  test    eax, eax
0x18005761c  jnz     short loc_18005765F
0x18005761e  call    cs:__imp_GetLastError
0x180057624  mov     ebx, eax
0x180057626  mov     rcx, cs:WPP_GLOBAL_Control
0x18005762d  lea     rax, WPP_GLOBAL_Control
0x180057634  cmp     rcx, rax
0x180057637  jz      short loc_18005766C
0x180057639  test    byte ptr [rcx+6Ch], 4
0x18005763d  jz      short loc_18005766C
0x18005763f  cmp     byte ptr [rcx+69h], 1
0x180057643  jb      short loc_18005766C
0x180057645  mov     rcx, [rcx+60h]
0x180057649  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057650  mov     edx, 0B6h
0x180057655  mov     r9d, ebx
0x180057658  call    WPP_SF_d
0x18005765d  jmp     short loc_18005766C
0x18005765f  cmp     [rsp+0B8h+FileInformation.nNumberOfLinks], 1
0x180057667  setbe   al
0x18005766a  mov     [rdi], al
0x18005766c  mov     rcx, rsi; hObject
0x18005766f  call    cs:__imp_CloseHandle
0x180057675  lea     rcx, [rsp+0B8h+var_78]; this
0x18005767a  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18005767f  mov     eax, ebx
0x180057681  mov     rcx, [rsp+0B8h+var_28]
0x180057689  xor     rcx, rsp; StackCookie
0x18005768c  call    __security_check_cookie
0x180057691  mov     rbx, [rsp+0B8h+arg_0]
0x180057699  add     rsp, 0A0h
0x1800576a0  pop     r14
0x1800576a2  pop     rdi
0x1800576a3  pop     rsi
0x1800576a4  retn
```
