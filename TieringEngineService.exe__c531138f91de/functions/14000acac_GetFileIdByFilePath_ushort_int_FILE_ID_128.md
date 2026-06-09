# GetFileIdByFilePath(ushort *,int,_FILE_ID_128 *)

- ea: `0x14000acac`
- end: `0x14000aea2`
- name: `?GetFileIdByFilePath@@YAJPEAGHPEAU_FILE_ID_128@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, struct _FILE_ID_128 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000d804`
- `0x14003c7e8`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14000acac`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ae73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ae73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000ad8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000ad8a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14000ae08`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14000ae08`

## string_xrefs

- `0x14000ace0`: `GetFileIdByFilePath`

## pseudocode

```c
__int64 __fastcall GetFileIdByFilePath(LPCWSTR lpFileName, int a2, struct _FILE_ID_128 *a3)
{
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  void *v8; // rdi
  DWORD LastError; // eax
  DWORD v10; // eax
  _BYTE v12[8]; // [rsp+40h] [rbp-48h] BYREF
  int v13; // [rsp+48h] [rbp-40h]
  _BYTE FileInformation[24]; // [rsp+50h] [rbp-38h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "GetFileIdByFilePath";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( a3 )
  {
    FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, a2 != 0 ? 35651712 : 33554560, 0);
    v8 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = ATL::AtlHresultFromWin32(LastError);
      v13 = v6;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
          (_DWORD)lpFileName,
          v6);
      }
    }
    else
    {
      if ( GetFileInformationByHandleEx(FileW, MaximumFileInfoByHandleClass, FileInformation, 0x18u) )
      {
        v6 = v13;
        *a3 = *(struct _FILE_ID_128 *)&FileInformation[8];
      }
      else
      {
        v10 = GetLastError();
        v6 = ATL::AtlHresultFromWin32(v10);
        v13 = v6;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
            (_DWORD)lpFileName,
            v6);
        }
      }
      CloseHandle(v8);
    }
  }
  else
  {
    v6 = -2147024809;
    v13 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids, 2147942487LL);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v12);
  return v6;
}

```

## disassembly

```asm
0x14000acac  mov     [rsp+arg_8], rbx
0x14000acb1  push    rbp
0x14000acb2  push    rsi
0x14000acb3  push    rdi
0x14000acb4  sub     rsp, 70h
0x14000acb8  mov     rax, cs:__security_cookie
0x14000acbf  xor     rax, rsp
0x14000acc2  mov     [rsp+88h+var_20], rax
0x14000acc7  mov     rax, gs:58h
0x14000acd0  mov     rsi, rcx
0x14000acd3  mov     ebx, edx
0x14000acd5  mov     rbp, r8
0x14000acd8  mov     edx, 8
0x14000acdd  mov     rcx, [rax]
0x14000ace0  lea     rax, aGetfileidbyfil; "GetFileIdByFilePath"
0x14000ace7  mov     [rdx+rcx], rax
0x14000aceb  lea     rcx, [rsp+88h+var_48]; this
0x14000acf0  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000acf5  xor     eax, eax
0x14000acf7  xorps   xmm0, xmm0
0x14000acfa  mov     [rsp+88h+var_28], rax
0x14000acff  movups  [rsp+88h+FileInformation], xmm0
0x14000ad04  test    rbp, rbp
0x14000ad07  jnz     short loc_14000AD58
0x14000ad09  mov     ebx, 80070057h
0x14000ad0e  mov     [rsp+88h+var_40], ebx
0x14000ad12  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad19  lea     rax, WPP_GLOBAL_Control
0x14000ad20  cmp     rcx, rax
0x14000ad23  jz      loc_14000AE79
0x14000ad29  test    byte ptr [rcx+1Ch], 1
0x14000ad2d  jz      loc_14000AE79
0x14000ad33  cmp     byte ptr [rcx+19h], 2
0x14000ad37  jb      loc_14000AE79
0x14000ad3d  mov     rcx, [rcx+10h]
0x14000ad41  lea     edx, [rbp+1Eh]
0x14000ad44  mov     r9d, ebx
0x14000ad47  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000ad4e  call    WPP_SF_d
0x14000ad53  jmp     loc_14000AE79
0x14000ad58  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x14000ad61  neg     ebx
0x14000ad63  mov     edx, 80h; dwDesiredAccess
0x14000ad68  mov     rcx, rsi; lpFileName
0x14000ad6b  sbb     eax, eax
0x14000ad6d  xor     r9d, r9d; lpSecurityAttributes
0x14000ad70  and     eax, 200000h
0x14000ad75  add     eax, 2000080h
0x14000ad7a  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14000ad7e  lea     r8d, [r9+7]; dwShareMode
0x14000ad82  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x14000ad8a  call    cs:__imp_CreateFileW
0x14000ad90  mov     rdi, rax
0x14000ad93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ad97  jnz     short loc_14000ADF6
0x14000ad99  call    cs:__imp_GetLastError
0x14000ad9f  mov     ecx, eax; unsigned int
0x14000ada1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000ada6  mov     ebx, eax
0x14000ada8  mov     [rsp+88h+var_40], eax
0x14000adac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adb3  lea     rax, WPP_GLOBAL_Control
0x14000adba  cmp     rcx, rax
0x14000adbd  jz      loc_14000AE79
0x14000adc3  test    byte ptr [rcx+1Ch], 1
0x14000adc7  jz      loc_14000AE79
0x14000adcd  cmp     byte ptr [rcx+19h], 2
0x14000add1  jb      loc_14000AE79
0x14000add7  mov     rcx, [rcx+10h]
0x14000addb  lea     edx, [rdi+20h]
0x14000adde  mov     r9, rsi
0x14000ade1  mov     [rsp+88h+dwCreationDisposition], ebx
0x14000ade5  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000adec  call    WPP_SF_Sd
0x14000adf1  jmp     loc_14000AE79
0x14000adf6  mov     r9d, 18h; dwBufferSize
0x14000adfc  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x14000ae01  mov     rcx, rdi; hFile
0x14000ae04  lea     edx, [r9-6]; FileInformationClass
0x14000ae08  call    cs:__imp_GetFileInformationByHandleEx
0x14000ae0e  test    eax, eax
0x14000ae10  jnz     short loc_14000AE62
0x14000ae12  call    cs:__imp_GetLastError
0x14000ae18  mov     ecx, eax; unsigned int
0x14000ae1a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000ae1f  mov     ebx, eax
0x14000ae21  mov     [rsp+88h+var_40], eax
0x14000ae25  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae2c  lea     rax, WPP_GLOBAL_Control
0x14000ae33  cmp     rcx, rax
0x14000ae36  jz      short loc_14000AE70
0x14000ae38  test    byte ptr [rcx+1Ch], 1
0x14000ae3c  jz      short loc_14000AE70
0x14000ae3e  cmp     byte ptr [rcx+19h], 2
0x14000ae42  jb      short loc_14000AE70
0x14000ae44  mov     rcx, [rcx+10h]
0x14000ae48  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000ae4f  mov     edx, 20h ; ' '
0x14000ae54  mov     [rsp+88h+dwCreationDisposition], ebx
0x14000ae58  mov     r9, rsi
0x14000ae5b  call    WPP_SF_Sd
0x14000ae60  jmp     short loc_14000AE70
0x14000ae62  movups  xmm0, [rsp+88h+FileInformation+8]
0x14000ae67  mov     ebx, [rsp+88h+var_40]
0x14000ae6b  movdqu  xmmword ptr [rbp+0], xmm0
0x14000ae70  mov     rcx, rdi; hObject
0x14000ae73  call    cs:__imp_CloseHandle
0x14000ae79  lea     rcx, [rsp+88h+var_48]; this
0x14000ae7e  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000ae83  mov     eax, ebx
0x14000ae85  mov     rcx, [rsp+88h+var_20]
0x14000ae8a  xor     rcx, rsp; StackCookie
0x14000ae8d  call    __security_check_cookie
0x14000ae92  mov     rbx, [rsp+88h+arg_8]
0x14000ae9a  add     rsp, 70h
0x14000ae9e  pop     rdi
0x14000ae9f  pop     rsi
0x14000aea0  pop     rbp
0x14000aea1  retn
```
