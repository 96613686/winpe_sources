# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140010cdc`
- end: `0x140011007`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140030cd8`
- `0x140031c08`

## callees

- `0x140002728`
- `0x14000cc58`
- `0x14000e6dc`
- `0x140010cdc`
- `0x14001444c`
- `0x140014474`
- `0x140014500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f12`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010da1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010de0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010e4f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010da1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010de0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140010e4f`
- `ntdll!NtQueryInformationProcess` at `0x140010d55`
- `ntdll!NtQueryInformationProcess` at `0x140010d55`

## pseudocode

```c
__int64 __fastcall UtilGetProcessCommandLine(HANDLE hProcess, __int64 a2)
{
  NTSTATUS v4; // eax
  SIZE_T v5; // rbx
  unsigned int v6; // ebx
  signed int LastError; // eax
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  LPCVOID lpBaseAddress[2]; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-9h] BYREF
  char *v15; // [rsp+48h] [rbp-1h]
  _WORD v16[8]; // [rsp+50h] [rbp+7h] BYREF
  _OWORD ProcessInformation[4]; // [rsp+60h] [rbp+17h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+67h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+C0h] [rbp+77h] BYREF
  __int64 Buffer; // [rsp+C8h] [rbp+7Fh] BYREF

  Buffer = 0;
  lpBuffer = v16;
  v15 = (char *)v16;
  v16[0] = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  memset(ProcessInformation, 0, 48);
  *(_OWORD *)lpBaseAddress = 0;
  if ( hProcess && a2 )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength);
    if ( v4 < 0 || ReturnLength != 48 || !*((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_QWORD *)&ProcessInformation[0] + 1),
          ReturnLength,
          (unsigned int)v4,
          ReturnLength,
          *((_QWORD *)&ProcessInformation[0] + 1));
      }
      v6 = -2147467259;
      goto LABEL_39;
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
                                 &lpBuffer,
                                 v5 >> 1) )
        {
          v6 = -2147024882;
          goto LABEL_39;
        }
        NumberOfBytesRead = 0;
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], lpBuffer, v5, &NumberOfBytesRead) )
        {
          if ( NumberOfBytesRead >> 1 > (v15 - (_BYTE *)lpBuffer) >> 1 )
            __int2c();
          v15 = (char *)lpBuffer + 2 * (NumberOfBytesRead >> 1);
          *(_WORD *)v15 = 0;
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpBuffer);
          v6 = 0;
          goto LABEL_39;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_39:
          if ( lpBuffer != v16 )
            operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
          return v6;
        }
        v9 = 61;
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_39;
        }
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
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_39;
      }
      v9 = 59;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    if ( lpBuffer != v16 )
      operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140010cdc  mov     [rsp-8+arg_8], rbx
0x140010ce1  push    rbp
0x140010ce2  push    rsi
0x140010ce3  push    rdi
0x140010ce4  lea     rbp, [rsp-47h]
0x140010ce9  sub     rsp, 90h
0x140010cf0  xorps   xmm0, xmm0
0x140010cf3  mov     [rbp+57h+Buffer], 0
0x140010cfb  lea     rax, [rbp+57h+var_50]
0x140010cff  mov     rsi, rdx
0x140010d02  mov     [rbp+57h+lpBuffer], rax
0x140010d06  mov     rdi, rcx
0x140010d09  lea     rax, [rbp+57h+var_50]
0x140010d0d  mov     [rbp+57h+var_58], rax
0x140010d11  xor     eax, eax
0x140010d13  mov     [rbp+57h+var_50], ax
0x140010d17  mov     [rbp+57h+NumberOfBytesRead], rax
0x140010d1b  mov     [rbp+57h+arg_0], eax
0x140010d1e  movups  [rbp+57h+ProcessInformation], xmm0
0x140010d22  movups  [rbp+57h+var_30], xmm0
0x140010d26  movups  [rbp+57h+var_20], xmm0
0x140010d2a  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x140010d2e  test    rcx, rcx
0x140010d31  jz      loc_140010FA8
0x140010d37  test    rdx, rdx
0x140010d3a  jz      loc_140010FA8
0x140010d40  lea     rax, [rbp+57h+arg_0]
0x140010d44  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140010d4a  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140010d4e  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x140010d53  xor     edx, edx; ProcessInformationClass
0x140010d55  call    cs:__imp_NtQueryInformationProcess
0x140010d5b  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x140010d5f  mov     r9d, eax
0x140010d62  mov     r8d, [rbp+57h+arg_0]
0x140010d66  test    eax, eax
0x140010d68  js      loc_140010F5A
0x140010d6e  cmp     r8d, 30h ; '0'
0x140010d72  jnz     loc_140010F5A
0x140010d78  test    rdx, rdx
0x140010d7b  jz      loc_140010F5A
0x140010d81  lea     rax, [rbp+57h+NumberOfBytesRead]
0x140010d85  mov     [rbp+57h+NumberOfBytesRead], 0
0x140010d8d  lea     r9d, [r8-28h]; nSize
0x140010d91  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x140010d96  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x140010d9a  add     rdx, 20h ; ' '; lpBaseAddress
0x140010d9e  mov     rcx, rdi; hProcess
0x140010da1  call    cs:__imp_ReadProcessMemory
0x140010da7  test    eax, eax
0x140010da9  jz      loc_140010F12
0x140010daf  cmp     [rbp+57h+NumberOfBytesRead], 8
0x140010db4  jnz     loc_140010F12
0x140010dba  mov     rdx, [rbp+57h+Buffer]
0x140010dbe  lea     rax, [rbp+57h+NumberOfBytesRead]
0x140010dc2  add     rdx, 70h ; 'p'; lpBaseAddress
0x140010dc6  mov     [rbp+57h+NumberOfBytesRead], 0
0x140010dce  mov     r9d, 10h; nSize
0x140010dd4  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x140010dd9  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x140010ddd  mov     rcx, rdi; hProcess
0x140010de0  call    cs:__imp_ReadProcessMemory
0x140010de6  test    eax, eax
0x140010de8  jz      loc_140010ED5
0x140010dee  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x140010df3  jnz     loc_140010ED5
0x140010df9  cmp     [rbp+57h+lpBaseAddress+8], 0
0x140010dfe  jz      loc_140010ED5
0x140010e04  mov     ebx, 2000h
0x140010e09  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x140010e0d  jb      short loc_140010E13
0x140010e0f  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x140010e13  mov     rdx, rbx
0x140010e16  lea     rcx, [rbp+57h+lpBuffer]
0x140010e1a  shr     rdx, 1
0x140010e1d  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x140010e22  test    al, al
0x140010e24  jnz     short loc_140010E30
0x140010e26  mov     ebx, 8007000Eh
0x140010e2b  jmp     loc_140010F8B
0x140010e30  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x140010e34  lea     rax, [rbp+57h+NumberOfBytesRead]
0x140010e38  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x140010e3c  mov     r9, rbx; nSize
0x140010e3f  mov     rcx, rdi; hProcess
0x140010e42  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x140010e47  mov     [rbp+57h+NumberOfBytesRead], 0
0x140010e4f  call    cs:__imp_ReadProcessMemory
0x140010e55  test    eax, eax
0x140010e57  jnz     short loc_140010E99
0x140010e59  call    cs:__imp_GetLastError
0x140010e5f  mov     ebx, eax
0x140010e61  test    eax, eax
0x140010e63  jle     short loc_140010E6E
0x140010e65  movzx   ebx, ax
0x140010e68  or      ebx, 80070000h
0x140010e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e75  lea     rax, WPP_GLOBAL_Control
0x140010e7c  cmp     rcx, rax
0x140010e7f  jz      loc_140010F8B
0x140010e85  test    byte ptr [rcx+1Ch], 1
0x140010e89  jz      loc_140010F8B
0x140010e8f  mov     edx, 3Dh ; '='
0x140010e94  jmp     loc_140010F45
0x140010e99  mov     rax, [rbp+57h+var_58]
0x140010e9d  mov     rdx, [rbp+57h+lpBuffer]
0x140010ea1  mov     rcx, [rbp+57h+NumberOfBytesRead]
0x140010ea5  sub     rax, rdx
0x140010ea8  sar     rax, 1
0x140010eab  shr     rcx, 1
0x140010eae  cmp     rcx, rax
0x140010eb1  jbe     short loc_140010EB5
0x140010eb3  int     2Ch; Windows NT - assertion failure
0x140010eb5  lea     rcx, [rdx+rcx*2]
0x140010eb9  xor     eax, eax
0x140010ebb  mov     [rbp+57h+var_58], rcx
0x140010ebf  lea     rdx, [rbp+57h+lpBuffer]
0x140010ec3  mov     [rcx], ax
0x140010ec6  mov     rcx, rsi
0x140010ec9  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x140010ece  xor     ebx, ebx
0x140010ed0  jmp     loc_140010F8B
0x140010ed5  call    cs:__imp_GetLastError
0x140010edb  mov     ebx, eax
0x140010edd  test    eax, eax
0x140010edf  jle     short loc_140010EEA
0x140010ee1  movzx   ebx, ax
0x140010ee4  or      ebx, 80070000h
0x140010eea  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ef1  lea     rax, WPP_GLOBAL_Control
0x140010ef8  cmp     rcx, rax
0x140010efb  jz      loc_140010F8B
0x140010f01  test    byte ptr [rcx+1Ch], 1
0x140010f05  jz      loc_140010F8B
0x140010f0b  mov     edx, 3Ch ; '<'
0x140010f10  jmp     short loc_140010F45
0x140010f12  call    cs:__imp_GetLastError
0x140010f18  mov     ebx, eax
0x140010f1a  test    eax, eax
0x140010f1c  jle     short loc_140010F27
0x140010f1e  movzx   ebx, ax
0x140010f21  or      ebx, 80070000h
0x140010f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f2e  lea     rax, WPP_GLOBAL_Control
0x140010f35  cmp     rcx, rax
0x140010f38  jz      short loc_140010F8B
0x140010f3a  test    byte ptr [rcx+1Ch], 1
0x140010f3e  jz      short loc_140010F8B
0x140010f40  mov     edx, 3Bh ; ';'
0x140010f45  mov     rcx, [rcx+10h]
0x140010f49  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140010f50  mov     r9d, ebx
0x140010f53  call    WPP_SF_d
0x140010f58  jmp     short loc_140010F8B
0x140010f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f61  lea     rax, WPP_GLOBAL_Control
0x140010f68  cmp     rcx, rax
0x140010f6b  jz      short loc_140010F86
0x140010f6d  test    byte ptr [rcx+1Ch], 1
0x140010f71  jz      short loc_140010F86
0x140010f73  mov     rcx, [rcx+10h]
0x140010f77  mov     [rsp+0A0h+var_78], rdx
0x140010f7c  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x140010f81  call    WPP_SF_DDq
0x140010f86  mov     ebx, 80004005h
0x140010f8b  mov     rcx, [rbp+57h+lpBuffer]; void *
0x140010f8f  lea     rax, [rbp+57h+var_50]
0x140010f93  cmp     rcx, rax
0x140010f96  jz      short loc_140010FA4
0x140010f98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010f9f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010fa4  mov     eax, ebx
0x140010fa6  jmp     short loc_140010FF4
0x140010fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140010faf  lea     rax, WPP_GLOBAL_Control
0x140010fb6  cmp     rcx, rax
0x140010fb9  jz      short loc_140010FEF
0x140010fbb  test    byte ptr [rcx+1Ch], 1
0x140010fbf  jz      short loc_140010FEF
0x140010fc1  mov     rcx, [rcx+10h]
0x140010fc5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140010fcc  mov     edx, 39h ; '9'
0x140010fd1  call    WPP_SF_
0x140010fd6  mov     rcx, [rbp+57h+lpBuffer]; void *
0x140010fda  lea     rax, [rbp+57h+var_50]
0x140010fde  cmp     rcx, rax
0x140010fe1  jz      short loc_140010FEF
0x140010fe3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010fea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010fef  mov     eax, 80070057h
0x140010ff4  mov     rbx, [rsp+0A0h+arg_8]
0x140010ffc  add     rsp, 90h
0x140011003  pop     rdi
0x140011004  pop     rsi
0x140011005  pop     rbp
0x140011006  retn
```
