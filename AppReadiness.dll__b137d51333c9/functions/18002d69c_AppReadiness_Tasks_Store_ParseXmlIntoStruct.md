# AppReadiness::Tasks::Store::ParseXmlIntoStruct

- ea: `0x18002d69c`
- end: `0x18002d8da`
- name: `AppReadiness::Tasks::Store::ParseXmlIntoStruct`
- size: `574`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c8f0`
- `0x18002d4e0`
- `0x18002d5d0`
- `0x18002e950`
- `0x18002eefc`

## callees

- `0x18000e4a0`
- `0x180027a4c`
- `0x18002bf58`
- `0x18002d69c`
- `0x18003893c`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800689a8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d7d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d7d9`

## string_xrefs

- `0x18002d6fd`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18002d87d`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18002d710`: `reader->GetNodeType(&nodeType)`
- `0x18002d890`: `reader->GetLocalName(&elementName, nullptr)`
- `0x18002d709`: `AppReadiness::Tasks::Store::ParseXmlIntoStruct`
- `0x18002d889`: `AppReadiness::Tasks::Store::ParseXmlIntoStruct`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppReadiness::Tasks::Store::ParseXmlIntoStruct(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 result; // rax
  bool v10; // r14
  int v11; // eax
  unsigned __int64 i; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // [rsp+30h] [rbp-41h] BYREF
  LPCWCH lpString2; // [rsp+38h] [rbp-39h] BYREF
  __int64 v17; // [rsp+40h] [rbp-31h]
  LPCWCH v18; // [rsp+48h] [rbp-29h] BYREF
  __int64 v19; // [rsp+50h] [rbp-21h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-19h] BYREF

  v17 = a5;
  v15 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &v15);
  if ( (int)result < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      result,
      "reader->GetNodeType(&nodeType)",
      "AppReadiness::Tasks::Store::ParseXmlIntoStruct",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
      412);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( v15 == 1 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
    if ( !(_DWORD)result )
    {
      v10 = 0;
LABEL_6:
      while ( !v10 )
      {
        result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 48LL))(a1, &v15);
        if ( (_DWORD)result )
          break;
        if ( v15 == 1 )
        {
          lpString2 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, LPCWCH *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, &lpString2, 0);
          if ( v11 < 0 )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)pExceptionObject,
              v11,
              "reader->GetLocalName(&elementName, nullptr)",
              "AppReadiness::Tasks::Store::ParseXmlIntoStruct",
              "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
              428);
            throw (Windows::HResultException *)pExceptionObject;
          }
          for ( i = 0; i < a2; ++i )
          {
            if ( CompareStringOrdinal(*(LPCWCH *)(a3 + 24 * i), -1, lpString2, -1, 0) == 2 )
            {
              AppReadiness::Tasks::Store::ReadElementString(pExceptionObject, a1);
              v13 = *(_QWORD *)(a3 + 24 * i + 8);
              if ( *(_QWORD *)(a3 + 24 * i + 16) )
                (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(a3 + 24 * i + 16))(
                  *(_QWORD *)(a3 + 24 * i),
                  pExceptionObject,
                  v13 + a4);
              else
                std::wstring::operator=(v13 + a4, pExceptionObject);
              result = std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
              goto LABEL_6;
            }
          }
          v14 = *(_QWORD *)(v17 + 56);
          if ( !v14
            || (v18 = lpString2,
                v19 = a1,
                result = (*(__int64 (__fastcall **)(__int64, __int64 *, LPCWCH *))(*(_QWORD *)v14 + 16LL))(
                           v14,
                           &v19,
                           &v18),
                (_BYTE)result) )
          {
            result = AppReadiness::Tasks::Store::Skip(a1);
          }
        }
        else
        {
          v10 = v15 == 15;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d69c  mov     [rsp-8+arg_8], rbx
0x18002d6a1  push    rbp
0x18002d6a2  push    rsi
0x18002d6a3  push    rdi
0x18002d6a4  push    r12
0x18002d6a6  push    r13
0x18002d6a8  push    r14
0x18002d6aa  push    r15
0x18002d6ac  lea     rbp, [rsp-1Fh]
0x18002d6b1  sub     rsp, 90h
0x18002d6b8  mov     rax, cs:__security_cookie
0x18002d6bf  xor     rax, rsp
0x18002d6c2  mov     [rbp+4Fh+var_40], rax
0x18002d6c6  mov     r12, r9
0x18002d6c9  mov     r15, r8
0x18002d6cc  mov     r13, rdx
0x18002d6cf  mov     rbx, rcx
0x18002d6d2  mov     rsi, [rbp+4Fh+arg_20]
0x18002d6d6  mov     [rbp+4Fh+var_80], rsi
0x18002d6da  mov     [rbp+4Fh+var_90], 0
0x18002d6e1  mov     rax, [rcx]
0x18002d6e4  lea     rdx, [rbp+4Fh+var_90]
0x18002d6e8  mov     rax, [rax+38h]
0x18002d6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6f1  test    eax, eax
0x18002d6f3  jns     short loc_18002D733
0x18002d6f5  mov     [rsp+0C0h+var_98], 19Ch; int
0x18002d6fd  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002d704  mov     qword ptr [rsp+0C0h+bIgnoreCase], rcx; char *
0x18002d709  lea     r9, aAppreadinessTa_31; "AppReadiness::Tasks::Store::ParseXmlInt"...
0x18002d710  lea     r8, aReaderGetnodet; "reader->GetNodeType(&nodeType)"
0x18002d717  mov     edx, eax; int
0x18002d719  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18002d71d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002d722  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002d729  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18002d72d  call    _CxxThrowException_0
0x18002d733  cmp     [rbp+4Fh+var_90], 1
0x18002d737  jnz     loc_18002D8B3
0x18002d73d  mov     rax, [rbx]
0x18002d740  mov     rcx, rbx
0x18002d743  mov     rax, [rax+0A0h]
0x18002d74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d74f  test    eax, eax
0x18002d751  jnz     loc_18002D8B3
0x18002d757  xor     r14b, r14b
0x18002d75a  test    r14b, r14b
0x18002d75d  jnz     loc_18002D8B3
0x18002d763  mov     rax, [rbx]
0x18002d766  lea     rdx, [rbp+4Fh+var_90]
0x18002d76a  mov     rcx, rbx
0x18002d76d  mov     rax, [rax+30h]
0x18002d771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d776  test    eax, eax
0x18002d778  jnz     loc_18002D8B3
0x18002d77e  mov     ecx, [rbp+4Fh+var_90]
0x18002d781  sub     ecx, 1
0x18002d784  jz      short loc_18002D790
0x18002d786  cmp     ecx, 0Eh
0x18002d789  jnz     short loc_18002D75A
0x18002d78b  mov     r14b, 1
0x18002d78e  jmp     short loc_18002D75A
0x18002d790  mov     [rbp+4Fh+lpString2], 0
0x18002d798  mov     rax, [rbx]
0x18002d79b  xor     r8d, r8d
0x18002d79e  lea     rdx, [rbp+4Fh+lpString2]
0x18002d7a2  mov     rcx, rbx
0x18002d7a5  mov     rax, [rax+70h]
0x18002d7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ae  test    eax, eax
0x18002d7b0  js      loc_18002D875
0x18002d7b6  xor     edi, edi
0x18002d7b8  cmp     rdi, r13
0x18002d7bb  jnb     short loc_18002D833
0x18002d7bd  lea     rsi, [rdi+rdi*2]
0x18002d7c1  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x18002d7c9  or      eax, 0FFFFFFFFh
0x18002d7cc  mov     r9d, eax; cchCount2
0x18002d7cf  mov     r8, [rbp+4Fh+lpString2]; lpString2
0x18002d7d3  mov     edx, eax; cchCount1
0x18002d7d5  mov     rcx, [r15+rsi*8]; lpString1
0x18002d7d9  call    cs:__imp_CompareStringOrdinal
0x18002d7df  cmp     eax, 2
0x18002d7e2  jz      short loc_18002D7E9
0x18002d7e4  inc     rdi
0x18002d7e7  jmp     short loc_18002D7B8
0x18002d7e9  mov     rdx, rbx
0x18002d7ec  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18002d7f0  call    AppReadiness__Tasks__Store__ReadElementString
0x18002d7f5  nop
0x18002d7f6  mov     r9, [r15+rsi*8+10h]
0x18002d7fb  mov     rax, [r15+rsi*8+8]
0x18002d800  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18002d804  test    r9, r9
0x18002d807  jnz     short loc_18002D814
0x18002d809  lea     rcx, [rax+r12]
0x18002d80d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002d812  jmp     short loc_18002D825
0x18002d814  lea     r8, [rax+r12]
0x18002d818  mov     rcx, [r15+rsi*8]
0x18002d81c  mov     rax, r9
0x18002d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d824  nop
0x18002d825  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18002d829  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002d82e  jmp     loc_18002D75A
0x18002d833  mov     rax, [rbp+4Fh+var_80]
0x18002d837  mov     rcx, [rax+38h]
0x18002d83b  test    rcx, rcx
0x18002d83e  jz      short loc_18002D868
0x18002d840  mov     rax, [rbp+4Fh+lpString2]
0x18002d844  mov     [rbp+4Fh+var_78], rax
0x18002d848  mov     [rbp+4Fh+var_70], rbx
0x18002d84c  mov     rax, [rcx]
0x18002d84f  lea     r8, [rbp+4Fh+var_78]
0x18002d853  lea     rdx, [rbp+4Fh+var_70]
0x18002d857  mov     rax, [rax+10h]
0x18002d85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d860  test    al, al
0x18002d862  jz      loc_18002D75A
0x18002d868  mov     rcx, rbx
0x18002d86b  call    AppReadiness__Tasks__Store__Skip
0x18002d870  jmp     loc_18002D75A
0x18002d875  mov     [rsp+0C0h+var_98], 1ACh; int
0x18002d87d  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002d884  mov     qword ptr [rsp+0C0h+bIgnoreCase], rcx; char *
0x18002d889  lea     r9, aAppreadinessTa_31; "AppReadiness::Tasks::Store::ParseXmlInt"...
0x18002d890  lea     r8, aReaderGetlocal_0; "reader->GetLocalName(&elementName, null"...
0x18002d897  mov     edx, eax; int
0x18002d899  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18002d89d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002d8a2  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002d8a9  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18002d8ad  call    _CxxThrowException_0
0x18002d8b3  mov     rcx, [rbp+4Fh+var_40]
0x18002d8b7  xor     rcx, rsp; StackCookie
0x18002d8ba  call    __security_check_cookie
0x18002d8bf  mov     rbx, [rsp+0C0h+arg_8]
0x18002d8c7  add     rsp, 90h
0x18002d8ce  pop     r15
0x18002d8d0  pop     r14
0x18002d8d2  pop     r13
0x18002d8d4  pop     r12
0x18002d8d6  pop     rdi
0x18002d8d7  pop     rsi
0x18002d8d8  pop     rbp
0x18002d8d9  retn
```
