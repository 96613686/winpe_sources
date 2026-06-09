# Common::Deployment::MountedFolder::Remove(ushort const *,ushort const *)

- ea: `0x180081484`
- end: `0x18008166f`
- name: `?Remove@MountedFolder@Deployment@Common@@SAJPEBG0@Z`
- size: `491`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18006b638`
- `0x180117970`

## callees

- `0x18000669c`
- `0x180012fc8`
- `0x18003bea4`
- `0x180081484`
- `0x180081678`
- `0x180081860`
- `0x1800aa820`
- `0x1800af1bc`
- `0x180184354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081525`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081504`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081504`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18008160e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18008160e`
- `KERNEL32!DeviceIoControl` at `0x1800815c6`
- `KERNEL32!DeviceIoControl` at `0x1800815c6`

## string_xrefs

- `0x1800814b4`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x18008156d`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x1800815db`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x180081623`: `onecore\admin\appmodel\common\mountedfolder.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::MountedFolder::Remove(LPCWSTR lpPathName, unsigned __int16 *a2)
{
  int IsMounted; // eax
  unsigned int v4; // ebx
  Common *FileW; // rax
  Common *v7; // rsi
  signed int v8; // eax
  void *v9; // rdx
  unsigned int LastError; // edi
  int ReparseBuffer; // eax
  const struct std::nothrow_t *v12; // rdx
  void *v13; // rcx
  void *v14; // rbx
  void *v15; // rdx
  const char *v16; // r9
  Common *v17; // rcx
  int v18; // edx
  const char *v19; // r9
  const struct std::nothrow_t *v20; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-38h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID lpInBuffer; // [rsp+68h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF
  Common *v26; // [rsp+78h] [rbp+20h]

  lpInBuffer = a2;
  LOBYTE(lpInBuffer) = 0;
  IsMounted = Common::Deployment::MountedFolder::IsMounted(lpPathName, (bool *)&lpInBuffer);
  v4 = IsMounted;
  if ( IsMounted < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
      (const char *)(unsigned int)IsMounted,
      dwCreationDisposition);
    return v4;
  }
  if ( !(_BYTE)lpInBuffer )
    return 2147942487LL;
  FileW = (Common *)CreateFileW(lpPathName, 0x40040000u, 0, 0, 3u, 0x2200000u, 0);
  v7 = FileW;
  v26 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    lpInBuffer = 0;
    ReparseBuffer = Common::Deployment::MountedFolder::GetReparseBuffer(
                      FileW,
                      (struct _REPARSE_DATA_BUFFER **)&lpInBuffer);
    LastError = ReparseBuffer;
    if ( ReparseBuffer >= 0 )
    {
      v14 = lpInBuffer;
      *((_WORD *)lpInBuffer + 2) = 0;
      BytesReturned = 0;
      if ( DeviceIoControl(v7, 0x900ACu, v14, 8u, 0, 0, &BytesReturned, 0) )
      {
        Common::CloseHandleHelper(v7, v15);
        v26 = 0;
        if ( RemoveDirectoryW(lpPathName) )
        {
          if ( Common::Deployment::IsFileInUseError((Common::Deployment *)LastError, v18) )
            Common::Deployment::LogFileInUse<DesktopAppXProvider::FileInUse>(lpPathName);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x7E,
                        (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
                        v19);
        }
        operator delete(v14, v20);
        v17 = 0;
        goto LABEL_19;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7B,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
                    v16);
      v13 = v14;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mountedfolder.cpp",
        (const char *)(unsigned int)ReparseBuffer,
        dwCreationDispositiona);
      v13 = lpInBuffer;
    }
    operator delete(v13, v12);
  }
  else
  {
    v8 = GetLastError();
    LastError = v8;
    if ( v8 > 0 )
      LastError = (unsigned __int16)v8 | 0x80070000;
  }
  v17 = v7;
LABEL_19:
  Common::CloseHandleHelper(v17, v9);
  return LastError;
}

```

## disassembly

```asm
0x180081484  mov     rax, rsp
0x180081487  mov     [rax+8], rbx
0x18008148b  mov     [rax+10h], rdx
0x18008148f  push    rbp
0x180081490  push    rsi
0x180081491  push    rdi
0x180081492  sub     rsp, 40h
0x180081496  mov     rbp, rcx
0x180081499  mov     byte ptr [rax+10h], 0
0x18008149d  lea     rdx, [rax+10h]; bool *
0x1800814a1  call    ?IsMounted@MountedFolder@Deployment@Common@@SAJPEBGPEA_N@Z; Common::Deployment::MountedFolder::IsMounted(ushort const *,bool *)
0x1800814a6  mov     ebx, eax
0x1800814a8  mov     rcx, [rsp+58h]; this
0x1800814ad  test    eax, eax
0x1800814af  jns     short loc_1800814CC
0x1800814b1  mov     r9d, eax; char *
0x1800814b4  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x1800814bb  mov     edx, 64h ; 'd'; void *
0x1800814c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800814c5  mov     eax, ebx
0x1800814c7  jmp     loc_180081661
0x1800814cc  cmp     byte ptr [rsp+58h+lpInBuffer], 0
0x1800814d1  jnz     short loc_1800814DD
0x1800814d3  mov     eax, 80070057h
0x1800814d8  jmp     loc_180081661
0x1800814dd  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800814e6  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800814ee  mov     [rsp+58h+dwCreationDisposition], 3; int
0x1800814f6  xor     r9d, r9d; lpSecurityAttributes
0x1800814f9  xor     r8d, r8d; dwShareMode
0x1800814fc  mov     edx, 40040000h; dwDesiredAccess
0x180081501  mov     rcx, rbp; lpFileName
0x180081504  call    cs:__imp_CreateFileW
0x18008150b  nop     dword ptr [rax+rax+00h]
0x180081510  mov     rsi, rax
0x180081513  mov     [rsp+58h+arg_18], rax
0x180081518  lea     rcx, [rax+1]
0x18008151c  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180081523  jnz     short loc_180081549
0x180081525  call    cs:__imp_GetLastError
0x18008152c  nop     dword ptr [rax+rax+00h]
0x180081531  mov     edi, eax
0x180081533  test    eax, eax
0x180081535  jle     loc_1800815F5
0x18008153b  movzx   edi, ax
0x18008153e  or      edi, 80070000h
0x180081544  jmp     loc_1800815F5
0x180081549  mov     [rsp+58h+lpInBuffer], 0
0x180081552  lea     rdx, [rsp+58h+lpInBuffer]; struct _REPARSE_DATA_BUFFER **
0x180081557  mov     rcx, rsi; hDevice
0x18008155a  call    ?GetReparseBuffer@MountedFolder@Deployment@Common@@CAJQEAXPEAPEAU_REPARSE_DATA_BUFFER@@@Z; Common::Deployment::MountedFolder::GetReparseBuffer(void * const,_REPARSE_DATA_BUFFER * *)
0x18008155f  mov     edi, eax
0x180081561  mov     rcx, [rsp+58h]; this
0x180081566  test    eax, eax
0x180081568  jns     short loc_180081586
0x18008156a  mov     r9d, eax; char *
0x18008156d  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x180081574  mov     edx, 6Dh ; 'm'; void *
0x180081579  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008157e  nop
0x18008157f  mov     rcx, [rsp+58h+lpInBuffer]
0x180081584  jmp     short loc_1800815EF
0x180081586  xor     eax, eax
0x180081588  mov     rbx, [rsp+58h+lpInBuffer]
0x18008158d  mov     [rbx+4], ax
0x180081591  mov     [rsp+58h+BytesReturned], eax
0x180081595  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18008159a  lea     rax, [rsp+58h+BytesReturned]
0x18008159f  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x1800815a4  mov     [rsp+58h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800815ac  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOutBuffer
0x1800815b5  mov     r9d, 8; nInBufferSize
0x1800815bb  mov     r8, rbx; lpInBuffer
0x1800815be  mov     edx, 900ACh; dwIoControlCode
0x1800815c3  mov     rcx, rsi; hDevice
0x1800815c6  call    cs:__imp_DeviceIoControl
0x1800815cd  nop     dword ptr [rax+rax+00h]
0x1800815d2  test    eax, eax
0x1800815d4  jnz     short loc_1800815FA
0x1800815d6  mov     rcx, [rsp+58h]; this
0x1800815db  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x1800815e2  lea     edx, [rax+7Bh]; void *
0x1800815e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800815ea  mov     edi, eax
0x1800815ec  mov     rcx, rbx; void *
0x1800815ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800815f4  nop
0x1800815f5  mov     rcx, rsi
0x1800815f8  jmp     short loc_18008165A
0x1800815fa  mov     rcx, rsi; this
0x1800815fd  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x180081602  mov     [rsp+58h+arg_18], 0
0x18008160b  mov     rcx, rbp; lpPathName
0x18008160e  call    cs:__imp_RemoveDirectoryW
0x180081615  nop     dword ptr [rax+rax+00h]
0x18008161a  test    eax, eax
0x18008161c  jnz     short loc_180081636
0x18008161e  mov     rcx, [rsp+58h]; this
0x180081623  lea     r8, aOnecoreAdminAp_123; "onecore\\admin\\appmodel\\common\\mount"...
0x18008162a  lea     edx, [rax+7Eh]; void *
0x18008162d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180081632  mov     edi, eax
0x180081634  jmp     short loc_18008164F
0x180081636  mov     ecx, edi; this
0x180081638  call    ?IsFileInUseError@Deployment@Common@@YA_NJ@Z; Common::Deployment::IsFileInUseError(long)
0x18008163d  test    al, al
0x18008163f  jz      short loc_18008164F
0x180081641  xor     r8d, r8d
0x180081644  mov     edx, edi
0x180081646  mov     rcx, rbp; lpFileName
0x180081649  call    ??$LogFileInUse@VFileInUse@DesktopAppXProvider@@@Deployment@Common@@YAXPEBGJ0_N@Z; Common::Deployment::LogFileInUse<DesktopAppXProvider::FileInUse>(ushort const *,long,ushort const *,bool)
0x18008164e  nop
0x18008164f  mov     rcx, rbx; void *
0x180081652  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180081657  nop
0x180081658  xor     ecx, ecx; this
0x18008165a  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x18008165f  mov     eax, edi
0x180081661  mov     rbx, [rsp+58h+arg_0]
0x180081666  add     rsp, 40h
0x18008166a  pop     rdi
0x18008166b  pop     rsi
0x18008166c  pop     rbp
0x18008166d  retn
```
