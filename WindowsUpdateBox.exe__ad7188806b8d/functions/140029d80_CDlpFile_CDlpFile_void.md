# CDlpFile::~CDlpFile(void)

- ea: `0x140029d80`
- end: `0x140029f55`
- name: `??1CDlpFile@@UEAA@XZ`
- size: `469`
- prototype: `void __fastcall(CDlpFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002b360`

## callees

- `0x1400135b8`
- `0x140029950`
- `0x140029d80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140029dad`
- `KERNEL32!DeleteCriticalSection` at `0x140029dcb`
- `KERNEL32!DeleteCriticalSection` at `0x140029de9`
- `KERNEL32!DeleteCriticalSection` at `0x140029e07`
- `KERNEL32!DeleteCriticalSection` at `0x140029e25`
- `KERNEL32!DeleteCriticalSection` at `0x140029e43`
- `KERNEL32!DeleteCriticalSection` at `0x140029dad`
- `KERNEL32!DeleteCriticalSection` at `0x140029dcb`
- `KERNEL32!DeleteCriticalSection` at `0x140029de9`
- `KERNEL32!DeleteCriticalSection` at `0x140029e07`
- `KERNEL32!DeleteCriticalSection` at `0x140029e25`
- `KERNEL32!DeleteCriticalSection` at `0x140029e43`
- `KERNEL32!HeapFree` at `0x140029e73`
- `KERNEL32!HeapFree` at `0x140029eae`
- `KERNEL32!HeapFree` at `0x140029ee9`
- `KERNEL32!HeapFree` at `0x140029f24`
- `KERNEL32!HeapFree` at `0x140029e73`
- `KERNEL32!HeapFree` at `0x140029eae`
- `KERNEL32!HeapFree` at `0x140029ee9`
- `KERNEL32!HeapFree` at `0x140029f24`
- `KERNEL32!GetProcessHeap` at `0x140029e5e`
- `KERNEL32!GetProcessHeap` at `0x140029e99`
- `KERNEL32!GetProcessHeap` at `0x140029ed4`
- `KERNEL32!GetProcessHeap` at `0x140029f0f`
- `KERNEL32!GetProcessHeap` at `0x140029e5e`
- `KERNEL32!GetProcessHeap` at `0x140029e99`
- `KERNEL32!GetProcessHeap` at `0x140029ed4`
- `KERNEL32!GetProcessHeap` at `0x140029f0f`

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
  CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>((__int64)this);
}

```

## disassembly

```asm
0x140029d80  push    rdi
0x140029d82  sub     rsp, 30h
0x140029d86  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140029d8f  mov     [rsp+38h+arg_0], rbx
0x140029d94  mov     [rsp+38h+arg_8], rsi
0x140029d99  mov     rdi, rcx
0x140029d9c  lea     rbx, [rcx+230h]
0x140029da3  xor     esi, esi
0x140029da5  cmp     [rbx+28h], esi
0x140029da8  jz      short loc_140029DBC
0x140029daa  mov     rcx, rbx; lpCriticalSection
0x140029dad  call    cs:__imp_DeleteCriticalSection
0x140029db4  nop     dword ptr [rax+rax+00h]
0x140029db9  mov     [rbx+28h], esi
0x140029dbc  lea     rbx, [rdi+1F0h]
0x140029dc3  cmp     [rbx+28h], esi
0x140029dc6  jz      short loc_140029DDA
0x140029dc8  mov     rcx, rbx; lpCriticalSection
0x140029dcb  call    cs:__imp_DeleteCriticalSection
0x140029dd2  nop     dword ptr [rax+rax+00h]
0x140029dd7  mov     [rbx+28h], esi
0x140029dda  lea     rbx, [rdi+1B0h]
0x140029de1  cmp     [rbx+28h], esi
0x140029de4  jz      short loc_140029DF8
0x140029de6  mov     rcx, rbx; lpCriticalSection
0x140029de9  call    cs:__imp_DeleteCriticalSection
0x140029df0  nop     dword ptr [rax+rax+00h]
0x140029df5  mov     [rbx+28h], esi
0x140029df8  lea     rbx, [rdi+178h]
0x140029dff  cmp     [rbx+28h], esi
0x140029e02  jz      short loc_140029E16
0x140029e04  mov     rcx, rbx; lpCriticalSection
0x140029e07  call    cs:__imp_DeleteCriticalSection
0x140029e0e  nop     dword ptr [rax+rax+00h]
0x140029e13  mov     [rbx+28h], esi
0x140029e16  lea     rbx, [rdi+140h]
0x140029e1d  cmp     [rbx+28h], esi
0x140029e20  jz      short loc_140029E34
0x140029e22  mov     rcx, rbx; lpCriticalSection
0x140029e25  call    cs:__imp_DeleteCriticalSection
0x140029e2c  nop     dword ptr [rax+rax+00h]
0x140029e31  mov     [rbx+28h], esi
0x140029e34  lea     rbx, [rdi+108h]
0x140029e3b  cmp     [rbx+28h], esi
0x140029e3e  jz      short loc_140029E52
0x140029e40  mov     rcx, rbx; lpCriticalSection
0x140029e43  call    cs:__imp_DeleteCriticalSection
0x140029e4a  nop     dword ptr [rax+rax+00h]
0x140029e4f  mov     [rbx+28h], esi
0x140029e52  mov     rbx, [rdi+0F0h]
0x140029e59  test    rbx, rbx
0x140029e5c  jz      short loc_140029E8D
0x140029e5e  call    cs:__imp_GetProcessHeap
0x140029e65  nop     dword ptr [rax+rax+00h]
0x140029e6a  mov     rcx, rax; hHeap
0x140029e6d  lea     r8, [rbx-4]; lpMem
0x140029e71  xor     edx, edx; dwFlags
0x140029e73  call    cs:__imp_HeapFree
0x140029e7a  nop     dword ptr [rax+rax+00h]
0x140029e7f  xor     ecx, ecx
0x140029e81  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140029e86  mov     [rdi+0F0h], rsi
0x140029e8d  mov     rbx, [rdi+0E8h]
0x140029e94  test    rbx, rbx
0x140029e97  jz      short loc_140029EC8
0x140029e99  call    cs:__imp_GetProcessHeap
0x140029ea0  nop     dword ptr [rax+rax+00h]
0x140029ea5  mov     rcx, rax; hHeap
0x140029ea8  lea     r8, [rbx-4]; lpMem
0x140029eac  xor     edx, edx; dwFlags
0x140029eae  call    cs:__imp_HeapFree
0x140029eb5  nop     dword ptr [rax+rax+00h]
0x140029eba  xor     ecx, ecx
0x140029ebc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140029ec1  mov     [rdi+0E8h], rsi
0x140029ec8  mov     rbx, [rdi+0E0h]
0x140029ecf  test    rbx, rbx
0x140029ed2  jz      short loc_140029F03
0x140029ed4  call    cs:__imp_GetProcessHeap
0x140029edb  nop     dword ptr [rax+rax+00h]
0x140029ee0  mov     rcx, rax; hHeap
0x140029ee3  lea     r8, [rbx-4]; lpMem
0x140029ee7  xor     edx, edx; dwFlags
0x140029ee9  call    cs:__imp_HeapFree
0x140029ef0  nop     dword ptr [rax+rax+00h]
0x140029ef5  xor     ecx, ecx
0x140029ef7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140029efc  mov     [rdi+0E0h], rsi
0x140029f03  mov     rbx, [rdi+0D8h]
0x140029f0a  test    rbx, rbx
0x140029f0d  jz      short loc_140029F3E
0x140029f0f  call    cs:__imp_GetProcessHeap
0x140029f16  nop     dword ptr [rax+rax+00h]
0x140029f1b  mov     rcx, rax; hHeap
0x140029f1e  lea     r8, [rbx-4]; lpMem
0x140029f22  xor     edx, edx; dwFlags
0x140029f24  call    cs:__imp_HeapFree
0x140029f2b  nop     dword ptr [rax+rax+00h]
0x140029f30  xor     ecx, ecx
0x140029f32  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140029f37  mov     [rdi+0D8h], rsi
0x140029f3e  mov     rcx, rdi
0x140029f41  mov     rbx, [rsp+38h+arg_0]
0x140029f46  mov     rsi, [rsp+38h+arg_8]
0x140029f4b  add     rsp, 30h
0x140029f4f  pop     rdi
0x140029f50  jmp     ??1?$CDlpErrorImpl@V?$CUnknownRefChainImpl@VIDlpFile@@@@@@UEAA@XZ; CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>(void)
```
