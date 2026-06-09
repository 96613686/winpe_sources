# CreateDefaultRemoteAdminRule(uint,uint,ushort const *,ushort const *,_tag_FW_PORTS *,_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)

- ea: `0x180020d60`
- end: `0x1800210a0`
- name: `?CreateDefaultRemoteAdminRule@@YAJIIPEBG0PEAU_tag_FW_PORTS@@PEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, __int64 *, __int64, __int64, void **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001e4b0`

## callees

- `0x1800042c4`
- `0x180006000`
- `0x180006f50`
- `0x18001f650`
- `0x18001ffd4`
- `0x180020d60`
- `0x180024148`
- `0x180039bb8`

## import_xrefs

- `fwbase!FwAlloc` at `0x180020e4a`
- `fwbase!FwAlloc` at `0x180020e4a`
- `fwbase!FwStringCopy` at `0x180020f7d`
- `fwbase!FwStringCopy` at `0x180020fbe`
- `fwbase!FwStringCopy` at `0x180020fff`
- `fwbase!FwStringCopy` at `0x180020f7d`
- `fwbase!FwStringCopy` at `0x180020fbe`
- `fwbase!FwStringCopy` at `0x180020fff`
- `fwbase!FwBuildIndirectString` at `0x180020ef8`
- `fwbase!FwBuildIndirectString` at `0x180020f39`
- `fwbase!FwBuildIndirectString` at `0x180020ef8`
- `fwbase!FwBuildIndirectString` at `0x180020f39`
- `fwbase!FwSizeTMultiply` at `0x180020e0e`
- `fwbase!FwSizeTMultiply` at `0x180020e0e`

## string_xrefs

- `0x180020ff1`: `@FirewallAPI.dll,-29752`

## pseudocode

```c
__int64 __fastcall CreateDefaultRemoteAdminRule(
        unsigned int a1,
        unsigned int a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        void **a6,
        unsigned int a7)
{
  int DefaultRule; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // ebx
  LPCOLESTR v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 *v20; // rax
  __int64 v22; // [rsp+38h] [rbp-60h] BYREF

  *a6 = 0;
  DefaultRule = CreateDefaultRule(a6, a7);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 147;
LABEL_35:
        v18 = (unsigned int)DefaultRule;
        goto LABEL_36;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  *((_WORD *)*a6 + 28) = *(_WORD *)a5;
  v17 = *(unsigned int *)(a5 + 8);
  if ( (_DWORD)v17 )
  {
    v22 = 0;
    DefaultRule = FwSizeTMultiply((unsigned int)v17, 4, &v22);
    v14 = DefaultRule;
    if ( DefaultRule < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v16 = 148;
          goto LABEL_35;
        }
LABEL_37:
        if ( v15 != (LPCOLESTR)&WPP_GLOBAL_Control && (v15[14] & 1) != 0 )
        {
          v19 = *((_QWORD *)v15 + 2);
          v20 = &qword_18003DA20;
          if ( a3 )
            v20 = a3;
          WPP_SF_dSd(v19, v12, v13, a1, (__int64)v20, v14);
        }
      }
LABEL_42:
      FwFreeWFRule(*a6);
      *a6 = 0;
      return v14;
    }
    *((_QWORD *)*a6 + 9) = FwAlloc(v22);
    if ( !*((_QWORD *)*a6 + 9) )
    {
      v14 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v16 = 149;
          v18 = 2147942414LL;
LABEL_36:
          WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v18);
          v15 = WPP_GLOBAL_Control;
          goto LABEL_37;
        }
        goto LABEL_37;
      }
      goto LABEL_42;
    }
    *((_DWORD *)*a6 + 16) = v17;
    memset_0(*((void **)*a6 + 9), 0, 4 * v17);
    memcpy_0(*((void **)*a6 + 9), *(const void **)(a5 + 16), 4 * v17);
  }
  *((_DWORD *)*a6 + 72) = 3;
  *((_WORD *)*a6 + 146) = 0;
  *((_DWORD *)*a6 + 11) = 1;
  *((_WORD *)*a6 + 24) = 6;
  DefaultRule = FwBuildIndirectString(a1, (char *)*a6 + 24);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 150;
        goto LABEL_35;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  DefaultRule = FwBuildIndirectString(a2, (char *)*a6 + 32);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 151;
        goto LABEL_35;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  DefaultRule = FwStringCopy(a3, (char *)*a6 + 272);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 152;
        goto LABEL_35;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  DefaultRule = FwStringCopy(a4, (char *)*a6 + 280);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 153;
        goto LABEL_35;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  DefaultRule = FwStringCopy(L"@FirewallAPI.dll,-29752", (char *)*a6 + 312);
  v14 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 154;
        goto LABEL_35;
      }
      goto LABEL_37;
    }
    goto LABEL_42;
  }
  return v14;
}

```

## disassembly

```asm
0x180020d60  push    rbx
0x180020d62  push    rbp
0x180020d63  push    rsi
0x180020d64  push    rdi
0x180020d65  push    r12
0x180020d67  push    r13
0x180020d69  push    r14
0x180020d6b  push    r15
0x180020d6d  sub     rsp, 58h
0x180020d71  mov     rax, cs:__security_cookie
0x180020d78  xor     rax, rsp
0x180020d7b  mov     [rsp+98h+var_58], rax
0x180020d80  mov     rsi, [rsp+98h+arg_28]
0x180020d88  mov     r15d, edx
0x180020d8b  mov     edx, [rsp+98h+arg_30]
0x180020d92  mov     ebp, ecx
0x180020d94  mov     r14, [rsp+98h+arg_20]
0x180020d9c  mov     rcx, rsi
0x180020d9f  mov     r12, r9
0x180020da2  mov     r13, r8
0x180020da5  mov     qword ptr [rsi], 0
0x180020dac  call    ?CreateDefaultRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180020db1  mov     ebx, eax
0x180020db3  test    eax, eax
0x180020db5  jns     short loc_180020DE2
0x180020db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dbe  lea     rdi, WPP_GLOBAL_Control
0x180020dc5  cmp     rcx, rdi
0x180020dc8  jz      loc_180021071
0x180020dce  test    byte ptr [rcx+1Ch], 1
0x180020dd2  jz      loc_180021043
0x180020dd8  mov     edx, 93h
0x180020ddd  jmp     loc_180021029
0x180020de2  mov     rcx, [rsi]
0x180020de5  movzx   eax, word ptr [r14]
0x180020de9  mov     [rcx+38h], ax
0x180020ded  mov     edi, [r14+8]
0x180020df1  test    edi, edi
0x180020df3  jz      loc_180020EC3
0x180020df9  lea     r8, [rsp+98h+var_60]
0x180020dfe  mov     [rsp+98h+var_60], 0
0x180020e07  mov     edx, 4
0x180020e0c  mov     ecx, edi
0x180020e0e  call    cs:__imp_FwSizeTMultiply
0x180020e14  mov     ebx, eax
0x180020e16  test    eax, eax
0x180020e18  jns     short loc_180020E45
0x180020e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e21  lea     rdi, WPP_GLOBAL_Control
0x180020e28  cmp     rcx, rdi
0x180020e2b  jz      loc_180021071
0x180020e31  test    byte ptr [rcx+1Ch], 1
0x180020e35  jz      loc_180021043
0x180020e3b  mov     edx, 94h
0x180020e40  jmp     loc_180021029
0x180020e45  mov     rcx, [rsp+98h+var_60]
0x180020e4a  call    cs:__imp_FwAlloc
0x180020e50  mov     rcx, [rsi]
0x180020e53  mov     [rcx+48h], rax
0x180020e57  mov     rax, [rsi]
0x180020e5a  cmp     qword ptr [rax+48h], 0
0x180020e5f  jnz     short loc_180020E94
0x180020e61  mov     ebx, 8007000Eh
0x180020e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e6d  lea     rdi, WPP_GLOBAL_Control
0x180020e74  cmp     rcx, rdi
0x180020e77  jz      loc_180021071
0x180020e7d  test    byte ptr [rcx+1Ch], 1
0x180020e81  jz      loc_180021043
0x180020e87  mov     edx, 95h
0x180020e8c  mov     r9d, ebx
0x180020e8f  jmp     loc_18002102C
0x180020e94  mov     [rax+40h], edi
0x180020e97  lea     rbx, ds:0[rdi*4]
0x180020e9f  mov     rcx, [rsi]
0x180020ea2  mov     r8, rbx; Size
0x180020ea5  xor     edx, edx; Val
0x180020ea7  mov     rcx, [rcx+48h]; void *
0x180020eab  call    memset_0
0x180020eb0  mov     rcx, [rsi]
0x180020eb3  mov     r8, rbx; Size
0x180020eb6  mov     rdx, [r14+10h]; Src
0x180020eba  mov     rcx, [rcx+48h]; void *
0x180020ebe  call    memcpy_0
0x180020ec3  mov     rax, [rsi]
0x180020ec6  mov     dword ptr [rax+120h], 3
0x180020ed0  xor     eax, eax
0x180020ed2  mov     rcx, [rsi]
0x180020ed5  mov     [rcx+124h], ax
0x180020edc  mov     ecx, ebp
0x180020ede  mov     rax, [rsi]
0x180020ee1  mov     dword ptr [rax+2Ch], 1
0x180020ee8  mov     rax, [rsi]
0x180020eeb  mov     word ptr [rax+30h], 6
0x180020ef1  mov     rdx, [rsi]
0x180020ef4  add     rdx, 18h
0x180020ef8  call    cs:__imp_FwBuildIndirectString
0x180020efe  mov     ebx, eax
0x180020f00  test    eax, eax
0x180020f02  jns     short loc_180020F2F
0x180020f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f0b  lea     rdi, WPP_GLOBAL_Control
0x180020f12  cmp     rcx, rdi
0x180020f15  jz      loc_180021071
0x180020f1b  test    byte ptr [rcx+1Ch], 1
0x180020f1f  jz      loc_180021043
0x180020f25  mov     edx, 96h
0x180020f2a  jmp     loc_180021029
0x180020f2f  mov     rdx, [rsi]
0x180020f32  mov     ecx, r15d
0x180020f35  add     rdx, 20h ; ' '
0x180020f39  call    cs:__imp_FwBuildIndirectString
0x180020f3f  mov     ebx, eax
0x180020f41  test    eax, eax
0x180020f43  jns     short loc_180020F70
0x180020f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f4c  lea     rdi, WPP_GLOBAL_Control
0x180020f53  cmp     rcx, rdi
0x180020f56  jz      loc_180021071
0x180020f5c  test    byte ptr [rcx+1Ch], 1
0x180020f60  jz      loc_180021043
0x180020f66  mov     edx, 97h
0x180020f6b  jmp     loc_180021029
0x180020f70  mov     rdx, [rsi]
0x180020f73  mov     rcx, r13
0x180020f76  add     rdx, 110h
0x180020f7d  call    cs:__imp_FwStringCopy
0x180020f83  mov     ebx, eax
0x180020f85  test    eax, eax
0x180020f87  jns     short loc_180020FB1
0x180020f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f90  lea     rdi, WPP_GLOBAL_Control
0x180020f97  cmp     rcx, rdi
0x180020f9a  jz      loc_180021071
0x180020fa0  test    byte ptr [rcx+1Ch], 1
0x180020fa4  jz      loc_180021043
0x180020faa  mov     edx, 98h
0x180020faf  jmp     short loc_180021029
0x180020fb1  mov     rdx, [rsi]
0x180020fb4  mov     rcx, r12
0x180020fb7  add     rdx, 118h
0x180020fbe  call    cs:__imp_FwStringCopy
0x180020fc4  mov     ebx, eax
0x180020fc6  test    eax, eax
0x180020fc8  jns     short loc_180020FEE
0x180020fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fd1  lea     rdi, WPP_GLOBAL_Control
0x180020fd8  cmp     rcx, rdi
0x180020fdb  jz      loc_180021071
0x180020fe1  test    byte ptr [rcx+1Ch], 1
0x180020fe5  jz      short loc_180021043
0x180020fe7  mov     edx, 99h
0x180020fec  jmp     short loc_180021029
0x180020fee  mov     rdx, [rsi]
0x180020ff1  lea     rcx, aFirewallapiDll_1; "@FirewallAPI.dll,-29752"
0x180020ff8  add     rdx, 138h
0x180020fff  call    cs:__imp_FwStringCopy
0x180021005  mov     ebx, eax
0x180021007  test    eax, eax
0x180021009  jns     short loc_180021080
0x18002100b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021012  lea     rdi, WPP_GLOBAL_Control
0x180021019  cmp     rcx, rdi
0x18002101c  jz      short loc_180021071
0x18002101e  test    byte ptr [rcx+1Ch], 1
0x180021022  jz      short loc_180021043
0x180021024  mov     edx, 9Ah
0x180021029  mov     r9d, eax
0x18002102c  mov     rcx, [rcx+10h]
0x180021030  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180021037  call    WPP_SF_d
0x18002103c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021043  cmp     rcx, rdi
0x180021046  jz      short loc_180021071
0x180021048  test    byte ptr [rcx+1Ch], 1
0x18002104c  jz      short loc_180021071
0x18002104e  mov     rcx, [rcx+10h]
0x180021052  lea     rax, qword_18003DA20
0x180021059  test    r13, r13
0x18002105c  mov     [rsp+98h+var_70], ebx
0x180021060  mov     r9d, ebp
0x180021063  cmovnz  rax, r13
0x180021067  mov     [rsp+98h+var_78], rax
0x18002106c  call    WPP_SF_dSd
0x180021071  mov     rcx, [rsi]; void *
0x180021074  call    FwFreeWFRule
0x180021079  mov     qword ptr [rsi], 0
0x180021080  mov     eax, ebx
0x180021082  mov     rcx, [rsp+98h+var_58]
0x180021087  xor     rcx, rsp; StackCookie
0x18002108a  call    __security_check_cookie
0x18002108f  add     rsp, 58h
0x180021093  pop     r15
0x180021095  pop     r14
0x180021097  pop     r13
0x180021099  pop     r12
0x18002109b  pop     rdi
0x18002109c  pop     rsi
0x18002109d  pop     rbp
0x18002109e  pop     rbx
0x18002109f  retn
```
