# XvmmPort::CreateClientPort(_GUID const &,uchar,uchar,unsigned __int64,uint *,SipcPort * *)

- ea: `0x18002774c`
- end: `0x180027a39`
- name: `?CreateClientPort@XvmmPort@@SAJAEBU_GUID@@EE_KPEAIPEAPEAVSipcPort@@@Z`
- size: `749`
- prototype: `static int(const struct _GUID *, unsigned __int8, unsigned __int8, unsigned __int64, unsigned int *, struct SipcPort **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180026d6c`

## callees

- `0x18000c11c`
- `0x180025278`
- `0x18002774c`
- `0x180029b8c`
- `0x18002b60c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002789e`
- `ntdll!RtlAllocateHeap` at `0x18002789e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027826`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027826`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800277bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800277bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002794d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002795f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002794d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002795f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279c6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027877`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027877`

## pseudocode

```c
int __fastcall XvmmPort::CreateClientPort(
        const struct _GUID *a1,
        unsigned __int8 a2,
        unsigned __int8 a3,
        unsigned __int64 a4,
        unsigned int *OutBuffer,
        struct SipcPort **a6)
{
  unsigned int *v6; // r14
  LPCWSTR *v7; // rsi
  struct SipcPort **v8; // r15
  HANDLE FileW; // rdi
  int result; // eax
  XvmmPort *Heap; // rax
  XvmmPort *v14; // rbx
  HANDLE v15; // rdx
  __int16 v16; // r8
  __int128 v17; // xmm0
  int started; // edi
  XvmmPort *v19; // rcx
  const struct std::nothrow_t *v20; // rdx
  HANDLE v21; // rcx
  int v22; // ebx
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-10h] BYREF
  HANDLE InBuffer; // [rsp+48h] [rbp-8h] BYREF

  v6 = OutBuffer;
  v7 = (LPCWSTR *)&XvmmPort::c_driverPaths;
  v8 = a6;
  *OutBuffer = 0;
  *v8 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(*v7, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    result = GetLastError();
    if ( result != 2 )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( ++v7 == (LPCWSTR *)&AlpcPort::c_serverObjectAttributes )
      return -2147024894;
  }
  InBuffer = CreateEventW(0, 0, 0, 0);
  if ( !InBuffer
    || (LOWORD(OutBuffer) = 0,
        BytesReturned = 0,
        !DeviceIoControl(FileW, 0x15008Cu, &InBuffer, 8u, &OutBuffer, 2u, &BytesReturned, 0)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v22 = -2147418113;
    if ( LastError < 0 )
      v22 = LastError;
    if ( InBuffer )
    {
      CloseHandle(InBuffer);
      InBuffer = 0;
    }
    goto LABEL_27;
  }
  Heap = (XvmmPort *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
  v14 = Heap;
  if ( !Heap )
  {
    if ( InBuffer )
    {
      CloseHandle(InBuffer);
      InBuffer = 0;
    }
    v22 = -2147024882;
LABEL_27:
    CloseHandle(FileW);
    return v22;
  }
  v15 = InBuffer;
  v16 = (__int16)OutBuffer;
  *((_QWORD *)Heap + 4) = 0;
  *((_DWORD *)Heap + 6) = 0;
  *((_QWORD *)Heap + 2) = (char *)Heap + 8;
  *((_QWORD *)Heap + 1) = (char *)Heap + 8;
  *((_QWORD *)Heap + 6) = FileW;
  *((_QWORD *)Heap + 7) = v15;
  *((_DWORD *)Heap + 10) = 0;
  *((_BYTE *)Heap + 44) = 1;
  *(_QWORD *)Heap = &XvmmPort::`vftable';
  v17 = (__int128)*a1;
  *((_WORD *)Heap + 40) = v16;
  *((_BYTE *)Heap + 82) = 0;
  *((_OWORD *)Heap + 4) = v17;
  InBuffer = 0;
  started = SipcPort::Initialize(Heap);
  v19 = v14;
  if ( started < 0 )
  {
LABEL_12:
    XvmmPort::~XvmmPort(v19);
    operator delete(v14, v20);
    if ( InBuffer )
    {
      CloseHandle(InBuffer);
      InBuffer = 0;
    }
    CloseHandle(0);
    return started;
  }
  LODWORD(a6) = 0;
  started = XvmmPort::StartXboxProxy(v14, a2, a3, a4, (unsigned int *)&a6);
  if ( started < 0 )
  {
    v19 = v14;
    goto LABEL_12;
  }
  v21 = InBuffer;
  *v6 = (unsigned int)a6;
  *v8 = v14;
  if ( v21 )
  {
    CloseHandle(v21);
    InBuffer = 0;
  }
  CloseHandle(0);
  return 0;
}

```

## disassembly

```asm
0x18002774c  mov     [rsp-38h+arg_10], rbx
0x180027751  mov     [rsp-38h+arg_8], dl
0x180027755  mov     [rsp-38h+arg_0], rcx
0x18002775a  push    rbp
0x18002775b  push    rsi
0x18002775c  push    rdi
0x18002775d  push    r12
0x18002775f  push    r13
0x180027761  push    r14
0x180027763  push    r15
0x180027765  mov     rbp, rsp
0x180027768  sub     rsp, 50h
0x18002776c  mov     r14, [rbp+OutBuffer]
0x180027770  lea     rsi, ?c_driverPaths@XvmmPort@@0QBQEBGB; ushort const * const near * const XvmmPort::c_driverPaths
0x180027777  mov     r15, [rbp+arg_28]
0x18002777b  mov     r12, r9
0x18002777e  mov     r13b, r8b
0x180027781  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027785  mov     dword ptr [r14], 0
0x18002778c  mov     qword ptr [r15], 0
0x180027793  mov     rcx, [rsi]; lpFileName
0x180027796  xor     r9d, r9d; lpSecurityAttributes
0x180027799  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800277a2  mov     edx, 0C0000000h; dwDesiredAccess
0x1800277a7  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800277af  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x1800277b7  lea     r8d, [r9+3]; dwShareMode
0x1800277bb  call    cs:__imp_CreateFileW
0x1800277c2  nop     dword ptr [rax+rax+00h]
0x1800277c7  mov     rdi, rax
0x1800277ca  cmp     rax, rbx
0x1800277cd  jz      short loc_1800277ED
0x1800277cf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800277d3  jz      short loc_1800277E4
0x1800277d5  mov     rcx, rbx; hObject
0x1800277d8  call    cs:__imp_CloseHandle
0x1800277df  nop     dword ptr [rax+rax+00h]
0x1800277e4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800277e8  jnz     short loc_18002781C
0x1800277ea  mov     rbx, rdi
0x1800277ed  call    cs:__imp_GetLastError
0x1800277f4  nop     dword ptr [rax+rax+00h]
0x1800277f9  cmp     eax, 2
0x1800277fc  jnz     loc_180027A14
0x180027802  add     rsi, 8
0x180027806  lea     rax, ?c_serverObjectAttributes@AlpcPort@@0U_OBJECT_ATTRIBUTES@@B; _OBJECT_ATTRIBUTES const AlpcPort::c_serverObjectAttributes
0x18002780d  cmp     rsi, rax
0x180027810  jnz     short loc_180027793
0x180027812  mov     eax, 80070002h
0x180027817  jmp     loc_180027A20
0x18002781c  xor     r9d, r9d; lpName
0x18002781f  xor     r8d, r8d; bInitialState
0x180027822  xor     edx, edx; bManualReset
0x180027824  xor     ecx, ecx; lpEventAttributes
0x180027826  call    cs:__imp_CreateEventW
0x18002782d  nop     dword ptr [rax+rax+00h]
0x180027832  xor     esi, esi
0x180027834  mov     [rbp+InBuffer], rax
0x180027838  test    rax, rax
0x18002783b  jz      loc_1800279C6
0x180027841  mov     [rsp+50h+lpOverlapped], rsi; lpOverlapped
0x180027846  lea     rax, [rbp+BytesReturned]
0x18002784a  mov     [rsp+50h+hTemplateFile], rax; lpBytesReturned
0x18002784f  lea     r9d, [rsi+8]; nInBufferSize
0x180027853  lea     rax, [rbp+OutBuffer]
0x180027857  mov     [rsp+50h+dwFlagsAndAttributes], 2; nOutBufferSize
0x18002785f  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180027863  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; lpOutBuffer
0x180027868  mov     edx, 15008Ch; dwIoControlCode
0x18002786d  mov     word ptr [rbp+OutBuffer], si
0x180027871  mov     rcx, rdi; hDevice
0x180027874  mov     [rbp+BytesReturned], esi
0x180027877  call    cs:__imp_DeviceIoControl
0x18002787e  nop     dword ptr [rax+rax+00h]
0x180027883  test    eax, eax
0x180027885  jz      loc_1800279C6
0x18002788b  mov     rcx, gs:60h
0x180027894  lea     r8d, [rsi+58h]; Size
0x180027898  xor     edx, edx; Flags
0x18002789a  mov     rcx, [rcx+30h]; HeapHandle
0x18002789e  call    cs:__imp_RtlAllocateHeap
0x1800278a5  nop     dword ptr [rax+rax+00h]
0x1800278aa  mov     rbx, rax
0x1800278ad  test    rax, rax
0x1800278b0  jz      loc_1800279A6
0x1800278b6  mov     rdx, [rbp+InBuffer]
0x1800278ba  lea     rcx, [rax+8]
0x1800278be  movzx   r8d, word ptr [rbp+OutBuffer]
0x1800278c3  mov     [rax+20h], rsi
0x1800278c7  mov     [rcx+10h], esi
0x1800278ca  mov     [rcx+8], rcx
0x1800278ce  mov     [rcx], rcx
0x1800278d1  mov     rcx, rbx; this
0x1800278d4  mov     [rbx+30h], rdi
0x1800278d8  mov     [rbx+38h], rdx
0x1800278dc  mov     [rax+28h], esi
0x1800278df  mov     byte ptr [rax+2Ch], 1
0x1800278e3  lea     rax, ??_7XvmmPort@@6B@; const XvmmPort::`vftable'
0x1800278ea  mov     [rbx], rax
0x1800278ed  mov     rax, [rbp+arg_0]
0x1800278f1  movups  xmm0, xmmword ptr [rax]
0x1800278f4  mov     [rbx+50h], r8w
0x1800278f9  mov     [rbx+52h], sil
0x1800278fd  movdqu  xmmword ptr [rbx+40h], xmm0
0x180027902  mov     [rbp+InBuffer], rsi
0x180027906  call    ?Initialize@SipcPort@@IEAAJXZ; SipcPort::Initialize(void)
0x18002790b  mov     edi, eax
0x18002790d  mov     rcx, rbx; this
0x180027910  test    eax, eax
0x180027912  js      short loc_180027937
0x180027914  mov     dl, [rbp+arg_8]; unsigned __int8
0x180027917  lea     rax, [rbp+arg_28]
0x18002791b  mov     r9, r12; unsigned __int64
0x18002791e  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; unsigned int *
0x180027923  mov     r8b, r13b; unsigned __int8
0x180027926  mov     dword ptr [rbp+arg_28], esi
0x180027929  call    ?StartXboxProxy@XvmmPort@@AEAAJEE_KPEAI@Z; XvmmPort::StartXboxProxy(uchar,uchar,unsigned __int64,uint *)
0x18002792e  mov     edi, eax
0x180027930  test    eax, eax
0x180027932  jns     short loc_180027972
0x180027934  mov     rcx, rbx; this
0x180027937  call    ??1XvmmPort@@UEAA@XZ; XvmmPort::~XvmmPort(void)
0x18002793c  mov     rcx, rbx; P
0x18002793f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027944  mov     rcx, [rbp+InBuffer]; hObject
0x180027948  test    rcx, rcx
0x18002794b  jz      short loc_18002795D
0x18002794d  call    cs:__imp_CloseHandle
0x180027954  nop     dword ptr [rax+rax+00h]
0x180027959  mov     [rbp+InBuffer], rsi
0x18002795d  xor     ecx, ecx; hObject
0x18002795f  call    cs:__imp_CloseHandle
0x180027966  nop     dword ptr [rax+rax+00h]
0x18002796b  mov     eax, edi
0x18002796d  jmp     loc_180027A20
0x180027972  mov     rcx, [rbp+InBuffer]; hObject
0x180027976  mov     eax, dword ptr [rbp+arg_28]
0x180027979  mov     [r14], eax
0x18002797c  mov     [r15], rbx
0x18002797f  test    rcx, rcx
0x180027982  jz      short loc_180027994
0x180027984  call    cs:__imp_CloseHandle
0x18002798b  nop     dword ptr [rax+rax+00h]
0x180027990  mov     [rbp+InBuffer], rsi
0x180027994  xor     ecx, ecx; hObject
0x180027996  call    cs:__imp_CloseHandle
0x18002799d  nop     dword ptr [rax+rax+00h]
0x1800279a2  xor     eax, eax
0x1800279a4  jmp     short loc_180027A20
0x1800279a6  mov     rcx, [rbp+InBuffer]; hObject
0x1800279aa  test    rcx, rcx
0x1800279ad  jz      short loc_1800279BF
0x1800279af  call    cs:__imp_CloseHandle
0x1800279b6  nop     dword ptr [rax+rax+00h]
0x1800279bb  mov     [rbp+InBuffer], rsi
0x1800279bf  mov     ebx, 8007000Eh
0x1800279c4  jmp     short loc_180027A01
0x1800279c6  call    cs:__imp_GetLastError
0x1800279cd  nop     dword ptr [rax+rax+00h]
0x1800279d2  test    eax, eax
0x1800279d4  jle     short loc_1800279DE
0x1800279d6  movzx   eax, ax
0x1800279d9  or      eax, 80070000h
0x1800279de  mov     rcx, [rbp+InBuffer]; hObject
0x1800279e2  test    eax, eax
0x1800279e4  mov     ebx, 8000FFFFh
0x1800279e9  cmovs   ebx, eax
0x1800279ec  test    rcx, rcx
0x1800279ef  jz      short loc_180027A01
0x1800279f1  call    cs:__imp_CloseHandle
0x1800279f8  nop     dword ptr [rax+rax+00h]
0x1800279fd  mov     [rbp+InBuffer], rsi
0x180027a01  mov     rcx, rdi; hObject
0x180027a04  call    cs:__imp_CloseHandle
0x180027a0b  nop     dword ptr [rax+rax+00h]
0x180027a10  mov     eax, ebx
0x180027a12  jmp     short loc_180027A20
0x180027a14  test    eax, eax
0x180027a16  jle     short loc_180027A20
0x180027a18  movzx   eax, ax
0x180027a1b  or      eax, 80070000h
0x180027a20  mov     rbx, [rsp+50h+arg_10]
0x180027a28  add     rsp, 50h
0x180027a2c  pop     r15
0x180027a2e  pop     r14
0x180027a30  pop     r13
0x180027a32  pop     r12
0x180027a34  pop     rdi
0x180027a35  pop     rsi
0x180027a36  pop     rbp
0x180027a37  retn
```
