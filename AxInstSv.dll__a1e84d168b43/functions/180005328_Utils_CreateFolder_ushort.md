# Utils::CreateFolder(ushort *)

- ea: `0x180005328`
- end: `0x1800053dc`
- name: `?CreateFolder@Utils@@SAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005328`
- `0x180006aec`

## callees

- `0x180001720`
- `0x180005328`
- `0x180005b30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000537e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000537e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000539c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000539c`

## pseudocode

```c
signed int __fastcall Utils::CreateFolder(LPCWSTR lpPathName)
{
  int v2; // edx
  signed int result; // eax
  wchar_t Str[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = lpPathName[1] - 58;
  if ( lpPathName[1] == 58 )
    v2 = lpPathName[2];
  if ( !v2 )
    return 0;
  result = StringCchCopyW(Str, 0x104u, lpPathName);
  if ( result >= 0 )
  {
    *wcsrchr(Str, 0x5Cu) = 0;
    result = Utils::CreateFolder(Str);
    if ( result >= 0 )
    {
      if ( !CreateDirectoryW(lpPathName, 0) )
      {
        result = GetLastError();
        if ( result != 183 )
        {
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
          return result;
        }
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005328  push    rbx
0x18000532a  sub     rsp, 240h
0x180005331  mov     rax, cs:__security_cookie
0x180005338  xor     rax, rsp
0x18000533b  mov     [rsp+248h+var_18], rax
0x180005343  movzx   edx, word ptr [rcx+2]
0x180005347  mov     rbx, rcx
0x18000534a  sub     edx, 3Ah ; ':'
0x18000534d  jnz     short loc_18000535A
0x18000534f  movzx   edx, word ptr [rcx+4]
0x180005353  xor     eax, eax
0x180005355  movzx   ecx, ax
0x180005358  sub     edx, ecx
0x18000535a  test    edx, edx
0x18000535c  jz      short loc_1800053C1
0x18000535e  mov     r8, rbx; unsigned __int16 *
0x180005361  lea     rcx, [rsp+248h+Str]; unsigned __int16 *
0x180005366  mov     edx, 104h; unsigned __int64
0x18000536b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005370  test    eax, eax
0x180005372  js      short loc_1800053C3
0x180005374  mov     edx, 5Ch ; '\'; Ch
0x180005379  lea     rcx, [rsp+248h+Str]; Str
0x18000537e  call    cs:__imp_wcsrchr
0x180005384  xor     edx, edx
0x180005386  lea     rcx, [rsp+248h+Str]; lpPathName
0x18000538b  mov     [rax], dx
0x18000538e  call    ?CreateFolder@Utils@@SAJPEAG@Z; Utils::CreateFolder(ushort *)
0x180005393  test    eax, eax
0x180005395  js      short loc_1800053C3
0x180005397  xor     edx, edx; lpSecurityAttributes
0x180005399  mov     rcx, rbx; lpPathName
0x18000539c  call    cs:__imp_CreateDirectoryW
0x1800053a2  test    eax, eax
0x1800053a4  jnz     short loc_1800053C1
0x1800053a6  call    cs:__imp_GetLastError
0x1800053ac  cmp     eax, 0B7h
0x1800053b1  jz      short loc_1800053C1
0x1800053b3  test    eax, eax
0x1800053b5  jle     short loc_1800053C3
0x1800053b7  movzx   eax, ax
0x1800053ba  or      eax, 80070000h
0x1800053bf  jmp     short loc_1800053C3
0x1800053c1  xor     eax, eax
0x1800053c3  mov     rcx, [rsp+248h+var_18]
0x1800053cb  xor     rcx, rsp; StackCookie
0x1800053ce  call    __security_check_cookie
0x1800053d3  add     rsp, 240h
0x1800053da  pop     rbx
0x1800053db  retn
```
