# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1400113b8`
- end: `0x14001170e`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140032ec4`
- `0x140033dfc`

## callees

- `0x140002748`
- `0x14000cf48`
- `0x14000e9d4`
- `0x1400113b8`
- `0x140014ee4`
- `0x140014f14`
- `0x140014fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001154d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001154d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011612`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140011483`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400114c8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14001153d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140011483`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400114c8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14001153d`
- `ntdll!NtQueryInformationProcess` at `0x140011431`
- `ntdll!NtQueryInformationProcess` at `0x140011431`

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
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v6);
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    if ( lpBuffer != v16 )
      operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400113b8  mov     [rsp-8+arg_8], rbx
0x1400113bd  push    rbp
0x1400113be  push    rsi
0x1400113bf  push    rdi
0x1400113c0  lea     rbp, [rsp-47h]
0x1400113c5  sub     rsp, 90h
0x1400113cc  xorps   xmm0, xmm0
0x1400113cf  mov     [rbp+57h+Buffer], 0
0x1400113d7  lea     rax, [rbp+57h+var_50]
0x1400113db  mov     rsi, rdx
0x1400113de  mov     [rbp+57h+lpBuffer], rax
0x1400113e2  mov     rdi, rcx
0x1400113e5  lea     rax, [rbp+57h+var_50]
0x1400113e9  mov     [rbp+57h+var_58], rax
0x1400113ed  xor     eax, eax
0x1400113ef  mov     [rbp+57h+var_50], ax
0x1400113f3  mov     [rbp+57h+NumberOfBytesRead], rax
0x1400113f7  mov     [rbp+57h+arg_0], eax
0x1400113fa  movups  [rbp+57h+ProcessInformation], xmm0
0x1400113fe  movups  [rbp+57h+var_30], xmm0
0x140011402  movups  [rbp+57h+var_20], xmm0
0x140011406  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x14001140a  test    rcx, rcx
0x14001140d  jz      loc_1400116AE
0x140011413  test    rdx, rdx
0x140011416  jz      loc_1400116AE
0x14001141c  lea     rax, [rbp+57h+arg_0]
0x140011420  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140011426  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14001142a  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x14001142f  xor     edx, edx; ProcessInformationClass
0x140011431  call    cs:__imp_NtQueryInformationProcess
0x140011438  nop     dword ptr [rax+rax+00h]
0x14001143d  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x140011441  mov     r9d, eax
0x140011444  mov     r8d, [rbp+57h+arg_0]
0x140011448  test    eax, eax
0x14001144a  js      loc_140011660
0x140011450  cmp     r8d, 30h ; '0'
0x140011454  jnz     loc_140011660
0x14001145a  test    rdx, rdx
0x14001145d  jz      loc_140011660
0x140011463  lea     rax, [rbp+57h+NumberOfBytesRead]
0x140011467  mov     [rbp+57h+NumberOfBytesRead], 0
0x14001146f  lea     r9d, [r8-28h]; nSize
0x140011473  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x140011478  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14001147c  add     rdx, 20h ; ' '; lpBaseAddress
0x140011480  mov     rcx, rdi; hProcess
0x140011483  call    cs:__imp_ReadProcessMemory
0x14001148a  nop     dword ptr [rax+rax+00h]
0x14001148f  test    eax, eax
0x140011491  jz      loc_140011612
0x140011497  cmp     [rbp+57h+NumberOfBytesRead], 8
0x14001149c  jnz     loc_140011612
0x1400114a2  mov     rdx, [rbp+57h+Buffer]
0x1400114a6  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1400114aa  add     rdx, 70h ; 'p'; lpBaseAddress
0x1400114ae  mov     [rbp+57h+NumberOfBytesRead], 0
0x1400114b6  mov     r9d, 10h; nSize
0x1400114bc  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x1400114c1  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x1400114c5  mov     rcx, rdi; hProcess
0x1400114c8  call    cs:__imp_ReadProcessMemory
0x1400114cf  nop     dword ptr [rax+rax+00h]
0x1400114d4  test    eax, eax
0x1400114d6  jz      loc_1400115CF
0x1400114dc  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x1400114e1  jnz     loc_1400115CF
0x1400114e7  cmp     [rbp+57h+lpBaseAddress+8], 0
0x1400114ec  jz      loc_1400115CF
0x1400114f2  mov     ebx, 2000h
0x1400114f7  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x1400114fb  jb      short loc_140011501
0x1400114fd  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x140011501  mov     rdx, rbx
0x140011504  lea     rcx, [rbp+57h+lpBuffer]
0x140011508  shr     rdx, 1
0x14001150b  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x140011510  test    al, al
0x140011512  jnz     short loc_14001151E
0x140011514  mov     ebx, 8007000Eh
0x140011519  jmp     loc_140011691
0x14001151e  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x140011522  lea     rax, [rbp+57h+NumberOfBytesRead]
0x140011526  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x14001152a  mov     r9, rbx; nSize
0x14001152d  mov     rcx, rdi; hProcess
0x140011530  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x140011535  mov     [rbp+57h+NumberOfBytesRead], 0
0x14001153d  call    cs:__imp_ReadProcessMemory
0x140011544  nop     dword ptr [rax+rax+00h]
0x140011549  test    eax, eax
0x14001154b  jnz     short loc_140011593
0x14001154d  call    cs:__imp_GetLastError
0x140011554  nop     dword ptr [rax+rax+00h]
0x140011559  mov     ebx, eax
0x14001155b  test    eax, eax
0x14001155d  jle     short loc_140011568
0x14001155f  movzx   ebx, ax
0x140011562  or      ebx, 80070000h
0x140011568  mov     rcx, cs:WPP_GLOBAL_Control
0x14001156f  lea     rax, WPP_GLOBAL_Control
0x140011576  cmp     rcx, rax
0x140011579  jz      loc_140011691
0x14001157f  test    byte ptr [rcx+1Ch], 1
0x140011583  jz      loc_140011691
0x140011589  mov     edx, 3Dh ; '='
0x14001158e  jmp     loc_14001164B
0x140011593  mov     rax, [rbp+57h+var_58]
0x140011597  mov     rdx, [rbp+57h+lpBuffer]
0x14001159b  mov     rcx, [rbp+57h+NumberOfBytesRead]
0x14001159f  sub     rax, rdx
0x1400115a2  sar     rax, 1
0x1400115a5  shr     rcx, 1
0x1400115a8  cmp     rcx, rax
0x1400115ab  jbe     short loc_1400115AF
0x1400115ad  int     2Ch; Windows NT - assertion failure
0x1400115af  lea     rcx, [rdx+rcx*2]
0x1400115b3  xor     eax, eax
0x1400115b5  mov     [rbp+57h+var_58], rcx
0x1400115b9  lea     rdx, [rbp+57h+lpBuffer]
0x1400115bd  mov     [rcx], ax
0x1400115c0  mov     rcx, rsi
0x1400115c3  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1400115c8  xor     ebx, ebx
0x1400115ca  jmp     loc_140011691
0x1400115cf  call    cs:__imp_GetLastError
0x1400115d6  nop     dword ptr [rax+rax+00h]
0x1400115db  mov     ebx, eax
0x1400115dd  test    eax, eax
0x1400115df  jle     short loc_1400115EA
0x1400115e1  movzx   ebx, ax
0x1400115e4  or      ebx, 80070000h
0x1400115ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115f1  lea     rax, WPP_GLOBAL_Control
0x1400115f8  cmp     rcx, rax
0x1400115fb  jz      loc_140011691
0x140011601  test    byte ptr [rcx+1Ch], 1
0x140011605  jz      loc_140011691
0x14001160b  mov     edx, 3Ch ; '<'
0x140011610  jmp     short loc_14001164B
0x140011612  call    cs:__imp_GetLastError
0x140011619  nop     dword ptr [rax+rax+00h]
0x14001161e  mov     ebx, eax
0x140011620  test    eax, eax
0x140011622  jle     short loc_14001162D
0x140011624  movzx   ebx, ax
0x140011627  or      ebx, 80070000h
0x14001162d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011634  lea     rax, WPP_GLOBAL_Control
0x14001163b  cmp     rcx, rax
0x14001163e  jz      short loc_140011691
0x140011640  test    byte ptr [rcx+1Ch], 1
0x140011644  jz      short loc_140011691
0x140011646  mov     edx, 3Bh ; ';'
0x14001164b  mov     rcx, [rcx+10h]
0x14001164f  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011656  mov     r9d, ebx
0x140011659  call    WPP_SF_d
0x14001165e  jmp     short loc_140011691
0x140011660  mov     rcx, cs:WPP_GLOBAL_Control
0x140011667  lea     rax, WPP_GLOBAL_Control
0x14001166e  cmp     rcx, rax
0x140011671  jz      short loc_14001168C
0x140011673  test    byte ptr [rcx+1Ch], 1
0x140011677  jz      short loc_14001168C
0x140011679  mov     rcx, [rcx+10h]
0x14001167d  mov     [rsp+0A0h+var_78], rdx
0x140011682  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x140011687  call    WPP_SF_DDq
0x14001168c  mov     ebx, 80004005h
0x140011691  mov     rcx, [rbp+57h+lpBuffer]; void *
0x140011695  lea     rax, [rbp+57h+var_50]
0x140011699  cmp     rcx, rax
0x14001169c  jz      short loc_1400116AA
0x14001169e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400116a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400116aa  mov     eax, ebx
0x1400116ac  jmp     short loc_1400116FA
0x1400116ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116b5  lea     rax, WPP_GLOBAL_Control
0x1400116bc  cmp     rcx, rax
0x1400116bf  jz      short loc_1400116F5
0x1400116c1  test    byte ptr [rcx+1Ch], 1
0x1400116c5  jz      short loc_1400116F5
0x1400116c7  mov     rcx, [rcx+10h]
0x1400116cb  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400116d2  mov     edx, 39h ; '9'
0x1400116d7  call    WPP_SF_
0x1400116dc  mov     rcx, [rbp+57h+lpBuffer]; void *
0x1400116e0  lea     rax, [rbp+57h+var_50]
0x1400116e4  cmp     rcx, rax
0x1400116e7  jz      short loc_1400116F5
0x1400116e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400116f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400116f5  mov     eax, 80070057h
0x1400116fa  mov     rbx, [rsp+0A0h+arg_8]
0x140011702  add     rsp, 90h
0x140011709  pop     rdi
0x14001170a  pop     rsi
0x14001170b  pop     rbp
0x14001170c  retn
```
