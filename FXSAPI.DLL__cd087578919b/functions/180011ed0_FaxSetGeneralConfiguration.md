# FaxSetGeneralConfiguration

- ea: `0x180011ed0`
- end: `0x18001224b`
- name: `FaxSetGeneralConfiguration`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180011ed0`
- `0x180014314`
- `0x18002bab8`
- `0x18002bb58`
- `0x180033e20`
- `0x1800348dc`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180012176`
- `RPCRT4!NdrClientCall3` at `0x180012176`
- `KERNEL32!SetLastError` at `0x180011f52`
- `KERNEL32!SetLastError` at `0x180011fa8`
- `KERNEL32!SetLastError` at `0x180012021`
- `KERNEL32!SetLastError` at `0x1800121fa`
- `KERNEL32!SetLastError` at `0x180011f52`
- `KERNEL32!SetLastError` at `0x180011fa8`
- `KERNEL32!SetLastError` at `0x180012021`
- `KERNEL32!SetLastError` at `0x1800121fa`

## pseudocode

```c
__int64 __fastcall FaxSetGeneralConfiguration(__int64 a1, unsigned int a2, _DWORD *a3)
{
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ecx
  unsigned int v10; // r13d
  unsigned __int8 *v11; // rsi
  int Pointer; // ebx
  _QWORD *v13; // rax
  CLIENT_CALL_RETURN v14; // rax
  __int64 v16; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytes; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 *v18; // [rsp+98h] [rbp+20h]

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 348, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 349;
LABEL_45:
    WPP_SF_(v7[2], v8, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( a2 )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 350, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, a2);
    }
    return 0;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 351;
    goto LABEL_45;
  }
  if ( *a3 == 88 )
  {
    dwBytes = 88;
    SerializeGeneralConfig(a3, 0, 0, 0, 0, &dwBytes);
    v10 = dwBytes;
    v11 = (unsigned __int8 *)pMemAlloc((unsigned int)dwBytes);
    v18 = v11;
    if ( v11 )
    {
      dwBytes = 88;
      SerializeGeneralConfig(a3, 0, v11, v10, v11, &dwBytes);
      if ( (unsigned int)MarshallDownStructure(v11, (struct _FieldInfo *)&fax_general_config_fields, 0x58u) )
      {
        v13 = *(_QWORD **)(a1 + 32);
        dwBytes = 0;
        LODWORD(v16) = 0;
        v14.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x62u, 0, *v13, v16, v11, v10).Pointer;
        Pointer = (int)v14.Pointer;
        dwBytes = v14.Simple;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 354, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
        }
        Pointer = 1359;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 353, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v10);
      }
      Pointer = 8;
    }
    pMemFree(v11);
    if ( !Pointer )
      return 1;
    v9 = Pointer;
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_dd(v6[2], 352, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v9 = 13;
  }
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x180011ed0  mov     [rsp+arg_8], rbx
0x180011ed5  push    rsi
0x180011ed6  push    r12
0x180011ed8  push    r13
0x180011eda  push    r14
0x180011edc  push    r15
0x180011ede  sub     rsp, 50h
0x180011ee2  mov     r12, r8
0x180011ee5  mov     r15d, edx
0x180011ee8  mov     r14, rcx
0x180011eeb  lea     rsi, WPP_GLOBAL_Control
0x180011ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ef9  mov     ebx, 1000h
0x180011efe  cmp     rcx, rsi
0x180011f01  jz      short loc_180011F2A
0x180011f03  test    [rcx+1Ch], ebx
0x180011f06  jz      short loc_180011F2A
0x180011f08  cmp     byte ptr [rcx+19h], 5
0x180011f0c  jb      short loc_180011F2A
0x180011f0e  mov     edx, 15Ch
0x180011f13  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011f1a  mov     rcx, [rcx+10h]
0x180011f1e  call    WPP_SF_
0x180011f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f2a  test    r14, r14
0x180011f2d  jz      loc_1800121F5
0x180011f33  cmp     dword ptr [r14], 0
0x180011f37  jz      loc_1800121F5
0x180011f3d  cmp     dword ptr [r14+10h], 0
0x180011f42  jnz     loc_1800121F5
0x180011f48  test    r15d, r15d
0x180011f4b  jz      short loc_180011F9E
0x180011f4d  mov     ecx, 57h ; 'W'; dwErrCode
0x180011f52  call    cs:__imp_SetLastError
0x180011f59  nop     dword ptr [rax+rax+00h]
0x180011f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f65  cmp     rcx, rsi
0x180011f68  jz      loc_180012232
0x180011f6e  test    [rcx+1Ch], ebx
0x180011f71  jz      loc_180012232
0x180011f77  cmp     byte ptr [rcx+19h], 2
0x180011f7b  jb      loc_180012232
0x180011f81  mov     edx, 15Eh
0x180011f86  mov     r9d, r15d
0x180011f89  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011f90  mov     rcx, [rcx+10h]
0x180011f94  call    WPP_SF_d
0x180011f99  jmp     loc_180012232
0x180011f9e  test    r12, r12
0x180011fa1  jnz     short loc_180011FE1
0x180011fa3  lea     ecx, [r12+57h]; dwErrCode
0x180011fa8  call    cs:__imp_SetLastError
0x180011faf  nop     dword ptr [rax+rax+00h]
0x180011fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fbb  cmp     rcx, rsi
0x180011fbe  jz      loc_180012232
0x180011fc4  test    [rcx+1Ch], ebx
0x180011fc7  jz      loc_180012232
0x180011fcd  cmp     byte ptr [rcx+19h], 2
0x180011fd1  jb      loc_180012232
0x180011fd7  mov     edx, 15Fh
0x180011fdc  jmp     loc_180012222
0x180011fe1  mov     eax, [r12]
0x180011fe5  mov     r8d, 58h ; 'X'
0x180011feb  cmp     eax, r8d
0x180011fee  jz      short loc_180012032
0x180011ff0  cmp     rcx, rsi
0x180011ff3  jz      short loc_18001201C
0x180011ff5  test    [rcx+1Ch], ebx
0x180011ff8  jz      short loc_18001201C
0x180011ffa  cmp     byte ptr [rcx+19h], 2
0x180011ffe  jb      short loc_18001201C
0x180012000  mov     edx, 160h
0x180012005  mov     dword ptr [rsp+78h+var_58], eax
0x180012009  mov     r9d, r8d
0x18001200c  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180012013  mov     rcx, [rcx+10h]
0x180012017  call    WPP_SF_dd
0x18001201c  mov     ecx, 0Dh; dwErrCode
0x180012021  call    cs:__imp_SetLastError
0x180012028  nop     dword ptr [rax+rax+00h]
0x18001202d  jmp     loc_180012232
0x180012032  mov     [rsp+78h+dwBytes], r8
0x18001203a  lea     rax, [rsp+78h+dwBytes]
0x180012042  mov     [rsp+78h+var_50], rax
0x180012047  mov     [rsp+78h+var_58], 0
0x180012050  xor     r9d, r9d
0x180012053  xor     r8d, r8d
0x180012056  mov     edx, r15d
0x180012059  mov     rcx, r12
0x18001205c  call    SerializeGeneralConfig
0x180012061  mov     r13, [rsp+78h+dwBytes]
0x180012069  mov     ecx, r13d; dwBytes
0x18001206c  call    pMemAlloc
0x180012071  mov     rsi, rax
0x180012074  mov     [rsp+78h+arg_18], rax
0x18001207c  test    rax, rax
0x18001207f  jnz     short loc_1800120C1
0x180012081  mov     rcx, cs:WPP_GLOBAL_Control
0x180012088  lea     rax, WPP_GLOBAL_Control
0x18001208f  cmp     rcx, rax
0x180012092  jz      short loc_1800120B7
0x180012094  test    [rcx+1Ch], ebx
0x180012097  jz      short loc_1800120B7
0x180012099  cmp     byte ptr [rcx+19h], 2
0x18001209d  jb      short loc_1800120B7
0x18001209f  mov     edx, 161h
0x1800120a4  mov     r9d, r13d
0x1800120a7  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800120ae  mov     rcx, [rcx+10h]
0x1800120b2  call    WPP_SF_d
0x1800120b7  mov     ebx, 8
0x1800120bc  jmp     loc_1800121DB
0x1800120c1  mov     [rsp+78h+dwBytes], 58h ; 'X'
0x1800120cd  lea     rax, [rsp+78h+dwBytes]
0x1800120d5  mov     [rsp+78h+var_50], rax
0x1800120da  mov     [rsp+78h+var_58], rsi
0x1800120df  mov     r9d, r13d
0x1800120e2  mov     r8, rsi
0x1800120e5  mov     edx, r15d
0x1800120e8  mov     rcx, r12
0x1800120eb  call    SerializeGeneralConfig
0x1800120f0  mov     r8d, 58h ; 'X'; unsigned __int64
0x1800120f6  lea     rdx, ?fax_general_config_fields@@3PAU_FieldInfo@@A; struct _FieldInfo *
0x1800120fd  mov     rcx, rsi; unsigned __int8 *
0x180012100  call    MarshallDownStructure
0x180012105  test    eax, eax
0x180012107  jnz     short loc_180012146
0x180012109  mov     rcx, cs:WPP_GLOBAL_Control
0x180012110  lea     rax, WPP_GLOBAL_Control
0x180012117  cmp     rcx, rax
0x18001211a  jz      short loc_18001213C
0x18001211c  test    [rcx+1Ch], ebx
0x18001211f  jz      short loc_18001213C
0x180012121  cmp     byte ptr [rcx+19h], 2
0x180012125  jb      short loc_18001213C
0x180012127  mov     edx, 162h
0x18001212c  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180012133  mov     rcx, [rcx+10h]
0x180012137  call    WPP_SF_
0x18001213c  mov     ebx, 54Fh
0x180012141  jmp     loc_1800121DB
0x180012146  mov     rax, [r14+20h]
0x18001214a  mov     [rsp+78h+dwBytes], 0
0x180012156  mov     [rsp+78h+var_48], r13d
0x18001215b  mov     [rsp+78h+var_50], rsi
0x180012160  mov     dword ptr [rsp+78h+var_58], r15d
0x180012165  mov     r9, [rax]
0x180012168  xor     r8d, r8d; pReturnValue
0x18001216b  lea     edx, [r8+62h]; nProcNum
0x18001216f  lea     rcx, pProxyInfo; pProxyInfo
0x180012176  call    cs:__imp_NdrClientCall3
0x18001217d  nop     dword ptr [rax+rax+00h]
0x180012182  mov     rbx, rax
0x180012185  mov     [rsp+78h+dwBytes], rax
0x18001218d  mov     [rsp+78h+var_38], eax
0x180012191  jmp     short loc_1800121DB
0x180012193  mov     ebx, eax
0x180012195  mov     [rsp+78h+var_38], eax
0x180012199  lea     rdx, WPP_GLOBAL_Control
0x1800121a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121a7  cmp     rcx, rdx
0x1800121aa  jz      short loc_1800121D3
0x1800121ac  test    dword ptr [rcx+1Ch], 1000h
0x1800121b3  jz      short loc_1800121D3
0x1800121b5  cmp     byte ptr [rcx+19h], 2
0x1800121b9  jb      short loc_1800121D3
0x1800121bb  mov     edx, 163h
0x1800121c0  mov     r9d, eax
0x1800121c3  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800121ca  mov     rcx, [rcx+10h]
0x1800121ce  call    WPP_SF_d
0x1800121d3  mov     rsi, [rsp+78h+arg_18]
0x1800121db  mov     rcx, rsi; lpMem
0x1800121de  call    pMemFree
0x1800121e3  test    ebx, ebx
0x1800121e5  jz      short loc_1800121EE
0x1800121e7  mov     ecx, ebx
0x1800121e9  jmp     loc_180012021
0x1800121ee  mov     eax, 1
0x1800121f3  jmp     short loc_180012234
0x1800121f5  mov     ecx, 6; dwErrCode
0x1800121fa  call    cs:__imp_SetLastError
0x180012201  nop     dword ptr [rax+rax+00h]
0x180012206  mov     rcx, cs:WPP_GLOBAL_Control
0x18001220d  cmp     rcx, rsi
0x180012210  jz      short loc_180012232
0x180012212  test    [rcx+1Ch], ebx
0x180012215  jz      short loc_180012232
0x180012217  cmp     byte ptr [rcx+19h], 2
0x18001221b  jb      short loc_180012232
0x18001221d  mov     edx, 15Dh
0x180012222  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180012229  mov     rcx, [rcx+10h]
0x18001222d  call    WPP_SF_
0x180012232  xor     eax, eax
0x180012234  mov     rbx, [rsp+78h+arg_8]
0x18001223c  add     rsp, 50h
0x180012240  pop     r15
0x180012242  pop     r14
0x180012244  pop     r13
0x180012246  pop     r12
0x180012248  pop     rsi
0x180012249  retn
```
