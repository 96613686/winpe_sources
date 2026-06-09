# JobExecution::OmaDmMsiConfirmSession(ushort const *,bool &)

- ea: `0x14000e09c`
- end: `0x14000e18c`
- name: `?OmaDmMsiConfirmSession@JobExecution@@CAJPEBGAEA_N@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000cd78`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x14000e09c`
- `0x14001a8aa`

## import_xrefs

- `KERNEL32!Sleep` at `0x14000e10c`
- `KERNEL32!Sleep` at `0x14000e10c`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x14000e0d8`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x14000e0d8`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x14000e169`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x14000e169`
- `omadmapi!__imp_OmaDmCloseSession` at `0x14000e14c`
- `omadmapi!__imp_OmaDmCloseSession` at `0x14000e14c`

## string_xrefs

- `0x14000e175`: `OmaDmMsiConfirmSession failed with Error 0x%1!x!`

## pseudocode

```c
__int64 __fastcall JobExecution::OmaDmMsiConfirmSession(const unsigned __int16 *a1, bool *a2)
{
  int v4; // ebx
  int InitiationInfo; // edi
  int v6; // ecx
  int v7; // ebx
  int v8; // eax
  _DWORD v10[26]; // [rsp+20h] [rbp-68h] BYREF

  memset_0(v10, 0, 0x40u);
  v10[0] = 64;
  if ( a1 )
  {
    v4 = 12;
    *a2 = 0;
    while ( 1 )
    {
      InitiationInfo = OmaDmGetInitiationInfo(a1, v10);
      if ( InitiationInfo < 0 )
        break;
      v6 = v4--;
      if ( v6 <= 0 )
        break;
      if ( ((v10[5] - 3) & 0xFFFFFFFD) == 0 )
      {
        LogInfo(L"Successfully confirmed OMADM alert notification.");
        *a2 = 1;
        break;
      }
      LogInfo(L"Waiting 10 seconds for notification to be processed...");
      Sleep(0x2710u);
    }
    if ( v4 )
    {
      v7 = 0;
      if ( InitiationInfo < 0 )
        v7 = InitiationInfo;
    }
    else
    {
      LogWarn(L"Timed out for waiting for OMADM notification.");
      v7 = -2147012894;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  v8 = OmaDmCloseSession(a1);
  if ( v8 < 0 )
    LogError(L"OmaDmCloseSession failed with Error 0x%1!x!", (unsigned int)v8);
  OmaDmFreeInitiationInfo(v10);
  if ( v7 < 0 )
    LogError(L"OmaDmMsiConfirmSession failed with Error 0x%1!x!", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000e09c  push    rbx
0x14000e09e  push    rbp
0x14000e09f  push    rsi
0x14000e0a0  push    rdi
0x14000e0a1  sub     rsp, 68h
0x14000e0a5  mov     rsi, rdx
0x14000e0a8  mov     rbp, rcx
0x14000e0ab  mov     ebx, 40h ; '@'
0x14000e0b0  lea     rcx, [rsp+88h+var_68]; void *
0x14000e0b5  mov     r8d, ebx; Size
0x14000e0b8  xor     edx, edx; Val
0x14000e0ba  call    memset_0
0x14000e0bf  mov     [rsp+88h+var_68], ebx
0x14000e0c3  test    rbp, rbp
0x14000e0c6  jz      short loc_14000E144
0x14000e0c8  mov     ebx, 0Ch
0x14000e0cd  mov     byte ptr [rsi], 0
0x14000e0d0  lea     rdx, [rsp+88h+var_68]
0x14000e0d5  mov     rcx, rbp
0x14000e0d8  call    cs:__imp_OmaDmGetInitiationInfo
0x14000e0de  mov     edi, eax
0x14000e0e0  test    eax, eax
0x14000e0e2  js      short loc_14000E123
0x14000e0e4  mov     ecx, ebx
0x14000e0e6  dec     ebx
0x14000e0e8  test    ecx, ecx
0x14000e0ea  jle     short loc_14000E123
0x14000e0ec  mov     ecx, [rsp+88h+var_54]
0x14000e0f0  add     ecx, 0FFFFFFFDh
0x14000e0f3  test    ecx, 0FFFFFFFDh
0x14000e0f9  jz      short loc_14000E114
0x14000e0fb  lea     rcx, aWaiting10Secon; "Waiting 10 seconds for notification to "...
0x14000e102  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e107  mov     ecx, 2710h; dwMilliseconds
0x14000e10c  call    cs:__imp_Sleep
0x14000e112  jmp     short loc_14000E0D0
0x14000e114  lea     rcx, aSuccessfullyCo_0; "Successfully confirmed OMADM alert noti"...
0x14000e11b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e120  mov     byte ptr [rsi], 1
0x14000e123  test    ebx, ebx
0x14000e125  jnz     short loc_14000E13A
0x14000e127  lea     rcx, aTimedOutForWai; "Timed out for waiting for OMADM notific"...
0x14000e12e  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000e133  mov     ebx, 80072EE2h
0x14000e138  jmp     short loc_14000E149
0x14000e13a  xor     ebx, ebx
0x14000e13c  test    edi, edi
0x14000e13e  jns     short loc_14000E149
0x14000e140  mov     ebx, edi
0x14000e142  jmp     short loc_14000E149
0x14000e144  mov     ebx, 80070057h
0x14000e149  mov     rcx, rbp
0x14000e14c  call    cs:__imp_OmaDmCloseSession
0x14000e152  test    eax, eax
0x14000e154  jns     short loc_14000E164
0x14000e156  mov     edx, eax
0x14000e158  lea     rcx, aOmadmclosesess; "OmaDmCloseSession failed with Error 0x%"...
0x14000e15f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000e164  lea     rcx, [rsp+88h+var_68]
0x14000e169  call    cs:__imp_OmaDmFreeInitiationInfo
0x14000e16f  test    ebx, ebx
0x14000e171  jns     short loc_14000E181
0x14000e173  mov     edx, ebx
0x14000e175  lea     rcx, aOmadmmsiconfir; "OmaDmMsiConfirmSession failed with Erro"...
0x14000e17c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000e181  mov     eax, ebx
0x14000e183  add     rsp, 68h
0x14000e187  pop     rdi
0x14000e188  pop     rsi
0x14000e189  pop     rbp
0x14000e18a  pop     rbx
0x14000e18b  retn
```
