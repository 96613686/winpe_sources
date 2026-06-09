# _anonymous_namespace_::StorageValue_256_::WriteInt32

- ea: `0x180027120`
- end: `0x1800271db`
- name: `_anonymous_namespace_::StorageValue_256_::WriteInt32`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003d20`
- `0x18000a9b0`
- `0x18000dd9c`
- `0x1800195c4`
- `0x180027120`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002715d`
- `ADVAPI32!RegSetValueExW` at `0x18002715d`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::StorageValue_256_::WriteInt32(__int64 a1, int a2)
{
  const WCHAR **v2; // rdi
  const WCHAR *v3; // rdx
  LSTATUS result; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF

  Data = a2;
  v2 = (const WCHAR **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) <= 7u )
    v3 = (const WCHAR *)(a1 + 16);
  else
    v3 = *v2;
  result = RegSetValueExW(*(HKEY *)(a1 + 48), v3, 0, 4u, (const BYTE *)&Data, 4u);
  v5 = result;
  if ( result )
  {
    if ( result > 0 )
      v5 = (unsigned __int16)result | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = std::wstring::c_str(v2);
      WPP_SF_Sd(*(_QWORD *)(v7 + 16), 12, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v6, v5);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180027120  mov     [rsp+arg_0], rbx
0x180027125  mov     [rsp+Data], edx
0x180027129  push    rdi
0x18002712a  sub     rsp, 60h
0x18002712e  lea     rdi, [rcx+10h]
0x180027132  cmp     qword ptr [rdi+18h], 7
0x180027137  jbe     short loc_18002713E
0x180027139  mov     rdx, [rdi]
0x18002713c  jmp     short loc_180027141
0x18002713e  mov     rdx, rdi; lpValueName
0x180027141  mov     rcx, [rcx+30h]; hKey
0x180027145  lea     rax, [rsp+68h+Data]
0x18002714a  mov     r9d, 4; dwType
0x180027150  xor     r8d, r8d; Reserved
0x180027153  mov     [rsp+68h+cbData], r9d; cbData
0x180027158  mov     [rsp+68h+lpData], rax; lpData
0x18002715d  call    cs:__imp_RegSetValueExW
0x180027163  mov     ebx, eax
0x180027165  test    eax, eax
0x180027167  jnz     short loc_180027174
0x180027169  mov     rbx, [rsp+68h+arg_0]
0x18002716e  add     rsp, 60h
0x180027172  pop     rdi
0x180027173  retn
0x180027174  jle     short loc_18002717F
0x180027176  movzx   ebx, ax
0x180027179  or      ebx, 80070000h
0x18002717f  mov     r10, cs:WPP_GLOBAL_Control
0x180027186  lea     rax, WPP_GLOBAL_Control
0x18002718d  cmp     r10, rax
0x180027190  jz      short loc_1800271BD
0x180027192  test    byte ptr [r10+1Ch], 1
0x180027197  jz      short loc_1800271BD
0x180027199  mov     rcx, rdi
0x18002719c  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800271a1  mov     rcx, [r10+10h]
0x1800271a5  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x1800271ac  mov     r9, rax
0x1800271af  mov     dword ptr [rsp+68h+lpData], ebx
0x1800271b3  mov     edx, 0Ch
0x1800271b8  call    WPP_SF_Sd
0x1800271bd  mov     edx, ebx; int
0x1800271bf  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800271c4  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800271c9  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800271d0  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800271d5  call    _CxxThrowException_0
```
