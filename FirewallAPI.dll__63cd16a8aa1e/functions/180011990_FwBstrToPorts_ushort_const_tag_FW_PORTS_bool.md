# FwBstrToPorts(ushort * const,_tag_FW_PORTS *,bool)

- ea: `0x180011990`
- end: `0x180011b64`
- name: `?FwBstrToPorts@@YAJQEAGPEAU_tag_FW_PORTS@@_N@Z`
- size: `468`
- prototype: `int(unsigned __int16 *const, struct _tag_FW_PORTS *, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012030`
- `0x18003fa20`
- `0x1800515f0`

## callees

- `0x180005954`
- `0x180011990`
- `0x180012f40`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800119e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800119e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011a5a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011abb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011a5a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011abb`
- `fwbase!FwBaseFree` at `0x180011b25`
- `fwbase!FwBaseFree` at `0x180011b33`
- `fwbase!FwBaseFree` at `0x180011b25`
- `fwbase!FwBaseFree` at `0x180011b33`
- `fwbase!FwStringCopy` at `0x1800119ff`
- `fwbase!FwStringCopy` at `0x1800119ff`
- `FWPolicyIOMgr!FwParseAllPortVersions` at `0x180011aa1`
- `FWPolicyIOMgr!FwParseAllPortVersions` at `0x180011aa1`

## pseudocode

```c
__int64 __fastcall FwBstrToPorts(unsigned __int16 *const a1, struct _tag_FW_PORTS *a2, char a3)
{
  int v5; // ebx
  FwPolicy2 *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  wchar_t *v9; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF

  String = 0;
  Context = 0;
  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  if ( a1 && *a1 && (!a3 || (unsigned int)_o__wcsicmp(a1, "*")) )
  {
    v5 = FwStringCopy(a1, &String);
    if ( v5 >= 0 )
    {
      v9 = wcstok_s(String, L",", &Context);
      if ( v9 )
      {
        do
        {
          v5 = FwParseAllPortVersions(v9, a2);
          if ( v5 < 0 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 30;
              goto LABEL_9;
            }
            goto LABEL_26;
          }
          v9 = wcstok_s(0, L",", &Context);
        }
        while ( v9 );
        if ( !(unsigned int)FwIsValidPorts(a2) )
        {
          v8 = 2147942487LL;
          v5 = -2147024809;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 31;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v8 = 2147942487LL;
        v5 = -2147024809;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 29;
LABEL_10:
          WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v8);
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 28;
LABEL_9:
        v8 = (unsigned int)v5;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v5 = 0;
  }
LABEL_26:
  FwBaseFree(String);
  if ( v5 < 0 )
  {
    FwBaseFree(*((_QWORD *)a2 + 2));
    *(_OWORD *)a2 = 0;
    *((_QWORD *)a2 + 2) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011990  mov     r11, rsp
0x180011993  mov     [r11+18h], rbx
0x180011997  mov     [r11+20h], rsi
0x18001199b  push    rdi
0x18001199c  sub     rsp, 40h
0x1800119a0  mov     rax, cs:__security_cookie
0x1800119a7  xor     rax, rsp
0x1800119aa  mov     [rsp+48h+var_18], rax
0x1800119af  xor     esi, esi
0x1800119b1  xor     eax, eax
0x1800119b3  mov     [r11-28h], rsi
0x1800119b7  xorps   xmm0, xmm0
0x1800119ba  mov     [r11-20h], rsi
0x1800119be  mov     rdi, rdx
0x1800119c1  mov     rbx, rcx
0x1800119c4  movups  xmmword ptr [rdx], xmm0
0x1800119c7  mov     [rdx+10h], rax
0x1800119cb  test    rcx, rcx
0x1800119ce  jz      loc_180011B1E
0x1800119d4  cmp     [rcx], si
0x1800119d7  jz      loc_180011B1E
0x1800119dd  test    r8b, r8b
0x1800119e0  jz      short loc_1800119F7
0x1800119e2  lea     rdx, asc_18007C438; "*"
0x1800119e9  call    cs:__imp__o__wcsicmp
0x1800119ef  test    eax, eax
0x1800119f1  jz      loc_180011B1E
0x1800119f7  lea     rdx, [rsp+48h+String]
0x1800119fc  mov     rcx, rbx
0x1800119ff  call    cs:__imp_FwStringCopy
0x180011a05  mov     ebx, eax
0x180011a07  test    eax, eax
0x180011a09  jns     short loc_180011A49
0x180011a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a12  lea     rax, WPP_GLOBAL_Control
0x180011a19  cmp     rcx, rax
0x180011a1c  jz      loc_180011B20
0x180011a22  test    byte ptr [rcx+1Ch], 1
0x180011a26  jz      loc_180011B20
0x180011a2c  mov     edx, 1Ch
0x180011a31  mov     r9d, ebx
0x180011a34  mov     rcx, [rcx+10h]
0x180011a38  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180011a3f  call    WPP_SF_d
0x180011a44  jmp     loc_180011B20
0x180011a49  mov     rcx, [rsp+48h+String]; String
0x180011a4e  lea     r8, [rsp+48h+Context]; Context
0x180011a53  lea     rdx, Delimiter; ","
0x180011a5a  call    cs:__imp_wcstok_s
0x180011a60  test    rax, rax
0x180011a63  jnz     short loc_180011A9B
0x180011a65  mov     r9d, 80070057h
0x180011a6b  mov     ebx, r9d
0x180011a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a75  lea     rax, WPP_GLOBAL_Control
0x180011a7c  cmp     rcx, rax
0x180011a7f  jz      loc_180011B20
0x180011a85  test    byte ptr [rcx+1Ch], 1
0x180011a89  jz      loc_180011B20
0x180011a8f  mov     edx, 1Dh
0x180011a94  jmp     short loc_180011A34
0x180011a96  test    rax, rax
0x180011a99  jz      short loc_180011AE6
0x180011a9b  mov     rdx, rdi
0x180011a9e  mov     rcx, rax
0x180011aa1  call    cs:__imp_?FwParseAllPortVersions@@YAJPEBGPEAU_tag_FW_PORTS@@@Z; FwParseAllPortVersions(ushort const *,_tag_FW_PORTS *)
0x180011aa7  mov     ebx, eax
0x180011aa9  test    eax, eax
0x180011aab  js      short loc_180011AC3
0x180011aad  lea     r8, [rsp+48h+Context]; Context
0x180011ab2  xor     ecx, ecx; String
0x180011ab4  lea     rdx, Delimiter; ","
0x180011abb  call    cs:__imp_wcstok_s
0x180011ac1  jmp     short loc_180011A96
0x180011ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aca  lea     rax, WPP_GLOBAL_Control
0x180011ad1  cmp     rcx, rax
0x180011ad4  jz      short loc_180011B20
0x180011ad6  test    byte ptr [rcx+1Ch], 1
0x180011ada  jz      short loc_180011B20
0x180011adc  mov     edx, 1Eh
0x180011ae1  jmp     loc_180011A31
0x180011ae6  mov     rcx, rdi; struct _tag_FW_PORTS *
0x180011ae9  call    ?FwIsValidPorts@@YAHPEBU_tag_FW_PORTS@@@Z; FwIsValidPorts(_tag_FW_PORTS const *)
0x180011aee  test    eax, eax
0x180011af0  jnz     short loc_180011B20
0x180011af2  mov     r9d, 80070057h
0x180011af8  mov     ebx, r9d
0x180011afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b02  lea     rax, WPP_GLOBAL_Control
0x180011b09  cmp     rcx, rax
0x180011b0c  jz      short loc_180011B20
0x180011b0e  test    byte ptr [rcx+1Ch], 1
0x180011b12  jz      short loc_180011B20
0x180011b14  mov     edx, 1Fh
0x180011b19  jmp     loc_180011A34
0x180011b1e  mov     ebx, esi
0x180011b20  mov     rcx, [rsp+48h+String]
0x180011b25  call    cs:__imp_FwBaseFree
0x180011b2b  test    ebx, ebx
0x180011b2d  jns     short loc_180011B45
0x180011b2f  mov     rcx, [rdi+10h]
0x180011b33  call    cs:__imp_FwBaseFree
0x180011b39  xorps   xmm0, xmm0
0x180011b3c  xor     eax, eax
0x180011b3e  movups  xmmword ptr [rdi], xmm0
0x180011b41  mov     [rdi+10h], rax
0x180011b45  mov     eax, ebx
0x180011b47  mov     rcx, [rsp+48h+var_18]
0x180011b4c  xor     rcx, rsp; StackCookie
0x180011b4f  call    __security_check_cookie
0x180011b54  mov     rbx, [rsp+48h+arg_10]
0x180011b59  mov     rsi, [rsp+48h+arg_18]
0x180011b5e  add     rsp, 40h
0x180011b62  pop     rdi
0x180011b63  retn
```
