# ResealTpmBinding(void *)

- ea: `0x180039268`
- end: `0x1800393b3`
- name: `?ResealTpmBinding@@YAJPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035870`

## callees

- `0x180039268`
- `0x1800394b0`
- `0x18003c0b8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003928a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800392af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800392f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003928a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800392af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800392f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392c4`

## string_xrefs

- `0x1800392a8`: `FveCommitChanges`
- `0x1800392bd`: `GetProcAddressFveCommitChanges`
- `0x1800392ed`: `FveCommitChangesEx`
- `0x180039359`: `CommitChanges`
- `0x180039366`: `CommitChangesEx`
- `0x18003937d`: `CommitChangesOld`

## pseudocode

```c
__int64 __fastcall ResealTpmBinding(void *a1)
{
  FARPROC ProcAddress; // rbx
  const unsigned __int16 *v3; // rdi
  FARPROC v4; // rsi
  signed int LastError; // eax
  signed int v6; // ebx
  FARPROC v7; // rbp
  int v8; // eax
  int v9; // eax
  int v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  ProcAddress = GetProcAddress(fveapiDll, "FveKeyManagement");
  if ( !ProcAddress )
  {
    v3 = L"GetProcAddressFveKeyManagement";
    goto LABEL_5;
  }
  v4 = GetProcAddress(fveapiDll, "FveCommitChanges");
  if ( v4 )
  {
    v7 = GetProcAddress(fveapiDll, "FveCommitChangesEx");
    v8 = ((__int64 (__fastcall *)(void *, __int64, int *))ProcAddress)(a1, 4, &v11);
    v6 = v8;
    if ( v8 != 1 )
    {
      if ( v8 < 0 )
      {
        v3 = L"KeyManagement";
LABEL_20:
        SBServicingLogMessage(
          (wchar_t *)L"ResealTpmBinding failed with error %x actionString %ls",
          (unsigned int)v6,
          v3);
        SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ResealTpmBinding", v3);
        return (unsigned int)v6;
      }
      if ( v7 )
      {
        v9 = ((__int64 (__fastcall *)(void *, __int64))v7)(a1, 2);
        v6 = v9;
        if ( v9 == -2147024809 )
        {
          v6 = ((__int64 (__fastcall *)(void *))v4)(a1);
          if ( v6 < 0 )
          {
            v3 = L"CommitChanges";
            goto LABEL_20;
          }
        }
        else if ( v9 < 0 )
        {
          v3 = L"CommitChangesEx";
          goto LABEL_20;
        }
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(void *))v4)(a1);
        if ( v6 < 0 )
        {
          v3 = L"CommitChangesOld";
          goto LABEL_20;
        }
      }
    }
    return 0;
  }
  v3 = L"GetProcAddressFveCommitChanges";
LABEL_5:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_20;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039268  push    rbx
0x18003926a  push    rbp
0x18003926b  push    rsi
0x18003926c  push    rdi
0x18003926d  sub     rsp, 28h
0x180039271  mov     rdi, rcx
0x180039274  mov     [rsp+48h+arg_8], 0
0x18003927c  mov     rcx, cs:?fveapiDll@@3PEAUHINSTANCE__@@EA; hModule
0x180039283  lea     rdx, aFvekeymanageme; "FveKeyManagement"
0x18003928a  call    cs:__imp_GetProcAddress
0x180039290  mov     rbx, rax
0x180039293  test    rax, rax
0x180039296  jnz     short loc_1800392A1
0x180039298  lea     rdi, aGetprocaddress; "GetProcAddressFveKeyManagement"
0x18003929f  jmp     short loc_1800392C4
0x1800392a1  mov     rcx, cs:?fveapiDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800392a8  lea     rdx, aFvecommitchang_3; "FveCommitChanges"
0x1800392af  call    cs:__imp_GetProcAddress
0x1800392b5  mov     rsi, rax
0x1800392b8  test    rax, rax
0x1800392bb  jnz     short loc_1800392E6
0x1800392bd  lea     rdi, aGetprocaddress_0; "GetProcAddressFveCommitChanges"
0x1800392c4  call    cs:__imp_GetLastError
0x1800392ca  mov     ebx, eax
0x1800392cc  test    eax, eax
0x1800392ce  jle     short loc_1800392D9
0x1800392d0  movzx   ebx, ax
0x1800392d3  or      ebx, 80070000h
0x1800392d9  test    ebx, ebx
0x1800392db  jns     loc_1800393A8
0x1800392e1  jmp     loc_180039384
0x1800392e6  mov     rcx, cs:?fveapiDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800392ed  lea     rdx, aFvecommitchang_2; "FveCommitChangesEx"
0x1800392f4  call    cs:__imp_GetProcAddress
0x1800392fa  lea     r8, [rsp+48h+arg_8]
0x1800392ff  mov     edx, 4
0x180039304  mov     rbp, rax
0x180039307  mov     rcx, rdi
0x18003930a  mov     rax, rbx
0x18003930d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039312  mov     ebx, eax
0x180039314  cmp     eax, 1
0x180039317  jz      loc_1800393A6
0x18003931d  test    eax, eax
0x18003931f  jns     short loc_18003932A
0x180039321  lea     rdi, aKeymanagement; "KeyManagement"
0x180039328  jmp     short loc_180039384
0x18003932a  mov     rcx, rdi
0x18003932d  test    rbp, rbp
0x180039330  jz      short loc_18003936F
0x180039332  mov     edx, 2
0x180039337  mov     rax, rbp
0x18003933a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003933f  mov     ebx, eax
0x180039341  cmp     eax, 80070057h
0x180039346  jnz     short loc_180039362
0x180039348  mov     rcx, rdi
0x18003934b  mov     rax, rsi
0x18003934e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039353  mov     ebx, eax
0x180039355  test    eax, eax
0x180039357  jns     short loc_1800393A6
0x180039359  lea     rdi, aCommitchanges; "CommitChanges"
0x180039360  jmp     short loc_180039384
0x180039362  test    eax, eax
0x180039364  jns     short loc_1800393A6
0x180039366  lea     rdi, aCommitchangese; "CommitChangesEx"
0x18003936d  jmp     short loc_180039384
0x18003936f  mov     rax, rsi
0x180039372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039377  mov     ebx, eax
0x180039379  test    eax, eax
0x18003937b  jns     short loc_1800393A6
0x18003937d  lea     rdi, aCommitchangeso; "CommitChangesOld"
0x180039384  mov     r8, rdi
0x180039387  lea     rcx, aResealtpmbindi_0; "ResealTpmBinding failed with error %x a"...
0x18003938e  mov     edx, ebx
0x180039390  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180039395  mov     rdx, rdi; unsigned __int16 *
0x180039398  lea     rcx, aResealtpmbindi; "ResealTpmBinding"
0x18003939f  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x1800393a4  jmp     short loc_1800393A8
0x1800393a6  xor     ebx, ebx
0x1800393a8  mov     eax, ebx
0x1800393aa  add     rsp, 28h
0x1800393ae  pop     rdi
0x1800393af  pop     rsi
0x1800393b0  pop     rbp
0x1800393b1  pop     rbx
0x1800393b2  retn
```
