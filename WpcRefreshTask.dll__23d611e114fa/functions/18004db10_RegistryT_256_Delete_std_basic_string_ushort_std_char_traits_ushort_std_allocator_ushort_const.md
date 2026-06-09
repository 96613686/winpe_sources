# RegistryT<256>::Delete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004db10`
- end: `0x18004dc57`
- name: `?Delete@?$RegistryT@$0BAA@@@UEAAAEAV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800920dc`

## callees

- `0x180006ee0`
- `0x18000e93c`
- `0x180035af4`
- `0x180035e0c`
- `0x18004db10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004db63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004db63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004db3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004db3d`

## pseudocode

```c
__int64 __fastcall RegistryT<256>::Delete(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  LSTATUS v4; // eax
  unsigned int v5; // edi
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  __int64 v11; // r10
  int v12; // eax
  __int64 v13; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  v2 = a2;
  if ( *((_QWORD *)a2 + 2) < 0x100u )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    v4 = RegDeleteTreeW(*(HKEY *)(a1 + 16), a2);
    v5 = v4;
    if ( (v4 & 0xFFFFFFFD) != 0 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = std::wstring::c_str(v2);
        WPP_SF_Sd(*(_QWORD *)(v13 + 16), 16, (int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v12, v5);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v6 = v2;
  else
    v6 = *(const WCHAR **)v2;
  v7 = RegDeleteValueW(*(HKEY *)(a1 + 16), v6);
  v8 = v7;
  if ( (v7 & 0xFFFFFFFD) != 0 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = std::wstring::c_str(v2);
      WPP_SF_Sd(*(_QWORD *)(v11 + 16), 17, (int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v10, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18004db10  mov     [rsp+arg_0], rbx
0x18004db15  mov     [rsp+arg_8], rsi
0x18004db1a  push    rdi
0x18004db1b  sub     rsp, 60h
0x18004db1f  cmp     qword ptr [rdx+10h], 100h
0x18004db27  mov     rbx, rdx
0x18004db2a  mov     rsi, rcx
0x18004db2d  jnb     short loc_18004DB50
0x18004db2f  cmp     qword ptr [rdx+18h], 7
0x18004db34  jbe     short loc_18004DB39
0x18004db36  mov     rdx, [rdx]; lpSubKey
0x18004db39  mov     rcx, [rcx+10h]; hKey
0x18004db3d  call    cs:__imp_RegDeleteTreeW
0x18004db43  mov     edi, eax
0x18004db45  test    eax, 0FFFFFFFDh
0x18004db4a  jnz     loc_18004DBEE
0x18004db50  cmp     qword ptr [rbx+18h], 7
0x18004db55  jbe     short loc_18004DB5C
0x18004db57  mov     rdx, [rbx]
0x18004db5a  jmp     short loc_18004DB5F
0x18004db5c  mov     rdx, rbx; lpValueName
0x18004db5f  mov     rcx, [rsi+10h]; hKey
0x18004db63  call    cs:__imp_RegDeleteValueW
0x18004db69  mov     edi, eax
0x18004db6b  test    eax, 0FFFFFFFDh
0x18004db70  jnz     short loc_18004DB85
0x18004db72  mov     rbx, [rsp+68h+arg_0]
0x18004db77  mov     rax, rsi
0x18004db7a  mov     rsi, [rsp+68h+arg_8]
0x18004db7f  add     rsp, 60h
0x18004db83  pop     rdi
0x18004db84  retn
0x18004db85  test    eax, eax
0x18004db87  jle     short loc_18004DB92
0x18004db89  movzx   edi, ax
0x18004db8c  or      edi, 80070000h
0x18004db92  mov     r10, cs:WPP_GLOBAL_Control
0x18004db99  lea     rax, WPP_GLOBAL_Control
0x18004dba0  cmp     r10, rax
0x18004dba3  jz      short loc_18004DBD0
0x18004dba5  test    byte ptr [r10+1Ch], 1
0x18004dbaa  jz      short loc_18004DBD0
0x18004dbac  mov     rcx, rbx
0x18004dbaf  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004dbb4  mov     rcx, [r10+10h]
0x18004dbb8  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x18004dbbf  mov     r9, rax
0x18004dbc2  mov     [rsp+68h+var_48], edi
0x18004dbc6  mov     edx, 11h
0x18004dbcb  call    WPP_SF_Sd
0x18004dbd0  mov     edx, edi; int
0x18004dbd2  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18004dbd7  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004dbdc  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004dbe3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18004dbe8  call    _CxxThrowException_0
0x18004dbee  test    eax, eax
0x18004dbf0  jle     short loc_18004DBFB
0x18004dbf2  movzx   edi, ax
0x18004dbf5  or      edi, 80070000h
0x18004dbfb  mov     r10, cs:WPP_GLOBAL_Control
0x18004dc02  lea     rax, WPP_GLOBAL_Control
0x18004dc09  cmp     r10, rax
0x18004dc0c  jz      short loc_18004DC39
0x18004dc0e  test    byte ptr [r10+1Ch], 1
0x18004dc13  jz      short loc_18004DC39
0x18004dc15  mov     rcx, rbx
0x18004dc18  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004dc1d  mov     rcx, [r10+10h]
0x18004dc21  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x18004dc28  mov     r9, rax
0x18004dc2b  mov     [rsp+68h+var_48], edi
0x18004dc2f  mov     edx, 10h
0x18004dc34  call    WPP_SF_Sd
0x18004dc39  mov     edx, edi; int
0x18004dc3b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18004dc40  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004dc45  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004dc4c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18004dc51  call    _CxxThrowException_0
```
