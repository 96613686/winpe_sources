# ProcessDriver32Info(ulong,_WINMMDRIVERINFO *,bool)

- ea: `0x180010be0`
- end: `0x180010d9f`
- name: `?ProcessDriver32Info@@YAJKPEAU_WINMMDRIVERINFO@@_N@Z`
- size: `447`
- prototype: `__int64 __fastcall(unsigned int, struct _WINMMDRIVERINFO *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038d98`

## callees

- `0x180010be0`
- `0x180010da8`
- `0x180010dd0`
- `0x180033464`
- `0x18003e920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010d05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010d05`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180010d2d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180010d4a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180010d2d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180010d4a`

## string_xrefs

- `0x180010c52`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180010c6e`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180010d65`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180010d86`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`

## pseudocode

```c
__int64 __fastcall ProcessDriver32Info(unsigned int a1, struct _WINMMDRIVERINFO *a2, char a3)
{
  __int64 v4; // r14
  int i; // edi
  int v7; // eax
  unsigned int v8; // ebx
  char *v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int pdwType; // [rsp+20h] [rbp-68h]
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD v15; // [rsp+44h] [rbp-44h] BYREF
  WCHAR Value[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = a1;
  v15 = 0;
  for ( i = 1; ; ++i )
  {
    while ( 1 )
    {
      if ( i > 9 )
        return 0;
      v7 = StringCchPrintfW(Value, 7u, L"%s%d", (&aliasTypes)[v4]);
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
          (const char *)(unsigned int)v7,
          i);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
          (const char *)v8,
          pdwType);
        return v8;
      }
      v10 = (char *)a2 + 522 * i;
      if ( a3 )
        break;
      pcbData = 260;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
              Value,
              2u,
              &v15,
              v10 + 2,
              &pcbData) )
        *v10 = 1;
LABEL_8:
      ++i;
    }
    if ( !*v10 || v10[1] )
      goto LABEL_8;
    v11 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32", Value);
    if ( v11 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x4E,
               (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
               (const char *)v11,
               i);
    v12 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
            Value);
    if ( v12 )
      break;
    *v10 = 0;
  }
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x50,
           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
           (const char *)v12,
           i);
}

```

## disassembly

```asm
0x180010be0  push    rbp
0x180010be2  push    rsi
0x180010be3  push    rdi
0x180010be4  push    r14
0x180010be6  push    r15
0x180010be8  sub     rsp, 60h
0x180010bec  mov     rax, cs:__security_cookie
0x180010bf3  xor     rax, rsp
0x180010bf6  mov     [rsp+88h+var_30], rax
0x180010bfb  movzx   esi, r8b
0x180010bff  mov     r14d, ecx
0x180010c02  mov     rbp, rdx
0x180010c05  mov     [rsp+88h+var_44], 0
0x180010c0d  mov     edi, 1
0x180010c12  mov     [rsp+88h+arg_10], rbx
0x180010c1a  lea     r15, ?aliasTypes@@3PAPEBGA; ushort const * near * aliasTypes
0x180010c21  cmp     edi, 9
0x180010c24  jg      short loc_180010CA5
0x180010c26  mov     r9, [r15+r14*8]
0x180010c2a  lea     r8, aSD_0; "%s%d"
0x180010c31  mov     edx, 7; unsigned __int64
0x180010c36  mov     dword ptr [rsp+88h+pdwType], edi; unsigned int
0x180010c3a  lea     rcx, [rsp+88h+Value]; unsigned __int16 *
0x180010c3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010c44  mov     ebx, eax
0x180010c46  test    eax, eax
0x180010c48  jns     short loc_180010CA9
0x180010c4a  mov     rcx, [rsp+88h]; this
0x180010c52  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180010c59  mov     r9d, eax; char *
0x180010c5c  mov     edx, 30h ; '0'; void *
0x180010c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c66  mov     rcx, [rsp+88h]; this
0x180010c6e  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180010c75  mov     r9d, ebx; char *
0x180010c78  mov     edx, 45h ; 'E'; void *
0x180010c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c82  mov     eax, ebx
0x180010c84  mov     rbx, [rsp+88h+arg_10]
0x180010c8c  mov     rcx, [rsp+88h+var_30]
0x180010c91  xor     rcx, rsp; StackCookie
0x180010c94  call    __security_check_cookie
0x180010c99  add     rsp, 60h
0x180010c9d  pop     r15
0x180010c9f  pop     r14
0x180010ca1  pop     rdi
0x180010ca2  pop     rsi
0x180010ca3  pop     rbp
0x180010ca4  retn
0x180010ca5  xor     eax, eax
0x180010ca7  jmp     short loc_180010C84
0x180010ca9  movsxd  rax, edi
0x180010cac  imul    rbx, rax, 20Ah
0x180010cb3  add     rbx, rbp
0x180010cb6  test    sil, sil
0x180010cb9  jz      short loc_180010CC7
0x180010cbb  cmp     byte ptr [rbx], 0
0x180010cbe  jnz     short loc_180010D14
0x180010cc0  inc     edi
0x180010cc2  jmp     loc_180010C21
0x180010cc7  lea     rcx, [rsp+88h+var_48]
0x180010ccc  mov     [rsp+88h+var_48], 104h
0x180010cd4  mov     [rsp+88h+pcbData], rcx; pcbData
0x180010cd9  lea     rax, [rbx+2]
0x180010cdd  mov     [rsp+88h+pvData], rax; pvData
0x180010ce2  lea     r8, [rsp+88h+Value]; lpValue
0x180010ce7  lea     rax, [rsp+88h+var_44]
0x180010cec  mov     r9d, 2; dwFlags
0x180010cf2  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180010cf9  mov     [rsp+88h+pdwType], rax; pdwType
0x180010cfe  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180010d05  call    cs:__imp_RegGetValueW
0x180010d0b  test    eax, eax
0x180010d0d  jnz     short loc_180010CC0
0x180010d0f  mov     byte ptr [rbx], 1
0x180010d12  jmp     short loc_180010CC0
0x180010d14  cmp     byte ptr [rbx+1], 0
0x180010d18  jnz     short loc_180010CC0
0x180010d1a  lea     r8, [rsp+88h+Value]; lpValueName
0x180010d1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010d26  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180010d2d  call    cs:__imp_RegDeleteKeyValueW
0x180010d33  test    eax, eax
0x180010d35  jnz     short loc_180010D5D
0x180010d37  lea     r8, [rsp+88h+Value]; lpValueName
0x180010d3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010d43  lea     rdx, ?driver32WowPath@@3QBGB; "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x180010d4a  call    cs:__imp_RegDeleteKeyValueW
0x180010d50  test    eax, eax
0x180010d52  jnz     short loc_180010D7E
0x180010d54  mov     [rbx], al
0x180010d56  inc     edi
0x180010d58  jmp     loc_180010C21
0x180010d5d  mov     rcx, [rsp+88h]; this
0x180010d65  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180010d6c  mov     r9d, eax; char *
0x180010d6f  mov     edx, 4Eh ; 'N'; void *
0x180010d74  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010d79  jmp     loc_180010C84
0x180010d7e  mov     rcx, [rsp+88h]; this
0x180010d86  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180010d8d  mov     r9d, eax; char *
0x180010d90  mov     edx, 50h ; 'P'; void *
0x180010d95  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010d9a  jmp     loc_180010C84
```
