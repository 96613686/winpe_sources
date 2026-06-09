# PWGRCore::CPWGRBitmapEncoder::EncodeBitmapToStream(Microsoft::WRL::ComPtr<IPageBitmapProvider> const &,Microsoft::WRL::ComPtr<IStream> const &)

- ea: `0x18000c514`
- end: `0x18000c78f`
- name: `?EncodeBitmapToStream@CPWGRBitmapEncoder@PWGRCore@@QEAAXAEBV?$ComPtr@UIPageBitmapProvider@@@WRL@Microsoft@@AEBV?$ComPtr@UIStream@@@45@@Z`
- size: `635`
- prototype: `__int64 __fastcall(PWGRCore::CPWGRBitmapEncoder *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180009e3c`

## callees

- `0x1800021a0`
- `0x180002d30`
- `0x18000a0ac`
- `0x18000ae2c`
- `0x18000aef4`
- `0x18000afcc`
- `0x18000b094`
- `0x18000b170`
- `0x18000b238`
- `0x18000c514`
- `0x18000c798`
- `0x18000c7c4`
- `0x18000c89c`
- `0x18000c9a8`
- `0x18000d93c`
- `0x18000d9dc`
- `0x18000f544`
- `0x18000f550`
- `0x180011010`

## string_xrefs

- `0x18000c76a`: `Failed to write to ouput Stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PWGRCore::CPWGRBitmapEncoder::EncodeBitmapToStream(
        PWGRCore::CPWGRBitmapEncoder *this,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rbp
  __int64 v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // edi
  void **v13; // r14
  bool NextLine; // al
  char v15; // di
  int v16; // ecx
  bool v17; // bp
  __int64 v18; // r8
  int v19; // eax
  unsigned int v20; // edi
  unsigned int v21; // edi
  unsigned int v22; // edi
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // eax
  void *v27; // rdx
  unsigned int v28; // r8d
  unsigned int v29; // [rsp+20h] [rbp-68h]
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v32; // [rsp+90h] [rbp+8h] BYREF

  v5 = (_QWORD *)((char *)this + 8);
  v6 = *((_QWORD *)this + 1);
  if ( v6 != *((_QWORD *)this + 2) )
    *((_QWORD *)this + 2) = v6;
  v7 = *a3;
  if ( *(_QWORD *)this != *a3 )
  {
    if ( v7 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 8LL))(*a3);
    v8 = *(_QWORD *)this;
    *(_QWORD *)this = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *((_QWORD *)this + 5) = 0;
  v9 = *((_QWORD *)this + 7);
  v10 = *a2;
  if ( *(_QWORD *)(v9 + 24) != *a2 )
  {
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*a2);
    v11 = *(_QWORD *)(v9 + 24);
    *(_QWORD *)(v9 + 24) = v10;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  PWGRCore::CPWGRBitmapWrapper::_InitializeBuffer((PWGRCore::CPWGRBitmapWrapper *)v9, *(_DWORD *)(v9 + 72));
  PWGRCore::CPWGRBitmapWrapper::_GetNextImageBand((PWGRCore::CPWGRBitmapWrapper *)v9);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 7) + 24LL) + 64LL))(*(_QWORD *)(*((_QWORD *)this + 7) + 24LL));
  *((_DWORD *)this + 8) = *(_DWORD *)(*((_QWORD *)this + 7) + 56LL);
  v13 = (void **)((char *)this + 72);
  std::vector<unsigned char>::resize((char *)this + 72);
  if ( v12 >= 8 )
  {
    v20 = v12 >> 3;
    *((_DWORD *)this + 12) = v20;
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 2;
            if ( v25 )
            {
              if ( v25 != 2 )
              {
                v26 = wil::verify_hresult<long>(2147942487LL);
                wil::details::in1diag3::Throw_Hr(retaddr, v27, v28, (const char *)v26, v29);
              }
              PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<8>(this);
            }
            else
            {
              PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<6>(this);
            }
          }
          else
          {
            PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<4>(this);
          }
        }
        else
        {
          PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<3>(this);
        }
      }
      else
      {
        PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<2>(this);
      }
      goto LABEL_22;
    }
  }
  else
  {
    *((_DWORD *)this + 12) = 1;
  }
  NextLine = PWGRCore::CPWGRBitmapEncoder::_GetNextLine(this);
  *((_DWORD *)this + 9) = *((_DWORD *)this + 8);
  if ( !NextLine )
  {
    do
    {
      memcpy_0(*v13, *((const void **)this + 5), *((unsigned int *)this + 8));
      v15 = 0;
      while ( 1 )
      {
        v17 = PWGRCore::CPWGRBitmapEncoder::_GetNextLine(this);
        if ( v17 || memcmp_0(*v13, *((const void **)this + 5), *((unsigned int *)this + 8)) )
          break;
        if ( ++v15 == -1 )
        {
          v17 = PWGRCore::CPWGRBitmapEncoder::_GetNextLine(this);
          break;
        }
      }
      PWGRCore::CPWGRBitmapEncoder::_EncodeImageScanLine<1>(
        v16,
        (_DWORD)v5,
        (unsigned int)*v13,
        *((_DWORD *)this + 9),
        v15);
      PWGRCore::CPWGRBitmapEncoder::_CheckAndWritetoStream(this);
    }
    while ( !v17 );
  }
LABEL_22:
  v18 = v5[1] - *v5;
  if ( v18 )
  {
    v32 = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *))(**(_QWORD **)this + 32LL))(
            *(_QWORD *)this,
            *v5,
            v18,
            &v32);
    if ( v19 < 0 )
    {
      PrintCore::WindowsError::WindowsError(
        (PrintCore::WindowsError *)pExceptionObject,
        v19,
        "Failed to write to ouput Stream",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pwgraster\\pwgrcore\\pwgrbitmapencoder.cpp",
        0x6Fu);
      throw (PrintCore::WindowsError *)pExceptionObject;
    }
    std::vector<unsigned char>::resize(v5);
  }
}

```

## disassembly

```asm
0x18000c514  mov     [rsp+arg_8], rbx
0x18000c519  mov     [rsp+arg_10], rbp
0x18000c51e  push    rsi
0x18000c51f  push    rdi
0x18000c520  push    r14
0x18000c522  sub     rsp, 70h
0x18000c526  mov     r14, rdx
0x18000c529  mov     rbx, rcx
0x18000c52c  lea     rsi, [rcx+8]
0x18000c530  mov     rax, [rsi]
0x18000c533  cmp     rax, [rsi+8]
0x18000c537  jz      short loc_18000C53D
0x18000c539  mov     [rsi+8], rax
0x18000c53d  mov     rdi, [r8]
0x18000c540  cmp     [rcx], rdi
0x18000c543  jz      short loc_18000C572
0x18000c545  test    rdi, rdi
0x18000c548  jz      short loc_18000C55A
0x18000c54a  mov     rax, [rdi]
0x18000c54d  mov     rcx, rdi
0x18000c550  mov     rax, [rax+8]
0x18000c554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c559  nop
0x18000c55a  mov     rcx, [rbx]
0x18000c55d  mov     [rbx], rdi
0x18000c560  test    rcx, rcx
0x18000c563  jz      short loc_18000C572
0x18000c565  mov     rax, [rcx]
0x18000c568  mov     rax, [rax+10h]
0x18000c56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c571  nop
0x18000c572  mov     qword ptr [rbx+28h], 0
0x18000c57a  mov     rbp, [rbx+38h]
0x18000c57e  mov     rdi, [r14]
0x18000c581  cmp     [rbp+18h], rdi
0x18000c585  jz      short loc_18000C5B6
0x18000c587  test    rdi, rdi
0x18000c58a  jz      short loc_18000C59C
0x18000c58c  mov     rax, [rdi]
0x18000c58f  mov     rcx, rdi
0x18000c592  mov     rax, [rax+8]
0x18000c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c59b  nop
0x18000c59c  mov     rcx, [rbp+18h]
0x18000c5a0  mov     [rbp+18h], rdi
0x18000c5a4  test    rcx, rcx
0x18000c5a7  jz      short loc_18000C5B6
0x18000c5a9  mov     rax, [rcx]
0x18000c5ac  mov     rax, [rax+10h]
0x18000c5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b5  nop
0x18000c5b6  mov     edx, [rbp+48h]; unsigned int
0x18000c5b9  mov     rcx, rbp; this
0x18000c5bc  call    ?_InitializeBuffer@CPWGRBitmapWrapper@PWGRCore@@AEAAXI@Z; PWGRCore::CPWGRBitmapWrapper::_InitializeBuffer(uint)
0x18000c5c1  mov     rcx, rbp; this
0x18000c5c4  call    ?_GetNextImageBand@CPWGRBitmapWrapper@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapWrapper::_GetNextImageBand(void)
0x18000c5c9  mov     rax, [rbx+38h]
0x18000c5cd  mov     rcx, [rax+18h]
0x18000c5d1  mov     rax, [rcx]
0x18000c5d4  mov     rax, [rax+40h]
0x18000c5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5dd  mov     edi, eax
0x18000c5df  mov     rcx, [rbx+38h]
0x18000c5e3  mov     edx, [rcx+38h]
0x18000c5e6  mov     [rbx+20h], edx
0x18000c5e9  lea     r14, [rbx+48h]
0x18000c5ed  mov     rcx, r14
0x18000c5f0  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000c5f5  cmp     edi, 8
0x18000c5f8  jnb     loc_18000C6D7
0x18000c5fe  mov     dword ptr [rbx+30h], 1
0x18000c605  mov     rcx, rbx; this
0x18000c608  call    ?_GetNextLine@CPWGRBitmapEncoder@PWGRCore@@AEAA_NXZ; PWGRCore::CPWGRBitmapEncoder::_GetNextLine(void)
0x18000c60d  mov     ecx, [rbx+20h]
0x18000c610  mov     [rbx+24h], ecx
0x18000c613  test    al, al
0x18000c615  jnz     short loc_18000C682
0x18000c617  mov     r8d, [rbx+20h]; Size
0x18000c61b  mov     rdx, [rbx+28h]; Src
0x18000c61f  mov     rcx, [r14]; void *
0x18000c622  call    memcpy_0
0x18000c627  xor     dil, dil
0x18000c62a  mov     rcx, rbx; this
0x18000c62d  call    ?_GetNextLine@CPWGRBitmapEncoder@PWGRCore@@AEAA_NXZ; PWGRCore::CPWGRBitmapEncoder::_GetNextLine(void)
0x18000c632  mov     bpl, al
0x18000c635  test    al, al
0x18000c637  jnz     short loc_18000C661
0x18000c639  mov     r8d, [rbx+20h]; Size
0x18000c63d  mov     rdx, [rbx+28h]; Buf2
0x18000c641  mov     rcx, [r14]; Buf1
0x18000c644  call    memcmp_0
0x18000c649  test    eax, eax
0x18000c64b  jnz     short loc_18000C661
0x18000c64d  inc     dil
0x18000c650  cmp     dil, 0FFh
0x18000c654  jnz     short loc_18000C62A
0x18000c656  mov     rcx, rbx; this
0x18000c659  call    ?_GetNextLine@CPWGRBitmapEncoder@PWGRCore@@AEAA_NXZ; PWGRCore::CPWGRBitmapEncoder::_GetNextLine(void)
0x18000c65e  mov     bpl, al
0x18000c661  mov     r9d, [rbx+24h]
0x18000c665  mov     byte ptr [rsp+88h+var_68], dil
0x18000c66a  mov     r8, [r14]
0x18000c66d  mov     rdx, rsi
0x18000c670  call    ??$_EncodeImageScanLine@$00@CPWGRBitmapEncoder@PWGRCore@@AEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAY00$$CBE_KE@Z; PWGRCore::CPWGRBitmapEncoder::_EncodeImageScanLine<1>(std::vector<uchar> &,uchar const (*)[1],unsigned __int64,uchar)
0x18000c675  mov     rcx, rbx; this
0x18000c678  call    ?_CheckAndWritetoStream@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_CheckAndWritetoStream(void)
0x18000c67d  test    bpl, bpl
0x18000c680  jz      short loc_18000C617
0x18000c682  mov     r8, [rsi+8]
0x18000c686  sub     r8, [rsi]
0x18000c689  jz      short loc_18000C6C2
0x18000c68b  mov     [rsp+88h+arg_0], 0
0x18000c696  mov     rcx, [rbx]
0x18000c699  mov     rax, [rcx]
0x18000c69c  lea     r9, [rsp+88h+arg_0]
0x18000c6a4  mov     rdx, [rsi]
0x18000c6a7  mov     rax, [rax+20h]
0x18000c6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b0  test    eax, eax
0x18000c6b2  js      loc_18000C75B
0x18000c6b8  xor     edx, edx
0x18000c6ba  mov     rcx, rsi
0x18000c6bd  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000c6c2  lea     r11, [rsp+88h+var_18]
0x18000c6c7  mov     rbx, [r11+28h]
0x18000c6cb  mov     rbp, [r11+30h]
0x18000c6cf  mov     rsp, r11
0x18000c6d2  pop     r14
0x18000c6d4  pop     rdi
0x18000c6d5  pop     rsi
0x18000c6d6  retn
0x18000c6d7  shr     edi, 3
0x18000c6da  mov     [rbx+30h], edi
0x18000c6dd  sub     edi, 1
0x18000c6e0  jz      loc_18000C605
0x18000c6e6  sub     edi, 1
0x18000c6e9  jz      short loc_18000C733
0x18000c6eb  sub     edi, 1
0x18000c6ee  jz      short loc_18000C726
0x18000c6f0  sub     edi, 1
0x18000c6f3  jz      short loc_18000C719
0x18000c6f5  sub     edi, 2
0x18000c6f8  jz      short loc_18000C70C
0x18000c6fa  cmp     edi, 2
0x18000c6fd  jnz     short loc_18000C740
0x18000c6ff  mov     rcx, rbx; this
0x18000c702  call    ??$_EncodeBuffer@$07@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<8>(void)
0x18000c707  jmp     loc_18000C682
0x18000c70c  mov     rcx, rbx; this
0x18000c70f  call    ??$_EncodeBuffer@$05@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<6>(void)
0x18000c714  jmp     loc_18000C682
0x18000c719  mov     rcx, rbx; this
0x18000c71c  call    ??$_EncodeBuffer@$03@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<4>(void)
0x18000c721  jmp     loc_18000C682
0x18000c726  mov     rcx, rbx; this
0x18000c729  call    ??$_EncodeBuffer@$02@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<3>(void)
0x18000c72e  jmp     loc_18000C682
0x18000c733  mov     rcx, rbx; this
0x18000c736  call    ??$_EncodeBuffer@$01@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapEncoder::_EncodeBuffer<2>(void)
0x18000c73b  jmp     loc_18000C682
0x18000c740  mov     ecx, 80070057h
0x18000c745  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c74a  mov     r9d, eax; char *
0x18000c74d  mov     rcx, [rsp+88h]; this
0x18000c755  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c75b  mov     [rsp+88h+var_68], 6Fh ; 'o'; unsigned int
0x18000c763  lea     r9, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c76a  lea     r8, aFailedToWriteT; "Failed to write to ouput Stream"
0x18000c771  mov     edx, eax; int
0x18000c773  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000c778  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x18000c77d  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x18000c784  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000c789  call    _CxxThrowException_0
```
