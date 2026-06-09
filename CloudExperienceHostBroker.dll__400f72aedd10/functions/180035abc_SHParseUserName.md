# SHParseUserName

- ea: `0x180035abc`
- end: `0x180035b9a`
- name: `SHParseUserName`
- size: `222`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027510`
- `0x180035f7c`

## callees

- `0x180009f30`
- `0x18000ec4c`
- `0x18003595c`
- `0x180035abc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035b4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035b4e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180035af5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180035af5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180035b61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180035b61`

## pseudocode

```c
__int64 __fastcall SHParseUserName(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, unsigned __int16 *a4)
{
  int v8; // ebx
  PWSTR v9; // rax
  __int64 v10; // r11
  DWORD nSize; // [rsp+20h] [rbp-58h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-50h] BYREF

  v8 = -2147467259;
  if ( a1 )
  {
    v9 = StrChrW(a1, 0x5Cu);
    if ( v9 )
    {
      v8 = StringCchCopyW(a4, 0x101u, v9 + 1);
      if ( v8 >= 0 )
      {
        v8 = StringCchCopyNW(a2, a3, a1, (v10 - (__int64)a1) >> 1);
        if ( v8 >= 0 )
        {
          nSize = 16;
          if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) && !lstrcmpiW(Buffer, a2) )
            goto LABEL_9;
        }
      }
    }
    else
    {
      v8 = StringCchCopyW(a4, 0x101u, a1);
      if ( v8 >= 0 )
LABEL_9:
        *a2 = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180035abc  push    rbx
0x180035abe  push    rbp
0x180035abf  push    rsi
0x180035ac0  push    rdi
0x180035ac1  push    r14
0x180035ac3  sub     rsp, 50h
0x180035ac7  mov     rax, cs:__security_cookie
0x180035ace  xor     rax, rsp
0x180035ad1  mov     [rsp+78h+var_30], rax
0x180035ad6  mov     r14d, r8d
0x180035ad9  mov     rbp, r9
0x180035adc  mov     rdi, rdx
0x180035adf  mov     rsi, rcx
0x180035ae2  mov     ebx, 80004005h
0x180035ae7  test    rcx, rcx
0x180035aea  jz      loc_180035B80
0x180035af0  mov     edx, 5Ch ; '\'; wMatch
0x180035af5  call    cs:__imp_StrChrW
0x180035afb  mov     edx, 101h; unsigned __int64
0x180035b00  mov     rcx, rbp; unsigned __int16 *
0x180035b03  mov     r11, rax
0x180035b06  test    rax, rax
0x180035b09  jz      short loc_180035B6D
0x180035b0b  lea     r8, [rax+2]; unsigned __int16 *
0x180035b0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035b14  mov     ebx, eax
0x180035b16  test    eax, eax
0x180035b18  js      short loc_180035B80
0x180035b1a  sub     r11, rsi
0x180035b1d  mov     edx, r14d; unsigned __int64
0x180035b20  sar     r11, 1
0x180035b23  mov     r8, rsi; unsigned __int16 *
0x180035b26  mov     r9, r11; unsigned __int64
0x180035b29  mov     rcx, rdi; unsigned __int16 *
0x180035b2c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180035b31  mov     ebx, eax
0x180035b33  test    eax, eax
0x180035b35  js      short loc_180035B80
0x180035b37  lea     r8, [rsp+78h+nSize]; nSize
0x180035b3c  mov     [rsp+78h+nSize], 10h
0x180035b44  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180035b49  mov     ecx, 4; NameType
0x180035b4e  call    cs:__imp_GetComputerNameExW
0x180035b54  cmp     eax, 1
0x180035b57  jnz     short loc_180035B80
0x180035b59  mov     rdx, rdi; lpString2
0x180035b5c  lea     rcx, [rsp+78h+Buffer]; lpString1
0x180035b61  call    cs:__imp_lstrcmpiW
0x180035b67  test    eax, eax
0x180035b69  jnz     short loc_180035B80
0x180035b6b  jmp     short loc_180035B7B
0x180035b6d  mov     r8, rsi; unsigned __int16 *
0x180035b70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035b75  mov     ebx, eax
0x180035b77  test    eax, eax
0x180035b79  js      short loc_180035B80
0x180035b7b  xor     eax, eax
0x180035b7d  mov     [rdi], ax
0x180035b80  mov     eax, ebx
0x180035b82  mov     rcx, [rsp+78h+var_30]
0x180035b87  xor     rcx, rsp; StackCookie
0x180035b8a  call    __security_check_cookie
0x180035b8f  add     rsp, 50h
0x180035b93  pop     r14
0x180035b95  pop     rdi
0x180035b96  pop     rsi
0x180035b97  pop     rbp
0x180035b98  pop     rbx
0x180035b99  retn
```
