# CreateLqsUnicodeFile(wchar_t const *)

- ea: `0x180026698`
- end: `0x1800267fc`
- name: `?CreateLqsUnicodeFile@@YAJPEB_W@Z`
- size: `356`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180029950`

## callees

- `0x18000e558`
- `0x1800261c0`
- `0x180026698`
- `0x18002c61c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800266d9`
- `KERNEL32!GetLastError` at `0x18002676b`
- `KERNEL32!GetLastError` at `0x1800266d9`
- `KERNEL32!GetLastError` at `0x18002676b`
- `KERNEL32!CreateFileW` at `0x1800266c8`
- `KERNEL32!CreateFileW` at `0x1800266c8`
- `KERNEL32!WriteFile` at `0x180026761`
- `KERNEL32!WriteFile` at `0x180026761`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateLqsUnicodeFile(const wchar_t *a1)
{
  HANDLE FileW; // rax
  signed int LastError; // ebx
  bool v3; // sf
  unsigned __int16 v4; // r8
  bool v5; // sf
  __int16 Buffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF
  HANDLE v9; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 1u, 0x100u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    v3 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = LastError < 0;
    }
    if ( v3 )
    {
      v4 = 1152;
LABEL_17:
      LogMsgHR(LastError, (wchar_t *)L"lqs", v4);
    }
  }
  else
  {
    Buffer = -257;
    NumberOfBytesWritten = 0;
    if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == 2 )
      {
        LastError = 0;
        goto LABEL_21;
      }
      v4 = 615;
      LastError = -1072824319;
      goto LABEL_17;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    v5 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError < 0;
    }
    if ( v5 )
    {
      v4 = 1153;
      goto LABEL_17;
    }
  }
LABEL_21:
  CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180026698  mov     rax, rsp
0x18002669b  mov     [rax+8], rbx
0x18002669f  push    rdi
0x1800266a0  sub     rsp, 40h
0x1800266a4  mov     rdi, rcx
0x1800266a7  mov     qword ptr [rax-18h], 0
0x1800266af  mov     dword ptr [rax-20h], 100h
0x1800266b6  mov     dword ptr [rax-28h], 1
0x1800266bd  xor     r9d, r9d; lpSecurityAttributes
0x1800266c0  xor     r8d, r8d; dwShareMode
0x1800266c3  mov     edx, 40000000h; dwDesiredAccess
0x1800266c8  call    cs:__imp_CreateFileW
0x1800266ce  mov     [rsp+48h+arg_18], rax
0x1800266d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800266d7  jnz     short loc_180026736
0x1800266d9  call    cs:__imp_GetLastError
0x1800266df  mov     ebx, eax
0x1800266e1  lea     rax, WPP_GLOBAL_Control
0x1800266e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266ef  cmp     rcx, rax
0x1800266f2  jz      short loc_180026716
0x1800266f4  test    byte ptr [rcx+1Ch], 1
0x1800266f8  jz      short loc_180026716
0x1800266fa  mov     edx, 14h
0x1800266ff  mov     dword ptr [rsp+48h+lpOverlapped], ebx; char
0x180026703  mov     r9, rdi
0x180026706  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x18002670d  mov     rcx, [rcx+10h]; LoggerHandle
0x180026711  call    WPP_SF_Sd
0x180026716  test    ebx, ebx
0x180026718  jle     short loc_180026725
0x18002671a  movzx   ebx, bx
0x18002671d  or      ebx, 80070000h
0x180026723  test    ebx, ebx
0x180026725  jns     loc_1800267E5
0x18002672b  mov     r8d, 480h
0x180026731  jmp     loc_1800267BF
0x180026736  mov     [rsp+48h+Buffer], 0FEFFh
0x18002673d  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180026745  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18002674e  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180026753  mov     r8d, 2; nNumberOfBytesToWrite
0x180026759  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x18002675e  mov     rcx, rax; hFile
0x180026761  call    cs:__imp_WriteFile
0x180026767  test    eax, eax
0x180026769  jnz     short loc_1800267CF
0x18002676b  call    cs:__imp_GetLastError
0x180026771  mov     ebx, eax
0x180026773  lea     rax, WPP_GLOBAL_Control
0x18002677a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026781  cmp     rcx, rax
0x180026784  jz      short loc_1800267A8
0x180026786  test    byte ptr [rcx+1Ch], 1
0x18002678a  jz      short loc_1800267A8
0x18002678c  mov     edx, 15h
0x180026791  mov     dword ptr [rsp+48h+lpOverlapped], ebx; char
0x180026795  mov     r9, rdi
0x180026798  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x18002679f  mov     rcx, [rcx+10h]; LoggerHandle
0x1800267a3  call    WPP_SF_Sd
0x1800267a8  test    ebx, ebx
0x1800267aa  jle     short loc_1800267B7
0x1800267ac  movzx   ebx, bx
0x1800267af  or      ebx, 80070000h
0x1800267b5  test    ebx, ebx
0x1800267b7  jns     short loc_1800267E5
0x1800267b9  mov     r8d, 481h; unsigned __int16
0x1800267bf  lea     rdx, aLqs_0; "lqs"
0x1800267c6  mov     ecx, ebx; int
0x1800267c8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800267cd  jmp     short loc_1800267E5
0x1800267cf  cmp     [rsp+48h+NumberOfBytesWritten], 2
0x1800267d4  jz      short loc_1800267E3
0x1800267d6  mov     r8d, 267h
0x1800267dc  mov     ebx, 0C00E0001h
0x1800267e1  jmp     short loc_1800267BF
0x1800267e3  xor     ebx, ebx
0x1800267e5  lea     rcx, [rsp+48h+arg_18]; this
0x1800267ea  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800267ef  mov     eax, ebx
0x1800267f1  mov     rbx, [rsp+48h+arg_0]
0x1800267f6  add     rsp, 40h
0x1800267fa  pop     rdi
0x1800267fb  retn
```
