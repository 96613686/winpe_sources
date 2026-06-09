# SuspRunStartupAppTask(_SYSPREP_OS_OFFLINE *,StartupScanFlags)

- ea: `0x180003610`
- end: `0x180003881`
- name: `?SuspRunStartupAppTask@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800019a0`
- `0x180001a00`
- `0x180001a60`

## callees

- `0x180001bc0`
- `0x180002c64`
- `0x180003164`
- `0x180003478`
- `0x180003610`
- `0x180003f24`
- `0x180004102`
- `0x180004130`

## import_xrefs

- `msvcrt!wcschr` at `0x1800036db`
- `msvcrt!wcschr` at `0x1800036db`

## pseudocode

```c
__int64 __fastcall SuspRunStartupAppTask(__int64 a1, unsigned int a2)
{
  _QWORD *v2; // rdi
  const wchar_t *v4; // rcx
  unsigned int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // r15
  __int64 v9; // rbx
  const wchar_t *v10; // rsi
  wchar_t *v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  _QWORD *v18; // rcx
  BOOL v19; // esi
  unsigned int v20; // edi
  unsigned int v21; // r14d
  unsigned int v22; // ebx
  const wchar_t *v24; // [rsp+30h] [rbp-50h]
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  int v26; // [rsp+40h] [rbp-40h]
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  int v28; // [rsp+50h] [rbp-30h]
  wchar_t String2[12]; // [rsp+58h] [rbp-28h] BYREF

  v2 = WPP_GLOBAL_Control;
  v25 = 0;
  v4 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
  v26 = 0;
  v24 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
  v27 = 0;
  v6 = 0;
  v28 = 0;
  while ( 2 )
  {
    v7 = v6;
    v8 = 0;
    do
    {
      v9 = qword_180006C70[v7];
      v10 = off_180006020[v8];
      if ( a1 )
      {
        if ( v9 == -2147483647 )
        {
          v9 = *(_QWORD *)(a1 + 8);
        }
        else
        {
          if ( v9 != -2147483646 || (wcscpy(String2, L"SOFTWARE"), wcsncmp_0(v10, String2, 8u)) )
          {
            v13 = -2147021886;
            if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
            {
              v14 = v2[2];
              v15 = 23;
              v16 = 3010;
LABEL_20:
              WPP_SF_D(v14, v15, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids, v16);
              return v13;
            }
            return v13;
          }
          v9 = *(_QWORD *)(a1 + 40);
          v11 = wcschr(v10, 0x5Cu);
          v4 = L"Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
          v24 = L"Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
          v10 = v11 + 1;
        }
      }
      v12 = SuspCountRegKeyPathStartupApps(&v25, v9, v10, v4, a2);
      if ( v12 >= 0 )
        goto LABEL_13;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_91e8665fb8f03560ae482285a745ac49_Traceguids,
          (unsigned __int16)v12);
LABEL_13:
        v2 = WPP_GLOBAL_Control;
      }
      v4 = v24;
      v8 = (unsigned int)(v8 + 1);
      v7 = v6;
    }
    while ( (unsigned int)v8 < 3 );
    if ( ++v6 < 2 )
      continue;
    break;
  }
  v17 = SuspCountFolderStartupApps(a1, a2, &v27);
  v13 = v17;
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v13;
    v16 = (unsigned __int16)v17;
    v15 = 24;
LABEL_25:
    v14 = v18[2];
    goto LABEL_20;
  }
  if ( (a2 & 1) != 0 )
    return 0;
  v19 = 0;
  v20 = v26 + v28;
  v21 = HIDWORD(v25) + HIDWORD(v27);
  v22 = v25 + v27;
  SuspUtilsSetTestValues(HIDWORD(v25) + HIDWORD(v27), v26 + v28, v25 + v27);
  if ( v20 > v22 )
    v19 = v21 >= 3;
  v13 = SuspRaiseNotification(v19);
  if ( (v13 & 0x80000000) == 0 )
    return 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = (unsigned __int16)v13;
    v15 = 25;
    goto LABEL_25;
  }
  return v13;
}

```

## disassembly

```asm
0x180003610  mov     [rsp-38h+arg_10], rbx
0x180003615  push    rbp
0x180003616  push    rsi
0x180003617  push    rdi
0x180003618  push    r12
0x18000361a  push    r13
0x18000361c  push    r14
0x18000361e  push    r15
0x180003620  mov     rbp, rsp
0x180003623  sub     rsp, 80h
0x18000362a  mov     rax, cs:__security_cookie
0x180003631  xor     rax, rsp
0x180003634  mov     [rbp+var_10], rax
0x180003638  mov     rdi, cs:WPP_GLOBAL_Control
0x18000363f  xor     eax, eax
0x180003641  mov     r13, rcx
0x180003644  mov     [rbp+var_48], rax
0x180003648  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000364f  mov     [rbp+var_40], eax
0x180003652  mov     [rbp+var_50], rcx
0x180003656  mov     r12d, edx
0x180003659  mov     [rbp+var_38], rax
0x18000365d  xor     r14d, r14d
0x180003660  mov     [rbp+var_30], eax
0x180003663  lea     rdx, cs:180000000h
0x18000366a  mov     eax, r14d
0x18000366d  xor     r15d, r15d
0x180003670  mov     rbx, ds:rva qword_180006C70[rdx+rax*8]
0x180003678  mov     rsi, ds:rva off_180006020[rdx+r15*8]; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"... ...
0x180003680  test    r13, r13
0x180003683  jz      short loc_1800036F0
0x180003685  cmp     rbx, 0FFFFFFFF80000001h
0x18000368c  jnz     short loc_180003694
0x18000368e  mov     rbx, [r13+8]
0x180003692  jmp     short loc_1800036F0
0x180003694  cmp     rbx, 0FFFFFFFF80000002h
0x18000369b  jnz     loc_18000377C
0x1800036a1  movups  xmm0, xmmword ptr cs:aSoftware; "SOFTWARE"
0x1800036a8  movzx   eax, word ptr cs:aSoftware+10h; ""
0x1800036af  lea     rdx, [rbp+String2]; String2
0x1800036b3  mov     r8d, 8; MaxCount
0x1800036b9  mov     [rbp+var_18], ax
0x1800036bd  mov     rcx, rsi; String1
0x1800036c0  movups  xmmword ptr [rbp+String2], xmm0
0x1800036c4  call    wcsncmp_0
0x1800036c9  test    eax, eax
0x1800036cb  jnz     loc_18000377C
0x1800036d1  mov     rbx, [r13+28h]
0x1800036d5  lea     edx, [rax+5Ch]; Ch
0x1800036d8  mov     rcx, rsi; Str
0x1800036db  call    cs:__imp_wcschr
0x1800036e1  lea     rcx, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Exp"...
0x1800036e8  mov     [rbp+var_50], rcx
0x1800036ec  lea     rsi, [rax+2]
0x1800036f0  mov     r9, rcx
0x1800036f3  mov     [rsp+80h+var_60], r12d
0x1800036f8  lea     rcx, [rbp+var_48]
0x1800036fc  mov     r8, rsi
0x1800036ff  mov     rdx, rbx
0x180003702  call    ?SuspCountRegKeyPathStartupApps@@YAJPEAU_SUS_COUNTS@@PEAUHKEY__@@PEBG2W4StartupScanFlags@@@Z; SuspCountRegKeyPathStartupApps(_SUS_COUNTS *,HKEY__ *,ushort const *,ushort const *,StartupScanFlags)
0x180003707  test    eax, eax
0x180003709  jns     short loc_18000373F
0x18000370b  mov     rdi, cs:WPP_GLOBAL_Control
0x180003712  lea     rsi, WPP_GLOBAL_Control
0x180003719  cmp     rdi, rsi
0x18000371c  jz      short loc_18000374D
0x18000371e  test    byte ptr [rdi+1Ch], 1
0x180003722  jz      short loc_18000374D
0x180003724  mov     rcx, [rdi+10h]
0x180003728  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x18000372f  movzx   r9d, ax
0x180003733  mov     edx, 0Fh
0x180003738  call    WPP_SF_D
0x18000373d  jmp     short loc_180003746
0x18000373f  lea     rsi, WPP_GLOBAL_Control
0x180003746  mov     rdi, cs:WPP_GLOBAL_Control
0x18000374d  mov     rcx, [rbp+var_50]
0x180003751  lea     rdx, cs:180000000h
0x180003758  inc     r15d
0x18000375b  mov     eax, r14d
0x18000375e  cmp     r15d, 3
0x180003762  jb      loc_180003670
0x180003768  mov     r15d, 1
0x18000376e  add     r14d, r15d
0x180003771  cmp     r14d, 2
0x180003775  jnb     short loc_1800037BB
0x180003777  jmp     loc_180003663
0x18000377c  mov     ebx, 80070BC2h
0x180003781  lea     rax, WPP_GLOBAL_Control
0x180003788  cmp     rdi, rax
0x18000378b  jz      loc_180003858
0x180003791  test    byte ptr [rdi+1Ch], 1
0x180003795  jz      loc_180003858
0x18000379b  mov     rcx, [rdi+10h]
0x18000379f  mov     edx, 17h
0x1800037a4  mov     r9d, 0BC2h
0x1800037aa  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x1800037b1  call    WPP_SF_D
0x1800037b6  jmp     loc_180003858
0x1800037bb  lea     r8, [rbp+var_38]
0x1800037bf  mov     edx, r12d
0x1800037c2  mov     rcx, r13
0x1800037c5  call    ?SuspCountFolderStartupApps@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@PEAU_SUS_COUNTS@@@Z; SuspCountFolderStartupApps(_SYSPREP_OS_OFFLINE *,StartupScanFlags,_SUS_COUNTS *)
0x1800037ca  mov     ebx, eax
0x1800037cc  test    eax, eax
0x1800037ce  jns     short loc_1800037F1
0x1800037d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037d7  cmp     rcx, rsi
0x1800037da  jz      short loc_180003858
0x1800037dc  test    [rcx+1Ch], r15b
0x1800037e0  jz      short loc_180003858
0x1800037e2  movzx   r9d, ax
0x1800037e6  mov     edx, 18h
0x1800037eb  mov     rcx, [rcx+10h]
0x1800037ef  jmp     short loc_1800037AA
0x1800037f1  test    r15b, r12b
0x1800037f4  jnz     short loc_180003856
0x1800037f6  mov     edi, [rbp+var_30]
0x1800037f9  xor     esi, esi
0x1800037fb  mov     r14d, dword ptr [rbp+var_38+4]
0x1800037ff  mov     ebx, dword ptr [rbp+var_38]
0x180003802  add     edi, [rbp+var_40]
0x180003805  add     r14d, dword ptr [rbp+var_48+4]
0x180003809  mov     edx, edi; unsigned int
0x18000380b  add     ebx, dword ptr [rbp+var_48]
0x18000380e  mov     ecx, r14d; unsigned int
0x180003811  mov     r8d, ebx; unsigned int
0x180003814  call    ?SuspUtilsSetTestValues@@YAKKKK@Z; SuspUtilsSetTestValues(ulong,ulong,ulong)
0x180003819  cmp     edi, ebx
0x18000381b  jbe     short loc_180003825
0x18000381d  cmp     r14d, 3
0x180003821  cmovnb  esi, r15d
0x180003825  mov     ecx, esi
0x180003827  call    ?SuspRaiseNotification@@YAJW4_SUS_NOTIFICATION@@@Z; SuspRaiseNotification(_SUS_NOTIFICATION)
0x18000382c  mov     ebx, eax
0x18000382e  test    eax, eax
0x180003830  jns     short loc_180003856
0x180003832  mov     rcx, cs:WPP_GLOBAL_Control
0x180003839  lea     rax, WPP_GLOBAL_Control
0x180003840  cmp     rcx, rax
0x180003843  jz      short loc_180003858
0x180003845  test    [rcx+1Ch], r15b
0x180003849  jz      short loc_180003858
0x18000384b  movzx   r9d, bx
0x18000384f  mov     edx, 19h
0x180003854  jmp     short loc_1800037EB
0x180003856  xor     ebx, ebx
0x180003858  mov     eax, ebx
0x18000385a  mov     rcx, [rbp+var_10]
0x18000385e  xor     rcx, rsp; StackCookie
0x180003861  call    __security_check_cookie
0x180003866  mov     rbx, [rsp+80h+arg_10]
0x18000386e  add     rsp, 80h
0x180003875  pop     r15
0x180003877  pop     r14
0x180003879  pop     r13
0x18000387b  pop     r12
0x18000387d  pop     rdi
0x18000387e  pop     rsi
0x18000387f  pop     rbp
0x180003880  retn
```
