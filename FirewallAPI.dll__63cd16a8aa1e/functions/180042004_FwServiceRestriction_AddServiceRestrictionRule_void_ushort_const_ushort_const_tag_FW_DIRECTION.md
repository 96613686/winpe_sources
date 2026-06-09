# FwServiceRestriction::AddServiceRestrictionRule(void *,ushort const *,ushort const *,_tag_FW_DIRECTION)

- ea: `0x180042004`
- end: `0x1800422ec`
- name: `?AddServiceRestrictionRule@FwServiceRestriction@@AEAAJPEAXPEBG1W4_tag_FW_DIRECTION@@@Z`
- size: `744`
- prototype: `int __high(void *, const unsigned __int16 *, const unsigned __int16 *, enum _tag_FW_DIRECTION)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180042b70`

## callees

- `0x180005954`
- `0x1800140b0`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x180042004`
- `0x1800422f4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800420c4`
- `RPCRT4!UuidCreate` at `0x1800420c4`
- `RPCRT4!UuidToStringW` at `0x1800420d4`
- `RPCRT4!UuidToStringW` at `0x1800420d4`
- `RPCRT4!RpcStringFreeW` at `0x1800422af`
- `RPCRT4!RpcStringFreeW` at `0x1800422af`
- `fwbase!FwStringCopy` at `0x1800420f2`
- `fwbase!FwStringCopy` at `0x1800421c9`
- `fwbase!FwStringCopy` at `0x18004220a`
- `fwbase!FwStringCopy` at `0x1800420f2`
- `fwbase!FwStringCopy` at `0x1800421c9`
- `fwbase!FwStringCopy` at `0x18004220a`
- `FWPolicyIOMgr!FwEmptyWFRule` at `0x1800422ba`
- `FWPolicyIOMgr!FwEmptyWFRule` at `0x1800422ba`

## pseudocode

```c
__int64 __fastcall FwServiceRestriction::AddServiceRestrictionRule(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  unsigned int v8; // esi
  unsigned int v9; // r14d
  signed int v10; // ebx
  FwServiceRestriction *v11; // rcx
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  FwServiceRestriction *v14; // rcx
  int v15; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-E0h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE Src[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+6Ch] [rbp-94h]
  __int16 v26; // [rsp+70h] [rbp-90h]
  _BYTE v27[8]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v28[8]; // [rsp+158h] [rbp+58h] BYREF
  int v29; // [rsp+160h] [rbp+60h]
  __int16 v30; // [rsp+164h] [rbp+64h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids);
  memset_0(Src, 0, 0x1F8u);
  v8 = 23308;
  StringUuid = 0;
  if ( a5 != 1 )
    v8 = 23310;
  Uuid = 0;
  v9 = 23309;
  if ( a5 != 1 )
    v9 = 23311;
  v20 = 545;
  UuidCreate(&Uuid);
  if ( UuidToStringW(&Uuid, &StringUuid) )
  {
    v10 = -2147418113;
    goto LABEL_37;
  }
  v10 = FwStringCopy(StringUuid, v21);
  if ( v10 >= 0 )
  {
    v10 = FwServiceRestriction::BuildServiceNameDescString(v11, v8, a3, &v22);
    if ( v10 >= 0 )
    {
      v10 = FwServiceRestriction::BuildServiceNameDescString(v14, v9, a3, &v23);
      if ( v10 >= 0 )
      {
        v25 = a5;
        v26 = 256;
        v10 = FwStringCopy(a4, v27);
        if ( v10 >= 0 )
        {
          v10 = FwStringCopy(a3, v28);
          if ( v10 >= 0 )
          {
            v29 = 2;
            v30 = 1;
            v24 = 0x7FFFFFFF;
            v15 = FWAddFirewallRule(a2, Src);
            v10 = v15;
            if ( v15 > 0 )
              v10 = (unsigned __int16)v15 | 0x80070000;
            if ( v10 < 0 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v13 = 46;
                goto LABEL_36;
              }
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 45;
              goto LABEL_36;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 44;
            goto LABEL_36;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 43;
          goto LABEL_36;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 42;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 41;
LABEL_36:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids, (unsigned int)v10);
    }
  }
LABEL_37:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  FwEmptyWFRule(Src);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180042004  mov     [rsp-8+arg_0], rbx
0x180042009  push    rbp
0x18004200a  push    rsi
0x18004200b  push    rdi
0x18004200c  push    r12
0x18004200e  push    r13
0x180042010  push    r14
0x180042012  push    r15
0x180042014  lea     rbp, [rsp-150h]
0x18004201c  sub     rsp, 250h
0x180042023  mov     rax, cs:__security_cookie
0x18004202a  xor     rax, rsp
0x18004202d  mov     [rbp+180h+var_40], rax
0x180042034  mov     r13, r9
0x180042037  mov     rdi, r8
0x18004203a  mov     r12, rdx
0x18004203d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042044  lea     rax, WPP_GLOBAL_Control
0x18004204b  cmp     rcx, rax
0x18004204e  jz      short loc_18004206B
0x180042050  test    byte ptr [rcx+1Ch], 8
0x180042054  jz      short loc_18004206B
0x180042056  mov     rcx, [rcx+10h]
0x18004205a  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180042061  mov     edx, 28h ; '('
0x180042066  call    WPP_SF_
0x18004206b  xor     edx, edx; Val
0x18004206d  lea     rcx, [rsp+280h+Src]; void *
0x180042072  mov     r8d, 1F8h; Size
0x180042078  call    memset_0
0x18004207d  mov     r15d, [rbp+180h+arg_20]
0x180042084  mov     esi, 5B0Ch
0x180042089  mov     ecx, 1
0x18004208e  mov     [rsp+280h+StringUuid], 0
0x180042097  cmp     r15d, ecx
0x18004209a  xorps   xmm0, xmm0
0x18004209d  lea     rcx, [rsp+280h+Uuid]; Uuid
0x1800420a2  lea     eax, [rsi+2]
0x1800420a5  cmovnz  esi, eax
0x1800420a8  mov     eax, 5B0Fh
0x1800420ad  movups  xmmword ptr [rsp+280h+Uuid.Data1], xmm0
0x1800420b2  lea     r14d, [rax-2]
0x1800420b6  cmovnz  r14d, eax
0x1800420ba  mov     eax, 221h
0x1800420bf  mov     [rsp+280h+var_238], ax
0x1800420c4  call    cs:__imp_UuidCreate
0x1800420ca  lea     rdx, [rsp+280h+StringUuid]; StringUuid
0x1800420cf  lea     rcx, [rsp+280h+Uuid]; Uuid
0x1800420d4  call    cs:__imp_UuidToStringW
0x1800420da  test    eax, eax
0x1800420dc  jz      short loc_1800420E8
0x1800420de  mov     ebx, 8000FFFFh
0x1800420e3  jmp     loc_1800422A2
0x1800420e8  mov     rcx, [rsp+280h+StringUuid]
0x1800420ed  lea     rdx, [rsp+280h+var_230]
0x1800420f2  call    cs:__imp_FwStringCopy
0x1800420f8  mov     ebx, eax
0x1800420fa  test    eax, eax
0x1800420fc  jns     short loc_18004212C
0x1800420fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180042105  lea     rax, WPP_GLOBAL_Control
0x18004210c  cmp     rcx, rax
0x18004210f  jz      loc_1800422A2
0x180042115  mov     edi, 1
0x18004211a  test    [rcx+1Ch], dil
0x18004211e  jz      loc_1800422A2
0x180042124  lea     edx, [rdi+28h]
0x180042127  jmp     loc_18004228F
0x18004212c  lea     r9, [rsp+280h+var_228]; unsigned __int16 **
0x180042131  mov     r8, rdi; unsigned __int16 *
0x180042134  mov     edx, esi; unsigned int
0x180042136  call    ?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z; FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)
0x18004213b  mov     ebx, eax
0x18004213d  test    eax, eax
0x18004213f  jns     short loc_18004216F
0x180042141  mov     rcx, cs:WPP_GLOBAL_Control
0x180042148  lea     rax, WPP_GLOBAL_Control
0x18004214f  cmp     rcx, rax
0x180042152  jz      loc_1800422A2
0x180042158  mov     edi, 1
0x18004215d  test    [rcx+1Ch], dil
0x180042161  jz      loc_1800422A2
0x180042167  lea     edx, [rdi+29h]
0x18004216a  jmp     loc_18004228F
0x18004216f  lea     r9, [rsp+280h+var_220]; unsigned __int16 **
0x180042174  mov     r8, rdi; unsigned __int16 *
0x180042177  mov     edx, r14d; unsigned int
0x18004217a  call    ?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z; FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)
0x18004217f  mov     ebx, eax
0x180042181  test    eax, eax
0x180042183  jns     short loc_1800421B3
0x180042185  mov     rcx, cs:WPP_GLOBAL_Control
0x18004218c  lea     rax, WPP_GLOBAL_Control
0x180042193  cmp     rcx, rax
0x180042196  jz      loc_1800422A2
0x18004219c  mov     edi, 1
0x1800421a1  test    [rcx+1Ch], dil
0x1800421a5  jz      loc_1800422A2
0x1800421ab  lea     edx, [rdi+2Ah]
0x1800421ae  jmp     loc_18004228F
0x1800421b3  mov     eax, 100h
0x1800421b8  mov     [rsp+280h+var_214], r15d
0x1800421bd  lea     rdx, [rbp+180h+var_130]
0x1800421c1  mov     [rsp+280h+var_210], ax
0x1800421c6  mov     rcx, r13
0x1800421c9  call    cs:__imp_FwStringCopy
0x1800421cf  mov     ebx, eax
0x1800421d1  test    eax, eax
0x1800421d3  jns     short loc_180042203
0x1800421d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421dc  lea     rax, WPP_GLOBAL_Control
0x1800421e3  cmp     rcx, rax
0x1800421e6  jz      loc_1800422A2
0x1800421ec  mov     edi, 1
0x1800421f1  test    [rcx+1Ch], dil
0x1800421f5  jz      loc_1800422A2
0x1800421fb  lea     edx, [rdi+2Bh]
0x1800421fe  jmp     loc_18004228F
0x180042203  lea     rdx, [rbp+180h+var_128]
0x180042207  mov     rcx, rdi
0x18004220a  call    cs:__imp_FwStringCopy
0x180042210  mov     ebx, eax
0x180042212  test    eax, eax
0x180042214  jns     short loc_180042239
0x180042216  mov     rcx, cs:WPP_GLOBAL_Control
0x18004221d  lea     rax, WPP_GLOBAL_Control
0x180042224  cmp     rcx, rax
0x180042227  jz      short loc_1800422A2
0x180042229  mov     edi, 1
0x18004222e  test    [rcx+1Ch], dil
0x180042232  jz      short loc_1800422A2
0x180042234  lea     edx, [rdi+2Ch]
0x180042237  jmp     short loc_18004228F
0x180042239  mov     edi, 1
0x18004223e  mov     [rbp+180h+var_120], 2
0x180042245  lea     rdx, [rsp+280h+Src]; Src
0x18004224a  mov     [rbp+180h+var_11C], di
0x18004224e  mov     rcx, r12; __int64
0x180042251  mov     [rsp+280h+var_218], 7FFFFFFFh
0x180042259  call    FWAddFirewallRule
0x18004225e  mov     ebx, eax
0x180042260  test    eax, eax
0x180042262  jle     short loc_18004226D
0x180042264  movzx   ebx, ax
0x180042267  or      ebx, 80070000h
0x18004226d  test    ebx, ebx
0x18004226f  jns     short loc_1800422A2
0x180042271  mov     rcx, cs:WPP_GLOBAL_Control
0x180042278  lea     rax, WPP_GLOBAL_Control
0x18004227f  cmp     rcx, rax
0x180042282  jz      short loc_1800422A2
0x180042284  test    [rcx+1Ch], dil
0x180042288  jz      short loc_1800422A2
0x18004228a  mov     edx, 2Eh ; '.'
0x18004228f  mov     rcx, [rcx+10h]
0x180042293  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x18004229a  mov     r9d, ebx
0x18004229d  call    WPP_SF_d
0x1800422a2  cmp     [rsp+280h+StringUuid], 0
0x1800422a8  jz      short loc_1800422B5
0x1800422aa  lea     rcx, [rsp+280h+StringUuid]; String
0x1800422af  call    cs:__imp_RpcStringFreeW
0x1800422b5  lea     rcx, [rsp+280h+Src]
0x1800422ba  call    cs:__imp_FwEmptyWFRule
0x1800422c0  mov     eax, ebx
0x1800422c2  mov     rcx, [rbp+180h+var_40]
0x1800422c9  xor     rcx, rsp; StackCookie
0x1800422cc  call    __security_check_cookie
0x1800422d1  mov     rbx, [rsp+280h+arg_0]
0x1800422d9  add     rsp, 250h
0x1800422e0  pop     r15
0x1800422e2  pop     r14
0x1800422e4  pop     r13
0x1800422e6  pop     r12
0x1800422e8  pop     rdi
0x1800422e9  pop     rsi
0x1800422ea  pop     rbp
0x1800422eb  retn
```
