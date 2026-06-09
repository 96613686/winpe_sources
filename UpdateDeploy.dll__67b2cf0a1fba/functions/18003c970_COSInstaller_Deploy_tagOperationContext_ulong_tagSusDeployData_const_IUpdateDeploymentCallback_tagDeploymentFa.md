# COSInstaller::Deploy(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions)

- ea: `0x18003c970`
- end: `0x18003cc08`
- name: `?Deploy@COSInstaller@@UEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x18003bd48`
- `0x18003bf88`
- `0x18003c970`
- `0x18003cc10`
- `0x18003d2b8`
- `0x18003d7a8`
- `0x180043464`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003ca22`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003ca22`

## string_xrefs

- `0x18003cae2`: `Commit`
- `0x18003cb88`: `Install`
- `0x18003cb45`: `Uninstall`
- `0x18003c9b8`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003caa8`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003cb54`: `Deployment handler does not support uninstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall COSInstaller::Deploy(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, int a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  _QWORD v15[5]; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v18; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  const char *v20; // [rsp+90h] [rbp-70h] BYREF
  void *v21; // [rsp+98h] [rbp-68h]
  void *lpMem; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+A8h] [rbp-58h]
  __int128 v24; // [rsp+B8h] [rbp-48h]
  __int128 v25; // [rsp+C8h] [rbp-38h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  _BYTE v27[8]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 UnbiasedTime[4]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v18 = a3;
  if ( !a3 )
  {
    v9 = -2145124316;
    v10 = 133;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v9,
      v14);
    return v9;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    v10 = 134;
    goto LABEL_3;
  }
  v17 = 0;
  v20 = 0;
  v21 = 0;
  lpMem = 0;
  v23 = 0;
  v26 = 0;
  v24 = 0;
  v19[0] = 0;
  v25 = 0;
  CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v27);
  UnbiasedTime[2] = 0;
  QueryUnbiasedInterruptTime(UnbiasedTime);
  OSDeploymentEventSummary::GenerateCV((OSDeploymentEventSummary *)&v20);
  v15[0] = v27;
  v16 = 1;
  v15[1] = &v20;
  v15[2] = &v18;
  v15[3] = v19;
  v15[4] = &v17;
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _DWORD *))(*(_QWORD *)a1 + 48LL))(a1, v18, a4, v19);
  v9 = v17;
  if ( v17 >= 0 )
  {
    if ( v19[0] )
    {
      switch ( *(_DWORD *)(a4 + 288) )
      {
        case 1:
          v20 = "Install";
          v12 = COSInstaller::Install(a1, a2, v18, a4, a5, a6, v21);
          break;
        case 2:
          v20 = "Uninstall";
          WUTrace(0, 0, 4096, 3);
          v9 = -2145116156;
          v17 = -2145116156;
          goto LABEL_20;
        case 4:
          v20 = "Revert";
          v12 = COSInstaller::Revert(a1, a2, v18, a4, a5, a6, v21);
          break;
        case 8:
          v20 = "Commit";
          v12 = COSInstaller::Commit(a1, v18, a4, a5, a6, v21);
          break;
        default:
          goto LABEL_20;
      }
      v9 = v12;
      v17 = v12;
      goto LABEL_20;
    }
    v9 = -2145116156;
    v11 = 157;
    v17 = -2145116156;
  }
  else
  {
    v11 = 153;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)v9,
    v14);
LABEL_20:
  wil::details::lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___::_lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___(v15);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v21 )
    SusFree(v21);
  return v9;
}

```

## disassembly

```asm
0x18003c970  push    rbp
0x18003c972  push    rbx
0x18003c973  push    rsi
0x18003c974  push    rdi
0x18003c975  push    r14
0x18003c977  push    r15
0x18003c979  lea     rbp, [rsp-18h]
0x18003c97e  sub     rsp, 118h
0x18003c985  mov     rax, cs:__security_cookie
0x18003c98c  xor     rax, rsp
0x18003c98f  mov     [rbp+40h+var_38], rax
0x18003c993  mov     r14, [rbp+40h+arg_20]
0x18003c997  mov     rdi, r9
0x18003c99a  mov     [rsp+140h+var_C8], r8d
0x18003c99f  mov     r15, rdx
0x18003c9a2  mov     rsi, rcx
0x18003c9a5  test    r8d, r8d
0x18003c9a8  jnz     short loc_18003C9CC
0x18003c9aa  mov     ebx, 80240024h
0x18003c9af  mov     edx, 85h; void *
0x18003c9b4  mov     rcx, [rbp+48h]; this
0x18003c9b8  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003c9bf  mov     r9d, ebx; char *
0x18003c9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c9c7  jmp     loc_18003CBEA
0x18003c9cc  test    rdi, rdi
0x18003c9cf  jnz     short loc_18003C9DD
0x18003c9d1  mov     ebx, 80004003h
0x18003c9d6  mov     edx, 86h
0x18003c9db  jmp     short loc_18003C9B4
0x18003c9dd  xor     eax, eax
0x18003c9df  mov     [rsp+140h+var_D0], 0
0x18003c9e7  xorps   xmm0, xmm0
0x18003c9ea  mov     [rbp+40h+var_B0], rax
0x18003c9ee  lea     rcx, [rbp+40h+var_60]; this
0x18003c9f2  mov     [rbp+40h+var_A8], rax
0x18003c9f6  mov     [rbp+40h+lpMem], rax
0x18003c9fa  movups  [rbp+40h+var_98], xmm0
0x18003c9fe  mov     [rbp+40h+var_68], rax
0x18003ca02  movups  [rbp+40h+var_88], xmm0
0x18003ca06  mov     [rbp+40h+var_C0], 0
0x18003ca0d  movups  [rbp+40h+var_78], xmm0
0x18003ca11  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x18003ca16  lea     rcx, [rbp+40h+UnbiasedTime]; UnbiasedTime
0x18003ca1a  mov     [rbp+40h+var_48], 0
0x18003ca22  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003ca28  lea     rcx, [rbp+40h+var_B0]; this
0x18003ca2c  call    ?GenerateCV@OSDeploymentEventSummary@@QEAAXXZ; OSDeploymentEventSummary::GenerateCV(void)
0x18003ca31  mov     edx, [rsp+140h+var_C8]
0x18003ca35  lea     rax, [rbp+40h+var_60]
0x18003ca39  mov     [rsp+140h+var_100], rax
0x18003ca3e  lea     r9, [rbp+40h+var_C0]
0x18003ca42  lea     rax, [rbp+40h+var_B0]
0x18003ca46  mov     [rsp+140h+var_D8], 1
0x18003ca4b  mov     [rsp+140h+var_F8], rax
0x18003ca50  mov     r8, rdi
0x18003ca53  lea     rax, [rsp+140h+var_C8]
0x18003ca58  mov     rcx, rsi
0x18003ca5b  mov     [rsp+140h+var_F0], rax
0x18003ca60  lea     rax, [rbp+40h+var_C0]
0x18003ca64  mov     [rsp+140h+var_E8], rax
0x18003ca69  lea     rax, [rsp+140h+var_D0]
0x18003ca6e  mov     [rsp+140h+var_E0], rax
0x18003ca73  mov     rax, [rsi]
0x18003ca76  mov     rax, [rax+30h]
0x18003ca7a  call    _guard_dispatch_icall
0x18003ca7f  mov     [rsp+140h+var_D0], eax
0x18003ca83  mov     ebx, eax
0x18003ca85  test    eax, eax
0x18003ca87  jns     short loc_18003CA90
0x18003ca89  mov     edx, 99h
0x18003ca8e  jmp     short loc_18003CAA4
0x18003ca90  cmp     [rbp+40h+var_C0], 0
0x18003ca94  jnz     short loc_18003CABC
0x18003ca96  mov     ebx, 80242004h
0x18003ca9b  mov     edx, 9Dh; void *
0x18003caa0  mov     [rsp+140h+var_D0], ebx
0x18003caa4  mov     rcx, [rbp+48h]; this
0x18003caa8  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003caaf  mov     r9d, ebx; char *
0x18003cab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cab7  jmp     loc_18003CBBC
0x18003cabc  mov     edx, [rdi+120h]
0x18003cac2  sub     edx, 1
0x18003cac5  jz      loc_18003CB83
0x18003cacb  sub     edx, 1
0x18003cace  jz      short loc_18003CB45
0x18003cad0  sub     edx, 2
0x18003cad3  jz      short loc_18003CB10
0x18003cad5  cmp     edx, 4
0x18003cad8  jnz     loc_18003CBBC
0x18003cade  mov     edx, [rsp+140h+var_C8]
0x18003cae2  lea     rax, aCommit_0; "Commit"
0x18003cae9  mov     [rbp+40h+var_B0], rax
0x18003caed  mov     r9, r14
0x18003caf0  mov     rax, [rbp+40h+var_A8]
0x18003caf4  mov     r8, rdi
0x18003caf7  mov     [rsp+140h+var_118], rax
0x18003cafc  mov     rcx, rsi
0x18003caff  mov     eax, [rbp+40h+arg_28]
0x18003cb02  mov     dword ptr [rsp+140h+var_120], eax
0x18003cb06  call    ?Commit@COSInstaller@@AEAAJKQEBUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Commit(ulong,tagSusDeployData const * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x18003cb0b  jmp     loc_18003CBB6
0x18003cb10  mov     r8d, [rsp+140h+var_C8]
0x18003cb15  lea     rax, aRevert; "Revert"
0x18003cb1c  mov     [rbp+40h+var_B0], rax
0x18003cb20  mov     r9, rdi
0x18003cb23  mov     rax, [rbp+40h+var_A8]
0x18003cb27  mov     rdx, r15
0x18003cb2a  mov     [rsp+140h+var_110], rax
0x18003cb2f  mov     rcx, rsi
0x18003cb32  mov     eax, [rbp+40h+arg_28]
0x18003cb35  mov     dword ptr [rsp+140h+var_118], eax
0x18003cb39  mov     [rsp+140h+var_120], r14
0x18003cb3e  call    ?Revert@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Revert(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x18003cb43  jmp     short loc_18003CBB6
0x18003cb45  lea     rax, aUninstall_0; "Uninstall"
0x18003cb4c  xor     edx, edx
0x18003cb4e  mov     [rbp+40h+var_B0], rax
0x18003cb52  xor     ecx, ecx
0x18003cb54  lea     rax, aDeploymentHand; "Deployment handler does not support uni"...
0x18003cb5b  mov     r8d, 1000h
0x18003cb61  mov     [rsp+140h+var_118], rax
0x18003cb66  lea     r9d, [rdx+3]
0x18003cb6a  mov     [rsp+140h+var_120], 0
0x18003cb73  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003cb78  mov     ebx, 80242004h
0x18003cb7d  mov     [rsp+140h+var_D0], ebx
0x18003cb81  jmp     short loc_18003CBBC
0x18003cb83  mov     r8d, [rsp+140h+var_C8]
0x18003cb88  lea     rax, aInstall_0; "Install"
0x18003cb8f  mov     [rbp+40h+var_B0], rax
0x18003cb93  mov     r9, rdi
0x18003cb96  mov     rax, [rbp+40h+var_A8]
0x18003cb9a  mov     rdx, r15
0x18003cb9d  mov     [rsp+140h+var_110], rax
0x18003cba2  mov     rcx, rsi
0x18003cba5  mov     eax, [rbp+40h+arg_28]
0x18003cba8  mov     dword ptr [rsp+140h+var_118], eax
0x18003cbac  mov     [rsp+140h+var_120], r14
0x18003cbb1  call    ?Install@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Install(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x18003cbb6  mov     ebx, eax
0x18003cbb8  mov     [rsp+140h+var_D0], eax
0x18003cbbc  lea     rcx, [rsp+140h+var_100]
0x18003cbc1  call    wil__details__lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103______lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___
0x18003cbc6  mov     rcx, [rbp+40h+lpMem]; lpMem
0x18003cbca  test    rcx, rcx
0x18003cbcd  jz      short loc_18003CBDC
0x18003cbcf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003cbd4  mov     [rbp+40h+lpMem], 0
0x18003cbdc  mov     rcx, [rbp+40h+var_A8]; lpMem
0x18003cbe0  test    rcx, rcx
0x18003cbe3  jz      short loc_18003CBEA
0x18003cbe5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003cbea  mov     eax, ebx
0x18003cbec  mov     rcx, [rbp+40h+var_38]
0x18003cbf0  xor     rcx, rsp; StackCookie
0x18003cbf3  call    __security_check_cookie
0x18003cbf8  add     rsp, 118h
0x18003cbff  pop     r15
0x18003cc01  pop     r14
0x18003cc03  pop     rdi
0x18003cc04  pop     rsi
0x18003cc05  pop     rbx
0x18003cc06  pop     rbp
0x18003cc07  retn
```
