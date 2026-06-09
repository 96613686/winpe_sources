# Windows::Globalization::Spelling::FilesMapper::CreateFileMappingW(void *)

- ea: `0x180059bc0`
- end: `0x180059d12`
- name: `?CreateFileMappingW@FilesMapper@Spelling@Globalization@Windows@@AEAA?BU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@PEAX@Z`
- size: `338`
- prototype: `struct __MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 __high(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180085e2c`

## callees

- `0x1800202e4`
- `0x180021920`
- `0x1800222ac`
- `0x180038b40`
- `0x18004186c`
- `0x180047c48`
- `0x180059bc0`
- `0x180059d18`
- `0x180061320`
- `0x18008610c`
- `0x180086168`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059ca3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059ca3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180059c95`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180059c95`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Globalization::Spelling::FilesMapper::CreateFileMappingW(__int64 a1, __int64 a2, void *a3)
{
  unsigned __int64 FileSizeFromHandle; // rax
  __int64 v7; // rax
  __int64 v8; // r14
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rsi
  const WCHAR *lpName; // rax
  _QWORD *v12; // rax
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v15[8]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v16[64]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v17; // [rsp+D0h] [rbp+17h]

  *(_OWORD *)a2 = 0;
  FileSizeFromHandle = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle(a3);
  *(_QWORD *)(a2 + 8) = FileSizeFromHandle;
  if ( FileSizeFromHandle )
  {
    v7 = CreateUuid(&FileMappingAttributes);
    std::vector<std::wstring>::push_back(a1 + 48, v7);
    std::wstring::_Tidy_deallocate(&FileMappingAttributes);
    v15[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
    v15[1] = CloseHandle;
    v15[7] = v15;
    v8 = *(_QWORD *)(a1 + 56);
    memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
    if ( ACUtil::CreateSecurityAttributesForAppContainer(v9, &FileMappingAttributes) >= 0 )
    {
      lpName = (const WCHAR *)(v8 - 32);
      if ( *(_QWORD *)(v8 - 32 + 24) > 7u )
        lpName = *(const WCHAR **)lpName;
      v10 = (__int64)CreateFileMappingW(a3, &FileMappingAttributes, 2u, 0, 0, lpName);
      LocalFree(FileMappingAttributes.lpSecurityDescriptor);
    }
    else
    {
      v10 = -1;
    }
    std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(v16, v10, v15);
    std::_Func_class<void,UserDictionary *>::_Tidy(v15);
    if ( v17 != -1 )
    {
      std::vector<std::unique_ptr<void,std::function<int (void *)>>>::push_back(a1 + 24, v16);
      v12 = (_QWORD *)(*(_QWORD *)(a1 + 56) - 32LL);
      if ( v12[3] > 7u )
        v12 = (_QWORD *)*v12;
      *(_QWORD *)a2 = v12;
    }
    std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x180059bc0  push    rbp
0x180059bc2  push    rbx
0x180059bc3  push    rsi
0x180059bc4  push    rdi
0x180059bc5  push    r14
0x180059bc7  lea     rbp, [rsp-37h]
0x180059bcc  sub     rsp, 0F0h
0x180059bd3  mov     rax, cs:__security_cookie
0x180059bda  xor     rax, rsp
0x180059bdd  mov     [rbp+57h+var_30], rax
0x180059be1  mov     rsi, r8
0x180059be4  mov     rbx, rdx
0x180059be7  mov     rdi, rcx
0x180059bea  xorps   xmm0, xmm0
0x180059bed  movups  xmmword ptr [rdx], xmm0
0x180059bf0  mov     rcx, r8; void *
0x180059bf3  call    ?GetFileSizeFromHandle@UserDictionaries@Spelling@Globalization@Windows@@SA_KPEAX@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle(void *)
0x180059bf8  mov     [rbx+8], rax
0x180059bfc  test    rax, rax
0x180059bff  jz      loc_180059CF5
0x180059c05  lea     rcx, [rsp+110h+FileMappingAttributes]
0x180059c0a  call    ?CreateUuid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CreateUuid(void)
0x180059c0f  nop
0x180059c10  lea     rcx, [rdi+30h]
0x180059c14  mov     rdx, rax
0x180059c17  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180059c1c  nop
0x180059c1d  lea     rcx, [rsp+110h+FileMappingAttributes]
0x180059c22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059c27  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x180059c2e  mov     [rbp+57h+var_C0], rax
0x180059c32  mov     rax, cs:__imp_CloseHandle
0x180059c39  mov     [rbp+57h+var_B8], rax
0x180059c3d  lea     rax, [rbp+57h+var_C0]
0x180059c41  mov     [rbp+57h+var_88], rax
0x180059c45  mov     r14, [rdi+38h]
0x180059c49  xorps   xmm0, xmm0
0x180059c4c  xor     eax, eax
0x180059c4e  movups  xmmword ptr [rsp+110h+FileMappingAttributes.nLength], xmm0
0x180059c53  mov     qword ptr [rbp+57h+FileMappingAttributes.bInheritHandle], rax
0x180059c57  lea     rdx, [rsp+110h+FileMappingAttributes]; struct _SECURITY_ATTRIBUTES *
0x180059c5c  call    ?CreateSecurityAttributesForAppContainer@ACUtil@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; ACUtil::CreateSecurityAttributesForAppContainer(ushort const *,_SECURITY_ATTRIBUTES *)
0x180059c61  test    eax, eax
0x180059c63  jns     short loc_180059C6B
0x180059c65  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180059c69  jmp     short loc_180059CA9
0x180059c6b  lea     rax, [r14-20h]
0x180059c6f  cmp     qword ptr [rax+18h], 7
0x180059c74  jbe     short loc_180059C79
0x180059c76  mov     rax, [rax]
0x180059c79  mov     [rsp+110h+lpName], rax; lpName
0x180059c7e  mov     [rsp+110h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180059c86  xor     r9d, r9d; dwMaximumSizeHigh
0x180059c89  lea     r8d, [r9+2]; flProtect
0x180059c8d  lea     rdx, [rsp+110h+FileMappingAttributes]; lpFileMappingAttributes
0x180059c92  mov     rcx, rsi; hFile
0x180059c95  call    cs:__imp_CreateFileMappingW
0x180059c9b  mov     rsi, rax
0x180059c9e  mov     rcx, [rsp+110h+FileMappingAttributes.lpSecurityDescriptor]; hMem
0x180059ca3  call    cs:__imp_LocalFree
0x180059ca9  lea     r8, [rbp+57h+var_C0]
0x180059cad  mov     rdx, rsi
0x180059cb0  lea     rcx, [rbp+57h+var_80]
0x180059cb4  call    ??$?0V?$function@$$A6AHPEAX@Z@std@@$0A@@?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6AHPEAX@Z@1@@Z; std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(void *,std::function<int (void *)> &&)
0x180059cb9  nop
0x180059cba  lea     rcx, [rbp+57h+var_C0]
0x180059cbe  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180059cc3  cmp     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x180059cc8  jz      short loc_180059CEC
0x180059cca  lea     rcx, [rdi+18h]
0x180059cce  lea     rdx, [rbp+57h+var_80]
0x180059cd2  call    ?push_back@?$vector@V?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@V?$allocator@V?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@2@@Z; std::vector<std::unique_ptr<void,std::function<int (void *)>>>::push_back(std::unique_ptr<void,std::function<int (void *)>> &&)
0x180059cd7  mov     rax, [rdi+38h]
0x180059cdb  add     rax, 0FFFFFFFFFFFFFFE0h
0x180059cdf  cmp     qword ptr [rax+18h], 7
0x180059ce4  jbe     short loc_180059CE9
0x180059ce6  mov     rax, [rax]
0x180059ce9  mov     [rbx], rax
0x180059cec  lea     rcx, [rbp+57h+var_80]
0x180059cf0  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180059cf5  mov     rax, rbx
0x180059cf8  mov     rcx, [rbp+57h+var_30]
0x180059cfc  xor     rcx, rsp; StackCookie
0x180059cff  call    __security_check_cookie
0x180059d04  add     rsp, 0F0h
0x180059d0b  pop     r14
0x180059d0d  pop     rdi
0x180059d0e  pop     rsi
0x180059d0f  pop     rbx
0x180059d10  pop     rbp
0x180059d11  retn
```
