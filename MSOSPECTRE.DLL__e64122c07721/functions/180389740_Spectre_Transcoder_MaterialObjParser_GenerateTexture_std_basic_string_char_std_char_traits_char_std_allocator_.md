# Spectre::Transcoder::MaterialObjParser::GenerateTexture(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180389740`
- end: `0x1803899e6`
- name: `?GenerateTexture@MaterialObjParser@Transcoder@Spectre@@IEAA?AV?$shared_ptr@VTextureDescriptor@Transcoder@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `678`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1803899f0`

## callees

- `0x180015770`
- `0x1800157b0`
- `0x1801cd320`
- `0x180357e10`
- `0x180389740`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039ebc0`
- `0x18039f8e0`
- `0x18039f910`
- `0x180490890`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180389858`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180389858`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1803897d5`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1803897d5`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1803897b8`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180389849`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1803897b8`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180389849`

## string_xrefs

- `0x1803899b2`: `Failed to read the entire stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Spectre::Transcoder::MaterialObjParser::GenerateTexture(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rdi
  __int128 *v6; // r9
  __int128 *v7; // rcx
  unsigned __int64 v8; // r14
  void *v9; // rax
  void *v10; // rbx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  __int64 v13; // rax
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  __int128 v17; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v18; // [rsp+48h] [rbp-91h]
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-79h] BYREF
  char v20[24]; // [rsp+A0h] [rbp-39h] BYREF
  void *Block; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v22; // [rsp+C0h] [rbp-19h] BYREF
  _DWORD *v23; // [rsp+D0h] [rbp-9h]
  _DWORD *v24; // [rsp+D8h] [rbp-1h]

  v22 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), &v22);
  v5 = v22;
  if ( (_QWORD)v22 )
  {
    Block = 0;
    std::istream::seekg(v22, 0, 2);
    v17 = 0;
    v18 = 0;
    v6 = (__int128 *)std::istream::tellg(v5, v20);
    v7 = &v17;
    if ( *(_QWORD *)v6 + *((_QWORD *)v6 + 1) >= _mm_srli_si128((__m128i)0LL, 8).m128i_i64[0] )
      v7 = v6;
    v8 = *(_QWORD *)v7 + *((_QWORD *)v7 + 1);
    v9 = operator new[](v8);
    v10 = v9;
    if ( v9 )
      memset_0(v9, 0, v8);
    else
      v10 = 0;
    std::istream::seekg(v5, 0, 0);
    std::istream::read(v5, v10, v8);
    if ( *(_QWORD *)(v5 + 8) != v8 )
    {
      std::string::string(&v17, "Failed to read the entire stream");
      Spectre::Utils::SpectreException::SpectreException(pExceptionObject, &v17, 0);
      throw (Spectre::Utils::SpectreException *)pExceptionObject;
    }
    Block = v10;
    v11 = operator new(0x98u);
    v12 = v11;
    if ( v11 )
    {
      *(_OWORD *)v11 = 0;
      v11[2] = 1;
      v11[3] = 1;
      *(_QWORD *)v11 = &std::_Ref_count_obj2<Spectre::Transcoder::TextureDescriptor>::`vftable';
      Spectre::Transcoder::TextureDescriptor::TextureDescriptor(
        (__int64)(v11 + 4),
        (Spectre::ImagingV2::ImagingComponent **)&Block,
        v8);
    }
    else
    {
      v12 = 0;
    }
    v23 = v12 + 4;
    v24 = v12;
    v13 = std::string::string(pExceptionObject, a3);
    Spectre::Transcoder::ITraversableWithName::SetName(v12 + 4, v13);
    *a2 = v12 + 4;
    a2[1] = v12;
    if ( Block )
      operator delete(Block);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
  }
  else
  {
    v15 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    *a2 = 0;
    a2[1] = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180389740  push    rbp
0x180389742  push    rbx
0x180389743  push    rsi
0x180389744  push    rdi
0x180389745  push    r12
0x180389747  push    r14
0x180389749  push    r15
0x18038974b  lea     rbp, [rsp-27h]
0x180389750  sub     rsp, 100h
0x180389757  movaps  [rsp+130h+var_40], xmm6
0x18038975f  mov     rax, cs:__security_cookie
0x180389766  xor     rax, rsp
0x180389769  mov     [rbp+57h+var_50], rax
0x18038976d  mov     r15, r8
0x180389770  mov     rsi, rdx
0x180389773  mov     [rsp+130h+var_108], rdx
0x180389778  xor     r12d, r12d
0x18038977b  mov     [rsp+130h+var_110], r12d
0x180389780  xorps   xmm0, xmm0
0x180389783  movups  [rbp+57h+var_70], xmm0
0x180389787  mov     rcx, [rcx+8]
0x18038978b  mov     rax, [rcx]
0x18038978e  lea     rdx, [rbp+57h+var_70]
0x180389792  mov     rax, [rax+8]
0x180389796  call    cs:__guard_dispatch_icall_fptr
0x18038979c  nop
0x18038979d  mov     rdi, qword ptr [rbp+57h+var_70]
0x1803897a1  test    rdi, rdi
0x1803897a4  jz      loc_18038993F
0x1803897aa  mov     [rbp+57h+Block], r12
0x1803897ae  xor     edx, edx
0x1803897b0  lea     r8d, [r12+2]
0x1803897b5  mov     rcx, rdi
0x1803897b8  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1803897be  xorps   xmm6, xmm6
0x1803897c1  movdqu  [rsp+130h+var_F8], xmm6
0x1803897c7  xor     eax, eax
0x1803897c9  mov     [rsp+130h+var_E8], rax
0x1803897ce  lea     rdx, [rbp+57h+var_90]
0x1803897d2  mov     rcx, rdi
0x1803897d5  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x1803897db  mov     r9, rax
0x1803897de  mov     r8, [rax+8]
0x1803897e2  add     r8, [rax]
0x1803897e5  xorps   xmm0, xmm0
0x1803897e8  psrldq  xmm0, 8
0x1803897ed  movq    rdx, xmm0
0x1803897f2  movq    rax, xmm6
0x1803897f7  add     rdx, rax
0x1803897fa  lea     rcx, [rsp+130h+var_F8]
0x1803897ff  cmp     r8, rdx
0x180389802  cmovge  rcx, r9
0x180389806  mov     r14, [rcx+8]
0x18038980a  add     r14, [rcx]
0x18038980d  mov     [rsp+130h+var_108], r12
0x180389812  mov     rcx, r14; unsigned __int64
0x180389815  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18038981a  mov     rbx, rax
0x18038981d  test    rax, rax
0x180389820  jz      short loc_180389831
0x180389822  mov     r8, r14; Size
0x180389825  xor     edx, edx; Val
0x180389827  mov     rcx, rax; void *
0x18038982a  call    memset_0
0x18038982f  jmp     short loc_180389834
0x180389831  mov     rbx, r12
0x180389834  mov     [rsp+130h+var_108], rbx
0x180389839  mov     [rsp+130h+var_110], 6
0x180389841  xor     r8d, r8d
0x180389844  xor     edx, edx
0x180389846  mov     rcx, rdi
0x180389849  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18038984f  mov     r8, r14
0x180389852  mov     rdx, rbx
0x180389855  mov     rcx, rdi
0x180389858  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18038985e  cmp     [rdi+8], r14
0x180389862  jnz     loc_1803899B2
0x180389868  mov     [rbp+57h+Block], rbx
0x18038986c  mov     ecx, 98h; Size
0x180389871  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180389876  mov     rdi, rax
0x180389879  mov     [rsp+130h+var_100], rax
0x18038987e  test    rax, rax
0x180389881  jz      short loc_1803898B3
0x180389883  xorps   xmm0, xmm0
0x180389886  movups  xmmword ptr [rax], xmm0
0x180389889  mov     dword ptr [rax+8], 1
0x180389890  mov     dword ptr [rax+0Ch], 1
0x180389897  lea     rax, ??_7?$_Ref_count_obj2@VTextureDescriptor@Transcoder@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Transcoder::TextureDescriptor>::`vftable'
0x18038989e  mov     [rdi], rax
0x1803898a1  lea     rcx, [rdi+10h]
0x1803898a5  mov     r8, r14
0x1803898a8  lea     rdx, [rbp+57h+Block]
0x1803898ac  call    ??0TextureDescriptor@Transcoder@Spectre@@QEAA@$$QEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@_K@Z; Spectre::Transcoder::TextureDescriptor::TextureDescriptor(std::unique_ptr<uchar [0]> &&,unsigned __int64)
0x1803898b1  jmp     short loc_1803898B6
0x1803898b3  mov     rdi, r12
0x1803898b6  xorps   xmm0, xmm0
0x1803898b9  movups  [rbp+57h+var_60], xmm0
0x1803898bd  lea     rbx, [rdi+10h]
0x1803898c1  mov     qword ptr [rbp+57h+var_60], rbx
0x1803898c5  mov     qword ptr [rbp+57h+var_60+8], rdi
0x1803898c9  mov     rdx, r15
0x1803898cc  lea     rcx, [rbp+57h+pExceptionObject]
0x1803898d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1803898d5  mov     rdx, rax
0x1803898d8  mov     rcx, rbx
0x1803898db  call    ?SetName@ITraversableWithName@Transcoder@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Transcoder::ITraversableWithName::SetName(std::string)
0x1803898e0  mov     [rsi], rbx
0x1803898e3  mov     [rsi+8], rdi
0x1803898e7  mov     rcx, [rbp+57h+Block]; Block
0x1803898eb  test    rcx, rcx
0x1803898ee  jz      short loc_1803898F6
0x1803898f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1803898f5  nop
0x1803898f6  mov     rdi, qword ptr [rbp+57h+var_70+8]
0x1803898fa  test    rdi, rdi
0x1803898fd  jz      loc_180389989
0x180389903  mov     ebx, 0FFFFFFFFh
0x180389908  mov     eax, ebx
0x18038990a  lock xadd [rdi+8], eax
0x18038990f  cmp     eax, 1
0x180389912  jnz     short loc_180389989
0x180389914  mov     rax, [rdi]
0x180389917  mov     rcx, rdi
0x18038991a  mov     rax, [rax]
0x18038991d  call    cs:__guard_dispatch_icall_fptr
0x180389923  lock xadd [rdi+0Ch], ebx
0x180389928  cmp     ebx, 1
0x18038992b  jnz     short loc_180389989
0x18038992d  mov     rdx, [rdi]
0x180389930  mov     rcx, rdi
0x180389933  mov     rax, [rdx+8]
0x180389937  call    cs:__guard_dispatch_icall_fptr
0x18038993d  jmp     short loc_180389989
0x18038993f  mov     rdi, qword ptr [rbp+57h+var_70+8]
0x180389943  test    rdi, rdi
0x180389946  jz      short loc_180389982
0x180389948  mov     ebx, 0FFFFFFFFh
0x18038994d  mov     eax, ebx
0x18038994f  lock xadd [rdi+8], eax
0x180389954  cmp     eax, 1
0x180389957  jnz     short loc_180389982
0x180389959  mov     rax, [rdi]
0x18038995c  mov     rcx, rdi
0x18038995f  mov     rax, [rax]
0x180389962  call    cs:__guard_dispatch_icall_fptr
0x180389968  lock xadd [rdi+0Ch], ebx
0x18038996d  cmp     ebx, 1
0x180389970  jnz     short loc_180389982
0x180389972  mov     rax, [rdi]
0x180389975  mov     rcx, rdi
0x180389978  mov     rax, [rax+8]
0x18038997c  call    cs:__guard_dispatch_icall_fptr
0x180389982  mov     [rsi], r12
0x180389985  mov     [rsi+8], r12
0x180389989  mov     rax, rsi
0x18038998c  mov     rcx, [rbp+57h+var_50]
0x180389990  xor     rcx, rsp; StackCookie
0x180389993  call    __security_check_cookie
0x180389998  movaps  xmm6, [rsp+130h+var_40]
0x1803899a0  add     rsp, 100h
0x1803899a7  pop     r15
0x1803899a9  pop     r14
0x1803899ab  pop     r12
0x1803899ad  pop     rdi
0x1803899ae  pop     rsi
0x1803899af  pop     rbx
0x1803899b0  pop     rbp
0x1803899b1  retn
0x1803899b2  lea     rdx, aFailedToReadTh; "Failed to read the entire stream"
0x1803899b9  lea     rcx, [rsp+130h+var_F8]
0x1803899be  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1803899c3  nop
0x1803899c4  xor     r8d, r8d
0x1803899c7  lea     rdx, [rsp+130h+var_F8]
0x1803899cc  lea     rcx, [rbp+57h+pExceptionObject]
0x1803899d0  call    ??0SpectreException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreException::SpectreException(std::string const &,bool)
0x1803899d5  lea     rdx, _TI3?AUSpectreException@Utils@Spectre@@; pThrowInfo
0x1803899dc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1803899e0  call    _CxxThrowException_0
```
