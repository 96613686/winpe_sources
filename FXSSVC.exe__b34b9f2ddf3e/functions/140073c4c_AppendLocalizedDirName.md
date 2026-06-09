# AppendLocalizedDirName

- ea: `0x140073c4c`
- end: `0x140073fe7`
- name: `AppendLocalizedDirName`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140074258`

## callees

- `0x140002c43`
- `0x140004a30`
- `0x140004b30`
- `0x140004b58`
- `0x140066544`
- `0x140073c4c`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140073d5f`
- `KERNEL32!FreeLibrary` at `0x140073d5f`
- `KERNEL32!GetLastError` at `0x140073d91`
- `KERNEL32!GetLastError` at `0x140073e5a`
- `KERNEL32!GetLastError` at `0x140073eb2`
- `KERNEL32!GetLastError` at `0x140073f34`
- `KERNEL32!GetLastError` at `0x140073d91`
- `KERNEL32!GetLastError` at `0x140073e5a`
- `KERNEL32!GetLastError` at `0x140073eb2`
- `KERNEL32!GetLastError` at `0x140073f34`
- `KERNEL32!LoadLibraryW` at `0x140073e4c`
- `KERNEL32!LoadLibraryW` at `0x140073e4c`
- `KERNEL32!GetProcAddress` at `0x140073ea7`
- `KERNEL32!GetProcAddress` at `0x140073ea7`

## string_xrefs

- `0x140073e45`: `Kernel32.dll`
- `0x140073e9d`: `GetFileMUIPath`

## pseudocode

```c
__int64 __fastcall AppendLocalizedDirName(_WORD *a1, unsigned __int16 *a2)
{
  HMODULE v4; // rsi
  int v5; // ebx
  unsigned __int16 *v6; // r8
  int v7; // eax
  unsigned int v8; // edi
  DWORD v9; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // r8
  __int64 v15; // rax
  _WORD *v16; // rcx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  DWORD v19; // eax
  __int64 result; // rax
  __int64 v21; // [rsp+48h] [rbp-460h]
  _BYTE v22[528]; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v23[264]; // [rsp+260h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
  }
  memset_0(v22, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  HIWORD(v21) = 0;
  if ( !(unsigned int)LonghornOrMore() )
  {
    v4 = 0;
LABEL_7:
    v5 = 0;
    goto LABEL_8;
  }
  if ( !a1 )
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
    }
    v9 = 87;
    goto LABEL_55;
  }
  v13 = 260;
  v14 = v22;
  v5 = 1;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*a1 )
      break;
    *v14++ = *a1++;
    --v15;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  v8 = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
    }
    goto LABEL_55;
  }
  LibraryW = LoadLibraryW(L"Kernel32.dll");
  v4 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    v12 = 38;
LABEL_38:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, LastError);
    goto LABEL_55;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetFileMUIPath");
  if ( !ProcAddress )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v19);
    }
    goto LABEL_16;
  }
  if ( !((unsigned int (__fastcall *)(__int64, _BYTE *, _QWORD))ProcAddress)(16, v22, 0) )
  {
    v9 = GetLastError();
    if ( v9 != 18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
      }
      goto LABEL_16;
    }
    goto LABEL_7;
  }
LABEL_8:
  v6 = (unsigned __int16 *)v22;
  if ( v5 )
    v6 = v23;
  v7 = StringCchCopyW(a2, 0x104u, v6);
  v8 = v7;
  if ( v7 < 0
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, (unsigned int)v7);
  }
  v9 = 0;
  if ( v4 )
  {
LABEL_16:
    if ( FreeLibrary(v4)
      || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    v12 = 42;
    goto LABEL_38;
  }
LABEL_55:
  result = (unsigned __int16)v8;
  if ( (v8 & 0x80000000) == 0 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x140073c4c  mov     [rsp+arg_0], rbx
0x140073c51  mov     [rsp+arg_10], rbp
0x140073c56  push    rsi
0x140073c57  push    rdi
0x140073c58  push    r12
0x140073c5a  push    r13
0x140073c5c  push    r14
0x140073c5e  sub     rsp, 480h
0x140073c65  mov     rax, cs:__security_cookie
0x140073c6c  xor     rax, rsp
0x140073c6f  mov     [rsp+4A8h+var_38], rax
0x140073c77  mov     rbp, rdx
0x140073c7a  mov     rdi, rcx
0x140073c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140073c84  lea     r12, WPP_GLOBAL_Control
0x140073c8b  lea     r13, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x140073c92  cmp     rcx, r12
0x140073c95  jz      short loc_140073CB4
0x140073c97  test    byte ptr [rcx+1Ch], 2
0x140073c9b  jz      short loc_140073CB4
0x140073c9d  cmp     byte ptr [rcx+19h], 5
0x140073ca1  jb      short loc_140073CB4
0x140073ca3  mov     rcx, [rcx+10h]
0x140073ca7  mov     edx, 23h ; '#'
0x140073cac  mov     r8, r13
0x140073caf  call    WPP_SF_
0x140073cb4  mov     ebx, 208h
0x140073cb9  lea     rcx, [rsp+4A8h+var_458]; void *
0x140073cbe  mov     r8d, ebx; Size
0x140073cc1  xor     edx, edx; Val
0x140073cc3  call    memset_0
0x140073cc8  mov     r8d, ebx; Size
0x140073ccb  lea     rcx, [rsp+4A8h+var_248]; void *
0x140073cd3  xor     edx, edx; Val
0x140073cd5  call    memset_0
0x140073cda  mov     ebx, 104h
0x140073cdf  xor     r14d, r14d
0x140073ce2  mov     [rsp+4A8h+var_468], ebx
0x140073ce6  mov     [rsp+4A8h+var_460], r14
0x140073ceb  call    LonghornOrMore
0x140073cf0  test    eax, eax
0x140073cf2  jnz     loc_140073DA8
0x140073cf8  mov     esi, r14d
0x140073cfb  mov     ebx, r14d
0x140073cfe  lea     rax, [rsp+4A8h+var_248]
0x140073d06  test    ebx, ebx
0x140073d08  lea     r8, [rsp+4A8h+var_458]
0x140073d0d  mov     edx, 104h; unsigned __int64
0x140073d12  cmovnz  r8, rax; unsigned __int16 *
0x140073d16  mov     rcx, rbp; unsigned __int16 *
0x140073d19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140073d1e  mov     edi, eax
0x140073d20  test    eax, eax
0x140073d22  jns     short loc_140073D50
0x140073d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d2b  cmp     rcx, r12
0x140073d2e  jz      short loc_140073D50
0x140073d30  test    byte ptr [rcx+1Ch], 2
0x140073d34  jz      short loc_140073D50
0x140073d36  cmp     byte ptr [rcx+19h], 2
0x140073d3a  jb      short loc_140073D50
0x140073d3c  mov     rcx, [rcx+10h]
0x140073d40  mov     edx, 29h ; ')'
0x140073d45  mov     r9d, eax
0x140073d48  mov     r8, r13
0x140073d4b  call    WPP_SF_d
0x140073d50  mov     ebx, r14d
0x140073d53  test    rsi, rsi
0x140073d56  jz      loc_140073FB3
0x140073d5c  mov     rcx, rsi; hLibModule
0x140073d5f  call    cs:__imp_FreeLibrary
0x140073d65  test    eax, eax
0x140073d67  jnz     loc_140073FB3
0x140073d6d  mov     rax, cs:WPP_GLOBAL_Control
0x140073d74  cmp     rax, r12
0x140073d77  jz      loc_140073FB3
0x140073d7d  test    byte ptr [rax+1Ch], 2
0x140073d81  jz      loc_140073FB3
0x140073d87  cmp     byte ptr [rax+19h], 3
0x140073d8b  jb      loc_140073FB3
0x140073d91  call    cs:__imp_GetLastError
0x140073d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d9e  mov     edx, 2Ah ; '*'
0x140073da3  jmp     loc_140073E89
0x140073da8  test    rdi, rdi
0x140073dab  jz      loc_140073F82
0x140073db1  mov     rdx, rbx
0x140073db4  lea     r8, [rsp+4A8h+var_458]
0x140073db9  mov     ebx, 1
0x140073dbe  mov     eax, 7FFFFFFEh
0x140073dc3  test    rax, rax
0x140073dc6  jz      short loc_140073DE4
0x140073dc8  movzx   ecx, word ptr [rdi]
0x140073dcb  test    cx, cx
0x140073dce  jz      short loc_140073DE4
0x140073dd0  mov     [r8], cx
0x140073dd4  add     rdi, 2
0x140073dd8  add     r8, 2
0x140073ddc  sub     rax, rbx
0x140073ddf  sub     rdx, rbx
0x140073de2  jnz     short loc_140073DC3
0x140073de4  mov     rax, rdx
0x140073de7  lea     rcx, [r8-2]
0x140073deb  neg     rax
0x140073dee  sbb     edi, edi
0x140073df0  not     edi
0x140073df2  and     edi, 8007007Ah
0x140073df8  test    rdx, rdx
0x140073dfb  cmovnz  rcx, r8
0x140073dff  mov     [rcx], r14w
0x140073e03  jnz     short loc_140073E45
0x140073e05  mov     ebx, r14d
0x140073e08  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e0f  cmp     rcx, r12
0x140073e12  jz      loc_140073FB3
0x140073e18  test    byte ptr [rcx+1Ch], 2
0x140073e1c  jz      loc_140073FB3
0x140073e22  cmp     byte ptr [rcx+19h], 2
0x140073e26  jb      loc_140073FB3
0x140073e2c  mov     rcx, [rcx+10h]
0x140073e30  mov     edx, 25h ; '%'
0x140073e35  mov     r9d, edi
0x140073e38  mov     r8, r13
0x140073e3b  call    WPP_SF_d
0x140073e40  jmp     loc_140073FB3
0x140073e45  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x140073e4c  call    cs:__imp_LoadLibraryW
0x140073e52  mov     rsi, rax
0x140073e55  test    rax, rax
0x140073e58  jnz     short loc_140073E9D
0x140073e5a  call    cs:__imp_GetLastError
0x140073e60  mov     ebx, eax
0x140073e62  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e69  cmp     rcx, r12
0x140073e6c  jz      loc_140073FB3
0x140073e72  test    byte ptr [rcx+1Ch], 2
0x140073e76  jz      loc_140073FB3
0x140073e7c  cmp     byte ptr [rcx+19h], 3
0x140073e80  jb      loc_140073FB3
0x140073e86  lea     edx, [rsi+26h]
0x140073e89  mov     rcx, [rcx+10h]
0x140073e8d  mov     r8, r13
0x140073e90  mov     r9d, eax
0x140073e93  call    WPP_SF_d
0x140073e98  jmp     loc_140073FB3
0x140073e9d  lea     rdx, aGetfilemuipath; "GetFileMUIPath"
0x140073ea4  mov     rcx, rax; hModule
0x140073ea7  call    cs:__imp_GetProcAddress
0x140073ead  test    rax, rax
0x140073eb0  jnz     short loc_140073EF7
0x140073eb2  call    cs:__imp_GetLastError
0x140073eb8  mov     ebx, eax
0x140073eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ec1  cmp     rcx, r12
0x140073ec4  jz      loc_140073D5C
0x140073eca  test    byte ptr [rcx+1Ch], 2
0x140073ece  jz      loc_140073D5C
0x140073ed4  cmp     byte ptr [rcx+19h], 3
0x140073ed8  jb      loc_140073D5C
0x140073ede  mov     rcx, [rcx+10h]
0x140073ee2  mov     edx, 27h ; '''
0x140073ee7  mov     r9d, eax
0x140073eea  mov     r8, r13
0x140073eed  call    WPP_SF_d
0x140073ef2  jmp     loc_140073D5C
0x140073ef7  lea     rcx, [rsp+4A8h+var_460]
0x140073efc  xor     r9d, r9d
0x140073eff  mov     [rsp+4A8h+var_478], rcx
0x140073f04  lea     rdx, [rsp+4A8h+var_458]
0x140073f09  lea     rcx, [rsp+4A8h+var_468]
0x140073f0e  xor     r8d, r8d
0x140073f11  mov     [rsp+4A8h+var_480], rcx
0x140073f16  lea     rcx, [rsp+4A8h+var_248]
0x140073f1e  mov     [rsp+4A8h+var_488], rcx
0x140073f23  lea     ecx, [r9+10h]
0x140073f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140073f2c  test    eax, eax
0x140073f2e  jnz     loc_140073CFE
0x140073f34  call    cs:__imp_GetLastError
0x140073f3a  mov     ebx, eax
0x140073f3c  cmp     eax, 12h
0x140073f3f  jz      loc_140073CFB
0x140073f45  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f4c  cmp     rcx, r12
0x140073f4f  jz      loc_140073D5C
0x140073f55  test    byte ptr [rcx+1Ch], 2
0x140073f59  jz      loc_140073D5C
0x140073f5f  cmp     byte ptr [rcx+19h], 2
0x140073f63  jb      loc_140073D5C
0x140073f69  mov     rcx, [rcx+10h]
0x140073f6d  mov     edx, 28h ; '('
0x140073f72  mov     r9d, edi
0x140073f75  mov     r8, r13
0x140073f78  call    WPP_SF_d
0x140073f7d  jmp     loc_140073D5C
0x140073f82  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f89  mov     edi, r14d
0x140073f8c  cmp     rcx, r12
0x140073f8f  jz      short loc_140073FAE
0x140073f91  test    byte ptr [rcx+1Ch], 2
0x140073f95  jz      short loc_140073FAE
0x140073f97  cmp     byte ptr [rcx+19h], 2
0x140073f9b  jb      short loc_140073FAE
0x140073f9d  mov     rcx, [rcx+10h]
0x140073fa1  mov     edx, 24h ; '$'
0x140073fa6  mov     r8, r13
0x140073fa9  call    WPP_SF_
0x140073fae  mov     ebx, 57h ; 'W'
0x140073fb3  test    edi, edi
0x140073fb5  movzx   eax, di
0x140073fb8  cmovns  eax, ebx
0x140073fbb  mov     rcx, [rsp+4A8h+var_38]
0x140073fc3  xor     rcx, rsp; StackCookie
0x140073fc6  call    __security_check_cookie
0x140073fcb  lea     r11, [rsp+4A8h+var_28]
0x140073fd3  mov     rbx, [r11+30h]
0x140073fd7  mov     rbp, [r11+40h]
0x140073fdb  mov     rsp, r11
0x140073fde  pop     r14
0x140073fe0  pop     r13
0x140073fe2  pop     r12
0x140073fe4  pop     rdi
0x140073fe5  pop     rsi
0x140073fe6  retn
```
