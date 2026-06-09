# LoadIndex(_INDEX_STRUCT *)

- ea: `0x180007c14`
- end: `0x180007e99`
- name: `?LoadIndex@@YAKPEAU_INDEX_STRUCT@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(struct _INDEX_STRUCT *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800064a8`

## callees

- `0x180004dc4`
- `0x180004dec`
- `0x18000768c`
- `0x180007c14`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007cc5`
- `KERNEL32!GetLastError` at `0x180007d2b`
- `KERNEL32!GetLastError` at `0x180007cc5`
- `KERNEL32!GetLastError` at `0x180007d2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007ca1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007ca1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e5b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e5b`
- `KERNEL32!GetFileAttributesExW` at `0x180007df2`
- `KERNEL32!GetFileAttributesExW` at `0x180007df2`
- `KERNEL32!WaitForSingleObject` at `0x180007c97`
- `KERNEL32!WaitForSingleObject` at `0x180007c97`
- `KERNEL32!ReleaseMutex` at `0x180007e79`
- `KERNEL32!ReleaseMutex` at `0x180007e79`
- `DEVRTL!NdxTableSetTypeDefinition` at `0x180007d21`
- `DEVRTL!NdxTableSetTypeDefinition` at `0x180007d21`
- `DEVRTL!NdxTableFirstObject` at `0x180007e11`
- `DEVRTL!NdxTableFirstObject` at `0x180007e38`
- `DEVRTL!NdxTableFirstObject` at `0x180007e11`
- `DEVRTL!NdxTableFirstObject` at `0x180007e38`
- `DEVRTL!NdxTableOpen` at `0x180007cb5`
- `DEVRTL!NdxTableOpen` at `0x180007cb5`
- `DEVRTL!NdxTableNextObject` at `0x180007e24`
- `DEVRTL!NdxTableNextObject` at `0x180007e4b`
- `DEVRTL!NdxTableNextObject` at `0x180007e24`
- `DEVRTL!NdxTableNextObject` at `0x180007e4b`

## pseudocode

```c
__int64 __fastcall LoadIndex(struct _INDEX_STRUCT *a1, __int64 a2)
{
  HANDLE v3; // rcx
  __int64 v4; // rax
  DWORD LastError; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  int i; // eax
  int j; // eax
  __int64 v11; // rdx
  HANDLE v12; // rcx
  __int128 FileInformation; // [rsp+20h] [rbp-29h] BYREF
  __int128 v15; // [rsp+30h] [rbp-19h]
  int v16; // [rsp+40h] [rbp-9h]
  _OWORD v17[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v18; // [rsp+68h] [rbp+1Fh]

  v16 = 0;
  v18 = 0;
  FileInformation = 0;
  v15 = 0;
  memset(v17, 0, sizeof(v17));
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  v3 = g_hDmrcPrivateMutex;
  v16 = 0;
  FileInformation = 0;
  v15 = 0;
  if ( !g_hDmrcPrivateMutex )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
    v3 = g_hDmrcPrivateMutex;
  }
  WaitForSingleObject(v3, 0xFFFFFFFF);
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
  v4 = NdxTableOpen(*((_QWORD *)a1 + 1), 2, 0);
  *((_QWORD *)a1 + 5) = v4;
  if ( v4 == -1 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 28;
LABEL_11:
      WPP_SF_d(v6[2], v7, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, LastError);
    }
  }
  else if ( (unsigned int)NdxTableSetTypeDefinition(
                            v4,
                            &NdxTypeDefinition,
                            27,
                            7024,
                            FileInformation,
                            *((_QWORD *)&FileInformation + 1),
                            v15)
         || (v8 = GetLastError(), LastError = v8, v8 == 183) )
  {
    if ( (unsigned int)IsIndexCorrupt(a1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
      LastError = 1392;
    }
    else
    {
      if ( GetFileAttributesExW(*((LPCWSTR *)a1 + 1), GetFileExInfoStandard, &FileInformation) )
        *((_QWORD *)a1 + 6) = *(_QWORD *)((char *)&v15 + 4);
      for ( i = NdxTableFirstObject(*((_QWORD *)a1 + 5), 1, v17); i; i = NdxTableNextObject(v17) )
        _InterlockedIncrement(&g_nPackages);
      for ( j = NdxTableFirstObject(*((_QWORD *)a1 + 5), 0, v17); j; j = NdxTableNextObject(v17) )
        _InterlockedIncrement(&g_nPackages);
      LastError = 0;
    }
  }
  else if ( v8 == 1306 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 30;
      goto LABEL_11;
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)a1 + 4);
  v12 = g_hDmrcPrivateMutex;
  if ( !g_hDmrcPrivateMutex )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v11);
    v12 = g_hDmrcPrivateMutex;
  }
  ReleaseMutex(v12);
  return LastError;
}

```

## disassembly

```asm
0x180007c14  push    rbp
0x180007c16  push    rbx
0x180007c17  push    rsi
0x180007c18  push    rdi
0x180007c19  lea     rbp, [rsp-3Fh]
0x180007c1e  sub     rsp, 88h
0x180007c25  mov     rax, cs:__security_cookie
0x180007c2c  xor     rax, rsp
0x180007c2f  mov     [rbp+57h+var_30], rax
0x180007c33  xor     eax, eax
0x180007c35  xorps   xmm0, xmm0
0x180007c38  mov     [rbp+57h+var_60], eax
0x180007c3b  xorps   xmm1, xmm1
0x180007c3e  mov     [rbp+57h+var_38], rax
0x180007c42  mov     rdi, rcx
0x180007c45  movups  [rbp+57h+FileInformation], xmm0
0x180007c49  movups  [rbp+57h+var_70], xmm0
0x180007c4d  movups  [rbp+57h+var_58], xmm1
0x180007c51  movups  [rbp+57h+var_48], xmm1
0x180007c55  test    rcx, rcx
0x180007c58  jnz     short loc_180007C5F
0x180007c5a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c5f  cmp     dword ptr [rdi], 494E4445h
0x180007c65  jz      short loc_180007C6C
0x180007c67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c6c  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; void * g_hDmrcPrivateMutex
0x180007c73  xor     eax, eax
0x180007c75  mov     [rbp+57h+var_60], eax
0x180007c78  xorps   xmm0, xmm0
0x180007c7b  movups  [rbp+57h+FileInformation], xmm0
0x180007c7f  movups  [rbp+57h+var_70], xmm0
0x180007c83  test    rcx, rcx
0x180007c86  jnz     short loc_180007C94
0x180007c88  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c8d  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; hHandle
0x180007c94  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007c97  call    cs:__imp_WaitForSingleObject
0x180007c9d  lea     rcx, [rdi+20h]; SRWLock
0x180007ca1  call    cs:__imp_AcquireSRWLockExclusive
0x180007ca7  mov     rcx, [rdi+8]
0x180007cab  xor     r9d, r9d
0x180007cae  xor     r8d, r8d
0x180007cb1  lea     edx, [r9+2]
0x180007cb5  call    cs:__imp_NdxTableOpen
0x180007cbb  mov     [rdi+28h], rax
0x180007cbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007cc3  jnz     short loc_180007D0B
0x180007cc5  call    cs:__imp_GetLastError
0x180007ccb  mov     ebx, eax
0x180007ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cd4  lea     rax, WPP_GLOBAL_Control
0x180007cdb  cmp     rcx, rax
0x180007cde  jz      loc_180007E57
0x180007ce4  test    byte ptr [rcx+1Ch], 1
0x180007ce8  jz      loc_180007E57
0x180007cee  mov     edx, 1Ch
0x180007cf3  mov     rcx, [rcx+10h]
0x180007cf7  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180007cfe  mov     r9d, ebx
0x180007d01  call    WPP_SF_d
0x180007d06  jmp     loc_180007E57
0x180007d0b  mov     r9d, 1B70h
0x180007d11  lea     rdx, ?NdxTypeDefinition@@3PAU_NDX_TYPE_DEF@@A; _NDX_TYPE_DEF near * NdxTypeDefinition
0x180007d18  mov     r8d, 1Bh
0x180007d1e  mov     rcx, rax
0x180007d21  call    cs:__imp_NdxTableSetTypeDefinition
0x180007d27  test    eax, eax
0x180007d29  jnz     short loc_180007DA7
0x180007d2b  call    cs:__imp_GetLastError
0x180007d31  mov     ebx, eax
0x180007d33  cmp     eax, 0B7h
0x180007d38  jz      short loc_180007DA7
0x180007d3a  cmp     eax, 51Ah
0x180007d3f  jnz     short loc_180007D7C
0x180007d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d48  lea     rax, WPP_GLOBAL_Control
0x180007d4f  cmp     rcx, rax
0x180007d52  jz      loc_180007E57
0x180007d58  test    byte ptr [rcx+1Ch], 1
0x180007d5c  jz      loc_180007E57
0x180007d62  mov     rcx, [rcx+10h]
0x180007d66  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180007d6d  mov     edx, 1Dh
0x180007d72  call    WPP_SF_
0x180007d77  jmp     loc_180007E57
0x180007d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d83  lea     rax, WPP_GLOBAL_Control
0x180007d8a  cmp     rcx, rax
0x180007d8d  jz      loc_180007E57
0x180007d93  test    byte ptr [rcx+1Ch], 1
0x180007d97  jz      loc_180007E57
0x180007d9d  mov     edx, 1Eh
0x180007da2  jmp     loc_180007CF3
0x180007da7  mov     rcx, rdi; struct _INDEX_STRUCT *
0x180007daa  call    IsIndexCorrupt
0x180007daf  test    eax, eax
0x180007db1  jz      short loc_180007DE8
0x180007db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dba  lea     rax, WPP_GLOBAL_Control
0x180007dc1  cmp     rcx, rax
0x180007dc4  jz      short loc_180007DE1
0x180007dc6  test    byte ptr [rcx+1Ch], 1
0x180007dca  jz      short loc_180007DE1
0x180007dcc  mov     rcx, [rcx+10h]
0x180007dd0  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180007dd7  mov     edx, 1Fh
0x180007ddc  call    WPP_SF_
0x180007de1  mov     ebx, 570h
0x180007de6  jmp     short loc_180007E57
0x180007de8  mov     rcx, [rdi+8]; lpFileName
0x180007dec  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180007df0  xor     edx, edx; fInfoLevelId
0x180007df2  call    cs:__imp_GetFileAttributesExW
0x180007df8  test    eax, eax
0x180007dfa  jz      short loc_180007E04
0x180007dfc  mov     rax, qword ptr [rbp+57h+var_70+4]
0x180007e00  mov     [rdi+30h], rax
0x180007e04  mov     rcx, [rdi+28h]
0x180007e08  lea     r8, [rbp+57h+var_58]
0x180007e0c  mov     edx, 1
0x180007e11  call    cs:__imp_NdxTableFirstObject
0x180007e17  jmp     short loc_180007E2A
0x180007e19  lock inc cs:?g_nPackages@@3JC; long volatile g_nPackages
0x180007e20  lea     rcx, [rbp+57h+var_58]
0x180007e24  call    cs:__imp_NdxTableNextObject
0x180007e2a  test    eax, eax
0x180007e2c  jnz     short loc_180007E19
0x180007e2e  mov     rcx, [rdi+28h]
0x180007e32  lea     r8, [rbp+57h+var_58]
0x180007e36  xor     edx, edx
0x180007e38  call    cs:__imp_NdxTableFirstObject
0x180007e3e  jmp     short loc_180007E51
0x180007e40  lock inc cs:?g_nPackages@@3JC; long volatile g_nPackages
0x180007e47  lea     rcx, [rbp+57h+var_58]
0x180007e4b  call    cs:__imp_NdxTableNextObject
0x180007e51  test    eax, eax
0x180007e53  jnz     short loc_180007E40
0x180007e55  xor     ebx, ebx
0x180007e57  lea     rcx, [rdi+20h]; SRWLock
0x180007e5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e61  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; void * g_hDmrcPrivateMutex
0x180007e68  test    rcx, rcx
0x180007e6b  jnz     short loc_180007E79
0x180007e6d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007e72  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; hMutex
0x180007e79  call    cs:__imp_ReleaseMutex
0x180007e7f  mov     eax, ebx
0x180007e81  mov     rcx, [rbp+57h+var_30]
0x180007e85  xor     rcx, rsp; StackCookie
0x180007e88  call    __security_check_cookie
0x180007e8d  add     rsp, 88h
0x180007e94  pop     rdi
0x180007e95  pop     rsi
0x180007e96  pop     rbx
0x180007e97  pop     rbp
0x180007e98  retn
```
