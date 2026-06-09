# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180097e34`
- end: `0x180098126`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002054c`

## callees

- `0x180004bb4`
- `0x180009b40`
- `0x180009bb4`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001fe24`
- `0x180097e34`
- `0x180099258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098051`
- `ntdll!NtQueryInformationProcess` at `0x180097ead`
- `ntdll!NtQueryInformationProcess` at `0x180097ead`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097ef9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f38`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097fa7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097ef9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f38`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097fa7`

## pseudocode

```c
__int64 __fastcall UtilGetProcessCommandLine(HANDLE hProcess, __int64 a2)
{
  NTSTATUS v4; // eax
  SIZE_T v5; // rbx
  unsigned int v6; // ebx
  signed int LastError; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  LPCVOID lpBaseAddress[2]; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpBuffer[2]; // [rsp+40h] [rbp-9h] BYREF
  _WORD v15[8]; // [rsp+50h] [rbp+7h] BYREF
  _OWORD ProcessInformation[4]; // [rsp+60h] [rbp+17h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+67h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+C0h] [rbp+77h] BYREF
  __int64 Buffer; // [rsp+C8h] [rbp+7Fh] BYREF

  Buffer = 0;
  lpBuffer[0] = v15;
  lpBuffer[1] = v15;
  v15[0] = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  memset(ProcessInformation, 0, 48);
  *(_OWORD *)lpBaseAddress = 0;
  if ( hProcess && a2 )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength);
    if ( v4 < 0 || ReturnLength != 48 || !*((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_QWORD *)&ProcessInformation[0] + 1),
          ReturnLength,
          (unsigned int)v4,
          ReturnLength,
          *((_QWORD *)&ProcessInformation[0] + 1));
      v6 = -2147467259;
      goto LABEL_37;
    }
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(
           hProcess,
           (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
           &Buffer,
           8u,
           &NumberOfBytesRead)
      && NumberOfBytesRead == 8 )
    {
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead)
        && NumberOfBytesRead == 16
        && lpBaseAddress[1] )
      {
        v5 = 0x2000;
        if ( LOWORD(lpBaseAddress[0]) <= 0x2000u )
          v5 = LOWORD(lpBaseAddress[0]);
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 lpBuffer,
                                 v5 >> 1) )
        {
          v6 = -2147024882;
LABEL_37:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
          return v6;
        }
        NumberOfBytesRead = 0;
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], lpBuffer[0], v5, &NumberOfBytesRead) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(
            lpBuffer,
            NumberOfBytesRead >> 1);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, lpBuffer);
          v6 = 0;
          goto LABEL_37;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_37;
        v9 = 61;
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_37;
        v9 = 60;
      }
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_37;
      v9 = 59;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180097e34  mov     [rsp-8+arg_8], rbx
0x180097e39  push    rbp
0x180097e3a  push    rsi
0x180097e3b  push    rdi
0x180097e3c  lea     rbp, [rsp-47h]
0x180097e41  sub     rsp, 90h
0x180097e48  xorps   xmm0, xmm0
0x180097e4b  mov     [rbp+57h+Buffer], 0
0x180097e53  lea     rax, [rbp+57h+var_50]
0x180097e57  mov     rsi, rdx
0x180097e5a  mov     [rbp+57h+lpBuffer], rax
0x180097e5e  mov     rdi, rcx
0x180097e61  lea     rax, [rbp+57h+var_50]
0x180097e65  mov     [rbp+57h+var_58], rax
0x180097e69  xor     eax, eax
0x180097e6b  mov     [rbp+57h+var_50], ax
0x180097e6f  mov     [rbp+57h+NumberOfBytesRead], rax
0x180097e73  mov     [rbp+57h+arg_0], eax
0x180097e76  movups  [rbp+57h+ProcessInformation], xmm0
0x180097e7a  movups  [rbp+57h+var_30], xmm0
0x180097e7e  movups  [rbp+57h+var_20], xmm0
0x180097e82  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x180097e86  test    rcx, rcx
0x180097e89  jz      loc_1800980D7
0x180097e8f  test    rdx, rdx
0x180097e92  jz      loc_1800980D7
0x180097e98  lea     rax, [rbp+57h+arg_0]
0x180097e9c  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180097ea2  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180097ea6  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180097eab  xor     edx, edx; ProcessInformationClass
0x180097ead  call    cs:__imp_NtQueryInformationProcess
0x180097eb3  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x180097eb7  mov     r9d, eax
0x180097eba  mov     r8d, [rbp+57h+arg_0]
0x180097ebe  test    eax, eax
0x180097ec0  js      loc_180098099
0x180097ec6  cmp     r8d, 30h ; '0'
0x180097eca  jnz     loc_180098099
0x180097ed0  test    rdx, rdx
0x180097ed3  jz      loc_180098099
0x180097ed9  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097edd  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097ee5  lea     r9d, [r8-28h]; nSize
0x180097ee9  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097eee  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180097ef2  add     rdx, 20h ; ' '; lpBaseAddress
0x180097ef6  mov     rcx, rdi; hProcess
0x180097ef9  call    cs:__imp_ReadProcessMemory
0x180097eff  test    eax, eax
0x180097f01  jz      loc_180098051
0x180097f07  cmp     [rbp+57h+NumberOfBytesRead], 8
0x180097f0c  jnz     loc_180098051
0x180097f12  mov     rdx, [rbp+57h+Buffer]
0x180097f16  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097f1a  add     rdx, 70h ; 'p'; lpBaseAddress
0x180097f1e  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097f26  mov     r9d, 10h; nSize
0x180097f2c  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097f31  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x180097f35  mov     rcx, rdi; hProcess
0x180097f38  call    cs:__imp_ReadProcessMemory
0x180097f3e  test    eax, eax
0x180097f40  jz      loc_180098014
0x180097f46  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x180097f4b  jnz     loc_180098014
0x180097f51  cmp     [rbp+57h+lpBaseAddress+8], 0
0x180097f56  jz      loc_180098014
0x180097f5c  mov     ebx, 2000h
0x180097f61  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x180097f65  jb      short loc_180097F6B
0x180097f67  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x180097f6b  mov     rdx, rbx
0x180097f6e  lea     rcx, [rbp+57h+lpBuffer]
0x180097f72  shr     rdx, 1
0x180097f75  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180097f7a  test    al, al
0x180097f7c  jnz     short loc_180097F88
0x180097f7e  mov     ebx, 8007000Eh
0x180097f83  jmp     loc_1800980CA
0x180097f88  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x180097f8c  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097f90  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x180097f94  mov     r9, rbx; nSize
0x180097f97  mov     rcx, rdi; hProcess
0x180097f9a  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097f9f  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097fa7  call    cs:__imp_ReadProcessMemory
0x180097fad  test    eax, eax
0x180097faf  jnz     short loc_180097FF1
0x180097fb1  call    cs:__imp_GetLastError
0x180097fb7  mov     ebx, eax
0x180097fb9  test    eax, eax
0x180097fbb  jle     short loc_180097FC6
0x180097fbd  movzx   ebx, ax
0x180097fc0  or      ebx, 80070000h
0x180097fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180097fcd  lea     rax, WPP_GLOBAL_Control
0x180097fd4  cmp     rcx, rax
0x180097fd7  jz      loc_1800980CA
0x180097fdd  test    byte ptr [rcx+1Ch], 1
0x180097fe1  jz      loc_1800980CA
0x180097fe7  mov     edx, 3Dh ; '='
0x180097fec  jmp     loc_180098084
0x180097ff1  mov     rdx, [rbp+57h+NumberOfBytesRead]
0x180097ff5  lea     rcx, [rbp+57h+lpBuffer]
0x180097ff9  shr     rdx, 1
0x180097ffc  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180098001  lea     rdx, [rbp+57h+lpBuffer]
0x180098005  mov     rcx, rsi
0x180098008  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18009800d  xor     ebx, ebx
0x18009800f  jmp     loc_1800980CA
0x180098014  call    cs:__imp_GetLastError
0x18009801a  mov     ebx, eax
0x18009801c  test    eax, eax
0x18009801e  jle     short loc_180098029
0x180098020  movzx   ebx, ax
0x180098023  or      ebx, 80070000h
0x180098029  mov     rcx, cs:WPP_GLOBAL_Control
0x180098030  lea     rax, WPP_GLOBAL_Control
0x180098037  cmp     rcx, rax
0x18009803a  jz      loc_1800980CA
0x180098040  test    byte ptr [rcx+1Ch], 1
0x180098044  jz      loc_1800980CA
0x18009804a  mov     edx, 3Ch ; '<'
0x18009804f  jmp     short loc_180098084
0x180098051  call    cs:__imp_GetLastError
0x180098057  mov     ebx, eax
0x180098059  test    eax, eax
0x18009805b  jle     short loc_180098066
0x18009805d  movzx   ebx, ax
0x180098060  or      ebx, 80070000h
0x180098066  mov     rcx, cs:WPP_GLOBAL_Control
0x18009806d  lea     rax, WPP_GLOBAL_Control
0x180098074  cmp     rcx, rax
0x180098077  jz      short loc_1800980CA
0x180098079  test    byte ptr [rcx+1Ch], 1
0x18009807d  jz      short loc_1800980CA
0x18009807f  mov     edx, 3Bh ; ';'
0x180098084  mov     rcx, [rcx+10h]
0x180098088  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009808f  mov     r9d, ebx
0x180098092  call    WPP_SF_d
0x180098097  jmp     short loc_1800980CA
0x180098099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980a0  lea     rax, WPP_GLOBAL_Control
0x1800980a7  cmp     rcx, rax
0x1800980aa  jz      short loc_1800980C5
0x1800980ac  test    byte ptr [rcx+1Ch], 1
0x1800980b0  jz      short loc_1800980C5
0x1800980b2  mov     rcx, [rcx+10h]
0x1800980b6  mov     [rsp+0A0h+var_78], rdx
0x1800980bb  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x1800980c0  call    WPP_SF_DDq
0x1800980c5  mov     ebx, 80004005h
0x1800980ca  lea     rcx, [rbp+57h+lpBuffer]; void *
0x1800980ce  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800980d3  mov     eax, ebx
0x1800980d5  jmp     short loc_180098113
0x1800980d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980de  lea     rax, WPP_GLOBAL_Control
0x1800980e5  cmp     rcx, rax
0x1800980e8  jz      short loc_180098105
0x1800980ea  test    byte ptr [rcx+1Ch], 1
0x1800980ee  jz      short loc_180098105
0x1800980f0  mov     rcx, [rcx+10h]
0x1800980f4  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800980fb  mov     edx, 39h ; '9'
0x180098100  call    WPP_SF_
0x180098105  lea     rcx, [rbp+57h+lpBuffer]; void *
0x180098109  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009810e  mov     eax, 80070057h
0x180098113  mov     rbx, [rsp+0A0h+arg_8]
0x18009811b  add     rsp, 90h
0x180098122  pop     rdi
0x180098123  pop     rsi
0x180098124  pop     rbp
0x180098125  retn
```
