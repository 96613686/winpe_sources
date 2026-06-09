# SaveRule(_tag_FW_RULE *,void *)

- ea: `0x180014368`
- end: `0x18001467f`
- name: `?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z`
- size: `791`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE *, void *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000270c`
- `0x180013e64`
- `0x180030d08`
- `0x180030da4`
- `0x1800392c0`
- `0x180044108`
- `0x180044480`

## callees

- `0x1800051c0`
- `0x180005954`
- `0x180009760`
- `0x1800140b0`
- `0x180014368`
- `0x180014690`
- `0x1800277b0`
- `0x1800284c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014556`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014556`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014512`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014512`
- `fwbase!FwBaseFree` at `0x180014429`
- `fwbase!FwBaseFree` at `0x180014429`
- `fwbase!FwStringCopy` at `0x1800145b4`
- `fwbase!FwStringCopy` at `0x1800145b4`

## pseudocode

```c
__int64 __fastcall SaveRule(struct _tag_FW_RULE *a1, void *a2)
{
  __int64 v2; // r15
  __int16 v4; // r13
  int v6; // r14d
  __int64 v7; // r12
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int v12; // eax
  FwPolicy2 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // [rsp+20h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+28h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-88h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  v4 = *((_WORD *)a1 + 4);
  v6 = 0;
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  v18 = 0;
  if ( v4 == 256 )
  {
    *((_WORD *)a1 + 4) = 512;
    v8 = CoCreateGuid(&pguid);
    if ( v8 >= 0 )
    {
      if ( StringFromGUID2(&pguid, sz, 39) )
      {
        v8 = FwStringCopy(sz, &v18);
        if ( v8 >= 0 )
        {
          v6 = 1;
          *((_QWORD *)a1 + 2) = v18;
          goto LABEL_2;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_8;
        v17 = 68;
      }
      else
      {
        v8 = -2147418113;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_8;
        v17 = 67;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_8;
      v17 = 66;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v8);
    goto LABEL_8;
  }
LABEL_2:
  v7 = *(_QWORD *)a1;
  *(_QWORD *)a1 = 0;
  if ( v6 != 1 )
  {
    v8 = FwRuleUnlocalize(a2, a1);
    if ( v8 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_7;
      v14 = 70;
    }
    else
    {
      v9 = FWSetFirewallRule((__int64)a2, a1);
      v8 = v9;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_7;
      if ( v8 == -2147024894 )
      {
        v12 = FWAddFirewallRule((__int64)a2, a1);
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( v8 >= 0 )
          goto LABEL_7;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_7;
        v14 = 71;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_7;
        v14 = 72;
      }
    }
LABEL_45:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v8);
    goto LABEL_7;
  }
  v15 = FWAddFirewallRule((__int64)a2, a1);
  v8 = v15;
  if ( v15 > 0 )
    v8 = (unsigned __int16)v15 | 0x80070000;
  if ( v8 >= 0 )
  {
    FWDeleteFirewallRule(a2, v2);
    goto LABEL_7;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 69;
    goto LABEL_45;
  }
LABEL_7:
  *(_QWORD *)a1 = v7;
  if ( v8 < 0 )
  {
LABEL_8:
    v10 = v18;
    *((_QWORD *)a1 + 2) = v2;
    *((_WORD *)a1 + 4) = v4;
    goto LABEL_9;
  }
  if ( v6 != 1 )
    return (unsigned int)v8;
  v10 = v2;
LABEL_9:
  FwBaseFree(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014368  mov     [rsp+arg_10], rbx
0x18001436d  mov     [rsp+arg_18], rbp
0x180014372  push    rdi
0x180014373  push    r12
0x180014375  push    r13
0x180014377  push    r14
0x180014379  push    r15
0x18001437b  sub     rsp, 0A0h
0x180014382  mov     rax, cs:__security_cookie
0x180014389  xor     rax, rsp
0x18001438c  mov     [rsp+0C8h+var_38], rax
0x180014394  mov     r15, [rcx+10h]
0x180014398  mov     rbp, rdx
0x18001439b  movzx   r13d, word ptr [rcx+8]
0x1800143a0  mov     rdi, rcx
0x1800143a3  xorps   xmm0, xmm0
0x1800143a6  lea     rcx, [rsp+0C8h+sz]; void *
0x1800143ab  xor     r14d, r14d
0x1800143ae  xor     edx, edx; Val
0x1800143b0  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x1800143b5  lea     r8d, [r14+4Eh]; Size
0x1800143b9  call    memset_0
0x1800143be  mov     eax, 100h
0x1800143c3  mov     [rsp+0C8h+var_A8], r14
0x1800143c8  cmp     r13w, ax
0x1800143cc  jz      loc_180014507
0x1800143d2  mov     r12, [rdi]
0x1800143d5  mov     rdx, rdi; Src
0x1800143d8  mov     qword ptr [rdi], 0
0x1800143df  mov     rcx, rbp; __int64
0x1800143e2  cmp     r14d, 1
0x1800143e6  jz      loc_1800144C0
0x1800143ec  call    ?FwRuleUnlocalize@@YAJPEAXPEAU_tag_FW_RULE@@@Z; FwRuleUnlocalize(void *,_tag_FW_RULE *)
0x1800143f1  mov     ebx, eax
0x1800143f3  test    eax, eax
0x1800143f5  js      loc_180014607
0x1800143fb  mov     rdx, rdi; Src
0x1800143fe  mov     rcx, rbp; __int64
0x180014401  call    FWSetFirewallRule
0x180014406  mov     ebx, eax
0x180014408  test    eax, eax
0x18001440a  jg      short loc_18001445E
0x18001440c  test    ebx, ebx
0x18001440e  js      short loc_180014469
0x180014410  mov     [rdi], r12
0x180014413  test    ebx, ebx
0x180014415  jns     loc_18001466D
0x18001441b  mov     rcx, [rsp+0C8h+var_A8]
0x180014420  mov     [rdi+10h], r15
0x180014424  mov     [rdi+8], r13w
0x180014429  call    cs:__imp_FwBaseFree
0x18001442f  mov     eax, ebx
0x180014431  mov     rcx, [rsp+0C8h+var_38]
0x180014439  xor     rcx, rsp; StackCookie
0x18001443c  call    __security_check_cookie
0x180014441  lea     r11, [rsp+0C8h+var_28]
0x180014449  mov     rbx, [r11+40h]
0x18001444d  mov     rbp, [r11+48h]
0x180014451  mov     rsp, r11
0x180014454  pop     r15
0x180014456  pop     r14
0x180014458  pop     r13
0x18001445a  pop     r12
0x18001445c  pop     rdi
0x18001445d  retn
0x18001445e  movzx   ebx, ax
0x180014461  or      ebx, 80070000h
0x180014467  jmp     short loc_18001440C
0x180014469  cmp     ebx, 80070002h
0x18001446f  jnz     loc_18001462F
0x180014475  mov     rdx, rdi; Src
0x180014478  mov     rcx, rbp; __int64
0x18001447b  call    FWAddFirewallRule
0x180014480  mov     ebx, eax
0x180014482  test    eax, eax
0x180014484  jg      short loc_1800144B5
0x180014486  test    ebx, ebx
0x180014488  jns     short loc_180014410
0x18001448a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014491  lea     rax, WPP_GLOBAL_Control
0x180014498  cmp     rcx, rax
0x18001449b  jz      loc_180014410
0x1800144a1  test    byte ptr [rcx+1Ch], 1
0x1800144a5  jz      loc_180014410
0x1800144ab  mov     edx, 47h ; 'G'
0x1800144b0  jmp     loc_180014655
0x1800144b5  movzx   ebx, ax
0x1800144b8  or      ebx, 80070000h
0x1800144be  jmp     short loc_180014486
0x1800144c0  call    FWAddFirewallRule
0x1800144c5  mov     ebx, eax
0x1800144c7  test    eax, eax
0x1800144c9  jle     short loc_1800144D4
0x1800144cb  movzx   ebx, ax
0x1800144ce  or      ebx, 80070000h
0x1800144d4  test    ebx, ebx
0x1800144d6  jns     loc_1800145F7
0x1800144dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144e3  lea     rax, WPP_GLOBAL_Control
0x1800144ea  cmp     rcx, rax
0x1800144ed  jz      loc_180014410
0x1800144f3  test    byte ptr [rcx+1Ch], 1
0x1800144f7  jz      loc_180014410
0x1800144fd  mov     edx, 45h ; 'E'
0x180014502  jmp     loc_180014655
0x180014507  lea     rcx, [rsp+0C8h+pguid]; pguid
0x18001450c  mov     word ptr [rdi+8], 200h
0x180014512  call    cs:__imp_CoCreateGuid
0x180014518  mov     ebx, eax
0x18001451a  test    eax, eax
0x18001451c  jns     short loc_180014546
0x18001451e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014525  lea     rax, WPP_GLOBAL_Control
0x18001452c  cmp     rcx, rax
0x18001452f  jz      loc_18001441B
0x180014535  test    byte ptr [rcx+1Ch], 1
0x180014539  jz      loc_18001441B
0x18001453f  mov     edx, 42h ; 'B'
0x180014544  jmp     short loc_180014592
0x180014546  mov     r8d, 27h ; '''; cchMax
0x18001454c  lea     rdx, [rsp+0C8h+sz]; lpsz
0x180014551  lea     rcx, [rsp+0C8h+pguid]; rguid
0x180014556  call    cs:__imp_StringFromGUID2
0x18001455c  test    eax, eax
0x18001455e  jnz     short loc_1800145AA
0x180014560  mov     ebx, 8000FFFFh
0x180014565  mov     rcx, cs:WPP_GLOBAL_Control
0x18001456c  lea     rax, WPP_GLOBAL_Control
0x180014573  cmp     rcx, rax
0x180014576  jz      loc_18001441B
0x18001457c  test    byte ptr [rcx+1Ch], 1
0x180014580  jz      loc_18001441B
0x180014586  mov     edx, 43h ; 'C'
0x18001458b  jmp     short loc_180014592
0x18001458d  mov     edx, 44h ; 'D'
0x180014592  mov     rcx, [rcx+10h]
0x180014596  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18001459d  mov     r9d, ebx
0x1800145a0  call    WPP_SF_d
0x1800145a5  jmp     loc_18001441B
0x1800145aa  lea     rdx, [rsp+0C8h+var_A8]
0x1800145af  lea     rcx, [rsp+0C8h+sz]
0x1800145b4  call    cs:__imp_FwStringCopy
0x1800145ba  mov     ebx, eax
0x1800145bc  test    eax, eax
0x1800145be  jns     short loc_1800145E3
0x1800145c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145c7  lea     rax, WPP_GLOBAL_Control
0x1800145ce  cmp     rcx, rax
0x1800145d1  jz      loc_18001441B
0x1800145d7  test    byte ptr [rcx+1Ch], 1
0x1800145db  jz      loc_18001441B
0x1800145e1  jmp     short loc_18001458D
0x1800145e3  mov     rax, [rsp+0C8h+var_A8]
0x1800145e8  mov     r14d, 1
0x1800145ee  mov     [rdi+10h], rax
0x1800145f2  jmp     loc_1800143D2
0x1800145f7  mov     rdx, r15
0x1800145fa  mov     rcx, rbp
0x1800145fd  call    FWDeleteFirewallRule
0x180014602  jmp     loc_180014410
0x180014607  mov     rcx, cs:WPP_GLOBAL_Control
0x18001460e  lea     rax, WPP_GLOBAL_Control
0x180014615  cmp     rcx, rax
0x180014618  jz      loc_180014410
0x18001461e  test    byte ptr [rcx+1Ch], 1
0x180014622  jz      loc_180014410
0x180014628  mov     edx, 46h ; 'F'
0x18001462d  jmp     short loc_180014655
0x18001462f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014636  lea     rax, WPP_GLOBAL_Control
0x18001463d  cmp     rcx, rax
0x180014640  jz      loc_180014410
0x180014646  test    byte ptr [rcx+1Ch], 1
0x18001464a  jz      loc_180014410
0x180014650  mov     edx, 48h ; 'H'
0x180014655  mov     rcx, [rcx+10h]
0x180014659  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180014660  mov     r9d, ebx
0x180014663  call    WPP_SF_d
0x180014668  jmp     loc_180014410
0x18001466d  cmp     r14d, 1
0x180014671  jnz     loc_18001442F
0x180014677  mov     rcx, r15
0x18001467a  jmp     loc_180014429
```
