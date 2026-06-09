# FileUtils::GetTroubleshootersRootDirectoryPath(ushort * *)

- ea: `0x18002c154`
- end: `0x18002c24f`
- name: `?GetTroubleshootersRootDirectoryPath@FileUtils@@SAJPEAPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002b7a4`
- `0x18002b9c0`
- `0x18002be98`

## callees

- `0x18000a6e0`
- `0x18001206c`
- `0x18001208c`
- `0x18001e164`
- `0x18002407c`
- `0x18002c154`

## import_xrefs

- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18002c180`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18002c180`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall FileUtils::GetTroubleshootersRootDirectoryPath(unsigned __int16 **a1)
{
  const char *v2; // r9
  int v4; // eax
  unsigned int v5; // ebx
  int v6[2]; // [rsp+20h] [rbp-248h] BYREF
  __int64 v7; // [rsp+28h] [rbp-240h]
  __int64 v8; // [rsp+30h] [rbp-238h]
  _BYTE v9[528]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !(unsigned int)GetTempPath2W(260, v9) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x90,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
             v2);
  *(_QWORD *)v6 = 0;
  v7 = 0;
  v8 = 0;
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v6,
         L"%sTroubleshooters",
         v9);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    *a1 = *(unsigned __int16 **)v6;
    *(_QWORD *)v6 = 0;
    v8 = 0;
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
      (const char *)(unsigned int)v4,
      v6[0]);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v6);
  return v5;
}

```

## disassembly

```asm
0x18002c154  mov     [rsp+arg_8], rbx
0x18002c159  push    rdi
0x18002c15a  sub     rsp, 260h
0x18002c161  mov     rax, cs:__security_cookie
0x18002c168  xor     rax, rsp
0x18002c16b  mov     [rsp+268h+var_18], rax
0x18002c173  mov     rdi, rcx
0x18002c176  lea     rdx, [rsp+268h+var_228]
0x18002c17b  mov     ecx, 104h
0x18002c180  call    cs:__imp_GetTempPath2W
0x18002c186  test    eax, eax
0x18002c188  jnz     short loc_18002C1A8
0x18002c18a  mov     rcx, [rsp+268h]; this
0x18002c192  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002c199  mov     edx, 90h; void *
0x18002c19e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c1a3  jmp     loc_18002C22E
0x18002c1a8  lea     r8, [rsp+268h+var_228]
0x18002c1ad  mov     qword ptr [rsp+268h+var_248], 0; int
0x18002c1b6  lea     rdx, aStroubleshoote; "%sTroubleshooters"
0x18002c1bd  mov     [rsp+268h+var_240], 0
0x18002c1c6  lea     rcx, [rsp+268h+var_248]
0x18002c1cb  mov     [rsp+268h+var_238], 0
0x18002c1d4  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002c1d9  mov     ebx, eax
0x18002c1db  test    eax, eax
0x18002c1dd  jns     short loc_18002C1FD
0x18002c1df  mov     rcx, [rsp+268h]; this
0x18002c1e7  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002c1ee  mov     r9d, eax; char *
0x18002c1f1  mov     edx, 93h; void *
0x18002c1f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c1fb  jmp     short loc_18002C222
0x18002c1fd  mov     rax, qword ptr [rsp+268h+var_248]
0x18002c202  xor     ebx, ebx
0x18002c204  mov     [rdi], rax
0x18002c207  mov     qword ptr [rsp+268h+var_248], 0
0x18002c210  mov     [rsp+268h+var_238], 0
0x18002c219  mov     [rsp+268h+var_240], 0
0x18002c222  lea     rcx, [rsp+268h+var_248]
0x18002c227  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002c22c  mov     eax, ebx
0x18002c22e  mov     rcx, [rsp+268h+var_18]
0x18002c236  xor     rcx, rsp; StackCookie
0x18002c239  call    __security_check_cookie
0x18002c23e  mov     rbx, [rsp+268h+arg_8]
0x18002c246  add     rsp, 260h
0x18002c24d  pop     rdi
0x18002c24e  retn
```
