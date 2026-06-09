# FwBstrToPorts(ushort * const,_tag_FW_PORTS *,bool)

- ea: `0x180011760`
- end: `0x18001195f`
- name: `?FwBstrToPorts@@YAJQEAGPEAU_tag_FW_PORTS@@_N@Z`
- size: `511`
- prototype: `int(unsigned __int16 *const, struct _tag_FW_PORTS *, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011ed0`
- `0x180042b60`
- `0x180054c80`

## callees

- `0x180005e0c`
- `0x180011760`
- `0x180012e90`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800117b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800117b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011836`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800118a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180011836`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800118a3`
- `fwbase!FwBaseFree` at `0x180011913`
- `fwbase!FwBaseFree` at `0x180011927`
- `fwbase!FwBaseFree` at `0x180011913`
- `fwbase!FwBaseFree` at `0x180011927`
- `fwbase!FwStringCopy` at `0x1800117d5`
- `fwbase!FwStringCopy` at `0x1800117d5`
- `FWPolicyIOMgr!FwParseAllPortVersions` at `0x180011883`
- `FWPolicyIOMgr!FwParseAllPortVersions` at `0x180011883`

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
0x180011760  mov     r11, rsp
0x180011763  mov     [r11+18h], rbx
0x180011767  mov     [r11+20h], rsi
0x18001176b  push    rdi
0x18001176c  sub     rsp, 40h
0x180011770  mov     rax, cs:__security_cookie
0x180011777  xor     rax, rsp
0x18001177a  mov     [rsp+48h+var_18], rax
0x18001177f  xor     esi, esi
0x180011781  xor     eax, eax
0x180011783  mov     [r11-28h], rsi
0x180011787  xorps   xmm0, xmm0
0x18001178a  mov     [r11-20h], rsi
0x18001178e  mov     rdi, rdx
0x180011791  mov     rbx, rcx
0x180011794  movups  xmmword ptr [rdx], xmm0
0x180011797  mov     [rdx+10h], rax
0x18001179b  test    rcx, rcx
0x18001179e  jz      loc_18001190C
0x1800117a4  cmp     [rcx], si
0x1800117a7  jz      loc_18001190C
0x1800117ad  test    r8b, r8b
0x1800117b0  jz      short loc_1800117CD
0x1800117b2  lea     rdx, asc_180080438; "*"
0x1800117b9  call    cs:__imp__o__wcsicmp
0x1800117c0  nop     dword ptr [rax+rax+00h]
0x1800117c5  test    eax, eax
0x1800117c7  jz      loc_18001190C
0x1800117cd  lea     rdx, [rsp+48h+String]
0x1800117d2  mov     rcx, rbx
0x1800117d5  call    cs:__imp_FwStringCopy
0x1800117dc  nop     dword ptr [rax+rax+00h]
0x1800117e1  mov     ebx, eax
0x1800117e3  test    eax, eax
0x1800117e5  jns     short loc_180011825
0x1800117e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117ee  lea     rax, WPP_GLOBAL_Control
0x1800117f5  cmp     rcx, rax
0x1800117f8  jz      loc_18001190E
0x1800117fe  test    byte ptr [rcx+1Ch], 1
0x180011802  jz      loc_18001190E
0x180011808  mov     edx, 1Ch
0x18001180d  mov     r9d, ebx
0x180011810  mov     rcx, [rcx+10h]
0x180011814  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18001181b  call    WPP_SF_d
0x180011820  jmp     loc_18001190E
0x180011825  mov     rcx, [rsp+48h+String]; String
0x18001182a  lea     r8, [rsp+48h+Context]; Context
0x18001182f  lea     rdx, Delimiter; ","
0x180011836  call    cs:__imp_wcstok_s
0x18001183d  nop     dword ptr [rax+rax+00h]
0x180011842  test    rax, rax
0x180011845  jnz     short loc_18001187D
0x180011847  mov     r9d, 80070057h
0x18001184d  mov     ebx, r9d
0x180011850  mov     rcx, cs:WPP_GLOBAL_Control
0x180011857  lea     rax, WPP_GLOBAL_Control
0x18001185e  cmp     rcx, rax
0x180011861  jz      loc_18001190E
0x180011867  test    byte ptr [rcx+1Ch], 1
0x18001186b  jz      loc_18001190E
0x180011871  mov     edx, 1Dh
0x180011876  jmp     short loc_180011810
0x180011878  test    rax, rax
0x18001187b  jz      short loc_1800118D4
0x18001187d  mov     rdx, rdi
0x180011880  mov     rcx, rax
0x180011883  call    cs:__imp_?FwParseAllPortVersions@@YAJPEBGPEAU_tag_FW_PORTS@@@Z; FwParseAllPortVersions(ushort const *,_tag_FW_PORTS *)
0x18001188a  nop     dword ptr [rax+rax+00h]
0x18001188f  mov     ebx, eax
0x180011891  test    eax, eax
0x180011893  js      short loc_1800118B1
0x180011895  lea     r8, [rsp+48h+Context]; Context
0x18001189a  xor     ecx, ecx; String
0x18001189c  lea     rdx, Delimiter; ","
0x1800118a3  call    cs:__imp_wcstok_s
0x1800118aa  nop     dword ptr [rax+rax+00h]
0x1800118af  jmp     short loc_180011878
0x1800118b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118b8  lea     rax, WPP_GLOBAL_Control
0x1800118bf  cmp     rcx, rax
0x1800118c2  jz      short loc_18001190E
0x1800118c4  test    byte ptr [rcx+1Ch], 1
0x1800118c8  jz      short loc_18001190E
0x1800118ca  mov     edx, 1Eh
0x1800118cf  jmp     loc_18001180D
0x1800118d4  mov     rcx, rdi; struct _tag_FW_PORTS *
0x1800118d7  call    ?FwIsValidPorts@@YAHPEBU_tag_FW_PORTS@@@Z; FwIsValidPorts(_tag_FW_PORTS const *)
0x1800118dc  test    eax, eax
0x1800118de  jnz     short loc_18001190E
0x1800118e0  mov     r9d, 80070057h
0x1800118e6  mov     ebx, r9d
0x1800118e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118f0  lea     rax, WPP_GLOBAL_Control
0x1800118f7  cmp     rcx, rax
0x1800118fa  jz      short loc_18001190E
0x1800118fc  test    byte ptr [rcx+1Ch], 1
0x180011900  jz      short loc_18001190E
0x180011902  mov     edx, 1Fh
0x180011907  jmp     loc_180011810
0x18001190c  mov     ebx, esi
0x18001190e  mov     rcx, [rsp+48h+String]
0x180011913  call    cs:__imp_FwBaseFree
0x18001191a  nop     dword ptr [rax+rax+00h]
0x18001191f  test    ebx, ebx
0x180011921  jns     short loc_18001193F
0x180011923  mov     rcx, [rdi+10h]
0x180011927  call    cs:__imp_FwBaseFree
0x18001192e  nop     dword ptr [rax+rax+00h]
0x180011933  xorps   xmm0, xmm0
0x180011936  xor     eax, eax
0x180011938  movups  xmmword ptr [rdi], xmm0
0x18001193b  mov     [rdi+10h], rax
0x18001193f  mov     eax, ebx
0x180011941  mov     rcx, [rsp+48h+var_18]
0x180011946  xor     rcx, rsp; StackCookie
0x180011949  call    __security_check_cookie
0x18001194e  mov     rbx, [rsp+48h+arg_10]
0x180011953  mov     rsi, [rsp+48h+arg_18]
0x180011958  add     rsp, 40h
0x18001195c  pop     rdi
0x18001195d  retn
```
