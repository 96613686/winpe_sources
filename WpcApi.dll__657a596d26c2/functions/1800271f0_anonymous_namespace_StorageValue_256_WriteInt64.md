# _anonymous_namespace_::StorageValue_256_::WriteInt64

- ea: `0x1800271f0`
- end: `0x1800272af`
- name: `_anonymous_namespace_::StorageValue_256_::WriteInt64`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003d20`
- `0x18000a9b0`
- `0x18000dd9c`
- `0x1800195c4`
- `0x1800271f0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180027231`
- `ADVAPI32!RegSetValueExW` at `0x180027231`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::StorageValue_256_::WriteInt64(__int64 a1, __int64 a2)
{
  const WCHAR **v2; // rdi
  const WCHAR *v3; // rdx
  LSTATUS result; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  __int64 Data; // [rsp+78h] [rbp+10h] BYREF

  Data = a2;
  v2 = (const WCHAR **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) <= 7u )
    v3 = (const WCHAR *)(a1 + 16);
  else
    v3 = *v2;
  result = RegSetValueExW(*(HKEY *)(a1 + 48), v3, 0, 0xBu, (const BYTE *)&Data, 8u);
  v5 = result;
  if ( result )
  {
    if ( result > 0 )
      v5 = (unsigned __int16)result | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = std::wstring::c_str(v2);
      WPP_SF_Sd(*(_QWORD *)(v7 + 16), 13, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v6, v5);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800271f0  mov     [rsp+arg_0], rbx
0x1800271f5  mov     [rsp+Data], rdx
0x1800271fa  push    rdi
0x1800271fb  sub     rsp, 60h
0x1800271ff  lea     rdi, [rcx+10h]
0x180027203  cmp     qword ptr [rdi+18h], 7
0x180027208  jbe     short loc_18002720F
0x18002720a  mov     rdx, [rdi]
0x18002720d  jmp     short loc_180027212
0x18002720f  mov     rdx, rdi; lpValueName
0x180027212  mov     rcx, [rcx+30h]; hKey
0x180027216  lea     rax, [rsp+68h+Data]
0x18002721b  mov     [rsp+68h+cbData], 8; cbData
0x180027223  mov     r9d, 0Bh; dwType
0x180027229  xor     r8d, r8d; Reserved
0x18002722c  mov     [rsp+68h+lpData], rax; lpData
0x180027231  call    cs:__imp_RegSetValueExW
0x180027237  mov     ebx, eax
0x180027239  test    eax, eax
0x18002723b  jnz     short loc_180027248
0x18002723d  mov     rbx, [rsp+68h+arg_0]
0x180027242  add     rsp, 60h
0x180027246  pop     rdi
0x180027247  retn
0x180027248  jle     short loc_180027253
0x18002724a  movzx   ebx, ax
0x18002724d  or      ebx, 80070000h
0x180027253  mov     r10, cs:WPP_GLOBAL_Control
0x18002725a  lea     rax, WPP_GLOBAL_Control
0x180027261  cmp     r10, rax
0x180027264  jz      short loc_180027291
0x180027266  test    byte ptr [r10+1Ch], 1
0x18002726b  jz      short loc_180027291
0x18002726d  mov     rcx, rdi
0x180027270  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180027275  mov     rcx, [r10+10h]
0x180027279  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x180027280  mov     r9, rax
0x180027283  mov     dword ptr [rsp+68h+lpData], ebx
0x180027287  mov     edx, 0Dh
0x18002728c  call    WPP_SF_Sd
0x180027291  mov     edx, ebx; int
0x180027293  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027298  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002729d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800272a4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800272a9  call    _CxxThrowException_0
```
