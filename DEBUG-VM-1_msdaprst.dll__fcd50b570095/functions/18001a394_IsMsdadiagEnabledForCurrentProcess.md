# IsMsdadiagEnabledForCurrentProcess

- ea: `0x18001a394`
- end: `0x18001a544`
- name: `IsMsdadiagEnabledForCurrentProcess`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018cb0`

## callees

- `0x180001838`
- `0x180018cfc`
- `0x1800190dc`
- `0x18001a394`
- `0x18002e060`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001a422`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a422`
- `ADVAPI32!RegCloseKey` at `0x18001a510`
- `ADVAPI32!RegCloseKey` at `0x18001a510`

## string_xrefs

- `0x18001a4f2`: `:Path`

## pseudocode

```c
__int64 IsMsdadiagEnabledForCurrentProcess()
{
  unsigned int v0; // ebx
  __int64 v1; // rax
  unsigned __int64 v2; // rcx
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v7; // [rsp+40h] [rbp-C0h]
  __int64 v8; // [rsp+48h] [rbp-B8h]
  WCHAR SubKey[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[280]; // [rsp+A0h] [rbp-60h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\BidInterfac\\Loader");
  v0 = 0;
  hKey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    v8 = 0;
    v7 = 0;
    if ( (unsigned int)BuildApplicationPid(Filename) )
    {
      if ( (unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
        goto LABEL_14;
      if ( (unsigned __int64)(2 * v7) >= 0x224 )
        goto LABEL_13;
      Filename[v7] = 0;
      if ( (unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
      {
LABEL_14:
        v0 = v5;
        goto LABEL_10;
      }
      v1 = v8;
      if ( v8 )
      {
        Filename[v8] = 42;
        v2 = 2 * v1 + 2;
        if ( v2 < 0x224 )
        {
          *(WCHAR *)((char *)Filename + v2) = 0;
          if ( !(unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
            goto LABEL_9;
          goto LABEL_14;
        }
LABEL_13:
        _report_rangecheckfailure();
      }
    }
LABEL_9:
    v3 = IsMsdadiagEnabledForCurrentProcessInternal(hKey, L":Path", &v5);
    v0 = v3 != 0 ? v5 : 0;
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18001a394  mov     [rsp-8+arg_0], rbx
0x18001a399  push    rbp
0x18001a39a  lea     rbp, [rsp-1E0h]
0x18001a3a2  sub     rsp, 2E0h
0x18001a3a9  mov     rax, cs:__security_cookie
0x18001a3b0  xor     rax, rsp
0x18001a3b3  mov     [rbp+1E0h+var_10], rax
0x18001a3ba  movaps  xmm0, xmmword ptr cs:SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x18001a3c1  lea     rax, [rsp+2E0h+hKey]
0x18001a3c6  movaps  xmm1, xmmword ptr cs:SubKey+10h; "\\Microsoft\\BidInterface\\Loader"
0x18001a3cd  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18001a3d2  movaps  xmmword ptr [rsp+2E0h+SubKey], xmm0
0x18001a3d7  xor     ebx, ebx
0x18001a3d9  movaps  xmm0, xmmword ptr cs:SubKey+20h; "ft\\BidInterface\\Loader"
0x18001a3e0  mov     r9d, 20019h; samDesired
0x18001a3e6  movaps  [rsp+2E0h+var_270], xmm0
0x18001a3eb  xor     r8d, r8d; ulOptions
0x18001a3ee  movups  xmm0, xmmword ptr cs:SubKey+3Eh; "\\Loader"
0x18001a3f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a3fc  mov     [rsp+2E0h+hKey], 0
0x18001a405  movaps  [rsp+2E0h+var_280], xmm1
0x18001a40a  movaps  xmm1, xmmword ptr cs:SubKey+30h; "terface\\Loader"
0x18001a411  movaps  [rbp+1E0h+var_260], xmm1
0x18001a415  movups  [rbp+1E0h+var_260+0Eh], xmm0
0x18001a419  mov     [rsp+2E0h+var_2B0], ebx
0x18001a41d  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001a422  call    cs:__imp_RegOpenKeyExW
0x18001a428  test    eax, eax
0x18001a42a  jnz     loc_18001A506
0x18001a430  lea     r9, [rsp+2E0h+var_2A0]
0x18001a435  mov     [rsp+2E0h+var_298], rbx
0x18001a43a  lea     r8, [rsp+2E0h+var_298]
0x18001a43f  mov     [rsp+2E0h+var_2A0], rbx
0x18001a444  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x18001a448  call    BuildApplicationPid
0x18001a44d  test    eax, eax
0x18001a44f  jz      loc_18001A4E8
0x18001a455  mov     rcx, [rsp+2E0h+hKey]
0x18001a45a  lea     r8, [rsp+2E0h+var_2B0]
0x18001a45f  lea     rdx, [rbp+1E0h+Filename]
0x18001a463  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001a468  test    eax, eax
0x18001a46a  jnz     loc_18001A53E
0x18001a470  mov     rax, [rsp+2E0h+var_2A0]
0x18001a475  mov     ebx, 224h
0x18001a47a  lea     rcx, [rax+rax]
0x18001a47e  cmp     rcx, rbx
0x18001a481  jnb     loc_18001A538
0x18001a487  xor     eax, eax
0x18001a489  lea     r8, [rsp+2E0h+var_2B0]
0x18001a48e  mov     [rbp+rcx+1E0h+Filename], ax
0x18001a493  lea     rdx, [rbp+1E0h+Filename]
0x18001a497  mov     rcx, [rsp+2E0h+hKey]
0x18001a49c  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001a4a1  test    eax, eax
0x18001a4a3  jnz     loc_18001A53E
0x18001a4a9  mov     rax, [rsp+2E0h+var_298]
0x18001a4ae  test    rax, rax
0x18001a4b1  jz      short loc_18001A4E8
0x18001a4b3  mov     ecx, 2Ah ; '*'
0x18001a4b8  mov     [rbp+rax*2+1E0h+Filename], cx
0x18001a4bd  lea     rcx, ds:2[rax*2]
0x18001a4c5  cmp     rcx, rbx
0x18001a4c8  jnb     short loc_18001A538
0x18001a4ca  xor     eax, eax
0x18001a4cc  lea     r8, [rsp+2E0h+var_2B0]
0x18001a4d1  mov     [rbp+rcx+1E0h+Filename], ax
0x18001a4d6  lea     rdx, [rbp+1E0h+Filename]
0x18001a4da  mov     rcx, [rsp+2E0h+hKey]
0x18001a4df  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001a4e4  test    eax, eax
0x18001a4e6  jnz     short loc_18001A53E
0x18001a4e8  mov     rcx, [rsp+2E0h+hKey]
0x18001a4ed  lea     r8, [rsp+2E0h+var_2B0]
0x18001a4f2  lea     rdx, aPath; ":Path"
0x18001a4f9  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001a4fe  neg     eax
0x18001a500  sbb     ebx, ebx
0x18001a502  and     ebx, [rsp+2E0h+var_2B0]
0x18001a506  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001a50b  test    rcx, rcx
0x18001a50e  jz      short loc_18001A516
0x18001a510  call    cs:__imp_RegCloseKey
0x18001a516  mov     eax, ebx
0x18001a518  mov     rcx, [rbp+1E0h+var_10]
0x18001a51f  xor     rcx, rsp; StackCookie
0x18001a522  call    __security_check_cookie
0x18001a527  mov     rbx, [rsp+2E0h+arg_0]
0x18001a52f  add     rsp, 2E0h
0x18001a536  pop     rbp
0x18001a537  retn
0x18001a538  call    __report_rangecheckfailure
0x18001a53e  mov     ebx, [rsp+2E0h+var_2B0]
0x18001a542  jmp     short loc_18001A506
```
