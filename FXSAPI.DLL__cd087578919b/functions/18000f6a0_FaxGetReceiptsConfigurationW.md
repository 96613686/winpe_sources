# FaxGetReceiptsConfigurationW

- ea: `0x18000f6a0`
- end: `0x18000fa06`
- name: `FaxGetReceiptsConfigurationW`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f540`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000f6a0`
- `0x18002bb58`
- `0x180034538`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000f77c`
- `RPCRT4!NdrClientCall3` at `0x18000f77c`
- `KERNEL32!SetLastError` at `0x18000f715`
- `KERNEL32!SetLastError` at `0x18000f7ea`
- `KERNEL32!SetLastError` at `0x18000f857`
- `KERNEL32!SetLastError` at `0x18000f9b9`
- `KERNEL32!SetLastError` at `0x18000f715`
- `KERNEL32!SetLastError` at `0x18000f7ea`
- `KERNEL32!SetLastError` at `0x18000f857`
- `KERNEL32!SetLastError` at `0x18000f9b9`

## pseudocode

```c
__int64 __fastcall FaxGetReceiptsConfigurationW(__int64 a1, LPVOID *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  CLIENT_CALL_RETURN v7; // rax
  unsigned __int64 v8; // rdx
  unsigned int v9; // ecx
  _QWORD *v10; // rdx
  _WORD *v11; // r8
  unsigned int v12; // eax
  unsigned __int64 v13; // r8
  _QWORD *v14; // rdx
  _WORD *v15; // r8
  unsigned int v16; // eax
  unsigned __int64 v17; // r8
  _QWORD *v18; // rdx
  _WORD *v19; // r8
  unsigned int v20; // eax
  unsigned __int64 v21; // r8
  _WORD *v22; // rdx
  unsigned int v23; // eax
  unsigned int v25; // [rsp+60h] [rbp+8h] BYREF
  LPVOID *v26; // [rsp+68h] [rbp+10h]
  CLIENT_CALL_RETURN v27; // [rsp+70h] [rbp+18h]

  v26 = a2;
  v25 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 115;
LABEL_58:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 116;
    goto LABEL_58;
  }
  *a2 = 0;
  v6 = *(_QWORD **)(a1 + 32);
  v27.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x22u, 0, *v6, a2, &v25).Pointer;
  v27.Pointer = v7.Pointer;
  if ( LODWORD(v7.Pointer) )
  {
    SetLastError((DWORD)v7.Pointer);
  }
  else
  {
    if ( !(unsigned int)MarshallUpStructure(a2, &v25, &fax_receipts_config_fields, 72, 1, 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      SetLastError(0x54Fu);
      pMemFree(*a2);
      *a2 = 0;
      return 0;
    }
    v8 = *((_QWORD *)*a2 + 3);
    v9 = v25;
    if ( v8 <= v25 )
    {
      if ( v8 )
      {
        *((_QWORD *)*a2 + 3) = (char *)*a2 + v8;
        v9 = v25;
      }
      v10 = *a2;
      v11 = (_WORD *)*((_QWORD *)*a2 + 3);
      if ( v11 )
      {
        v12 = (v9 + (_DWORD)v10 - (_DWORD)v11) >> 1;
        if ( !v12 )
          return 0;
        while ( *v11 )
        {
          ++v11;
          if ( !--v12 )
            return 0;
        }
      }
      v13 = v10[5];
      if ( v13 <= v9 )
      {
        if ( v13 )
        {
          v10[5] = (char *)v10 + v13;
          v9 = v25;
        }
        v14 = *a2;
        v15 = (_WORD *)*((_QWORD *)*a2 + 5);
        if ( v15 )
        {
          v16 = (v9 + (_DWORD)v14 - (_DWORD)v15) >> 1;
          if ( !v16 )
            return 0;
          while ( *v15 )
          {
            ++v15;
            if ( !--v16 )
              return 0;
          }
        }
        v17 = v14[6];
        if ( v17 <= v9 )
        {
          if ( v17 )
          {
            v14[6] = (char *)v14 + v17;
            v9 = v25;
          }
          v18 = *a2;
          v19 = (_WORD *)*((_QWORD *)*a2 + 6);
          if ( v19 )
          {
            v20 = (v9 + (_DWORD)v18 - (_DWORD)v19) >> 1;
            if ( !v20 )
              return 0;
            while ( *v19 )
            {
              ++v19;
              if ( !--v20 )
                return 0;
            }
          }
          v21 = v18[7];
          if ( v21 <= v9 )
          {
            if ( v21 )
            {
              v18[7] = (char *)v18 + v21;
              v9 = v25;
            }
            v22 = (_WORD *)*((_QWORD *)*a2 + 7);
            if ( v22 )
            {
              v23 = (v9 + (unsigned int)*a2 - (_DWORD)v22) >> 1;
              if ( !v23 )
                return 0;
              while ( *v22 )
              {
                ++v22;
                if ( !--v23 )
                  return 0;
              }
            }
            return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f6a0  mov     [rsp+arg_18], rbx
0x18000f6a5  mov     [rsp+arg_8], rdx
0x18000f6aa  push    rsi
0x18000f6ab  push    rdi
0x18000f6ac  push    r15
0x18000f6ae  sub     rsp, 40h
0x18000f6b2  mov     rsi, rdx
0x18000f6b5  mov     rbx, rcx
0x18000f6b8  xor     edi, edi
0x18000f6ba  mov     [rsp+58h+arg_0], edi
0x18000f6be  lea     r15, WPP_GLOBAL_Control
0x18000f6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6cc  cmp     rcx, r15
0x18000f6cf  jz      short loc_18000F6F3
0x18000f6d1  test    dword ptr [rcx+1Ch], 1000h
0x18000f6d8  jz      short loc_18000F6F3
0x18000f6da  cmp     byte ptr [rcx+19h], 5
0x18000f6de  jb      short loc_18000F6F3
0x18000f6e0  lea     edx, [rdi+72h]
0x18000f6e3  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f6ea  mov     rcx, [rcx+10h]
0x18000f6ee  call    WPP_SF_
0x18000f6f3  test    rbx, rbx
0x18000f6f6  jz      loc_18000F9B4
0x18000f6fc  cmp     [rbx], edi
0x18000f6fe  jz      loc_18000F9B4
0x18000f704  cmp     [rbx+10h], edi
0x18000f707  jnz     loc_18000F9B4
0x18000f70d  test    rsi, rsi
0x18000f710  jnz     short loc_18000F750
0x18000f712  lea     ecx, [rsi+57h]; dwErrCode
0x18000f715  call    cs:__imp_SetLastError
0x18000f71c  nop     dword ptr [rax+rax+00h]
0x18000f721  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f728  cmp     rcx, r15
0x18000f72b  jz      loc_18000F9F5
0x18000f731  test    dword ptr [rcx+1Ch], 1000h
0x18000f738  jz      loc_18000F9F5
0x18000f73e  cmp     byte ptr [rcx+19h], 2
0x18000f742  jb      loc_18000F9F5
0x18000f748  lea     edx, [rsi+74h]
0x18000f74b  jmp     loc_18000F9E5
0x18000f750  mov     [rsi], rdi
0x18000f753  mov     rax, [rbx+20h]
0x18000f757  mov     [rsp+58h+arg_10], rdi
0x18000f75c  lea     rcx, [rsp+58h+arg_0]
0x18000f761  mov     [rsp+58h+var_30], rcx
0x18000f766  mov     [rsp+58h+var_38], rsi
0x18000f76b  mov     r9, [rax]
0x18000f76e  xor     r8d, r8d; pReturnValue
0x18000f771  lea     edx, [r8+22h]; nProcNum
0x18000f775  lea     rcx, pProxyInfo; pProxyInfo
0x18000f77c  call    cs:__imp_NdrClientCall3
0x18000f783  nop     dword ptr [rax+rax+00h]
0x18000f788  mov     rbx, rax
0x18000f78b  mov     [rsp+58h+arg_10], rax
0x18000f790  mov     [rsp+58h+var_28], eax
0x18000f794  jmp     short loc_18000F7E4
0x18000f796  mov     ebx, eax
0x18000f798  mov     [rsp+58h+var_28], eax
0x18000f79c  lea     rdx, WPP_GLOBAL_Control
0x18000f7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7aa  cmp     rcx, rdx
0x18000f7ad  jz      short loc_18000F7D6
0x18000f7af  test    dword ptr [rcx+1Ch], 1000h
0x18000f7b6  jz      short loc_18000F7D6
0x18000f7b8  cmp     byte ptr [rcx+19h], 2
0x18000f7bc  jb      short loc_18000F7D6
0x18000f7be  mov     edx, 75h ; 'u'
0x18000f7c3  mov     r9d, eax
0x18000f7c6  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f7cd  mov     rcx, [rcx+10h]
0x18000f7d1  call    WPP_SF_d
0x18000f7d6  xor     edi, edi
0x18000f7d8  lea     r15, WPP_GLOBAL_Control
0x18000f7df  mov     rsi, [rsp+58h+arg_8]
0x18000f7e4  test    ebx, ebx
0x18000f7e6  jz      short loc_18000F7FB
0x18000f7e8  mov     ecx, ebx; dwErrCode
0x18000f7ea  call    cs:__imp_SetLastError
0x18000f7f1  nop     dword ptr [rax+rax+00h]
0x18000f7f6  jmp     loc_18000F9F5
0x18000f7fb  mov     ebx, 1
0x18000f800  mov     dword ptr [rsp+58h+var_30], ebx
0x18000f804  mov     dword ptr [rsp+58h+var_38], ebx
0x18000f808  lea     r9d, [rbx+47h]
0x18000f80c  lea     r8, ?fax_receipts_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_receipts_config_fields
0x18000f813  lea     rdx, [rsp+58h+arg_0]
0x18000f818  mov     rcx, rsi
0x18000f81b  call    MarshallUpStructure
0x18000f820  test    eax, eax
0x18000f822  jnz     short loc_18000F873
0x18000f824  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f82b  cmp     rcx, r15
0x18000f82e  jz      short loc_18000F852
0x18000f830  test    dword ptr [rcx+1Ch], 1000h
0x18000f837  jz      short loc_18000F852
0x18000f839  cmp     byte ptr [rcx+19h], 2
0x18000f83d  jb      short loc_18000F852
0x18000f83f  lea     edx, [rbx+75h]
0x18000f842  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f849  mov     rcx, [rcx+10h]
0x18000f84d  call    WPP_SF_
0x18000f852  mov     ecx, 54Fh; dwErrCode
0x18000f857  call    cs:__imp_SetLastError
0x18000f85e  nop     dword ptr [rax+rax+00h]
0x18000f863  mov     rcx, [rsi]; lpMem
0x18000f866  call    pMemFree
0x18000f86b  mov     [rsi], rdi
0x18000f86e  jmp     loc_18000F9F5
0x18000f873  mov     r8, [rsi]
0x18000f876  mov     rdx, [r8+18h]
0x18000f87a  mov     ecx, [rsp+58h+arg_0]
0x18000f87e  cmp     rdx, rcx
0x18000f881  ja      loc_18000F9F5
0x18000f887  test    rdx, rdx
0x18000f88a  jz      short loc_18000F898
0x18000f88c  lea     rax, [rdx+r8]
0x18000f890  mov     [r8+18h], rax
0x18000f894  mov     ecx, [rsp+58h+arg_0]
0x18000f898  mov     rdx, [rsi]
0x18000f89b  mov     r8, [rdx+18h]
0x18000f89f  test    r8, r8
0x18000f8a2  jz      short loc_18000F8CB
0x18000f8a4  mov     eax, edx
0x18000f8a6  sub     eax, r8d
0x18000f8a9  add     eax, ecx
0x18000f8ab  shr     eax, 1
0x18000f8ad  jz      loc_18000F9F5
0x18000f8b3  or      r9d, 0FFFFFFFFh
0x18000f8b7  cmp     di, [r8]
0x18000f8bb  jz      short loc_18000F8CF
0x18000f8bd  add     r8, 2
0x18000f8c1  add     eax, r9d
0x18000f8c4  jnz     short loc_18000F8B7
0x18000f8c6  jmp     loc_18000F9F5
0x18000f8cb  or      r9d, 0FFFFFFFFh
0x18000f8cf  mov     r8, [rdx+28h]
0x18000f8d3  mov     eax, ecx
0x18000f8d5  cmp     r8, rax
0x18000f8d8  ja      loc_18000F9F5
0x18000f8de  test    r8, r8
0x18000f8e1  jz      short loc_18000F8EF
0x18000f8e3  lea     rax, [r8+rdx]
0x18000f8e7  mov     [rdx+28h], rax
0x18000f8eb  mov     ecx, [rsp+58h+arg_0]
0x18000f8ef  mov     rdx, [rsi]
0x18000f8f2  mov     r8, [rdx+28h]
0x18000f8f6  test    r8, r8
0x18000f8f9  jz      short loc_18000F91E
0x18000f8fb  mov     eax, edx
0x18000f8fd  sub     eax, r8d
0x18000f900  add     eax, ecx
0x18000f902  shr     eax, 1
0x18000f904  jz      loc_18000F9F5
0x18000f90a  cmp     di, [r8]
0x18000f90e  jz      short loc_18000F91E
0x18000f910  add     r8, 2
0x18000f914  add     eax, r9d
0x18000f917  jnz     short loc_18000F90A
0x18000f919  jmp     loc_18000F9F5
0x18000f91e  mov     r8, [rdx+30h]
0x18000f922  mov     eax, ecx
0x18000f924  cmp     r8, rax
0x18000f927  ja      loc_18000F9F5
0x18000f92d  test    r8, r8
0x18000f930  jz      short loc_18000F93E
0x18000f932  lea     rax, [r8+rdx]
0x18000f936  mov     [rdx+30h], rax
0x18000f93a  mov     ecx, [rsp+58h+arg_0]
0x18000f93e  mov     rdx, [rsi]
0x18000f941  mov     r8, [rdx+30h]
0x18000f945  test    r8, r8
0x18000f948  jz      short loc_18000F96D
0x18000f94a  mov     eax, edx
0x18000f94c  sub     eax, r8d
0x18000f94f  add     eax, ecx
0x18000f951  shr     eax, 1
0x18000f953  jz      loc_18000F9F5
0x18000f959  cmp     di, [r8]
0x18000f95d  jz      short loc_18000F96D
0x18000f95f  add     r8, 2
0x18000f963  add     eax, r9d
0x18000f966  jnz     short loc_18000F959
0x18000f968  jmp     loc_18000F9F5
0x18000f96d  mov     r8, [rdx+38h]
0x18000f971  mov     eax, ecx
0x18000f973  cmp     r8, rax
0x18000f976  ja      short loc_18000F9F5
0x18000f978  test    r8, r8
0x18000f97b  jz      short loc_18000F989
0x18000f97d  lea     rax, [r8+rdx]
0x18000f981  mov     [rdx+38h], rax
0x18000f985  mov     ecx, [rsp+58h+arg_0]
0x18000f989  mov     r8, [rsi]
0x18000f98c  mov     rdx, [r8+38h]
0x18000f990  test    rdx, rdx
0x18000f993  jz      short loc_18000F9B0
0x18000f995  mov     eax, r8d
0x18000f998  sub     eax, edx
0x18000f99a  add     eax, ecx
0x18000f99c  shr     eax, 1
0x18000f99e  jz      short loc_18000F9F5
0x18000f9a0  cmp     di, [rdx]
0x18000f9a3  jz      short loc_18000F9B0
0x18000f9a5  add     rdx, 2
0x18000f9a9  add     eax, r9d
0x18000f9ac  jnz     short loc_18000F9A0
0x18000f9ae  jmp     short loc_18000F9F5
0x18000f9b0  mov     eax, ebx
0x18000f9b2  jmp     short loc_18000F9F7
0x18000f9b4  mov     ecx, 6; dwErrCode
0x18000f9b9  call    cs:__imp_SetLastError
0x18000f9c0  nop     dword ptr [rax+rax+00h]
0x18000f9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9cc  cmp     rcx, r15
0x18000f9cf  jz      short loc_18000F9F5
0x18000f9d1  test    dword ptr [rcx+1Ch], 1000h
0x18000f9d8  jz      short loc_18000F9F5
0x18000f9da  cmp     byte ptr [rcx+19h], 2
0x18000f9de  jb      short loc_18000F9F5
0x18000f9e0  mov     edx, 73h ; 's'
0x18000f9e5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f9ec  mov     rcx, [rcx+10h]
0x18000f9f0  call    WPP_SF_
0x18000f9f5  xor     eax, eax
0x18000f9f7  mov     rbx, [rsp+58h+arg_18]
0x18000f9fc  add     rsp, 40h
0x18000fa00  pop     r15
0x18000fa02  pop     rdi
0x18000fa03  pop     rsi
0x18000fa04  retn
```
