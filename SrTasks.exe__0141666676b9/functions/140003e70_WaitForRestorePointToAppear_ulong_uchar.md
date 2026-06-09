# WaitForRestorePointToAppear(ulong,uchar *)

- ea: `0x140003e70`
- end: `0x1400041e6`
- name: `?WaitForRestorePointToAppear@@YAJKPEAE@Z`
- size: `886`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000312c`
- `0x140004a70`

## callees

- `0x140002e1c`
- `0x140003e70`
- `0x140005444`
- `0x1400054f4`
- `0x140005554`
- `0x140005ac0`
- `0x14000e324`
- `0x14000e41c`
- `0x140011010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140003f6d`
- `ADVAPI32!RegOpenKeyExW` at `0x140003f6d`
- `ADVAPI32!RegCloseKey` at `0x140003fd7`
- `ADVAPI32!RegCloseKey` at `0x140004028`
- `ADVAPI32!RegCloseKey` at `0x140003fd7`
- `ADVAPI32!RegCloseKey` at `0x140004028`
- `KERNEL32!Sleep` at `0x14000415f`
- `KERNEL32!Sleep` at `0x14000415f`
- `KERNEL32!GetTickCount64` at `0x14000407b`
- `KERNEL32!GetTickCount64` at `0x140004145`
- `KERNEL32!GetTickCount64` at `0x14000407b`
- `KERNEL32!GetTickCount64` at `0x140004145`
- `SRCORE!SrFreeRpPropArray` at `0x140004090`
- `SRCORE!SrFreeRpPropArray` at `0x1400041a1`
- `SRCORE!SrFreeRpPropArray` at `0x140004090`
- `SRCORE!SrFreeRpPropArray` at `0x1400041a1`
- `ole32!CoCreateInstance` at `0x14000405c`
- `ole32!CoCreateInstance` at `0x14000405c`

## pseudocode

```c
__int64 __fastcall WaitForRestorePointToAppear(unsigned int a1, unsigned __int8 *a2)
{
  unsigned __int64 v4; // rdi
  int v5; // r9d
  int v6; // eax
  ULONGLONG TickCount64; // rsi
  __int64 v8; // r8
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  __int64 v13; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  HRESULT v16; // [rsp+48h] [rbp-41h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-3Dh]
  __int16 v18; // [rsp+4Eh] [rbp-3Bh]
  _BYTE v19[64]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v20; // [rsp+100h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "WaitForRestorePointToAppear", 0x36Au, 1u);
  ppv = 0;
  *a2 = 0;
  v20 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v19, "GetTimeToWaitForRestorePointToAppear", 0x349u, 1u);
  hKey = 0;
  v4 = 5;
  v14 = 5;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
         0,
         0x20019u,
         &hKey) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore");
    goto LABEL_19;
  }
  v6 = SxRegReadULONGLONG(hKey, L"WaitForRestorePointToAppear", &v14, v5);
  if ( v6 < 0 || v6 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)L"WaitForRestorePointToAppear",
        v6);
LABEL_19:
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    v4 = v14;
LABEL_21:
    hKey = 0;
    goto LABEL_22;
  }
  v4 = v14;
LABEL_22:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v19);
  v16 = CoCreateInstance(&CLSID_SrControl, 0, 1u, &IID_ISrControl, &ppv);
  if ( v16 < 0 )
  {
    v18 = 888;
    goto LABEL_44;
  }
  v17 = 888;
  TickCount64 = GetTickCount64();
  while ( 1 )
  {
    SrFreeRpPropArray(v20, &v13);
    v20 = 0;
    v13 = 0;
    v16 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, &v20, &v13);
    if ( v16 < 0 )
    {
      v18 = 899;
      goto LABEL_44;
    }
    v17 = 899;
    v9 = 0;
    if ( !v20 )
      goto LABEL_33;
    while ( *(_DWORD *)(152LL * v9 + v13 + 24) != a1 )
    {
      if ( ++v9 >= v20 )
        goto LABEL_33;
    }
    *a2 = 1;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v8, a1);
LABEL_33:
      v10 = WPP_GLOBAL_Control;
    }
    if ( v9 != v20 )
      goto LABEL_44;
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x8000000) != 0 )
      WPP_SF_L(v10[2], 54, v8, a1);
    if ( GetTickCount64() - TickCount64 >= 60000 * v4 )
      break;
    Sleep(0x2710u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
LABEL_44:
  SrFreeRpPropArray(v20, &v13);
  v11 = v16;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v11;
}

```

## disassembly

```asm
0x140003e70  mov     [rsp-8+arg_0], rbx
0x140003e75  mov     [rsp-8+arg_8], rsi
0x140003e7a  push    rbp
0x140003e7b  push    rdi
0x140003e7c  push    r13
0x140003e7e  push    r14
0x140003e80  push    r15
0x140003e82  lea     rbp, [rsp-37h]
0x140003e87  sub     rsp, 0C0h
0x140003e8e  mov     r15, rdx
0x140003e91  mov     r14d, ecx
0x140003e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e9b  lea     r13, WPP_GLOBAL_Control
0x140003ea2  lea     rsi, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140003ea9  mov     ebx, 20000000h
0x140003eae  cmp     rcx, r13
0x140003eb1  jz      short loc_140003EC9
0x140003eb3  test    [rcx+1Ch], ebx
0x140003eb6  jz      short loc_140003EC9
0x140003eb8  mov     rcx, [rcx+10h]
0x140003ebc  mov     edx, 34h ; '4'
0x140003ec1  mov     r8, rsi
0x140003ec4  call    WPP_SF_
0x140003ec9  mov     edi, 1
0x140003ece  lea     rdx, aWaitforrestore; "WaitForRestorePointToAppear"
0x140003ed5  mov     r9d, edi; unsigned __int16
0x140003ed8  lea     rcx, [rbp+57h+var_98]; this
0x140003edc  mov     r8d, 36Ah; unsigned __int16
0x140003ee2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003ee7  xor     eax, eax
0x140003ee9  mov     [rbp+57h+ppv], 0
0x140003ef1  mov     [r15], al
0x140003ef4  mov     [rbp+57h+arg_10], 0
0x140003efb  mov     [rbp+57h+var_B0], 0
0x140003f03  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f0a  cmp     rcx, r13
0x140003f0d  jz      short loc_140003F23
0x140003f0f  test    [rcx+1Ch], ebx
0x140003f12  jz      short loc_140003F23
0x140003f14  mov     rcx, [rcx+10h]
0x140003f18  lea     edx, [rdi+30h]
0x140003f1b  mov     r8, rsi
0x140003f1e  call    WPP_SF_
0x140003f23  mov     r9d, edi; unsigned __int16
0x140003f26  lea     rdx, aGettimetowaitf; "GetTimeToWaitForRestorePointToAppear"
0x140003f2d  mov     r8d, 349h; unsigned __int16
0x140003f33  lea     rcx, [rbp+57h+var_60]; this
0x140003f37  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003f3c  lea     rax, [rbp+57h+hKey]
0x140003f40  mov     [rbp+57h+hKey], 0
0x140003f48  mov     edi, 5
0x140003f4d  mov     [rsp+0E0h+phkResult], rax; phkResult
0x140003f52  mov     r9d, 20019h; samDesired
0x140003f58  mov     [rbp+57h+var_A8], rdi
0x140003f5c  xor     r8d, r8d; ulOptions
0x140003f5f  lea     rdx, c_wszRegistryKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003f66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003f6d  call    cs:__imp_RegOpenKeyExW
0x140003f73  test    eax, eax
0x140003f75  jz      short loc_140003FAC
0x140003f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f7e  cmp     rcx, r13
0x140003f81  jz      loc_14000401A
0x140003f87  test    dword ptr [rcx+1Ch], 4000000h
0x140003f8e  jz      loc_14000401A
0x140003f94  mov     rcx, [rcx+10h]
0x140003f98  lea     edx, [rdi+2Dh]
0x140003f9b  lea     r9, c_wszRegistryKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003fa2  mov     r8, rsi
0x140003fa5  call    WPP_SF_S
0x140003faa  jmp     short loc_14000401A
0x140003fac  mov     rcx, [rbp+57h+hKey]; hKey
0x140003fb0  lea     r8, [rbp+57h+var_A8]; unsigned __int64 *
0x140003fb4  lea     rdx, c_wszWaitForRestorePointToAppear; "WaitForRestorePointToAppear"
0x140003fbb  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x140003fc0  test    eax, eax
0x140003fc2  js      short loc_140003FE9
0x140003fc4  cmp     eax, 1
0x140003fc7  jz      short loc_140003FE9
0x140003fc9  mov     rcx, [rbp+57h+hKey]; hKey
0x140003fcd  lea     rax, [rcx-1]
0x140003fd1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140003fd5  ja      short loc_140003FE3
0x140003fd7  call    cs:__imp_RegCloseKey
0x140003fdd  mov     rdi, [rbp+57h+var_A8]
0x140003fe1  jmp     short loc_14000402E
0x140003fe3  mov     rdi, [rbp+57h+var_A8]
0x140003fe7  jmp     short loc_140004036
0x140003fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ff0  cmp     rcx, r13
0x140003ff3  jz      short loc_14000401A
0x140003ff5  test    dword ptr [rcx+1Ch], 4000000h
0x140003ffc  jz      short loc_14000401A
0x140003ffe  mov     rcx, [rcx+10h]
0x140004002  lea     r9, c_wszWaitForRestorePointToAppear; "WaitForRestorePointToAppear"
0x140004009  mov     edx, 33h ; '3'
0x14000400e  mov     dword ptr [rsp+0E0h+phkResult], eax
0x140004012  mov     r8, rsi
0x140004015  call    WPP_SF_SD
0x14000401a  mov     rcx, [rbp+57h+hKey]; hKey
0x14000401e  lea     rax, [rcx-1]
0x140004022  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140004026  ja      short loc_140004036
0x140004028  call    cs:__imp_RegCloseKey
0x14000402e  mov     [rbp+57h+hKey], 0
0x140004036  lea     rcx, [rbp+57h+var_60]; this
0x14000403a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000403f  xor     edx, edx; pUnkOuter
0x140004041  lea     rax, [rbp+57h+ppv]
0x140004045  lea     r9, IID_ISrControl; riid
0x14000404c  mov     [rsp+0E0h+phkResult], rax; ppv
0x140004051  lea     rcx, CLSID_SrControl; rclsid
0x140004058  lea     r8d, [rdx+1]; dwClsContext
0x14000405c  call    cs:__imp_CoCreateInstance
0x140004062  mov     [rbp+57h+var_98], eax
0x140004065  test    eax, eax
0x140004067  mov     eax, 378h
0x14000406c  jns     short loc_140004077
0x14000406e  mov     [rbp+57h+var_92], ax
0x140004072  jmp     loc_14000419A
0x140004077  mov     [rbp+57h+var_94], ax
0x14000407b  call    cs:__imp_GetTickCount64
0x140004081  mov     rsi, rax
0x140004084  mov     ecx, [rbp+57h+arg_10]
0x140004087  lea     rdx, [rbp+57h+var_B0]
0x14000408b  mov     ebx, 383h
0x140004090  call    cs:__imp_SrFreeRpPropArray
0x140004096  mov     rcx, [rbp+57h+ppv]
0x14000409a  lea     r8, [rbp+57h+var_B0]
0x14000409e  mov     [rbp+57h+arg_10], 0
0x1400040a5  mov     [rbp+57h+var_B0], 0
0x1400040ad  mov     rdx, [rcx]
0x1400040b0  mov     rax, [rdx+20h]
0x1400040b4  lea     rdx, [rbp+57h+arg_10]
0x1400040b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040bd  mov     [rbp+57h+var_98], eax
0x1400040c0  test    eax, eax
0x1400040c2  js      loc_140004196
0x1400040c8  mov     [rbp+57h+var_94], bx
0x1400040cc  xor     ebx, ebx
0x1400040ce  cmp     [rbp+57h+arg_10], ebx
0x1400040d1  jbe     short loc_14000411A
0x1400040d3  mov     rdx, [rbp+57h+var_B0]
0x1400040d7  mov     eax, ebx
0x1400040d9  imul    rcx, rax, 98h
0x1400040e0  cmp     [rcx+rdx+18h], r14d
0x1400040e5  jz      short loc_1400040F0
0x1400040e7  inc     ebx
0x1400040e9  cmp     ebx, [rbp+57h+arg_10]
0x1400040ec  jb      short loc_1400040D7
0x1400040ee  jmp     short loc_14000411A
0x1400040f0  mov     byte ptr [r15], 1
0x1400040f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040fb  cmp     rcx, r13
0x1400040fe  jz      short loc_140004121
0x140004100  test    dword ptr [rcx+1Ch], 8000000h
0x140004107  jz      short loc_140004121
0x140004109  mov     rcx, [rcx+10h]
0x14000410d  mov     edx, 35h ; '5'
0x140004112  mov     r9d, r14d
0x140004115  call    WPP_SF_L
0x14000411a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004121  cmp     ebx, [rbp+57h+arg_10]
0x140004124  jnz     short loc_14000419A
0x140004126  cmp     rcx, r13
0x140004129  jz      short loc_140004145
0x14000412b  test    dword ptr [rcx+1Ch], 8000000h
0x140004132  jz      short loc_140004145
0x140004134  mov     rcx, [rcx+10h]
0x140004138  mov     edx, 36h ; '6'
0x14000413d  mov     r9d, r14d
0x140004140  call    WPP_SF_L
0x140004145  call    cs:__imp_GetTickCount64
0x14000414b  imul    rcx, rdi, 0EA60h
0x140004152  sub     rax, rsi
0x140004155  cmp     rax, rcx
0x140004158  jnb     short loc_14000416A
0x14000415a  mov     ecx, 2710h; dwMilliseconds
0x14000415f  call    cs:__imp_Sleep
0x140004165  jmp     loc_140004084
0x14000416a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004171  cmp     rcx, r13
0x140004174  jz      short loc_14000419A
0x140004176  test    dword ptr [rcx+1Ch], 8000000h
0x14000417d  jz      short loc_14000419A
0x14000417f  mov     rcx, [rcx+10h]
0x140004183  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x14000418a  mov     edx, 37h ; '7'
0x14000418f  call    WPP_SF_
0x140004194  jmp     short loc_14000419A
0x140004196  mov     [rbp+57h+var_92], bx
0x14000419a  mov     ecx, [rbp+57h+arg_10]
0x14000419d  lea     rdx, [rbp+57h+var_B0]
0x1400041a1  call    cs:__imp_SrFreeRpPropArray
0x1400041a7  mov     rcx, [rbp+57h+ppv]
0x1400041ab  mov     ebx, [rbp+57h+var_98]
0x1400041ae  test    rcx, rcx
0x1400041b1  jz      short loc_1400041BF
0x1400041b3  mov     rdx, [rcx]
0x1400041b6  mov     rax, [rdx+10h]
0x1400041ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041bf  lea     rcx, [rbp+57h+var_98]; this
0x1400041c3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400041c8  lea     r11, [rsp+0E0h+var_20]
0x1400041d0  mov     eax, ebx
0x1400041d2  mov     rbx, [r11+30h]
0x1400041d6  mov     rsi, [r11+38h]
0x1400041da  mov     rsp, r11
0x1400041dd  pop     r15
0x1400041df  pop     r14
0x1400041e1  pop     r13
0x1400041e3  pop     rdi
0x1400041e4  pop     rbp
0x1400041e5  retn
```
