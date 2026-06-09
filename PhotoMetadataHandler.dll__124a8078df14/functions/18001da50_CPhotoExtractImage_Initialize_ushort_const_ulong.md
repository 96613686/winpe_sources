# CPhotoExtractImage::Initialize(ushort const *,ulong)

- ea: `0x18001da50`
- end: `0x18001db37`
- name: `?Initialize@CPhotoExtractImage@@UEAAJPEBGK@Z`
- size: `231`
- prototype: `__int64 __fastcall(CPhotoExtractImage *this, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007804`
- `0x18000c060`
- `0x1800110b8`
- `0x18001da50`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001da75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001da75`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001daac`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001daac`

## pseudocode

```c
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
0x18001da50  mov     [rsp+arg_8], rbx
0x18001da55  mov     [rsp+arg_10], rbp
0x18001da5a  push    rsi
0x18001da5b  push    rdi
0x18001da5c  push    r14
0x18001da5e  sub     rsp, 20h
0x18001da62  mov     r14d, r8d
0x18001da65  mov     rbp, rdx
0x18001da68  mov     rdi, rcx
0x18001da6b  lea     rsi, [rcx+258h]
0x18001da72  mov     rcx, rsi; lpCriticalSection
0x18001da75  call    cs:__imp_EnterCriticalSection
0x18001da7b  mov     rax, cs:WPP_GLOBAL_Control
0x18001da82  mov     r8, [rax+38h]; unsigned __int64
0x18001da86  test    r8, r8
0x18001da89  jz      short loc_18001DA98
0x18001da8b  mov     r9b, 1; unsigned __int8
0x18001da8e  mov     edx, 0Ch; unsigned int
0x18001da93  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001da98  mov     [rsp+38h+ppstm], 0
0x18001daa1  lea     r8, [rsp+38h+ppstm]; ppstm
0x18001daa6  mov     edx, r14d; grfMode
0x18001daa9  mov     rcx, rbp; pszFile
0x18001daac  call    cs:__imp_SHCreateStreamOnFileW
0x18001dab2  mov     ebx, eax
0x18001dab4  test    eax, eax
0x18001dab6  js      short loc_18001DAF1
0x18001dab8  lea     rcx, [rdi-8]
0x18001dabc  mov     rax, [rcx]
0x18001dabf  mov     r8d, r14d
0x18001dac2  mov     rdx, [rsp+38h+ppstm]
0x18001dac7  mov     rax, [rax+18h]
0x18001dacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dad0  mov     ebx, eax
0x18001dad2  test    eax, eax
0x18001dad4  js      short loc_18001DAF1
0x18001dad6  mov     r8, rbp; unsigned __int16 *
0x18001dad9  mov     edx, 104h; unsigned __int64
0x18001dade  lea     rcx, [rdi+40h]; unsigned __int16 *
0x18001dae2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001dae7  test    eax, eax
0x18001dae9  jns     short loc_18001DAF1
0x18001daeb  xor     eax, eax
0x18001daed  mov     [rdi+40h], ax
0x18001daf1  mov     rax, cs:WPP_GLOBAL_Control
0x18001daf8  mov     r8, [rax+38h]; unsigned __int64
0x18001dafc  test    r8, r8
0x18001daff  jz      short loc_18001DB0E
0x18001db01  mov     r9b, 2; unsigned __int8
0x18001db04  mov     edx, 0Ch; unsigned int
0x18001db09  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001db0e  mov     rcx, rsi; lpCriticalSection
0x18001db11  call    cs:__imp_LeaveCriticalSection
0x18001db17  nop
0x18001db18  lea     rcx, [rsp+38h+ppstm]
0x18001db1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001db22  mov     eax, ebx
0x18001db24  mov     rbx, [rsp+38h+arg_8]
0x18001db29  mov     rbp, [rsp+38h+arg_10]
0x18001db2e  add     rsp, 20h
0x18001db32  pop     r14
0x18001db34  pop     rdi
0x18001db35  pop     rsi
0x18001db36  retn
```
