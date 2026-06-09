# GetFirstThreadInProcess(ulong,ulong *)

- ea: `0x140016500`
- end: `0x140016691`
- name: `?GetFirstThreadInProcess@@YAJKPEAK@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140016cbc`

## callees

- `0x140002470`
- `0x1400032ef`
- `0x14001444c`
- `0x140014474`
- `0x140016500`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001661b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001661b`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x1400165bc`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x1400165bc`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x1400165a4`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x1400165a4`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001657e`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001657e`

## pseudocode

```c
__int64 __fastcall GetFirstThreadInProcess(unsigned int a1, unsigned int *a2)
{
  unsigned int v4; // edi
  char *Toolhelp32Snapshot; // rbx
  DWORD th32OwnerProcessID; // eax
  signed int LastError_0; // eax
  THREADENTRY32 te; // [rsp+20h] [rbp-38h] BYREF

  memset(&te, 0, sizeof(te));
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
    }
    return v4;
  }
  *a2 = 0;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(4u, 0);
  if ( Toolhelp32Snapshot != (char *)-1LL && Toolhelp32Snapshot + 1 != (char *)1 )
  {
    te.dwSize = 28;
    if ( Thread32First(Toolhelp32Snapshot, &te) )
    {
      if ( te.th32OwnerProcessID == a1 )
        goto LABEL_16;
      while ( Thread32Next(Toolhelp32Snapshot, &te) )
      {
        th32OwnerProcessID = te.th32OwnerProcessID;
        if ( te.th32OwnerProcessID == a1 )
          goto LABEL_12;
      }
    }
    th32OwnerProcessID = te.th32OwnerProcessID;
LABEL_12:
    if ( th32OwnerProcessID != a1 )
    {
      v4 = -2147023728;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, a1);
      }
      goto LABEL_17;
    }
LABEL_16:
    *a2 = te.th32ThreadID;
    v4 = 0;
LABEL_17:
    CloseHandle(Toolhelp32Snapshot);
    return v4;
  }
  LastError_0 = GetLastError_0();
  v4 = LastError_0;
  if ( LastError_0 > 0 )
    v4 = (unsigned __int16)LastError_0 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140016500  mov     [rsp+arg_10], rbx
0x140016505  mov     [rsp+arg_18], rsi
0x14001650a  push    rdi
0x14001650b  sub     rsp, 50h
0x14001650f  mov     rax, cs:__security_cookie
0x140016516  xor     rax, rsp
0x140016519  mov     [rsp+58h+var_18], rax
0x14001651e  xorps   xmm0, xmm0
0x140016521  xor     eax, eax
0x140016523  mov     rdi, rdx
0x140016526  mov     esi, ecx
0x140016528  movups  xmmword ptr [rsp+58h+te.dwSize], xmm0
0x14001652d  movups  xmmword ptr [rsp+58h+te.th32OwnerProcessID], xmm0
0x140016532  test    rdx, rdx
0x140016535  jnz     short loc_140016577
0x140016537  mov     edi, 80070057h
0x14001653c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016543  lea     rax, WPP_GLOBAL_Control
0x14001654a  cmp     rcx, rax
0x14001654d  jz      loc_140016672
0x140016553  test    byte ptr [rcx+1Ch], 1
0x140016557  jz      loc_140016672
0x14001655d  mov     rcx, [rcx+10h]
0x140016561  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016568  mov     edx, 0Dh
0x14001656d  call    WPP_SF_
0x140016572  jmp     loc_140016672
0x140016577  mov     [rdx], eax
0x140016579  xor     edx, edx; th32ProcessID
0x14001657b  lea     ecx, [rdx+4]; dwFlags
0x14001657e  call    cs:__imp_CreateToolhelp32Snapshot
0x140016584  mov     rbx, rax
0x140016587  inc     rax
0x14001658a  cmp     rax, 1
0x14001658e  jbe     loc_140016623
0x140016594  lea     rdx, [rsp+58h+te]; lpte
0x140016599  mov     [rsp+58h+te.dwSize], 1Ch
0x1400165a1  mov     rcx, rbx; hSnapshot
0x1400165a4  call    cs:__imp_Thread32First
0x1400165aa  test    eax, eax
0x1400165ac  jz      short loc_1400165D0
0x1400165ae  cmp     [rsp+58h+te.th32OwnerProcessID], esi
0x1400165b2  jz      short loc_140016610
0x1400165b4  lea     rdx, [rsp+58h+te]; lpte
0x1400165b9  mov     rcx, rbx; hSnapshot
0x1400165bc  call    cs:__imp_Thread32Next
0x1400165c2  test    eax, eax
0x1400165c4  jz      short loc_1400165D0
0x1400165c6  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x1400165ca  cmp     eax, esi
0x1400165cc  jnz     short loc_1400165B4
0x1400165ce  jmp     short loc_1400165D4
0x1400165d0  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x1400165d4  cmp     eax, esi
0x1400165d6  jz      short loc_140016610
0x1400165d8  mov     edi, 80070490h
0x1400165dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165e4  lea     rax, WPP_GLOBAL_Control
0x1400165eb  cmp     rcx, rax
0x1400165ee  jz      short loc_140016618
0x1400165f0  test    byte ptr [rcx+1Ch], 1
0x1400165f4  jz      short loc_140016618
0x1400165f6  mov     rcx, [rcx+10h]
0x1400165fa  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016601  mov     edx, 0Fh
0x140016606  mov     r9d, esi
0x140016609  call    WPP_SF_d
0x14001660e  jmp     short loc_140016618
0x140016610  mov     eax, [rsp+58h+te.th32ThreadID]
0x140016614  mov     [rdi], eax
0x140016616  xor     edi, edi
0x140016618  mov     rcx, rbx; hObject
0x14001661b  call    cs:__imp_CloseHandle
0x140016621  jmp     short loc_140016672
0x140016623  call    GetLastError_0
0x140016628  mov     edi, eax
0x14001662a  test    eax, eax
0x14001662c  jle     short loc_140016637
0x14001662e  movzx   edi, ax
0x140016631  or      edi, 80070000h
0x140016637  test    edi, edi
0x140016639  mov     eax, 80004005h
0x14001663e  cmovns  edi, eax
0x140016641  mov     rcx, cs:WPP_GLOBAL_Control
0x140016648  lea     rax, WPP_GLOBAL_Control
0x14001664f  cmp     rcx, rax
0x140016652  jz      short loc_140016672
0x140016654  test    byte ptr [rcx+1Ch], 1
0x140016658  jz      short loc_140016672
0x14001665a  mov     rcx, [rcx+10h]
0x14001665e  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016665  mov     edx, 0Eh
0x14001666a  mov     r9d, edi
0x14001666d  call    WPP_SF_d
0x140016672  mov     eax, edi
0x140016674  mov     rcx, [rsp+58h+var_18]
0x140016679  xor     rcx, rsp; StackCookie
0x14001667c  call    __security_check_cookie
0x140016681  mov     rbx, [rsp+58h+arg_10]
0x140016686  mov     rsi, [rsp+58h+arg_18]
0x14001668b  add     rsp, 50h
0x14001668f  pop     rdi
0x140016690  retn
```
