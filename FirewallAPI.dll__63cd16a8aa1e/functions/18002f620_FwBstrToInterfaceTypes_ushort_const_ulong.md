# FwBstrToInterfaceTypes(ushort * const,ulong *)

- ea: `0x18002f620`
- end: `0x18002f74b`
- name: `?FwBstrToInterfaceTypes@@YAJQEAGPEAK@Z`
- size: `299`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003eaa0`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x18002f620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f66c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f66c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f6d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f6d0`
- `fwbase!FwBaseFree` at `0x18002f71c`
- `fwbase!FwBaseFree` at `0x18002f71c`
- `fwbase!FwStringCopy` at `0x18002f682`
- `fwbase!FwStringCopy` at `0x18002f682`
- `FWPolicyIOMgr!FwParseInterfaceType` at `0x18002f6e3`
- `FWPolicyIOMgr!FwParseInterfaceType` at `0x18002f6e3`

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
0x18002f620  mov     r11, rsp
0x18002f623  mov     [r11+18h], rbx
0x18002f627  mov     [r11+20h], rsi
0x18002f62b  push    rdi
0x18002f62c  sub     rsp, 40h
0x18002f630  mov     rax, cs:__security_cookie
0x18002f637  xor     rax, rsp
0x18002f63a  mov     [rsp+48h+var_10], rax
0x18002f63f  xor     esi, esi
0x18002f641  mov     rdi, rdx
0x18002f644  mov     [r11-28h], rsi
0x18002f648  mov     rbx, rcx
0x18002f64b  mov     [r11-20h], rsi
0x18002f64f  mov     [rsp+48h+var_18], esi
0x18002f653  test    rcx, rcx
0x18002f656  jz      loc_18002F713
0x18002f65c  cmp     [rcx], si
0x18002f65f  jz      loc_18002F713
0x18002f665  lea     rdx, aAll; "All"
0x18002f66c  call    cs:__imp__o__wcsicmp
0x18002f672  test    eax, eax
0x18002f674  jz      loc_18002F713
0x18002f67a  lea     rdx, [rsp+48h+String]
0x18002f67f  mov     rcx, rbx
0x18002f682  call    cs:__imp_FwStringCopy
0x18002f688  mov     ebx, eax
0x18002f68a  test    eax, eax
0x18002f68c  jns     short loc_18002F6BF
0x18002f68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f695  lea     rax, WPP_GLOBAL_Control
0x18002f69c  cmp     rcx, rax
0x18002f69f  jz      short loc_18002F717
0x18002f6a1  test    byte ptr [rcx+1Ch], 1
0x18002f6a5  jz      short loc_18002F717
0x18002f6a7  lea     edx, [rsi+0Ah]
0x18002f6aa  mov     rcx, [rcx+10h]
0x18002f6ae  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18002f6b5  mov     r9d, ebx
0x18002f6b8  call    WPP_SF_d
0x18002f6bd  jmp     short loc_18002F717
0x18002f6bf  mov     rcx, [rsp+48h+String]; String
0x18002f6c4  lea     r8, [rsp+48h+Context]; Context
0x18002f6c9  lea     rdx, Delimiter; ","
0x18002f6d0  call    cs:__imp_wcstok_s
0x18002f6d6  test    rax, rax
0x18002f6d9  jz      short loc_18002F717
0x18002f6db  lea     rdx, [rsp+48h+var_18]
0x18002f6e0  mov     rcx, rax
0x18002f6e3  call    cs:__imp_?FwParseInterfaceType@@YAJPEBGPEAK@Z; FwParseInterfaceType(ushort const *,ulong *)
0x18002f6e9  mov     ebx, eax
0x18002f6eb  test    eax, eax
0x18002f6ed  js      short loc_18002F6F3
0x18002f6ef  xor     ecx, ecx
0x18002f6f1  jmp     short loc_18002F6C4
0x18002f6f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6fa  lea     rax, WPP_GLOBAL_Control
0x18002f701  cmp     rcx, rax
0x18002f704  jz      short loc_18002F717
0x18002f706  test    byte ptr [rcx+1Ch], 1
0x18002f70a  jz      short loc_18002F717
0x18002f70c  mov     edx, 0Bh
0x18002f711  jmp     short loc_18002F6AA
0x18002f713  mov     [rdi], esi
0x18002f715  mov     ebx, esi
0x18002f717  mov     rcx, [rsp+48h+String]
0x18002f71c  call    cs:__imp_FwBaseFree
0x18002f722  test    ebx, ebx
0x18002f724  js      short loc_18002F72C
0x18002f726  mov     eax, [rsp+48h+var_18]
0x18002f72a  mov     [rdi], eax
0x18002f72c  mov     eax, ebx
0x18002f72e  mov     rcx, [rsp+48h+var_10]
0x18002f733  xor     rcx, rsp; StackCookie
0x18002f736  call    __security_check_cookie
0x18002f73b  mov     rbx, [rsp+48h+arg_10]
0x18002f740  mov     rsi, [rsp+48h+arg_18]
0x18002f745  add     rsp, 40h
0x18002f749  pop     rdi
0x18002f74a  retn
```
