# FwCreateOrOpenDynamicKeywordRegKey(_tag_WF_DYNAMIC_KEYWORD_TYPE,_tag_FW_STORE_TYPE,HKEY__ * *)

- ea: `0x1800194f0`
- end: `0x1800196ab`
- name: `?FwCreateOrOpenDynamicKeywordRegKey@@YAJW4_tag_WF_DYNAMIC_KEYWORD_TYPE@@W4_tag_FW_STORE_TYPE@@PEAPEAUHKEY__@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(int, int, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019034`
- `0x18002b3d0`
- `0x18002e740`

## callees

- `0x1800042c4`
- `0x1800194f0`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180019558`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180019558`
- `fwbase!FwRegOpenKey` at `0x1800195d5`
- `fwbase!FwRegOpenKey` at `0x1800195d5`
- `fwbase!FwRegCreateKey` at `0x180019622`
- `fwbase!FwRegCreateKey` at `0x180019622`

## pseudocode

```c
__int64 __fastcall FwCreateOrOpenDynamicKeywordRegKey(int a1, int a2, _QWORD *a3)
{
  unsigned __int64 v4; // r14
  int v6; // ebx
  LPCOLESTR v7; // rcx
  __int64 v8; // rdx
  int *v9; // rax
  int *v10; // rdi
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  int Parameter; // [rsp+38h] [rbp-30h] BYREF
  int v14; // [rsp+3Ch] [rbp-2Ch] BYREF

  v4 = 260LL * a1;
  v14 = 0;
  v12 = 0;
  if ( dword_18004D264[v4]
    || (Parameter = 0,
        InitOnceExecuteOnce(&g_InitOnce, InitHandleFunction, &Parameter, 0),
        v6 = Parameter,
        Parameter >= 0) )
  {
    if ( a2 == 2 )
    {
      v9 = &dword_18004CE64;
    }
    else
    {
      if ( a2 != 11 )
      {
        v6 = -2147024809;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v8 = 381;
          goto LABEL_23;
        }
        return (unsigned int)v6;
      }
      v9 = &dword_18004D064;
    }
    v10 = &v9[v4];
    v6 = FwRegOpenKey(-2147483646, &v9[v4], 131103, &v12, &v14);
    if ( v6 >= 0 )
    {
      if ( v14 || (v6 = FwRegCreateKey(-2147483646, v10, 131103, &v12), v6 >= 0) )
      {
        *a3 = v12;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v8 = 383;
          goto LABEL_23;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v8 = 382;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 380;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800194f0  mov     [rsp+arg_8], rbx
0x1800194f5  push    rsi
0x1800194f6  push    rdi
0x1800194f7  push    r14
0x1800194f9  sub     rsp, 50h
0x1800194fd  mov     rax, cs:__security_cookie
0x180019504  xor     rax, rsp
0x180019507  mov     [rsp+68h+var_28], rax
0x18001950c  movsxd  rax, ecx
0x18001950f  mov     rsi, r8
0x180019512  imul    r14, rax, 410h
0x180019519  lea     rax, dword_18004D264
0x180019520  mov     [rsp+68h+var_2C], 0
0x180019528  mov     edi, edx
0x18001952a  mov     [rsp+68h+var_38], 0
0x180019533  cmp     dword ptr [r14+rax], 0
0x180019538  jnz     short loc_180019591
0x18001953a  xor     r9d, r9d; Context
0x18001953d  mov     [rsp+68h+Parameter], 0
0x180019545  lea     r8, [rsp+68h+Parameter]; Parameter
0x18001954a  lea     rdx, ?InitHandleFunction@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180019551  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180019558  call    cs:__imp_InitOnceExecuteOnce
0x18001955e  mov     ebx, [rsp+68h+Parameter]
0x180019562  test    ebx, ebx
0x180019564  jns     short loc_180019591
0x180019566  mov     rcx, cs:WPP_GLOBAL_Control
0x18001956d  lea     rax, WPP_GLOBAL_Control
0x180019574  cmp     rcx, rax
0x180019577  jz      loc_18001968E
0x18001957d  test    byte ptr [rcx+1Ch], 1
0x180019581  jz      loc_18001968E
0x180019587  mov     edx, 17Ch
0x18001958c  jmp     loc_18001967B
0x180019591  cmp     edi, 2
0x180019594  jnz     short loc_18001959F
0x180019596  lea     rax, dword_18004CE64
0x18001959d  jmp     short loc_1800195AF
0x18001959f  cmp     edi, 0Bh
0x1800195a2  jnz     loc_180019658
0x1800195a8  lea     rax, dword_18004D064
0x1800195af  lea     rdi, [r14+rax]
0x1800195b3  mov     rcx, 0FFFFFFFF80000002h
0x1800195ba  lea     rax, [rsp+68h+var_2C]
0x1800195bf  mov     r14d, 2001Fh
0x1800195c5  mov     r8d, r14d
0x1800195c8  mov     [rsp+68h+var_48], rax
0x1800195cd  lea     r9, [rsp+68h+var_38]
0x1800195d2  mov     rdx, rdi
0x1800195d5  call    cs:__imp_FwRegOpenKey
0x1800195db  mov     ebx, eax
0x1800195dd  test    eax, eax
0x1800195df  jns     short loc_180019609
0x1800195e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195e8  lea     rax, WPP_GLOBAL_Control
0x1800195ef  cmp     rcx, rax
0x1800195f2  jz      loc_18001968E
0x1800195f8  test    byte ptr [rcx+1Ch], 1
0x1800195fc  jz      loc_18001968E
0x180019602  mov     edx, 17Eh
0x180019607  jmp     short loc_18001967B
0x180019609  cmp     [rsp+68h+var_2C], 0
0x18001960e  jnz     short loc_18001964E
0x180019610  lea     r9, [rsp+68h+var_38]
0x180019615  mov     r8d, r14d
0x180019618  mov     rdx, rdi
0x18001961b  mov     rcx, 0FFFFFFFF80000002h
0x180019622  call    cs:__imp_FwRegCreateKey
0x180019628  mov     ebx, eax
0x18001962a  test    eax, eax
0x18001962c  jns     short loc_18001964E
0x18001962e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019635  lea     rax, WPP_GLOBAL_Control
0x18001963c  cmp     rcx, rax
0x18001963f  jz      short loc_18001968E
0x180019641  test    byte ptr [rcx+1Ch], 1
0x180019645  jz      short loc_18001968E
0x180019647  mov     edx, 17Fh
0x18001964c  jmp     short loc_18001967B
0x18001964e  mov     rax, [rsp+68h+var_38]
0x180019653  mov     [rsi], rax
0x180019656  jmp     short loc_18001968E
0x180019658  mov     ebx, 80070057h
0x18001965d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019664  lea     rax, WPP_GLOBAL_Control
0x18001966b  cmp     rcx, rax
0x18001966e  jz      short loc_18001968E
0x180019670  test    byte ptr [rcx+1Ch], 1
0x180019674  jz      short loc_18001968E
0x180019676  mov     edx, 17Dh
0x18001967b  mov     rcx, [rcx+10h]
0x18001967f  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180019686  mov     r9d, ebx
0x180019689  call    WPP_SF_d
0x18001968e  mov     eax, ebx
0x180019690  mov     rcx, [rsp+68h+var_28]
0x180019695  xor     rcx, rsp; StackCookie
0x180019698  call    __security_check_cookie
0x18001969d  mov     rbx, [rsp+68h+arg_8]
0x1800196a2  add     rsp, 50h
0x1800196a6  pop     r14
0x1800196a8  pop     rdi
0x1800196a9  pop     rsi
0x1800196aa  retn
```
