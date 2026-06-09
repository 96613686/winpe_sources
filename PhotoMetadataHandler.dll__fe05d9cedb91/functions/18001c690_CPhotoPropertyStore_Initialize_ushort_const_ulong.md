# CPhotoPropertyStore::Initialize(ushort const *,ulong)

- ea: `0x18001c690`
- end: `0x18001c74f`
- name: `?Initialize@CPhotoPropertyStore@@UEAAJPEBGK@Z`
- size: `191`
- prototype: `__int64 __fastcall(CPhotoPropertyStore *this, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007804`
- `0x1800110b8`
- `0x18001c690`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c734`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6af`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001c6ec`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001c6ec`

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
0x18001c690  push    rbx
0x18001c692  push    rbp
0x18001c693  push    rsi
0x18001c694  push    rdi
0x18001c695  sub     rsp, 28h
0x18001c699  mov     rdi, rcx
0x18001c69c  mov     [rsp+48h+ppstm], 0
0x18001c6a5  add     rcx, 58h ; 'X'; lpCriticalSection
0x18001c6a9  mov     ebp, r8d
0x18001c6ac  mov     rbx, rdx
0x18001c6af  call    cs:__imp_EnterCriticalSection
0x18001c6b5  mov     rax, cs:WPP_GLOBAL_Control
0x18001c6bc  mov     r8, [rax+38h]; unsigned __int64
0x18001c6c0  test    r8, r8
0x18001c6c3  jz      short loc_18001C6D2
0x18001c6c5  mov     r9b, 1; unsigned __int8
0x18001c6c8  mov     edx, 1; unsigned int
0x18001c6cd  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001c6d2  cmp     dword ptr [rdi+0A8h], 0
0x18001c6d9  jz      short loc_18001C6E2
0x18001c6db  mov     ebx, 800704DFh
0x18001c6e0  jmp     short loc_18001C713
0x18001c6e2  lea     r8, [rsp+48h+ppstm]; ppstm
0x18001c6e7  mov     edx, ebp; grfMode
0x18001c6e9  mov     rcx, rbx; pszFile
0x18001c6ec  call    cs:__imp_SHCreateStreamOnFileW
0x18001c6f2  mov     ebx, eax
0x18001c6f4  test    eax, eax
0x18001c6f6  js      short loc_18001C713
0x18001c6f8  mov     rax, [rdi-8]
0x18001c6fc  lea     rcx, [rdi-8]
0x18001c700  mov     rdx, [rsp+48h+ppstm]
0x18001c705  mov     r8d, ebp
0x18001c708  mov     rax, [rax+18h]
0x18001c70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c711  mov     ebx, eax
0x18001c713  mov     rax, cs:WPP_GLOBAL_Control
0x18001c71a  mov     r8, [rax+38h]; unsigned __int64
0x18001c71e  test    r8, r8
0x18001c721  jz      short loc_18001C730
0x18001c723  mov     r9b, 2; unsigned __int8
0x18001c726  mov     edx, 1; unsigned int
0x18001c72b  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001c730  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001c734  call    cs:__imp_LeaveCriticalSection
0x18001c73a  lea     rcx, [rsp+48h+ppstm]
0x18001c73f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c744  mov     eax, ebx
0x18001c746  add     rsp, 28h
0x18001c74a  pop     rdi
0x18001c74b  pop     rsi
0x18001c74c  pop     rbp
0x18001c74d  pop     rbx
0x18001c74e  retn
```
