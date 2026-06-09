# CMsmqVssWriter::ReadRestoreFile(wchar_t const *,void * *,wchar_t * *)

- ea: `0x180092810`
- end: `0x1800929f6`
- name: `?ReadRestoreFile@CMsmqVssWriter@@AEAAJPEB_WPEAPEAXPEAPEA_W@Z`
- size: `486`
- prototype: `int(CMsmqVssWriter *__hidden this, const wchar_t *, void **, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180092cb8`
- `0x180093428`

## callees

- `0x180012ea8`
- `0x18002c61c`
- `0x180092810`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18009293c`
- `msvcrt!free` at `0x18009296b`
- `msvcrt!free` at `0x18009298d`
- `msvcrt!free` at `0x18009293c`
- `msvcrt!free` at `0x18009296b`
- `msvcrt!free` at `0x18009298d`
- `KERNEL32!GetLastError` at `0x180092872`
- `KERNEL32!GetLastError` at `0x18009290b`
- `KERNEL32!GetLastError` at `0x1800929a5`
- `KERNEL32!GetLastError` at `0x180092872`
- `KERNEL32!GetLastError` at `0x18009290b`
- `KERNEL32!GetLastError` at `0x1800929a5`
- `KERNEL32!CreateFileW` at `0x180092858`
- `KERNEL32!CreateFileW` at `0x180092858`
- `KERNEL32!GetFileSize` at `0x18009289f`
- `KERNEL32!GetFileSize` at `0x18009289f`
- `KERNEL32!ReadFile` at `0x180092901`
- `KERNEL32!ReadFile` at `0x180092901`

## string_xrefs

- `0x18009292a`: `writer/mqwriter`
- `0x180092954`: `writer/mqwriter`
- `0x1800929c4`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsmqVssWriter::ReadRestoreFile(CMsmqVssWriter *this, const wchar_t *a2, void **a3, wchar_t **a4)
{
  HANDLE FileW; // rax
  void *v7; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  unsigned __int16 v10; // r8
  DWORD FileSize; // eax
  DWORD v12; // esi
  unsigned __int64 v13; // rbp
  wchar_t *v14; // rbx
  signed int v15; // eax
  signed int v16; // edi
  signed int v18; // eax
  CMsmqVssWriter *NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF
  HANDLE v20; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesRead = this;
  *a4 = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  v20 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_23;
    v10 = 1540;
    goto LABEL_22;
  }
  FileSize = GetFileSize(FileW, 0);
  v12 = FileSize;
  if ( FileSize == -1 || (FileSize & 1) != 0 )
  {
    v18 = GetLastError();
    v9 = v18;
    if ( v18 > 0 )
      v9 = (unsigned __int16)v18 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_23;
    v10 = 1560;
LABEL_22:
    LogMsgHR(v9, (wchar_t *)L"writer/mqwriter", v10);
    goto LABEL_23;
  }
  LODWORD(NumberOfBytesRead) = 0;
  v13 = (FileSize >> 1) + 1;
  v14 = (wchar_t *)MmAllocate(saturated_mul(v13, 2u));
  if ( ReadFile(v7, v14, v12, (LPDWORD)&NumberOfBytesRead, 0) )
  {
    if ( (_DWORD)NumberOfBytesRead == v12 )
    {
      v14[v13 - 1] = 0;
      *a3 = v7;
      v20 = 0;
      *a4 = v14;
      free(0);
      CHandle::~CHandle((CHandle *)&v20);
      return 0;
    }
    v16 = -1072824319;
    LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0x640u);
    free(v14);
  }
  else
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( v16 < 0 )
      LogMsgHR(v16, (wchar_t *)L"writer/mqwriter", 0x62Cu);
    free(v14);
  }
  v9 = v16;
LABEL_23:
  CHandle::~CHandle((CHandle *)&v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180092810  mov     rax, rsp
0x180092813  mov     [rax+10h], rbx
0x180092817  mov     [rax+8], rcx
0x18009281b  push    rbp
0x18009281c  push    rsi
0x18009281d  push    rdi
0x18009281e  push    r14
0x180092820  push    r15
0x180092822  sub     rsp, 50h
0x180092826  mov     r14, r9
0x180092829  mov     r15, r8
0x18009282c  mov     rcx, rdx; lpFileName
0x18009282f  mov     qword ptr [r9], 0
0x180092836  mov     qword ptr [rax-48h], 0
0x18009283e  mov     dword ptr [rax-50h], 80h
0x180092845  mov     dword ptr [rax-58h], 3
0x18009284c  xor     r9d, r9d; lpSecurityAttributes
0x18009284f  mov     edx, 80000000h; dwDesiredAccess
0x180092854  lea     r8d, [r9+1]; dwShareMode
0x180092858  call    cs:__imp_CreateFileW
0x18009285e  mov     rdi, rax
0x180092861  mov     [rsp+78h+arg_18], rax
0x180092869  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009286d  cmp     rax, rbx
0x180092870  jnz     short loc_18009289A
0x180092872  call    cs:__imp_GetLastError
0x180092878  mov     ebx, eax
0x18009287a  test    eax, eax
0x18009287c  jle     short loc_180092887
0x18009287e  movzx   ebx, ax
0x180092881  or      ebx, 80070000h
0x180092887  test    ebx, ebx
0x180092889  jns     loc_1800929D3
0x18009288f  mov     r8d, 604h
0x180092895  jmp     loc_1800929C4
0x18009289a  xor     edx, edx; lpFileSizeHigh
0x18009289c  mov     rcx, rdi; hFile
0x18009289f  call    cs:__imp_GetFileSize
0x1800928a5  mov     esi, eax
0x1800928a7  cmp     eax, 0FFFFFFFFh
0x1800928aa  jz      loc_1800929A5
0x1800928b0  test    sil, 1
0x1800928b4  jnz     loc_1800929A5
0x1800928ba  mov     dword ptr [rsp+78h+NumberOfBytesRead], 0
0x1800928c5  mov     ebp, eax
0x1800928c7  shr     ebp, 1
0x1800928c9  inc     ebp
0x1800928cb  mov     eax, 2
0x1800928d0  mul     rbp
0x1800928d3  cmovb   rax, rbx
0x1800928d7  mov     rcx, rax; unsigned __int64
0x1800928da  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800928df  mov     rbx, rax
0x1800928e2  mov     [rsp+78h+var_38], rax
0x1800928e7  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800928f0  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800928f8  mov     r8d, esi; nNumberOfBytesToRead
0x1800928fb  mov     rdx, rax; lpBuffer
0x1800928fe  mov     rcx, rdi; hFile
0x180092901  call    cs:__imp_ReadFile
0x180092907  test    eax, eax
0x180092909  jnz     short loc_180092945
0x18009290b  call    cs:__imp_GetLastError
0x180092911  mov     edi, eax
0x180092913  test    eax, eax
0x180092915  jle     short loc_180092920
0x180092917  movzx   edi, ax
0x18009291a  or      edi, 80070000h
0x180092920  test    edi, edi
0x180092922  jns     short loc_180092939
0x180092924  mov     r8d, 62Ch; unsigned __int16
0x18009292a  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092931  mov     ecx, edi; int
0x180092933  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092938  nop
0x180092939  mov     rcx, rbx; Block
0x18009293c  call    cs:__imp_free
0x180092942  nop
0x180092943  jmp     short loc_180092972
0x180092945  cmp     dword ptr [rsp+78h+NumberOfBytesRead], esi
0x18009294c  jz      short loc_180092976
0x18009294e  mov     r8d, 640h; unsigned __int16
0x180092954  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009295b  mov     edi, 0C00E0001h
0x180092960  mov     ecx, edi; int
0x180092962  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092967  nop
0x180092968  mov     rcx, rbx; Block
0x18009296b  call    cs:__imp_free
0x180092971  nop
0x180092972  mov     ebx, edi
0x180092974  jmp     short loc_1800929D3
0x180092976  xor     eax, eax
0x180092978  mov     [rbx+rbp*2-2], ax
0x18009297d  mov     [r15], rdi
0x180092980  mov     [rsp+78h+arg_18], rax
0x180092988  mov     [r14], rbx
0x18009298b  xor     ecx, ecx; Block
0x18009298d  call    cs:__imp_free
0x180092993  nop
0x180092994  lea     rcx, [rsp+78h+arg_18]; this
0x18009299c  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1800929a1  xor     eax, eax
0x1800929a3  jmp     short loc_1800929E2
0x1800929a5  call    cs:__imp_GetLastError
0x1800929ab  mov     ebx, eax
0x1800929ad  test    eax, eax
0x1800929af  jle     short loc_1800929BA
0x1800929b1  movzx   ebx, ax
0x1800929b4  or      ebx, 80070000h
0x1800929ba  test    ebx, ebx
0x1800929bc  jns     short loc_1800929D3
0x1800929be  mov     r8d, 618h; unsigned __int16
0x1800929c4  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800929cb  mov     ecx, ebx; int
0x1800929cd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800929d2  nop
0x1800929d3  lea     rcx, [rsp+78h+arg_18]; this
0x1800929db  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1800929e0  mov     eax, ebx
0x1800929e2  mov     rbx, [rsp+78h+arg_8]
0x1800929ea  add     rsp, 50h
0x1800929ee  pop     r15
0x1800929f0  pop     r14
0x1800929f2  pop     rdi
0x1800929f3  pop     rsi
0x1800929f4  pop     rbp
0x1800929f5  retn
```
