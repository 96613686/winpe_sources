# UtilSetPathToSoftReserve(wchar_t const *)

- ea: `0x140012fb0`
- end: `0x1400130f0`
- name: `?UtilSetPathToSoftReserve@@YAJPEB_W@Z`
- size: `320`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14003ecdc`
- `0x14004125c`

## callees

- `0x140012fb0`
- `0x140014f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400130d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400130d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140012fec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140012fec`
- `ntdll!NtSetInformationFile` at `0x140013088`
- `ntdll!NtSetInformationFile` at `0x140013088`

## pseudocode

```c
__int64 __fastcall UtilSetPathToSoftReserve(const wchar_t *a1)
{
  HANDLE FileW; // rax
  void *v2; // rdi
  signed int LastError; // eax
  unsigned int v4; // ebx
  NTSTATUS v5; // ebx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  int FileInformation; // [rsp+68h] [rbp+10h] BYREF

  FileInformation = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(a1, 0x180u, 7u, 0, 3u, 0x2000080u, 0);
  v2 = FileW;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    FileInformation = 2;
    v5 = NtSetInformationFile(FileW, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    if ( v5 >= 0 )
    {
      v4 = 0;
    }
    else
    {
      v4 = v5 | 0x10000000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v4);
      }
    }
    CloseHandle(v2);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140012fb0  mov     rax, rsp
0x140012fb3  mov     [rax+8], rbx
0x140012fb7  push    rdi
0x140012fb8  sub     rsp, 50h
0x140012fbc  mov     qword ptr [rax-28h], 0
0x140012fc4  xor     r9d, r9d; lpSecurityAttributes
0x140012fc7  xorps   xmm0, xmm0
0x140012fca  mov     dword ptr [rax-30h], 2000080h
0x140012fd1  mov     edx, 180h; dwDesiredAccess
0x140012fd6  mov     dword ptr [rax+10h], 0
0x140012fdd  movups  xmmword ptr [rax-18h], xmm0
0x140012fe1  lea     r8d, [r9+7]; dwShareMode
0x140012fe5  mov     dword ptr [rax-38h], 3
0x140012fec  call    cs:__imp_CreateFileW
0x140012ff3  nop     dword ptr [rax+rax+00h]
0x140012ff8  mov     rdi, rax
0x140012ffb  lea     rcx, [rax+1]
0x140012fff  cmp     rcx, 1
0x140013003  ja      short loc_140013065
0x140013005  call    cs:__imp_GetLastError
0x14001300c  nop     dword ptr [rax+rax+00h]
0x140013011  mov     ebx, eax
0x140013013  test    eax, eax
0x140013015  jle     short loc_140013020
0x140013017  movzx   ebx, ax
0x14001301a  or      ebx, 80070000h
0x140013020  test    ebx, ebx
0x140013022  mov     eax, 80004005h
0x140013027  cmovns  ebx, eax
0x14001302a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013031  lea     rax, WPP_GLOBAL_Control
0x140013038  cmp     rcx, rax
0x14001303b  jz      loc_1400130E2
0x140013041  test    byte ptr [rcx+1Ch], 2
0x140013045  jz      loc_1400130E2
0x14001304b  mov     rcx, [rcx+10h]
0x14001304f  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140013056  mov     edx, 0B8h
0x14001305b  mov     r9d, ebx
0x14001305e  call    WPP_SF_d
0x140013063  jmp     short loc_1400130E2
0x140013065  mov     r9d, 4; Length
0x14001306b  mov     [rsp+58h+FileInformation], 2
0x140013073  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x140013078  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x140013080  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x140013085  mov     rcx, rdi; FileHandle
0x140013088  call    cs:__imp_NtSetInformationFile
0x14001308f  nop     dword ptr [rax+rax+00h]
0x140013094  mov     ebx, eax
0x140013096  test    eax, eax
0x140013098  jns     short loc_1400130D1
0x14001309a  bts     ebx, 1Ch
0x14001309e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130a5  lea     rax, WPP_GLOBAL_Control
0x1400130ac  cmp     rcx, rax
0x1400130af  jz      short loc_1400130D3
0x1400130b1  test    byte ptr [rcx+1Ch], 2
0x1400130b5  jz      short loc_1400130D3
0x1400130b7  mov     rcx, [rcx+10h]
0x1400130bb  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400130c2  mov     edx, 0B9h
0x1400130c7  mov     r9d, ebx
0x1400130ca  call    WPP_SF_d
0x1400130cf  jmp     short loc_1400130D3
0x1400130d1  xor     ebx, ebx
0x1400130d3  mov     rcx, rdi; hObject
0x1400130d6  call    cs:__imp_CloseHandle
0x1400130dd  nop     dword ptr [rax+rax+00h]
0x1400130e2  mov     eax, ebx
0x1400130e4  mov     rbx, [rsp+58h+arg_0]
0x1400130e9  add     rsp, 50h
0x1400130ed  pop     rdi
0x1400130ee  retn
```
