# RegistryT<256>::Delete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800260c0`
- end: `0x180026207`
- name: `?Delete@?$RegistryT@$0BAA@@@UEAAAEAV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180003d20`
- `0x18000a9b0`
- `0x18000dd9c`
- `0x1800195c4`
- `0x1800260c0`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x1800260ed`
- `ADVAPI32!RegDeleteTreeW` at `0x1800260ed`
- `ADVAPI32!RegDeleteValueW` at `0x180026113`
- `ADVAPI32!RegDeleteValueW` at `0x180026113`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v12 = std::wstring::c_str(v2);
        WPP_SF_Sd(*(_QWORD *)(v13 + 16), 16, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v12, v5);
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
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = std::wstring::c_str(v2);
      WPP_SF_Sd(*(_QWORD *)(v11 + 16), 17, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v10, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x1800260c0  mov     [rsp+arg_0], rbx
0x1800260c5  mov     [rsp+arg_8], rsi
0x1800260ca  push    rdi
0x1800260cb  sub     rsp, 60h
0x1800260cf  cmp     qword ptr [rdx+10h], 100h
0x1800260d7  mov     rbx, rdx
0x1800260da  mov     rsi, rcx
0x1800260dd  jnb     short loc_180026100
0x1800260df  cmp     qword ptr [rdx+18h], 7
0x1800260e4  jbe     short loc_1800260E9
0x1800260e6  mov     rdx, [rdx]; lpSubKey
0x1800260e9  mov     rcx, [rcx+10h]; hKey
0x1800260ed  call    cs:__imp_RegDeleteTreeW
0x1800260f3  mov     edi, eax
0x1800260f5  test    eax, 0FFFFFFFDh
0x1800260fa  jnz     loc_18002619E
0x180026100  cmp     qword ptr [rbx+18h], 7
0x180026105  jbe     short loc_18002610C
0x180026107  mov     rdx, [rbx]
0x18002610a  jmp     short loc_18002610F
0x18002610c  mov     rdx, rbx; lpValueName
0x18002610f  mov     rcx, [rsi+10h]; hKey
0x180026113  call    cs:__imp_RegDeleteValueW
0x180026119  mov     edi, eax
0x18002611b  test    eax, 0FFFFFFFDh
0x180026120  jnz     short loc_180026135
0x180026122  mov     rbx, [rsp+68h+arg_0]
0x180026127  mov     rax, rsi
0x18002612a  mov     rsi, [rsp+68h+arg_8]
0x18002612f  add     rsp, 60h
0x180026133  pop     rdi
0x180026134  retn
0x180026135  test    eax, eax
0x180026137  jle     short loc_180026142
0x180026139  movzx   edi, ax
0x18002613c  or      edi, 80070000h
0x180026142  mov     r10, cs:WPP_GLOBAL_Control
0x180026149  lea     rax, WPP_GLOBAL_Control
0x180026150  cmp     r10, rax
0x180026153  jz      short loc_180026180
0x180026155  test    byte ptr [r10+1Ch], 1
0x18002615a  jz      short loc_180026180
0x18002615c  mov     rcx, rbx
0x18002615f  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180026164  mov     rcx, [r10+10h]
0x180026168  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x18002616f  mov     r9, rax
0x180026172  mov     [rsp+68h+var_48], edi
0x180026176  mov     edx, 11h
0x18002617b  call    WPP_SF_Sd
0x180026180  mov     edx, edi; int
0x180026182  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180026187  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002618c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180026193  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180026198  call    _CxxThrowException_0
0x18002619e  test    eax, eax
0x1800261a0  jle     short loc_1800261AB
0x1800261a2  movzx   edi, ax
0x1800261a5  or      edi, 80070000h
0x1800261ab  mov     r10, cs:WPP_GLOBAL_Control
0x1800261b2  lea     rax, WPP_GLOBAL_Control
0x1800261b9  cmp     r10, rax
0x1800261bc  jz      short loc_1800261E9
0x1800261be  test    byte ptr [r10+1Ch], 1
0x1800261c3  jz      short loc_1800261E9
0x1800261c5  mov     rcx, rbx
0x1800261c8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800261cd  mov     rcx, [r10+10h]
0x1800261d1  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x1800261d8  mov     r9, rax
0x1800261db  mov     [rsp+68h+var_48], edi
0x1800261df  mov     edx, 10h
0x1800261e4  call    WPP_SF_Sd
0x1800261e9  mov     edx, edi; int
0x1800261eb  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800261f0  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800261f5  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800261fc  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180026201  call    _CxxThrowException_0
```
