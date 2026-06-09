# FwCreateOrOpenHyperVVMCreatorsRegKey(HKEY__ * *)

- ea: `0x1800184b4`
- end: `0x18001860b`
- name: `?FwCreateOrOpenHyperVVMCreatorsRegKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800183f0`
- `0x18002e930`
- `0x18002f1c0`

## callees

- `0x1800042c4`
- `0x1800184b4`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800184ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800184ff`
- `fwbase!FwRegOpenKey` at `0x18001856e`
- `fwbase!FwRegOpenKey` at `0x18001856e`
- `fwbase!FwRegCreateKey` at `0x1800185ba`
- `fwbase!FwRegCreateKey` at `0x1800185ba`

## pseudocode

```c
__int64 __fastcall FwCreateOrOpenHyperVVMCreatorsRegKey(HKEY *a1)
{
  int v2; // ebx
  LPCOLESTR v3; // rcx
  __int64 v4; // rdx
  HKEY v6; // [rsp+30h] [rbp-28h] BYREF
  int Parameter; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+3Ch] [rbp-1Ch] BYREF

  v8 = 0;
  v6 = 0;
  Parameter = 0;
  InitOnceExecuteOnce(&g_InitOnce, InitHandleFunction, &Parameter, 0);
  v2 = Parameter;
  if ( Parameter >= 0 )
  {
    v2 = FwRegOpenKey(-2147483646, &g_HyperVVMCreatorsRegPath, 131103, &v6, &v8);
    if ( v2 >= 0 )
    {
      if ( v8 || (v2 = FwRegCreateKey(-2147483646, &g_HyperVVMCreatorsRegPath, 131103, &v6), v2 >= 0) )
      {
        *a1 = v6;
        return (unsigned int)v2;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v4 = 409;
        goto LABEL_5;
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v4 = 408;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v4 = 407;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800184b4  mov     [rsp+arg_8], rbx
0x1800184b9  push    rdi
0x1800184ba  sub     rsp, 50h
0x1800184be  mov     rax, cs:__security_cookie
0x1800184c5  xor     rax, rsp
0x1800184c8  mov     [rsp+58h+var_18], rax
0x1800184cd  mov     rdi, rcx
0x1800184d0  mov     [rsp+58h+var_1C], 0
0x1800184d8  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800184df  mov     [rsp+58h+var_28], 0
0x1800184e8  xor     r9d, r9d; Context
0x1800184eb  mov     [rsp+58h+Parameter], 0
0x1800184f3  lea     r8, [rsp+58h+Parameter]; Parameter
0x1800184f8  lea     rdx, ?InitHandleFunction@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800184ff  call    cs:__imp_InitOnceExecuteOnce
0x180018505  mov     ebx, [rsp+58h+Parameter]
0x180018509  test    ebx, ebx
0x18001850b  jns     short loc_18001854B
0x18001850d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018514  lea     rax, WPP_GLOBAL_Control
0x18001851b  cmp     rcx, rax
0x18001851e  jz      loc_1800185F1
0x180018524  test    byte ptr [rcx+1Ch], 1
0x180018528  jz      loc_1800185F1
0x18001852e  mov     edx, 197h
0x180018533  mov     rcx, [rcx+10h]
0x180018537  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001853e  mov     r9d, ebx
0x180018541  call    WPP_SF_d
0x180018546  jmp     loc_1800185F1
0x18001854b  lea     rax, [rsp+58h+var_1C]
0x180018550  mov     r8d, 2001Fh
0x180018556  lea     r9, [rsp+58h+var_28]
0x18001855b  mov     [rsp+58h+var_38], rax
0x180018560  lea     rdx, ?g_HyperVVMCreatorsRegPath@@3PAGA; ushort near * g_HyperVVMCreatorsRegPath
0x180018567  mov     rcx, 0FFFFFFFF80000002h
0x18001856e  call    cs:__imp_FwRegOpenKey
0x180018574  mov     ebx, eax
0x180018576  test    eax, eax
0x180018578  jns     short loc_18001859A
0x18001857a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018581  lea     rax, WPP_GLOBAL_Control
0x180018588  cmp     rcx, rax
0x18001858b  jz      short loc_1800185F1
0x18001858d  test    byte ptr [rcx+1Ch], 1
0x180018591  jz      short loc_1800185F1
0x180018593  mov     edx, 198h
0x180018598  jmp     short loc_180018533
0x18001859a  cmp     [rsp+58h+var_1C], 0
0x18001859f  jnz     short loc_1800185E9
0x1800185a1  lea     r9, [rsp+58h+var_28]
0x1800185a6  mov     r8d, 2001Fh
0x1800185ac  lea     rdx, ?g_HyperVVMCreatorsRegPath@@3PAGA; ushort near * g_HyperVVMCreatorsRegPath
0x1800185b3  mov     rcx, 0FFFFFFFF80000002h
0x1800185ba  call    cs:__imp_FwRegCreateKey
0x1800185c0  mov     ebx, eax
0x1800185c2  test    eax, eax
0x1800185c4  jns     short loc_1800185E9
0x1800185c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185cd  lea     rax, WPP_GLOBAL_Control
0x1800185d4  cmp     rcx, rax
0x1800185d7  jz      short loc_1800185F1
0x1800185d9  test    byte ptr [rcx+1Ch], 1
0x1800185dd  jz      short loc_1800185F1
0x1800185df  mov     edx, 199h
0x1800185e4  jmp     loc_180018533
0x1800185e9  mov     rax, [rsp+58h+var_28]
0x1800185ee  mov     [rdi], rax
0x1800185f1  mov     eax, ebx
0x1800185f3  mov     rcx, [rsp+58h+var_18]
0x1800185f8  xor     rcx, rsp; StackCookie
0x1800185fb  call    __security_check_cookie
0x180018600  mov     rbx, [rsp+58h+arg_8]
0x180018605  add     rsp, 50h
0x180018609  pop     rdi
0x18001860a  retn
```
