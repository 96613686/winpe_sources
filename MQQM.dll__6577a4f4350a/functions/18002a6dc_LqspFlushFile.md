# LqspFlushFile

- ea: `0x18002a6dc`
- end: `0x18002a811`
- name: `LqspFlushFile`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180029950`

## callees

- `0x18000e558`
- `0x180012ea8`
- `0x18002a6dc`
- `0x18002c574`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a742`
- `KERNEL32!GetLastError` at `0x18002a7b6`
- `KERNEL32!GetLastError` at `0x18002a742`
- `KERNEL32!GetLastError` at `0x18002a7b6`
- `KERNEL32!CreateFileW` at `0x18002a714`
- `KERNEL32!CreateFileW` at `0x18002a714`
- `KERNEL32!FlushFileBuffers` at `0x18002a78f`
- `KERNEL32!FlushFileBuffers` at `0x18002a78f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LqspFlushFile(const WCHAR *a1)
{
  HANDLE FileW; // rax
  char LastError; // al
  char v4; // al
  unsigned int v5; // ebx
  HANDLE v6; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 3u, 0xA0000000, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    }
    LogMsgBOOL(0, (wchar_t *)L"lqs", 0x230u);
    CHandle::~CHandle((CHandle *)&v6);
    return 0;
  }
  else
  {
    if ( FlushFileBuffers(FileW) )
    {
      v5 = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = GetLastError();
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4);
      }
      LogMsgBOOL(0, (wchar_t *)L"lqs", 0x23Au);
      v5 = 0;
    }
    CHandle::~CHandle((CHandle *)&v6);
    return v5;
  }
}

```

## disassembly

```asm
0x18002a6dc  mov     rax, rsp
0x18002a6df  mov     [rax+8], rbx
0x18002a6e3  push    rdi
0x18002a6e4  sub     rsp, 40h
0x18002a6e8  mov     rdi, rcx
0x18002a6eb  mov     qword ptr [rax+10h], 0
0x18002a6f3  mov     qword ptr [rax-18h], 0
0x18002a6fb  mov     dword ptr [rax-20h], 0A0000000h
0x18002a702  mov     dword ptr [rax-28h], 3
0x18002a709  xor     r9d, r9d; lpSecurityAttributes
0x18002a70c  xor     r8d, r8d; dwShareMode
0x18002a70f  mov     edx, 40000000h; dwDesiredAccess
0x18002a714  call    cs:__imp_CreateFileW
0x18002a71a  mov     [rsp+48h+arg_8], rax
0x18002a71f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a723  jnz     short loc_18002A78C
0x18002a725  lea     rax, WPP_GLOBAL_Control
0x18002a72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a733  cmp     rcx, rax
0x18002a736  jz      short loc_18002A769
0x18002a738  mov     ebx, 1
0x18002a73d  test    [rcx+1Ch], bl
0x18002a740  jz      short loc_18002A769
0x18002a742  call    cs:__imp_GetLastError
0x18002a748  lea     edx, [rbx+9]
0x18002a74b  mov     dword ptr [rsp+48h+var_28], eax; char
0x18002a74f  mov     r9, rdi
0x18002a752  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x18002a759  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a760  mov     rcx, [rcx+10h]; LoggerHandle
0x18002a764  call    WPP_SF_Sd
0x18002a769  mov     r8d, 230h; unsigned __int16
0x18002a76f  lea     rdx, aLqs_0; "lqs"
0x18002a776  xor     ecx, ecx; int
0x18002a778  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18002a77d  nop
0x18002a77e  lea     rcx, [rsp+48h+arg_8]; this
0x18002a783  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18002a788  xor     eax, eax
0x18002a78a  jmp     short loc_18002A806
0x18002a78c  mov     rcx, rax; hFile
0x18002a78f  call    cs:__imp_FlushFileBuffers
0x18002a795  test    eax, eax
0x18002a797  jnz     short loc_18002A7F5
0x18002a799  lea     rax, WPP_GLOBAL_Control
0x18002a7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7a7  cmp     rcx, rax
0x18002a7aa  jz      short loc_18002A7DD
0x18002a7ac  mov     ebx, 1
0x18002a7b1  test    [rcx+1Ch], bl
0x18002a7b4  jz      short loc_18002A7DD
0x18002a7b6  call    cs:__imp_GetLastError
0x18002a7bc  lea     edx, [rbx+0Ah]
0x18002a7bf  mov     dword ptr [rsp+48h+var_28], eax; char
0x18002a7c3  mov     r9, rdi
0x18002a7c6  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x18002a7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7d4  mov     rcx, [rcx+10h]; LoggerHandle
0x18002a7d8  call    WPP_SF_Sd
0x18002a7dd  mov     r8d, 23Ah; unsigned __int16
0x18002a7e3  lea     rdx, aLqs_0; "lqs"
0x18002a7ea  xor     ecx, ecx; int
0x18002a7ec  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18002a7f1  xor     ebx, ebx
0x18002a7f3  jmp     short loc_18002A7FA
0x18002a7f5  mov     ebx, 1
0x18002a7fa  lea     rcx, [rsp+48h+arg_8]; this
0x18002a7ff  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18002a804  mov     eax, ebx
0x18002a806  mov     rbx, [rsp+48h+arg_0]
0x18002a80b  add     rsp, 40h
0x18002a80f  pop     rdi
0x18002a810  retn
```
