# CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress(int *)

- ea: `0x14000300c`
- end: `0x140003145`
- name: `?s_CheckDiskProtectionUninstallInProgress@CWmsSelfHealingSvc@@CAJPEAH@Z`
- size: `313`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1400029e8`

## callees

- `0x14000300c`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140003067`
- `ADVAPI32!RegGetValueW` at `0x140003067`
- `KERNEL32!IsDebuggerPresent` at `0x1400030be`
- `KERNEL32!IsDebuggerPresent` at `0x1400030be`

## string_xrefs

- `0x140003092`: `CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress`
- `0x140003059`: `System\CurrentControlSet\Services\WMS\Parameters\`
- `0x140003031`: `DelayedUninstall`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress(int *a1)
{
  LSTATUS ValueW; // eax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+30h] [rbp-28h]
  unsigned int v6; // [rsp+38h] [rbp-20h]
  int v7; // [rsp+68h] [rbp+10h] BYREF
  DWORD v8; // [rsp+70h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
             L"DelayedUninstall",
             0x10u,
             0,
             &v7,
             &v8);
  v3 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      0x2AAu,
      L"CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      v3);
    if ( IsDebuggerPresent() )
    {
      v6 = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        682,
        L"CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v6);
    }
    else
    {
      LODWORD(v5) = v3;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        682,
        L"CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v5);
    }
  }
  else
  {
    v3 = 0;
    *a1 = v7 != 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14000300c  mov     r11, rsp
0x14000300f  mov     [r11+8], rbx
0x140003013  mov     [r11+20h], rdi
0x140003017  push    r12
0x140003019  push    r14
0x14000301b  push    r15
0x14000301d  sub     rsp, 40h
0x140003021  lea     rax, [r11+18h]
0x140003025  mov     [rsp+58h+arg_8], 0
0x14000302d  mov     [r11-28h], rax
0x140003031  lea     r8, Value; "DelayedUninstall"
0x140003038  lea     rax, [r11+10h]
0x14000303c  mov     [rsp+58h+arg_10], 4
0x140003044  mov     rdi, rcx
0x140003047  mov     [r11-30h], rax
0x14000304b  mov     r9d, 10h; dwFlags
0x140003051  mov     qword ptr [r11-38h], 0
0x140003059  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WM"...
0x140003060  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003067  call    cs:__imp_RegGetValueW
0x14000306d  mov     ebx, eax
0x14000306f  test    eax, 0FFFFFFFDh
0x140003074  jz      loc_140003121
0x14000307a  test    eax, eax
0x14000307c  jle     short loc_140003087
0x14000307e  movzx   ebx, ax
0x140003081  or      ebx, 80070000h
0x140003087  lea     r12, aCbraex; "CBRAEx"
0x14000308e  mov     [rsp+58h+var_30], ebx; int
0x140003092  lea     r14, aCwmsselfhealin_4; "CWmsSelfHealingSvc::s_CheckDiskProtecti"...
0x140003099  mov     edi, 2AAh
0x14000309e  lea     r15, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x1400030a5  mov     r9, r12; unsigned __int16 *
0x1400030a8  mov     r8, r14; unsigned __int16 *
0x1400030ab  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x1400030b0  mov     edx, edi; unsigned int
0x1400030b2  lea     rcx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400030b9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400030be  call    cs:__imp_IsDebuggerPresent
0x1400030c4  test    eax, eax
0x1400030c6  jz      short loc_1400030F8
0x1400030c8  mov     [rsp+58h+var_20], ebx
0x1400030cc  lea     r8, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400030d3  mov     [rsp+58h+var_28], r15
0x1400030d8  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400030df  mov     qword ptr [rsp+58h+var_30], r12
0x1400030e4  mov     r9d, edi
0x1400030e7  mov     ecx, 2; unsigned __int8
0x1400030ec  mov     [rsp+58h+var_38], r14
0x1400030f1  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400030f6  jmp     short loc_14000312E
0x1400030f8  mov     dword ptr [rsp+58h+var_28], ebx
0x1400030fc  lea     rdx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140003103  mov     qword ptr [rsp+58h+var_30], r15
0x140003108  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000310f  mov     r9, r14
0x140003112  mov     [rsp+58h+var_38], r12
0x140003117  mov     r8d, edi
0x14000311a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000311f  jmp     short loc_14000312E
0x140003121  xor     ecx, ecx
0x140003123  xor     ebx, ebx
0x140003125  cmp     [rsp+58h+arg_8], ecx
0x140003129  setnz   cl
0x14000312c  mov     [rdi], ecx
0x14000312e  mov     rdi, [rsp+58h+arg_18]
0x140003133  mov     eax, ebx
0x140003135  mov     rbx, [rsp+58h+arg_0]
0x14000313a  add     rsp, 40h
0x14000313e  pop     r15
0x140003140  pop     r14
0x140003142  pop     r12
0x140003144  retn
```
