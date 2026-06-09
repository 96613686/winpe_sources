# CPhotoExtractImage::Initialize(ushort const *,ulong)

- ea: `0x18001e840`
- end: `0x18001e93a`
- name: `?Initialize@CPhotoExtractImage@@UEAAJPEBGK@Z`
- size: `250`
- prototype: `int(CPhotoExtractImage *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008b54`
- `0x18000c610`
- `0x18001186c`
- `0x18001e840`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e90d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e90d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e865`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e865`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001e8a2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001e8a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPhotoExtractImage::Initialize(CPhotoExtractImage *this, const unsigned __int16 *a2, DWORD a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  const struct _GUID *v7; // rcx
  unsigned __int64 v8; // r8
  const struct _GUID *v9; // rcx
  HRESULT v10; // ebx
  unsigned __int64 v11; // r8
  IStream *ppstm; // [rsp+40h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 600);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 15);
  v8 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v8 )
    ShellPrivateTraceEvent(v7, 0xCu, v8, 1u);
  ppstm = 0;
  v10 = SHCreateStreamOnFileW(a2, a3, &ppstm);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(char *, IStream *, _QWORD))(*((_QWORD *)this - 1) + 24LL))(
            (char *)this - 8,
            ppstm,
            a3);
    if ( v10 >= 0 && (int)StringCchCopyW((unsigned __int16 *)this + 32, 0x104u, a2) < 0 )
      *((_WORD *)this + 32) = 0;
  }
  v11 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v11 )
    ShellPrivateTraceEvent(v9, 0xCu, v11, 2u);
  LeaveCriticalSection(v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001e840  mov     [rsp+arg_8], rbx
0x18001e845  mov     [rsp+arg_10], rbp
0x18001e84a  push    rsi
0x18001e84b  push    rdi
0x18001e84c  push    r14
0x18001e84e  sub     rsp, 20h
0x18001e852  mov     r14d, r8d
0x18001e855  mov     rbp, rdx
0x18001e858  mov     rdi, rcx
0x18001e85b  lea     rsi, [rcx+258h]
0x18001e862  mov     rcx, rsi; lpCriticalSection
0x18001e865  call    cs:__imp_EnterCriticalSection
0x18001e86c  nop     dword ptr [rax+rax+00h]
0x18001e871  mov     rax, cs:WPP_GLOBAL_Control
0x18001e878  mov     r8, [rax+38h]; unsigned __int64
0x18001e87c  test    r8, r8
0x18001e87f  jz      short loc_18001E88E
0x18001e881  mov     r9b, 1; unsigned __int8
0x18001e884  mov     edx, 0Ch; unsigned int
0x18001e889  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001e88e  mov     [rsp+38h+ppstm], 0
0x18001e897  lea     r8, [rsp+38h+ppstm]; ppstm
0x18001e89c  mov     edx, r14d; grfMode
0x18001e89f  mov     rcx, rbp; pszFile
0x18001e8a2  call    cs:__imp_SHCreateStreamOnFileW
0x18001e8a9  nop     dword ptr [rax+rax+00h]
0x18001e8ae  mov     ebx, eax
0x18001e8b0  test    eax, eax
0x18001e8b2  js      short loc_18001E8ED
0x18001e8b4  lea     rcx, [rdi-8]
0x18001e8b8  mov     rax, [rcx]
0x18001e8bb  mov     r8d, r14d
0x18001e8be  mov     rdx, [rsp+38h+ppstm]
0x18001e8c3  mov     rax, [rax+18h]
0x18001e8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8cc  mov     ebx, eax
0x18001e8ce  test    eax, eax
0x18001e8d0  js      short loc_18001E8ED
0x18001e8d2  mov     r8, rbp; unsigned __int16 *
0x18001e8d5  mov     edx, 104h; unsigned __int64
0x18001e8da  lea     rcx, [rdi+40h]; unsigned __int16 *
0x18001e8de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e8e3  test    eax, eax
0x18001e8e5  jns     short loc_18001E8ED
0x18001e8e7  xor     eax, eax
0x18001e8e9  mov     [rdi+40h], ax
0x18001e8ed  mov     rax, cs:WPP_GLOBAL_Control
0x18001e8f4  mov     r8, [rax+38h]; unsigned __int64
0x18001e8f8  test    r8, r8
0x18001e8fb  jz      short loc_18001E90A
0x18001e8fd  mov     r9b, 2; unsigned __int8
0x18001e900  mov     edx, 0Ch; unsigned int
0x18001e905  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001e90a  mov     rcx, rsi; lpCriticalSection
0x18001e90d  call    cs:__imp_LeaveCriticalSection
0x18001e914  nop     dword ptr [rax+rax+00h]
0x18001e919  nop
0x18001e91a  lea     rcx, [rsp+38h+ppstm]
0x18001e91f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e924  mov     eax, ebx
0x18001e926  mov     rbx, [rsp+38h+arg_8]
0x18001e92b  mov     rbp, [rsp+38h+arg_10]
0x18001e930  add     rsp, 20h
0x18001e934  pop     r14
0x18001e936  pop     rdi
0x18001e937  pop     rsi
0x18001e938  retn
```
