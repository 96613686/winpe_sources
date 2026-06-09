# GetWin32AppId

- ea: `0x180040ae4`
- end: `0x180040e64`
- name: `GetWin32AppId`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800409a8`

## callees

- `0x18001358c`
- `0x180040ae4`
- `0x180040e6c`
- `0x1800e55cc`
- `0x1800f6f10`
- `0x1800f7a38`
- `0x1800f8e54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d65`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040da7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040dca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040df0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040e4d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040e56`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d65`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040d83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040da7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040dca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040df0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040e4d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040e56`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180040b21`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180040b6f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180040b21`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180040b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040b33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040b33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040cc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040cc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e44`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180040b5f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180040b5f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180040b8c`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180040b8c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180040bb0`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180040bb0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180040b45`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180040b45`

## string_xrefs

- `0x180040d42`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040d91`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040db3`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040dd9`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040e2d`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040e17`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall GetWin32AppId(unsigned __int16 **a1)
{
  WCHAR *v2; // rsi
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  void *v5; // rdi
  DWORD FileVersionInfoSizeW; // eax
  DWORD v7; // r14d
  void *v8; // rax
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  unsigned int v12; // r14d
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  int i; // ecx
  unsigned __int64 v18; // r15
  __int64 v19; // r14
  int *v20; // r12
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rbx
  int v23; // eax
  unsigned int v24; // r14d
  unsigned int LastError; // ebx
  int v27; // [rsp+20h] [rbp-79h]
  DWORD dwSize; // [rsp+40h] [rbp-59h] BYREF
  unsigned int puLen; // [rsp+44h] [rbp-55h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v31[4]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 v32[8]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v33; // [rsp+78h] [rbp-21h]
  __int128 v34; // [rsp+88h] [rbp-11h]
  __int16 v35; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a1 = 0;
  dwSize = 0x7FFF;
  v2 = (WCHAR *)malloc(0xFFFEu);
  if ( !v2 )
    return 2147942414LL;
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, v2, &dwSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA7,
                  (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
                  v4);
    goto LABEL_27;
  }
  lpBuffer = 0;
  v5 = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(v2, 0);
  v7 = FileVersionInfoSizeW;
  if ( FileVersionInfoSizeW )
  {
    v8 = malloc(FileVersionInfoSizeW);
    v5 = v8;
    if ( !v8 )
    {
      free(0);
      LastError = -2147024882;
      goto LABEL_27;
    }
    if ( GetFileVersionInfoW(v2, 0, v7, v8) )
    {
      puLen = 0;
      if ( VerQueryValueW(v5, L"\\", &lpBuffer, &puLen) )
        goto LABEL_7;
      free(v5);
      LastError = -2147467259;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC0,
                    (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
                    v9);
      free(v5);
    }
LABEL_27:
    free(v2);
    return LastError;
  }
LABEL_7:
  v35 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( !lpBuffer )
  {
    v31[0] = 3014704;
    v31[1] = 3014704;
    v31[2] = 3014704;
    v31[3] = 48;
    o_wcsncpy_s_0(v32, 25, v31);
    goto LABEL_9;
  }
  v27 = *((unsigned __int16 *)lpBuffer + 4);
  v10 = StringCchPrintfW(v32, 0x19u, L"%hu.%hu.%hu.%hu", *((unsigned __int16 *)lpBuffer + 5));
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)(unsigned int)v10,
      v27);
    free(v5);
    LastError = v12;
    goto LABEL_27;
  }
LABEL_9:
  v13 = 0x7FFF;
  v14 = v2;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = (0x7FFF - v13) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
  if ( v13 )
  {
    v16 = 0;
    for ( i = v15 - 1; i >= 0; --i )
    {
      if ( v2[i] == 92 )
      {
        v16 = i + 1;
        break;
      }
    }
    v18 = (int)v15 - v16 + 27;
    v19 = (int)v15 - v16 + 26;
    if ( (int)v15 - v16 == -27 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v20 = (int *)&v2[v16];
  }
  else
  {
    v18 = 27;
    v20 = &dword_1801B7F9C;
    v19 = 26;
  }
  v21 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19 + 2);
  v22 = v21;
  if ( !v21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)0x8007000ELL,
      v27);
    free(v5);
    free(v2);
    return 2147942414LL;
  }
  *v21 = 0;
  v21[v19] = 0;
  v23 = StringCchPrintfW(v21, v18, aS_0, v20);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)(unsigned int)v23,
      (int)v32);
    CoTaskMemFree(v22);
    free(v5);
    free(v2);
    return v24;
  }
  else
  {
    *a1 = v22;
    free(v5);
    free(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x180040ae4  push    rbp
0x180040ae6  push    rbx
0x180040ae7  push    rsi
0x180040ae8  push    rdi
0x180040ae9  push    r12
0x180040aeb  push    r13
0x180040aed  push    r14
0x180040aef  push    r15
0x180040af1  lea     rbp, [rsp-1Fh]
0x180040af6  sub     rsp, 0B8h
0x180040afd  mov     rax, cs:__security_cookie
0x180040b04  xor     rax, rsp
0x180040b07  mov     [rbp+57h+var_50], rax
0x180040b0b  mov     r13, rcx
0x180040b0e  xor     r15d, r15d
0x180040b11  mov     [rcx], r15
0x180040b14  mov     ebx, 7FFFh
0x180040b19  mov     ecx, 0FFFEh; Size
0x180040b1e  mov     [rbp+57h+dwSize], ebx
0x180040b21  call    cs:__imp_malloc
0x180040b27  mov     rsi, rax
0x180040b2a  test    rax, rax
0x180040b2d  jz      loc_180040D6B
0x180040b33  call    cs:__imp_GetCurrentProcess
0x180040b39  lea     r9, [rbp+57h+dwSize]; lpdwSize
0x180040b3d  mov     r8, rsi; lpExeName
0x180040b40  mov     rcx, rax; hProcess
0x180040b43  xor     edx, edx; dwFlags
0x180040b45  call    cs:__imp_QueryFullProcessImageNameW
0x180040b4b  test    eax, eax
0x180040b4d  jz      loc_180040DD5
0x180040b53  xor     edx, edx; lpdwHandle
0x180040b55  mov     [rbp+57h+lpBuffer], r15
0x180040b59  mov     rcx, rsi; lptstrFilename
0x180040b5c  mov     edi, r15d
0x180040b5f  call    cs:__imp_GetFileVersionInfoSizeW
0x180040b65  mov     r14d, eax
0x180040b68  test    eax, eax
0x180040b6a  jz      short loc_180040BBE
0x180040b6c  mov     ecx, r14d; Size
0x180040b6f  call    cs:__imp_malloc
0x180040b75  mov     rdi, rax
0x180040b78  test    rax, rax
0x180040b7b  jz      loc_180040DEE
0x180040b81  mov     r9, rax; lpData
0x180040b84  mov     r8d, r14d; dwLen
0x180040b87  xor     edx, edx; dwHandle
0x180040b89  mov     rcx, rsi; lptstrFilename
0x180040b8c  call    cs:__imp_GetFileVersionInfoW
0x180040b92  test    eax, eax
0x180040b94  jz      loc_180040D8D
0x180040b9a  lea     r9, [rbp+57h+puLen]; puLen
0x180040b9e  mov     [rbp+57h+puLen], r15d
0x180040ba2  lea     r8, [rbp+57h+lpBuffer]; lplpBuffer
0x180040ba6  mov     rcx, rdi; pBlock
0x180040ba9  lea     rdx, SubBlock; "\\"
0x180040bb0  call    cs:__imp_VerQueryValueW
0x180040bb6  test    eax, eax
0x180040bb8  jz      loc_180040D72
0x180040bbe  mov     r8, [rbp+57h+lpBuffer]
0x180040bc2  xorps   xmm0, xmm0
0x180040bc5  xor     eax, eax
0x180040bc7  mov     [rbp+57h+var_58], ax
0x180040bcb  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x180040bcf  movups  [rbp+57h+var_78], xmm0
0x180040bd3  movups  [rbp+57h+var_68], xmm0
0x180040bd7  test    r8, r8
0x180040bda  jz      loc_180040C66
0x180040be0  movzx   ecx, word ptr [r8+0Eh]
0x180040be5  movzx   edx, word ptr [r8+8]
0x180040bea  movzx   eax, word ptr [r8+0Ch]
0x180040bef  movzx   r9d, word ptr [r8+0Ah]
0x180040bf4  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x180040bfb  mov     [rsp+0F0h+var_C0], eax
0x180040bff  mov     [rsp+0F0h+var_C8], ecx
0x180040c03  lea     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180040c07  mov     [rsp+0F0h+var_D0], edx; int
0x180040c0b  mov     edx, 19h; unsigned __int64
0x180040c10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040c15  mov     r14d, eax
0x180040c18  test    eax, eax
0x180040c1a  js      loc_180040DAF
0x180040c20  mov     rcx, rbx
0x180040c23  mov     rax, rsi
0x180040c26  cmp     [rax], r15w
0x180040c2a  jz      short loc_180040C36
0x180040c2c  add     rax, 2
0x180040c30  sub     rcx, 1
0x180040c34  jnz     short loc_180040C26
0x180040c36  sub     rbx, rcx
0x180040c39  mov     rax, rcx
0x180040c3c  neg     rax
0x180040c3f  sbb     rdx, rdx
0x180040c42  and     rdx, rbx
0x180040c45  test    rcx, rcx
0x180040c48  jz      loc_180040DFD
0x180040c4e  mov     r8, r15
0x180040c51  lea     ecx, [rdx-1]
0x180040c54  test    ecx, ecx
0x180040c56  js      short loc_180040CA1
0x180040c58  movsxd  rax, ecx
0x180040c5b  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x180040c60  jz      short loc_180040C9B
0x180040c62  dec     ecx
0x180040c64  jmp     short loc_180040C54
0x180040c66  mov     r9d, 7
0x180040c6c  mov     [rbp+57h+var_98], 2E0030h
0x180040c73  lea     r8, [rbp+57h+var_98]
0x180040c77  mov     [rbp+57h+var_94], 2E0030h
0x180040c7e  lea     rcx, [rbp+57h+var_88]
0x180040c82  mov     [rbp+57h+var_90], 2E0030h
0x180040c89  mov     [rbp+57h+var_8C], 30h ; '0'
0x180040c90  lea     edx, [r9+12h]
0x180040c94  call    _o_wcsncpy_s_0
0x180040c99  jmp     short loc_180040C20
0x180040c9b  lea     eax, [rcx+1]
0x180040c9e  movsxd  r8, eax
0x180040ca1  movsxd  r15, edx
0x180040ca4  sub     r15, r8
0x180040ca7  add     r15, 1Bh
0x180040cab  lea     r14, [r15-1]
0x180040caf  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180040cb3  jz      loc_180040E13
0x180040cb9  lea     r12, [rsi+r8*2]
0x180040cbd  lea     rcx, ds:2[r14*2]; cb
0x180040cc5  call    cs:__imp_CoTaskMemAlloc
0x180040ccb  mov     rbx, rax
0x180040cce  test    rax, rax
0x180040cd1  jz      short loc_180040D3E
0x180040cd3  xor     ecx, ecx
0x180040cd5  lea     r8, aS_0; "%s"
0x180040cdc  mov     [rax], cx
0x180040cdf  mov     r9, r12
0x180040ce2  mov     [rax+r14*2], cx
0x180040ce7  mov     rdx, r15; unsigned __int64
0x180040cea  lea     rax, [rbp+57h+var_88]
0x180040cee  mov     rcx, rbx; unsigned __int16 *
0x180040cf1  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180040cf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040cfb  mov     r14d, eax
0x180040cfe  test    eax, eax
0x180040d00  js      loc_180040E29
0x180040d06  mov     rcx, rdi; Block
0x180040d09  mov     [r13+0], rbx
0x180040d0d  call    cs:__imp_free
0x180040d13  mov     rcx, rsi; Block
0x180040d16  call    cs:__imp_free
0x180040d1c  xor     eax, eax
0x180040d1e  mov     rcx, [rbp+57h+var_50]
0x180040d22  xor     rcx, rsp; StackCookie
0x180040d25  call    __security_check_cookie
0x180040d2a  add     rsp, 0B8h
0x180040d31  pop     r15
0x180040d33  pop     r14
0x180040d35  pop     r13
0x180040d37  pop     r12
0x180040d39  pop     rdi
0x180040d3a  pop     rsi
0x180040d3b  pop     rbx
0x180040d3c  pop     rbp
0x180040d3d  retn
0x180040d3e  mov     rcx, [rbp+5Fh]; this
0x180040d42  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040d49  mov     r9d, 8007000Eh; char *
0x180040d4f  mov     edx, 0FBh; void *
0x180040d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d59  mov     rcx, rdi; Block
0x180040d5c  call    cs:__imp_free
0x180040d62  mov     rcx, rsi; Block
0x180040d65  call    cs:__imp_free
0x180040d6b  mov     eax, 8007000Eh
0x180040d70  jmp     short loc_180040D1E
0x180040d72  mov     rcx, rdi; Block
0x180040d75  call    cs:__imp_free
0x180040d7b  mov     ebx, 80004005h
0x180040d80  mov     rcx, rsi; Block
0x180040d83  call    cs:__imp_free
0x180040d89  mov     eax, ebx
0x180040d8b  jmp     short loc_180040D1E
0x180040d8d  mov     rcx, [rbp+5Fh]; this
0x180040d91  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040d98  mov     edx, 0C0h; void *
0x180040d9d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040da2  mov     rcx, rdi; Block
0x180040da5  mov     ebx, eax
0x180040da7  call    cs:__imp_free
0x180040dad  jmp     short loc_180040D80
0x180040daf  mov     rcx, [rbp+5Fh]; this
0x180040db3  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040dba  mov     r9d, r14d; char *
0x180040dbd  mov     edx, 0E0h; void *
0x180040dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040dc7  mov     rcx, rdi; Block
0x180040dca  call    cs:__imp_free
0x180040dd0  mov     ebx, r14d
0x180040dd3  jmp     short loc_180040D80
0x180040dd5  mov     rcx, [rbp+5Fh]; this
0x180040dd9  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040de0  mov     edx, 0A7h; void *
0x180040de5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040dea  mov     ebx, eax
0x180040dec  jmp     short loc_180040D80
0x180040dee  xor     ecx, ecx; Block
0x180040df0  call    cs:__imp_free
0x180040df6  mov     ebx, 8007000Eh
0x180040dfb  jmp     short loc_180040D80
0x180040dfd  mov     r15d, 1Bh
0x180040e03  lea     r12, dword_1801B7F9C
0x180040e0a  lea     r14d, [r15-1]
0x180040e0e  jmp     loc_180040CBD
0x180040e13  mov     rcx, [rbp+5Fh]; this
0x180040e17  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040e1e  mov     edx, 0F89h; void *
0x180040e23  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180040e29  mov     rcx, [rbp+5Fh]; this
0x180040e2d  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040e34  mov     r9d, r14d; char *
0x180040e37  mov     edx, 106h; void *
0x180040e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e41  mov     rcx, rbx; pv
0x180040e44  call    cs:__imp_CoTaskMemFree
0x180040e4a  mov     rcx, rdi; Block
0x180040e4d  call    cs:__imp_free
0x180040e53  mov     rcx, rsi; Block
0x180040e56  call    cs:__imp_free
0x180040e5c  mov     eax, r14d
0x180040e5f  jmp     loc_180040D1E
```
