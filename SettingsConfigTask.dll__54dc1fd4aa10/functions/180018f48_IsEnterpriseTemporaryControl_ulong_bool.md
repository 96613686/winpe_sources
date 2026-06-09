# IsEnterpriseTemporaryControl(ulong,bool *)

- ea: `0x180018f48`
- end: `0x180018fed`
- name: `?IsEnterpriseTemporaryControl@@YAJKPEA_N@Z`
- size: `165`
- prototype: `int(unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018ff4`

## callees

- `0x18000972c`
- `0x1800136e4`
- `0x1800137e4`
- `0x180018f48`
- `0x18001c8d0`

## string_xrefs

- `0x180018f87`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180018fc1`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180018f65`: `ActiveConfig`
- `0x180018f70`: `SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls\Active`

## pseudocode

```c
__int64 __fastcall IsEnterpriseTemporaryControl(__int64 a1, bool *a2)
{
  int DwordFromRegistry; // eax
  int IsValidFeatureID; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  DwordFromRegistry = ETCpGetDwordFromRegistry(
                        L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement\\EnterpriseTempControls\\Active",
                        L"ActiveConfig",
                        (LPBYTE)&v9);
  IsValidFeatureID = DwordFromRegistry;
  if ( DwordFromRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)(unsigned int)DwordFromRegistry,
      v7);
    v5 = 158;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)(unsigned int)IsValidFeatureID,
      v7);
    *a2 = 0;
    return 0;
  }
  IsValidFeatureID = ETCpIsValidFeatureID(0xB446228E, v9, a2);
  if ( IsValidFeatureID < 0 )
  {
    v5 = 161;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180018f48  mov     rax, rsp
0x180018f4b  mov     [rax+10h], rbx
0x180018f4f  mov     [rax+18h], rsi
0x180018f53  mov     [rax+8], ecx
0x180018f56  push    rdi; int
0x180018f57  sub     rsp, 20h
0x180018f5b  mov     rsi, rdx
0x180018f5e  mov     dword ptr [rax+8], 0
0x180018f65  lea     rdx, aActiveconfig; "ActiveConfig"
0x180018f6c  lea     r8, [rax+8]; lpData
0x180018f70  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x180018f77  call    ?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z; ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x180018f7c  mov     ebx, eax
0x180018f7e  test    eax, eax
0x180018f80  jns     short loc_180018FA5
0x180018f82  mov     rcx, [rsp+28h]; this
0x180018f87  lea     rdi, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180018f8e  mov     r8, rdi; unsigned int
0x180018f91  mov     r9d, eax; char *
0x180018f94  mov     edx, 72h ; 'r'; void *
0x180018f99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f9e  mov     edx, 9Eh
0x180018fa3  jmp     short loc_180018FC8
0x180018fa5  mov     edx, [rsp+28h+arg_0]; unsigned int
0x180018fa9  mov     r8, rsi; bool *
0x180018fac  mov     ecx, 0B446228Eh; unsigned int
0x180018fb1  call    ?ETCpIsValidFeatureID@@YAJKKPEA_N@Z; ETCpIsValidFeatureID(ulong,ulong,bool *)
0x180018fb6  mov     ebx, eax
0x180018fb8  test    eax, eax
0x180018fba  jns     short loc_180018FDB
0x180018fbc  mov     edx, 0A1h; void *
0x180018fc1  lea     rdi, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180018fc8  mov     rcx, [rsp+28h]; this
0x180018fcd  mov     r9d, ebx; char *
0x180018fd0  mov     r8, rdi; unsigned int
0x180018fd3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018fd8  mov     byte ptr [rsi], 0
0x180018fdb  mov     rbx, [rsp+28h+arg_8]
0x180018fe0  xor     eax, eax
0x180018fe2  mov     rsi, [rsp+28h+arg_10]
0x180018fe7  add     rsp, 20h
0x180018feb  pop     rdi
0x180018fec  retn
```
