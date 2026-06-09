# InitializeProcessImageNameUM

- ea: `0x180011ea8`
- end: `0x180012289`
- name: `InitializeProcessImageNameUM`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1800129ac`

## callees

- `0x18000da50`
- `0x180011ea8`
- `0x180017794`
- `0x18001a998`
- `0x18001b5a0`
- `0x18001b5ec`
- `0x18001b7a9`
- `0x18001b7e0`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x180012049`
- `ntdll!_wcsnicmp` at `0x180012049`
- `ntdll!wcsncpy_s` at `0x1800120ce`
- `ntdll!wcsncpy_s` at `0x180012146`
- `ntdll!wcsncpy_s` at `0x1800120ce`
- `ntdll!wcsncpy_s` at `0x180012146`
- `ntdll!_wsplitpath_s` at `0x180011fe4`
- `ntdll!_wsplitpath_s` at `0x180011fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001206b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001206b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011f57`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800120df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800120df`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800120a3`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180012108`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800120a3`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180012108`

## pseudocode

```c
unsigned int InitializeProcessImageNameUM()
{
  HANDLE CurrentProcess; // rdi
  unsigned int result; // eax
  __int64 v2; // r8
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rsi
  DWORD ProcessId; // eax
  DWORD v7; // edi
  wchar_t *v8; // rcx
  int v9; // eax
  __int64 v10; // r8
  wchar_t *v11; // rdi
  __int64 v12; // rax
  const wchar_t *v13; // r8
  _QWORD *v14; // rcx
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v16[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  wchar_t *Source; // [rsp+68h] [rbp-98h]
  __int128 v19; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String1; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[510]; // [rsp+82h] [rbp-7Eh] BYREF
  wchar_t Destination; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v23[526]; // [rsp+282h] [rbp+182h] BYREF
  WCHAR ExeName; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v25[526]; // [rsp+492h] [rbp+392h] BYREF

  CurrentProcess = GetCurrentProcess();
  if ( !CurrentProcess )
  {
    result = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v4 = 10;
      return WPP_SF_D(v3[2], v4, v2, result);
    }
    return result;
  }
  ExeName = 0;
  memset_0(v25, 0, 0x206u);
  dwSize = 260;
  if ( QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, &dwSize) )
  {
    String1 = 0;
    memset_0(v21, 0, sizeof(v21));
    result = _wsplitpath_s(&ExeName, 0, 0, 0, 0, &String1, 0x100u, 0, 0);
    if ( result )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v4 = 12;
        return WPP_SF_D(v3[2], v4, v2, result);
      }
      return result;
    }
    Destination = 0;
    memset_0(v23, 0, 0x206u);
    v5 = -1;
    if ( !_wcsnicmp(&String1, L"svchost", 7u) )
    {
      ProcessId = GetProcessId(CurrentProcess);
      v17 = 0;
      v7 = ProcessId;
      v16[0] = ProcessId;
      Source = 0;
      v16[1] = NtCurrentTeb()->SubProcessTag;
      if ( !(unsigned int)I_QueryTagInformation(0, 1, v16) )
      {
        if ( !Source )
          goto LABEL_29;
        wcsncpy_s(&Destination, 0x104u, Source, 0xFFFFFFFFFFFFFFFFuLL);
        v8 = Source;
        goto LABEL_17;
      }
      v19 = 0;
      LODWORD(v19) = v7;
      v9 = I_QueryTagInformation(0, 3, &v19);
      if ( v9 )
      {
        if ( v9 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v10, (unsigned int)v9);
        }
      }
      else
      {
        v11 = (wchar_t *)*((_QWORD *)&v19 + 1);
        if ( *((_QWORD *)&v19 + 1) )
        {
          if ( **((_DWORD **)&v19 + 1) == 1 )
          {
            v12 = *(_QWORD *)(*((_QWORD *)&v19 + 1) + 8LL);
            if ( *(_DWORD *)v12 == 1 )
            {
              v13 = *(const wchar_t **)(v12 + 8);
              if ( v13 )
                wcsncpy_s(&Destination, 0x104u, v13, 0xFFFFFFFFFFFFFFFFuLL);
            }
          }
          v8 = v11;
LABEL_17:
          LocalFree(v8);
          goto LABEL_29;
        }
      }
    }
    do
LABEL_29:
      ++v5;
    while ( *(_WORD *)&v23[2 * v5 - 2] );
    if ( v5 )
      result = StringCchPrintfW(g_processImageName, 0x104u, L"%ls[%ls]", &String1, &Destination);
    else
      result = StringCchCopyW(g_processImageName, 0x104u, &String1);
    if ( result == -2147024774 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v14 + 28) & 2) != 0 )
          {
            result = WPP_SF_S(v14[2], 15, v2, &String1);
            v14 = WPP_GLOBAL_Control;
          }
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
            return WPP_SF_S(v14[2], 16, v2, &Destination);
        }
      }
    }
    else if ( (result & 0x80000000) != 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 17;
        return WPP_SF_D(v3[2], v4, v2, result);
      }
    }
    return result;
  }
  result = GetLastError();
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v4 = 11;
    return WPP_SF_D(v3[2], v4, v2, result);
  }
  return result;
}

```

## disassembly

```asm
0x180011ea8  push    rbp
0x180011eaa  push    rbx
0x180011eab  push    rsi
0x180011eac  push    rdi
0x180011ead  push    r12
0x180011eaf  push    r14
0x180011eb1  lea     rbp, [rsp-5B8h]
0x180011eb9  sub     rsp, 6B8h
0x180011ec0  mov     rax, cs:__security_cookie
0x180011ec7  xor     rax, rsp
0x180011eca  mov     [rbp+5E0h+var_40], rax
0x180011ed1  call    cs:__imp_GetCurrentProcess
0x180011ed8  nop     dword ptr [rax+rax+00h]
0x180011edd  xor     r14d, r14d
0x180011ee0  mov     rdi, rax
0x180011ee3  test    rax, rax
0x180011ee6  jnz     short loc_180011F1D
0x180011ee8  call    cs:__imp_GetLastError
0x180011eef  nop     dword ptr [rax+rax+00h]
0x180011ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011efb  lea     rbx, WPP_GLOBAL_Control
0x180011f02  cmp     rcx, rbx
0x180011f05  jz      loc_180012269
0x180011f0b  test    byte ptr [rcx+1Ch], 2
0x180011f0f  jz      loc_180012269
0x180011f15  lea     edx, [rdi+0Ah]
0x180011f18  jmp     loc_18001225D
0x180011f1d  mov     ebx, 206h
0x180011f22  mov     [rbp+5E0h+ExeName], r14w
0x180011f2a  mov     r8d, ebx; Size
0x180011f2d  lea     rcx, [rbp+5E0h+var_24E]; void *
0x180011f34  xor     edx, edx; Val
0x180011f36  call    memset_0
0x180011f3b  mov     r12d, 104h
0x180011f41  lea     r9, [rsp+6E0h+dwSize]; lpdwSize
0x180011f46  lea     r8, [rbp+5E0h+ExeName]; lpExeName
0x180011f4d  mov     [rsp+6E0h+dwSize], r12d
0x180011f52  xor     edx, edx; dwFlags
0x180011f54  mov     rcx, rdi; hProcess
0x180011f57  call    cs:__imp_QueryFullProcessImageNameW
0x180011f5e  nop     dword ptr [rax+rax+00h]
0x180011f63  test    eax, eax
0x180011f65  jnz     short loc_180011F9E
0x180011f67  call    cs:__imp_GetLastError
0x180011f6e  nop     dword ptr [rax+rax+00h]
0x180011f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f7a  lea     rbx, WPP_GLOBAL_Control
0x180011f81  cmp     rcx, rbx
0x180011f84  jz      loc_180012269
0x180011f8a  test    byte ptr [rcx+1Ch], 2
0x180011f8e  jz      loc_180012269
0x180011f94  mov     edx, 0Bh
0x180011f99  jmp     loc_18001225D
0x180011f9e  xor     edx, edx; Val
0x180011fa0  mov     [rbp+5E0h+String1], r14w
0x180011fa5  mov     r8d, 1FEh; Size
0x180011fab  lea     rcx, [rbp+5E0h+var_65E]; void *
0x180011faf  call    memset_0
0x180011fb4  mov     [rsp+6E0h+ExtCount], r14; ExtCount
0x180011fb9  lea     rax, [rbp+5E0h+String1]
0x180011fbd  mov     [rsp+6E0h+Ext], r14; Ext
0x180011fc2  lea     rcx, [rbp+5E0h+ExeName]; FullPath
0x180011fc9  mov     [rsp+6E0h+FilenameCount], 100h; FilenameCount
0x180011fd2  xor     r9d, r9d; Dir
0x180011fd5  mov     [rsp+6E0h+Filename], rax; Filename
0x180011fda  xor     r8d, r8d; DriveCount
0x180011fdd  xor     edx, edx; Drive
0x180011fdf  mov     [rsp+6E0h+DirCount], r14; DirCount
0x180011fe4  call    cs:__imp__wsplitpath_s
0x180011feb  nop     dword ptr [rax+rax+00h]
0x180011ff0  test    eax, eax
0x180011ff2  jz      short loc_18001201F
0x180011ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ffb  lea     rbx, WPP_GLOBAL_Control
0x180012002  cmp     rcx, rbx
0x180012005  jz      loc_180012269
0x18001200b  test    byte ptr [rcx+1Ch], 2
0x18001200f  jz      loc_180012269
0x180012015  mov     edx, 0Ch
0x18001201a  jmp     loc_18001225D
0x18001201f  mov     r8, rbx; Size
0x180012022  mov     [rbp+5E0h+Destination], r14w
0x18001202a  xor     edx, edx; Val
0x18001202c  lea     rcx, [rbp+5E0h+var_45E]; void *
0x180012033  call    memset_0
0x180012038  mov     r8d, 7; MaxCount
0x18001203e  lea     rdx, aSvchost; "svchost"
0x180012045  lea     rcx, [rbp+5E0h+String1]; String1
0x180012049  call    cs:__imp__wcsnicmp
0x180012050  nop     dword ptr [rax+rax+00h]
0x180012055  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012059  lea     rbx, WPP_GLOBAL_Control
0x180012060  test    eax, eax
0x180012062  jnz     loc_18001217C
0x180012068  mov     rcx, rdi; Process
0x18001206b  call    cs:__imp_GetProcessId
0x180012072  nop     dword ptr [rax+rax+00h]
0x180012077  xorps   xmm0, xmm0
0x18001207a  lea     r8, [rsp+6E0h+var_688]
0x18001207f  movups  [rsp+6E0h+var_688], xmm0
0x180012084  mov     edi, eax
0x180012086  lea     edx, [rsi+2]
0x180012089  xor     eax, eax
0x18001208b  mov     dword ptr [rsp+6E0h+var_688], edi
0x18001208f  mov     [rsp+6E0h+Source], rax
0x180012094  mov     rcx, gs:1720h
0x18001209d  mov     dword ptr [rsp+6E0h+var_688+4], ecx
0x1800120a1  xor     ecx, ecx
0x1800120a3  call    cs:__imp_I_QueryTagInformation
0x1800120aa  nop     dword ptr [rax+rax+00h]
0x1800120af  test    eax, eax
0x1800120b1  jnz     short loc_1800120F0
0x1800120b3  mov     r8, [rsp+6E0h+Source]; Source
0x1800120b8  test    r8, r8
0x1800120bb  jz      loc_18001217C
0x1800120c1  mov     r9, rsi; MaxCount
0x1800120c4  lea     rcx, [rbp+5E0h+Destination]; Destination
0x1800120cb  mov     rdx, r12; SizeInWords
0x1800120ce  call    cs:__imp_wcsncpy_s
0x1800120d5  nop     dword ptr [rax+rax+00h]
0x1800120da  mov     rcx, [rsp+6E0h+Source]; hMem
0x1800120df  call    cs:__imp_LocalFree
0x1800120e6  nop     dword ptr [rax+rax+00h]
0x1800120eb  jmp     loc_18001217C
0x1800120f0  xorps   xmm0, xmm0
0x1800120f3  lea     r8, [rsp+6E0h+var_670]
0x1800120f8  movups  [rsp+6E0h+var_670], xmm0
0x1800120fd  mov     edx, 3
0x180012102  mov     dword ptr [rsp+6E0h+var_670], edi
0x180012106  xor     ecx, ecx
0x180012108  call    cs:__imp_I_QueryTagInformation
0x18001210f  nop     dword ptr [rax+rax+00h]
0x180012114  test    eax, eax
0x180012116  jnz     short loc_180012157
0x180012118  mov     rdi, qword ptr [rsp+6E0h+var_670+8]
0x18001211d  test    rdi, rdi
0x180012120  jz      short loc_18001217C
0x180012122  cmp     dword ptr [rdi], 1
0x180012125  jnz     short loc_180012152
0x180012127  mov     rax, [rdi+8]
0x18001212b  cmp     dword ptr [rax], 1
0x18001212e  jnz     short loc_180012152
0x180012130  mov     r8, [rax+8]; Source
0x180012134  test    r8, r8
0x180012137  jz      short loc_180012152
0x180012139  mov     r9, rsi; MaxCount
0x18001213c  lea     rcx, [rbp+5E0h+Destination]; Destination
0x180012143  mov     rdx, r12; SizeInWords
0x180012146  call    cs:__imp_wcsncpy_s
0x18001214d  nop     dword ptr [rax+rax+00h]
0x180012152  mov     rcx, rdi
0x180012155  jmp     short loc_1800120DF
0x180012157  jns     short loc_18001217C
0x180012159  mov     rcx, cs:WPP_GLOBAL_Control
0x180012160  cmp     rcx, rbx
0x180012163  jz      short loc_18001217C
0x180012165  test    byte ptr [rcx+1Ch], 2
0x180012169  jz      short loc_18001217C
0x18001216b  mov     rcx, [rcx+10h]
0x18001216f  mov     edx, 0Dh
0x180012174  mov     r9d, eax
0x180012177  call    WPP_SF_D
0x18001217c  lea     rax, [rbp+5E0h+Destination]
0x180012183  inc     rsi
0x180012186  cmp     [rax+rsi*2], r14w
0x18001218b  jnz     short loc_180012183
0x18001218d  lea     rcx, g_processImageName; "UNKNOWN"
0x180012194  mov     rdx, r12; cchDest
0x180012197  test    rsi, rsi
0x18001219a  jz      short loc_1800121BA
0x18001219c  lea     rax, [rbp+5E0h+Destination]
0x1800121a3  lea     r9, [rbp+5E0h+String1]
0x1800121a7  mov     [rsp+6E0h+DirCount], rax
0x1800121ac  lea     r8, aLsLs; "%ls[%ls]"
0x1800121b3  call    StringCchPrintfW
0x1800121b8  jmp     short loc_1800121C3
0x1800121ba  lea     r8, [rbp+5E0h+String1]; pszSrc
0x1800121be  call    StringCchCopyW
0x1800121c3  cmp     eax, 8007007Ah
0x1800121c8  jnz     short loc_180012242
0x1800121ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121d1  cmp     rcx, rbx
0x1800121d4  jz      loc_180012269
0x1800121da  test    byte ptr [rcx+1Ch], 2
0x1800121de  jz      short loc_1800121FC
0x1800121e0  mov     rcx, [rcx+10h]
0x1800121e4  lea     r8, WPP_e1d0dcb54b7b37c40c9d35ea35f91ff9_Traceguids
0x1800121eb  mov     edx, 0Eh
0x1800121f0  call    WPP_SF_
0x1800121f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121fc  cmp     rcx, rbx
0x1800121ff  jz      short loc_180012269
0x180012201  test    byte ptr [rcx+1Ch], 2
0x180012205  jz      short loc_180012220
0x180012207  mov     rcx, [rcx+10h]
0x18001220b  lea     r9, [rbp+5E0h+String1]
0x18001220f  mov     edx, 0Fh
0x180012214  call    WPP_SF_S
0x180012219  mov     rcx, cs:WPP_GLOBAL_Control
0x180012220  cmp     rcx, rbx
0x180012223  jz      short loc_180012269
0x180012225  test    byte ptr [rcx+1Ch], 2
0x180012229  jz      short loc_180012269
0x18001222b  mov     rcx, [rcx+10h]
0x18001222f  lea     r9, [rbp+5E0h+Destination]
0x180012236  mov     edx, 10h
0x18001223b  call    WPP_SF_S
0x180012240  jmp     short loc_180012269
0x180012242  test    eax, eax
0x180012244  jns     short loc_180012269
0x180012246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001224d  cmp     rcx, rbx
0x180012250  jz      short loc_180012269
0x180012252  test    byte ptr [rcx+1Ch], 1
0x180012256  jz      short loc_180012269
0x180012258  mov     edx, 11h
0x18001225d  mov     rcx, [rcx+10h]
0x180012261  mov     r9d, eax
0x180012264  call    WPP_SF_D
0x180012269  mov     rcx, [rbp+5E0h+var_40]
0x180012270  xor     rcx, rsp; StackCookie
0x180012273  call    __security_check_cookie
0x180012278  add     rsp, 6B8h
0x18001227f  pop     r14
0x180012281  pop     r12
0x180012283  pop     rdi
0x180012284  pop     rsi
0x180012285  pop     rbx
0x180012286  pop     rbp
0x180012287  retn
```
