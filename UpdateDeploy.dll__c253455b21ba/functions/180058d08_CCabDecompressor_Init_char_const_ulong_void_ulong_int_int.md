# CCabDecompressor::Init(char const * *,ulong,void *,ulong,int,int)

- ea: `0x180058d08`
- end: `0x180058efa`
- name: `?Init@CCabDecompressor@@QEAAJPEAPEBDKPEAXKHH@Z`
- size: `498`
- prototype: `__int64 __fastcall(CCabDecompressor *this, const char **, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180059dfc`

## callees

- `0x180003180`
- `0x180058d08`
- `0x180058f00`
- `0x18005a0c0`
- `0x18005a414`
- `0x180061960`
- `0x180062558`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180058e37`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180058e37`
- `RPCRT4!UuidToStringA` at `0x180058e6c`
- `RPCRT4!UuidToStringA` at `0x180058e6c`
- `Cabinet!__imp_FDICreate` at `0x180058dff`
- `Cabinet!__imp_FDICreate` at `0x180058dff`

## string_xrefs

- `0x180058d45`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x180058e50`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::Init(
        CCabDecompressor *this,
        const char **a2,
        unsigned int a3,
        void *a4,
        unsigned int a5)
{
  __int64 v5; // rdi
  const char **v6; // rbp
  unsigned int LastFDIErrorHr; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  _QWORD *v11; // rax
  HFDI v12; // rax
  HRESULT v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rsi
  int pfnwrite; // [rsp+20h] [rbp-78h]
  GUID pguid; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = a3;
  v6 = a2;
  if ( !a2 && a3 )
  {
    LastFDIErrorHr = -2147024809;
    v9 = 96;
    goto LABEL_4;
  }
  v11 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 )
  {
    v11[3] = 0;
    *v11 = &CSusListIterator<COutputMemoryFile>::`vftable';
    v11[1] = 0;
    v11[2] = 0;
    v11[4] = 0;
  }
  *((_QWORD *)this + 8) = v11;
  if ( !v11 )
  {
    LastFDIErrorHr = -2147024882;
    v9 = 99;
    goto LABEL_4;
  }
  v12 = FDICreate(
          CCabDecompressor::CabDecompressorMemAlloc,
          CCabDecompressor::CabDecompressorMemFree,
          CCabDecompressor::CabDecompressorFileOpen,
          CCabDecompressor::CabDecompressorFileRead,
          CCabDecompressor::CabDecompressorFileWrite,
          CCabDecompressor::CabDecompressorFileClose,
          CCabDecompressor::CabDecompressorFileSeek,
          0,
          (PERF)this + 2);
  *((_QWORD *)this + 5) = v12;
  if ( !v12 )
  {
    LastFDIErrorHr = CCabDecompressor::GetLastFDIErrorHr(this);
    if ( (LastFDIErrorHr & 0x80000000) == 0 )
      return LastFDIErrorHr;
    v9 = 117;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)LastFDIErrorHr,
      pfnwrite);
    return LastFDIErrorHr;
  }
  pguid = 0;
  v13 = CoCreateGuid(&pguid);
  if ( v13 < 0 )
  {
    v14 = 129;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)v13,
      pfnwrite);
    return (unsigned int)v13;
  }
  v13 = UuidToStringA(&pguid, (RPC_CSTR *)this + 6);
  if ( v13 < 0 )
  {
    v14 = 131;
    goto LABEL_15;
  }
  v13 = CSusArrayList<char *,CSusSortedArrayListItemOpsLPSTR>::Grow((char *)this + 80, (unsigned int)v5);
  if ( v13 < 0 )
  {
    v14 = 136;
    goto LABEL_15;
  }
  if ( (_DWORD)v5 )
  {
    v15 = v5;
    do
    {
      CSusSortedArrayList<char const *,CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete>::Add(
        (char *)this + 80,
        v6++);
      --v15;
    }
    while ( v15 );
  }
  *((_DWORD *)this + 38) = a5;
  result = 0;
  *((_DWORD *)this + 28) = v5;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 39) = 0;
  *((_DWORD *)this + 18) = 1;
  return result;
}

```

## disassembly

```asm
0x180058d08  push    rbx
0x180058d0a  push    rbp
0x180058d0b  push    rsi
0x180058d0c  push    rdi
0x180058d0d  push    r14
0x180058d0f  sub     rsp, 70h
0x180058d13  mov     rax, cs:__security_cookie
0x180058d1a  xor     rax, rsp
0x180058d1d  mov     [rsp+98h+var_38], rax
0x180058d22  mov     edi, r8d
0x180058d25  mov     rbp, rdx
0x180058d28  mov     rbx, rcx
0x180058d2b  test    rdx, rdx
0x180058d2e  jnz     short loc_180058D5B
0x180058d30  test    r8d, r8d
0x180058d33  jz      short loc_180058D5B
0x180058d35  mov     ebx, 80070057h
0x180058d3a  lea     edx, [rbp+60h]; void *
0x180058d3d  mov     rcx, [rsp+98h]; this
0x180058d45  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180058d4c  mov     r9d, ebx; char *
0x180058d4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d54  mov     eax, ebx
0x180058d56  jmp     loc_180058EE2
0x180058d5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180058d62  mov     ecx, 28h ; '('; unsigned __int64
0x180058d67  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180058d6c  test    rax, rax
0x180058d6f  jz      short loc_180058D9B
0x180058d71  lea     rcx, ??_7?$CSusListIterator@VCOutputMemoryFile@@@@6B@; const CSusListIterator<COutputMemoryFile>::`vftable'
0x180058d78  mov     qword ptr [rax+18h], 0
0x180058d80  mov     [rax], rcx
0x180058d83  mov     qword ptr [rax+8], 0
0x180058d8b  mov     qword ptr [rax+10h], 0
0x180058d93  mov     qword ptr [rax+20h], 0
0x180058d9b  mov     [rbx+40h], rax
0x180058d9f  test    rax, rax
0x180058da2  jnz     short loc_180058DAE
0x180058da4  mov     ebx, 8007000Eh
0x180058da9  lea     edx, [rax+63h]
0x180058dac  jmp     short loc_180058D3D
0x180058dae  lea     rax, [rbx+18h]
0x180058db2  mov     [rsp+98h+perf], rax; perf
0x180058db7  lea     r9, ?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z; pfnread
0x180058dbe  mov     [rsp+98h+cpuType], 0; cpuType
0x180058dc6  lea     rax, ?CabDecompressorFileSeek@CCabDecompressor@@CAJ_JJH@Z; CCabDecompressor::CabDecompressorFileSeek(__int64,long,int)
0x180058dcd  mov     [rsp+98h+pfnseek], rax; pfnseek
0x180058dd2  lea     r8, ?CabDecompressorFileOpen@CCabDecompressor@@CA_JPEBDHH@Z; pfnopen
0x180058dd9  lea     rax, ?CabDecompressorFileClose@CCabDecompressor@@CAH_J@Z; CCabDecompressor::CabDecompressorFileClose(__int64)
0x180058de0  mov     [rsp+98h+pfnclose], rax; pfnclose
0x180058de5  lea     rdx, ?CabDecompressorMemFree@CCabDecompressor@@CAXPEAX@Z; pfnfree
0x180058dec  lea     rax, ?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z; CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)
0x180058df3  lea     rcx, ?CabDecompressorMemAlloc@CCabDecompressor@@CAPEAXK@Z; pfnalloc
0x180058dfa  mov     [rsp+98h+pfnwrite], rax; int
0x180058dff  call    cs:__imp_FDICreate
0x180058e05  mov     [rbx+28h], rax
0x180058e09  test    rax, rax
0x180058e0c  jnz     short loc_180058E2A
0x180058e0e  mov     rcx, rbx; this
0x180058e11  call    ?GetLastFDIErrorHr@CCabDecompressor@@QEAAJXZ; CCabDecompressor::GetLastFDIErrorHr(void)
0x180058e16  mov     ebx, eax
0x180058e18  test    eax, eax
0x180058e1a  jns     loc_180058D54
0x180058e20  mov     edx, 75h ; 'u'
0x180058e25  jmp     loc_180058D3D
0x180058e2a  xorps   xmm0, xmm0
0x180058e2d  lea     rcx, [rsp+98h+pguid]; pguid
0x180058e32  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x180058e37  call    cs:__imp_CoCreateGuid
0x180058e3d  mov     esi, eax
0x180058e3f  test    eax, eax
0x180058e41  jns     short loc_180058E63
0x180058e43  mov     edx, 81h; void *
0x180058e48  mov     rcx, [rsp+98h]; this
0x180058e50  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180058e57  mov     r9d, esi; char *
0x180058e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e5f  mov     eax, esi
0x180058e61  jmp     short loc_180058EE2
0x180058e63  lea     rdx, [rbx+30h]; StringUuid
0x180058e67  lea     rcx, [rsp+98h+pguid]; Uuid
0x180058e6c  call    cs:__imp_UuidToStringA
0x180058e72  mov     esi, eax
0x180058e74  test    eax, eax
0x180058e76  jns     short loc_180058E7F
0x180058e78  mov     edx, 83h
0x180058e7d  jmp     short loc_180058E48
0x180058e7f  mov     edx, edi
0x180058e81  lea     rcx, [rbx+50h]
0x180058e85  call    ?Grow@?$CSusArrayList@PEADVCSusSortedArrayListItemOpsLPSTR@@@@QEAAJK@Z; CSusArrayList<char *,CSusSortedArrayListItemOpsLPSTR>::Grow(ulong)
0x180058e8a  mov     esi, eax
0x180058e8c  test    eax, eax
0x180058e8e  jns     short loc_180058E97
0x180058e90  mov     edx, 88h
0x180058e95  jmp     short loc_180058E48
0x180058e97  test    edi, edi
0x180058e99  jz      short loc_180058EB4
0x180058e9b  mov     rsi, rdi
0x180058e9e  mov     rdx, rbp
0x180058ea1  lea     rcx, [rbx+50h]
0x180058ea5  call    ?Add@?$CSusSortedArrayList@PEBDVCSusSortedArrayListItemOpsLPCSTRNoDelete@CCabDecompressor@@@@QEAAJAEBQEBDK@Z; CSusSortedArrayList<char const *,CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete>::Add(char const * const &,ulong)
0x180058eaa  add     rbp, 8
0x180058eae  sub     rsi, 1
0x180058eb2  jnz     short loc_180058E9E
0x180058eb4  mov     eax, [rsp+98h+arg_20]
0x180058ebb  mov     [rbx+98h], eax
0x180058ec1  xor     eax, eax
0x180058ec3  mov     [rbx+70h], edi
0x180058ec6  mov     qword ptr [rbx+90h], 0
0x180058ed1  mov     dword ptr [rbx+9Ch], 0
0x180058edb  mov     dword ptr [rbx+48h], 1
0x180058ee2  mov     rcx, [rsp+98h+var_38]
0x180058ee7  xor     rcx, rsp; StackCookie
0x180058eea  call    __security_check_cookie
0x180058eef  add     rsp, 70h
0x180058ef3  pop     r14
0x180058ef5  pop     rdi
0x180058ef6  pop     rsi
0x180058ef7  pop     rbp
0x180058ef8  pop     rbx
0x180058ef9  retn
```
