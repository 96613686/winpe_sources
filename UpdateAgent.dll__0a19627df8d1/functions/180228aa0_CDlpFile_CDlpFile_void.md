# CDlpFile::~CDlpFile(void)

- ea: `0x180228aa0`
- end: `0x180228c75`
- name: `??1CDlpFile@@UEAA@XZ`
- size: `469`
- prototype: `void __fastcall(CDlpFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18022a130`

## callees

- `0x180077664`
- `0x180228658`
- `0x180228aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228acd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228aeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228acd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228aeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228bb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228bf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228bb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228bf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228b93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228c09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228c44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228b93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228c09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228c44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDlpFile::~CDlpFile(CDlpFile *this)
{
  char *v2; // rbx
  __int64 v3; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax

  v2 = (char *)this + 560;
  if ( *((_DWORD *)this + 150) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
    *((_DWORD *)v2 + 10) = 0;
  }
  if ( *((_DWORD *)this + 134) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
    *((_DWORD *)this + 134) = 0;
  }
  if ( *((_DWORD *)this + 118) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
    *((_DWORD *)this + 118) = 0;
  }
  if ( *((_DWORD *)this + 104) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    *((_DWORD *)this + 104) = 0;
  }
  if ( *((_DWORD *)this + 90) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
    *((_DWORD *)this + 90) = 0;
  }
  if ( *((_DWORD *)this + 76) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    *((_DWORD *)this + 76) = 0;
  }
  v3 = *((_QWORD *)this + 30);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 30) = 0;
  }
  v5 = *((_QWORD *)this + 29);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 29) = 0;
  }
  v7 = *((_QWORD *)this + 28);
  if ( v7 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 28) = 0;
  }
  v9 = *((_QWORD *)this + 27);
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, (LPVOID)(v9 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 27) = 0;
  }
  CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>(this);
}

```

## disassembly

```asm
0x180228aa0  push    rdi
0x180228aa2  sub     rsp, 30h
0x180228aa6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180228aaf  mov     [rsp+38h+arg_0], rbx
0x180228ab4  mov     [rsp+38h+arg_8], rsi
0x180228ab9  mov     rdi, rcx
0x180228abc  lea     rbx, [rcx+230h]
0x180228ac3  xor     esi, esi
0x180228ac5  cmp     [rbx+28h], esi
0x180228ac8  jz      short loc_180228ADC
0x180228aca  mov     rcx, rbx; lpCriticalSection
0x180228acd  call    cs:__imp_DeleteCriticalSection
0x180228ad4  nop     dword ptr [rax+rax+00h]
0x180228ad9  mov     [rbx+28h], esi
0x180228adc  lea     rbx, [rdi+1F0h]
0x180228ae3  cmp     [rbx+28h], esi
0x180228ae6  jz      short loc_180228AFA
0x180228ae8  mov     rcx, rbx; lpCriticalSection
0x180228aeb  call    cs:__imp_DeleteCriticalSection
0x180228af2  nop     dword ptr [rax+rax+00h]
0x180228af7  mov     [rbx+28h], esi
0x180228afa  lea     rbx, [rdi+1B0h]
0x180228b01  cmp     [rbx+28h], esi
0x180228b04  jz      short loc_180228B18
0x180228b06  mov     rcx, rbx; lpCriticalSection
0x180228b09  call    cs:__imp_DeleteCriticalSection
0x180228b10  nop     dword ptr [rax+rax+00h]
0x180228b15  mov     [rbx+28h], esi
0x180228b18  lea     rbx, [rdi+178h]
0x180228b1f  cmp     [rbx+28h], esi
0x180228b22  jz      short loc_180228B36
0x180228b24  mov     rcx, rbx; lpCriticalSection
0x180228b27  call    cs:__imp_DeleteCriticalSection
0x180228b2e  nop     dword ptr [rax+rax+00h]
0x180228b33  mov     [rbx+28h], esi
0x180228b36  lea     rbx, [rdi+140h]
0x180228b3d  cmp     [rbx+28h], esi
0x180228b40  jz      short loc_180228B54
0x180228b42  mov     rcx, rbx; lpCriticalSection
0x180228b45  call    cs:__imp_DeleteCriticalSection
0x180228b4c  nop     dword ptr [rax+rax+00h]
0x180228b51  mov     [rbx+28h], esi
0x180228b54  lea     rbx, [rdi+108h]
0x180228b5b  cmp     [rbx+28h], esi
0x180228b5e  jz      short loc_180228B72
0x180228b60  mov     rcx, rbx; lpCriticalSection
0x180228b63  call    cs:__imp_DeleteCriticalSection
0x180228b6a  nop     dword ptr [rax+rax+00h]
0x180228b6f  mov     [rbx+28h], esi
0x180228b72  mov     rbx, [rdi+0F0h]
0x180228b79  test    rbx, rbx
0x180228b7c  jz      short loc_180228BAD
0x180228b7e  call    cs:__imp_GetProcessHeap
0x180228b85  nop     dword ptr [rax+rax+00h]
0x180228b8a  mov     rcx, rax; hHeap
0x180228b8d  lea     r8, [rbx-4]; lpMem
0x180228b91  xor     edx, edx; dwFlags
0x180228b93  call    cs:__imp_HeapFree
0x180228b9a  nop     dword ptr [rax+rax+00h]
0x180228b9f  xor     ecx, ecx
0x180228ba1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228ba6  mov     [rdi+0F0h], rsi
0x180228bad  mov     rbx, [rdi+0E8h]
0x180228bb4  test    rbx, rbx
0x180228bb7  jz      short loc_180228BE8
0x180228bb9  call    cs:__imp_GetProcessHeap
0x180228bc0  nop     dword ptr [rax+rax+00h]
0x180228bc5  mov     rcx, rax; hHeap
0x180228bc8  lea     r8, [rbx-4]; lpMem
0x180228bcc  xor     edx, edx; dwFlags
0x180228bce  call    cs:__imp_HeapFree
0x180228bd5  nop     dword ptr [rax+rax+00h]
0x180228bda  xor     ecx, ecx
0x180228bdc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228be1  mov     [rdi+0E8h], rsi
0x180228be8  mov     rbx, [rdi+0E0h]
0x180228bef  test    rbx, rbx
0x180228bf2  jz      short loc_180228C23
0x180228bf4  call    cs:__imp_GetProcessHeap
0x180228bfb  nop     dword ptr [rax+rax+00h]
0x180228c00  mov     rcx, rax; hHeap
0x180228c03  lea     r8, [rbx-4]; lpMem
0x180228c07  xor     edx, edx; dwFlags
0x180228c09  call    cs:__imp_HeapFree
0x180228c10  nop     dword ptr [rax+rax+00h]
0x180228c15  xor     ecx, ecx
0x180228c17  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228c1c  mov     [rdi+0E0h], rsi
0x180228c23  mov     rbx, [rdi+0D8h]
0x180228c2a  test    rbx, rbx
0x180228c2d  jz      short loc_180228C5E
0x180228c2f  call    cs:__imp_GetProcessHeap
0x180228c36  nop     dword ptr [rax+rax+00h]
0x180228c3b  mov     rcx, rax; hHeap
0x180228c3e  lea     r8, [rbx-4]; lpMem
0x180228c42  xor     edx, edx; dwFlags
0x180228c44  call    cs:__imp_HeapFree
0x180228c4b  nop     dword ptr [rax+rax+00h]
0x180228c50  xor     ecx, ecx
0x180228c52  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228c57  mov     [rdi+0D8h], rsi
0x180228c5e  mov     rcx, rdi
0x180228c61  mov     rbx, [rsp+38h+arg_0]
0x180228c66  mov     rsi, [rsp+38h+arg_8]
0x180228c6b  add     rsp, 30h
0x180228c6f  pop     rdi
0x180228c70  jmp     ??1?$CDlpErrorImpl@V?$CUnknownRefChainImpl@VIDlpFile@@@@@@UEAA@XZ; CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>(void)
```
