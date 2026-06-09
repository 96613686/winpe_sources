# _anonymous_namespace_::StorageValue_256_::WriteString

- ea: `0x1800272c0`
- end: `0x18002738a`
- name: `_anonymous_namespace_::StorageValue_256_::WriteString`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003d20`
- `0x18000a9b0`
- `0x18000dd9c`
- `0x1800195c4`
- `0x1800272c0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002730c`
- `ADVAPI32!RegSetValueExW` at `0x18002730c`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::StorageValue_256_::WriteString(__int64 a1, __int64 *lpData)
{
  DWORD cbData; // r8d
  const WCHAR **v3; // rdi
  const WCHAR *v4; // rax
  LSTATUS result; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  cbData = 2 * *((_DWORD *)lpData + 4) + 2;
  if ( (unsigned __int64)lpData[3] > 7 )
    lpData = (__int64 *)*lpData;
  v3 = (const WCHAR **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) <= 7u )
    v4 = (const WCHAR *)(a1 + 16);
  else
    v4 = *v3;
  result = RegSetValueExW(*(HKEY *)(a1 + 48), v4, 0, 1u, (const BYTE *)lpData, cbData);
  v6 = result;
  if ( result )
  {
    if ( result > 0 )
      v6 = (unsigned __int16)result | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = std::wstring::c_str(v3);
      WPP_SF_Sd(*(_QWORD *)(v8 + 16), 14, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v7, v6);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800272c0  mov     [rsp+arg_0], rbx
0x1800272c5  push    rdi
0x1800272c6  sub     rsp, 60h
0x1800272ca  cmp     qword ptr [rdx+18h], 7
0x1800272cf  mov     eax, [rdx+10h]
0x1800272d2  lea     r8d, ds:2[rax*2]
0x1800272da  jbe     short loc_1800272DF
0x1800272dc  mov     rdx, [rdx]
0x1800272df  lea     rdi, [rcx+10h]
0x1800272e3  cmp     qword ptr [rdi+18h], 7
0x1800272e8  jbe     short loc_1800272EF
0x1800272ea  mov     rax, [rdi]
0x1800272ed  jmp     short loc_1800272F2
0x1800272ef  mov     rax, rdi
0x1800272f2  mov     rcx, [rcx+30h]; hKey
0x1800272f6  mov     r9d, 1; dwType
0x1800272fc  mov     [rsp+68h+cbData], r8d; cbData
0x180027301  xor     r8d, r8d; Reserved
0x180027304  mov     [rsp+68h+lpData], rdx; lpData
0x180027309  mov     rdx, rax; lpValueName
0x18002730c  call    cs:__imp_RegSetValueExW
0x180027312  mov     ebx, eax
0x180027314  test    eax, eax
0x180027316  jnz     short loc_180027323
0x180027318  mov     rbx, [rsp+68h+arg_0]
0x18002731d  add     rsp, 60h
0x180027321  pop     rdi
0x180027322  retn
0x180027323  jle     short loc_18002732E
0x180027325  movzx   ebx, ax
0x180027328  or      ebx, 80070000h
0x18002732e  mov     r10, cs:WPP_GLOBAL_Control
0x180027335  lea     rax, WPP_GLOBAL_Control
0x18002733c  cmp     r10, rax
0x18002733f  jz      short loc_18002736C
0x180027341  test    byte ptr [r10+1Ch], 1
0x180027346  jz      short loc_18002736C
0x180027348  mov     rcx, rdi
0x18002734b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180027350  mov     rcx, [r10+10h]
0x180027354  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x18002735b  mov     r9, rax
0x18002735e  mov     dword ptr [rsp+68h+lpData], ebx
0x180027362  mov     edx, 0Eh
0x180027367  call    WPP_SF_Sd
0x18002736c  mov     edx, ebx; int
0x18002736e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027373  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027378  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002737f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027384  call    _CxxThrowException_0
```
