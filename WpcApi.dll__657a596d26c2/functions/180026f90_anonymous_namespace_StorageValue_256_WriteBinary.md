# _anonymous_namespace_::StorageValue_256_::WriteBinary

- ea: `0x180026f90`
- end: `0x180027045`
- name: `_anonymous_namespace_::StorageValue_256_::WriteBinary`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003d20`
- `0x18000a9b0`
- `0x18000dd9c`
- `0x1800195c4`
- `0x180026f90`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180026fc7`
- `ADVAPI32!RegSetValueExW` at `0x180026fc7`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::StorageValue_256_::WriteBinary(__int64 a1, const BYTE *a2, DWORD cbData)
{
  const WCHAR **v3; // rdi
  const WCHAR *v5; // rdx
  LSTATUS result; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  v3 = (const WCHAR **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) <= 7u )
    v5 = (const WCHAR *)(a1 + 16);
  else
    v5 = *v3;
  result = RegSetValueExW(*(HKEY *)(a1 + 48), v5, 0, 3u, a2, cbData);
  v7 = result;
  if ( result )
  {
    if ( result > 0 )
      v7 = (unsigned __int16)result | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = std::wstring::c_str(v3);
      WPP_SF_Sd(*(_QWORD *)(v9 + 16), 11, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v8, v7);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180026f90  mov     [rsp+arg_0], rbx
0x180026f95  push    rdi
0x180026f96  sub     rsp, 60h
0x180026f9a  lea     rdi, [rcx+10h]
0x180026f9e  mov     rax, rdx
0x180026fa1  cmp     qword ptr [rdi+18h], 7
0x180026fa6  jbe     short loc_180026FAD
0x180026fa8  mov     rdx, [rdi]
0x180026fab  jmp     short loc_180026FB0
0x180026fad  mov     rdx, rdi; lpValueName
0x180026fb0  mov     rcx, [rcx+30h]; hKey
0x180026fb4  mov     r9d, 3; dwType
0x180026fba  mov     [rsp+68h+cbData], r8d; cbData
0x180026fbf  xor     r8d, r8d; Reserved
0x180026fc2  mov     [rsp+68h+lpData], rax; lpData
0x180026fc7  call    cs:__imp_RegSetValueExW
0x180026fcd  mov     ebx, eax
0x180026fcf  test    eax, eax
0x180026fd1  jnz     short loc_180026FDE
0x180026fd3  mov     rbx, [rsp+68h+arg_0]
0x180026fd8  add     rsp, 60h
0x180026fdc  pop     rdi
0x180026fdd  retn
0x180026fde  jle     short loc_180026FE9
0x180026fe0  movzx   ebx, ax
0x180026fe3  or      ebx, 80070000h
0x180026fe9  mov     r10, cs:WPP_GLOBAL_Control
0x180026ff0  lea     rax, WPP_GLOBAL_Control
0x180026ff7  cmp     r10, rax
0x180026ffa  jz      short loc_180027027
0x180026ffc  test    byte ptr [r10+1Ch], 1
0x180027001  jz      short loc_180027027
0x180027003  mov     rcx, rdi
0x180027006  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002700b  mov     rcx, [r10+10h]
0x18002700f  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x180027016  mov     r9, rax
0x180027019  mov     dword ptr [rsp+68h+lpData], ebx
0x18002701d  mov     edx, 0Bh
0x180027022  call    WPP_SF_Sd
0x180027027  mov     edx, ebx; int
0x180027029  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002702e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027033  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002703a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002703f  call    _CxxThrowException_0
```
