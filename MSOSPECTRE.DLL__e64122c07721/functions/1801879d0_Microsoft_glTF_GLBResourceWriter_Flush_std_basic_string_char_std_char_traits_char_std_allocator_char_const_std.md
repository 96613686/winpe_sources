# Microsoft::glTF::GLBResourceWriter::Flush(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1801879d0`
- end: `0x1801880cc`
- name: `?Flush@GLBResourceWriter@glTF@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z`
- size: `1788`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002cfdc`
- `0x1801fcf80`
- `0x18034f040`

## callees

- `0x18001ebf0`
- `0x18008f520`
- `0x180184da0`
- `0x180187430`
- `0x1801879d0`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`

## import_xrefs

- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187b3d`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187b7c`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187bb9`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187bf6`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187c35`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187d0f`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187d4e`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187df5`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187b3d`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187b7c`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187bb9`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187bf6`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187c35`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187d0f`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187d4e`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x180187df5`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x180187d82`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x180187d82`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187ac3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187cd7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187e9f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187ac3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187cd7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180187e9f`

## string_xrefs

- `0x180187ea6`: `Unable to write to buffer.`
- `0x180187ef0`: `Unable to write to buffer.`
- `0x180187f34`: `Unable to write to buffer.`
- `0x180187f76`: `Unable to write to buffer.`
- `0x180187fb8`: `Unable to write to buffer.`
- `0x180187ffa`: `Unable to write to buffer.`
- `0x18018803c`: `Unable to write to buffer.`
- `0x18018807e`: `Unable to write to buffer.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::glTF::GLBResourceWriter::Flush(_QWORD **a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // rsi
  _QWORD *v6; // r12
  int v7; // edx
  unsigned int v8; // r15d
  int v9; // ecx
  void *v10; // rcx
  unsigned __int64 v11; // r14
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 v14; // rdi
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // r8
  _QWORD *v18; // rax
  _QWORD *v19; // rdx
  _BYTE *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdi
  char *v23; // rbx
  __int64 v24; // rsi
  volatile signed __int32 *v25; // rbx
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v27; // [rsp+28h] [rbp-D8h] BYREF
  volatile signed __int32 *v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v31; // [rsp+40h] [rbp-C0h]
  char *v32; // [rsp+50h] [rbp-B0h]
  _BYTE v33[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v36[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v38[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[24]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v40[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v41[24]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v42[24]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v43[24]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v44[24]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v45[24]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v46[24]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v47[24]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  void *Block[3]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int64 v50; // [rsp+1F0h] [rbp+F0h]
  void *v51; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int64 v52; // [rsp+210h] [rbp+110h]

  v4 = a2;
  v6 = a2 + 2;
  v7 = *((_DWORD *)a2 + 4);
  v8 = 4 - (v7 & 3);
  if ( (v7 & 3) == 0 )
    v8 = 0;
  v29 = v7 + v8;
  v50 = 15;
  Block[2] = (void *)11;
  strcpy((char *)Block, "binary_glTF");
  v9 = ((__int64 (__fastcall *)(_QWORD **, void **))(*a1)[3])(a1, Block);
  v26 = v9;
  if ( v50 >= 0x10 )
  {
    v10 = Block[0];
    if ( v50 + 1 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v10);
    v9 = v26;
  }
  LOBYTE(Block[0]) = 0;
  v11 = 4 - (v9 & 3u);
  if ( (v9 & 3) == 0 )
    v11 = 0;
  v26 = v11 + v9;
  v30 = v29 + 28 + v11 + v9;
  (*(void (__fastcall **)(_QWORD *, __int64 *, __int64))(*a1[1] + 8LL))(a1[1], &v27, a3);
  v12 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v33, "The output stream is not in a good state.");
    throw (std::runtime_error *)v33;
  }
  std::ostream::write(v27, "glTF", 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v12 + 4LL) + v12 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v34, "Unable to write to buffer.");
    throw (std::runtime_error *)v34;
  }
  v13 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v35, "The output stream is not in a good state.");
    throw (std::runtime_error *)v35;
  }
  std::ostream::write(v27, &dword_180571E84, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v13 + 4LL) + v13 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v36, "Unable to write to buffer.");
    throw (std::runtime_error *)v36;
  }
  v14 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v37, "The output stream is not in a good state.");
    throw (std::runtime_error *)v37;
  }
  std::ostream::write(v27, &v30, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v14 + 4LL) + v14 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v38, "Unable to write to buffer.");
    throw (std::runtime_error *)v38;
  }
  v15 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v39, "The output stream is not in a good state.");
    throw (std::runtime_error *)v39;
  }
  std::ostream::write(v27, &v29, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v15 + 4LL) + v15 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v40, "Unable to write to buffer.");
    throw (std::runtime_error *)v40;
  }
  v16 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v41, "The output stream is not in a good state.");
    throw (std::runtime_error *)v41;
  }
  std::ostream::write(v27, "JSON", 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v16 + 4LL) + v16 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v42, "Unable to write to buffer.");
    throw (std::runtime_error *)v42;
  }
  if ( v4[3] >= 0x10u )
    v4 = (_QWORD *)*v4;
  Microsoft::glTF::StreamUtils::WriteBinary<void>(v27, v4, *v6);
  if ( v8 )
  {
    _mm_lfence();
    LOBYTE(v17) = 32;
    v18 = (_QWORD *)std::string::string(&v51, v8, v17);
    v19 = v18;
    if ( v18[3] >= 0x10u )
      v19 = (_QWORD *)*v18;
    Microsoft::glTF::StreamUtils::WriteBinary<void>(v27, v19, v18[2]);
    if ( v52 >= 0x10 )
    {
      v20 = v51;
      if ( v52 + 1 >= 0x1000 )
      {
        v20 = (_BYTE *)*((_QWORD *)v51 - 1);
        if ( (unsigned __int64)((_BYTE *)v51 - v20 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v20);
    }
    LOBYTE(v51) = 0;
  }
  v21 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v43, "The output stream is not in a good state.");
    throw (std::runtime_error *)v43;
  }
  std::ostream::write(v27, &v26, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v21 + 4LL) + v21 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v44, "Unable to write to buffer.");
    throw (std::runtime_error *)v44;
  }
  v22 = v27;
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v45, "The output stream is not in a good state.");
    throw (std::runtime_error *)v45;
  }
  std::ostream::write(v27, "BIN", 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v22 + 4LL) + v22 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v46, "Unable to write to buffer.");
    throw (std::runtime_error *)v46;
  }
  if ( v26 )
    std::ostream::operator<<(v27, *(_QWORD *)((char *)a1[14] + *(int *)(*a1[14] + 4LL) + 72));
  if ( (_DWORD)v11 )
  {
    v31 = 0;
    v32 = 0;
    _mm_lfence();
    v23 = (char *)std::_Allocate<16,std::_Default_allocate_traits,0>((unsigned int)v11);
    *(_QWORD *)&v31 = v23;
    v32 = &v23[v11];
    memset_0(v23, 0, (unsigned int)v11);
    *((_QWORD *)&v31 + 1) = &v23[v11];
    v24 = v27;
    if ( *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 16) )
    {
      std::runtime_error::runtime_error((std::runtime_error *)v47, "The output stream is not in a good state.");
      throw (std::runtime_error *)v47;
    }
    std::ostream::write(v27, v23, v11);
    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v24 + 4LL) + v24 + 16) & 6) != 0 )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to write to buffer.");
      throw (std::runtime_error *)pExceptionObject;
    }
    if ( v23 )
    {
      if ( v11 >= 0x1000 )
      {
        if ( (unsigned __int64)&v23[-*((_QWORD *)v23 - 1) - 8] > 0x1F )
          _invalid_parameter_noinfo_noreturn();
        v23 = (char *)*((_QWORD *)v23 - 1);
      }
      operator delete(v23);
    }
  }
  v25 = v28;
  if ( v28 && _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
    if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
  }
}

```

## disassembly

```asm
0x1801879d0  mov     [rsp-8+arg_18], rbx
0x1801879d5  push    rbp
0x1801879d6  push    rsi
0x1801879d7  push    rdi
0x1801879d8  push    r12
0x1801879da  push    r13
0x1801879dc  push    r14
0x1801879de  push    r15
0x1801879e0  lea     rbp, [rsp-120h]
0x1801879e8  sub     rsp, 220h
0x1801879ef  mov     rax, cs:__security_cookie
0x1801879f6  xor     rax, rsp
0x1801879f9  mov     [rbp+150h+var_38], rax
0x180187a00  mov     rdi, r8
0x180187a03  mov     rsi, rdx
0x180187a06  mov     r13, rcx
0x180187a09  lea     r12, [rdx+10h]
0x180187a0d  mov     edx, [r12]
0x180187a11  mov     eax, edx
0x180187a13  and     eax, 3
0x180187a16  mov     r15d, 4
0x180187a1c  sub     r15d, eax
0x180187a1f  xor     ebx, ebx
0x180187a21  test    rax, rax
0x180187a24  cmovz   r15d, ebx
0x180187a28  lea     eax, [rdx+r15]
0x180187a2c  mov     [rsp+250h+var_218], eax
0x180187a30  mov     [rbp+150h+var_60], 0Fh
0x180187a3b  mov     [rbp+150h+var_68], 0Bh
0x180187a46  movsd   xmm0, qword ptr cs:aBinaryGltf; "binary_glTF"
0x180187a4e  movsd   [rbp+150h+Block], xmm0
0x180187a56  movzx   eax, word ptr cs:aBinaryGltf+8; "lTF"
0x180187a5d  mov     [rbp+150h+var_70], ax
0x180187a64  movzx   eax, byte ptr cs:aBinaryGltf+0Ah; "F"
0x180187a6b  mov     [rbp+150h+var_6E], al
0x180187a71  mov     [rbp+150h+var_6D], bl
0x180187a77  mov     rax, [rcx]
0x180187a7a  lea     rdx, [rbp+150h+Block]
0x180187a81  call    qword ptr [rax+18h]
0x180187a84  mov     rcx, rax
0x180187a87  mov     [rsp+250h+var_230], eax
0x180187a8b  mov     rdx, [rbp+150h+var_60]
0x180187a92  cmp     rdx, 10h
0x180187a96  jb      short loc_180187AD3
0x180187a98  inc     rdx
0x180187a9b  mov     rcx, [rbp+150h+Block]; Block
0x180187aa2  mov     rax, rcx
0x180187aa5  cmp     rdx, 1000h
0x180187aac  jb      short loc_180187ACA
0x180187aae  add     rdx, 27h ; '''
0x180187ab2  mov     rcx, [rcx-8]
0x180187ab6  sub     rax, rcx
0x180187ab9  add     rax, 0FFFFFFFFFFFFFFF8h
0x180187abd  cmp     rax, 1Fh
0x180187ac1  jbe     short loc_180187ACA
0x180187ac3  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180187aca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180187acf  mov     ecx, [rsp+250h+var_230]
0x180187ad3  mov     byte ptr [rbp+150h+Block], 0
0x180187ada  mov     eax, ecx
0x180187adc  and     eax, 3
0x180187adf  mov     r14d, 4
0x180187ae5  sub     r14d, eax
0x180187ae8  test    rax, rax
0x180187aeb  cmovz   r14d, ebx
0x180187aef  add     ecx, r14d
0x180187af2  mov     [rsp+250h+var_230], ecx
0x180187af6  mov     eax, [rsp+250h+var_218]
0x180187afa  add     eax, 1Ch
0x180187afd  add     ecx, eax
0x180187aff  mov     [rsp+250h+var_214], ecx
0x180187b03  mov     rcx, [r13+8]
0x180187b07  mov     rax, [rcx]
0x180187b0a  mov     r8, rdi
0x180187b0d  lea     rdx, [rsp+250h+var_228]
0x180187b12  call    qword ptr [rax+8]
0x180187b15  nop
0x180187b16  mov     rdi, [rsp+250h+var_228]
0x180187b1b  mov     rax, [rdi]
0x180187b1e  movsxd  rcx, dword ptr [rax+4]
0x180187b22  cmp     dword ptr [rcx+rdi+10h], 0
0x180187b27  jnz     loc_180187ECD
0x180187b2d  mov     r8d, 4
0x180187b33  lea     rdx, aGltf_1; "glTF"
0x180187b3a  mov     rcx, rdi
0x180187b3d  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187b43  mov     rax, [rdi]
0x180187b46  movsxd  rcx, dword ptr [rax+4]
0x180187b4a  test    byte ptr [rcx+rdi+10h], 6
0x180187b4f  jnz     loc_180187EF0
0x180187b55  mov     rdi, [rsp+250h+var_228]
0x180187b5a  mov     rax, [rdi]
0x180187b5d  movsxd  rcx, dword ptr [rax+4]
0x180187b61  cmp     dword ptr [rcx+rdi+10h], 0
0x180187b66  jnz     loc_180187F13
0x180187b6c  mov     r8d, 4
0x180187b72  lea     rdx, dword_180571E84
0x180187b79  mov     rcx, rdi
0x180187b7c  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187b82  mov     rax, [rdi]
0x180187b85  movsxd  rcx, dword ptr [rax+4]
0x180187b89  test    byte ptr [rcx+rdi+10h], 6
0x180187b8e  jnz     loc_180187F34
0x180187b94  mov     rdi, [rsp+250h+var_228]
0x180187b99  mov     rax, [rdi]
0x180187b9c  movsxd  rcx, dword ptr [rax+4]
0x180187ba0  cmp     dword ptr [rcx+rdi+10h], 0
0x180187ba5  jnz     loc_180187F55
0x180187bab  mov     r8d, 4
0x180187bb1  lea     rdx, [rsp+250h+var_214]
0x180187bb6  mov     rcx, rdi
0x180187bb9  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187bbf  mov     rax, [rdi]
0x180187bc2  movsxd  rcx, dword ptr [rax+4]
0x180187bc6  test    byte ptr [rcx+rdi+10h], 6
0x180187bcb  jnz     loc_180187F76
0x180187bd1  mov     rdi, [rsp+250h+var_228]
0x180187bd6  mov     rax, [rdi]
0x180187bd9  movsxd  rcx, dword ptr [rax+4]
0x180187bdd  cmp     dword ptr [rcx+rdi+10h], 0
0x180187be2  jnz     loc_180187F97
0x180187be8  mov     r8d, 4
0x180187bee  lea     rdx, [rsp+250h+var_218]
0x180187bf3  mov     rcx, rdi
0x180187bf6  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187bfc  mov     rax, [rdi]
0x180187bff  movsxd  rcx, dword ptr [rax+4]
0x180187c03  test    byte ptr [rcx+rdi+10h], 6
0x180187c08  jnz     loc_180187FB8
0x180187c0e  mov     rdi, [rsp+250h+var_228]
0x180187c13  mov     rax, [rdi]
0x180187c16  movsxd  rcx, dword ptr [rax+4]
0x180187c1a  cmp     dword ptr [rcx+rdi+10h], 0
0x180187c1f  jnz     loc_180187FD9
0x180187c25  mov     r8d, 4
0x180187c2b  lea     rdx, aJson; "JSON"
0x180187c32  mov     rcx, rdi
0x180187c35  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187c3b  mov     rax, [rdi]
0x180187c3e  movsxd  rcx, dword ptr [rax+4]
0x180187c42  test    byte ptr [rcx+rdi+10h], 6
0x180187c47  jnz     loc_180187FFA
0x180187c4d  cmp     qword ptr [rsi+18h], 10h
0x180187c52  jb      short loc_180187C57
0x180187c54  mov     rsi, [rsi]
0x180187c57  mov     r8, [r12]
0x180187c5b  mov     rdx, rsi
0x180187c5e  mov     rcx, [rsp+250h+var_228]
0x180187c63  call    ??$WriteBinary@X@StreamUtils@glTF@Microsoft@@SA_KAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX_K@Z; Microsoft::glTF::StreamUtils::WriteBinary<void>(std::ostream &,void const *,unsigned __int64)
0x180187c68  test    r15d, r15d
0x180187c6b  jz      short loc_180187CEA
0x180187c6d  lfence
0x180187c70  mov     edx, r15d
0x180187c73  mov     r8b, 20h ; ' '
0x180187c76  lea     rcx, [rbp+150h+var_58]
0x180187c7d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180187c82  nop
0x180187c83  mov     rdx, rax
0x180187c86  cmp     qword ptr [rax+18h], 10h
0x180187c8b  jb      short loc_180187C90
0x180187c8d  mov     rdx, [rax]
0x180187c90  mov     r8, [rax+10h]
0x180187c94  mov     rcx, [rsp+250h+var_228]
0x180187c99  call    ??$WriteBinary@X@StreamUtils@glTF@Microsoft@@SA_KAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX_K@Z; Microsoft::glTF::StreamUtils::WriteBinary<void>(std::ostream &,void const *,unsigned __int64)
0x180187c9e  nop
0x180187c9f  mov     rdx, [rbp+150h+var_40]
0x180187ca6  cmp     rdx, 10h
0x180187caa  jb      short loc_180187CE3
0x180187cac  inc     rdx
0x180187caf  mov     rcx, [rbp+150h+var_58]; Block
0x180187cb6  mov     rax, rcx
0x180187cb9  cmp     rdx, 1000h
0x180187cc0  jb      short loc_180187CDE
0x180187cc2  add     rdx, 27h ; '''
0x180187cc6  mov     rcx, [rcx-8]
0x180187cca  sub     rax, rcx
0x180187ccd  add     rax, 0FFFFFFFFFFFFFFF8h
0x180187cd1  cmp     rax, 1Fh
0x180187cd5  jbe     short loc_180187CDE
0x180187cd7  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180187cde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180187ce3  mov     byte ptr [rbp+150h+var_58], 0
0x180187cea  mov     rdi, [rsp+250h+var_228]
0x180187cef  mov     rax, [rdi]
0x180187cf2  movsxd  rcx, dword ptr [rax+4]
0x180187cf6  cmp     dword ptr [rcx+rdi+10h], 0
0x180187cfb  jnz     loc_18018801B
0x180187d01  mov     r8d, 4
0x180187d07  lea     rdx, [rsp+250h+var_230]
0x180187d0c  mov     rcx, rdi
0x180187d0f  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187d15  mov     rax, [rdi]
0x180187d18  movsxd  rcx, dword ptr [rax+4]
0x180187d1c  test    byte ptr [rcx+rdi+10h], 6
0x180187d21  jnz     loc_18018803C
0x180187d27  mov     rdi, [rsp+250h+var_228]
0x180187d2c  mov     rax, [rdi]
0x180187d2f  movsxd  rcx, dword ptr [rax+4]
0x180187d33  cmp     dword ptr [rcx+rdi+10h], 0
0x180187d38  jnz     loc_18018805D
0x180187d3e  mov     r8d, 4
0x180187d44  lea     rdx, aBin_0; "BIN"
0x180187d4b  mov     rcx, rdi
0x180187d4e  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187d54  mov     rax, [rdi]
0x180187d57  movsxd  rcx, dword ptr [rax+4]
0x180187d5b  test    byte ptr [rcx+rdi+10h], 6
0x180187d60  jnz     loc_18018807E
0x180187d66  cmp     [rsp+250h+var_230], 0
0x180187d6b  jbe     short loc_180187D88
0x180187d6d  mov     rdx, [r13+70h]
0x180187d71  mov     rax, [rdx]
0x180187d74  movsxd  rcx, dword ptr [rax+4]
0x180187d78  mov     rdx, [rcx+rdx+48h]
0x180187d7d  mov     rcx, [rsp+250h+var_228]
0x180187d82  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::ostream::operator<<(std::streambuf *)
0x180187d88  test    r14d, r14d
0x180187d8b  jz      loc_180187E3F
0x180187d91  mov     esi, r14d
0x180187d94  xorps   xmm0, xmm0
0x180187d97  movdqu  [rsp+250h+var_210], xmm0
0x180187d9d  mov     [rsp+250h+var_200], rbx
0x180187da2  mov     rdi, rbx
0x180187da5  lfence
0x180187da8  mov     ecx, esi
0x180187daa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x180187daf  mov     rbx, rax
0x180187db2  mov     qword ptr [rsp+250h+var_210], rax
0x180187db7  lea     rdi, [rax+r14]
0x180187dbb  mov     [rsp+250h+var_200], rdi
0x180187dc0  mov     r8d, esi; Size
0x180187dc3  xor     edx, edx; Val
0x180187dc5  mov     rcx, rax; void *
0x180187dc8  call    memset_0
0x180187dcd  mov     qword ptr [rsp+250h+var_210+8], rdi
0x180187dd2  mov     rsi, [rsp+250h+var_228]
0x180187dd7  sub     rdi, rbx
0x180187dda  mov     rax, [rsi]
0x180187ddd  movsxd  rcx, dword ptr [rax+4]
0x180187de1  cmp     dword ptr [rcx+rsi+10h], 0
0x180187de6  jnz     loc_1801880A5
0x180187dec  mov     r8, rdi
0x180187def  mov     rdx, rbx
0x180187df2  mov     rcx, rsi
0x180187df5  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x180187dfb  mov     rax, [rsi]
0x180187dfe  movsxd  rcx, dword ptr [rax+4]
0x180187e02  test    byte ptr [rcx+rsi+10h], 6
0x180187e07  jnz     loc_180187EA6
0x180187e0d  test    rbx, rbx
0x180187e10  jz      short loc_180187E3F
0x180187e12  cmp     rdi, 1000h
0x180187e19  jb      short loc_180187E33
0x180187e1b  add     rdi, 27h ; '''
0x180187e1f  mov     rcx, [rbx-8]
0x180187e23  sub     rbx, rcx
0x180187e26  lea     rax, [rbx-8]
0x180187e2a  cmp     rax, 1Fh
0x180187e2e  ja      short loc_180187E9F
0x180187e30  mov     rbx, rcx
0x180187e33  mov     rdx, rdi
0x180187e36  mov     rcx, rbx; Block
0x180187e39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180187e3e  nop
0x180187e3f  mov     rbx, [rsp+250h+var_220]
0x180187e44  test    rbx, rbx
0x180187e47  jz      short loc_180187E75
0x180187e49  mov     edi, 0FFFFFFFFh
0x180187e4e  mov     eax, edi
0x180187e50  lock xadd [rbx+8], eax
0x180187e55  cmp     eax, 1
0x180187e58  jnz     short loc_180187E75
0x180187e5a  mov     rax, [rbx]
0x180187e5d  mov     rcx, rbx
0x180187e60  call    qword ptr [rax]
0x180187e62  lock xadd [rbx+0Ch], edi
0x180187e67  cmp     edi, 1
0x180187e6a  jnz     short loc_180187E75
0x180187e6c  mov     rax, [rbx]
0x180187e6f  mov     rcx, rbx
0x180187e72  call    qword ptr [rax+8]
0x180187e75  mov     rcx, [rbp+150h+var_38]
0x180187e7c  xor     rcx, rsp; StackCookie
0x180187e7f  call    __security_check_cookie
0x180187e84  mov     rbx, [rsp+250h+arg_18]
0x180187e8c  add     rsp, 220h
0x180187e93  pop     r15
0x180187e95  pop     r14
0x180187e97  pop     r13
0x180187e99  pop     r12
0x180187e9b  pop     rdi
0x180187e9c  pop     rsi
0x180187e9d  pop     rbp
0x180187e9e  retn
0x180187e9f  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180187ea6  lea     rdx, aUnableToWriteT; "Unable to write to buffer."
0x180187ead  lea     rcx, [rbp+150h+pExceptionObject]; this
0x180187eb4  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180187eb9  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180187ec0  lea     rcx, [rbp+150h+pExceptionObject]; pExceptionObject
  ... truncated ...
```
