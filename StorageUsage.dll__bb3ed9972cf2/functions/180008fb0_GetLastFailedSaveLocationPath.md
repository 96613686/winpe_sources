# GetLastFailedSaveLocationPath

- ea: `0x180008fb0`
- end: `0x1800091e7`
- name: `GetLastFailedSaveLocationPath`
- size: `567`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x180008fb0`
- `0x18000b350`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000903e`
- `RPCRT4!NdrClientCall3` at `0x18000903e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008fd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009084`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008fd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009084`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000907e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000907e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ffc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ffc`

## pseudocode

```c
__int64 GetLastFailedSaveLocationPath()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  __int64 v3; // r8
  ULONGLONG v5; // [rsp+38h] [rbp-E0h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v7; // [rsp+48h] [rbp-D0h] BYREF
  ULONGLONG v8; // [rsp+50h] [rbp-C8h] BYREF
  ULONGLONG v9; // [rsp+58h] [rbp-C0h] BYREF
  ULONGLONG v10; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+68h] [rbp-B0h] BYREF
  char v12[32]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 *v13; // [rsp+90h] [rbp-88h]
  __int64 v14; // [rsp+98h] [rbp-80h]
  ULONGLONG *v15; // [rsp+A0h] [rbp-78h]
  __int64 v16; // [rsp+A8h] [rbp-70h]
  ULONGLONG *v17; // [rsp+B0h] [rbp-68h]
  __int64 v18; // [rsp+B8h] [rbp-60h]
  ULONGLONG *v19; // [rsp+C0h] [rbp-58h]
  __int64 v20; // [rsp+C8h] [rbp-50h]
  ULONGLONG *v21; // [rsp+D0h] [rbp-48h]
  __int64 v22; // [rsp+D8h] [rbp-40h]
  CLIENT_CALL_RETURN *v23; // [rsp+E0h] [rbp-38h]
  __int64 v24; // [rsp+E8h] [rbp-30h]
  __int64 *v25; // [rsp+F0h] [rbp-28h]
  __int64 v26; // [rsp+F8h] [rbp-20h]

  TickCount64 = GetTickCount64();
  v5 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0x18u, 0).Pointer;
      Pointer = (int)v2.Pointer;
      v6.Pointer = v2.Pointer;
      ReleaseSRWLockShared(&g_SvcContextLock);
    }
    else
    {
      ReleaseSRWLockShared(&g_SvcContextLock);
      Pointer = -2147024890;
    }
  }
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v7 = 1;
    v13 = &v7;
    v14 = 8;
    v8 = v3 - TickCount64;
    v15 = &v8;
    v16 = 8;
    v9 = v3 - TickCount64;
    v17 = &v9;
    v18 = 8;
    v10 = v3 - TickCount64;
    v19 = &v10;
    v20 = 8;
    LODWORD(v5) = 25;
    v21 = &v5;
    v22 = 4;
    LODWORD(v6.Pointer) = Pointer;
    v23 = &v6;
    v24 = 4;
    v11 = 0x1000000;
    v25 = &v11;
    v26 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)byte_180035E29, 0, 9u, (__int64)v12);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180008fb0  mov     [rsp+arg_8], rbx
0x180008fb5  mov     [rsp+arg_10], rsi
0x180008fba  push    r14
0x180008fbc  sub     rsp, 110h
0x180008fc3  mov     rax, cs:__security_cookie
0x180008fca  xor     rax, rsp
0x180008fcd  mov     [rsp+118h+var_18], rax
0x180008fd5  mov     r14, rcx
0x180008fd8  call    cs:__imp_GetTickCount64
0x180008fde  mov     rsi, rax
0x180008fe1  mov     [rsp+118h+var_E0], rax
0x180008fe6  call    OpenSvcContext
0x180008feb  mov     ebx, eax
0x180008fed  test    eax, eax
0x180008fef  js      loc_180009084
0x180008ff5  lea     rcx, g_SvcContextLock; SRWLock
0x180008ffc  call    cs:__imp_AcquireSRWLockShared
0x180009002  mov     r9, cs:g_hSvcContext
0x180009009  test    r9, r9
0x18000900c  jnz     short loc_180009022
0x18000900e  lea     rcx, g_SvcContextLock; SRWLock
0x180009015  call    cs:__imp_ReleaseSRWLockShared
0x18000901b  mov     ebx, 80070006h
0x180009020  jmp     short loc_180009084
0x180009022  mov     [rsp+118h+var_D8], 0
0x18000902b  mov     [rsp+118h+var_F8], r14
0x180009030  xor     r8d, r8d; pReturnValue
0x180009033  lea     edx, [r8+18h]; nProcNum
0x180009037  lea     rcx, stru_18002E100; pProxyInfo
0x18000903e  call    cs:__imp_NdrClientCall3
0x180009044  mov     rbx, rax
0x180009047  mov     [rsp+118h+var_D8], rax
0x18000904c  mov     [rsp+118h+var_E8], eax
0x180009050  jmp     short loc_180009077
0x180009052  test    eax, eax
0x180009054  jle     short loc_18000905E
0x180009056  movzx   eax, ax
0x180009059  or      eax, 80070000h
0x18000905e  mov     [rsp+118h+var_E8], eax
0x180009062  mov     ecx, 8000FFFFh
0x180009067  test    eax, eax
0x180009069  cmovns  eax, ecx
0x18000906c  mov     ebx, eax
0x18000906e  mov     [rsp+118h+var_E8], eax
0x180009072  mov     rsi, [rsp+118h+var_E0]
0x180009077  lea     rcx, g_SvcContextLock; SRWLock
0x18000907e  call    cs:__imp_ReleaseSRWLockShared
0x180009084  call    cs:__imp_GetTickCount64
0x18000908a  mov     r8, rax
0x18000908d  mov     ecx, cs:dword_180040048
0x180009093  cmp     ecx, 5
0x180009096  jbe     loc_1800091BF
0x18000909c  mov     rdx, 400000000000h
0x1800090a6  lea     rcx, dword_180040048
0x1800090ad  call    _tlgKeywordOn
0x1800090b2  test    al, al
0x1800090b4  jz      loc_1800091BF
0x1800090ba  sub     r8, rsi
0x1800090bd  mov     [rsp+118h+var_D0], 1
0x1800090c6  lea     rax, [rsp+118h+var_D0]
0x1800090cb  mov     [rsp+118h+var_88], rax
0x1800090d3  mov     [rsp+118h+var_80], 8
0x1800090df  mov     [rsp+118h+var_C8], r8
0x1800090e4  lea     rax, [rsp+118h+var_C8]
0x1800090e9  mov     [rsp+118h+var_78], rax
0x1800090f1  mov     [rsp+118h+var_70], 8
0x1800090fd  mov     [rsp+118h+var_C0], r8
0x180009102  lea     rax, [rsp+118h+var_C0]
0x180009107  mov     [rsp+118h+var_68], rax
0x18000910f  mov     [rsp+118h+var_60], 8
0x18000911b  mov     [rsp+118h+var_B8], r8
0x180009120  lea     rax, [rsp+118h+var_B8]
0x180009125  mov     [rsp+118h+var_58], rax
0x18000912d  mov     [rsp+118h+var_50], 8
0x180009139  mov     dword ptr [rsp+118h+var_E0], 19h
0x180009141  lea     rax, [rsp+118h+var_E0]
0x180009146  mov     [rsp+118h+var_48], rax
0x18000914e  mov     [rsp+118h+var_40], 4
0x18000915a  mov     dword ptr [rsp+118h+var_D8], ebx
0x18000915e  lea     rax, [rsp+118h+var_D8]
0x180009163  mov     [rsp+118h+var_38], rax
0x18000916b  mov     [rsp+118h+var_30], 4
0x180009177  mov     [rsp+118h+var_B0], 1000000h
0x180009180  lea     rax, [rsp+118h+var_B0]
0x180009185  mov     [rsp+118h+var_28], rax
0x18000918d  mov     [rsp+118h+var_20], 8
0x180009199  lea     rax, [rsp+118h+var_A8]
0x18000919e  mov     [rsp+118h+var_F8], rax
0x1800091a3  mov     r9d, 9
0x1800091a9  xor     r8d, r8d
0x1800091ac  lea     rdx, byte_180035E29
0x1800091b3  lea     rcx, dword_180040048
0x1800091ba  call    _tlgWriteAgg
0x1800091bf  mov     eax, ebx
0x1800091c1  mov     rcx, [rsp+118h+var_18]
0x1800091c9  xor     rcx, rsp; StackCookie
0x1800091cc  call    __security_check_cookie
0x1800091d1  lea     r11, [rsp+118h+var_8]
0x1800091d9  mov     rbx, [r11+18h]
0x1800091dd  mov     rsi, [r11+20h]
0x1800091e1  mov     rsp, r11
0x1800091e4  pop     r14
0x1800091e6  retn
0x18002b17a  push    rbp
0x18002b17c  sub     rsp, 30h
0x18002b180  mov     rbp, rdx
0x18002b183  mov     rcx, [rcx]
0x18002b186  mov     ecx, [rcx]; ExceptionCode
0x18002b188  call    cs:__imp_I_RpcExceptionFilter
0x18002b18e  nop
0x18002b18f  add     rsp, 30h
0x18002b193  pop     rbp
0x18002b194  retn
```
