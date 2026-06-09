# CCabDecompressor::Init(char const * *,ulong,void *,ulong,int,int)

- ea: `0x14002eb58`
- end: `0x14002ed4a`
- name: `?Init@CCabDecompressor@@QEAAJPEAPEBDKPEAXKHH@Z`
- size: `498`
- prototype: `__int64 __fastcall(CCabDecompressor *this, const char **, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002fc9c`

## callees

- `0x140008de4`
- `0x14002eb58`
- `0x14002ed50`
- `0x14002ffa8`
- `0x1400302f4`
- `0x140045dc0`
- `0x140045df0`

## import_xrefs

- `RPCRT4!UuidToStringA` at `0x14002ecbc`
- `RPCRT4!UuidToStringA` at `0x14002ecbc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002ec87`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002ec87`
- `Cabinet!__imp_FDICreate` at `0x14002ec4f`
- `Cabinet!__imp_FDICreate` at `0x14002ec4f`

## string_xrefs

- `0x14002eb95`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002eca0`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

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
0x14002eb58  push    rbx
0x14002eb5a  push    rbp
0x14002eb5b  push    rsi
0x14002eb5c  push    rdi
0x14002eb5d  push    r14
0x14002eb5f  sub     rsp, 70h
0x14002eb63  mov     rax, cs:__security_cookie
0x14002eb6a  xor     rax, rsp
0x14002eb6d  mov     [rsp+98h+var_38], rax
0x14002eb72  mov     edi, r8d
0x14002eb75  mov     rbp, rdx
0x14002eb78  mov     rbx, rcx
0x14002eb7b  test    rdx, rdx
0x14002eb7e  jnz     short loc_14002EBAB
0x14002eb80  test    r8d, r8d
0x14002eb83  jz      short loc_14002EBAB
0x14002eb85  mov     ebx, 80070057h
0x14002eb8a  lea     edx, [rbp+60h]; void *
0x14002eb8d  mov     rcx, [rsp+98h]; this
0x14002eb95  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002eb9c  mov     r9d, ebx; char *
0x14002eb9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002eba4  mov     eax, ebx
0x14002eba6  jmp     loc_14002ED32
0x14002ebab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002ebb2  mov     ecx, 28h ; '('; unsigned __int64
0x14002ebb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002ebbc  test    rax, rax
0x14002ebbf  jz      short loc_14002EBEB
0x14002ebc1  lea     rcx, ??_7?$CSusListIterator@VCOutputMemoryFile@@@@6B@; const CSusListIterator<COutputMemoryFile>::`vftable'
0x14002ebc8  mov     qword ptr [rax+18h], 0
0x14002ebd0  mov     [rax], rcx
0x14002ebd3  mov     qword ptr [rax+8], 0
0x14002ebdb  mov     qword ptr [rax+10h], 0
0x14002ebe3  mov     qword ptr [rax+20h], 0
0x14002ebeb  mov     [rbx+40h], rax
0x14002ebef  test    rax, rax
0x14002ebf2  jnz     short loc_14002EBFE
0x14002ebf4  mov     ebx, 8007000Eh
0x14002ebf9  lea     edx, [rax+63h]
0x14002ebfc  jmp     short loc_14002EB8D
0x14002ebfe  lea     rax, [rbx+18h]
0x14002ec02  mov     [rsp+98h+perf], rax; perf
0x14002ec07  lea     r9, ?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z; pfnread
0x14002ec0e  mov     [rsp+98h+cpuType], 0; cpuType
0x14002ec16  lea     rax, ?CabDecompressorFileSeek@CCabDecompressor@@CAJ_JJH@Z; CCabDecompressor::CabDecompressorFileSeek(__int64,long,int)
0x14002ec1d  mov     [rsp+98h+pfnseek], rax; pfnseek
0x14002ec22  lea     r8, ?CabDecompressorFileOpen@CCabDecompressor@@CA_JPEBDHH@Z; pfnopen
0x14002ec29  lea     rax, ?CabDecompressorFileClose@CCabDecompressor@@CAH_J@Z; CCabDecompressor::CabDecompressorFileClose(__int64)
0x14002ec30  mov     [rsp+98h+pfnclose], rax; pfnclose
0x14002ec35  lea     rdx, ?CabDecompressorMemFree@CCabDecompressor@@CAXPEAX@Z; pfnfree
0x14002ec3c  lea     rax, ?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z; CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)
0x14002ec43  lea     rcx, ?CabDecompressorMemAlloc@CCabDecompressor@@CAPEAXK@Z; pfnalloc
0x14002ec4a  mov     [rsp+98h+pfnwrite], rax; int
0x14002ec4f  call    cs:__imp_FDICreate
0x14002ec55  mov     [rbx+28h], rax
0x14002ec59  test    rax, rax
0x14002ec5c  jnz     short loc_14002EC7A
0x14002ec5e  mov     rcx, rbx; this
0x14002ec61  call    ?GetLastFDIErrorHr@CCabDecompressor@@QEAAJXZ; CCabDecompressor::GetLastFDIErrorHr(void)
0x14002ec66  mov     ebx, eax
0x14002ec68  test    eax, eax
0x14002ec6a  jns     loc_14002EBA4
0x14002ec70  mov     edx, 75h ; 'u'
0x14002ec75  jmp     loc_14002EB8D
0x14002ec7a  xorps   xmm0, xmm0
0x14002ec7d  lea     rcx, [rsp+98h+pguid]; pguid
0x14002ec82  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x14002ec87  call    cs:__imp_CoCreateGuid
0x14002ec8d  mov     esi, eax
0x14002ec8f  test    eax, eax
0x14002ec91  jns     short loc_14002ECB3
0x14002ec93  mov     edx, 81h; void *
0x14002ec98  mov     rcx, [rsp+98h]; this
0x14002eca0  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002eca7  mov     r9d, esi; char *
0x14002ecaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002ecaf  mov     eax, esi
0x14002ecb1  jmp     short loc_14002ED32
0x14002ecb3  lea     rdx, [rbx+30h]; StringUuid
0x14002ecb7  lea     rcx, [rsp+98h+pguid]; Uuid
0x14002ecbc  call    cs:__imp_UuidToStringA
0x14002ecc2  mov     esi, eax
0x14002ecc4  test    eax, eax
0x14002ecc6  jns     short loc_14002ECCF
0x14002ecc8  mov     edx, 83h
0x14002eccd  jmp     short loc_14002EC98
0x14002eccf  mov     edx, edi
0x14002ecd1  lea     rcx, [rbx+50h]
0x14002ecd5  call    ?Grow@?$CSusArrayList@PEADVCSusSortedArrayListItemOpsLPSTR@@@@QEAAJK@Z; CSusArrayList<char *,CSusSortedArrayListItemOpsLPSTR>::Grow(ulong)
0x14002ecda  mov     esi, eax
0x14002ecdc  test    eax, eax
0x14002ecde  jns     short loc_14002ECE7
0x14002ece0  mov     edx, 88h
0x14002ece5  jmp     short loc_14002EC98
0x14002ece7  test    edi, edi
0x14002ece9  jz      short loc_14002ED04
0x14002eceb  mov     rsi, rdi
0x14002ecee  mov     rdx, rbp
0x14002ecf1  lea     rcx, [rbx+50h]
0x14002ecf5  call    ?Add@?$CSusSortedArrayList@PEBDVCSusSortedArrayListItemOpsLPCSTRNoDelete@CCabDecompressor@@@@QEAAJAEBQEBDK@Z; CSusSortedArrayList<char const *,CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete>::Add(char const * const &,ulong)
0x14002ecfa  add     rbp, 8
0x14002ecfe  sub     rsi, 1
0x14002ed02  jnz     short loc_14002ECEE
0x14002ed04  mov     eax, [rsp+98h+arg_20]
0x14002ed0b  mov     [rbx+98h], eax
0x14002ed11  xor     eax, eax
0x14002ed13  mov     [rbx+70h], edi
0x14002ed16  mov     qword ptr [rbx+90h], 0
0x14002ed21  mov     dword ptr [rbx+9Ch], 0
0x14002ed2b  mov     dword ptr [rbx+48h], 1
0x14002ed32  mov     rcx, [rsp+98h+var_38]
0x14002ed37  xor     rcx, rsp; StackCookie
0x14002ed3a  call    __security_check_cookie
0x14002ed3f  add     rsp, 70h
0x14002ed43  pop     r14
0x14002ed45  pop     rdi
0x14002ed46  pop     rsi
0x14002ed47  pop     rbp
0x14002ed48  pop     rbx
0x14002ed49  retn
```
