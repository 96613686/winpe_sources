# VerifyInfFile

- ea: `0x140015f08`
- end: `0x1400161b5`
- name: `VerifyInfFile`
- size: `685`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140014e08`

## callees

- `0x1400070bc`
- `0x14000bb4c`
- `0x14000bcbc`
- `0x14000c354`
- `0x140013d70`
- `0x140015f08`
- `0x14002e0d4`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015fed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016185`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016185`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140015f62`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140015f62`
- `DEVRTL!DevRtlCloseTextLogSection` at `0x140016170`
- `DEVRTL!DevRtlCloseTextLogSection` at `0x140016170`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x140015f84`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x140015f84`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140015f96`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001617d`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140015f96`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001617d`
- `drvstore!DriverPackageClose` at `0x14001615e`
- `drvstore!DriverPackageClose` at `0x14001615e`
- `drvstore!DriverPackageOpenW` at `0x140015fda`
- `drvstore!DriverPackageOpenW` at `0x140015fda`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140016011`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140016011`

## pseudocode

```c
__int64 __fastcall VerifyInfFile(size_t *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rsi
  int v8; // r15d
  __int64 v9; // rdx
  __int64 v10; // rax
  DWORD LastError; // edi
  unsigned int v12; // r11d
  int v13; // eax
  int FileTitle; // eax
  int v15; // edx
  __int64 v16; // r10
  int v18; // [rsp+64h] [rbp-964h] BYREF
  int v19; // [rsp+68h] [rbp-960h]
  __int64 ThreadLogToken; // [rsp+70h] [rbp-958h] BYREF
  __int64 v21; // [rsp+78h] [rbp-950h]
  _DWORD v22[178]; // [rsp+80h] [rbp-948h] BYREF
  _BYTE v23[540]; // [rsp+348h] [rbp-680h] BYREF
  _BYTE v24[524]; // [rsp+564h] [rbp-464h] BYREF
  unsigned __int16 v25[264]; // [rsp+770h] [rbp-258h] BYREF

  v6 = 0;
  v7 = 0;
  v21 = 0;
  memset_0(v22, 0, 0x6F0u);
  v18 = 0;
  v8 = 0;
  v19 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( !ThreadLogToken )
  {
    v8 = DevRtlCreateTextLogSectionW(a1, 1, L"VerifyInfFile", &ThreadLogToken);
    v19 = v8;
    DevRtlSetThreadLogToken(ThreadLogToken);
  }
  if ( a1 && a3 && *(_DWORD *)a3 == 1568 )
  {
    if ( a2 )
      v9 = *(unsigned __int16 *)(a2 + 16);
    else
      v9 = 0xFFFF;
    v10 = DriverPackageOpenW(a1, v9, 0, 0, 0);
    v7 = v10;
    v21 = v10;
    if ( v10 && (v22[0] = 1776, (unsigned int)DriverPackageGetVersionInfoW(v10, v22)) )
    {
      if ( (int)StringCchCopyW(v25, 0x104u, a1) >= 0
        && (unsigned int)pSetupTrimFileTitle(v25)
        && (unsigned int)pSetupConcatenatePaths(v25, v24, v12) )
      {
        *(_WORD *)(a3 + 4) = 0;
        *(_WORD *)(a3 + 524) = 0;
        *(_WORD *)(a3 + 1044) = 0;
        if ( (unsigned int)SpSignSkipValidation() )
        {
          LastError = 0;
          v13 = 218103812;
          v18 = 218103812;
        }
        else
        {
          FileTitle = pSetupGetFileTitle(a1);
          LastError = SpSignVerifyInfFile(
                        ThreadLogToken,
                        v15,
                        (_DWORD)a1,
                        FileTitle,
                        v16,
                        (__int64)v23,
                        a2,
                        a3 + 4,
                        a3 + 524,
                        a3 + 1044,
                        (__int64)&v18);
          v13 = v18;
        }
        if ( *(_DWORD *)a3 >= 0x620u )
          *(_DWORD *)(a3 + 1564) = v13;
      }
      else
      {
        LastError = 13;
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  if ( v7 )
    DriverPackageClose(v7);
  if ( v8 )
  {
    DevRtlCloseTextLogSection(ThreadLogToken, LastError);
    ThreadLogToken = 0;
    DevRtlSetThreadLogToken(0);
  }
  SetLastError(LastError);
  LOBYTE(v6) = LastError == 0;
  return v6;
}

```

## disassembly

```asm
0x140015f08  push    rbx
0x140015f0a  push    rsi
0x140015f0b  push    rdi
0x140015f0c  push    r12
0x140015f0e  push    r13
0x140015f10  push    r14
0x140015f12  push    r15
0x140015f14  sub     rsp, 990h
0x140015f1b  mov     rax, cs:__security_cookie
0x140015f22  xor     rax, rsp
0x140015f25  mov     [rsp+9C8h+var_48], rax
0x140015f2d  mov     r14, r8
0x140015f30  mov     r13, rdx
0x140015f33  mov     rdi, rcx
0x140015f36  xor     ebx, ebx
0x140015f38  mov     esi, ebx
0x140015f3a  mov     [rsp+9C8h+var_950], rbx
0x140015f3f  mov     r12d, 6F0h
0x140015f45  mov     r8d, r12d; Size
0x140015f48  xor     edx, edx; Val
0x140015f4a  lea     rcx, [rsp+9C8h+var_948]; void *
0x140015f52  call    memset_0
0x140015f57  mov     [rsp+9C8h+var_964], ebx
0x140015f5b  mov     r15d, ebx
0x140015f5e  mov     [rsp+9C8h+var_960], ebx
0x140015f62  call    cs:__imp_DevRtlGetThreadLogToken
0x140015f68  mov     [rsp+9C8h+var_958], rax
0x140015f6d  test    rax, rax
0x140015f70  jnz     short loc_140015F9C
0x140015f72  lea     r9, [rsp+9C8h+var_958]
0x140015f77  lea     r8, aVerifyinffile; "VerifyInfFile"
0x140015f7e  lea     edx, [rbx+1]
0x140015f81  mov     rcx, rdi
0x140015f84  call    cs:__imp_DevRtlCreateTextLogSectionW
0x140015f8a  mov     r15d, eax
0x140015f8d  mov     [rsp+9C8h+var_960], eax
0x140015f91  mov     rcx, [rsp+9C8h+var_958]
0x140015f96  call    cs:__imp_DevRtlSetThreadLogToken
0x140015f9c  test    rdi, rdi
0x140015f9f  jz      loc_140016151
0x140015fa5  test    r14, r14
0x140015fa8  jz      loc_140016151
0x140015fae  cmp     dword ptr [r14], 620h
0x140015fb5  jnz     loc_140016151
0x140015fbb  test    r13, r13
0x140015fbe  jz      short loc_140015FC7
0x140015fc0  movzx   edx, word ptr [r13+10h]
0x140015fc5  jmp     short loc_140015FCC
0x140015fc7  mov     edx, 0FFFFh
0x140015fcc  mov     [rsp+9C8h+var_9A8], rbx
0x140015fd1  xor     r9d, r9d
0x140015fd4  xor     r8d, r8d
0x140015fd7  mov     rcx, rdi
0x140015fda  call    cs:__imp_DriverPackageOpenW
0x140015fe0  mov     rsi, rax
0x140015fe3  mov     [rsp+9C8h+var_950], rax
0x140015fe8  test    rax, rax
0x140015feb  jnz     short loc_140015FFE
0x140015fed  call    cs:__imp_GetLastError
0x140015ff3  mov     edi, eax
0x140015ff5  mov     [rsp+9C8h+var_968], eax
0x140015ff9  jmp     loc_140016138
0x140015ffe  mov     [rsp+9C8h+var_948], r12d
0x140016006  lea     rdx, [rsp+9C8h+var_948]
0x14001600e  mov     rcx, rax
0x140016011  call    cs:__imp_DriverPackageGetVersionInfoW
0x140016017  test    eax, eax
0x140016019  jz      short loc_140015FED
0x14001601b  mov     r8, rdi; unsigned __int16 *
0x14001601e  mov     r11d, 104h
0x140016024  mov     edx, r11d; unsigned __int64
0x140016027  lea     rcx, [rsp+9C8h+var_258]; unsigned __int16 *
0x14001602f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140016034  test    eax, eax
0x140016036  js      loc_14001612F
0x14001603c  lea     rcx, [rsp+9C8h+var_258]
0x140016044  call    pSetupTrimFileTitle
0x140016049  test    eax, eax
0x14001604b  jz      loc_14001612F
0x140016051  mov     r8d, r11d
0x140016054  lea     rdx, [rsp+9C8h+var_464]
0x14001605c  lea     rcx, [rsp+9C8h+var_258]
0x140016064  call    pSetupConcatenatePaths
0x140016069  test    eax, eax
0x14001606b  jz      loc_14001612F
0x140016071  lea     r12, [r14+4]
0x140016075  mov     [r12], bx
0x14001607a  mov     [r14+20Ch], bx
0x140016082  mov     [r14+414h], bx
0x14001608a  call    SpSignSkipValidation
0x14001608f  test    eax, eax
0x140016091  jz      short loc_1400160A4
0x140016093  mov     edi, ebx
0x140016095  mov     [rsp+9C8h+var_968], ebx
0x140016099  mov     eax, 0D000004h
0x14001609e  mov     [rsp+9C8h+var_964], eax
0x1400160a2  jmp     short loc_14001611D
0x1400160a4  movzx   eax, [rsp+9C8h+var_258]
0x1400160ac  neg     ax
0x1400160af  sbb     r10, r10
0x1400160b2  lea     rax, [rsp+9C8h+var_258]
0x1400160ba  and     r10, rax
0x1400160bd  mov     rcx, rdi
0x1400160c0  call    pSetupGetFileTitle
0x1400160c5  mov     r9, rax
0x1400160c8  lea     rax, [rsp+9C8h+var_964]
0x1400160cd  mov     [rsp+9C8h+var_978], rax
0x1400160d2  lea     rax, [r14+414h]
0x1400160d9  mov     [rsp+9C8h+var_980], rax
0x1400160de  lea     rax, [r14+20Ch]
0x1400160e5  mov     [rsp+9C8h+var_988], rax
0x1400160ea  mov     [rsp+9C8h+var_990], r12
0x1400160ef  mov     [rsp+9C8h+var_998], r13
0x1400160f4  lea     rax, [rsp+9C8h+var_680]
0x1400160fc  mov     [rsp+9C8h+var_9A0], rax
0x140016101  mov     [rsp+9C8h+var_9A8], r10
0x140016106  mov     r8, rdi
0x140016109  mov     rcx, [rsp+9C8h+var_958]
0x14001610e  call    SpSignVerifyInfFile
0x140016113  mov     edi, eax
0x140016115  mov     [rsp+9C8h+var_968], eax
0x140016119  mov     eax, [rsp+9C8h+var_964]
0x14001611d  cmp     dword ptr [r14], 620h
0x140016124  jb      short loc_140016138
0x140016126  mov     [r14+61Ch], eax
0x14001612d  jmp     short loc_140016138
0x14001612f  mov     edi, 0Dh
0x140016134  mov     [rsp+9C8h+var_968], edi
0x140016138  jmp     short loc_140016156
0x14001613a  mov     edi, 0Dh
0x14001613f  mov     [rsp+9C8h+var_968], edi
0x140016143  xor     ebx, ebx
0x140016145  mov     rsi, [rsp+9C8h+var_950]
0x14001614a  mov     r15d, [rsp+9C8h+var_960]
0x14001614f  jmp     short loc_140016156
0x140016151  mov     edi, 57h ; 'W'
0x140016156  test    rsi, rsi
0x140016159  jz      short loc_140016164
0x14001615b  mov     rcx, rsi
0x14001615e  call    cs:__imp_DriverPackageClose
0x140016164  test    r15d, r15d
0x140016167  jz      short loc_140016183
0x140016169  mov     edx, edi
0x14001616b  mov     rcx, [rsp+9C8h+var_958]
0x140016170  call    cs:__imp_DevRtlCloseTextLogSection
0x140016176  mov     [rsp+9C8h+var_958], rbx
0x14001617b  xor     ecx, ecx
0x14001617d  call    cs:__imp_DevRtlSetThreadLogToken
0x140016183  mov     ecx, edi; dwErrCode
0x140016185  call    cs:__imp_SetLastError
0x14001618b  test    edi, edi
0x14001618d  setz    bl
0x140016190  mov     eax, ebx
0x140016192  mov     rcx, [rsp+9C8h+var_48]
0x14001619a  xor     rcx, rsp; StackCookie
0x14001619d  call    __security_check_cookie
0x1400161a2  add     rsp, 990h
0x1400161a9  pop     r15
0x1400161ab  pop     r14
0x1400161ad  pop     r13
0x1400161af  pop     r12
0x1400161b1  pop     rdi
0x1400161b2  pop     rsi
0x1400161b3  pop     rbx
0x1400161b4  retn
```
