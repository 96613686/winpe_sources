# pCheckPathTooLong(UnBCL::String const *)

- ea: `0x180013dd8`
- end: `0x180013f70`
- name: `?pCheckPathTooLong@@YAXPEBVString@UnBCL@@@Z`
- size: `408`
- prototype: `void __fastcall(const struct UnBCL::String *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180012600`
- `0x180013f78`

## callees

- `0x18000272c`
- `0x18000d02c`
- `0x18000d0bc`
- `0x18000d104`
- `0x18000d14c`
- `0x180013dd8`

## import_xrefs

- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180013e54`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180013e6c`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180013e54`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180013e6c`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013e32`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013ead`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013efb`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013e32`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013ead`
- `unbcl!??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z` at `0x180013efb`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013dfa`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013e79`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013ec5`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013dfa`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013e79`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180013ec5`
- `unbcl!?get_Platform@OperatingSystem@UnBCL@@QEBA?AW4PlatformID@2@XZ` at `0x180013dec`
- `unbcl!?get_Platform@OperatingSystem@UnBCL@@QEBA?AW4PlatformID@2@XZ` at `0x180013dec`
- `unbcl!?GetOSVersion@Environment@UnBCL@@SAPEBVOperatingSystem@2@H@Z` at `0x180013de3`
- `unbcl!?GetOSVersion@Environment@UnBCL@@SAPEBVOperatingSystem@2@H@Z` at `0x180013de3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013e10`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013e8b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013edd`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013e10`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013e8b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013edd`

## pseudocode

```c
void __fastcall pCheckPathTooLong(const struct UnBCL::String *a1)
{
  const struct UnBCL::OperatingSystem *OSVersion; // rax
  UnBCL::PathTooLongException *v3; // rbx
  const struct UnBCL::String *v4; // rax
  UnBCL::PathTooLongException *v5; // rbx
  const struct UnBCL::String *v6; // rax
  UnBCL::PathTooLongException *v7; // rbx
  const struct UnBCL::String *v8; // rax
  UnBCL::Exception *pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  UnBCL::PathTooLongException *v10; // [rsp+40h] [rbp+18h]

  OSVersion = UnBCL::Environment::GetOSVersion(0);
  if ( (unsigned int)UnBCL::OperatingSystem::get_Platform(OSVersion) == 2 )
  {
    if ( (int)UnBCL::String::get_Length(a1) > 260 )
    {
      v3 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
      v10 = v3;
      if ( v3 )
      {
        v4 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_1_();
        UnBCL::PathTooLongException::PathTooLongException(v3, v4);
        *(_QWORD *)v3 = &UnBCL::PathTooLongException::`local vftable';
      }
      else
      {
        v3 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::PathTooLongException>(v3);
      throw (UnBCL::PathTooLongException **)&pExceptionObject;
    }
  }
  else if ( UnBCL::String::StartsWith(a1, L"\\\\?\\", 1) || UnBCL::String::StartsWith(a1, L"\\\\?\\UNC\\", 1) )
  {
    if ( (int)UnBCL::String::get_Length(a1) > 0x7FFF )
    {
      v7 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
      v10 = v7;
      if ( v7 )
      {
        v8 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_2_();
        UnBCL::PathTooLongException::PathTooLongException(v7, v8);
        *(_QWORD *)v7 = &UnBCL::PathTooLongException::`local vftable';
      }
      else
      {
        v7 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::PathTooLongException>(v7);
      throw (UnBCL::PathTooLongException **)&pExceptionObject;
    }
  }
  else if ( (int)UnBCL::String::get_Length(a1) > 260 )
  {
    v5 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
    v10 = v5;
    if ( v5 )
    {
      v6 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_3_();
      UnBCL::PathTooLongException::PathTooLongException(v5, v6);
      *(_QWORD *)v5 = &UnBCL::PathTooLongException::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::PathTooLongException>(v5);
    throw (UnBCL::PathTooLongException **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180013dd8  push    rbx
0x180013dda  sub     rsp, 20h
0x180013dde  mov     rbx, rcx
0x180013de1  xor     ecx, ecx
0x180013de3  call    cs:__imp_?GetOSVersion@Environment@UnBCL@@SAPEBVOperatingSystem@2@H@Z; UnBCL::Environment::GetOSVersion(int)
0x180013de9  mov     rcx, rax
0x180013dec  call    cs:__imp_?get_Platform@OperatingSystem@UnBCL@@QEBA?AW4PlatformID@2@XZ; UnBCL::OperatingSystem::get_Platform(void)
0x180013df2  mov     rcx, rbx
0x180013df5  cmp     eax, 2
0x180013df8  jnz     short loc_180013E47
0x180013dfa  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x180013e00  cmp     eax, 104h
0x180013e05  jle     loc_180013ED2
0x180013e0b  mov     ecx, 38h ; '8'
0x180013e10  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013e16  mov     rbx, rax
0x180013e19  mov     [rsp+28h+arg_10], rax
0x180013e1e  test    rax, rax
0x180013e21  jz      loc_180013F2E
0x180013e27  call    UnBCL_____StringLiteral_1_
0x180013e2c  mov     rdx, rax
0x180013e2f  mov     rcx, rbx
0x180013e32  call    cs:__imp_??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x180013e38  lea     rax, ??_SPathTooLongException@UnBCL@@6B@; const UnBCL::PathTooLongException::`local vftable'
0x180013e3f  mov     [rbx], rax
0x180013e42  jmp     loc_180013F30
0x180013e47  mov     r8d, 1
0x180013e4d  lea     rdx, asc_18003D740; "\\\\?\\"
0x180013e54  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180013e5a  test    eax, eax
0x180013e5c  jnz     short loc_180013EC2
0x180013e5e  lea     r8d, [rax+1]
0x180013e62  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180013e69  mov     rcx, rbx
0x180013e6c  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180013e72  test    eax, eax
0x180013e74  jnz     short loc_180013EC2
0x180013e76  mov     rcx, rbx
0x180013e79  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x180013e7f  cmp     eax, 104h
0x180013e84  jle     short loc_180013ED2
0x180013e86  mov     ecx, 38h ; '8'
0x180013e8b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013e91  mov     rbx, rax
0x180013e94  mov     [rsp+28h+arg_10], rax
0x180013e99  test    rax, rax
0x180013e9c  jz      loc_180013F4F
0x180013ea2  call    UnBCL_____StringLiteral_3_
0x180013ea7  mov     rdx, rax
0x180013eaa  mov     rcx, rbx
0x180013ead  call    cs:__imp_??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x180013eb3  lea     rax, ??_SPathTooLongException@UnBCL@@6B@; const UnBCL::PathTooLongException::`local vftable'
0x180013eba  mov     [rbx], rax
0x180013ebd  jmp     loc_180013F51
0x180013ec2  mov     rcx, rbx
0x180013ec5  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x180013ecb  cmp     eax, 7FFFh
0x180013ed0  jg      short loc_180013ED8
0x180013ed2  add     rsp, 20h
0x180013ed6  pop     rbx
0x180013ed7  retn
0x180013ed8  mov     ecx, 38h ; '8'
0x180013edd  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013ee3  mov     rbx, rax
0x180013ee6  mov     [rsp+28h+arg_10], rax
0x180013eeb  test    rax, rax
0x180013eee  jz      short loc_180013F0D
0x180013ef0  call    UnBCL_____StringLiteral_2_
0x180013ef5  mov     rdx, rax
0x180013ef8  mov     rcx, rbx
0x180013efb  call    cs:__imp_??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x180013f01  lea     rax, ??_SPathTooLongException@UnBCL@@6B@; const UnBCL::PathTooLongException::`local vftable'
0x180013f08  mov     [rbx], rax
0x180013f0b  jmp     short loc_180013F0F
0x180013f0d  xor     ebx, ebx
0x180013f0f  mov     rcx, rbx
0x180013f12  call    ??$AddStackTraceToException@VPathTooLongException@UnBCL@@@@YAPEAVPathTooLongException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::PathTooLongException>(UnBCL::PathTooLongException *,char const *)
0x180013f17  mov     [rsp+28h+pExceptionObject], rax
0x180013f1c  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x180013f23  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180013f28  call    _CxxThrowException_0
0x180013f2e  xor     ebx, ebx
0x180013f30  mov     rcx, rbx
0x180013f33  call    ??$AddStackTraceToException@VPathTooLongException@UnBCL@@@@YAPEAVPathTooLongException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::PathTooLongException>(UnBCL::PathTooLongException *,char const *)
0x180013f38  mov     [rsp+28h+pExceptionObject], rax
0x180013f3d  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x180013f44  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180013f49  call    _CxxThrowException_0
0x180013f4f  xor     ebx, ebx
0x180013f51  mov     rcx, rbx
0x180013f54  call    ??$AddStackTraceToException@VPathTooLongException@UnBCL@@@@YAPEAVPathTooLongException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::PathTooLongException>(UnBCL::PathTooLongException *,char const *)
0x180013f59  mov     [rsp+28h+pExceptionObject], rax
0x180013f5e  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x180013f65  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180013f6a  call    _CxxThrowException_0
```
