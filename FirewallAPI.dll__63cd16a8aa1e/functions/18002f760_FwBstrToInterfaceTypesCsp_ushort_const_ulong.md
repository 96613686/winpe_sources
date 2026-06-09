# FwBstrToInterfaceTypesCsp(ushort const *,ulong *)

- ea: `0x18002f760`
- end: `0x18002f8d5`
- name: `?FwBstrToInterfaceTypesCsp@@YAJPEBGPEAK@Z`
- size: `373`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x18002f760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f7ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f7ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f81d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f874`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f81d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002f874`
- `fwbase!FwBaseFree` at `0x18002f8a6`
- `fwbase!FwBaseFree` at `0x18002f8a6`
- `fwbase!FwStringCopy` at `0x18002f7c4`
- `fwbase!FwStringCopy` at `0x18002f7c4`
- `FWPolicyIOMgr!FwParseInterfaceTypeCsp` at `0x18002f85a`
- `FWPolicyIOMgr!FwParseInterfaceTypeCsp` at `0x18002f85a`

## pseudocode

```c
__int64 __fastcall FwBstrToInterfaceTypesCsp(const unsigned __int16 *a1, unsigned int *a2)
{
  int v4; // ebx
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-18h] BYREF

  String = 0;
  Context = 0;
  v11 = 0;
  *a2 = 0;
  if ( a1 && *a1 && (unsigned int)_o__wcsicmp(a1, L"All") )
  {
    v4 = FwStringCopy(a1, &String);
    if ( v4 >= 0 )
    {
      v7 = wcstok_s(String, L",", &Context);
      if ( v7 )
      {
        while ( 1 )
        {
          v4 = FwParseInterfaceTypeCsp(v7, &v11);
          if ( v4 < 0 )
            break;
          v7 = wcstok_s(0, L",", &Context);
          if ( !v7 )
            goto LABEL_20;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 14;
          goto LABEL_8;
        }
      }
      else
      {
        v4 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 13;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 12;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v4);
      }
    }
  }
  else
  {
    v4 = 0;
  }
LABEL_20:
  FwBaseFree(String);
  if ( v4 >= 0 )
    *a2 = v11;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f760  mov     r11, rsp
0x18002f763  mov     [r11+18h], rbx
0x18002f767  mov     [r11+20h], rsi
0x18002f76b  push    rdi
0x18002f76c  sub     rsp, 40h
0x18002f770  mov     rax, cs:__security_cookie
0x18002f777  xor     rax, rsp
0x18002f77a  mov     [rsp+48h+var_10], rax
0x18002f77f  xor     esi, esi
0x18002f781  mov     rdi, rdx
0x18002f784  mov     [r11-28h], rsi
0x18002f788  mov     rbx, rcx
0x18002f78b  mov     [r11-20h], rsi
0x18002f78f  mov     [rsp+48h+var_18], esi
0x18002f793  mov     [rdx], esi
0x18002f795  test    rcx, rcx
0x18002f798  jz      loc_18002F89F
0x18002f79e  cmp     [rcx], si
0x18002f7a1  jz      loc_18002F89F
0x18002f7a7  lea     rdx, aAll; "All"
0x18002f7ae  call    cs:__imp__o__wcsicmp
0x18002f7b4  test    eax, eax
0x18002f7b6  jz      loc_18002F89F
0x18002f7bc  lea     rdx, [rsp+48h+String]
0x18002f7c1  mov     rcx, rbx
0x18002f7c4  call    cs:__imp_FwStringCopy
0x18002f7ca  mov     ebx, eax
0x18002f7cc  test    eax, eax
0x18002f7ce  jns     short loc_18002F80C
0x18002f7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7d7  lea     rax, WPP_GLOBAL_Control
0x18002f7de  cmp     rcx, rax
0x18002f7e1  jz      loc_18002F8A1
0x18002f7e7  test    byte ptr [rcx+1Ch], 1
0x18002f7eb  jz      loc_18002F8A1
0x18002f7f1  lea     edx, [rsi+0Ch]
0x18002f7f4  mov     rcx, [rcx+10h]
0x18002f7f8  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18002f7ff  mov     r9d, ebx
0x18002f802  call    WPP_SF_d
0x18002f807  jmp     loc_18002F8A1
0x18002f80c  mov     rcx, [rsp+48h+String]; String
0x18002f811  lea     r8, [rsp+48h+Context]; Context
0x18002f816  lea     rdx, Delimiter; ","
0x18002f81d  call    cs:__imp_wcstok_s
0x18002f823  test    rax, rax
0x18002f826  jnz     short loc_18002F852
0x18002f828  mov     ebx, 80070057h
0x18002f82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f834  lea     rax, WPP_GLOBAL_Control
0x18002f83b  cmp     rcx, rax
0x18002f83e  jz      short loc_18002F8A1
0x18002f840  test    byte ptr [rcx+1Ch], 1
0x18002f844  jz      short loc_18002F8A1
0x18002f846  mov     edx, 0Dh
0x18002f84b  jmp     short loc_18002F7F4
0x18002f84d  test    rax, rax
0x18002f850  jz      short loc_18002F8A1
0x18002f852  lea     rdx, [rsp+48h+var_18]
0x18002f857  mov     rcx, rax
0x18002f85a  call    cs:__imp_?FwParseInterfaceTypeCsp@@YAJPEBGPEAK@Z; FwParseInterfaceTypeCsp(ushort const *,ulong *)
0x18002f860  mov     ebx, eax
0x18002f862  test    eax, eax
0x18002f864  js      short loc_18002F87C
0x18002f866  lea     r8, [rsp+48h+Context]; Context
0x18002f86b  xor     ecx, ecx; String
0x18002f86d  lea     rdx, Delimiter; ","
0x18002f874  call    cs:__imp_wcstok_s
0x18002f87a  jmp     short loc_18002F84D
0x18002f87c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f883  lea     rax, WPP_GLOBAL_Control
0x18002f88a  cmp     rcx, rax
0x18002f88d  jz      short loc_18002F8A1
0x18002f88f  test    byte ptr [rcx+1Ch], 1
0x18002f893  jz      short loc_18002F8A1
0x18002f895  mov     edx, 0Eh
0x18002f89a  jmp     loc_18002F7F4
0x18002f89f  mov     ebx, esi
0x18002f8a1  mov     rcx, [rsp+48h+String]
0x18002f8a6  call    cs:__imp_FwBaseFree
0x18002f8ac  test    ebx, ebx
0x18002f8ae  js      short loc_18002F8B6
0x18002f8b0  mov     eax, [rsp+48h+var_18]
0x18002f8b4  mov     [rdi], eax
0x18002f8b6  mov     eax, ebx
0x18002f8b8  mov     rcx, [rsp+48h+var_10]
0x18002f8bd  xor     rcx, rsp; StackCookie
0x18002f8c0  call    __security_check_cookie
0x18002f8c5  mov     rbx, [rsp+48h+arg_10]
0x18002f8ca  mov     rsi, [rsp+48h+arg_18]
0x18002f8cf  add     rsp, 40h
0x18002f8d3  pop     rdi
0x18002f8d4  retn
```
