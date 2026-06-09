# LoadSingleBitmapIntoSection(HDC__ *,HBITMAP__ *,void * *)

- ea: `0x180002130`
- end: `0x180002383`
- name: `?LoadSingleBitmapIntoSection@@YAXPEAUHDC__@@PEAUHBITMAP__@@PEAPEAX@Z`
- size: `595`
- prototype: `void __fastcall(HDC hdc, HBITMAP hbm, LPHANDLE lpTargetHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180001db0`

## callees

- `0x180002130`
- `0x180003760`
- `0x1800037e4`
- `0x1800045ba`
- `0x18000578c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000231a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000231a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000235b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000235b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800021d5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800021d5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180002191`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180002191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000237c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000233e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000233e`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180002232`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800022b1`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180002232`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800022b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LoadSingleBitmapIntoSection(HDC hdc, HBITMAP hbm, LPHANDLE lpTargetHandle)
{
  unsigned int v6; // r8d
  HANDLE FileMappingW; // rdi
  unsigned int v8; // r8d
  const char *v9; // r9
  struct tagBITMAPINFO *v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  struct tagBITMAPINFO *v13; // rbx
  unsigned int v14; // r8d
  UINT biHeight; // r9d
  unsigned int v16; // r8d
  unsigned __int64 v17; // rcx
  HANDLE CurrentProcess; // rsi
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  int dwMaximumSizeLow; // [rsp+20h] [rbp-58h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-58h]
  int dwMaximumSizeLowb; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *lpTargetHandle = 0;
  if ( !(unsigned __int8)IsGetDIBitsPresent() )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xBD, v6, (const char *)0x80004001LL, dwMaximumSizeLow);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, 0x100000u, 0);
  if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC3, v8, v9);
  v10 = (struct tagBITMAPINFO *)MapViewOfFileEx(FileMappingW, 6u, 0, 0, 0, 0);
  v13 = v10;
  if ( !v10 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC6, v11, v12);
  memset_0(&v10->bmiHeader.biWidth, 0, 0x78u);
  v13->bmiHeader.biSize = 124;
  if ( !GetDIBits(hdc, hbm, 0, 0, 0, v13, 0) )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xD4, v14, (const char *)0x80070057LL, dwMaximumSizeLowa);
  biHeight = v13->bmiHeader.biHeight;
  if ( (int)(4 * v13->bmiHeader.biWidth * biHeight + 124) > 0x100000 )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xDC, v14, (const char *)0x8000000BLL, dwMaximumSizeLowa);
  v13[1].bmiHeader.biHeight = -16777216;
  v13->bmiHeader.biBitCount = 32;
  v13->bmiHeader.biCompression = 0;
  if ( GetDIBits(hdc, hbm, 0, biHeight, &v13[2].bmiHeader.biClrImportant, v13, 0) != v13->bmiHeader.biHeight )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xE5, v16, (const char *)0x80070057LL, dwMaximumSizeLowb);
  v17 = 0;
  if ( (v13->bmiHeader.biSizeImage & 0xFFFFFFFC) != 0 )
  {
    do
      *(&v13[2].bmiHeader.biClrImportant + v17++) |= 0xFF000000;
    while ( v17 < (unsigned __int64)v13->bmiHeader.biSizeImage >> 2 );
  }
  v13->bmiHeader.biBitCount = 32;
  v13->bmiHeader.biSize = 124;
  *(_QWORD *)&v13->bmiHeader.biCompression = 0;
  v13->bmiHeader.biClrUsed = 0;
  *(_DWORD *)&v13[1].bmiHeader.biPlanes = 1466527264;
  CurrentProcess = GetCurrentProcess();
  v19 = GetCurrentProcess();
  if ( !DuplicateHandle(v19, FileMappingW, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xF3, v20, v21);
  UnmapViewOfFile(v13);
  CloseHandle(FileMappingW);
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  push    rbp
0x180002136  push    rsi
0x180002137  push    rdi
0x180002138  push    r12
0x18000213a  push    r13
0x18000213c  push    r14
0x18000213e  push    r15
0x180002140  sub     rsp, 40h
0x180002144  mov     r14, r8
0x180002147  mov     rsi, rdx
0x18000214a  mov     rbp, rcx
0x18000214d  xor     r12d, r12d
0x180002150  mov     [r8], r12
0x180002153  call    IsGetDIBitsPresent
0x180002158  test    al, al
0x18000215a  jnz     short loc_180002172
0x18000215c  mov     rcx, [rsp+78h]; this
0x180002161  mov     edx, 0BDh; void *
0x180002166  mov     r9d, 80004001h; char *
0x18000216c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002172  mov     [rsp+78h+lpName], r12; lpName
0x180002177  mov     [rsp+78h+dwMaximumSizeLow], 100000h; dwMaximumSizeLow
0x18000217f  xor     r9d, r9d; dwMaximumSizeHigh
0x180002182  xor     edx, edx; lpFileMappingAttributes
0x180002184  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000218b  mov     r8d, 8000004h; flProtect
0x180002191  call    cs:__imp_CreateFileMappingW
0x180002197  mov     rdi, rax
0x18000219a  mov     [rsp+78h+arg_10], rax
0x1800021a2  mov     rcx, [rsp+78h]; this
0x1800021a7  inc     rax
0x1800021aa  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800021b0  jnz     short loc_1800021BD
0x1800021b2  mov     edx, 0C3h; void *
0x1800021b7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800021bd  mov     [rsp+78h+lpName], r12; lpBaseAddress
0x1800021c2  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x1800021c7  xor     r9d, r9d; dwFileOffsetLow
0x1800021ca  xor     r8d, r8d; dwFileOffsetHigh
0x1800021cd  mov     edx, 6; dwDesiredAccess
0x1800021d2  mov     rcx, rdi; hFileMappingObject
0x1800021d5  call    cs:__imp_MapViewOfFileEx
0x1800021db  mov     rbx, rax
0x1800021de  mov     [rsp+78h+arg_18], rax
0x1800021e6  mov     rcx, [rsp+78h]; this
0x1800021eb  test    rax, rax
0x1800021ee  jnz     short loc_1800021FB
0x1800021f0  mov     edx, 0C6h; void *
0x1800021f5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800021fb  lea     rcx, [rax+4]; void *
0x1800021ff  xor     edx, edx; Val
0x180002201  mov     r8d, 78h ; 'x'; Size
0x180002207  call    memset_0
0x18000220c  mov     dword ptr [rbx], 7Ch ; '|'
0x180002212  mov     r15, [rsp+78h]
0x180002217  mov     [rsp+78h+usage], r12d; usage
0x18000221c  mov     [rsp+78h+lpName], rbx; lpbmi
0x180002221  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r12; int
0x180002226  xor     r9d, r9d; cLines
0x180002229  xor     r8d, r8d; start
0x18000222c  mov     rdx, rsi; hbm
0x18000222f  mov     rcx, rbp; hdc
0x180002232  call    cs:__imp_GetDIBits
0x180002238  test    eax, eax
0x18000223a  jnz     short loc_180002250
0x18000223c  mov     edx, 0D4h; void *
0x180002241  mov     r9d, 80070057h; char *
0x180002247  mov     rcx, r15; this
0x18000224a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002250  mov     r9d, [rbx+8]; cLines
0x180002254  mov     eax, r9d
0x180002257  imul    eax, [rbx+4]
0x18000225b  lea     eax, ds:7Ch[rax*4]
0x180002262  cmp     eax, 100000h
0x180002267  jle     short loc_18000227F
0x180002269  mov     rcx, [rsp+78h]; this
0x18000226e  mov     edx, 0DCh; void *
0x180002273  mov     r9d, 8000000Bh; char *
0x180002279  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000227f  lea     r15, [rbx+7Ch]
0x180002283  mov     dword ptr [rbx+34h], 0FF000000h
0x18000228a  mov     r13d, 20h ; ' '
0x180002290  mov     [rbx+0Eh], r13w
0x180002295  mov     [rbx+10h], r12d
0x180002299  mov     [rsp+78h+usage], r12d; usage
0x18000229e  mov     [rsp+78h+lpName], rbx; lpbmi
0x1800022a3  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r15; int
0x1800022a8  xor     r8d, r8d; start
0x1800022ab  mov     rdx, rsi; hbm
0x1800022ae  mov     rcx, rbp; hdc
0x1800022b1  call    cs:__imp_GetDIBits
0x1800022b7  mov     rcx, [rsp+78h]; this
0x1800022bc  cmp     eax, [rbx+8]
0x1800022bf  jz      short loc_1800022D2
0x1800022c1  mov     edx, 0E5h; void *
0x1800022c6  mov     r9d, 80070057h; char *
0x1800022cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800022d2  mov     rcx, r12
0x1800022d5  mov     eax, [rbx+14h]
0x1800022d8  test    rax, 0FFFFFFFFFFFFFFFCh
0x1800022de  jbe     short loc_1800022F7
0x1800022e0  or      dword ptr [r15+rcx*4], 0FF000000h
0x1800022e8  inc     rcx
0x1800022eb  mov     eax, [rbx+14h]
0x1800022ee  shr     rax, 2
0x1800022f2  cmp     rcx, rax
0x1800022f5  jb      short loc_1800022E0
0x1800022f7  mov     [rbx+0Eh], r13w
0x1800022fc  mov     dword ptr [rbx], 7Ch ; '|'
0x180002302  mov     [rbx+10h], r12
0x180002306  mov     [rbx+20h], r12d
0x18000230a  mov     dword ptr [rbx+38h], 57696E20h
0x180002311  call    cs:__imp_GetCurrentProcess
0x180002317  mov     rsi, rax
0x18000231a  call    cs:__imp_GetCurrentProcess
0x180002320  mov     [rsp+78h+usage], 2; dwOptions
0x180002328  mov     dword ptr [rsp+78h+lpName], r12d; bInheritHandle
0x18000232d  mov     [rsp+78h+dwMaximumSizeLow], r12d; dwDesiredAccess
0x180002332  mov     r9, r14; lpTargetHandle
0x180002335  mov     r8, rsi; hTargetProcessHandle
0x180002338  mov     rdx, rdi; hSourceHandle
0x18000233b  mov     rcx, rax; hSourceProcessHandle
0x18000233e  call    cs:__imp_DuplicateHandle
0x180002344  mov     rcx, [rsp+78h]; this
0x180002349  test    eax, eax
0x18000234b  jnz     short loc_180002358
0x18000234d  mov     edx, 0F3h; void *
0x180002352  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180002358  mov     rcx, rbx; lpBaseAddress
0x18000235b  call    cs:__imp_UnmapViewOfFile
0x180002361  nop
0x180002362  mov     rcx, rdi
0x180002365  mov     rbx, [rsp+78h+arg_0]
0x18000236d  add     rsp, 40h
0x180002371  pop     r15
0x180002373  pop     r14
0x180002375  pop     r13
0x180002377  pop     r12
0x180002379  pop     rdi
0x18000237a  pop     rsi
0x18000237b  pop     rbp
0x18000237c  jmp     cs:__imp_CloseHandle
```
