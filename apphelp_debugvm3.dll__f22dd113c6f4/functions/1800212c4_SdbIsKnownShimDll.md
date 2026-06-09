# SdbIsKnownShimDll

- ea: `0x1800212c4`
- end: `0x1800213e3`
- name: `SdbIsKnownShimDll`
- size: `287`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180021000`
- `0x1800363b8`

## callees

- `0x18000f114`
- `0x1800212c4`
- `0x180039a5a`
- `0x180039a66`
- `0x18004842c`
- `0x18004bde0`
- `0x1800591b0`

## import_xrefs

- `ntdll!wcscpy_s` at `0x1800213ad`
- `ntdll!wcscpy_s` at `0x1800213ad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800213b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800213b8`

## string_xrefs

- `0x1800212f7`: `AcPlugin_`
- `0x180021366`: `Can't get shim plugin directory [%x]`
- `0x180021377`: `SdbIsKnownShimDll`

## pseudocode

```c
__int64 __fastcall SdbIsKnownShimDll(wchar_t *String1)
{
  unsigned int v2; // ebx
  unsigned int i; // ebx
  int ShimPluginDirectory; // eax
  __int64 v6; // rax
  DWORD FileAttributesW; // eax
  WCHAR FileName[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( String1 && *String1 )
  {
    for ( i = 0; i < 0x11; ++i )
    {
      if ( !wcsicmp_0(String1, off_18005BD20[i]) )
        return 1;
    }
  }
  v2 = 0;
  if ( !wcsnicmp_0(String1, L"AcPlugin_", 9u) )
  {
    ShimPluginDirectory = SdbpGetShimPluginDirectory(FileName);
    if ( ShimPluginDirectory >= 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( FileName[v6] );
      wcscpy_s(&FileName[v6], 260 - v6, String1);
      FileAttributesW = GetFileAttributesW(FileName);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 && (int)SdbpVerifySignature((__int64)FileName) >= 0 )
        return 1;
    }
    else
    {
      AslLogCallPrintf(1, "SdbIsKnownShimDll", 2195, "Can't get shim plugin directory [%x]", ShimPluginDirectory);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800212c4  push    rbx
0x1800212c6  push    rbp
0x1800212c7  push    rsi
0x1800212c8  push    rdi
0x1800212c9  sub     rsp, 258h
0x1800212d0  mov     rax, cs:__security_cookie
0x1800212d7  xor     rax, rsp
0x1800212da  mov     [rsp+278h+var_38], rax
0x1800212e2  xor     esi, esi
0x1800212e4  mov     rdi, rcx
0x1800212e7  mov     ebp, 1
0x1800212ec  test    rcx, rcx
0x1800212ef  jnz     short loc_18002132A
0x1800212f1  mov     r8d, 9; MaxCount
0x1800212f7  lea     rdx, aAcplugin; "AcPlugin_"
0x1800212fe  mov     rcx, rdi; String1
0x180021301  mov     ebx, esi
0x180021303  call    _wcsnicmp_0
0x180021308  test    eax, eax
0x18002130a  jz      short loc_180021358
0x18002130c  mov     eax, ebx
0x18002130e  mov     rcx, [rsp+278h+var_38]
0x180021316  xor     rcx, rsp; StackCookie
0x180021319  call    __security_check_cookie
0x18002131e  add     rsp, 258h
0x180021325  pop     rdi
0x180021326  pop     rsi
0x180021327  pop     rbp
0x180021328  pop     rbx
0x180021329  retn
0x18002132a  cmp     [rcx], si
0x18002132d  jz      short loc_1800212F1
0x18002132f  mov     ebx, esi
0x180021331  cmp     ebx, 11h
0x180021334  jnb     short loc_1800212F1
0x180021336  lea     rax, off_18005BD20; "AcGenral.dll"
0x18002133d  movsxd  rdx, ebx
0x180021340  mov     rcx, rdi; String1
0x180021343  mov     rdx, [rax+rdx*8]; String2
0x180021347  call    _wcsicmp_0
0x18002134c  test    eax, eax
0x18002134e  jz      short loc_180021354
0x180021350  add     ebx, ebp
0x180021352  jmp     short loc_180021331
0x180021354  mov     ebx, ebp
0x180021356  jmp     short loc_18002130C
0x180021358  lea     rcx, [rsp+278h+FileName]; SourceString
0x18002135d  call    SdbpGetShimPluginDirectory
0x180021362  test    eax, eax
0x180021364  jns     short loc_180021387
0x180021366  lea     r9, aCanTGetShimPlu; "Can't get shim plugin directory [%x]"
0x18002136d  mov     [rsp+278h+var_258], eax
0x180021371  mov     r8d, 893h
0x180021377  lea     rdx, aSdbisknownshim; "SdbIsKnownShimDll"
0x18002137e  mov     ecx, ebp
0x180021380  call    AslLogCallPrintf
0x180021385  jmp     short loc_18002130C
0x180021387  lea     rcx, [rsp+278h+FileName]
0x18002138c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021390  inc     rax
0x180021393  cmp     [rcx+rax*2], si
0x180021397  jnz     short loc_180021390
0x180021399  mov     edx, 104h
0x18002139e  lea     rcx, [rsp+278h+FileName]
0x1800213a3  sub     rdx, rax; SizeInWords
0x1800213a6  lea     rcx, [rcx+rax*2]; Destination
0x1800213aa  mov     r8, rdi; Source
0x1800213ad  call    cs:__imp_wcscpy_s
0x1800213b3  lea     rcx, [rsp+278h+FileName]; lpFileName
0x1800213b8  call    cs:__imp_GetFileAttributesW
0x1800213be  cmp     eax, 0FFFFFFFFh
0x1800213c1  jz      loc_18002130C
0x1800213c7  test    al, 10h
0x1800213c9  jnz     loc_18002130C
0x1800213cf  lea     rcx, [rsp+278h+FileName]
0x1800213d4  call    SdbpVerifySignature
0x1800213d9  test    eax, eax
0x1800213db  cmovns  ebx, ebp
0x1800213de  jmp     loc_18002130C
```
