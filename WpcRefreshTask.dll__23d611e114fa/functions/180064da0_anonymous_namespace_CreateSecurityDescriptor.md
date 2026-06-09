# _anonymous_namespace_::CreateSecurityDescriptor

- ea: `0x180064da0`
- end: `0x1800651c1`
- name: `_anonymous_namespace_::CreateSecurityDescriptor`
- size: `1057`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009a958`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180006ee0`
- `0x1800090f8`
- `0x180009a80`
- `0x18000e880`
- `0x18000e8b0`
- `0x18000e93c`
- `0x18001f348`
- `0x18001f4c8`
- `0x180035af4`
- `0x180035e0c`
- `0x180064da0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006510c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006510c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800650ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800650ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180065021`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180065021`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall anonymous_namespace_::CreateSecurityDescriptor(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *v5; // rbx
  unsigned __int64 v7; // r10
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPCWSTR v12; // r9
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  LPCWSTR *v16; // rcx
  __int64 v17; // rax
  const WCHAR *v18; // rcx
  BOOL v19; // ebx
  _BYTE *v20; // rdx
  HLOCAL v21; // rbx
  _DWORD *v22; // rax
  signed int LastError; // eax
  unsigned int v25; // ebx
  int v26; // eax
  __int64 v27; // r10
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-A8h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  unsigned __int64 v33; // [rsp+78h] [rbp-88h]
  _QWORD pExceptionObject[8]; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE *v37; // [rsp+100h] [rbp+0h]

  v5 = a2;
  v29[0] = a1;
  v30 = (_DWORD *)a4;
  *(_OWORD *)StringSecurityDescriptor = 0;
  v32 = 0;
  v7 = 7;
  v33 = 7;
  LOWORD(StringSecurityDescriptor[0]) = 0;
  v8 = a4 + 24;
  if ( a4 == -1 )
    v8 = 24;
  if ( *(_QWORD *)v8 )
  {
    v9 = *(_QWORD **)(a4 + 24);
    if ( !v9 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v10 = (_QWORD *)*v9;
    if ( v10 )
    {
      v11 = v10[2];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v11) < 2 )
        goto LABEL_48;
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      std::wstring::wstring(pExceptionObject, v11, a3, L"O:", 2, v10, v11);
      std::wstring::append(StringSecurityDescriptor);
      std::wstring::~wstring(pExceptionObject);
      v7 = v33;
      a3 = v32;
      v12 = StringSecurityDescriptor[0];
    }
    else
    {
      a3 = 4;
      v32 = 4;
      v12 = *(LPCWSTR *)L"O:CO";
      StringSecurityDescriptor[0] = *(LPCWSTR *)L"O:CO";
      LOWORD(StringSecurityDescriptor[1]) = 0;
    }
    v13 = *(_QWORD *)(a4 + 24);
    if ( !v13 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v14 = *(_QWORD **)(v13 + 8);
    if ( v14 )
    {
      v15 = v14[2];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v15) < 2 )
        goto LABEL_48;
      if ( v14[3] > 7u )
        v14 = (_QWORD *)*v14;
      std::wstring::wstring(pExceptionObject, v15, a3, L"G:", 2, v14, v15);
      std::wstring::append(StringSecurityDescriptor);
      std::wstring::~wstring(pExceptionObject);
    }
    else
    {
      v16 = StringSecurityDescriptor;
      if ( v7 - a3 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          StringSecurityDescriptor,
          4);
      }
      else
      {
        a2 = (_QWORD *)(a3 + 4);
        v32 = a3 + 4;
        if ( v7 > 7 )
          v16 = (LPCWSTR *)v12;
        *(LPCWSTR *)((char *)v16 + 2 * a3) = *(LPCWSTR *)L"G:CG";
        *((_WORD *)v16 + (_QWORD)a2) = 0;
      }
    }
  }
  if ( !v5 )
    goto LABEL_27;
  v17 = v5[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v17) < 2 )
LABEL_48:
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(pExceptionObject, a2, a3, L"D:", 2, v5, v17);
  std::wstring::append(StringSecurityDescriptor);
  std::wstring::~wstring(pExceptionObject);
LABEL_27:
  hMem = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable';
  pExceptionObject[1] = &hMem;
  pExceptionObject[7] = pExceptionObject;
  stdext::GetPointer<void *>::GetPointer<void *>(&SecurityDescriptor, pExceptionObject);
  v18 = (const WCHAR *)StringSecurityDescriptor;
  if ( v33 > 7 )
    v18 = StringSecurityDescriptor[0];
  v19 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v18, 1u, &SecurityDescriptor, 0);
  if ( v37 )
  {
    v29[0] = SecurityDescriptor;
    (*(void (__fastcall **)(_BYTE *, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v37 + 16LL))(v37, v29);
    if ( v37 )
    {
      v20 = v36;
      LOBYTE(v20) = v37 != v36;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v37 + 32LL))(v37, v20);
    }
  }
  if ( !v19 )
  {
    LastError = GetLastError();
    v25 = LastError;
    if ( LastError > 0 )
      v25 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = std::wstring::c_str(StringSecurityDescriptor);
      WPP_SF_Sd(*(_QWORD *)(v27 + 16), 10, (int)WPP_3c253eb01cea33b92b41eb2eed79eb93_Traceguids, v26, v25);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v25);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *a1 = 0;
  a1[1] = 0;
  v21 = hMem;
  if ( hMem )
  {
    v22 = operator new(0x18u);
    v30 = v22;
    *(_OWORD *)v22 = 0;
    v22[2] = 1;
    v22[3] = 1;
    *(_QWORD *)v22 = &std::_Ref_count_resource<void *,LocalDeallocator>::`vftable';
    *((_QWORD *)v22 + 2) = v21;
    *a1 = v21;
    a1[1] = v22;
    v21 = 0;
    hMem = 0;
  }
  if ( v21 )
    LocalFree(v21);
  std::wstring::~wstring(StringSecurityDescriptor);
  if ( *(_QWORD *)(a4 + 24) )
    *(_QWORD *)(a4 + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x180064da0  push    rbp
0x180064da2  push    rbx
0x180064da3  push    rsi
0x180064da4  push    rdi
0x180064da5  push    r12
0x180064da7  push    r13
0x180064da9  push    r14
0x180064dab  lea     rbp, [rsp-20h]
0x180064db0  sub     rsp, 120h
0x180064db7  mov     rax, cs:__security_cookie
0x180064dbe  xor     rax, rsp
0x180064dc1  mov     [rbp+50h+var_40], rax
0x180064dc5  mov     r14, r9
0x180064dc8  mov     rbx, rdx
0x180064dcb  mov     rsi, rcx
0x180064dce  mov     [rsp+150h+var_108], rcx
0x180064dd3  mov     [rsp+150h+var_F8], r9
0x180064dd8  xorps   xmm0, xmm0
0x180064ddb  movups  xmmword ptr [rsp+150h+StringSecurityDescriptor], xmm0
0x180064de0  mov     [rsp+150h+var_E0], 0
0x180064de9  mov     r10d, 7
0x180064def  mov     [rsp+150h+var_D8], r10
0x180064df4  xor     eax, eax
0x180064df6  mov     word ptr [rsp+150h+StringSecurityDescriptor], ax
0x180064dfb  lea     rax, [r9+1]
0x180064dff  lea     rcx, [rax+17h]
0x180064e03  lea     r12d, [r10+11h]
0x180064e07  test    rax, rax
0x180064e0a  cmovz   rcx, r12
0x180064e0e  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180064e18  lea     r13d, [r10-5]
0x180064e1c  cmp     qword ptr [rcx], 0
0x180064e20  jz      loc_180064F7A
0x180064e26  mov     rcx, [r9+18h]
0x180064e2a  test    rcx, rcx
0x180064e2d  jz      loc_18006517D
0x180064e33  mov     rcx, [rcx]
0x180064e36  lea     r12d, [r10-3]
0x180064e3a  test    rcx, rcx
0x180064e3d  jz      short loc_180064EA4
0x180064e3f  mov     rdx, [rcx+10h]
0x180064e43  mov     rax, rdi
0x180064e46  sub     rax, rdx
0x180064e49  cmp     rax, r13
0x180064e4c  jb      loc_1800651BB
0x180064e52  cmp     [rcx+18h], r10
0x180064e56  jbe     short loc_180064E5B
0x180064e58  mov     rcx, [rcx]
0x180064e5b  mov     [rsp+150h+var_120], rdx
0x180064e60  mov     [rsp+150h+var_128], rcx
0x180064e65  mov     [rsp+150h+var_130], r13
0x180064e6a  lea     r9, aO; "O:"
0x180064e71  lea     rcx, [rbp+50h+pExceptionObject]
0x180064e75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180064e7a  nop
0x180064e7b  lea     rdx, [rbp+50h+pExceptionObject]
0x180064e7f  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Src
0x180064e84  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180064e89  nop
0x180064e8a  lea     rcx, [rbp+50h+pExceptionObject]
0x180064e8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064e93  mov     r10, [rsp+150h+var_D8]
0x180064e98  mov     r8, [rsp+150h+var_E0]
0x180064e9d  mov     r9, [rsp+150h+StringSecurityDescriptor]
0x180064ea2  jmp     short loc_180064EBF
0x180064ea4  mov     r8, r12
0x180064ea7  mov     [rsp+150h+var_E0], r12
0x180064eac  mov     r9, qword ptr cs:aOCo; "O:CO"
0x180064eb3  mov     [rsp+150h+StringSecurityDescriptor], r9
0x180064eb8  xor     eax, eax
0x180064eba  mov     word ptr [rsp+150h+StringSecurityDescriptor+8], ax
0x180064ebf  mov     rcx, [r14+18h]
0x180064ec3  test    rcx, rcx
0x180064ec6  jz      loc_18006519C
0x180064ecc  mov     rcx, [rcx+8]
0x180064ed0  test    rcx, rcx
0x180064ed3  jz      short loc_180064F2C
0x180064ed5  mov     rdx, [rcx+10h]
0x180064ed9  mov     rax, rdi
0x180064edc  sub     rax, rdx
0x180064edf  cmp     rax, r13
0x180064ee2  jb      loc_1800651BB
0x180064ee8  cmp     qword ptr [rcx+18h], 7
0x180064eed  jbe     short loc_180064EF2
0x180064eef  mov     rcx, [rcx]
0x180064ef2  mov     [rsp+150h+var_120], rdx
0x180064ef7  mov     [rsp+150h+var_128], rcx
0x180064efc  mov     [rsp+150h+var_130], r13
0x180064f01  lea     r9, aG; "G:"
0x180064f08  lea     rcx, [rbp+50h+pExceptionObject]
0x180064f0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180064f11  nop
0x180064f12  lea     rdx, [rbp+50h+pExceptionObject]
0x180064f16  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Src
0x180064f1b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180064f20  nop
0x180064f21  lea     rcx, [rbp+50h+pExceptionObject]
0x180064f25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064f2a  jmp     short loc_180064F74
0x180064f2c  mov     rax, r10
0x180064f2f  sub     rax, r8
0x180064f32  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Src
0x180064f37  cmp     rax, r12
0x180064f3a  jb      short loc_180064F60
0x180064f3c  lea     rdx, [r8+4]
0x180064f40  mov     [rsp+150h+var_E0], rdx
0x180064f45  cmp     r10, 7
0x180064f49  cmova   rcx, r9
0x180064f4d  mov     rax, qword ptr cs:aGCg; "G:CG"
0x180064f54  mov     [rcx+r8*2], rax
0x180064f58  xor     eax, eax
0x180064f5a  mov     [rcx+rdx*2], ax
0x180064f5e  jmp     short loc_180064F74
0x180064f60  mov     [rsp+150h+var_130], r12; __int64
0x180064f65  lea     r9, aGCg; "G:CG"
0x180064f6c  mov     rdx, r12
0x180064f6f  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180064f74  mov     r12d, 18h
0x180064f7a  test    rbx, rbx
0x180064f7d  jz      short loc_180064FD1
0x180064f7f  mov     rax, [rbx+10h]
0x180064f83  sub     rdi, rax
0x180064f86  cmp     rdi, r13
0x180064f89  jb      loc_1800651BB
0x180064f8f  cmp     qword ptr [rbx+18h], 7
0x180064f94  jbe     short loc_180064F99
0x180064f96  mov     rbx, [rbx]
0x180064f99  mov     [rsp+150h+var_120], rax
0x180064f9e  mov     [rsp+150h+var_128], rbx
0x180064fa3  mov     [rsp+150h+var_130], r13
0x180064fa8  lea     r9, aD_1; "D:"
0x180064faf  lea     rcx, [rbp+50h+pExceptionObject]
0x180064fb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180064fb8  nop
0x180064fb9  lea     rdx, [rbp+50h+pExceptionObject]
0x180064fbd  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Src
0x180064fc2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180064fc7  nop
0x180064fc8  lea     rcx, [rbp+50h+pExceptionObject]
0x180064fcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064fd1  mov     [rsp+150h+hMem], 0
0x180064fda  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1a0a9a37411416c90e606832c1826ed5_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable'
0x180064fe1  mov     [rbp+50h+pExceptionObject], rax
0x180064fe5  lea     rax, [rsp+150h+hMem]
0x180064fea  mov     [rbp+50h+var_C8], rax
0x180064fee  lea     rax, [rbp+50h+pExceptionObject]
0x180064ff2  mov     [rbp+50h+var_98], rax
0x180064ff6  lea     rdx, [rbp+50h+pExceptionObject]
0x180064ffa  lea     rcx, [rbp+50h+SecurityDescriptor]
0x180064ffe  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x180065003  lea     rcx, [rsp+150h+StringSecurityDescriptor]
0x180065008  cmp     [rsp+150h+var_D8], 7
0x18006500e  cmova   rcx, [rsp+150h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180065014  xor     r9d, r9d; SecurityDescriptorSize
0x180065017  lea     r8, [rbp+50h+SecurityDescriptor]; SecurityDescriptor
0x18006501b  lea     edi, [r9+1]
0x18006501f  mov     edx, edi; StringSDRevision
0x180065021  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180065027  mov     ebx, eax
0x180065029  mov     rcx, [rbp+50h+var_50]
0x18006502d  test    rcx, rcx
0x180065030  jz      short loc_18006506C
0x180065032  mov     rax, [rbp+50h+SecurityDescriptor]
0x180065036  mov     [rsp+150h+var_108], rax
0x18006503b  mov     rax, [rcx]
0x18006503e  lea     rdx, [rsp+150h+var_108]
0x180065043  mov     rax, [rax+10h]
0x180065047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006504c  mov     rcx, [rbp+50h+var_50]
0x180065050  test    rcx, rcx
0x180065053  jz      short loc_18006506C
0x180065055  mov     rax, [rcx]
0x180065058  lea     rdx, [rbp+50h+var_88]
0x18006505c  cmp     rcx, rdx
0x18006505f  setnz   dl
0x180065062  mov     rax, [rax+20h]
0x180065066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006506b  nop
0x18006506c  test    ebx, ebx
0x18006506e  jz      loc_18006510C
0x180065074  mov     qword ptr [rsi], 0
0x18006507b  mov     qword ptr [rsi+8], 0
0x180065083  mov     rbx, [rsp+150h+hMem]
0x180065088  test    rbx, rbx
0x18006508b  jz      short loc_1800650C2
0x18006508d  mov     rcx, r12; Size
0x180065090  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065095  mov     [rsp+150h+var_F8], rax
0x18006509a  xorps   xmm0, xmm0
0x18006509d  movups  xmmword ptr [rax], xmm0
0x1800650a0  mov     [rax+8], edi
0x1800650a3  mov     [rax+0Ch], edi
0x1800650a6  lea     rcx, ??_7?$_Ref_count_resource@PEAXULocalDeallocator@@@std@@6B@; const std::_Ref_count_resource<void *,LocalDeallocator>::`vftable'
0x1800650ad  mov     [rax], rcx
0x1800650b0  mov     [rax+10h], rbx
0x1800650b4  mov     [rsi], rbx
0x1800650b7  mov     [rsi+8], rax
0x1800650bb  xor     ebx, ebx
0x1800650bd  mov     [rsp+150h+hMem], rbx
0x1800650c2  test    rbx, rbx
0x1800650c5  jz      short loc_1800650D1
0x1800650c7  mov     rcx, rbx; hMem
0x1800650ca  call    cs:__imp_LocalFree
0x1800650d0  nop
0x1800650d1  lea     rcx, [rsp+150h+StringSecurityDescriptor]
0x1800650d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800650db  nop
0x1800650dc  cmp     qword ptr [r14+18h], 0
0x1800650e1  jz      short loc_1800650EB
0x1800650e3  mov     qword ptr [r14+18h], 0
0x1800650eb  mov     rax, rsi
0x1800650ee  mov     rcx, [rbp+50h+var_40]
0x1800650f2  xor     rcx, rsp; StackCookie
0x1800650f5  call    __security_check_cookie
0x1800650fa  add     rsp, 120h
0x180065101  pop     r14
0x180065103  pop     r13
0x180065105  pop     r12
0x180065107  pop     rdi
0x180065108  pop     rsi
0x180065109  pop     rbx
0x18006510a  pop     rbp
0x18006510b  retn
0x18006510c  call    cs:__imp_GetLastError
0x180065112  nop
0x180065113  mov     ebx, eax
0x180065115  test    eax, eax
0x180065117  jle     short loc_180065122
0x180065119  movzx   ebx, ax
0x18006511c  or      ebx, 80070000h
0x180065122  lea     rax, WPP_GLOBAL_Control
0x180065129  mov     r10, cs:WPP_GLOBAL_Control
0x180065130  cmp     r10, rax
0x180065133  jz      short loc_180065161
0x180065135  test    [r10+1Ch], dil
0x180065139  jz      short loc_180065161
0x18006513b  lea     rcx, [rsp+150h+StringSecurityDescriptor]
0x180065140  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180065145  mov     edx, 0Ah
0x18006514a  mov     dword ptr [rsp+150h+var_130], ebx
0x18006514e  mov     r9, rax
0x180065151  lea     r8, WPP_3c253eb01cea33b92b41eb2eed79eb93_Traceguids
0x180065158  mov     rcx, [r10+10h]
0x18006515c  call    WPP_SF_Sd
0x180065161  mov     edx, ebx; int
0x180065163  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180065167  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18006516c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180065173  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180065177  call    _CxxThrowException_0
0x18006517d  mov     edx, 80004003h; int
0x180065182  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180065186  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18006518b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180065192  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180065196  call    _CxxThrowException_0
0x18006519c  mov     edx, 80004003h; int
0x1800651a1  lea     rcx, [rbp+50h+pExceptionObject]; this
0x1800651a5  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800651aa  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800651b1  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x1800651b5  call    _CxxThrowException_0
0x1800651bb  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
