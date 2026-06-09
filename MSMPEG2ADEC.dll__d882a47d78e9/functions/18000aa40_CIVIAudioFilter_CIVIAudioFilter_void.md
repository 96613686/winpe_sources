# CIVIAudioFilter::~CIVIAudioFilter(void)

- ea: `0x18000aa40`
- end: `0x18000ac91`
- name: `??1CIVIAudioFilter@@UEAA@XZ`
- size: `593`
- prototype: `void __fastcall(CIVIAudioFilter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000ae90`

## callees

- `0x1800013a0`
- `0x180001b80`
- `0x18000aa40`
- `0x180018e90`
- `0x180028cf0`
- `0x180050f60`
- `0x180051440`
- `0x180066d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000aaee`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000aafd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab4a`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab68`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab97`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000aaee`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000aafd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab4a`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab68`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000ab97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ac3a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ac3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000abec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000abec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac67`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18000aadb`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18000aadb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIVIAudioFilter::~CIVIAudioFilter(CIVIAudioFilter *this)
{
  void *v2; // rcx
  __int64 v3; // rdi
  void *v4; // rsi
  __int64 v5; // rdi
  void *v6; // rcx
  _QWORD *v7; // rsi
  void *v8; // rcx
  _QWORD *v9; // rsi
  void *v10; // rcx
  struct CIntelFFTInfo *v11; // rcx
  HMODULE v12; // rcx

  *(_QWORD *)this = &CIVIAudioFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CIVIAudioFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CNamedTransformFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 29) = &CIVIAudioFilter::`vftable'{for `CIVIAudioCodec'};
  *((_QWORD *)this + 1923) = &CIVIAudioFilter::`vftable'{for `ISpecifyPropertyPages'};
  *((_QWORD *)this + 1924) = &CIVIAudioFilter::`vftable'{for `ICodecAPI'};
  *((_QWORD *)this + 1925) = &CIVIAudioFilter::`vftable'{for `IPersistStream'};
  v2 = (void *)*((_QWORD *)this + 2154);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 2154) = 0;
  }
  v3 = *((_QWORD *)this + 2227);
  if ( v3 )
  {
    v4 = *(void **)v3;
    if ( *(_QWORD *)v3 )
    {
      ippsFFTFree_R_32f(*((_QWORD *)v4 + 29));
      _aligned_free(*((void **)v4 + 30));
      _aligned_free(*(void **)v3);
      *(_QWORD *)v3 = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 56));
    operator delete((void *)v3);
    *((_QWORD *)this + 2227) = 0;
  }
  v5 = *((_QWORD *)this + 2228);
  if ( v5 )
  {
    v6 = *(void **)(v5 + 112);
    if ( v6 )
      _aligned_free(v6);
    v7 = *(_QWORD **)(v5 + 80);
    if ( v7 )
    {
      v8 = (void *)v7[3];
      if ( v8 )
      {
        _aligned_free(v8);
        v7[3] = 0;
      }
      operator delete(v7);
    }
    v9 = *(_QWORD **)(v5 + 88);
    if ( v9 )
    {
      v10 = (void *)v9[3];
      if ( v10 )
      {
        _aligned_free(v10);
        v9[3] = 0;
      }
      operator delete(v9);
    }
    CAudioTimeCompression::freeTemps((CAudioTimeCompression *)v5);
    if ( *(_BYTE *)(v5 + 120) == 1 )
    {
      _InterlockedDecrement(&dword_1800ADBEC);
      *(_BYTE *)(v5 + 120) = 0;
      v11 = *(struct CIntelFFTInfo **)(v5 + 128);
      if ( v11 )
      {
        auippDeleteFFTInfo(v11);
        *(_QWORD *)(v5 + 128) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(v5 + 224));
    operator delete((void *)v5);
    *((_QWORD *)this + 2228) = 0;
  }
  DRM_Release(*((void **)this + 2148));
  *((_QWORD *)this + 2158) = 0;
  *((_QWORD *)this + 2157) = 0;
  *((_QWORD *)this + 2159) = 0;
  v12 = (HMODULE)*((_QWORD *)this + 2156);
  if ( v12 )
    FreeLibrary(v12);
  *((_QWORD *)this + 2156) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 387);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 15408));
  CIVIAudioCodec::~CIVIAudioCodec((CIVIAudioFilter *)((char *)this + 232));
  CTransformFilter::~CTransformFilter(this);
}

```

## disassembly

```asm
0x18000aa40  push    rbx
0x18000aa42  push    rbp
0x18000aa43  push    rsi
0x18000aa44  push    rdi
0x18000aa45  push    r14
0x18000aa47  sub     rsp, 20h
0x18000aa4b  mov     rbx, rcx
0x18000aa4e  lea     rax, ??_7CIVIAudioFilter@@6BCUnknown@@@; const CIVIAudioFilter::`vftable'{for `CUnknown'}
0x18000aa55  mov     [rcx], rax
0x18000aa58  lea     rax, ??_7CIVIAudioFilter@@6BIBaseFilter@@@; const CIVIAudioFilter::`vftable'{for `IBaseFilter'}
0x18000aa5f  mov     [rcx+18h], rax
0x18000aa63  lea     rax, ??_7CNamedTransformFilter@@6BIAMovieSetup@@@; const CNamedTransformFilter::`vftable'{for `IAMovieSetup'}
0x18000aa6a  mov     [rcx+20h], rax
0x18000aa6e  lea     rax, ??_7CIVIAudioFilter@@6BCIVIAudioCodec@@@; const CIVIAudioFilter::`vftable'{for `CIVIAudioCodec'}
0x18000aa75  mov     [rcx+0E8h], rax
0x18000aa7c  lea     rax, ??_7CIVIAudioFilter@@6BISpecifyPropertyPages@@@; const CIVIAudioFilter::`vftable'{for `ISpecifyPropertyPages'}
0x18000aa83  mov     [rcx+3C18h], rax
0x18000aa8a  lea     rax, ??_7CIVIAudioFilter@@6BICodecAPI@@@; const CIVIAudioFilter::`vftable'{for `ICodecAPI'}
0x18000aa91  mov     [rcx+3C20h], rax
0x18000aa98  lea     rax, ??_7CIVIAudioFilter@@6BIPersistStream@@@; const CIVIAudioFilter::`vftable'{for `IPersistStream'}
0x18000aa9f  mov     [rcx+3C28h], rax
0x18000aaa6  mov     rcx, [rcx+4350h]; Block
0x18000aaad  xor     ebp, ebp
0x18000aaaf  test    rcx, rcx
0x18000aab2  jz      short loc_18000AAC0
0x18000aab4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aab9  mov     [rbx+4350h], rbp
0x18000aac0  mov     rdi, [rbx+4598h]
0x18000aac7  test    rdi, rdi
0x18000aaca  jz      short loc_18000AB31
0x18000aacc  mov     rsi, [rdi]
0x18000aacf  test    rsi, rsi
0x18000aad2  jz      short loc_18000AB0C
0x18000aad4  mov     rcx, [rsi+0E8h]
0x18000aadb  call    cs:__imp_ippsFFTFree_R_32f
0x18000aae2  nop     dword ptr [rax+rax+00h]
0x18000aae7  mov     rcx, [rsi+0F0h]; Block
0x18000aaee  call    cs:__imp__aligned_free
0x18000aaf5  nop     dword ptr [rax+rax+00h]
0x18000aafa  mov     rcx, [rdi]; Block
0x18000aafd  call    cs:__imp__aligned_free
0x18000ab04  nop     dword ptr [rax+rax+00h]
0x18000ab09  mov     [rdi], rbp
0x18000ab0c  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000ab10  call    cs:__imp_DeleteCriticalSection
0x18000ab17  nop     dword ptr [rax+rax+00h]
0x18000ab1c  nop
0x18000ab1d  mov     edx, 70h ; 'p'
0x18000ab22  mov     rcx, rdi; Block
0x18000ab25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab2a  mov     [rbx+4598h], rbp
0x18000ab31  mov     rdi, [rbx+45A0h]
0x18000ab38  test    rdi, rdi
0x18000ab3b  jz      loc_18000AC0D
0x18000ab41  mov     rcx, [rdi+70h]; Block
0x18000ab45  test    rcx, rcx
0x18000ab48  jz      short loc_18000AB56
0x18000ab4a  call    cs:__imp__aligned_free
0x18000ab51  nop     dword ptr [rax+rax+00h]
0x18000ab56  mov     rsi, [rdi+50h]
0x18000ab5a  test    rsi, rsi
0x18000ab5d  jz      short loc_18000AB85
0x18000ab5f  mov     rcx, [rsi+18h]; Block
0x18000ab63  test    rcx, rcx
0x18000ab66  jz      short loc_18000AB78
0x18000ab68  call    cs:__imp__aligned_free
0x18000ab6f  nop     dword ptr [rax+rax+00h]
0x18000ab74  mov     [rsi+18h], rbp
0x18000ab78  mov     edx, 20h ; ' '
0x18000ab7d  mov     rcx, rsi; Block
0x18000ab80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab85  mov     rsi, [rdi+58h]
0x18000ab89  test    rsi, rsi
0x18000ab8c  jz      short loc_18000ABB4
0x18000ab8e  mov     rcx, [rsi+18h]; Block
0x18000ab92  test    rcx, rcx
0x18000ab95  jz      short loc_18000ABA7
0x18000ab97  call    cs:__imp__aligned_free
0x18000ab9e  nop     dword ptr [rax+rax+00h]
0x18000aba3  mov     [rsi+18h], rbp
0x18000aba7  mov     edx, 20h ; ' '
0x18000abac  mov     rcx, rsi; Block
0x18000abaf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000abb4  mov     rcx, rdi; this
0x18000abb7  call    ?freeTemps@CAudioTimeCompression@@IEAAJXZ; CAudioTimeCompression::freeTemps(void)
0x18000abbc  cmp     byte ptr [rdi+78h], 1
0x18000abc0  jnz     short loc_18000ABE5
0x18000abc2  lock dec cs:dword_1800ADBEC
0x18000abc9  mov     byte ptr [rdi+78h], 0
0x18000abcd  mov     rcx, [rdi+80h]; Block
0x18000abd4  test    rcx, rcx
0x18000abd7  jz      short loc_18000ABE5
0x18000abd9  call    ?auippDeleteFFTInfo@@YAXPEAUCIntelFFTInfo@@@Z; auippDeleteFFTInfo(CIntelFFTInfo *)
0x18000abde  mov     [rdi+80h], rbp
0x18000abe5  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x18000abec  call    cs:__imp_DeleteCriticalSection
0x18000abf3  nop     dword ptr [rax+rax+00h]
0x18000abf8  nop
0x18000abf9  mov     edx, 108h
0x18000abfe  mov     rcx, rdi; Block
0x18000ac01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac06  mov     [rbx+45A0h], rbp
0x18000ac0d  mov     rcx, [rbx+4320h]; Block
0x18000ac14  call    ?DRM_Release@@YAJPEAX@Z; DRM_Release(void *)
0x18000ac19  mov     [rbx+4370h], rbp
0x18000ac20  mov     [rbx+4368h], rbp
0x18000ac27  mov     [rbx+4378h], rbp
0x18000ac2e  mov     rcx, [rbx+4360h]; hLibModule
0x18000ac35  test    rcx, rcx
0x18000ac38  jz      short loc_18000AC46
0x18000ac3a  call    cs:__imp_FreeLibrary
0x18000ac41  nop     dword ptr [rax+rax+00h]
0x18000ac46  mov     [rbx+4360h], rbp
0x18000ac4d  lea     rcx, [rbx+3C78h]; lpCriticalSection
0x18000ac54  call    cs:__imp_DeleteCriticalSection
0x18000ac5b  nop     dword ptr [rax+rax+00h]
0x18000ac60  lea     rcx, [rbx+3C30h]; lpCriticalSection
0x18000ac67  call    cs:__imp_DeleteCriticalSection
0x18000ac6e  nop     dword ptr [rax+rax+00h]
0x18000ac73  lea     rcx, [rbx+0E8h]; this
0x18000ac7a  call    ??1CIVIAudioCodec@@UEAA@XZ; CIVIAudioCodec::~CIVIAudioCodec(void)
0x18000ac7f  mov     rcx, rbx; this
0x18000ac82  add     rsp, 20h
0x18000ac86  pop     r14
0x18000ac88  pop     rdi
0x18000ac89  pop     rsi
0x18000ac8a  pop     rbp
0x18000ac8b  pop     rbx
0x18000ac8c  jmp     ??1CTransformFilter@@UEAA@XZ; CTransformFilter::~CTransformFilter(void)
```
