# FwServiceRestriction::AddServiceRestrictionRule(void *,ushort const *,ushort const *,_tag_FW_DIRECTION)

- ea: `0x180045344`
- end: `0x180045657`
- name: `?AddServiceRestrictionRule@FwServiceRestriction@@AEAAJPEAXPEBG1W4_tag_FW_DIRECTION@@@Z`
- size: `787`
- prototype: `int __high(void *, const unsigned __int16 *, const unsigned __int16 *, enum _tag_FW_DIRECTION)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180045f40`

## callees

- `0x180005e0c`
- `0x180014110`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180045344`
- `0x180045660`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180045404`
- `RPCRT4!UuidCreate` at `0x180045404`
- `RPCRT4!UuidToStringW` at `0x18004541a`
- `RPCRT4!UuidToStringW` at `0x18004541a`
- `RPCRT4!RpcStringFreeW` at `0x18004560d`
- `RPCRT4!RpcStringFreeW` at `0x18004560d`
- `fwbase!FwStringCopy` at `0x18004543e`
- `fwbase!FwStringCopy` at `0x18004551b`
- `fwbase!FwStringCopy` at `0x180045562`
- `fwbase!FwStringCopy` at `0x18004543e`
- `fwbase!FwStringCopy` at `0x18004551b`
- `fwbase!FwStringCopy` at `0x180045562`
- `FWPolicyIOMgr!FwEmptyWFRule` at `0x18004561e`
- `FWPolicyIOMgr!FwEmptyWFRule` at `0x18004561e`

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
0x180045344  mov     [rsp-8+arg_0], rbx
0x180045349  push    rbp
0x18004534a  push    rsi
0x18004534b  push    rdi
0x18004534c  push    r12
0x18004534e  push    r13
0x180045350  push    r14
0x180045352  push    r15
0x180045354  lea     rbp, [rsp-150h]
0x18004535c  sub     rsp, 250h
0x180045363  mov     rax, cs:__security_cookie
0x18004536a  xor     rax, rsp
0x18004536d  mov     [rbp+180h+var_40], rax
0x180045374  mov     r13, r9
0x180045377  mov     rdi, r8
0x18004537a  mov     r12, rdx
0x18004537d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045384  lea     rax, WPP_GLOBAL_Control
0x18004538b  cmp     rcx, rax
0x18004538e  jz      short loc_1800453AB
0x180045390  test    byte ptr [rcx+1Ch], 8
0x180045394  jz      short loc_1800453AB
0x180045396  mov     rcx, [rcx+10h]
0x18004539a  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800453a1  mov     edx, 28h ; '('
0x1800453a6  call    WPP_SF_
0x1800453ab  xor     edx, edx; Val
0x1800453ad  lea     rcx, [rsp+280h+Src]; void *
0x1800453b2  mov     r8d, 1F8h; Size
0x1800453b8  call    memset_0
0x1800453bd  mov     r15d, [rbp+180h+arg_20]
0x1800453c4  mov     esi, 5B0Ch
0x1800453c9  mov     ecx, 1
0x1800453ce  mov     [rsp+280h+StringUuid], 0
0x1800453d7  cmp     r15d, ecx
0x1800453da  xorps   xmm0, xmm0
0x1800453dd  lea     rcx, [rsp+280h+Uuid]; Uuid
0x1800453e2  lea     eax, [rsi+2]
0x1800453e5  cmovnz  esi, eax
0x1800453e8  mov     eax, 5B0Fh
0x1800453ed  movups  xmmword ptr [rsp+280h+Uuid.Data1], xmm0
0x1800453f2  lea     r14d, [rax-2]
0x1800453f6  cmovnz  r14d, eax
0x1800453fa  mov     eax, 221h
0x1800453ff  mov     [rsp+280h+var_238], ax
0x180045404  call    cs:__imp_UuidCreate
0x18004540b  nop     dword ptr [rax+rax+00h]
0x180045410  lea     rdx, [rsp+280h+StringUuid]; StringUuid
0x180045415  lea     rcx, [rsp+280h+Uuid]; Uuid
0x18004541a  call    cs:__imp_UuidToStringW
0x180045421  nop     dword ptr [rax+rax+00h]
0x180045426  test    eax, eax
0x180045428  jz      short loc_180045434
0x18004542a  mov     ebx, 8000FFFFh
0x18004542f  jmp     loc_180045600
0x180045434  mov     rcx, [rsp+280h+StringUuid]
0x180045439  lea     rdx, [rsp+280h+var_230]
0x18004543e  call    cs:__imp_FwStringCopy
0x180045445  nop     dword ptr [rax+rax+00h]
0x18004544a  mov     ebx, eax
0x18004544c  test    eax, eax
0x18004544e  jns     short loc_18004547E
0x180045450  mov     rcx, cs:WPP_GLOBAL_Control
0x180045457  lea     rax, WPP_GLOBAL_Control
0x18004545e  cmp     rcx, rax
0x180045461  jz      loc_180045600
0x180045467  mov     edi, 1
0x18004546c  test    [rcx+1Ch], dil
0x180045470  jz      loc_180045600
0x180045476  lea     edx, [rdi+28h]
0x180045479  jmp     loc_1800455ED
0x18004547e  lea     r9, [rsp+280h+var_228]; unsigned __int16 **
0x180045483  mov     r8, rdi; unsigned __int16 *
0x180045486  mov     edx, esi; unsigned int
0x180045488  call    ?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z; FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)
0x18004548d  mov     ebx, eax
0x18004548f  test    eax, eax
0x180045491  jns     short loc_1800454C1
0x180045493  mov     rcx, cs:WPP_GLOBAL_Control
0x18004549a  lea     rax, WPP_GLOBAL_Control
0x1800454a1  cmp     rcx, rax
0x1800454a4  jz      loc_180045600
0x1800454aa  mov     edi, 1
0x1800454af  test    [rcx+1Ch], dil
0x1800454b3  jz      loc_180045600
0x1800454b9  lea     edx, [rdi+29h]
0x1800454bc  jmp     loc_1800455ED
0x1800454c1  lea     r9, [rsp+280h+var_220]; unsigned __int16 **
0x1800454c6  mov     r8, rdi; unsigned __int16 *
0x1800454c9  mov     edx, r14d; unsigned int
0x1800454cc  call    ?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z; FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)
0x1800454d1  mov     ebx, eax
0x1800454d3  test    eax, eax
0x1800454d5  jns     short loc_180045505
0x1800454d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800454de  lea     rax, WPP_GLOBAL_Control
0x1800454e5  cmp     rcx, rax
0x1800454e8  jz      loc_180045600
0x1800454ee  mov     edi, 1
0x1800454f3  test    [rcx+1Ch], dil
0x1800454f7  jz      loc_180045600
0x1800454fd  lea     edx, [rdi+2Ah]
0x180045500  jmp     loc_1800455ED
0x180045505  mov     eax, 100h
0x18004550a  mov     [rsp+280h+var_214], r15d
0x18004550f  lea     rdx, [rbp+180h+var_130]
0x180045513  mov     [rsp+280h+var_210], ax
0x180045518  mov     rcx, r13
0x18004551b  call    cs:__imp_FwStringCopy
0x180045522  nop     dword ptr [rax+rax+00h]
0x180045527  mov     ebx, eax
0x180045529  test    eax, eax
0x18004552b  jns     short loc_18004555B
0x18004552d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045534  lea     rax, WPP_GLOBAL_Control
0x18004553b  cmp     rcx, rax
0x18004553e  jz      loc_180045600
0x180045544  mov     edi, 1
0x180045549  test    [rcx+1Ch], dil
0x18004554d  jz      loc_180045600
0x180045553  lea     edx, [rdi+2Bh]
0x180045556  jmp     loc_1800455ED
0x18004555b  lea     rdx, [rbp+180h+var_128]
0x18004555f  mov     rcx, rdi
0x180045562  call    cs:__imp_FwStringCopy
0x180045569  nop     dword ptr [rax+rax+00h]
0x18004556e  mov     ebx, eax
0x180045570  test    eax, eax
0x180045572  jns     short loc_180045597
0x180045574  mov     rcx, cs:WPP_GLOBAL_Control
0x18004557b  lea     rax, WPP_GLOBAL_Control
0x180045582  cmp     rcx, rax
0x180045585  jz      short loc_180045600
0x180045587  mov     edi, 1
0x18004558c  test    [rcx+1Ch], dil
0x180045590  jz      short loc_180045600
0x180045592  lea     edx, [rdi+2Ch]
0x180045595  jmp     short loc_1800455ED
0x180045597  mov     edi, 1
0x18004559c  mov     [rbp+180h+var_120], 2
0x1800455a3  lea     rdx, [rsp+280h+Src]; Src
0x1800455a8  mov     [rbp+180h+var_11C], di
0x1800455ac  mov     rcx, r12; __int64
0x1800455af  mov     [rsp+280h+var_218], 7FFFFFFFh
0x1800455b7  call    FWAddFirewallRule
0x1800455bc  mov     ebx, eax
0x1800455be  test    eax, eax
0x1800455c0  jle     short loc_1800455CB
0x1800455c2  movzx   ebx, ax
0x1800455c5  or      ebx, 80070000h
0x1800455cb  test    ebx, ebx
0x1800455cd  jns     short loc_180045600
0x1800455cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800455d6  lea     rax, WPP_GLOBAL_Control
0x1800455dd  cmp     rcx, rax
0x1800455e0  jz      short loc_180045600
0x1800455e2  test    [rcx+1Ch], dil
0x1800455e6  jz      short loc_180045600
0x1800455e8  mov     edx, 2Eh ; '.'
0x1800455ed  mov     rcx, [rcx+10h]
0x1800455f1  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800455f8  mov     r9d, ebx
0x1800455fb  call    WPP_SF_d
0x180045600  cmp     [rsp+280h+StringUuid], 0
0x180045606  jz      short loc_180045619
0x180045608  lea     rcx, [rsp+280h+StringUuid]; String
0x18004560d  call    cs:__imp_RpcStringFreeW
0x180045614  nop     dword ptr [rax+rax+00h]
0x180045619  lea     rcx, [rsp+280h+Src]
0x18004561e  call    cs:__imp_FwEmptyWFRule
0x180045625  nop     dword ptr [rax+rax+00h]
0x18004562a  mov     eax, ebx
0x18004562c  mov     rcx, [rbp+180h+var_40]
0x180045633  xor     rcx, rsp; StackCookie
0x180045636  call    __security_check_cookie
0x18004563b  mov     rbx, [rsp+280h+arg_0]
0x180045643  add     rsp, 250h
0x18004564a  pop     r15
0x18004564c  pop     r14
0x18004564e  pop     r13
0x180045650  pop     r12
0x180045652  pop     rdi
0x180045653  pop     rsi
0x180045654  pop     rbp
0x180045655  retn
```
