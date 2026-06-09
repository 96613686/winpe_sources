# ReadGPDllNameFromReg(void)

- ea: `0x18002a4d8`
- end: `0x18002a6a1`
- name: `?ReadGPDllNameFromReg@@YAJXZ`
- size: `457`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002a710`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x18001eb5c`
- `0x18001f650`
- `0x18002a4d8`

## import_xrefs

- `fwbase!FwFree` at `0x18002a67d`
- `fwbase!FwFree` at `0x18002a67d`
- `fwbase!FwRegOpenKey` at `0x18002a530`
- `fwbase!FwRegOpenKey` at `0x18002a530`
- `fwbase!FwRegQueryString` at `0x18002a591`
- `fwbase!FwRegQueryString` at `0x18002a591`
- `fwbase!FwRegCloseKey` at `0x18002a673`
- `fwbase!FwRegCloseKey` at `0x18002a673`

## string_xrefs

- `0x18002a51a`: `SYSTEM\CurrentControlSet\Services\MPSSVC\Parameters`
- `0x18002a588`: `GPExtensionDLL`
- `0x18002a5eb`: `GPExtensionDLL`

## pseudocode

```c
__int64 ReadGPDllNameFromReg(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  LPCOLESTR v2; // rcx
  __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v7; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp-18h] BYREF
  int v9; // [rsp+40h] [rbp-10h] BYREF

  v7 = 0;
  v9 = 0;
  v8 = 0;
  v0 = FwRegOpenKey(-2147483646, L"SYSTEM\\CurrentControlSet\\Services\\MPSSVC\\Parameters", 1, &v7, &v9);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v3 = 10;
LABEL_23:
      v5 = (unsigned int)v0;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  if ( !v9 )
  {
    v1 = -2147024894;
    goto LABEL_25;
  }
  v0 = FwRegQueryString(v7, 0, L"GPExtensionDLL", &v8, &v9);
  v1 = v0;
  if ( v0 >= 0 )
  {
    if ( !v9 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      {
LABEL_16:
        v1 = -2147024894;
        if ( v2 != (LPCOLESTR)&WPP_GLOBAL_Control && (v2[14] & 1) != 0 )
        {
          v3 = 13;
          v5 = 2147942402LL;
LABEL_24:
          WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids, v5);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids,
        L"GPExtensionDLL");
      if ( !v9 )
      {
        v2 = WPP_GLOBAL_Control;
        goto LABEL_16;
      }
    }
    v0 = StringCchCopyW(&g_wszWfApiGp, v4, v8);
    v1 = v0;
    if ( v0 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v3 = 14;
        goto LABEL_23;
      }
    }
    goto LABEL_25;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v3 = 11;
    goto LABEL_23;
  }
LABEL_25:
  if ( v7 )
    FwRegCloseKey();
  FwFree(v8);
  return v1;
}

```

## disassembly

```asm
0x18002a4d8  mov     [rsp-8+arg_0], rbx
0x18002a4dd  mov     [rsp-8+arg_8], rdi
0x18002a4e2  push    rbp
0x18002a4e3  mov     rbp, rsp
0x18002a4e6  sub     rsp, 50h
0x18002a4ea  mov     rax, cs:__security_cookie
0x18002a4f1  xor     rax, rsp
0x18002a4f4  mov     [rbp+var_8], rax
0x18002a4f8  lea     rax, [rbp+var_10]
0x18002a4fc  mov     [rbp+var_20], 0
0x18002a504  lea     r9, [rbp+var_20]
0x18002a508  mov     [rsp+50h+var_30], rax
0x18002a50d  mov     r8d, 1
0x18002a513  mov     [rbp+var_10], 0
0x18002a51a  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\MP"...
0x18002a521  mov     [rbp+var_18], 0
0x18002a529  mov     rcx, 0FFFFFFFF80000002h
0x18002a530  call    cs:__imp_FwRegOpenKey
0x18002a536  mov     ebx, eax
0x18002a538  test    eax, eax
0x18002a53a  jns     short loc_18002A567
0x18002a53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a543  lea     rdi, WPP_GLOBAL_Control
0x18002a54a  cmp     rcx, rdi
0x18002a54d  jz      loc_18002A66A
0x18002a553  test    byte ptr [rcx+1Ch], 1
0x18002a557  jz      loc_18002A66A
0x18002a55d  mov     edx, 0Ah
0x18002a562  jmp     loc_18002A657
0x18002a567  cmp     [rbp+var_10], 0
0x18002a56b  jnz     short loc_18002A577
0x18002a56d  mov     ebx, 80070002h
0x18002a572  jmp     loc_18002A66A
0x18002a577  mov     rcx, [rbp+var_20]
0x18002a57b  lea     rax, [rbp+var_10]
0x18002a57f  lea     r9, [rbp+var_18]
0x18002a583  mov     [rsp+50h+var_30], rax
0x18002a588  lea     r8, aGpextensiondll; "GPExtensionDLL"
0x18002a58f  xor     edx, edx
0x18002a591  call    cs:__imp_FwRegQueryString
0x18002a597  mov     ebx, eax
0x18002a599  test    eax, eax
0x18002a59b  jns     short loc_18002A5C8
0x18002a59d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5a4  lea     rdi, WPP_GLOBAL_Control
0x18002a5ab  cmp     rcx, rdi
0x18002a5ae  jz      loc_18002A66A
0x18002a5b4  test    byte ptr [rcx+1Ch], 1
0x18002a5b8  jz      loc_18002A66A
0x18002a5be  mov     edx, 0Bh
0x18002a5c3  jmp     loc_18002A657
0x18002a5c8  cmp     [rbp+var_10], 0
0x18002a5cc  lea     rdi, WPP_GLOBAL_Control
0x18002a5d3  jnz     short loc_18002A62A
0x18002a5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5dc  cmp     rcx, rdi
0x18002a5df  jz      short loc_18002A610
0x18002a5e1  test    byte ptr [rcx+1Ch], 2
0x18002a5e5  jz      short loc_18002A610
0x18002a5e7  mov     rcx, [rcx+10h]
0x18002a5eb  lea     r9, aGpextensiondll; "GPExtensionDLL"
0x18002a5f2  mov     edx, 0Ch
0x18002a5f7  lea     r8, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids
0x18002a5fe  call    WPP_SF_S
0x18002a603  cmp     [rbp+var_10], 0
0x18002a607  jnz     short loc_18002A62A
0x18002a609  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a610  mov     ebx, 80070002h
0x18002a615  cmp     rcx, rdi
0x18002a618  jz      short loc_18002A66A
0x18002a61a  test    byte ptr [rcx+1Ch], 1
0x18002a61e  jz      short loc_18002A66A
0x18002a620  mov     edx, 0Dh
0x18002a625  mov     r9d, ebx
0x18002a628  jmp     short loc_18002A65A
0x18002a62a  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18002a62e  lea     rcx, ?g_wszWfApiGp@@3PAGA; unsigned __int16 *
0x18002a635  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a63a  mov     ebx, eax
0x18002a63c  test    eax, eax
0x18002a63e  jns     short loc_18002A66A
0x18002a640  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a647  cmp     rcx, rdi
0x18002a64a  jz      short loc_18002A66A
0x18002a64c  test    byte ptr [rcx+1Ch], 1
0x18002a650  jz      short loc_18002A66A
0x18002a652  mov     edx, 0Eh
0x18002a657  mov     r9d, eax
0x18002a65a  mov     rcx, [rcx+10h]
0x18002a65e  lea     r8, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids
0x18002a665  call    WPP_SF_d
0x18002a66a  mov     rcx, [rbp+var_20]
0x18002a66e  test    rcx, rcx
0x18002a671  jz      short loc_18002A679
0x18002a673  call    cs:__imp_FwRegCloseKey
0x18002a679  mov     rcx, [rbp+var_18]
0x18002a67d  call    cs:__imp_FwFree
0x18002a683  mov     eax, ebx
0x18002a685  mov     rcx, [rbp+var_8]
0x18002a689  xor     rcx, rsp; StackCookie
0x18002a68c  call    __security_check_cookie
0x18002a691  mov     rbx, [rsp+50h+arg_0]
0x18002a696  mov     rdi, [rsp+50h+arg_8]
0x18002a69b  add     rsp, 50h
0x18002a69f  pop     rbp
0x18002a6a0  retn
```
