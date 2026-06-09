# FwOpenOfflinePolicyStore

- ea: `0x18002fcd0`
- end: `0x180030068`
- name: `FwOpenOfflinePolicyStore`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180002ef0`
- `0x180003b94`
- `0x1800042c4`
- `0x180019e0c`
- `0x18001f650`
- `0x18002f540`
- `0x18002fcd0`
- `0x180039b94`

## import_xrefs

- `fwbase!FwAlloc` at `0x18002fdb0`
- `fwbase!FwAlloc` at `0x18002fdb0`
- `fwbase!FwStringBuild` at `0x18002ff88`
- `fwbase!FwStringBuild` at `0x18002ff88`
- `fwbase!FwRegCreateKey` at `0x18002ffd1`
- `fwbase!FwRegCreateKey` at `0x18002ffd1`
- `fwbase!FwRegQueryDWord` at `0x18002fed0`
- `fwbase!FwRegQueryDWord` at `0x18002fed0`

## pseudocode

```c
__int64 __fastcall FwOpenOfflinePolicyStore(__int64 a1, int a2, int a3, __int64 *a4)
{
  __int64 v5; // rbx
  LPCOLESTR v7; // rcx
  __int64 v8; // rsi
  int Key; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdi
  __int64 v13; // r12
  LPCOLESTR v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  _OWORD *v17; // rcx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  int v22; // [rsp+38h] [rbp-28h] BYREF
  int v23; // [rsp+3Ch] [rbp-24h] BYREF
  int v24; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 v25[4]; // [rsp+48h] [rbp-18h] BYREF

  v5 = a2;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 368, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v23 = 0;
  *(_QWORD *)v25 = 0x3100300030LL;
  v24 = 4;
  v22 = 0;
  if ( (unsigned int)(a3 - 1) <= 1 )
  {
    v8 = 2;
    if ( (_DWORD)v5 != 2 && (_DWORD)v5 != 7 )
    {
      Key = -2147024809;
      if ( v7 == (LPCOLESTR)&WPP_GLOBAL_Control || (v7[14] & 1) == 0 )
        return (unsigned int)Key;
      v10 = 369;
      v11 = 2147942487LL;
      goto LABEL_10;
    }
    v12 = FwAlloc(264);
    if ( !v12 )
    {
      Key = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)Key;
      v10 = 370;
      v11 = 2147942414LL;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v7 + 2), v10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v11);
      return (unsigned int)Key;
    }
    v13 = 33 * v5;
    if ( !wcsncmp_0((const wchar_t *)qword_18004D8B0[33 * v5], L"SYSTEM\\CurrentControlSet", 0x18u) )
    {
      v17 = (_OWORD *)v12;
      v18 = (_OWORD *)((char *)&PolicyStore + v13 * 8);
      do
      {
        *v17 = *v18;
        v17[1] = v18[1];
        v17[2] = v18[2];
        v17[3] = v18[3];
        v17[4] = v18[4];
        v17[5] = v18[5];
        v17[6] = v18[6];
        v19 = v18[7];
        v18 += 8;
        v17[7] = v19;
        v17 += 8;
        --v8;
      }
      while ( v8 );
      *(_QWORD *)v17 = *(_QWORD *)v18;
      *(_DWORD *)(v12 + 12) = a3;
      *(_QWORD *)(v12 + 16) = 0;
      Key = FwRegQueryDWord(a1, L"Select", L"Current", &v22, &v23);
      if ( Key >= 0 )
      {
        if ( !v23 )
          v22 = 1;
        Key = StringCchPrintfW(v25, 4u, L"%03d");
        if ( Key >= 0 )
        {
          Key = FwStringBuild(v12 + 16, L"ControlSet", v25, qword_18004D8B0[v13] + 48);
          if ( Key >= 0 )
          {
            Key = FwRegCreateKey(
                    a1,
                    *(_QWORD *)(v12 + 16),
                    *((unsigned int *)&FWPolicyAcessRightMap + *(int *)(v12 + 12)),
                    v12 + 40);
            if ( Key >= 0 )
            {
              Key = FwGetGlobalConfigFromLocalTempStore(*(_QWORD *)(v12 + 40), 10, v12, &v24);
              if ( Key < 0 )
              {
                *(_DWORD *)v12 = 0;
                Key = 0;
              }
              *a4 = v12;
              return (unsigned int)Key;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_41;
            v15 = 375;
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_41;
            v15 = 374;
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_41;
          v15 = 373;
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_41;
        v15 = 372;
      }
      v16 = (unsigned int)Key;
    }
    else
    {
      Key = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_41;
      v15 = 371;
      v16 = 2147942487LL;
    }
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v16);
LABEL_41:
    FwClosePolicyStore((struct _tag_WF_POLICY_STORE *)v12);
    return (unsigned int)Key;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002fcd0  mov     [rsp-38h+arg_10], rbx
0x18002fcd5  push    rbp
0x18002fcd6  push    rsi
0x18002fcd7  push    rdi
0x18002fcd8  push    r12
0x18002fcda  push    r13
0x18002fcdc  push    r14
0x18002fcde  push    r15
0x18002fce0  mov     rbp, rsp
0x18002fce3  sub     rsp, 60h
0x18002fce7  mov     rax, cs:__security_cookie
0x18002fcee  xor     rax, rsp
0x18002fcf1  mov     [rbp+var_10], rax
0x18002fcf5  mov     r13, r9
0x18002fcf8  movsxd  rbx, edx
0x18002fcfb  mov     r15d, r8d
0x18002fcfe  mov     [rbp+var_30], rcx
0x18002fd02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd09  lea     r14, WPP_GLOBAL_Control
0x18002fd10  lea     r12, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002fd17  cmp     rcx, r14
0x18002fd1a  jz      short loc_18002FD3A
0x18002fd1c  test    byte ptr [rcx+1Ch], 8
0x18002fd20  jz      short loc_18002FD3A
0x18002fd22  mov     rcx, [rcx+10h]
0x18002fd26  mov     edx, 170h
0x18002fd2b  mov     r8, r12
0x18002fd2e  call    WPP_SF_
0x18002fd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd3a  mov     rax, 3100300030h
0x18002fd44  mov     [rbp+var_24], 0
0x18002fd4b  mov     qword ptr [rbp+var_18], rax
0x18002fd4f  lea     eax, [r15-1]
0x18002fd53  mov     [rbp+var_20], 4
0x18002fd5a  mov     [rbp+var_28], 0
0x18002fd61  cmp     eax, 1
0x18002fd64  ja      loc_18003003F
0x18002fd6a  mov     esi, 2
0x18002fd6f  cmp     ebx, esi
0x18002fd71  jz      short loc_18002FDAB
0x18002fd73  cmp     ebx, 7
0x18002fd76  jz      short loc_18002FDAB
0x18002fd78  mov     eax, 80070057h
0x18002fd7d  mov     ebx, eax
0x18002fd7f  cmp     rcx, r14
0x18002fd82  jz      loc_18003003B
0x18002fd88  test    byte ptr [rcx+1Ch], 1
0x18002fd8c  jz      loc_18003003B
0x18002fd92  mov     edx, 171h
0x18002fd97  mov     r9d, eax
0x18002fd9a  mov     rcx, [rcx+10h]
0x18002fd9e  mov     r8, r12
0x18002fda1  call    WPP_SF_d
0x18002fda6  jmp     loc_18003003B
0x18002fdab  mov     ecx, 108h
0x18002fdb0  call    cs:__imp_FwAlloc
0x18002fdb6  mov     rdi, rax
0x18002fdb9  test    rax, rax
0x18002fdbc  jnz     short loc_18002FDE7
0x18002fdbe  mov     ebx, 8007000Eh
0x18002fdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdca  cmp     rcx, r14
0x18002fdcd  jz      loc_18003003B
0x18002fdd3  test    byte ptr [rcx+1Ch], 1
0x18002fdd7  jz      loc_18003003B
0x18002fddd  mov     edx, 172h
0x18002fde2  mov     r9d, ebx
0x18002fde5  jmp     short loc_18002FD9A
0x18002fde7  imul    r12, rbx, 108h
0x18002fdee  lea     rbx, __ImageBase
0x18002fdf5  mov     r8d, 18h; MaxCount
0x18002fdfb  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet"
0x18002fe02  mov     rcx, [r12+rbx+4D8B0h]; String1
0x18002fe0a  call    wcsncmp_0
0x18002fe0f  test    eax, eax
0x18002fe11  jz      short loc_18002FE41
0x18002fe13  mov     eax, 80070057h
0x18002fe18  mov     ebx, eax
0x18002fe1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe21  cmp     rcx, r14
0x18002fe24  jz      loc_18003000E
0x18002fe2a  test    byte ptr [rcx+1Ch], 1
0x18002fe2e  jz      loc_18003000E
0x18002fe34  mov     edx, 173h
0x18002fe39  mov     r9d, eax
0x18002fe3c  jmp     loc_18002FFFE
0x18002fe41  lea     rax, rva ?PolicyStore@@3PAU_tag_WF_POLICY_STORE@@A[rbx]; _tag_WF_POLICY_STORE near * PolicyStore ...
0x18002fe48  mov     rcx, rdi
0x18002fe4b  add     rax, r12
0x18002fe4e  mov     edx, 80h
0x18002fe53  movups  xmm0, xmmword ptr [rax]
0x18002fe56  movups  xmmword ptr [rcx], xmm0
0x18002fe59  movups  xmm1, xmmword ptr [rax+10h]
0x18002fe5d  movups  xmmword ptr [rcx+10h], xmm1
0x18002fe61  movups  xmm0, xmmword ptr [rax+20h]
0x18002fe65  movups  xmmword ptr [rcx+20h], xmm0
0x18002fe69  movups  xmm1, xmmword ptr [rax+30h]
0x18002fe6d  movups  xmmword ptr [rcx+30h], xmm1
0x18002fe71  movups  xmm0, xmmword ptr [rax+40h]
0x18002fe75  movups  xmmword ptr [rcx+40h], xmm0
0x18002fe79  movups  xmm1, xmmword ptr [rax+50h]
0x18002fe7d  movups  xmmword ptr [rcx+50h], xmm1
0x18002fe81  movups  xmm0, xmmword ptr [rax+60h]
0x18002fe85  movups  xmmword ptr [rcx+60h], xmm0
0x18002fe89  movups  xmm1, xmmword ptr [rax+70h]
0x18002fe8d  add     rax, rdx
0x18002fe90  movups  xmmword ptr [rcx+70h], xmm1
0x18002fe94  add     rcx, rdx
0x18002fe97  sub     rsi, 1
0x18002fe9b  jnz     short loc_18002FE53
0x18002fe9d  mov     rax, [rax]
0x18002fea0  lea     r14, [rdi+10h]
0x18002fea4  mov     [rcx], rax
0x18002fea7  lea     r9, [rbp+var_28]
0x18002feab  mov     [rdi+0Ch], r15d
0x18002feaf  lea     rax, [rbp+var_24]
0x18002feb3  mov     r15, [rbp+var_30]
0x18002feb7  lea     r8, aCurrent; "Current"
0x18002febe  mov     rcx, r15
0x18002fec1  mov     [r14], rsi
0x18002fec4  lea     rdx, aSelect; "Select"
0x18002fecb  mov     [rsp+60h+var_40], rax
0x18002fed0  call    cs:__imp_FwRegQueryDWord
0x18002fed6  mov     ebx, eax
0x18002fed8  test    eax, eax
0x18002feda  jns     short loc_18002FF07
0x18002fedc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fee3  lea     rax, WPP_GLOBAL_Control
0x18002feea  cmp     rcx, rax
0x18002feed  jz      loc_18003000E
0x18002fef3  test    byte ptr [rcx+1Ch], 1
0x18002fef7  jz      loc_18003000E
0x18002fefd  mov     edx, 174h
0x18002ff02  jmp     loc_18002FFFB
0x18002ff07  cmp     [rbp+var_24], esi
0x18002ff0a  jnz     short loc_18002FF18
0x18002ff0c  mov     r9d, 1
0x18002ff12  mov     [rbp+var_28], r9d
0x18002ff16  jmp     short loc_18002FF1C
0x18002ff18  mov     r9d, [rbp+var_28]
0x18002ff1c  lea     r8, a03d; "%03d"
0x18002ff23  mov     edx, 4; unsigned __int64
0x18002ff28  lea     rcx, [rbp+var_18]; unsigned __int16 *
0x18002ff2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ff31  mov     ebx, eax
0x18002ff33  test    eax, eax
0x18002ff35  jns     short loc_18002FF62
0x18002ff37  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff3e  lea     rax, WPP_GLOBAL_Control
0x18002ff45  cmp     rcx, rax
0x18002ff48  jz      loc_18003000E
0x18002ff4e  test    byte ptr [rcx+1Ch], 1
0x18002ff52  jz      loc_18003000E
0x18002ff58  mov     edx, 175h
0x18002ff5d  jmp     loc_18002FFFB
0x18002ff62  lea     r9, __ImageBase
0x18002ff69  mov     [rsp+60h+var_40], rsi
0x18002ff6e  mov     r9, [r12+r9+4D8B0h]
0x18002ff76  lea     r8, [rbp+var_18]
0x18002ff7a  add     r9, 30h ; '0'
0x18002ff7e  lea     rdx, aControlset; "ControlSet"
0x18002ff85  mov     rcx, r14
0x18002ff88  call    cs:__imp_FwStringBuild
0x18002ff8e  mov     ebx, eax
0x18002ff90  test    eax, eax
0x18002ff92  jns     short loc_18002FFB4
0x18002ff94  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff9b  lea     rax, WPP_GLOBAL_Control
0x18002ffa2  cmp     rcx, rax
0x18002ffa5  jz      short loc_18003000E
0x18002ffa7  test    byte ptr [rcx+1Ch], 1
0x18002ffab  jz      short loc_18003000E
0x18002ffad  mov     edx, 176h
0x18002ffb2  jmp     short loc_18002FFFB
0x18002ffb4  movsxd  r8, dword ptr [rdi+0Ch]
0x18002ffb8  lea     rax, __ImageBase
0x18002ffbf  mov     rdx, [r14]
0x18002ffc2  lea     r9, [rdi+28h]
0x18002ffc6  mov     rcx, r15
0x18002ffc9  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rax+r8*4]; ulong near * FWPolicyAcessRightMap ...
0x18002ffd1  call    cs:__imp_FwRegCreateKey
0x18002ffd7  mov     ebx, eax
0x18002ffd9  test    eax, eax
0x18002ffdb  jns     short loc_180030018
0x18002ffdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffe4  lea     rax, WPP_GLOBAL_Control
0x18002ffeb  cmp     rcx, rax
0x18002ffee  jz      short loc_18003000E
0x18002fff0  test    byte ptr [rcx+1Ch], 1
0x18002fff4  jz      short loc_18003000E
0x18002fff6  mov     edx, 177h
0x18002fffb  mov     r9d, ebx
0x18002fffe  mov     rcx, [rcx+10h]
0x180030002  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180030009  call    WPP_SF_d
0x18003000e  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x180030011  call    FwClosePolicyStore
0x180030016  jmp     short loc_18003003B
0x180030018  mov     rcx, [rdi+28h]
0x18003001c  lea     r9, [rbp+var_20]
0x180030020  mov     r8, rdi
0x180030023  mov     edx, 0Ah
0x180030028  call    FwGetGlobalConfigFromLocalTempStore
0x18003002d  mov     ebx, eax
0x18003002f  test    eax, eax
0x180030031  jns     short loc_180030037
0x180030033  mov     [rdi], esi
0x180030035  xor     ebx, ebx
0x180030037  mov     [r13+0], rdi
0x18003003b  mov     eax, ebx
0x18003003d  jmp     short loc_180030044
0x18003003f  mov     eax, 80070057h
0x180030044  mov     rcx, [rbp+var_10]
0x180030048  xor     rcx, rsp; StackCookie
0x18003004b  call    __security_check_cookie
0x180030050  mov     rbx, [rsp+60h+arg_10]
0x180030058  add     rsp, 60h
0x18003005c  pop     r15
0x18003005e  pop     r14
0x180030060  pop     r13
0x180030062  pop     r12
0x180030064  pop     rdi
0x180030065  pop     rsi
0x180030066  pop     rbp
0x180030067  retn
```
