# ETCpIsValidFeatureID(ulong,ulong,bool *)

- ea: `0x1800137e4`
- end: `0x18001391f`
- name: `?ETCpIsValidFeatureID@@YAJKKPEA_N@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180018f48`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x180009f8c`
- `0x1800136e4`
- `0x1800137e4`
- `0x18001c8d0`

## string_xrefs

- `0x180013867`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x1800138a4`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x1800138df`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180013835`: `SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls`

## pseudocode

```c
__int64 __fastcall ETCpIsValidFeatureID(unsigned int a1, int a2, bool *a3)
{
  int v6; // eax
  int DwordFromRegistry; // ebx
  int v9; // [rsp+20h] [rbp-158h]
  BYTE Data[16]; // [rsp+30h] [rbp-148h] BYREF
  WCHAR ValueName[32]; // [rsp+40h] [rbp-138h] BYREF
  WCHAR SubKey[104]; // [rsp+80h] [rbp-F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  *(_DWORD *)Data = 0;
  memset_0(SubKey, 0, 0xC8u);
  memset_0(ValueName, 0, sizeof(ValueName));
  v9 = a2;
  v6 = StringCchPrintfW(
         SubKey,
         0x64u,
         L"%s\\%lu",
         L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement\\EnterpriseTempControls");
  DwordFromRegistry = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)(unsigned int)v6,
      v9);
LABEL_4:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)(unsigned int)DwordFromRegistry,
      v9);
    goto LABEL_6;
  }
  DwordFromRegistry = StringCchPrintfW(ValueName, 0x20u, L"%lu", a1);
  if ( DwordFromRegistry < 0 )
    goto LABEL_4;
  DwordFromRegistry = ETCpGetDwordFromRegistry(SubKey, ValueName, Data);
  if ( DwordFromRegistry >= 0 )
  {
    *a3 = *(_DWORD *)Data != 0;
    return 0;
  }
LABEL_6:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
    (const char *)(unsigned int)DwordFromRegistry,
    v9);
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800137e4  push    rbx
0x1800137e6  push    rsi
0x1800137e7  push    rdi
0x1800137e8  sub     rsp, 160h
0x1800137ef  mov     rax, cs:__security_cookie
0x1800137f6  xor     rax, rsp
0x1800137f9  mov     [rsp+178h+var_28], rax
0x180013801  mov     rdi, r8
0x180013804  mov     dword ptr [rsp+178h+Data], 0
0x18001380c  mov     ebx, edx
0x18001380e  mov     esi, ecx
0x180013810  xor     edx, edx; Val
0x180013812  lea     rcx, [rsp+178h+SubKey]; void *
0x18001381a  mov     r8d, 0C8h; Size
0x180013820  call    memset_0
0x180013825  xor     edx, edx; Val
0x180013827  lea     rcx, [rsp+178h+ValueName]; void *
0x18001382c  lea     r8d, [rdx+40h]; Size
0x180013830  call    memset_0
0x180013835  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x18001383c  mov     [rsp+178h+var_158], ebx; int
0x180013840  lea     r8, aSLu; "%s\\%lu"
0x180013847  mov     edx, 64h ; 'd'; unsigned __int64
0x18001384c  lea     rcx, [rsp+178h+SubKey]; unsigned __int16 *
0x180013854  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013859  mov     ebx, eax
0x18001385b  test    eax, eax
0x18001385d  jns     short loc_18001387D
0x18001385f  mov     rcx, [rsp+178h]; this
0x180013867  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001386e  mov     r9d, eax; char *
0x180013871  mov     edx, 83h; void *
0x180013876  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001387b  jmp     short loc_18001389C
0x18001387d  mov     r9d, esi
0x180013880  lea     r8, aLu; "%lu"
0x180013887  mov     edx, 20h ; ' '; unsigned __int64
0x18001388c  lea     rcx, [rsp+178h+ValueName]; unsigned __int16 *
0x180013891  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013896  mov     ebx, eax
0x180013898  test    eax, eax
0x18001389a  jns     short loc_1800138BA
0x18001389c  mov     rcx, [rsp+178h]; this
0x1800138a4  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800138ab  mov     r9d, ebx; char *
0x1800138ae  mov     edx, 8Bh; void *
0x1800138b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800138b8  jmp     short loc_1800138D7
0x1800138ba  lea     r8, [rsp+178h+Data]; lpData
0x1800138bf  lea     rdx, [rsp+178h+ValueName]; lpValueName
0x1800138c4  lea     rcx, [rsp+178h+SubKey]; lpSubKey
0x1800138cc  call    ?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z; ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x1800138d1  mov     ebx, eax
0x1800138d3  test    eax, eax
0x1800138d5  jns     short loc_1800138F8
0x1800138d7  mov     rcx, [rsp+178h]; this
0x1800138df  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800138e6  mov     r9d, ebx; char *
0x1800138e9  mov     edx, 90h; void *
0x1800138ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800138f3  mov     byte ptr [rdi], 0
0x1800138f6  jmp     short loc_180013902
0x1800138f8  cmp     dword ptr [rsp+178h+Data], 0
0x1800138fd  setnz   al
0x180013900  mov     [rdi], al
0x180013902  xor     eax, eax
0x180013904  mov     rcx, [rsp+178h+var_28]
0x18001390c  xor     rcx, rsp; StackCookie
0x18001390f  call    __security_check_cookie
0x180013914  add     rsp, 160h
0x18001391b  pop     rdi
0x18001391c  pop     rsi
0x18001391d  pop     rbx
0x18001391e  retn
```
