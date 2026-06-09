# FaxEnumRoutingExtensionsW

- ea: `0x18000d130`
- end: `0x18000d54b`
- name: `FaxEnumRoutingExtensionsW`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ceb0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000d130`
- `0x18002bb58`
- `0x18003466c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d2bd`
- `RPCRT4!NdrClientCall3` at `0x18000d2bd`
- `KERNEL32!SetLastError` at `0x18000d1af`
- `KERNEL32!SetLastError` at `0x18000d1f6`
- `KERNEL32!SetLastError` at `0x18000d27c`
- `KERNEL32!SetLastError` at `0x18000d3a4`
- `KERNEL32!SetLastError` at `0x18000d4ff`
- `KERNEL32!SetLastError` at `0x18000d1af`
- `KERNEL32!SetLastError` at `0x18000d1f6`
- `KERNEL32!SetLastError` at `0x18000d27c`
- `KERNEL32!SetLastError` at `0x18000d3a4`
- `KERNEL32!SetLastError` at `0x18000d4ff`

## pseudocode

```c
__int64 __fastcall FaxEnumRoutingExtensionsW(__int64 a1, LPVOID *a2, _DWORD *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r9
  DWORD Pointer; // ecx
  CLIENT_CALL_RETURN v11; // rax
  unsigned int v12; // r10d
  unsigned int v13; // r8d
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  char *v16; // rdx
  _WORD *v17; // r9
  unsigned int v18; // eax
  unsigned __int64 v19; // r9
  char *v20; // rdx
  _WORD *v21; // r9
  unsigned int v22; // eax
  unsigned __int64 v23; // r9
  _WORD *v24; // rdx
  unsigned int v25; // eax
  unsigned int v27; // [rsp+80h] [rbp+8h] BYREF
  LPVOID *v28; // [rsp+88h] [rbp+10h]
  _DWORD *v29; // [rsp+90h] [rbp+18h]
  CLIENT_CALL_RETURN v30; // [rsp+98h] [rbp+20h]

  v29 = a3;
  v28 = a2;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 315;
LABEL_65:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 316;
    goto LABEL_65;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 317;
    goto LABEL_65;
  }
  *a2 = 0;
  v8 = *(_QWORD *)(a1 + 32);
  v9 = *(unsigned int *)(v8 + 80);
  if ( (unsigned int)v9 < 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v9);
    }
    Pointer = 7012;
    goto LABEL_24;
  }
  v30.Simple = 0;
  v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x4Eu, 0, *(_QWORD *)v8, a2, &v27, a3).Pointer;
  v30.Pointer = v11.Pointer;
  if ( LODWORD(v11.Pointer) )
  {
    Pointer = (DWORD)v11.Pointer;
LABEL_24:
    SetLastError(Pointer);
    return 0;
  }
  if ( (unsigned int)MarshallUpStructuresArray(a2, &v27, (unsigned int)*a3, &fax_routing_extension_info_fields, 64, 1) )
  {
    v12 = 0;
    if ( !*a3 )
      return 1;
    v13 = v27;
    while ( 1 )
    {
      v14 = (unsigned __int64)v12 << 6;
      v15 = *(_QWORD *)((char *)*a2 + v14 + 8);
      if ( v15 > v13 )
        break;
      if ( v15 )
      {
        *(_QWORD *)((char *)*a2 + v14 + 8) = (char *)*a2 + v15;
        v13 = v27;
      }
      v16 = (char *)*a2;
      v17 = *(_WORD **)((char *)*a2 + v14 + 8);
      if ( v17 )
      {
        v18 = (v13 + (_DWORD)v16 - (_DWORD)v17) >> 1;
        if ( !v18 )
          return 0;
        while ( *v17 )
        {
          if ( !--v18 )
            return 0;
          ++v17;
        }
      }
      v19 = *(_QWORD *)&v16[v14 + 16];
      if ( v19 > v13 )
        break;
      if ( v19 )
      {
        *(_QWORD *)&v16[v14 + 16] = &v16[v19];
        v13 = v27;
      }
      v20 = (char *)*a2;
      v21 = *(_WORD **)((char *)*a2 + v14 + 16);
      if ( v21 )
      {
        v22 = (v13 + (_DWORD)v20 - (_DWORD)v21) >> 1;
        if ( !v22 )
          return 0;
        while ( *v21 )
        {
          if ( !--v22 )
            return 0;
          ++v21;
        }
      }
      v23 = *(_QWORD *)&v20[v14 + 24];
      if ( v23 > v13 )
        break;
      if ( v23 )
      {
        *(_QWORD *)&v20[v14 + 24] = &v20[v23];
        v13 = v27;
      }
      v24 = *(_WORD **)((char *)*a2 + v14 + 24);
      if ( v24 )
      {
        v25 = (v13 + (unsigned int)*a2 - (_DWORD)v24) >> 1;
        if ( !v25 )
          return 0;
        while ( *v24 )
        {
          if ( !--v25 )
            return 0;
          ++v24;
        }
      }
      if ( ++v12 >= *a3 )
        return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
    SetLastError(0x54Fu);
    pMemFree(*a2);
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d130  mov     rax, rsp
0x18000d133  mov     [rax+18h], r8
0x18000d137  mov     [rax+10h], rdx
0x18000d13b  push    rbx
0x18000d13c  push    rdi
0x18000d13d  push    r12
0x18000d13f  push    r14
0x18000d141  push    r15
0x18000d143  sub     rsp, 50h
0x18000d147  mov     r12, r8
0x18000d14a  mov     r14, rdx
0x18000d14d  mov     rbx, rcx
0x18000d150  xor     edi, edi
0x18000d152  mov     [rax+8], edi
0x18000d155  lea     r15, WPP_GLOBAL_Control
0x18000d15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d163  cmp     rcx, r15
0x18000d166  jz      short loc_18000D18C
0x18000d168  test    dword ptr [rcx+1Ch], 1000h
0x18000d16f  jz      short loc_18000D18C
0x18000d171  cmp     byte ptr [rcx+19h], 5
0x18000d175  jb      short loc_18000D18C
0x18000d177  mov     edx, 13Ah
0x18000d17c  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d183  mov     rcx, [rcx+10h]
0x18000d187  call    WPP_SF_
0x18000d18c  test    rbx, rbx
0x18000d18f  jz      loc_18000D4FA
0x18000d195  cmp     [rbx], edi
0x18000d197  jz      loc_18000D4FA
0x18000d19d  cmp     [rbx+10h], edi
0x18000d1a0  jnz     loc_18000D4FA
0x18000d1a6  test    r14, r14
0x18000d1a9  jnz     short loc_18000D1EC
0x18000d1ab  lea     ecx, [r14+57h]; dwErrCode
0x18000d1af  call    cs:__imp_SetLastError
0x18000d1b6  nop     dword ptr [rax+rax+00h]
0x18000d1bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c2  cmp     rcx, r15
0x18000d1c5  jz      loc_18000D53B
0x18000d1cb  test    dword ptr [rcx+1Ch], 1000h
0x18000d1d2  jz      loc_18000D53B
0x18000d1d8  cmp     byte ptr [rcx+19h], 2
0x18000d1dc  jb      loc_18000D53B
0x18000d1e2  mov     edx, 13Ch
0x18000d1e7  jmp     loc_18000D52B
0x18000d1ec  test    r12, r12
0x18000d1ef  jnz     short loc_18000D233
0x18000d1f1  lea     ecx, [r12+57h]; dwErrCode
0x18000d1f6  call    cs:__imp_SetLastError
0x18000d1fd  nop     dword ptr [rax+rax+00h]
0x18000d202  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d209  cmp     rcx, r15
0x18000d20c  jz      loc_18000D53B
0x18000d212  test    dword ptr [rcx+1Ch], 1000h
0x18000d219  jz      loc_18000D53B
0x18000d21f  cmp     byte ptr [rcx+19h], 2
0x18000d223  jb      loc_18000D53B
0x18000d229  mov     edx, 13Dh
0x18000d22e  jmp     loc_18000D52B
0x18000d233  mov     [r14], rdi
0x18000d236  mov     rax, [rbx+20h]
0x18000d23a  mov     r9d, [rax+50h]
0x18000d23e  cmp     r9d, 10000h
0x18000d245  jnb     short loc_18000D28D
0x18000d247  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d24e  cmp     rcx, r15
0x18000d251  jz      short loc_18000D277
0x18000d253  test    dword ptr [rcx+1Ch], 1000h
0x18000d25a  jz      short loc_18000D277
0x18000d25c  cmp     byte ptr [rcx+19h], 5
0x18000d260  jb      short loc_18000D277
0x18000d262  mov     edx, 13Eh
0x18000d267  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d26e  mov     rcx, [rcx+10h]
0x18000d272  call    WPP_SF_d
0x18000d277  mov     ecx, 1B64h; dwErrCode
0x18000d27c  call    cs:__imp_SetLastError
0x18000d283  nop     dword ptr [rax+rax+00h]
0x18000d288  jmp     loc_18000D53B
0x18000d28d  mov     [rsp+78h+arg_18], rdi
0x18000d295  mov     [rsp+78h+var_48], r12
0x18000d29a  lea     rcx, [rsp+78h+arg_0]
0x18000d2a2  mov     [rsp+78h+var_50], rcx
0x18000d2a7  mov     [rsp+78h+var_58], r14
0x18000d2ac  mov     r9, [rax]
0x18000d2af  xor     r8d, r8d; pReturnValue
0x18000d2b2  lea     edx, [r8+4Eh]; nProcNum
0x18000d2b6  lea     rcx, pProxyInfo; pProxyInfo
0x18000d2bd  call    cs:__imp_NdrClientCall3
0x18000d2c4  nop     dword ptr [rax+rax+00h]
0x18000d2c9  mov     rbx, rax
0x18000d2cc  mov     [rsp+78h+arg_18], rax
0x18000d2d4  mov     [rsp+78h+var_38], eax
0x18000d2d8  jmp     short loc_18000D333
0x18000d2da  mov     ebx, eax
0x18000d2dc  mov     [rsp+78h+var_38], eax
0x18000d2e0  lea     rdx, WPP_GLOBAL_Control
0x18000d2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2ee  cmp     rcx, rdx
0x18000d2f1  jz      short loc_18000D31A
0x18000d2f3  test    dword ptr [rcx+1Ch], 1000h
0x18000d2fa  jz      short loc_18000D31A
0x18000d2fc  cmp     byte ptr [rcx+19h], 2
0x18000d300  jb      short loc_18000D31A
0x18000d302  mov     edx, 13Fh
0x18000d307  mov     r9d, eax
0x18000d30a  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d311  mov     rcx, [rcx+10h]
0x18000d315  call    WPP_SF_d
0x18000d31a  xor     edi, edi
0x18000d31c  lea     r15, WPP_GLOBAL_Control
0x18000d323  mov     r12, [rsp+78h+arg_10]
0x18000d32b  mov     r14, [rsp+78h+arg_8]
0x18000d333  test    ebx, ebx
0x18000d335  jz      short loc_18000D33E
0x18000d337  mov     ecx, ebx
0x18000d339  jmp     loc_18000D27C
0x18000d33e  mov     ebx, 1
0x18000d343  mov     dword ptr [rsp+78h+var_50], ebx
0x18000d347  mov     [rsp+78h+var_58], 40h ; '@'
0x18000d350  lea     r9, ?fax_routing_extension_info_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_routing_extension_info_fields
0x18000d357  mov     r8d, [r12]
0x18000d35b  lea     rdx, [rsp+78h+arg_0]
0x18000d363  mov     rcx, r14
0x18000d366  call    MarshallUpStructuresArray
0x18000d36b  test    eax, eax
0x18000d36d  jnz     short loc_18000D3C4
0x18000d36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d376  cmp     rcx, r15
0x18000d379  jz      short loc_18000D39F
0x18000d37b  test    dword ptr [rcx+1Ch], 1000h
0x18000d382  jz      short loc_18000D39F
0x18000d384  cmp     byte ptr [rcx+19h], 2
0x18000d388  jb      short loc_18000D39F
0x18000d38a  mov     edx, 140h
0x18000d38f  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d396  mov     rcx, [rcx+10h]
0x18000d39a  call    WPP_SF_
0x18000d39f  mov     ecx, 54Fh; dwErrCode
0x18000d3a4  call    cs:__imp_SetLastError
0x18000d3ab  nop     dword ptr [rax+rax+00h]
0x18000d3b0  mov     rcx, [r14]; lpMem
0x18000d3b3  call    pMemFree
0x18000d3b8  mov     [r14], rdi
0x18000d3bb  mov     [r12], edi
0x18000d3bf  jmp     loc_18000D53B
0x18000d3c4  mov     r10d, edi
0x18000d3c7  cmp     [r12], edi
0x18000d3cb  jbe     loc_18000D4F6
0x18000d3d1  or      r11d, 0FFFFFFFFh
0x18000d3d5  mov     r8d, [rsp+78h+arg_0]
0x18000d3dd  mov     ecx, r10d
0x18000d3e0  shl     rcx, 6
0x18000d3e4  mov     r9, [r14]
0x18000d3e7  mov     rdx, [rcx+r9+8]
0x18000d3ec  mov     eax, r8d
0x18000d3ef  cmp     rdx, rax
0x18000d3f2  ja      loc_18000D53B
0x18000d3f8  test    rdx, rdx
0x18000d3fb  jz      short loc_18000D40E
0x18000d3fd  lea     rax, [rdx+r9]
0x18000d401  mov     [rcx+r9+8], rax
0x18000d406  mov     r8d, [rsp+78h+arg_0]
0x18000d40e  mov     rdx, [r14]
0x18000d411  mov     r9, [rcx+rdx+8]
0x18000d416  test    r9, r9
0x18000d419  jz      short loc_18000D440
0x18000d41b  mov     eax, edx
0x18000d41d  sub     eax, r9d
0x18000d420  add     eax, r8d
0x18000d423  shr     eax, 1
0x18000d425  jz      loc_18000D53B
0x18000d42b  cmp     di, [r9]
0x18000d42f  jz      short loc_18000D440
0x18000d431  add     eax, r11d
0x18000d434  jz      loc_18000D53B
0x18000d43a  add     r9, 2
0x18000d43e  jmp     short loc_18000D42B
0x18000d440  mov     r9, [rcx+rdx+10h]
0x18000d445  mov     eax, r8d
0x18000d448  cmp     r9, rax
0x18000d44b  ja      loc_18000D53B
0x18000d451  test    r9, r9
0x18000d454  jz      short loc_18000D467
0x18000d456  lea     rax, [r9+rdx]
0x18000d45a  mov     [rcx+rdx+10h], rax
0x18000d45f  mov     r8d, [rsp+78h+arg_0]
0x18000d467  mov     rdx, [r14]
0x18000d46a  mov     r9, [rdx+rcx+10h]
0x18000d46f  test    r9, r9
0x18000d472  jz      short loc_18000D499
0x18000d474  mov     eax, edx
0x18000d476  sub     eax, r9d
0x18000d479  add     eax, r8d
0x18000d47c  shr     eax, 1
0x18000d47e  jz      loc_18000D53B
0x18000d484  cmp     di, [r9]
0x18000d488  jz      short loc_18000D499
0x18000d48a  add     eax, r11d
0x18000d48d  jz      loc_18000D53B
0x18000d493  add     r9, 2
0x18000d497  jmp     short loc_18000D484
0x18000d499  mov     r9, [rdx+rcx+18h]
0x18000d49e  mov     eax, r8d
0x18000d4a1  cmp     r9, rax
0x18000d4a4  ja      loc_18000D53B
0x18000d4aa  test    r9, r9
0x18000d4ad  jz      short loc_18000D4C0
0x18000d4af  lea     rax, [r9+rdx]
0x18000d4b3  mov     [rdx+rcx+18h], rax
0x18000d4b8  mov     r8d, [rsp+78h+arg_0]
0x18000d4c0  mov     r9, [r14]
0x18000d4c3  mov     rdx, [r9+rcx+18h]
0x18000d4c8  test    rdx, rdx
0x18000d4cb  jz      short loc_18000D4E9
0x18000d4cd  mov     eax, r9d
0x18000d4d0  sub     eax, edx
0x18000d4d2  add     eax, r8d
0x18000d4d5  shr     eax, 1
0x18000d4d7  jz      short loc_18000D53B
0x18000d4d9  cmp     di, [rdx]
0x18000d4dc  jz      short loc_18000D4E9
0x18000d4de  add     eax, r11d
0x18000d4e1  jz      short loc_18000D53B
0x18000d4e3  add     rdx, 2
0x18000d4e7  jmp     short loc_18000D4D9
0x18000d4e9  add     r10d, ebx
0x18000d4ec  cmp     r10d, [r12]
0x18000d4f0  jb      loc_18000D3DD
0x18000d4f6  mov     eax, ebx
0x18000d4f8  jmp     short loc_18000D53D
0x18000d4fa  mov     ecx, 6; dwErrCode
0x18000d4ff  call    cs:__imp_SetLastError
0x18000d506  nop     dword ptr [rax+rax+00h]
0x18000d50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d512  cmp     rcx, r15
0x18000d515  jz      short loc_18000D53B
0x18000d517  test    dword ptr [rcx+1Ch], 1000h
0x18000d51e  jz      short loc_18000D53B
0x18000d520  cmp     byte ptr [rcx+19h], 2
0x18000d524  jb      short loc_18000D53B
0x18000d526  mov     edx, 13Bh
0x18000d52b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d532  mov     rcx, [rcx+10h]
0x18000d536  call    WPP_SF_
0x18000d53b  xor     eax, eax
0x18000d53d  add     rsp, 50h
0x18000d541  pop     r15
0x18000d543  pop     r14
0x18000d545  pop     r12
0x18000d547  pop     rdi
0x18000d548  pop     rbx
0x18000d549  retn
```
