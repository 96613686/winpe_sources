# CPhotoPropertyStore::Initialize(ushort const *,ulong)

- ea: `0x18001d3e0`
- end: `0x18001d4b2`
- name: `?Initialize@CPhotoPropertyStore@@UEAAJPEBGK@Z`
- size: `210`
- prototype: `int(CPhotoPropertyStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008b54`
- `0x18001186c`
- `0x18001d3e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d490`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3ff`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001d442`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001d442`

## pseudocode

```c
__int64 __fastcall CPhotoPropertyStore::Initialize(CPhotoPropertyStore *this, const unsigned __int16 *a2, DWORD a3)
{
  const struct _GUID *v6; // rcx
  unsigned __int64 v7; // r8
  HRESULT v8; // ebx
  unsigned __int64 v9; // r8
  IStream *ppstm; // [rsp+50h] [rbp+8h] BYREF

  ppstm = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v7 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v7 )
    ShellPrivateTraceEvent(v6, 1u, v7, 1u);
  if ( *((_DWORD *)this + 42) )
  {
    v8 = -2147023649;
  }
  else
  {
    v8 = SHCreateStreamOnFileW(a2, a3, &ppstm);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(char *, IStream *, _QWORD))(*((_QWORD *)this - 1) + 24LL))(
             (char *)this - 8,
             ppstm,
             a3);
  }
  v9 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v9 )
    ShellPrivateTraceEvent(v6, 1u, v9, 2u);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d3e0  push    rbx
0x18001d3e2  push    rbp
0x18001d3e3  push    rsi
0x18001d3e4  push    rdi
0x18001d3e5  sub     rsp, 28h
0x18001d3e9  mov     rdi, rcx
0x18001d3ec  mov     [rsp+48h+ppstm], 0
0x18001d3f5  add     rcx, 58h ; 'X'; lpCriticalSection
0x18001d3f9  mov     ebp, r8d
0x18001d3fc  mov     rbx, rdx
0x18001d3ff  call    cs:__imp_EnterCriticalSection
0x18001d406  nop     dword ptr [rax+rax+00h]
0x18001d40b  mov     rax, cs:WPP_GLOBAL_Control
0x18001d412  mov     r8, [rax+38h]; unsigned __int64
0x18001d416  test    r8, r8
0x18001d419  jz      short loc_18001D428
0x18001d41b  mov     r9b, 1; unsigned __int8
0x18001d41e  mov     edx, 1; unsigned int
0x18001d423  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001d428  cmp     dword ptr [rdi+0A8h], 0
0x18001d42f  jz      short loc_18001D438
0x18001d431  mov     ebx, 800704DFh
0x18001d436  jmp     short loc_18001D46F
0x18001d438  lea     r8, [rsp+48h+ppstm]; ppstm
0x18001d43d  mov     edx, ebp; grfMode
0x18001d43f  mov     rcx, rbx; pszFile
0x18001d442  call    cs:__imp_SHCreateStreamOnFileW
0x18001d449  nop     dword ptr [rax+rax+00h]
0x18001d44e  mov     ebx, eax
0x18001d450  test    eax, eax
0x18001d452  js      short loc_18001D46F
0x18001d454  mov     rax, [rdi-8]
0x18001d458  lea     rcx, [rdi-8]
0x18001d45c  mov     rdx, [rsp+48h+ppstm]
0x18001d461  mov     r8d, ebp
0x18001d464  mov     rax, [rax+18h]
0x18001d468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46d  mov     ebx, eax
0x18001d46f  mov     rax, cs:WPP_GLOBAL_Control
0x18001d476  mov     r8, [rax+38h]; unsigned __int64
0x18001d47a  test    r8, r8
0x18001d47d  jz      short loc_18001D48C
0x18001d47f  mov     r9b, 2; unsigned __int8
0x18001d482  mov     edx, 1; unsigned int
0x18001d487  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001d48c  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001d490  call    cs:__imp_LeaveCriticalSection
0x18001d497  nop     dword ptr [rax+rax+00h]
0x18001d49c  lea     rcx, [rsp+48h+ppstm]
0x18001d4a1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d4a6  mov     eax, ebx
0x18001d4a8  add     rsp, 28h
0x18001d4ac  pop     rdi
0x18001d4ad  pop     rsi
0x18001d4ae  pop     rbp
0x18001d4af  pop     rbx
0x18001d4b0  retn
```
