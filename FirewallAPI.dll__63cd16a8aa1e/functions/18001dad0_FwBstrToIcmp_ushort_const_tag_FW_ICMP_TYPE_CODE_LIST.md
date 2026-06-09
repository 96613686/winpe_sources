# FwBstrToIcmp(ushort * const,_tag_FW_ICMP_TYPE_CODE_LIST *)

- ea: `0x18001dad0`
- end: `0x18001dc03`
- name: `?FwBstrToIcmp@@YAJQEAGPEAU_tag_FW_ICMP_TYPE_CODE_LIST@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(unsigned __int16 *const, struct _tag_FW_ICMP_TYPE_CODE_LIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001d8b0`

## callees

- `0x180005954`
- `0x18001dad0`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001db1e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001db1e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001db82`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001db82`
- `fwbase!FwBaseFree` at `0x18001dbca`
- `fwbase!FwBaseFree` at `0x18001dbd8`
- `fwbase!FwBaseFree` at `0x18001dbca`
- `fwbase!FwBaseFree` at `0x18001dbd8`
- `fwbase!FwStringCopy` at `0x18001db34`
- `fwbase!FwStringCopy` at `0x18001db34`
- `FWPolicyIOMgr!FwParseICMPTypeCodes` at `0x18001db93`
- `FWPolicyIOMgr!FwParseICMPTypeCodes` at `0x18001db93`

## pseudocode

```c
__int64 __fastcall FwBstrToIcmp(unsigned __int16 *const a1, struct _tag_FW_ICMP_TYPE_CODE_LIST *a2)
{
  int v4; // ebx
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  wchar_t *i; // rcx
  wchar_t *v8; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF

  String = 0;
  Context = 0;
  *(_OWORD *)a2 = 0;
  if ( a1 && *a1 && (unsigned int)_o__wcsicmp(a1, "*") )
  {
    v4 = FwStringCopy(a1, &String);
    if ( v4 >= 0 )
    {
      for ( i = String; ; i = 0 )
      {
        v8 = wcstok_s(i, L",", &Context);
        if ( !v8 )
          break;
        v4 = FwParseICMPTypeCodes(v8, a2);
        if ( v4 < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 33;
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
        v6 = 32;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v4);
      }
    }
  }
  else
  {
    v4 = 0;
  }
  FwBaseFree(String);
  if ( v4 < 0 )
  {
    FwBaseFree(*((_QWORD *)a2 + 1));
    *(_OWORD *)a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001dad0  mov     r11, rsp
0x18001dad3  mov     [r11+18h], rbx
0x18001dad7  mov     [r11+20h], rsi
0x18001dadb  push    rdi
0x18001dadc  sub     rsp, 40h
0x18001dae0  mov     rax, cs:__security_cookie
0x18001dae7  xor     rax, rsp
0x18001daea  mov     [rsp+48h+var_18], rax
0x18001daef  xor     esi, esi
0x18001daf1  xorps   xmm0, xmm0
0x18001daf4  mov     [r11-28h], rsi
0x18001daf8  mov     rdi, rdx
0x18001dafb  mov     [r11-20h], rsi
0x18001daff  mov     rbx, rcx
0x18001db02  movups  xmmword ptr [rdx], xmm0
0x18001db05  test    rcx, rcx
0x18001db08  jz      loc_18001DBC3
0x18001db0e  cmp     [rcx], si
0x18001db11  jz      loc_18001DBC3
0x18001db17  lea     rdx, asc_18007C438; "*"
0x18001db1e  call    cs:__imp__o__wcsicmp
0x18001db24  test    eax, eax
0x18001db26  jz      loc_18001DBC3
0x18001db2c  lea     rdx, [rsp+48h+String]
0x18001db31  mov     rcx, rbx
0x18001db34  call    cs:__imp_FwStringCopy
0x18001db3a  mov     ebx, eax
0x18001db3c  test    eax, eax
0x18001db3e  jns     short loc_18001DB71
0x18001db40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db47  lea     rax, WPP_GLOBAL_Control
0x18001db4e  cmp     rcx, rax
0x18001db51  jz      short loc_18001DBC5
0x18001db53  test    byte ptr [rcx+1Ch], 1
0x18001db57  jz      short loc_18001DBC5
0x18001db59  lea     edx, [rsi+20h]
0x18001db5c  mov     rcx, [rcx+10h]
0x18001db60  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18001db67  mov     r9d, ebx
0x18001db6a  call    WPP_SF_d
0x18001db6f  jmp     short loc_18001DBC5
0x18001db71  mov     rcx, [rsp+48h+String]; String
0x18001db76  lea     r8, [rsp+48h+Context]; Context
0x18001db7b  lea     rdx, Delimiter; ","
0x18001db82  call    cs:__imp_wcstok_s
0x18001db88  test    rax, rax
0x18001db8b  jz      short loc_18001DBC5
0x18001db8d  mov     rdx, rdi
0x18001db90  mov     rcx, rax
0x18001db93  call    cs:__imp_?FwParseICMPTypeCodes@@YAJPEBGPEAU_tag_FW_ICMP_TYPE_CODE_LIST@@@Z; FwParseICMPTypeCodes(ushort const *,_tag_FW_ICMP_TYPE_CODE_LIST *)
0x18001db99  mov     ebx, eax
0x18001db9b  test    eax, eax
0x18001db9d  js      short loc_18001DBA3
0x18001db9f  xor     ecx, ecx
0x18001dba1  jmp     short loc_18001DB76
0x18001dba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbaa  lea     rax, WPP_GLOBAL_Control
0x18001dbb1  cmp     rcx, rax
0x18001dbb4  jz      short loc_18001DBC5
0x18001dbb6  test    byte ptr [rcx+1Ch], 1
0x18001dbba  jz      short loc_18001DBC5
0x18001dbbc  mov     edx, 21h ; '!'
0x18001dbc1  jmp     short loc_18001DB5C
0x18001dbc3  mov     ebx, esi
0x18001dbc5  mov     rcx, [rsp+48h+String]
0x18001dbca  call    cs:__imp_FwBaseFree
0x18001dbd0  test    ebx, ebx
0x18001dbd2  jns     short loc_18001DBE4
0x18001dbd4  mov     rcx, [rdi+8]
0x18001dbd8  call    cs:__imp_FwBaseFree
0x18001dbde  xorps   xmm0, xmm0
0x18001dbe1  movups  xmmword ptr [rdi], xmm0
0x18001dbe4  mov     eax, ebx
0x18001dbe6  mov     rcx, [rsp+48h+var_18]
0x18001dbeb  xor     rcx, rsp; StackCookie
0x18001dbee  call    __security_check_cookie
0x18001dbf3  mov     rbx, [rsp+48h+arg_10]
0x18001dbf8  mov     rsi, [rsp+48h+arg_18]
0x18001dbfd  add     rsp, 40h
0x18001dc01  pop     rdi
0x18001dc02  retn
```
