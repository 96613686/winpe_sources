# CreateMiniportDevices

- ea: `0x180005d50`
- end: `0x18000620c`
- name: `CreateMiniportDevices`
- size: `1212`
- prototype: `__int64 __fastcall(int, unsigned int, char, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006214`

## callees

- `0x180005d50`
- `0x180006214`
- `0x180006670`
- `0x18000692c`
- `0x18001bcba`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005fc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005fc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006042`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000609d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000609d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005da4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006172`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005da4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006172`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000602d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000602d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000608a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000608a`

## pseudocode

```c
__int64 __fastcall CreateMiniportDevices(int a1, unsigned int a2, char a3, _QWORD *a4)
{
  HANDLE ProcessHeap; // rax
  signed int v7; // ebx
  __int16 MiniportsEnabledRegistry; // cx
  __int64 i; // r15
  const wchar_t *v10; // rax
  _QWORD *v11; // rdi
  signed int v12; // eax
  DWORD v13; // eax
  signed int LastError; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v20; // [rsp+40h] [rbp-59h] BYREF
  __int64 v21; // [rsp+48h] [rbp-51h] BYREF
  HANDLE hHandle[2]; // [rsp+50h] [rbp-49h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-39h]
  int v24; // [rsp+70h] [rbp-29h] BYREF
  const wchar_t *v25; // [rsp+78h] [rbp-21h]
  const wchar_t *v26; // [rsp+80h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-1h]
  __int16 v28; // [rsp+100h] [rbp+67h]

  memset_0(&v24, 0, 0x48u);
  ProcessHeap = GetProcessHeap();
  v20 = HeapAlloc(ProcessHeap, 8u, 8LL * (a2 + 1));
  if ( !v20 )
  {
    v7 = -2147024882;
    goto LABEL_64;
  }
  v7 = 0;
  v24 = 72;
  v27 = 8;
  MiniportsEnabledRegistry = GetMiniportsEnabledRegistry();
  v28 = MiniportsEnabledRegistry;
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    if ( !a1 )
      goto LABEL_63;
    v20[i] = 0;
    if ( (a1 & 1) != 0 )
    {
      a1 ^= 1u;
      if ( (MiniportsEnabledRegistry & 1) == 0 )
        continue;
      v25 = L"MS_AGILEVPNMINIPORT";
      v26 = L"ms_agilevpnminiport";
      goto LABEL_34;
    }
    if ( (a1 & 2) != 0 )
    {
      a1 ^= 2u;
      if ( (MiniportsEnabledRegistry & 2) == 0 )
        continue;
      v25 = L"MS_L2TPMINIPORT";
      v26 = L"ms_l2tpminiport";
      goto LABEL_34;
    }
    if ( (a1 & 4) != 0 )
    {
      a1 ^= 4u;
      if ( (MiniportsEnabledRegistry & 4) == 0 )
        continue;
      v25 = L"MS_PPTPMINIPORT";
      v10 = L"ms_pptpminiport";
LABEL_33:
      v26 = v10;
      goto LABEL_34;
    }
    if ( (a1 & 0x10) != 0 )
    {
      a1 ^= 0x10u;
      if ( (MiniportsEnabledRegistry & 0x10) == 0 )
        continue;
      v25 = L"MS_SSTPMINIPORT";
      v26 = L"ms_sstpminiport";
LABEL_34:
      v11 = v20;
      v21 = 0;
      *(_OWORD *)hHandle = 0;
      *(_OWORD *)lpMem = 0;
      hHandle[0] = CreateEventW(0, 0, 0, 0);
      if ( hHandle[0] )
      {
        v7 = SwDeviceCreate(
               L"MSRRAS",
               L"SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}",
               &v24,
               0,
               0,
               &RrasSwDeviceCreateCallback,
               hHandle,
               &v21);
        if ( v7 < 0 )
          goto LABEL_46;
        v13 = WaitForSingleObject(hHandle[0], 0x7530u);
        if ( !v13 )
          goto LABEL_43;
        if ( v13 == 258 )
        {
          v7 = -2147023436;
          goto LABEL_46;
        }
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 < 0 )
        {
LABEL_46:
          if ( v21 )
            SwDeviceClose();
        }
        else
        {
LABEL_43:
          if ( SLODWORD(lpMem[0]) < 0 )
          {
            v7 = (signed int)lpMem[0];
            goto LABEL_45;
          }
          v16 = GetProcessHeap();
          v17 = HeapAlloc(v16, 8u, 0x10u);
          if ( !v17 )
          {
            v7 = -2147024882;
            goto LABEL_46;
          }
          v17[1] = v21;
          *v17 = lpMem[1];
          lpMem[1] = 0;
          v11[i] = v17;
        }
      }
      else
      {
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
LABEL_45:
        if ( v7 < 0 )
          goto LABEL_46;
      }
      if ( hHandle[0] )
        CloseHandle(hHandle[0]);
      if ( lpMem[1] )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, lpMem[1]);
      }
      if ( v7 )
        goto LABEL_64;
      if ( (a3 & 4) != 0 )
      {
        v7 = WaitForInterface(*(_QWORD *)v20[i]);
        if ( v7 )
          goto LABEL_64;
      }
      MiniportsEnabledRegistry = v28;
      continue;
    }
    if ( (a1 & 8) != 0 )
    {
      a1 ^= 8u;
      if ( (MiniportsEnabledRegistry & 8) == 0 )
        continue;
      v25 = L"MS_PPPOEMINIPORT";
      v10 = L"ms_pppoeminiport";
      goto LABEL_33;
    }
    if ( (a1 & 0x100) != 0 )
    {
      a1 ^= 0x100u;
      if ( (MiniportsEnabledRegistry & 0x100) == 0 )
        continue;
      v25 = L"MS_GREMINIPORT";
      v10 = L"ms_greminiport";
      goto LABEL_33;
    }
    if ( (a1 & 0x20) != 0 )
    {
      a1 ^= 0x20u;
      if ( (MiniportsEnabledRegistry & 0x20) == 0 )
        continue;
      v25 = L"MS_NDISWANIP";
      v10 = L"ms_ndiswanip";
      goto LABEL_33;
    }
    if ( (a1 & 0x40) != 0 )
    {
      a1 ^= 0x40u;
      if ( (MiniportsEnabledRegistry & 0x40) == 0 )
        continue;
      v25 = L"MS_NDISWANIPV6";
      v10 = L"ms_ndiswanipv6";
      goto LABEL_33;
    }
    if ( (a1 & 0x80u) == 0 )
      goto LABEL_62;
    a1 ^= 0x80u;
    if ( (MiniportsEnabledRegistry & 0x80u) != 0 )
    {
      v25 = L"MS_NDISWANBH";
      v10 = L"ms_ndiswanbh";
      goto LABEL_33;
    }
  }
  if ( a1 )
  {
LABEL_62:
    v7 = -2147024809;
    goto LABEL_64;
  }
LABEL_63:
  v18 = v20;
  v20 = 0;
  *a4 = v18;
LABEL_64:
  ConfigureMiniports(0, 2u, &v20, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp-8+arg_18], r9
0x180005d55  mov     [rsp-8+arg_10], r8d
0x180005d5a  push    rbp
0x180005d5b  push    rbx
0x180005d5c  push    r13
0x180005d5e  push    r14
0x180005d60  lea     rbp, [rsp-3Fh]
0x180005d65  sub     rsp, 0D8h
0x180005d6c  mov     r13d, edx
0x180005d6f  mov     r14d, ecx
0x180005d72  xor     edx, edx; Val
0x180005d74  lea     rcx, [rbp+57h+var_80]; void *
0x180005d78  mov     r8d, 48h ; 'H'; Size
0x180005d7e  call    memset_0
0x180005d83  lea     ebx, [r13+1]
0x180005d87  mov     [rbp+57h+var_B0], 0
0x180005d8f  shl     rbx, 3
0x180005d93  call    cs:__imp_GetProcessHeap
0x180005d99  mov     r8, rbx; dwBytes
0x180005d9c  mov     edx, 8; dwFlags
0x180005da1  mov     rcx, rax; hHeap
0x180005da4  call    cs:__imp_HeapAlloc
0x180005daa  mov     [rbp+57h+var_B0], rax
0x180005dae  test    rax, rax
0x180005db1  jnz     short loc_180005DBD
0x180005db3  mov     ebx, 8007000Eh
0x180005db8  jmp     loc_1800061E9
0x180005dbd  mov     [rsp+0F0h+arg_8], rsi
0x180005dc5  xor     ebx, ebx
0x180005dc7  mov     [rsp+0F0h+var_20], rdi
0x180005dcf  mov     [rsp+0F0h+var_30], r15
0x180005dd7  mov     [rbp+57h+var_80], 48h ; 'H'
0x180005dde  mov     [rbp+57h+var_58], 8
0x180005de5  call    GetMiniportsEnabledRegistry
0x180005dea  mov     ecx, eax
0x180005dec  mov     [rbp+57h+arg_0], eax
0x180005def  xor     r15d, r15d
0x180005df2  mov     [rsp+0F0h+var_28], r12
0x180005dfa  lea     rdx, c_szInstId_MS_AgileVpnMiniport; "MS_AGILEVPNMINIPORT"
0x180005e01  lea     r8, c_szHwId_MS_AgileVpnMiniport; "ms_agilevpnminiport"
0x180005e08  lea     r11, c_szInstId_MS_L2tpMiniport; "MS_L2TPMINIPORT"
0x180005e0f  lea     r9, c_szInstId_MS_SstpMiniport; "MS_SSTPMINIPORT"
0x180005e16  lea     r10, c_szHwId_MS_SstpMiniport; "ms_sstpminiport"
0x180005e1d  lea     rdi, c_szHwId_MS_L2tpMiniport; "ms_l2tpminiport"
0x180005e24  lea     rsi, c_szInstId_MS_PptpMiniport; "MS_PPTPMINIPORT"
0x180005e2b  nop     dword ptr [rax+rax+00h]
0x180005e30  cmp     r15d, r13d
0x180005e33  jnb     loc_1800061AA
0x180005e39  test    r14d, r14d
0x180005e3c  jz      loc_1800061B6
0x180005e42  mov     rax, [rbp+57h+var_B0]
0x180005e46  lea     r12, ds:0[r15*8]
0x180005e4e  mov     qword ptr [r12+rax], 0
0x180005e56  test    r14b, 1
0x180005e5a  jz      short loc_180005E76
0x180005e5c  xor     r14d, 1
0x180005e60  test    cl, 1
0x180005e63  jz      loc_18000614C
0x180005e69  mov     [rbp+57h+var_78], rdx
0x180005e6d  mov     [rbp+57h+var_70], r8
0x180005e71  jmp     loc_180005FA7
0x180005e76  test    r14b, 2
0x180005e7a  jz      short loc_180005E96
0x180005e7c  xor     r14d, 2
0x180005e80  test    cl, 2
0x180005e83  jz      loc_18000614C
0x180005e89  mov     [rbp+57h+var_78], r11
0x180005e8d  mov     [rbp+57h+var_70], rdi
0x180005e91  jmp     loc_180005FA7
0x180005e96  test    r14b, 4
0x180005e9a  jz      short loc_180005EB9
0x180005e9c  xor     r14d, 4
0x180005ea0  test    cl, 4
0x180005ea3  jz      loc_18000614C
0x180005ea9  mov     [rbp+57h+var_78], rsi
0x180005ead  lea     rax, c_szHwId_MS_PptpMiniport; "ms_pptpminiport"
0x180005eb4  jmp     loc_180005FA3
0x180005eb9  test    r14b, 10h
0x180005ebd  jz      short loc_180005ED9
0x180005ebf  xor     r14d, 10h
0x180005ec3  test    cl, 10h
0x180005ec6  jz      loc_18000614C
0x180005ecc  mov     [rbp+57h+var_78], r9
0x180005ed0  mov     [rbp+57h+var_70], r10
0x180005ed4  jmp     loc_180005FA7
0x180005ed9  test    r14b, 8
0x180005edd  jz      short loc_180005F03
0x180005edf  xor     r14d, 8
0x180005ee3  test    cl, 8
0x180005ee6  jz      loc_18000614C
0x180005eec  lea     rax, c_szInstId_MS_PppoeMiniport; "MS_PPPOEMINIPORT"
0x180005ef3  mov     [rbp+57h+var_78], rax
0x180005ef7  lea     rax, c_szHwId_MS_PppoeMiniport; "ms_pppoeminiport"
0x180005efe  jmp     loc_180005FA3
0x180005f03  bt      r14d, 8
0x180005f08  jnb     short loc_180005F2D
0x180005f0a  btc     r14d, 8
0x180005f0f  bt      ecx, 8
0x180005f13  jnb     loc_18000614C
0x180005f19  lea     rax, c_szInstId_MS_GreMiniport; "MS_GREMINIPORT"
0x180005f20  mov     [rbp+57h+var_78], rax
0x180005f24  lea     rax, c_szHwId_MS_GreMiniport; "ms_greminiport"
0x180005f2b  jmp     short loc_180005FA3
0x180005f2d  test    r14b, 20h
0x180005f31  jz      short loc_180005F54
0x180005f33  xor     r14d, 20h
0x180005f37  test    cl, 20h
0x180005f3a  jz      loc_18000614C
0x180005f40  lea     rax, c_szInstId_MS_NdisWanIp; "MS_NDISWANIP"
0x180005f47  mov     [rbp+57h+var_78], rax
0x180005f4b  lea     rax, c_szHwId_MS_NdisWanIp; "ms_ndiswanip"
0x180005f52  jmp     short loc_180005FA3
0x180005f54  test    r14b, 40h
0x180005f58  jz      short loc_180005F7B
0x180005f5a  xor     r14d, 40h
0x180005f5e  test    cl, 40h
0x180005f61  jz      loc_18000614C
0x180005f67  lea     rax, c_szInstId_MS_NdisWanIpv6; "MS_NDISWANIPV6"
0x180005f6e  mov     [rbp+57h+var_78], rax
0x180005f72  lea     rax, c_szHwId_MS_NdisWanIpv6; "ms_ndiswanipv6"
0x180005f79  jmp     short loc_180005FA3
0x180005f7b  test    r14b, r14b
0x180005f7e  jns     loc_1800061AF
0x180005f84  btc     r14d, 7
0x180005f89  test    cl, cl
0x180005f8b  jns     loc_18000614C
0x180005f91  lea     rax, c_szInstId_MS_NdisWanBh; "MS_NDISWANBH"
0x180005f98  mov     [rbp+57h+var_78], rax
0x180005f9c  lea     rax, c_szHwId_MS_NdisWanBh; "ms_ndiswanbh"
0x180005fa3  mov     [rbp+57h+var_70], rax
0x180005fa7  mov     rdi, [rbp+57h+var_B0]
0x180005fab  xorps   xmm0, xmm0
0x180005fae  xor     ebx, ebx
0x180005fb0  xor     r9d, r9d; lpName
0x180005fb3  xor     r8d, r8d; bInitialState
0x180005fb6  mov     [rbp+57h+var_A8], rbx
0x180005fba  xor     edx, edx; bManualReset
0x180005fbc  xor     ecx, ecx; lpEventAttributes
0x180005fbe  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x180005fc2  mov     esi, ebx
0x180005fc4  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x180005fc8  call    cs:__imp_CreateEventW
0x180005fce  mov     [rbp+57h+hHandle], rax
0x180005fd2  test    rax, rax
0x180005fd5  jnz     short loc_180005FF5
0x180005fd7  call    cs:__imp_GetLastError
0x180005fdd  mov     ebx, eax
0x180005fdf  test    eax, eax
0x180005fe1  jle     loc_18000607D
0x180005fe7  movzx   ebx, ax
0x180005fea  or      ebx, 80070000h
0x180005ff0  jmp     loc_18000607D
0x180005ff5  lea     rax, [rbp+57h+var_A8]
0x180005ff9  xor     r9d, r9d
0x180005ffc  mov     [rsp+0F0h+var_B8], rax
0x180006001  lea     r8, [rbp+57h+var_80]
0x180006005  lea     rax, [rbp+57h+hHandle]
0x180006009  mov     [rsp+0F0h+var_C0], rax
0x18000600e  lea     rdx, aSwdMsrras5e259; "SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8"...
0x180006015  lea     rax, RrasSwDeviceCreateCallback
0x18000601c  mov     [rsp+0F0h+var_C8], rax
0x180006021  lea     rcx, aMsrras; "MSRRAS"
0x180006028  mov     [rsp+0F0h+var_D0], rbx
0x18000602d  call    cs:__imp_SwDeviceCreate
0x180006033  mov     ebx, eax
0x180006035  test    eax, eax
0x180006037  js      short loc_180006081
0x180006039  mov     rcx, [rbp+57h+hHandle]; hHandle
0x18000603d  mov     edx, 7530h; dwMilliseconds
0x180006042  call    cs:__imp_WaitForSingleObject
0x180006048  test    eax, eax
0x18000604a  jz      short loc_180006070
0x18000604c  cmp     eax, 102h
0x180006051  jz      loc_180006154
0x180006057  call    cs:__imp_GetLastError
0x18000605d  mov     ebx, eax
0x18000605f  test    eax, eax
0x180006061  jle     short loc_18000606C
0x180006063  movzx   ebx, ax
0x180006066  or      ebx, 80070000h
0x18000606c  test    ebx, ebx
0x18000606e  js      short loc_180006081
0x180006070  mov     eax, dword ptr [rbp+57h+lpMem]
0x180006073  test    eax, eax
0x180006075  jns     loc_18000615E
0x18000607b  mov     ebx, eax
0x18000607d  test    ebx, ebx
0x18000607f  jns     short loc_1800060C5
0x180006081  mov     rcx, [rbp+57h+var_A8]
0x180006085  test    rcx, rcx
0x180006088  jz      short loc_180006090
0x18000608a  call    cs:__imp_SwDeviceClose
0x180006090  test    rsi, rsi
0x180006093  jz      short loc_1800060C5
0x180006095  mov     rdi, [rsi]
0x180006098  test    rdi, rdi
0x18000609b  jz      short loc_1800060B1
0x18000609d  call    cs:__imp_GetProcessHeap
0x1800060a3  mov     r8, rdi; lpMem
0x1800060a6  xor     edx, edx; dwFlags
0x1800060a8  mov     rcx, rax; hHeap
0x1800060ab  call    cs:__imp_HeapFree
0x1800060b1  call    cs:__imp_GetProcessHeap
0x1800060b7  mov     r8, rsi; lpMem
0x1800060ba  xor     edx, edx; dwFlags
0x1800060bc  mov     rcx, rax; hHeap
0x1800060bf  call    cs:__imp_HeapFree
0x1800060c5  mov     rcx, [rbp+57h+hHandle]; hObject
0x1800060c9  test    rcx, rcx
0x1800060cc  jz      short loc_1800060D4
0x1800060ce  call    cs:__imp_CloseHandle
0x1800060d4  cmp     [rbp+57h+lpMem+8], 0
0x1800060d9  jz      short loc_1800060F0
0x1800060db  call    cs:__imp_GetProcessHeap
0x1800060e1  mov     r8, [rbp+57h+lpMem+8]; lpMem
0x1800060e5  xor     edx, edx; dwFlags
0x1800060e7  mov     rcx, rax; hHeap
0x1800060ea  call    cs:__imp_HeapFree
0x1800060f0  test    ebx, ebx
0x1800060f2  jnz     loc_1800061C9
0x1800060f8  test    byte ptr [rbp+57h+arg_10], 4
0x1800060fc  jz      short loc_180006118
0x1800060fe  mov     rax, [rbp+57h+var_B0]
0x180006102  mov     rcx, [r12+rax]
0x180006106  mov     rcx, [rcx]
0x180006109  call    WaitForInterface
0x18000610e  mov     ebx, eax
0x180006110  test    eax, eax
0x180006112  jnz     loc_1800061C9
0x180006118  mov     ecx, [rbp+57h+arg_0]
0x18000611b  lea     rsi, c_szInstId_MS_PptpMiniport; "MS_PPTPMINIPORT"
0x180006122  lea     rdi, c_szHwId_MS_L2tpMiniport; "ms_l2tpminiport"
0x180006129  lea     r11, c_szInstId_MS_L2tpMiniport; "MS_L2TPMINIPORT"
0x180006130  lea     r10, c_szHwId_MS_SstpMiniport; "ms_sstpminiport"
0x180006137  lea     r9, c_szInstId_MS_SstpMiniport; "MS_SSTPMINIPORT"
0x18000613e  lea     r8, c_szHwId_MS_AgileVpnMiniport; "ms_agilevpnminiport"
0x180006145  lea     rdx, c_szInstId_MS_AgileVpnMiniport; "MS_AGILEVPNMINIPORT"
0x18000614c  inc     r15d
0x18000614f  jmp     loc_180005E30
0x180006154  mov     ebx, 800705B4h
0x180006159  jmp     loc_180006081
0x18000615e  call    cs:__imp_GetProcessHeap
0x180006164  mov     edx, 8; dwFlags
0x180006169  mov     r8d, 10h; dwBytes
0x18000616f  mov     rcx, rax; hHeap
0x180006172  call    cs:__imp_HeapAlloc
0x180006178  mov     rsi, rax
0x18000617b  test    rax, rax
0x18000617e  jnz     short loc_18000618A
0x180006180  mov     ebx, 8007000Eh
0x180006185  jmp     loc_180006081
0x18000618a  mov     rax, [rbp+57h+var_A8]
0x18000618e  mov     [rsi+8], rax
0x180006192  mov     rax, [rbp+57h+lpMem+8]
0x180006196  mov     [rsi], rax
0x180006199  mov     [rbp+57h+lpMem+8], 0
0x1800061a1  mov     [rdi+r12], rsi
0x1800061a5  jmp     loc_1800060C5
0x1800061aa  test    r14d, r14d
0x1800061ad  jz      short loc_1800061B6
0x1800061af  mov     ebx, 80070057h
0x1800061b4  jmp     short loc_1800061C9
0x1800061b6  mov     rax, [rbp+57h+var_B0]
0x1800061ba  mov     rcx, [rbp+57h+arg_18]
0x1800061be  mov     [rbp+57h+var_B0], 0
0x1800061c6  mov     [rcx], rax
0x1800061c9  mov     r12, [rsp+0F0h+var_28]
0x1800061d1  mov     rdi, [rsp+0F0h+var_20]
0x1800061d9  mov     rsi, [rsp+0F0h+arg_8]
0x1800061e1  mov     r15, [rsp+0F0h+var_30]
0x1800061e9  xor     r9d, r9d
0x1800061ec  lea     r8, [rbp+57h+var_B0]
0x1800061f0  mov     edx, 2
0x1800061f5  xor     ecx, ecx
0x1800061f7  call    ConfigureMiniports
0x1800061fc  mov     eax, ebx
0x1800061fe  add     rsp, 0D8h
0x180006205  pop     r14
0x180006207  pop     r13
0x180006209  pop     rbx
0x18000620a  pop     rbp
0x18000620b  retn
```
