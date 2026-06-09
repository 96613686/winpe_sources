# FwBstrToInterfaceTypes(ushort * const,ulong *)

- ea: `0x180031700`
- end: `0x18003184e`
- name: `?FwBstrToInterfaceTypes@@YAJQEAGPEAK@Z`
- size: `334`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180041b20`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x180031700`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003174c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003174c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800317c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800317c0`
- `fwbase!FwBaseFree` at `0x180031818`
- `fwbase!FwBaseFree` at `0x180031818`
- `fwbase!FwStringCopy` at `0x180031768`
- `fwbase!FwStringCopy` at `0x180031768`
- `FWPolicyIOMgr!FwParseInterfaceType` at `0x1800317d9`
- `FWPolicyIOMgr!FwParseInterfaceType` at `0x1800317d9`

## pseudocode

```c
__int64 __fastcall FwBstrToInterfaceTypes(unsigned __int16 *const a1, unsigned int *a2)
{
  int v4; // ebx
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  wchar_t *i; // rcx
  wchar_t *v8; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+30h] [rbp-18h] BYREF

  String = 0;
  Context = 0;
  v12 = 0;
  if ( a1 && *a1 && (unsigned int)_o__wcsicmp(a1, L"All") )
  {
    v4 = FwStringCopy(a1, &String);
    if ( v4 >= 0 )
    {
      for ( i = String; ; i = 0 )
      {
        v8 = wcstok_s(i, L",", &Context);
        if ( !v8 )
          break;
        v4 = FwParseInterfaceType(v8, &v12);
        if ( v4 < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 11;
            goto LABEL_8;
          }
          break;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 10;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v4);
      }
    }
  }
  else
  {
    *a2 = 0;
    v4 = 0;
  }
  FwBaseFree(String);
  if ( v4 >= 0 )
    *a2 = v12;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180031700  mov     r11, rsp
0x180031703  mov     [r11+18h], rbx
0x180031707  mov     [r11+20h], rsi
0x18003170b  push    rdi
0x18003170c  sub     rsp, 40h
0x180031710  mov     rax, cs:__security_cookie
0x180031717  xor     rax, rsp
0x18003171a  mov     [rsp+48h+var_10], rax
0x18003171f  xor     esi, esi
0x180031721  mov     rdi, rdx
0x180031724  mov     [r11-28h], rsi
0x180031728  mov     rbx, rcx
0x18003172b  mov     [r11-20h], rsi
0x18003172f  mov     [rsp+48h+var_18], esi
0x180031733  test    rcx, rcx
0x180031736  jz      loc_18003180F
0x18003173c  cmp     [rcx], si
0x18003173f  jz      loc_18003180F
0x180031745  lea     rdx, aAll; "All"
0x18003174c  call    cs:__imp__o__wcsicmp
0x180031753  nop     dword ptr [rax+rax+00h]
0x180031758  test    eax, eax
0x18003175a  jz      loc_18003180F
0x180031760  lea     rdx, [rsp+48h+String]
0x180031765  mov     rcx, rbx
0x180031768  call    cs:__imp_FwStringCopy
0x18003176f  nop     dword ptr [rax+rax+00h]
0x180031774  mov     ebx, eax
0x180031776  test    eax, eax
0x180031778  jns     short loc_1800317AF
0x18003177a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031781  lea     rax, WPP_GLOBAL_Control
0x180031788  cmp     rcx, rax
0x18003178b  jz      loc_180031813
0x180031791  test    byte ptr [rcx+1Ch], 1
0x180031795  jz      short loc_180031813
0x180031797  lea     edx, [rsi+0Ah]
0x18003179a  mov     rcx, [rcx+10h]
0x18003179e  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800317a5  mov     r9d, ebx
0x1800317a8  call    WPP_SF_d
0x1800317ad  jmp     short loc_180031813
0x1800317af  mov     rcx, [rsp+48h+String]; String
0x1800317b4  lea     r8, [rsp+48h+Context]; Context
0x1800317b9  lea     rdx, Delimiter; ","
0x1800317c0  call    cs:__imp_wcstok_s
0x1800317c7  nop     dword ptr [rax+rax+00h]
0x1800317cc  test    rax, rax
0x1800317cf  jz      short loc_180031813
0x1800317d1  lea     rdx, [rsp+48h+var_18]
0x1800317d6  mov     rcx, rax
0x1800317d9  call    cs:__imp_?FwParseInterfaceType@@YAJPEBGPEAK@Z; FwParseInterfaceType(ushort const *,ulong *)
0x1800317e0  nop     dword ptr [rax+rax+00h]
0x1800317e5  mov     ebx, eax
0x1800317e7  test    eax, eax
0x1800317e9  js      short loc_1800317EF
0x1800317eb  xor     ecx, ecx
0x1800317ed  jmp     short loc_1800317B4
0x1800317ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317f6  lea     rax, WPP_GLOBAL_Control
0x1800317fd  cmp     rcx, rax
0x180031800  jz      short loc_180031813
0x180031802  test    byte ptr [rcx+1Ch], 1
0x180031806  jz      short loc_180031813
0x180031808  mov     edx, 0Bh
0x18003180d  jmp     short loc_18003179A
0x18003180f  mov     [rdi], esi
0x180031811  mov     ebx, esi
0x180031813  mov     rcx, [rsp+48h+String]
0x180031818  call    cs:__imp_FwBaseFree
0x18003181f  nop     dword ptr [rax+rax+00h]
0x180031824  test    ebx, ebx
0x180031826  js      short loc_18003182E
0x180031828  mov     eax, [rsp+48h+var_18]
0x18003182c  mov     [rdi], eax
0x18003182e  mov     eax, ebx
0x180031830  mov     rcx, [rsp+48h+var_10]
0x180031835  xor     rcx, rsp; StackCookie
0x180031838  call    __security_check_cookie
0x18003183d  mov     rbx, [rsp+48h+arg_10]
0x180031842  mov     rsi, [rsp+48h+arg_18]
0x180031847  add     rsp, 40h
0x18003184b  pop     rdi
0x18003184c  retn
```
