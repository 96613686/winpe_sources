# AlpcPort::CreateClientPort(_GUID const &,SIPC_SERVICE_BOUNDARY,uchar,uchar,SipcPrivateNamespaceAttributes const &,unsigned __int64,ushort,void *,uint *,SipcPort * *)

- ea: `0x180027214`
- end: `0x180027745`
- name: `?CreateClientPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@EEAEBUSipcPrivateNamespaceAttributes@@_KGPEAXPEAIPEAPEAVSipcPort@@@Z`
- size: `1329`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180026d6c`
- `0x18002a900`

## callees

- `0x18000c11c`
- `0x180024b24`
- `0x180024d58`
- `0x180027214`
- `0x180029b8c`
- `0x18004c88d`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x180027652`
- `ntdll!NtAlpcConnectPort` at `0x180027652`
- `ntdll!RtlAllocateHeap` at `0x1800272d7`
- `ntdll!RtlAllocateHeap` at `0x1800272d7`
- `ntdll!NtDelayExecution` at `0x1800275f6`
- `ntdll!NtDelayExecution` at `0x1800275f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027405`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002756b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002756b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027463`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027463`

## pseudocode

```c
__int64 __fastcall AlpcPort::CreateClientPort(
        LARGE_INTEGER a1,
        int a2,
        char a3,
        char a4,
        __int128 *a5,
        unsigned __int64 a6,
        __int16 a7,
        __int64 a8,
        _DWORD *a9,
        _QWORD *a10)
{
  char *Heap; // rax
  char *v12; // rsi
  _QWORD *v13; // rax
  int v14; // edi
  __int128 v15; // xmm6
  __int64 v16; // rdi
  __int128 v17; // xmm7
  __int128 v18; // xmm8
  __int128 v19; // xmm9
  __int128 v20; // xmm10
  __int128 v21; // xmm11
  __int128 v22; // xmm12
  __int128 v23; // xmm13
  __int128 v24; // xmm14
  HANDLE FileW; // rbx
  signed int v26; // eax
  __int16 *v27; // r14
  __int128 v28; // xmm1
  __int64 v29; // r8
  LARGE_INTEGER v30; // rdx
  __int128 v31; // xmm0
  __int64 v32; // rax
  signed int LastError; // eax
  const struct std::nothrow_t *v34; // rdx
  __int64 result; // rax
  LARGE_INTEGER v36; // rax
  int v37; // edi
  unsigned __int64 v38; // rdi
  size_t v39; // rbx
  DWORD BytesReturned[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-98h] BYREF
  __int64 v42; // [rsp+78h] [rbp-90h] BYREF
  LARGE_INTEGER Interval; // [rsp+80h] [rbp-88h] BYREF
  __int64 OutBuffer; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-78h]
  _OWORD v46[3]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v47[68]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v48[76]; // [rsp+11Ch] [rbp+14h] BYREF
  int InBuffer; // [rsp+168h] [rbp+60h] BYREF
  __int64 v50; // [rsp+16Ch] [rbp+64h]
  _BYTE v51[192]; // [rsp+178h] [rbp+70h] BYREF

  *a9 = 0;
  *a10 = 0;
  Interval = a1;
  LODWORD(v41) = a2;
  LOBYTE(BytesReturned[0]) = a4;
  v45 = a8;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1F8u);
  v12 = Heap;
  if ( !Heap )
    return 2147942414LL;
  *((_DWORD *)Heap + 6) = 0;
  v13 = Heap + 8;
  *((_QWORD *)v12 + 4) = 0;
  *((_QWORD *)v12 + 6) = 0;
  *((_DWORD *)v12 + 10) = 0;
  v13[1] = v13;
  *v13 = v13;
  *(_QWORD *)v12 = &AlpcPort::`vftable';
  v12[44] = 1;
  *(_OWORD *)(v12 + 56) = 0;
  *(_OWORD *)(v12 + 72) = 0;
  *((_QWORD *)v12 + 11) = 0;
  *((_QWORD *)v12 + 53) = 0;
  *((_WORD *)v12 + 29) = 40;
  *((_DWORD *)v12 + 106) = 1610612736;
  *((_WORD *)v12 + 248) = a7;
  v14 = SipcPort::Initialize((SipcPort *)v12);
  if ( v14 < 0 )
  {
LABEL_19:
    AlpcPort::~AlpcPort((AlpcPort *)v12);
    operator delete(v12, v34);
    return (unsigned int)v14;
  }
  memset(v46, 0, sizeof(v46));
  memset_0(v47, 0, sizeof(v47));
  memset_0(v48, 0, 0x44u);
  v15 = *a5;
  v16 = *((_QWORD *)a5 + 18);
  v17 = a5[1];
  BYTE2(v46[0]) = a3;
  LOBYTE(v46[0]) = 2;
  BYTE3(v46[0]) = BytesReturned[0];
  WORD2(v46[2]) = a7;
  v18 = a5[2];
  v19 = a5[3];
  v20 = a5[4];
  v21 = a5[5];
  v22 = a5[6];
  v23 = a5[7];
  v24 = a5[8];
  if ( a7 )
  {
    FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = -2147418113;
      if ( LastError < 0 )
        v14 = LastError;
      goto LABEL_19;
    }
    InBuffer = 0;
    v50 = 19;
    OutBuffer = 0;
    BytesReturned[1] = 0;
    if ( !DeviceIoControl(FileW, 0x1501E8u, &InBuffer, 0xCu, &OutBuffer, 8u, &BytesReturned[1], 0) )
    {
      v26 = GetLastError();
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      v14 = -2147418113;
      if ( v26 < 0 )
        v14 = v26;
      CloseHandle(FileW);
      goto LABEL_19;
    }
    *((_QWORD *)&v46[2] + 1) = OutBuffer;
    CloseHandle(FileW);
  }
  v27 = (__int16 *)(v12 + 56);
  v28 = v46[1];
  v29 = (unsigned int)v41;
  v30 = Interval;
  *((_OWORD *)v12 + 6) = v46[0];
  v31 = v46[2];
  *((_OWORD *)v12 + 7) = v28;
  *((_OWORD *)v12 + 8) = v31;
  *((_OWORD *)v12 + 9) = v15;
  *((_OWORD *)v12 + 10) = v17;
  *((_OWORD *)v12 + 11) = v18;
  *((_OWORD *)v12 + 12) = v19;
  *((_OWORD *)v12 + 13) = v20;
  *((_OWORD *)v12 + 14) = v21;
  *((_OWORD *)v12 + 15) = v22;
  *((_OWORD *)v12 + 16) = v23;
  *((_OWORD *)v12 + 17) = v24;
  *((_QWORD *)v12 + 36) = v16;
  *((_DWORD *)v12 + 14) = 15728840;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AlpcPortString::AlpcPortString)(v51, (LARGE_INTEGER)v30.QuadPart, v29);
  if ( a6 > 0xCCCCCCCCCCCCCCCLL || (v32 = MEMORY[0x7FFE0014] + 10 * a6, v32 <= 0) )
    v32 = 0x7FFFFFFFFFFFFFFFLL;
  v42 = v32;
  while ( 1 )
  {
    v41 = 368;
    v37 = NtAlpcConnectPort(
            v12 + 48,
            v51,
            0,
            &AlpcPort::c_clientEndpointAlpcAttributes,
            0x20000,
            v45,
            v12 + 56,
            &v41,
            0,
            0,
            &v42);
    if ( v37 >= 0 )
      break;
    if ( v37 != -1073741772 || MEMORY[0x7FFE0014] >= v42 )
    {
      v14 = v37 | 0x10000000;
      goto LABEL_19;
    }
    v36.QuadPart = MEMORY[0x7FFE0014] + 1000000LL;
    if ( v42 < MEMORY[0x7FFE0014] + 1000000LL )
      v36.QuadPart = v42;
    Interval = v36;
    NtDelayExecution(1u, &Interval);
  }
  if ( !*((_QWORD *)v12 + 6) )
  {
    v14 = v37 | 0x90000000;
    goto LABEL_19;
  }
  v38 = *v27;
  if ( *v27 < 0 )
    v38 = 0;
  BytesReturned[1] = 0;
  v39 = 4;
  if ( v38 < 4 )
    v39 = v38;
  memcpy_0(&BytesReturned[1], v12 + 96, v39);
  memset_0((char *)&BytesReturned[1] + v39, 0, 4 - v39);
  if ( v38 != 4 )
  {
    v14 = -2147418113;
    goto LABEL_19;
  }
  *a9 = BytesReturned[1];
  result = 0;
  *a10 = v12;
  return result;
}

```

## disassembly

```asm
0x180027214  mov     rax, rsp
0x180027217  push    rbp
0x180027218  push    rbx
0x180027219  push    rsi
0x18002721a  push    rdi
0x18002721b  push    r12
0x18002721d  push    r13
0x18002721f  push    r14
0x180027221  push    r15
0x180027223  lea     rbp, [rax-218h]
0x18002722a  sub     rsp, 2D8h
0x180027231  movaps  xmmword ptr [rax-58h], xmm6
0x180027235  movaps  xmmword ptr [rax-68h], xmm7
0x180027239  movaps  xmmword ptr [rax-78h], xmm8
0x18002723e  movaps  xmmword ptr [rax-88h], xmm9
0x180027246  movaps  xmmword ptr [rax-98h], xmm10
0x18002724e  movaps  xmmword ptr [rax-0A8h], xmm11
0x180027256  movaps  xmmword ptr [rax-0B8h], xmm12
0x18002725e  movaps  xmmword ptr [rax-0C8h], xmm13
0x180027266  movaps  xmmword ptr [rax-0D8h], xmm14
0x18002726e  mov     rax, cs:__security_cookie
0x180027275  xor     rax, rsp
0x180027278  mov     [rbp+210h+var_E0], rax
0x18002727f  mov     rax, [rbp+210h+arg_38]
0x180027286  xor     edi, edi
0x180027288  mov     r12, [rbp+210h+arg_40]
0x18002728f  mov     r15b, r8b
0x180027292  mov     r13, [rbp+210h+arg_48]
0x180027299  mov     r8d, 1F8h; Size
0x18002729f  mov     rbx, [rbp+210h+arg_20]
0x1800272a6  movzx   r14d, [rbp+210h+arg_30]
0x1800272ae  mov     [r12], edi
0x1800272b2  mov     [r13+0], rdi
0x1800272b6  mov     qword ptr [rsp+310h+Interval], rcx
0x1800272bb  mov     rcx, gs:60h
0x1800272c4  mov     dword ptr [rsp+310h+var_2A8], edx
0x1800272c8  xor     edx, edx; Flags
0x1800272ca  mov     byte ptr [rsp+310h+BytesReturned], r9b
0x1800272cf  mov     [rbp+210h+var_288], rax
0x1800272d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800272d7  call    cs:__imp_RtlAllocateHeap
0x1800272de  nop     dword ptr [rax+rax+00h]
0x1800272e3  mov     rsi, rax
0x1800272e6  test    rax, rax
0x1800272e9  jz      loc_1800276E5
0x1800272ef  mov     [rax+18h], edi
0x1800272f2  add     rax, 8
0x1800272f6  mov     [rsi+20h], rdi
0x1800272fa  xorps   xmm0, xmm0
0x1800272fd  mov     [rsi+30h], rdi
0x180027301  mov     rcx, rsi; this
0x180027304  mov     [rsi+28h], edi
0x180027307  mov     [rax+8], rax
0x18002730b  mov     [rax], rax
0x18002730e  lea     rax, ??_7AlpcPort@@6B@; const AlpcPort::`vftable'
0x180027315  mov     [rsi], rax
0x180027318  xor     eax, eax
0x18002731a  mov     byte ptr [rsi+2Ch], 1
0x18002731e  movups  xmmword ptr [rsi+38h], xmm0
0x180027322  movups  xmmword ptr [rsi+48h], xmm0
0x180027326  mov     [rsi+58h], rax
0x18002732a  mov     [rsi+1A8h], rax
0x180027331  mov     word ptr [rsi+3Ah], 28h ; '('
0x180027337  mov     dword ptr [rsi+1A8h], 60000000h
0x180027341  mov     [rsi+1F0h], r14w
0x180027349  call    ?Initialize@SipcPort@@IEAAJXZ; SipcPort::Initialize(void)
0x18002734e  mov     edi, eax
0x180027350  test    eax, eax
0x180027352  js      loc_18002758D
0x180027358  xor     eax, eax
0x18002735a  lea     rcx, [rbp+210h+var_240]; void *
0x18002735e  xorps   xmm0, xmm0
0x180027361  mov     dword ptr [rbp+210h+var_280], eax
0x180027364  xor     edx, edx; Val
0x180027366  mov     [rbp+210h+var_25C], rax
0x18002736a  movups  [rbp+210h+var_280+4], xmm0
0x18002736e  lea     edi, [rax+44h]
0x180027371  mov     [rbp+210h+var_254], eax
0x180027374  mov     r8d, edi; Size
0x180027377  movups  [rbp+210h+var_26C], xmm0
0x18002737b  call    memset_0
0x180027380  mov     r8d, edi; Size
0x180027383  lea     rcx, [rbp+210h+var_1FC]; void *
0x180027387  xor     edx, edx; Val
0x180027389  call    memset_0
0x18002738e  mov     al, byte ptr [rsp+310h+BytesReturned]
0x180027392  movups  xmm6, xmmword ptr [rbx]
0x180027395  mov     rdi, [rbx+90h]
0x18002739c  movups  xmm7, xmmword ptr [rbx+10h]
0x1800273a0  mov     byte ptr [rbp+210h+var_280+2], r15b
0x1800273a4  xor     r15d, r15d
0x1800273a7  mov     byte ptr [rbp+210h+var_280], 2
0x1800273ab  mov     byte ptr [rbp+210h+var_280+3], al
0x1800273ae  mov     word ptr [rbp+210h+var_25C], r14w
0x1800273b3  movups  xmm8, xmmword ptr [rbx+20h]
0x1800273b8  movups  xmm9, xmmword ptr [rbx+30h]
0x1800273bd  movups  xmm10, xmmword ptr [rbx+40h]
0x1800273c2  movups  xmm11, xmmword ptr [rbx+50h]
0x1800273c7  movups  xmm12, xmmword ptr [rbx+60h]
0x1800273cc  movups  xmm13, xmmword ptr [rbx+70h]
0x1800273d1  movups  xmm14, xmmword ptr [rbx+80h]
0x1800273d9  test    r14w, r14w
0x1800273dd  jz      loc_1800274C0
0x1800273e3  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x1800273e8  lea     r8d, [r15+3]; dwShareMode
0x1800273ec  mov     [rsp+310h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800273f1  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x1800273f8  xor     r9d, r9d; lpSecurityAttributes
0x1800273fb  mov     [rsp+310h+dwCreationDisposition], r8d; dwCreationDisposition
0x180027400  mov     edx, 0C0000000h; dwDesiredAccess
0x180027405  call    cs:__imp_CreateFileW
0x18002740c  nop     dword ptr [rax+rax+00h]
0x180027411  mov     rbx, rax
0x180027414  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027418  jz      loc_18002756B
0x18002741e  mov     [rsp+310h+lpOverlapped], r15; lpOverlapped
0x180027423  lea     rax, [rsp+310h+BytesReturned+4]
0x180027428  mov     [rsp+310h+hTemplateFile], rax; lpBytesReturned
0x18002742d  lea     r9d, [r15+0Ch]; nInBufferSize
0x180027431  lea     rax, [rbp+210h+OutBuffer]
0x180027435  mov     [rsp+310h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18002743d  lea     r8, [rbp+210h+InBuffer]; lpInBuffer
0x180027441  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; lpOutBuffer
0x180027446  mov     edx, 1501E8h; dwIoControlCode
0x18002744b  mov     [rbp+210h+InBuffer], r15d
0x18002744f  mov     rcx, rbx; hDevice
0x180027452  mov     [rbp+210h+var_1AC], 13h
0x18002745a  mov     [rbp+210h+OutBuffer], r15
0x18002745e  mov     [rsp+310h+BytesReturned+4], r15d
0x180027463  call    cs:__imp_DeviceIoControl
0x18002746a  nop     dword ptr [rax+rax+00h]
0x18002746f  test    eax, eax
0x180027471  jnz     short loc_1800274A9
0x180027473  call    cs:__imp_GetLastError
0x18002747a  nop     dword ptr [rax+rax+00h]
0x18002747f  test    eax, eax
0x180027481  jle     short loc_18002748B
0x180027483  movzx   eax, ax
0x180027486  or      eax, 80070000h
0x18002748b  test    eax, eax
0x18002748d  mov     edi, 8000FFFFh
0x180027492  mov     rcx, rbx; hObject
0x180027495  cmovs   edi, eax
0x180027498  call    cs:__imp_CloseHandle
0x18002749f  nop     dword ptr [rax+rax+00h]
0x1800274a4  jmp     loc_18002758D
0x1800274a9  mov     rax, [rbp+210h+OutBuffer]
0x1800274ad  mov     rcx, rbx; hObject
0x1800274b0  mov     [rbp+210h+var_25C+4], rax
0x1800274b4  call    cs:__imp_CloseHandle
0x1800274bb  nop     dword ptr [rax+rax+00h]
0x1800274c0  movaps  xmm0, [rbp+210h+var_280]
0x1800274c4  lea     r14, [rsi+38h]
0x1800274c8  movaps  xmm1, xmmword ptr [rbp-60h]
0x1800274cc  lea     r15, [r14+28h]
0x1800274d0  mov     r8d, dword ptr [rsp+310h+var_2A8]
0x1800274d5  lea     rcx, [rbp+210h+var_1A0]
0x1800274d9  mov     rdx, qword ptr [rsp+310h+Interval]
0x1800274de  movups  xmmword ptr [r15], xmm0
0x1800274e2  movaps  xmm0, [rbp+210h+var_26C+0Ch]
0x1800274e6  movups  xmmword ptr [r15+10h], xmm1
0x1800274eb  movups  xmmword ptr [r15+20h], xmm0
0x1800274f0  movups  xmmword ptr [r15+30h], xmm6
0x1800274f5  movups  xmmword ptr [r15+40h], xmm7
0x1800274fa  movups  xmmword ptr [r15+50h], xmm8
0x1800274ff  movups  xmmword ptr [r15+60h], xmm9
0x180027504  movups  xmmword ptr [r15+70h], xmm10
0x180027509  movups  xmmword ptr [r15+80h], xmm11
0x180027511  movups  xmmword ptr [r15+90h], xmm12
0x180027519  movups  xmmword ptr [r15+0A0h], xmm13
0x180027521  movups  xmmword ptr [r15+0B0h], xmm14
0x180027529  mov     [r15+0C0h], rdi
0x180027530  mov     dword ptr [r14], 0F000C8h
0x180027537  call    ??0AlpcPortString@@QEAA@AEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@@Z; AlpcPortString::AlpcPortString(_GUID const &,SIPC_SERVICE_BOUNDARY)
0x18002753c  mov     rax, [rbp+210h+arg_28]
0x180027543  mov     rdx, 0CCCCCCCCCCCCCCCh
0x18002754d  mov     rcx, ds:7FFE0014h
0x180027555  cmp     rax, rdx
0x180027558  ja      short loc_1800275A4
0x18002755a  lea     rax, [rax+rax*4]
0x18002755e  lea     rax, [rcx+rax*2]
0x180027562  xor     ecx, ecx
0x180027564  test    rax, rax
0x180027567  jle     short loc_1800275A6
0x180027569  jmp     short loc_1800275B0
0x18002756b  call    cs:__imp_GetLastError
0x180027572  nop     dword ptr [rax+rax+00h]
0x180027577  test    eax, eax
0x180027579  jle     short loc_180027583
0x18002757b  movzx   eax, ax
0x18002757e  or      eax, 80070000h
0x180027583  test    eax, eax
0x180027585  mov     edi, 8000FFFFh
0x18002758a  cmovs   edi, eax
0x18002758d  mov     rcx, rsi; this
0x180027590  call    ??1AlpcPort@@UEAA@XZ; AlpcPort::~AlpcPort(void)
0x180027595  mov     rcx, rsi; P
0x180027598  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002759d  mov     eax, edi
0x18002759f  jmp     loc_1800276EA
0x1800275a4  xor     ecx, ecx
0x1800275a6  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800275b0  mov     [rsp+310h+var_2A0], rax
0x1800275b5  lea     rbx, [rsi+30h]
0x1800275b9  jmp     short loc_180027604
0x1800275bb  cmp     edi, 0C0000034h
0x1800275c1  jnz     loc_1800276C1
0x1800275c7  mov     eax, 7FFE0014h
0x1800275cc  mov     rax, [rax]
0x1800275cf  mov     rcx, [rsp+310h+var_2A0]
0x1800275d4  cmp     rax, rcx
0x1800275d7  jge     loc_1800276C1
0x1800275dd  add     rax, 0F4240h
0x1800275e3  lea     rdx, [rsp+310h+Interval]; Interval
0x1800275e8  cmp     rcx, rax
0x1800275eb  cmovl   rax, rcx
0x1800275ef  mov     cl, 1; Alertable
0x1800275f1  mov     qword ptr [rsp+310h+Interval], rax
0x1800275f6  call    cs:__imp_NtDelayExecution
0x1800275fd  nop     dword ptr [rax+rax+00h]
0x180027602  xor     ecx, ecx
0x180027604  lea     rax, [rsp+310h+var_2A0]
0x180027609  mov     [rsp+310h+var_2A8], 170h
0x180027612  mov     [rsp+310h+var_2C0], rax
0x180027617  lea     r9, ?c_clientEndpointAlpcAttributes@AlpcPort@@0U_ALPC_PORT_ATTRIBUTES@@B; _ALPC_PORT_ATTRIBUTES const AlpcPort::c_clientEndpointAlpcAttributes
0x18002761e  mov     [rsp+310h+var_2C8], rcx
0x180027623  lea     rax, [rsp+310h+var_2A8]
0x180027628  mov     [rsp+310h+var_2D0], rcx
0x18002762d  lea     rdx, [rbp+210h+var_1A0]
0x180027631  mov     [rsp+310h+lpOverlapped], rax
0x180027636  xor     r8d, r8d
0x180027639  mov     rax, [rbp+210h+var_288]
0x18002763d  mov     rcx, rbx
0x180027640  mov     [rsp+310h+hTemplateFile], r14
0x180027645  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rax
0x18002764a  mov     [rsp+310h+dwCreationDisposition], 20000h
0x180027652  call    cs:__imp_NtAlpcConnectPort
0x180027659  nop     dword ptr [rax+rax+00h]
0x18002765e  xor     ecx, ecx
0x180027660  mov     edi, eax
0x180027662  test    eax, eax
0x180027664  js      loc_1800275BB
0x18002766a  cmp     [rbx], rcx
0x18002766d  jz      short loc_1800276DA
0x18002766f  cmp     [r14], cx
0x180027673  mov     rdx, r15; Src
0x180027676  movsx   rdi, word ptr [r14]
0x18002767a  lea     r14d, [rcx+4]
0x18002767e  cmovl   rdi, rcx
0x180027682  mov     [rsp+310h+BytesReturned+4], ecx
0x180027686  cmp     rdi, r14
0x180027689  lea     rcx, [rsp+310h+BytesReturned+4]; void *
0x18002768e  mov     ebx, r14d
0x180027691  cmovb   rbx, rdi
0x180027695  mov     r8, rbx; Size
0x180027698  call    memcpy_0
0x18002769d  mov     r8d, r14d
0x1800276a0  lea     rcx, [rsp+310h+BytesReturned+4]
0x1800276a5  sub     r8, rbx; Size
0x1800276a8  add     rcx, rbx; void *
0x1800276ab  xor     edx, edx; Val
0x1800276ad  call    memset_0
0x1800276b2  cmp     rdi, r14
0x1800276b5  jz      short loc_1800276CA
0x1800276b7  mov     edi, 8000FFFFh
0x1800276bc  jmp     loc_18002758D
0x1800276c1  bts     edi, 1Ch
0x1800276c5  jmp     loc_18002758D
0x1800276ca  mov     eax, [rsp+310h+BytesReturned+4]
0x1800276ce  mov     [r12], eax
0x1800276d2  xor     eax, eax
0x1800276d4  mov     [r13+0], rsi
0x1800276d8  jmp     short loc_1800276EA
0x1800276da  or      edi, 90000000h
0x1800276e0  jmp     loc_18002758D
0x1800276e5  mov     eax, 8007000Eh
0x1800276ea  mov     rcx, [rbp+210h+var_E0]
0x1800276f1  xor     rcx, rsp; StackCookie
0x1800276f4  call    __security_check_cookie
0x1800276f9  lea     r11, [rsp+310h+var_38]
0x180027701  movaps  xmm6, xmmword ptr [r11-18h]
0x180027706  movaps  xmm7, xmmword ptr [r11-28h]
0x18002770b  movaps  xmm8, xmmword ptr [r11-38h]
0x180027710  movaps  xmm9, xmmword ptr [r11-48h]
0x180027715  movaps  xmm10, xmmword ptr [r11-58h]
0x18002771a  movaps  xmm11, xmmword ptr [r11-68h]
0x18002771f  movaps  xmm12, xmmword ptr [r11-78h]
0x180027724  movaps  xmm13, xmmword ptr [r11-88h]
0x18002772c  movaps  xmm14, xmmword ptr [r11-98h]
0x180027734  mov     rsp, r11
0x180027737  pop     r15
0x180027739  pop     r14
0x18002773b  pop     r13
0x18002773d  pop     r12
0x18002773f  pop     rdi
0x180027740  pop     rsi
0x180027741  pop     rbx
0x180027742  pop     rbp
0x180027743  retn
```
