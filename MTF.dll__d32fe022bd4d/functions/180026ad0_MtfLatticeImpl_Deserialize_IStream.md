# MtfLatticeImpl::Deserialize(IStream *)

- ea: `0x180026ad0`
- end: `0x180026ed2`
- name: `?Deserialize@MtfLatticeImpl@@UEAAJPEAUIStream@@@Z`
- size: `1026`
- prototype: `__int64 __fastcall(MtfLatticeImpl *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001fc4`
- `0x18000d2a4`
- `0x180025248`
- `0x180026ad0`
- `0x18002ab2c`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MtfLatticeImpl::Deserialize(MtfLatticeImpl *this, struct IStream *a2)
{
  _QWORD *v4; // rsi
  _QWORD *v5; // rbx
  _QWORD *v6; // rdi
  int v7; // ebx
  unsigned int i; // r15d
  unsigned int v9; // eax
  MtfLatticeImpl::MtfLatticeFrameImpl *v10; // rax
  __int64 v11; // rdi
  unsigned __int64 v12; // r8
  bool v13; // al
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // r15
  unsigned int j; // r14d
  __int64 result; // rax
  __int64 v20; // rcx
  __int64 v21; // [rsp+30h] [rbp-58h] BYREF
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v23[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+8h] BYREF
  MtfLatticeImpl::MtfLatticeFrameImpl *v25; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+18h] BYREF
  int v27; // [rsp+A8h] [rbp+20h] BYREF

  v21 = 0;
  v22 = 0;
  v4 = (_QWORD *)((char *)this + 16);
  v5 = (_QWORD *)*((_QWORD *)this + 2);
  v6 = (_QWORD *)*((_QWORD *)this + 3);
  while ( v5 != v6 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
    ++v5;
  }
  try
  {
    v4[1] = *v4;
    v24 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &v24, 4);
    if ( v7 >= 0 )
    {
      if ( (__int64)(v4[2] - *v4) >> 3 < (unsigned __int64)v24 )
        std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(v4);
      v7 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)(*((_QWORD *)this + 5) + 16LL) + 40LL))(
             *((_QWORD *)this + 5) + 16LL,
             a2);
      if ( v7 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          v9 = v24;
          if ( i >= v24 )
            break;
          v10 = (MtfLatticeImpl::MtfLatticeFrameImpl *)operator new(0x20u);
          v25 = v10;
          if ( v10 )
            v11 = MtfLatticeImpl::MtfLatticeFrameImpl::MtfLatticeFrameImpl(v10);
          else
            v11 = 0;
          v23[0] = v11;
          v7 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)(*(_QWORD *)(v11 + 24) + 16LL) + 40LL))(
                 *(_QWORD *)(v11 + 24) + 16LL,
                 a2);
          if ( v7 < 0 )
            goto LABEL_44;
          v12 = *((_QWORD *)this + 3);
          v13 = (unsigned __int64)v23 < v12 && *v4 <= (unsigned __int64)v23;
          v14 = *((_QWORD *)this + 4);
          if ( v13 )
          {
            v15 = *v4;
            if ( v12 == v14 && !((__int64)(v14 - v12) >> 3) )
            {
              if ( (__int64)(v12 - v15) >> 3 == 0x1FFFFFFFFFFFFFFFLL )
                std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>>::_Xlen();
              std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(v4);
            }
            *(_QWORD *)v4[1] = *(_QWORD *)(*v4 + 8 * (((__int64)v23 - v15) >> 3));
          }
          else
          {
            if ( v12 == v14 && !((__int64)(v14 - v12) >> 3) )
            {
              if ( (__int64)(v12 - *v4) >> 3 == 0x1FFFFFFFFFFFFFFFLL )
                std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>>::_Xlen();
              std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(v4);
            }
            *(_QWORD *)v4[1] = v11;
          }
          v4[1] += 8LL;
        }
        v16 = 0;
        while ( (unsigned int)v16 < v9 )
        {
          v17 = *(_QWORD *)(*(_QWORD *)(*v4 + 8 * v16) + 24LL);
          v26 = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v26);
          if ( v7 < 0 )
            break;
          for ( j = 0; j < v26; ++j )
          {
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 32LL))(v17, j, &v21);
            if ( v7 < 0 )
              goto LABEL_44;
            v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
                   v21,
                   &GUID_b1445657_72ab_43f8_a85a_67520e48fb44,
                   &v22);
            if ( v7 < 0 )
              goto LABEL_44;
            LODWORD(v25) = 0;
            v27 = 0;
            if ( (*(int (__fastcall **)(__int64, MtfLatticeImpl::MtfLatticeFrameImpl **, int *))(*(_QWORD *)v22 + 48LL))(
                   v22,
                   &v25,
                   &v27) < 0 )
              goto LABEL_44;
            if ( (_DWORD)v25 != (_DWORD)v16 )
            {
              v7 = -2147418113;
              goto LABEL_44;
            }
            if ( (int)v25 >= v27 || v27 >= (int)v24 )
            {
              v7 = -2147483637;
              goto LABEL_44;
            }
            v20 = *(_QWORD *)(*(_QWORD *)(*v4 + 8LL * v27) + 16LL);
            v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 48LL))(v20, v21);
            if ( v7 < 0 )
              goto LABEL_44;
          }
          v16 = (unsigned int)(v16 + 1);
          v9 = v24;
        }
      }
    }
LABEL_44:
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    result = (unsigned int)v7;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180026ad0  push    rbx
0x180026ad2  push    rsi
0x180026ad3  push    rdi
0x180026ad4  push    r12
0x180026ad6  push    r14
0x180026ad8  push    r15
0x180026ada  sub     rsp, 58h
0x180026ade  mov     r12, rdx
0x180026ae1  mov     r14, rcx
0x180026ae4  mov     [rsp+88h+var_58], 0
0x180026aed  mov     [rsp+88h+var_50], 0
0x180026af6  lea     rsi, [rcx+10h]
0x180026afa  mov     rbx, [rsi]
0x180026afd  mov     rdi, [rsi+8]
0x180026b01  cmp     rbx, rdi
0x180026b04  jz      short loc_180026B1B
0x180026b06  mov     rcx, [rbx]
0x180026b09  mov     rax, [rcx]
0x180026b0c  mov     rax, [rax+10h]
0x180026b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b15  add     rbx, 8
0x180026b19  jmp     short loc_180026B01
0x180026b1b  mov     rax, [rsi]
0x180026b1e  mov     [rsi+8], rax
0x180026b22  mov     [rsp+88h+arg_0], 0
0x180026b2d  mov     rax, [r12]
0x180026b31  xor     r9d, r9d
0x180026b34  lea     r8d, [r9+4]
0x180026b38  lea     rdx, [rsp+88h+arg_0]
0x180026b40  mov     rcx, r12
0x180026b43  mov     rax, [rax+18h]
0x180026b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b4c  mov     ebx, eax
0x180026b4e  test    eax, eax
0x180026b50  js      loc_180026E20
0x180026b56  mov     edx, [rsp+88h+arg_0]
0x180026b5d  mov     rax, [rsi+10h]
0x180026b61  sub     rax, [rsi]
0x180026b64  sar     rax, 3
0x180026b68  cmp     rax, rdx
0x180026b6b  jnb     short loc_180026B75
0x180026b6d  mov     rcx, rsi
0x180026b70  call    ?_Reallocate@?$vector@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@V?$allocator@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@IEAAX_K@Z; std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(unsigned __int64)
0x180026b75  mov     rcx, [r14+28h]
0x180026b79  add     rcx, 10h
0x180026b7d  mov     rax, [rcx]
0x180026b80  mov     rdx, r12
0x180026b83  mov     rax, [rax+28h]
0x180026b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b8c  mov     ebx, eax
0x180026b8e  test    eax, eax
0x180026b90  js      loc_180026E20
0x180026b96  xor     r15d, r15d
0x180026b99  mov     eax, [rsp+88h+arg_0]
0x180026ba0  cmp     r15d, eax
0x180026ba3  jnb     loc_180026D1A
0x180026ba9  mov     ecx, 20h ; ' '; Size
0x180026bae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026bb3  mov     [rsp+88h+arg_8], rax
0x180026bbb  test    rax, rax
0x180026bbe  jz      short loc_180026BCD
0x180026bc0  mov     rcx, rax; this
0x180026bc3  call    ??0MtfLatticeFrameImpl@MtfLatticeImpl@@QEAA@XZ; MtfLatticeImpl::MtfLatticeFrameImpl::MtfLatticeFrameImpl(void)
0x180026bc8  mov     rdi, rax
0x180026bcb  jmp     short loc_180026BCF
0x180026bcd  xor     edi, edi
0x180026bcf  mov     [rsp+88h+var_48], rdi
0x180026bd4  mov     rcx, [rdi+18h]
0x180026bd8  add     rcx, 10h
0x180026bdc  mov     rax, [rcx]
0x180026bdf  mov     rdx, r12
0x180026be2  mov     rax, [rax+28h]
0x180026be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026beb  mov     ebx, eax
0x180026bed  test    eax, eax
0x180026bef  js      loc_180026E20
0x180026bf5  mov     r8, [r14+18h]
0x180026bf9  lea     rax, [rsp+88h+var_48]
0x180026bfe  cmp     rax, r8
0x180026c01  jnb     short loc_180026C11
0x180026c03  lea     rax, [rsp+88h+var_48]
0x180026c08  cmp     [rsi], rax
0x180026c0b  ja      short loc_180026C11
0x180026c0d  mov     al, 1
0x180026c0f  jmp     short loc_180026C13
0x180026c11  xor     al, al
0x180026c13  mov     r9, [r14+20h]
0x180026c17  test    al, al
0x180026c19  jz      loc_180026CA2
0x180026c1f  mov     rdi, [rsi]
0x180026c22  cmp     r8, r9
0x180026c25  jnz     short loc_180026C86
0x180026c27  mov     rax, r9
0x180026c2a  sub     rax, r8
0x180026c2d  sar     rax, 3
0x180026c31  cmp     rax, 1
0x180026c35  jnb     short loc_180026C86
0x180026c37  sub     r8, rdi
0x180026c3a  sar     r8, 3
0x180026c3e  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180026c48  mov     rax, rcx
0x180026c4b  sub     rax, r8
0x180026c4e  cmp     rax, 1
0x180026c52  jb      loc_180026EC6
0x180026c58  inc     r8
0x180026c5b  sub     r9, rdi
0x180026c5e  sar     r9, 3
0x180026c62  mov     rax, r9
0x180026c65  shr     rax, 1
0x180026c68  sub     rcx, rax
0x180026c6b  add     rax, r9
0x180026c6e  xor     edx, edx
0x180026c70  cmp     rcx, r9
0x180026c73  cmovnb  rdx, rax
0x180026c77  cmp     rdx, r8
0x180026c7a  cmovb   rdx, r8
0x180026c7e  mov     rcx, rsi
0x180026c81  call    ?_Reallocate@?$vector@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@V?$allocator@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@IEAAX_K@Z; std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(unsigned __int64)
0x180026c86  lea     rdx, [rsp+88h+var_48]
0x180026c8b  sub     rdx, rdi
0x180026c8e  sar     rdx, 3
0x180026c92  mov     rax, [rsi]
0x180026c95  mov     rcx, [rsi+8]
0x180026c99  mov     rax, [rax+rdx*8]
0x180026c9d  mov     [rcx], rax
0x180026ca0  jmp     short loc_180026D0D
0x180026ca2  cmp     r8, r9
0x180026ca5  jnz     short loc_180026D06
0x180026ca7  mov     rax, r9
0x180026caa  sub     rax, r8
0x180026cad  sar     rax, 3
0x180026cb1  cmp     rax, 1
0x180026cb5  jnb     short loc_180026D06
0x180026cb7  sub     r8, [rsi]
0x180026cba  sar     r8, 3
0x180026cbe  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180026cc8  mov     rax, rcx
0x180026ccb  sub     rax, r8
0x180026cce  cmp     rax, 1
0x180026cd2  jb      loc_180026ECB
0x180026cd8  inc     r8
0x180026cdb  sub     r9, [rsi]
0x180026cde  sar     r9, 3
0x180026ce2  mov     rax, r9
0x180026ce5  shr     rax, 1
0x180026ce8  sub     rcx, rax
0x180026ceb  add     rax, r9
0x180026cee  xor     edx, edx
0x180026cf0  cmp     rcx, r9
0x180026cf3  cmovnb  rdx, rax
0x180026cf7  cmp     rdx, r8
0x180026cfa  cmovb   rdx, r8
0x180026cfe  mov     rcx, rsi
0x180026d01  call    ?_Reallocate@?$vector@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@V?$allocator@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@IEAAX_K@Z; std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Reallocate(unsigned __int64)
0x180026d06  mov     rax, [rsi+8]
0x180026d0a  mov     [rax], rdi
0x180026d0d  add     qword ptr [rsi+8], 8
0x180026d12  inc     r15d
0x180026d15  jmp     loc_180026B99
0x180026d1a  xor     edi, edi
0x180026d1c  cmp     edi, eax
0x180026d1e  jnb     loc_180026E20
0x180026d24  mov     rax, [rsi]
0x180026d27  mov     rcx, [rax+rdi*8]
0x180026d2b  mov     r15, [rcx+18h]
0x180026d2f  mov     [rsp+88h+arg_10], 0
0x180026d3a  mov     rax, [r15]
0x180026d3d  lea     rdx, [rsp+88h+arg_10]
0x180026d45  mov     rcx, r15
0x180026d48  mov     rax, [rax+18h]
0x180026d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d51  mov     ebx, eax
0x180026d53  test    eax, eax
0x180026d55  js      loc_180026E20
0x180026d5b  xor     r14d, r14d
0x180026d5e  cmp     r14d, [rsp+88h+arg_10]
0x180026d66  jnb     loc_180026EB8
0x180026d6c  mov     rcx, [rsp+88h+var_58]
0x180026d71  test    rcx, rcx
0x180026d74  jz      short loc_180026D82
0x180026d76  mov     rax, [rcx]
0x180026d79  mov     rax, [rax+10h]
0x180026d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d82  mov     rcx, [rsp+88h+var_50]
0x180026d87  test    rcx, rcx
0x180026d8a  jz      short loc_180026D98
0x180026d8c  mov     rax, [rcx]
0x180026d8f  mov     rax, [rax+10h]
0x180026d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d98  mov     rax, [r15]
0x180026d9b  lea     r8, [rsp+88h+var_58]
0x180026da0  mov     edx, r14d
0x180026da3  mov     rcx, r15
0x180026da6  mov     rax, [rax+20h]
0x180026daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026daf  mov     ebx, eax
0x180026db1  test    eax, eax
0x180026db3  js      short loc_180026E20
0x180026db5  mov     rcx, [rsp+88h+var_58]
0x180026dba  mov     rax, [rcx]
0x180026dbd  lea     r8, [rsp+88h+var_50]
0x180026dc2  lea     rdx, _GUID_b1445657_72ab_43f8_a85a_67520e48fb44
0x180026dc9  mov     rax, [rax]
0x180026dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dd1  mov     ebx, eax
0x180026dd3  test    eax, eax
0x180026dd5  js      short loc_180026E20
0x180026dd7  mov     dword ptr [rsp+88h+arg_8], 0
0x180026de2  mov     [rsp+88h+arg_18], 0
0x180026ded  mov     rcx, [rsp+88h+var_50]
0x180026df2  mov     rax, [rcx]
0x180026df5  lea     r8, [rsp+88h+arg_18]
0x180026dfd  lea     rdx, [rsp+88h+arg_8]
0x180026e05  mov     rax, [rax+30h]
0x180026e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e0e  test    eax, eax
0x180026e10  js      short loc_180026E20
0x180026e12  cmp     dword ptr [rsp+88h+arg_8], edi
0x180026e19  jz      short loc_180026E63
0x180026e1b  mov     ebx, 8000FFFFh
0x180026e20  mov     rcx, [rsp+88h+var_58]
0x180026e25  test    rcx, rcx
0x180026e28  jz      short loc_180026E36
0x180026e2a  mov     rax, [rcx]
0x180026e2d  mov     rax, [rax+10h]
0x180026e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e36  mov     rcx, [rsp+88h+var_50]
0x180026e3b  test    rcx, rcx
0x180026e3e  jz      short loc_180026E4C
0x180026e40  mov     rdx, [rcx]
0x180026e43  mov     rax, [rdx+10h]
0x180026e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e4c  mov     eax, ebx
0x180026e4e  jmp     short loc_180026E55
0x180026e50  mov     eax, 80004005h
0x180026e55  add     rsp, 58h
0x180026e59  pop     r15
0x180026e5b  pop     r14
0x180026e5d  pop     r12
0x180026e5f  pop     rdi
0x180026e60  pop     rsi
0x180026e61  pop     rbx
0x180026e62  retn
0x180026e63  movsxd  rax, [rsp+88h+arg_18]
0x180026e6b  cmp     dword ptr [rsp+88h+arg_8], eax
0x180026e72  jge     short loc_180026EAE
0x180026e74  cmp     eax, [rsp+88h+arg_0]
0x180026e7b  jge     short loc_180026EAE
0x180026e7d  mov     rcx, rax
0x180026e80  mov     rax, [rsi]
0x180026e83  mov     rcx, [rax+rcx*8]
0x180026e87  mov     rcx, [rcx+10h]
0x180026e8b  mov     rax, [rcx]
0x180026e8e  mov     rdx, [rsp+88h+var_58]
0x180026e93  mov     rax, [rax+30h]
0x180026e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e9c  mov     ebx, eax
0x180026e9e  test    eax, eax
0x180026ea0  js      loc_180026E20
0x180026ea6  inc     r14d
0x180026ea9  jmp     loc_180026D5E
0x180026eae  mov     ebx, 8000000Bh
0x180026eb3  jmp     loc_180026E20
0x180026eb8  inc     edi
0x180026eba  mov     eax, [rsp+88h+arg_0]
0x180026ec1  jmp     loc_180026D1C
0x180026ec6  call    ?_Xlen@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>::_Xlen(void)
0x180026ecb  call    ?_Xlen@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>::_Xlen(void)
```
