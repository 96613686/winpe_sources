# FaxSetArchiveConfigurationW

- ea: `0x180011160`
- end: `0x18001145e`
- name: `FaxSetArchiveConfigurationW`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010f80`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180011160`
- `0x180014314`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001139f`
- `RPCRT4!NdrClientCall3` at `0x18001139f`
- `KERNEL32!SetLastError` at `0x1800111dd`
- `KERNEL32!SetLastError` at `0x180011260`
- `KERNEL32!SetLastError` at `0x18001133b`
- `KERNEL32!SetLastError` at `0x180011414`
- `KERNEL32!SetLastError` at `0x1800111dd`
- `KERNEL32!SetLastError` at `0x180011260`
- `KERNEL32!SetLastError` at `0x18001133b`
- `KERNEL32!SetLastError` at `0x180011414`

## pseudocode

```c
__int64 __fastcall FaxSetArchiveConfigurationW(__int64 a1, unsigned int a2, __int64 a3)
{
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _WORD *v9; // rax
  __int64 v10; // rdx
  DWORD v11; // ecx
  unsigned int Pointer; // eax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v8 = 165;
    goto LABEL_53;
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
    v8 = 166;
    goto LABEL_53;
  }
  if ( a2 <= 1 )
  {
    if ( *(_DWORD *)a3 == 40 )
    {
      if ( *(_DWORD *)(a3 + 4) )
      {
        if ( *(_DWORD *)(a3 + 20) < *(_DWORD *)(a3 + 24) )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
            WPP_SF_dd(v6[2], 169, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
          goto LABEL_45;
        }
        v9 = *(_WORD **)(a3 + 8);
        if ( !v9 || !*v9 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
            WPP_SF_(v6[2], 170, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
          goto LABEL_45;
        }
        v10 = 181;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v10;
        }
        while ( v10 );
        if ( !v10 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
            WPP_SF_(v6[2], 171, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
          v11 = 111;
          goto LABEL_40;
        }
      }
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x2Au,
                                0,
                                **(_QWORD **)(a1 + 32),
                                a2,
                                a3).Pointer;
      if ( !Pointer )
        return 1;
      v11 = Pointer;
      goto LABEL_40;
    }
    SetLastError(0x57u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 168;
LABEL_53:
    WPP_SF_(v7[2], v8, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    WPP_SF_d(v6[2], 167, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, a2);
LABEL_45:
  v11 = 87;
LABEL_40:
  SetLastError(v11);
  return 0;
}

```

## disassembly

```asm
0x180011160  push    rbx
0x180011162  push    rdi
0x180011163  push    r12
0x180011165  push    r13
0x180011167  push    r14
0x180011169  push    r15
0x18001116b  sub     rsp, 48h
0x18001116f  mov     r14, r8
0x180011172  mov     r12d, edx
0x180011175  mov     r15, rcx
0x180011178  lea     r13, WPP_GLOBAL_Control
0x18001117f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011186  mov     ebx, 1000h
0x18001118b  cmp     rcx, r13
0x18001118e  jz      short loc_1800111B7
0x180011190  test    [rcx+1Ch], ebx
0x180011193  jz      short loc_1800111B7
0x180011195  cmp     byte ptr [rcx+19h], 5
0x180011199  jb      short loc_1800111B7
0x18001119b  mov     edx, 0A4h
0x1800111a0  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800111a7  mov     rcx, [rcx+10h]
0x1800111ab  call    WPP_SF_
0x1800111b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111b7  xor     edi, edi
0x1800111b9  test    r15, r15
0x1800111bc  jz      loc_18001140F
0x1800111c2  cmp     [r15], edi
0x1800111c5  jz      loc_18001140F
0x1800111cb  cmp     [r15+10h], edi
0x1800111cf  jnz     loc_18001140F
0x1800111d5  test    r14, r14
0x1800111d8  jnz     short loc_180011216
0x1800111da  lea     ecx, [rdi+57h]; dwErrCode
0x1800111dd  call    cs:__imp_SetLastError
0x1800111e4  nop     dword ptr [rax+rax+00h]
0x1800111e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111f0  cmp     rcx, r13
0x1800111f3  jz      loc_18001144C
0x1800111f9  test    [rcx+1Ch], ebx
0x1800111fc  jz      loc_18001144C
0x180011202  cmp     byte ptr [rcx+19h], 2
0x180011206  jb      loc_18001144C
0x18001120c  mov     edx, 0A6h
0x180011211  jmp     loc_18001143C
0x180011216  cmp     r12d, 1
0x18001121a  jbe     short loc_180011255
0x18001121c  cmp     rcx, r13
0x18001121f  jz      loc_180011371
0x180011225  test    [rcx+1Ch], ebx
0x180011228  jz      loc_180011371
0x18001122e  cmp     byte ptr [rcx+19h], 2
0x180011232  jb      loc_180011371
0x180011238  mov     edx, 0A7h
0x18001123d  mov     r9d, r12d
0x180011240  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011247  mov     rcx, [rcx+10h]
0x18001124b  call    WPP_SF_d
0x180011250  jmp     loc_180011371
0x180011255  cmp     dword ptr [r14], 28h ; '('
0x180011259  jz      short loc_180011299
0x18001125b  mov     ecx, 57h ; 'W'; dwErrCode
0x180011260  call    cs:__imp_SetLastError
0x180011267  nop     dword ptr [rax+rax+00h]
0x18001126c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011273  cmp     rcx, r13
0x180011276  jz      loc_18001144C
0x18001127c  test    [rcx+1Ch], ebx
0x18001127f  jz      loc_18001144C
0x180011285  cmp     byte ptr [rcx+19h], 2
0x180011289  jb      loc_18001144C
0x18001128f  mov     edx, 0A8h
0x180011294  jmp     loc_18001143C
0x180011299  cmp     [r14+4], edi
0x18001129d  jz      loc_180011378
0x1800112a3  mov     eax, [r14+18h]
0x1800112a7  mov     r9d, [r14+14h]
0x1800112ab  cmp     r9d, eax
0x1800112ae  jnb     short loc_1800112EA
0x1800112b0  cmp     rcx, r13
0x1800112b3  jz      loc_180011371
0x1800112b9  test    [rcx+1Ch], ebx
0x1800112bc  jz      loc_180011371
0x1800112c2  cmp     byte ptr [rcx+19h], 2
0x1800112c6  jb      loc_180011371
0x1800112cc  mov     edx, 0A9h
0x1800112d1  mov     [rsp+78h+var_58], eax
0x1800112d5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800112dc  mov     rcx, [rcx+10h]
0x1800112e0  call    WPP_SF_dd
0x1800112e5  jmp     loc_180011371
0x1800112ea  mov     rax, [r14+8]
0x1800112ee  test    rax, rax
0x1800112f1  jz      short loc_18001134C
0x1800112f3  cmp     di, [rax]
0x1800112f6  jz      short loc_18001134C
0x1800112f8  mov     edx, 0B5h
0x1800112fd  cmp     [rax], di
0x180011300  jz      short loc_18001130C
0x180011302  add     rax, 2
0x180011306  sub     rdx, 1
0x18001130a  jnz     short loc_1800112FD
0x18001130c  test    rdx, rdx
0x18001130f  jnz     short loc_180011378
0x180011311  cmp     rcx, r13
0x180011314  jz      short loc_180011336
0x180011316  test    [rcx+1Ch], ebx
0x180011319  jz      short loc_180011336
0x18001131b  cmp     byte ptr [rcx+19h], 2
0x18001131f  jb      short loc_180011336
0x180011321  mov     edx, 0ABh
0x180011326  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001132d  mov     rcx, [rcx+10h]
0x180011331  call    WPP_SF_
0x180011336  mov     ecx, 6Fh ; 'o'; dwErrCode
0x18001133b  call    cs:__imp_SetLastError
0x180011342  nop     dword ptr [rax+rax+00h]
0x180011347  jmp     loc_18001144C
0x18001134c  cmp     rcx, r13
0x18001134f  jz      short loc_180011371
0x180011351  test    [rcx+1Ch], ebx
0x180011354  jz      short loc_180011371
0x180011356  cmp     byte ptr [rcx+19h], 2
0x18001135a  jb      short loc_180011371
0x18001135c  mov     edx, 0AAh
0x180011361  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011368  mov     rcx, [rcx+10h]
0x18001136c  call    WPP_SF_
0x180011371  mov     ecx, 57h ; 'W'
0x180011376  jmp     short loc_18001133B
0x180011378  mov     rax, [r15+20h]
0x18001137c  mov     [rsp+78h+arg_0], rdi
0x180011384  mov     [rsp+78h+var_50], r14
0x180011389  mov     [rsp+78h+var_58], r12d
0x18001138e  mov     r9, [rax]
0x180011391  xor     r8d, r8d; pReturnValue
0x180011394  lea     edx, [r8+2Ah]; nProcNum
0x180011398  lea     rcx, pProxyInfo; pProxyInfo
0x18001139f  call    cs:__imp_NdrClientCall3
0x1800113a6  nop     dword ptr [rax+rax+00h]
0x1800113ab  mov     rbx, rax
0x1800113ae  mov     [rsp+78h+arg_0], rax
0x1800113b6  mov     [rsp+78h+var_48], eax
0x1800113ba  jmp     short loc_1800113FD
0x1800113bc  mov     ebx, eax
0x1800113be  mov     [rsp+78h+var_48], eax
0x1800113c2  lea     rdx, WPP_GLOBAL_Control
0x1800113c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113d0  cmp     rcx, rdx
0x1800113d3  jz      short loc_1800113FD
0x1800113d5  test    dword ptr [rcx+1Ch], 1000h
0x1800113dc  jz      short loc_1800113FD
0x1800113de  cmp     byte ptr [rcx+19h], 2
0x1800113e2  jb      short loc_1800113FD
0x1800113e4  mov     edx, 0ACh
0x1800113e9  mov     r9d, eax
0x1800113ec  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800113f3  mov     rcx, [rcx+10h]
0x1800113f7  call    WPP_SF_d
0x1800113fc  nop
0x1800113fd  test    ebx, ebx
0x1800113ff  jz      short loc_180011408
0x180011401  mov     ecx, ebx
0x180011403  jmp     loc_18001133B
0x180011408  mov     eax, 1
0x18001140d  jmp     short loc_18001144E
0x18001140f  mov     ecx, 6; dwErrCode
0x180011414  call    cs:__imp_SetLastError
0x18001141b  nop     dword ptr [rax+rax+00h]
0x180011420  mov     rcx, cs:WPP_GLOBAL_Control
0x180011427  cmp     rcx, r13
0x18001142a  jz      short loc_18001144C
0x18001142c  test    [rcx+1Ch], ebx
0x18001142f  jz      short loc_18001144C
0x180011431  cmp     byte ptr [rcx+19h], 2
0x180011435  jb      short loc_18001144C
0x180011437  mov     edx, 0A5h
0x18001143c  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011443  mov     rcx, [rcx+10h]
0x180011447  call    WPP_SF_
0x18001144c  xor     eax, eax
0x18001144e  add     rsp, 48h
0x180011452  pop     r15
0x180011454  pop     r14
0x180011456  pop     r13
0x180011458  pop     r12
0x18001145a  pop     rdi
0x18001145b  pop     rbx
0x18001145c  retn
```
