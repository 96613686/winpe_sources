# WerpGetExtendedDiagData

- ea: `0x180068080`
- end: `0x18006831a`
- name: `WerpGetExtendedDiagData`
- size: `666`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x180068080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068217`
- `ntdll!NtQueryInformationProcess` at `0x1800680e1`
- `ntdll!NtQueryInformationProcess` at `0x1800680e1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180068149`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006820d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180068149`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006820d`

## pseudocode

```c
__int64 __fastcall WerpGetExtendedDiagData(HANDLE hProcess, _QWORD *a2, _DWORD *a3)
{
  NTSTATUS InformationProcess; // ebx
  unsigned int v7; // ebx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // eax
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  int v15; // eax
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  _OWORD ProcessInformation[3]; // [rsp+30h] [rbp-30h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+98h] [rbp+38h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+40h] BYREF
  LPCVOID Buffer; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v20 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    v7 = InformationProcess | 0x10000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v7;
    v9 = 175;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, v7);
    return v7;
  }
  if ( !ReadProcessMemory(
          hProcess,
          (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 40LL),
          &Buffer,
          8u,
          &NumberOfBytesRead) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v7;
    v9 = 176;
    goto LABEL_5;
  }
  if ( NumberOfBytesRead != 8 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return 2147942699LL;
    v13 = 177;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, 2147942699LL);
    return 2147942699LL;
  }
  if ( Buffer )
  {
    if ( !ReadProcessMemory(hProcess, Buffer, &v20, 8u, &NumberOfBytesRead) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v7;
      v9 = 179;
      goto LABEL_5;
    }
    if ( NumberOfBytesRead != 8 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147942699LL;
      v13 = 180;
      goto LABEL_32;
    }
    v15 = v20;
    if ( (unsigned int)v20 >= 8 )
    {
      if ( HIDWORD(v20) == 1464157250 )
      {
        *a2 = Buffer;
        *a3 = v15;
        return 0;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147943705LL;
      v17 = 183;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147943705LL;
      v17 = 182;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, 2147943705LL);
    return 2147943705LL;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
  return 2147943568LL;
}

```

## disassembly

```asm
0x180068080  push    rbp
0x180068082  push    rbx
0x180068083  push    rsi
0x180068084  push    rdi
0x180068085  push    r14
0x180068087  mov     rbp, rsp
0x18006808a  sub     rsp, 60h
0x18006808e  xorps   xmm0, xmm0
0x180068091  mov     qword ptr [rdx], 0
0x180068098  mov     dword ptr [r8], 0
0x18006809f  mov     rsi, r8
0x1800680a2  mov     r14, rdx
0x1800680a5  mov     [rbp+NumberOfBytesRead], 0
0x1800680ad  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x1800680b1  mov     [rbp+Buffer], 0
0x1800680b9  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800680bf  mov     [rbp+arg_10], 0
0x1800680c7  xor     edx, edx; ProcessInformationClass
0x1800680c9  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x1800680d2  mov     rdi, rcx
0x1800680d5  movups  [rbp+ProcessInformation], xmm0
0x1800680d9  movups  [rbp+var_20], xmm0
0x1800680dd  movups  [rbp+var_10], xmm0
0x1800680e1  call    cs:__imp_NtQueryInformationProcess
0x1800680e7  mov     ebx, eax
0x1800680e9  test    eax, eax
0x1800680eb  jns     short loc_180068129
0x1800680ed  bts     ebx, 1Ch
0x1800680f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800680f8  lea     rdx, WPP_GLOBAL_Control
0x1800680ff  cmp     rcx, rdx
0x180068102  jz      short loc_180068122
0x180068104  test    byte ptr [rcx+1Ch], 1
0x180068108  jz      short loc_180068122
0x18006810a  mov     edx, 0AFh
0x18006810f  mov     rcx, [rcx+10h]
0x180068113  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006811a  mov     r9d, ebx
0x18006811d  call    WPP_SF_d
0x180068122  mov     eax, ebx
0x180068124  jmp     loc_18006830F
0x180068129  mov     rdx, qword ptr [rbp+ProcessInformation+8]
0x18006812d  lea     rax, [rbp+NumberOfBytesRead]
0x180068131  mov     ebx, 8
0x180068136  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006813b  add     rdx, 28h ; '('; lpBaseAddress
0x18006813f  lea     r8, [rbp+Buffer]; lpBuffer
0x180068143  mov     r9d, ebx; nSize
0x180068146  mov     rcx, rdi; hProcess
0x180068149  call    cs:__imp_ReadProcessMemory
0x18006814f  test    eax, eax
0x180068151  jnz     short loc_180068188
0x180068153  call    cs:__imp_GetLastError
0x180068159  mov     ebx, eax
0x18006815b  test    eax, eax
0x18006815d  jle     short loc_180068168
0x18006815f  movzx   ebx, ax
0x180068162  or      ebx, 80070000h
0x180068168  mov     rcx, cs:WPP_GLOBAL_Control
0x18006816f  lea     rdx, WPP_GLOBAL_Control
0x180068176  cmp     rcx, rdx
0x180068179  jz      short loc_180068122
0x18006817b  test    byte ptr [rcx+1Ch], 1
0x18006817f  jz      short loc_180068122
0x180068181  mov     edx, 0B0h
0x180068186  jmp     short loc_18006810F
0x180068188  cmp     [rbp+NumberOfBytesRead], rbx
0x18006818c  jz      short loc_1800681B9
0x18006818e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068195  lea     rdx, WPP_GLOBAL_Control
0x18006819c  cmp     rcx, rdx
0x18006819f  jz      loc_180068291
0x1800681a5  test    byte ptr [rcx+1Ch], 1
0x1800681a9  jz      loc_180068291
0x1800681af  mov     edx, 0B1h
0x1800681b4  jmp     loc_18006827B
0x1800681b9  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x1800681bd  test    rdx, rdx
0x1800681c0  jnz     short loc_1800681FA
0x1800681c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800681c9  lea     rdx, WPP_GLOBAL_Control
0x1800681d0  cmp     rcx, rdx
0x1800681d3  jz      short loc_1800681F0
0x1800681d5  test    byte ptr [rcx+1Ch], 4
0x1800681d9  jz      short loc_1800681F0
0x1800681db  mov     rcx, [rcx+10h]
0x1800681df  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800681e6  mov     edx, 0B2h
0x1800681eb  call    WPP_SF_
0x1800681f0  mov     eax, 80070490h
0x1800681f5  jmp     loc_18006830F
0x1800681fa  lea     rax, [rbp+NumberOfBytesRead]
0x1800681fe  mov     r9, rbx; nSize
0x180068201  lea     r8, [rbp+arg_10]; lpBuffer
0x180068205  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006820a  mov     rcx, rdi; hProcess
0x18006820d  call    cs:__imp_ReadProcessMemory
0x180068213  test    eax, eax
0x180068215  jnz     short loc_180068257
0x180068217  call    cs:__imp_GetLastError
0x18006821d  mov     ebx, eax
0x18006821f  test    eax, eax
0x180068221  jle     short loc_18006822C
0x180068223  movzx   ebx, ax
0x180068226  or      ebx, 80070000h
0x18006822c  mov     rcx, cs:WPP_GLOBAL_Control
0x180068233  lea     rdx, WPP_GLOBAL_Control
0x18006823a  cmp     rcx, rdx
0x18006823d  jz      loc_180068122
0x180068243  test    byte ptr [rcx+1Ch], 1
0x180068247  jz      loc_180068122
0x18006824d  mov     edx, 0B3h
0x180068252  jmp     loc_18006810F
0x180068257  cmp     [rbp+NumberOfBytesRead], rbx
0x18006825b  jz      short loc_180068298
0x18006825d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068264  lea     rdx, WPP_GLOBAL_Control
0x18006826b  cmp     rcx, rdx
0x18006826e  jz      short loc_180068291
0x180068270  test    byte ptr [rcx+1Ch], 1
0x180068274  jz      short loc_180068291
0x180068276  mov     edx, 0B4h
0x18006827b  mov     rcx, [rcx+10h]
0x18006827f  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180068286  mov     r9d, 8007012Bh
0x18006828c  call    WPP_SF_d
0x180068291  mov     eax, 8007012Bh
0x180068296  jmp     short loc_18006830F
0x180068298  mov     rax, [rbp+arg_10]
0x18006829c  cmp     eax, ebx
0x18006829e  jnb     short loc_1800682C0
0x1800682a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682a7  lea     rdx, WPP_GLOBAL_Control
0x1800682ae  cmp     rcx, rdx
0x1800682b1  jz      short loc_1800682FD
0x1800682b3  test    byte ptr [rcx+1Ch], 1
0x1800682b7  jz      short loc_1800682FD
0x1800682b9  mov     edx, 0B6h
0x1800682be  jmp     short loc_1800682E7
0x1800682c0  cmp     dword ptr [rbp+arg_10+4], 57454442h
0x1800682c7  jz      short loc_180068304
0x1800682c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682d0  lea     rdx, WPP_GLOBAL_Control
0x1800682d7  cmp     rcx, rdx
0x1800682da  jz      short loc_1800682FD
0x1800682dc  test    byte ptr [rcx+1Ch], 1
0x1800682e0  jz      short loc_1800682FD
0x1800682e2  mov     edx, 0B7h
0x1800682e7  mov     rcx, [rcx+10h]
0x1800682eb  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800682f2  mov     r9d, 80070519h
0x1800682f8  call    WPP_SF_d
0x1800682fd  mov     eax, 80070519h
0x180068302  jmp     short loc_18006830F
0x180068304  mov     rcx, [rbp+Buffer]
0x180068308  mov     [r14], rcx
0x18006830b  mov     [rsi], eax
0x18006830d  xor     eax, eax
0x18006830f  add     rsp, 60h
0x180068313  pop     r14
0x180068315  pop     rdi
0x180068316  pop     rsi
0x180068317  pop     rbx
0x180068318  pop     rbp
0x180068319  retn
```
