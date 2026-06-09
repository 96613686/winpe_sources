# File::TryOpen(wchar_t const *,File::OpenMode)

- ea: `0x18000e3f0`
- end: `0x18000e534`
- name: `?TryOpen@File@@QEAAJPEB_WW4OpenMode@1@@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000e3d0`
- `0x1800105b4`
- `0x180041908`
- `0x1800a3f04`

## callees

- `0x18000e3f0`
- `0x18000e53c`
- `0x18000e5e8`
- `0x18000e86c`
- `0x18000f39c`
- `0x180028c50`
- `0x18004d664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e45d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e45d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e40a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e4b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e4f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e40a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e4b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e4f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e451`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e451`

## pseudocode

```c
__int64 __fastcall File::TryOpen(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  const char *v6; // rdx
  UINT v7; // edi
  int v8; // eax
  DWORD v9; // edx
  DWORD v10; // r8d
  DWORD dwCreationDisposition; // ecx
  HANDLE FileW; // rax
  DWORD LastError; // esi
  struct DWrite::RefString::Data *v14; // rbx
  unsigned int v15; // esi
  unsigned int v17; // ebx
  HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  v7 = SetErrorMode(0x8001u);
  v8 = a3 & 0xC;
  if ( (a3 & 0xC) == 0 )
  {
    v9 = 0x80000000;
    v10 = v8 + 7;
LABEL_3:
    dwCreationDisposition = 3;
    goto LABEL_4;
  }
  if ( v8 == 4 )
  {
    v9 = -1073741824;
    v10 = 5;
    goto LABEL_3;
  }
  if ( v8 != 8 )
  {
    FailAssert(0x4Du, v6);
    __debugbreak();
  }
  v9 = -1073741824;
  dwCreationDisposition = 2;
  v10 = 5;
LABEL_4:
  FileW = CreateFileW(a2, v9, v10, 0, dwCreationDisposition, (a3 & 2 | 0x10) << 24, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    GetDepersonalizedFilePath(&hObject, a2);
    v14 = (struct DWrite::RefString::Data *)hObject;
    LogEvent<long,EventTag,unsigned int,wchar_t const *>(g_errorTag, LastError, 1701603686, 97, (__int64)hObject + 8);
    v15 = IOException::MapFileOpenError(LastError);
    DWrite::RefString::DecrementRef(v14);
    SetErrorMode(v7);
    return v15;
  }
  else
  {
    hObject = FileW;
    v17 = File::TryOpen(a1, &hObject, a3);
    if ( hObject )
      CloseHandle(hObject);
    SetErrorMode(v7);
    return v17;
  }
}

```

## disassembly

```asm
0x18000e3f0  mov     [rsp+arg_0], rbx
0x18000e3f5  push    rbp
0x18000e3f6  push    rsi
0x18000e3f7  push    rdi
0x18000e3f8  sub     rsp, 40h
0x18000e3fc  mov     ebx, r8d
0x18000e3ff  mov     rbp, rdx
0x18000e402  mov     rsi, rcx
0x18000e405  mov     ecx, 8001h; uMode
0x18000e40a  call    cs:__imp_SetErrorMode
0x18000e410  mov     edi, eax
0x18000e412  mov     [rsp+58h+arg_10], eax
0x18000e416  mov     eax, ebx
0x18000e418  and     eax, 0Ch
0x18000e41b  jnz     loc_18000E4FB
0x18000e421  mov     edx, 80000000h; dwDesiredAccess
0x18000e426  lea     r8d, [rax+7]; dwShareMode
0x18000e42a  mov     ecx, 3
0x18000e42f  mov     eax, ebx
0x18000e431  and     eax, 2
0x18000e434  or      eax, 10h
0x18000e437  shl     eax, 18h
0x18000e43a  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18000e443  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000e447  mov     [rsp+58h+dwCreationDisposition], ecx; dwCreationDisposition
0x18000e44b  xor     r9d, r9d; lpSecurityAttributes
0x18000e44e  mov     rcx, rbp; lpFileName
0x18000e451  call    cs:__imp_CreateFileW
0x18000e457  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e45b  jnz     short loc_18000E4C7
0x18000e45d  call    cs:__imp_GetLastError
0x18000e463  mov     esi, eax
0x18000e465  mov     rdx, rbp
0x18000e468  lea     rcx, [rsp+58h+hObject]
0x18000e46d  call    ?GetDepersonalizedFilePath@@YA?AVRefString@DWrite@@PEB_W@Z; GetDepersonalizedFilePath(wchar_t const *)
0x18000e472  mov     r8, 6F69656C6966h
0x18000e47c  mov     rbx, [rsp+58h+hObject]
0x18000e481  lea     rcx, [rbx+8]
0x18000e485  mov     qword ptr [rsp+58h+dwCreationDisposition], rcx
0x18000e48a  mov     r9d, 61h ; 'a'
0x18000e490  mov     edx, esi
0x18000e492  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x18000e499  call    ??$LogEvent@JVEventTag@@IPEB_W@@YAXVEventTag@@J0IPEB_W@Z; LogEvent<long,EventTag,uint,wchar_t const *>(EventTag,long,EventTag,uint,wchar_t const *)
0x18000e49e  mov     ecx, esi; int
0x18000e4a0  call    ?MapFileOpenError@IOException@@SAHH@Z; IOException::MapFileOpenError(int)
0x18000e4a5  mov     esi, eax
0x18000e4a7  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18000e4aa  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000e4af  nop
0x18000e4b0  mov     ecx, edi; uMode
0x18000e4b2  call    cs:__imp_SetErrorMode
0x18000e4b8  mov     eax, esi
0x18000e4ba  mov     rbx, [rsp+58h+arg_0]
0x18000e4bf  add     rsp, 40h
0x18000e4c3  pop     rdi
0x18000e4c4  pop     rsi
0x18000e4c5  pop     rbp
0x18000e4c6  retn
0x18000e4c7  mov     [rsp+58h+hObject], rax
0x18000e4cc  mov     r8d, ebx
0x18000e4cf  lea     rdx, [rsp+58h+hObject]
0x18000e4d4  mov     rcx, rsi
0x18000e4d7  call    ?TryOpen@File@@QEAAJ$$QEAVWin32Handle@@W4OpenMode@1@@Z; File::TryOpen(Win32Handle &&,File::OpenMode)
0x18000e4dc  mov     ebx, eax
0x18000e4de  mov     rcx, [rsp+58h+hObject]; hObject
0x18000e4e3  test    rcx, rcx
0x18000e4e6  jz      short loc_18000E4EF
0x18000e4e8  call    cs:__imp_CloseHandle
0x18000e4ee  nop
0x18000e4ef  mov     ecx, edi; uMode
0x18000e4f1  call    cs:__imp_SetErrorMode
0x18000e4f7  mov     eax, ebx
0x18000e4f9  jmp     short loc_18000E4BA
0x18000e4fb  cmp     eax, 4
0x18000e4fe  jz      short loc_18000E523
0x18000e500  cmp     eax, 8
0x18000e503  jz      short loc_18000E510
0x18000e505  mov     ecx, 4Dh ; 'M'; unsigned int
0x18000e50a  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18000e50f  int     3; Trap to Debugger
0x18000e510  mov     edx, 0C0000000h
0x18000e515  mov     ecx, 2
0x18000e51a  lea     r8d, [rcx+3]
0x18000e51e  jmp     loc_18000E42F
0x18000e523  mov     edx, 0C0000000h
0x18000e528  mov     r8d, 5
0x18000e52e  jmp     loc_18000E42A
```
