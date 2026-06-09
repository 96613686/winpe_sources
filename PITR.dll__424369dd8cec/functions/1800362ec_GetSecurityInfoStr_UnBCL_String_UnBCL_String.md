# GetSecurityInfoStr(UnBCL::String *,UnBCL::String * *)

- ea: `0x1800362ec`
- end: `0x180036411`
- name: `?GetSecurityInfoStr@@YAJPEAVString@UnBCL@@PEAPEAV12@@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct UnBCL::String **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033180`

## callees

- `0x1800360ec`
- `0x1800362ec`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003636c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003636c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036384`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180036362`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180036362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363e5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800363a3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800363a3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800363be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800363be`

## pseudocode

```c
__int64 __fastcall GetSecurityInfoStr(struct UnBCL::String *a1, struct UnBCL::String **a2)
{
  int SecurityInfo; // ebx
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  UnBCL::String *v7; // rax
  struct UnBCL::String *v8; // rdi
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-18h] BYREF

  SecurityDescriptor = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  SecurityInfo = GetSecurityInfo(a1, &SecurityDescriptor);
  if ( SecurityInfo >= 0 )
  {
    StringSecurityDescriptor = 0;
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
           SecurityDescriptor,
           1u,
           0x9Fu,
           &StringSecurityDescriptor,
           0) )
    {
      v7 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v8 = v7;
      if ( v7 )
      {
        UnBCL::String::String(v7, StringSecurityDescriptor);
        *(_QWORD *)v8 = &UnBCL::String::`local vftable';
      }
      else
      {
        v8 = 0;
      }
      *a2 = v8;
      LocalFree(StringSecurityDescriptor);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError < 0;
      if ( LastError > 0 )
        v5 = 1;
      if ( v5 )
      {
        v6 = GetLastError();
        SecurityInfo = v6;
        if ( v6 > 0 )
          SecurityInfo = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        SecurityInfo = -2147467259;
      }
    }
    LocalFree(SecurityDescriptor);
  }
  return (unsigned int)SecurityInfo;
}

```

## disassembly

```asm
0x1800362ec  mov     r11, rsp
0x1800362ef  mov     [r11+18h], rbx
0x1800362f3  mov     [r11+20h], rsi
0x1800362f7  push    rdi
0x1800362f8  sub     rsp, 50h
0x1800362fc  mov     rax, cs:__security_cookie
0x180036303  xor     rax, rsp
0x180036306  mov     [rsp+58h+var_10], rax
0x18003630b  mov     rsi, rdx
0x18003630e  mov     qword ptr [r11-18h], 0
0x180036316  test    rcx, rcx
0x180036319  jz      loc_1800363EF
0x18003631f  test    rdx, rdx
0x180036322  jz      loc_1800363EF
0x180036328  lea     rdx, [r11-18h]; void **
0x18003632c  call    ?GetSecurityInfo@@YAJPEAVString@UnBCL@@PEAPEAX@Z; GetSecurityInfo(UnBCL::String *,void * *)
0x180036331  mov     ebx, eax
0x180036333  test    eax, eax
0x180036335  js      loc_1800363EB
0x18003633b  mov     [rsp+58h+StringSecurityDescriptor], 0
0x180036344  mov     [rsp+58h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x18003634d  lea     r9, [rsp+58h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180036352  mov     edx, 1; RequestedStringSDRevision
0x180036357  mov     r8d, 9Fh; SecurityInformation
0x18003635d  mov     rcx, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180036362  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180036368  test    eax, eax
0x18003636a  jnz     short loc_18003639E
0x18003636c  call    cs:__imp_GetLastError
0x180036372  mov     edi, 80070000h
0x180036377  test    eax, eax
0x180036379  jle     short loc_180036382
0x18003637b  movzx   eax, ax
0x18003637e  or      eax, edi
0x180036380  test    eax, eax
0x180036382  jns     short loc_180036397
0x180036384  call    cs:__imp_GetLastError
0x18003638a  mov     ebx, eax
0x18003638c  test    eax, eax
0x18003638e  jle     short loc_1800363E0
0x180036390  movzx   ebx, ax
0x180036393  or      ebx, edi
0x180036395  jmp     short loc_1800363E0
0x180036397  mov     ebx, 80004005h
0x18003639c  jmp     short loc_1800363E0
0x18003639e  mov     ecx, 18h
0x1800363a3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800363a9  mov     rdi, rax
0x1800363ac  mov     [rsp+58h+var_28], rax
0x1800363b1  test    rax, rax
0x1800363b4  jz      short loc_1800363D0
0x1800363b6  mov     rdx, [rsp+58h+StringSecurityDescriptor]
0x1800363bb  mov     rcx, rax
0x1800363be  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800363c4  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x1800363cb  mov     [rdi], rax
0x1800363ce  jmp     short loc_1800363D2
0x1800363d0  xor     edi, edi
0x1800363d2  mov     [rsi], rdi
0x1800363d5  mov     rcx, [rsp+58h+StringSecurityDescriptor]; hMem
0x1800363da  call    cs:__imp_LocalFree
0x1800363e0  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800363e5  call    cs:__imp_LocalFree
0x1800363eb  mov     eax, ebx
0x1800363ed  jmp     short loc_1800363F4
0x1800363ef  mov     eax, 80070057h
0x1800363f4  mov     rcx, [rsp+58h+var_10]
0x1800363f9  xor     rcx, rsp; StackCookie
0x1800363fc  call    __security_check_cookie
0x180036401  mov     rbx, [rsp+58h+arg_10]
0x180036406  mov     rsi, [rsp+58h+arg_18]
0x18003640b  add     rsp, 50h
0x18003640f  pop     rdi
0x180036410  retn
```
