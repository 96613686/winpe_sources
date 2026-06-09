# AlpcSection::Create(AlpcPort const *,unsigned __int64,SipcSectionId const &,void *,AlpcSection * *)

- ea: `0x180026448`
- end: `0x18002683f`
- name: `?Create@AlpcSection@@SAJPEBVAlpcPort@@_KAEBVSipcSectionId@@PEAXPEAPEAV1@@Z`
- size: `1015`
- prototype: `static int(const struct AlpcPort *, unsigned __int64, const struct SipcSectionId *, void *, struct AlpcSection **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180027c80`

## callees

- `0x180026448`
- `0x18002a5a0`
- `0x18002b9d4`
- `0x18004c8a5`

## import_xrefs

- `ntdll!NtAlpcCreateSectionView` at `0x1800266aa`
- `ntdll!NtAlpcCreateSectionView` at `0x1800266aa`
- `ntdll!NtQueryLicenseValue` at `0x180026545`
- `ntdll!NtQueryLicenseValue` at `0x180026545`
- `ntdll!NtAlpcCreatePortSection` at `0x180026675`
- `ntdll!NtAlpcCreatePortSection` at `0x180026675`
- `ntdll!RtlInitUnicodeString` at `0x180026520`
- `ntdll!RtlInitUnicodeString` at `0x180026520`
- `ntdll!RtlAllocateHeap` at `0x180026730`
- `ntdll!RtlAllocateHeap` at `0x180026730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026483`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026589`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026589`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264ac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002663f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026807`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002681c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002663f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800267c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026807`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002681c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800265ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800265ee`

## pseudocode

```c
__int64 __fastcall AlpcSection::Create(
        const struct AlpcPort *a1,
        unsigned __int64 a2,
        const struct SipcSectionId *a3,
        void *a4,
        struct AlpcSection **a5)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  signed int LastError; // eax
  int v11; // esi
  unsigned __int64 v13; // r14
  void *v14; // rbx
  PWSTR Buffer; // r15
  HANDLE FileW; // rdi
  signed int v17; // eax
  void *v18; // rcx
  int PortSection; // eax
  int v20; // eax
  int v21; // edi
  unsigned __int64 i; // rcx
  unsigned __int64 v23; // rdi
  char *Heap; // rax
  HANDLE v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r9
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  unsigned int v30; // edi
  unsigned __int64 InBuffer; // [rsp+40h] [rbp-41h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-39h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-29h] BYREF
  __int128 v35; // [rsp+68h] [rbp-19h] BYREF
  __int128 v36; // [rsp+78h] [rbp-9h] BYREF

  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    goto LABEL_2;
  LODWORD(InBuffer) = 0;
  BytesReturned = 0;
  v13 = (a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v14 = 0;
  DestinationString = 0;
  Buffer = 0;
  RtlInitUnicodeString(&DestinationString, L"Kernel-ProductInfo");
  if ( (int)NtQueryLicenseValue(&DestinationString, 0, &InBuffer, 4, &BytesReturned) >= 0 && (_DWORD)InBuffer == 192 )
  {
    FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_2:
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = -2147418113;
      if ( LastError < 0 )
        v11 = LastError;
      goto LABEL_6;
    }
    BytesReturned = 0;
    InBuffer = (v13 + 65575) & 0xFFFFFFFFFFFF0000uLL;
    DestinationString = 0;
    if ( !DeviceIoControl(FileW, 0x15026Cu, &InBuffer, 8u, &DestinationString, 0x10u, &BytesReturned, 0) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v11 = -2147418113;
      v18 = FileW;
      if ( v17 < 0 )
        v11 = v17;
      goto LABEL_17;
    }
    v14 = *(void **)&DestinationString.Length;
    Buffer = DestinationString.Buffer;
    CloseHandle(FileW);
  }
  v35 = 0;
  v36 = 0;
  PortSection = NtAlpcCreatePortSection(TargetHandle, 0, v14, v13 + 40, (char *)&v35 + 8, (char *)&v36 + 8);
  if ( PortSection < 0 )
  {
    v20 = PortSection | 0x10000000;
    v11 = -2147418113;
    if ( v20 < 0 )
      v11 = v20;
    goto LABEL_22;
  }
  v21 = NtAlpcCreateSectionView(TargetHandle, 0, &v35);
  if ( v21 >= 0 )
  {
    for ( i = 0; i < a2; i += 4096LL )
      *(_BYTE *)(v36 + i) = 0;
    memset_0((void *)(a2 + v36), 204, *((_QWORD *)&v36 + 1) - a2);
    v23 = v36 + ((*((_QWORD *)&v36 + 1) - 40LL) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)v23 = a2;
    *(_OWORD *)(v23 + 8) = *(_OWORD *)a3;
    *(_OWORD *)(v23 + 24) = *((_OWORD *)a3 + 1);
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    if ( Heap )
    {
      v25 = TargetHandle;
      v26 = *((_QWORD *)&v36 + 1);
      v27 = *((_QWORD *)&v35 + 1);
      *((_QWORD *)Heap + 4) = v36;
      *(_QWORD *)Heap = &SipcSection::`vftable';
      *((_QWORD *)Heap + 5) = v26;
      *((_QWORD *)Heap + 3) = a1;
      *((_QWORD *)Heap + 6) = *(_QWORD *)v23;
      v28 = *(_OWORD *)(v23 + 8);
      *a5 = (struct AlpcSection *)Heap;
      *(_OWORD *)(Heap + 56) = v28;
      v29 = *(_OWORD *)(v23 + 24);
      *(_QWORD *)Heap = &AlpcSection::`vftable';
      *((_DWORD *)Heap + 22) = 0;
      *(_OWORD *)(Heap + 72) = v29;
      *((_QWORD *)Heap + 12) = v25;
      *((_QWORD *)Heap + 13) = v27;
      *((_QWORD *)Heap + 14) = Buffer;
      TargetHandle = 0;
      SipcSection::ProtectExtraMemory((SipcSection *)Heap);
      if ( v14 )
        CloseHandle(v14);
      if ( TargetHandle )
        CloseHandle(TargetHandle);
      return 0;
    }
    *a5 = 0;
    v21 = -1073741801;
  }
  v11 = AlpcSection::Unmap((void *)v36, a4, *((void **)&v35 + 1));
  if ( v11 < 0 )
  {
LABEL_22:
    if ( !v14 )
      goto LABEL_6;
    v18 = v14;
LABEL_17:
    CloseHandle(v18);
LABEL_6:
    if ( TargetHandle )
      CloseHandle(TargetHandle);
    return (unsigned int)v11;
  }
  v30 = v21 | 0x10000000;
  if ( v14 )
    CloseHandle(v14);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  return v30;
}

```

## disassembly

```asm
0x180026448  mov     [rsp-8+arg_10], r8
0x18002644d  push    rbp
0x18002644e  push    rbx
0x18002644f  push    rsi
0x180026450  push    rdi
0x180026451  push    r12
0x180026453  push    r13
0x180026455  push    r14
0x180026457  push    r15
0x180026459  lea     rbp, [rsp-17h]
0x18002645e  sub     rsp, 98h
0x180026465  xor     edi, edi
0x180026467  mov     r12, r9
0x18002646a  mov     [rbp+4Fh+TargetHandle], rdi
0x18002646e  mov     rsi, rdx
0x180026471  mov     r13, rcx
0x180026474  call    cs:__imp_GetCurrentProcess
0x18002647b  nop     dword ptr [rax+rax+00h]
0x180026480  mov     rbx, rax
0x180026483  call    cs:__imp_GetCurrentProcess
0x18002648a  nop     dword ptr [rax+rax+00h]
0x18002648f  mov     [rsp+0D0h+dwOptions], 2; dwOptions
0x180026497  lea     r9, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x18002649b  mov     rcx, rax; hSourceProcessHandle
0x18002649e  mov     [rsp+0D0h+bInheritHandle], edi; bInheritHandle
0x1800264a2  mov     r8, rbx; hTargetProcessHandle
0x1800264a5  mov     [rsp+0D0h+dwDesiredAccess], edi; dwDesiredAccess
0x1800264a9  mov     rdx, r12; hSourceHandle
0x1800264ac  call    cs:__imp_DuplicateHandle
0x1800264b3  nop     dword ptr [rax+rax+00h]
0x1800264b8  test    eax, eax
0x1800264ba  jnz     short loc_1800264FA
0x1800264bc  call    cs:__imp_GetLastError
0x1800264c3  nop     dword ptr [rax+rax+00h]
0x1800264c8  test    eax, eax
0x1800264ca  jle     short loc_1800264D4
0x1800264cc  movzx   eax, ax
0x1800264cf  or      eax, 80070000h
0x1800264d4  test    eax, eax
0x1800264d6  mov     esi, 8000FFFFh
0x1800264db  cmovs   esi, eax
0x1800264de  mov     rcx, [rbp+4Fh+TargetHandle]; hObject
0x1800264e2  test    rcx, rcx
0x1800264e5  jz      short loc_1800264F3
0x1800264e7  call    cs:__imp_CloseHandle
0x1800264ee  nop     dword ptr [rax+rax+00h]
0x1800264f3  mov     eax, esi
0x1800264f5  jmp     loc_18002682A
0x1800264fa  xorps   xmm0, xmm0
0x1800264fd  mov     dword ptr [rbp+4Fh+InBuffer], edi
0x180026500  lea     r14, [rsi+7]
0x180026504  mov     [rbp+4Fh+BytesReturned], edi
0x180026507  lea     rdx, SourceString; "Kernel-ProductInfo"
0x18002650e  and     r14, 0FFFFFFFFFFFFFFF8h
0x180026512  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180026516  mov     rbx, rdi
0x180026519  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18002651d  mov     r15, rdi
0x180026520  call    cs:__imp_RtlInitUnicodeString
0x180026527  nop     dword ptr [rax+rax+00h]
0x18002652c  lea     rax, [rbp+4Fh+BytesReturned]
0x180026530  mov     r9d, 4
0x180026536  lea     r8, [rbp+4Fh+InBuffer]
0x18002653a  mov     qword ptr [rsp+0D0h+dwDesiredAccess], rax
0x18002653f  xor     edx, edx
0x180026541  lea     rcx, [rbp+4Fh+DestinationString]
0x180026545  call    cs:__imp_NtQueryLicenseValue
0x18002654c  nop     dword ptr [rax+rax+00h]
0x180026551  test    eax, eax
0x180026553  js      loc_18002664B
0x180026559  cmp     dword ptr [rbp+4Fh+InBuffer], 0C0h
0x180026560  jnz     loc_18002664B
0x180026566  mov     qword ptr [rsp+0D0h+dwOptions], rdi; hTemplateFile
0x18002656b  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x180026572  mov     r8d, 3; dwShareMode
0x180026578  mov     [rsp+0D0h+bInheritHandle], edi; dwFlagsAndAttributes
0x18002657c  xor     r9d, r9d; lpSecurityAttributes
0x18002657f  mov     [rsp+0D0h+dwDesiredAccess], r8d; dwCreationDisposition
0x180026584  mov     edx, 0C0000000h; dwDesiredAccess
0x180026589  call    cs:__imp_CreateFileW
0x180026590  nop     dword ptr [rax+rax+00h]
0x180026595  mov     rdi, rax
0x180026598  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002659c  jz      loc_1800264BC
0x1800265a2  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x1800265a7  lea     rax, [r14+10027h]
0x1800265ae  and     rax, 0FFFFFFFFFFFF0000h
0x1800265b4  mov     [rbp+4Fh+BytesReturned], ebx
0x1800265b7  mov     [rbp+4Fh+InBuffer], rax
0x1800265bb  lea     r8, [rbp+4Fh+InBuffer]; lpInBuffer
0x1800265bf  lea     rax, [rbp+4Fh+BytesReturned]
0x1800265c3  xorps   xmm0, xmm0
0x1800265c6  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpBytesReturned
0x1800265cb  mov     r9d, 8; nInBufferSize
0x1800265d1  lea     rax, [rbp+4Fh+DestinationString]
0x1800265d5  mov     [rsp+0D0h+bInheritHandle], 10h; nOutBufferSize
0x1800265dd  mov     edx, 15026Ch; dwIoControlCode
0x1800265e2  mov     qword ptr [rsp+0D0h+dwDesiredAccess], rax; lpOutBuffer
0x1800265e7  mov     rcx, rdi; hDevice
0x1800265ea  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800265ee  call    cs:__imp_DeviceIoControl
0x1800265f5  nop     dword ptr [rax+rax+00h]
0x1800265fa  test    eax, eax
0x1800265fc  jnz     short loc_180026634
0x1800265fe  call    cs:__imp_GetLastError
0x180026605  nop     dword ptr [rax+rax+00h]
0x18002660a  test    eax, eax
0x18002660c  jle     short loc_180026616
0x18002660e  movzx   eax, ax
0x180026611  or      eax, 80070000h
0x180026616  test    eax, eax
0x180026618  mov     esi, 8000FFFFh
0x18002661d  mov     rcx, rdi; hObject
0x180026620  cmovs   esi, eax
0x180026623  call    cs:__imp_CloseHandle
0x18002662a  nop     dword ptr [rax+rax+00h]
0x18002662f  jmp     loc_1800264DE
0x180026634  mov     rbx, qword ptr [rbp+4Fh+DestinationString.Length]
0x180026638  mov     rcx, rdi; hObject
0x18002663b  mov     r15, [rbp+4Fh+DestinationString.Buffer]
0x18002663f  call    cs:__imp_CloseHandle
0x180026646  nop     dword ptr [rax+rax+00h]
0x18002664b  mov     rcx, [rbp+4Fh+TargetHandle]
0x18002664f  lea     rax, [rbp+4Fh+var_50]
0x180026653  mov     qword ptr [rsp+0D0h+bInheritHandle], rax
0x180026658  lea     r9, [r14+28h]
0x18002665c  xorps   xmm0, xmm0
0x18002665f  lea     rax, [rbp+4Fh+var_60]
0x180026663  mov     r8, rbx
0x180026666  mov     qword ptr [rsp+0D0h+dwDesiredAccess], rax
0x18002666b  xor     edx, edx
0x18002666d  movups  xmmword ptr [rbp-19h], xmm0
0x180026671  movups  xmmword ptr [rbp-9], xmm0
0x180026675  call    cs:__imp_NtAlpcCreatePortSection
0x18002667c  nop     dword ptr [rax+rax+00h]
0x180026681  test    eax, eax
0x180026683  jns     short loc_1800266A0
0x180026685  or      eax, 10000000h
0x18002668a  mov     esi, 8000FFFFh
0x18002668f  cmovl   esi, eax
0x180026692  test    rbx, rbx
0x180026695  jz      loc_1800264DE
0x18002669b  mov     rcx, rbx
0x18002669e  jmp     short loc_180026623
0x1800266a0  mov     rcx, [rbp+4Fh+TargetHandle]
0x1800266a4  lea     r8, [rbp+4Fh+var_68]
0x1800266a8  xor     edx, edx
0x1800266aa  call    cs:__imp_NtAlpcCreateSectionView
0x1800266b1  nop     dword ptr [rax+rax+00h]
0x1800266b6  mov     edi, eax
0x1800266b8  test    eax, eax
0x1800266ba  js      loc_1800267E1
0x1800266c0  mov     r14, [rbp+4Fh+arg_20]
0x1800266c4  xor     ecx, ecx
0x1800266c6  test    rsi, rsi
0x1800266c9  jz      short loc_1800266DF
0x1800266cb  mov     rax, [rbp+4Fh+var_58]
0x1800266cf  mov     byte ptr [rax+rcx], 0
0x1800266d3  add     rcx, 1000h
0x1800266da  cmp     rcx, rsi
0x1800266dd  jb      short loc_1800266CB
0x1800266df  mov     r8, [rbp+4Fh+var_50]
0x1800266e3  mov     edx, 0CCh; Val
0x1800266e8  mov     rcx, [rbp+4Fh+var_58]
0x1800266ec  sub     r8, rsi; Size
0x1800266ef  add     rcx, rsi; void *
0x1800266f2  call    memset_0
0x1800266f7  mov     rdi, [rbp+4Fh+var_50]
0x1800266fb  xor     edx, edx; Flags
0x1800266fd  mov     rax, [rbp+4Fh+arg_10]
0x180026701  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180026705  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180026709  add     rdi, [rbp+4Fh+var_58]
0x18002670d  lea     r8d, [rdx+78h]; Size
0x180026711  mov     [rdi], rsi
0x180026714  movups  xmm0, xmmword ptr [rax]
0x180026717  movups  xmmword ptr [rdi+8], xmm0
0x18002671b  movups  xmm1, xmmword ptr [rax+10h]
0x18002671f  movups  xmmword ptr [rdi+18h], xmm1
0x180026723  mov     rcx, gs:60h
0x18002672c  mov     rcx, [rcx+30h]; HeapHandle
0x180026730  call    cs:__imp_RtlAllocateHeap
0x180026737  nop     dword ptr [rax+rax+00h]
0x18002673c  xor     esi, esi
0x18002673e  test    rax, rax
0x180026741  jz      loc_1800267D9
0x180026747  mov     rcx, [rbp+4Fh+var_58]
0x18002674b  lea     r10, ??_7SipcSection@@6B@; const SipcSection::`vftable'
0x180026752  mov     r8, [rbp+4Fh+TargetHandle]
0x180026756  mov     rdx, [rbp+4Fh+var_50]
0x18002675a  mov     r9, [rbp+4Fh+var_60]
0x18002675e  mov     [rax+20h], rcx
0x180026762  mov     [rax], r10
0x180026765  mov     [rax+28h], rdx
0x180026769  mov     [rax+18h], r13
0x18002676d  mov     rcx, [rdi]
0x180026770  mov     [rax+30h], rcx
0x180026774  lea     rcx, ??_7AlpcSection@@6B@; const AlpcSection::`vftable'
0x18002677b  movups  xmm0, xmmword ptr [rdi+8]
0x18002677f  mov     [r14], rax
0x180026782  movups  xmmword ptr [rax+38h], xmm0
0x180026786  movups  xmm1, xmmword ptr [rdi+18h]
0x18002678a  mov     [rax], rcx
0x18002678d  mov     rcx, rax; this
0x180026790  mov     [rax+58h], esi
0x180026793  movups  xmmword ptr [rax+48h], xmm1
0x180026797  mov     [rax+60h], r8
0x18002679b  mov     [rax+68h], r9
0x18002679f  mov     [rax+70h], r15
0x1800267a3  mov     [rbp+4Fh+TargetHandle], rsi
0x1800267a7  call    ?ProtectExtraMemory@SipcSection@@IEBAXXZ; SipcSection::ProtectExtraMemory(void)
0x1800267ac  test    rbx, rbx
0x1800267af  jz      short loc_1800267C0
0x1800267b1  mov     rcx, rbx; hObject
0x1800267b4  call    cs:__imp_CloseHandle
0x1800267bb  nop     dword ptr [rax+rax+00h]
0x1800267c0  mov     rcx, [rbp+4Fh+TargetHandle]; hObject
0x1800267c4  test    rcx, rcx
0x1800267c7  jz      short loc_1800267D5
0x1800267c9  call    cs:__imp_CloseHandle
0x1800267d0  nop     dword ptr [rax+rax+00h]
0x1800267d5  xor     eax, eax
0x1800267d7  jmp     short loc_18002682A
0x1800267d9  mov     [r14], rsi
0x1800267dc  mov     edi, 0C0000017h
0x1800267e1  mov     r8, [rbp+4Fh+var_60]; void *
0x1800267e5  mov     rdx, r12; void *
0x1800267e8  mov     rcx, [rbp+4Fh+var_58]; void *
0x1800267ec  call    ?Unmap@AlpcSection@@CAJPEAX00@Z; AlpcSection::Unmap(void *,void *,void *)
0x1800267f1  mov     esi, eax
0x1800267f3  test    eax, eax
0x1800267f5  js      loc_180026692
0x1800267fb  bts     edi, 1Ch
0x1800267ff  test    rbx, rbx
0x180026802  jz      short loc_180026813
0x180026804  mov     rcx, rbx; hObject
0x180026807  call    cs:__imp_CloseHandle
0x18002680e  nop     dword ptr [rax+rax+00h]
0x180026813  mov     rcx, [rbp+4Fh+TargetHandle]; hObject
0x180026817  test    rcx, rcx
0x18002681a  jz      short loc_180026828
0x18002681c  call    cs:__imp_CloseHandle
0x180026823  nop     dword ptr [rax+rax+00h]
0x180026828  mov     eax, edi
0x18002682a  add     rsp, 98h
0x180026831  pop     r15
0x180026833  pop     r14
0x180026835  pop     r13
0x180026837  pop     r12
0x180026839  pop     rdi
0x18002683a  pop     rsi
0x18002683b  pop     rbx
0x18002683c  pop     rbp
0x18002683d  retn
```
