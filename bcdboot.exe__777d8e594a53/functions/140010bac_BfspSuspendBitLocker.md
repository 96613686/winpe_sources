# BfspSuspendBitLocker

- ea: `0x140010bac`
- end: `0x140010e21`
- name: `BfspSuspendBitLocker`
- size: `629`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009fd4`

## callees

- `0x14000e628`
- `0x14001062c`
- `0x140010878`
- `0x140010bac`
- `0x1400265fa`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140010df1`
- `KERNEL32!FreeLibrary` at `0x140010df1`

## string_xrefs

- `0x140010c82`: `BfspOpenFveApi failed.FveApiFound = %d,HRESULT = [%x]`
- `0x140010d24`: `FveOpenVolumeW failed.HRESULT = [%x]`
- `0x140010dab`: `BfsTryCommitFveChanges failed.HRESULT = [%x]`

## pseudocode

```c
__int64 __fastcall BfspSuspendBitLocker(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  int v7; // eax
  int v8; // edi
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v17; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hLibModule[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v20; // [rsp+D0h] [rbp-30h]
  __int128 v21; // [rsp+E0h] [rbp-20h]
  __int64 v22; // [rsp+F0h] [rbp-10h]
  _DWORD v23[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v24; // [rsp+100h] [rbp+0h]
  __int64 v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v27[4]; // [rsp+130h] [rbp+30h] BYREF
  char v28; // [rsp+140h] [rbp+40h]
  int v29; // [rsp+144h] [rbp+44h]

  memset_0(hLibModule, 0, sizeof(hLibModule));
  LODWORD(v15) = 0;
  v25 = 0;
  v24 = 0;
  memset_0(v27, 0, 0x248u);
  v16 = -1;
  v23[0] = 32;
  v17 = v27;
  v22 = 0;
  v19 = 0;
  *a3 = 1;
  *a4 = 0;
  v23[1] = 1;
  v20 = 0;
  v21 = 0;
  v26 = 0;
  if ( !a1 )
    return 2147942487LL;
  v7 = BfspOpenFveApi((__int64)hLibModule, &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = v15;
    BfspLogMessage(3, L"BfspOpenFveApi failed.FveApiFound = %d,HRESULT = [%x]", (unsigned int)v15, (unsigned int)v7);
    if ( !v9 )
    {
      *a3 = 0;
      v8 = 0;
    }
    if ( v8 >= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v10 = ((__int64 (__fastcall *)(__int64, _DWORD *))hLibModule[1])(a1, v23);
  v8 = v10;
  if ( v10 < 0 )
  {
    BfspLogMessage(4, L"FveGetStatusW failed.HRESULT = [%x]", (unsigned int)v10);
LABEL_20:
    BfspLogMessage(4, L"BfspSuspendBitLocker failed.RebootCount = %dHRESULT = [%x]", 1, (unsigned int)v8, v15);
    goto LABEL_21;
  }
  if ( (v24 & 1) == 0 )
  {
    *a3 = 0;
    BfspLogMessage(2, L"BitLocker Not enabled.Flags = [%x]");
    goto LABEL_21;
  }
  if ( (v24 & 0x400) != 0 )
  {
    *a4 = 1;
    BfspLogMessage(2, L"BitLocker suspended.Flags = [%x]");
  }
  else
  {
    v11 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))hLibModule[2])(a1, 1, &v16);
    v8 = v11;
    if ( v11 < 0 )
    {
      BfspLogMessage(4, L"FveOpenVolumeW failed.HRESULT = [%x]", (unsigned int)v11);
      goto LABEL_20;
    }
    *(_QWORD *)&v20 = &v17;
    v27[0] = 584;
    v27[1] = 1;
    v27[2] = 1;
    v27[3] = 9;
    v28 = 1;
    v29 = 3;
    *(_QWORD *)&v19 = 0x100000038LL;
    *((_QWORD *)&v19 + 1) = 0x100010000LL;
    v12 = ((__int64 (__fastcall *)(__int64, __int128 *, __int128 *))hLibModule[5])(v16, &v19, &v26);
    v8 = v12;
    if ( v12 < 0 )
    {
      BfspLogMessage(4, L"FveAddAuthMethodInfo failed.HRESULT = [%x]", (unsigned int)v12);
      goto LABEL_20;
    }
    v13 = BfsTryCommitFveChanges(v16, hLibModule);
    v8 = v13;
    if ( v13 < 0 )
    {
      BfspLogMessage(4, L"BfsTryCommitFveChanges failed.HRESULT = [%x]", (unsigned int)v13);
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( v16 != -1 )
    ((void (*)(void))hLibModule[6])();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140010bac  push    rbp
0x140010bae  push    rbx
0x140010baf  push    rsi
0x140010bb0  push    rdi
0x140010bb1  push    r12
0x140010bb3  push    r13
0x140010bb5  push    r14
0x140010bb7  lea     rbp, [rsp-290h]
0x140010bbf  sub     rsp, 390h
0x140010bc6  mov     rax, cs:__security_cookie
0x140010bcd  xor     rax, rsp
0x140010bd0  mov     [rbp+2C0h+var_40], rax
0x140010bd7  mov     rsi, r8
0x140010bda  mov     rbx, rcx
0x140010bdd  mov     r8d, 80h; Size
0x140010be3  lea     rcx, [rsp+3C0h+hLibModule]; void *
0x140010be8  xor     edx, edx; Val
0x140010bea  mov     r14, r9
0x140010bed  call    memset_0
0x140010bf2  xorps   xmm0, xmm0
0x140010bf5  mov     dword ptr [rsp+3C0h+var_3A0], 0
0x140010bfd  xor     edx, edx; Val
0x140010bff  mov     [rbp+2C0h+var_2B0], 0
0x140010c07  mov     r8d, 248h; Size
0x140010c0d  lea     rcx, [rbp+2C0h+var_290]; void *
0x140010c11  movdqu  [rbp+2C0h+var_2C0], xmm0
0x140010c16  call    memset_0
0x140010c1b  xorps   xmm0, xmm0
0x140010c1e  mov     [rsp+3C0h+var_398], 0FFFFFFFFFFFFFFFFh
0x140010c27  lea     rax, [rbp+2C0h+var_290]
0x140010c2b  mov     [rbp+2C0h+var_2C8], 20h ; ' '
0x140010c32  mov     [rsp+3C0h+var_390], rax
0x140010c37  xor     eax, eax
0x140010c39  mov     [rbp+2C0h+var_2D0], rax
0x140010c3d  movups  [rbp+2C0h+var_300], xmm0
0x140010c41  lea     r12d, [rax+1]
0x140010c45  mov     [rsi], r12d
0x140010c48  mov     [r14], eax
0x140010c4b  mov     [rbp+2C0h+var_2C4], r12d
0x140010c4f  movups  [rbp+2C0h+var_2F0], xmm0
0x140010c53  movups  [rbp+2C0h+var_2E0], xmm0
0x140010c57  movups  [rbp+2C0h+var_2A8], xmm0
0x140010c5b  test    rbx, rbx
0x140010c5e  jz      loc_140010DFB
0x140010c64  lea     rdx, [rsp+3C0h+var_3A0]
0x140010c69  lea     rcx, [rsp+3C0h+hLibModule]
0x140010c6e  call    BfspOpenFveApi
0x140010c73  lea     r13d, [r12+3]
0x140010c78  mov     edi, eax
0x140010c7a  test    eax, eax
0x140010c7c  jns     short loc_140010CAE
0x140010c7e  mov     ebx, dword ptr [rsp+3C0h+var_3A0]
0x140010c82  lea     rdx, aBfspopenfveapi; "BfspOpenFveApi failed.FveApiFound = %d,"...
0x140010c89  mov     r8d, ebx
0x140010c8c  lea     ecx, [r12+2]
0x140010c91  mov     r9d, eax
0x140010c94  call    BfspLogMessage
0x140010c99  test    ebx, ebx
0x140010c9b  jnz     short loc_140010CA1
0x140010c9d  mov     [rsi], ebx
0x140010c9f  xor     edi, edi
0x140010ca1  test    edi, edi
0x140010ca3  jns     loc_140010DD2
0x140010ca9  jmp     loc_140010DBD
0x140010cae  mov     rax, [rsp+3C0h+var_378]
0x140010cb3  lea     rdx, [rbp+2C0h+var_2C8]
0x140010cb7  mov     rcx, rbx
0x140010cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010cbf  mov     edi, eax
0x140010cc1  test    eax, eax
0x140010cc3  jns     short loc_140010CD1
0x140010cc5  lea     rdx, aFvegetstatuswF; "FveGetStatusW failed.HRESULT = [%x]"
0x140010ccc  jmp     loc_140010DB2
0x140010cd1  mov     r8d, dword ptr [rbp+2C0h+var_2C0]
0x140010cd5  test    r12b, r8b
0x140010cd8  jnz     short loc_140010CF6
0x140010cda  mov     dword ptr [rsi], 0
0x140010ce0  lea     rdx, aBitlockerNotEn; "BitLocker Not enabled.Flags = [%x]"
0x140010ce7  mov     ecx, 2
0x140010cec  call    BfspLogMessage
0x140010cf1  jmp     loc_140010DD2
0x140010cf6  bt      r8d, 0Ah
0x140010cfb  jnb     short loc_140010D09
0x140010cfd  mov     [r14], r12d
0x140010d00  lea     rdx, aBitlockerSuspe; "BitLocker suspended.Flags = [%x]"
0x140010d07  jmp     short loc_140010CE7
0x140010d09  mov     rax, [rsp+3C0h+var_370]
0x140010d0e  lea     r8, [rsp+3C0h+var_398]
0x140010d13  mov     edx, r12d
0x140010d16  mov     rcx, rbx
0x140010d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d1e  mov     edi, eax
0x140010d20  test    eax, eax
0x140010d22  jns     short loc_140010D30
0x140010d24  lea     rdx, aFveopenvolumew_0; "FveOpenVolumeW failed.HRESULT = [%x]"
0x140010d2b  jmp     loc_140010DB2
0x140010d30  mov     rcx, [rsp+3C0h+var_398]
0x140010d35  lea     rax, [rsp+3C0h+var_390]
0x140010d3a  mov     qword ptr [rbp+2C0h+var_2F0], rax
0x140010d3e  lea     r8, [rbp+2C0h+var_2A8]
0x140010d42  mov     rax, [rsp+3C0h+var_358]
0x140010d47  lea     rdx, [rbp+2C0h+var_300]
0x140010d4b  mov     [rbp+2C0h+var_290], 248h
0x140010d52  mov     [rbp+2C0h+var_28C], r12d
0x140010d56  mov     [rbp+2C0h+var_288], r12d
0x140010d5a  mov     [rbp+2C0h+var_284], 9
0x140010d61  mov     [rbp+2C0h+var_280], r12b
0x140010d65  mov     [rbp+2C0h+var_27C], 3
0x140010d6c  mov     dword ptr [rbp+2C0h+var_300], 38h ; '8'
0x140010d73  mov     dword ptr [rbp+2C0h+var_300+4], r12d
0x140010d77  mov     dword ptr [rbp+2C0h+var_300+8], 10000h
0x140010d7e  mov     dword ptr [rbp+2C0h+var_300+0Ch], r12d
0x140010d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d87  mov     edi, eax
0x140010d89  test    eax, eax
0x140010d8b  jns     short loc_140010D96
0x140010d8d  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInfo failed.HRESULT = ["...
0x140010d94  jmp     short loc_140010DB2
0x140010d96  mov     rcx, [rsp+3C0h+var_398]
0x140010d9b  lea     rdx, [rsp+3C0h+hLibModule]
0x140010da0  call    BfsTryCommitFveChanges
0x140010da5  mov     edi, eax
0x140010da7  test    eax, eax
0x140010da9  jns     short loc_140010DD2
0x140010dab  lea     rdx, aBfstrycommitfv; "BfsTryCommitFveChanges failed.HRESULT ="...
0x140010db2  mov     r8d, eax
0x140010db5  mov     ecx, r13d
0x140010db8  call    BfspLogMessage
0x140010dbd  mov     r9d, edi
0x140010dc0  lea     rdx, aBfspsuspendbit; "BfspSuspendBitLocker failed.RebootCount"...
0x140010dc7  mov     r8d, r12d
0x140010dca  mov     ecx, r13d
0x140010dcd  call    BfspLogMessage
0x140010dd2  mov     rcx, [rsp+3C0h+var_398]
0x140010dd7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140010ddb  jz      short loc_140010DE7
0x140010ddd  mov     rax, [rsp+3C0h+var_350]
0x140010de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010de7  mov     rcx, [rsp+3C0h+hLibModule]; hLibModule
0x140010dec  test    rcx, rcx
0x140010def  jz      short loc_140010DF7
0x140010df1  call    cs:__imp_FreeLibrary
0x140010df7  mov     eax, edi
0x140010df9  jmp     short loc_140010E00
0x140010dfb  mov     eax, 80070057h
0x140010e00  mov     rcx, [rbp+2C0h+var_40]
0x140010e07  xor     rcx, rsp; StackCookie
0x140010e0a  call    __security_check_cookie
0x140010e0f  add     rsp, 390h
0x140010e16  pop     r14
0x140010e18  pop     r13
0x140010e1a  pop     r12
0x140010e1c  pop     rdi
0x140010e1d  pop     rsi
0x140010e1e  pop     rbx
0x140010e1f  pop     rbp
0x140010e20  retn
```
