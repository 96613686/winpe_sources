# FaxGetActivityLoggingConfigurationW

- ea: `0x18000d680`
- end: `0x18000d8f9`
- name: `FaxGetActivityLoggingConfigurationW`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d560`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000d680`
- `0x18002bb58`
- `0x180034538`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d760`
- `RPCRT4!NdrClientCall3` at `0x18000d760`
- `KERNEL32!SetLastError` at `0x18000d6f7`
- `KERNEL32!SetLastError` at `0x18000d7ce`
- `KERNEL32!SetLastError` at `0x18000d83d`
- `KERNEL32!SetLastError` at `0x18000d8ac`
- `KERNEL32!SetLastError` at `0x18000d6f7`
- `KERNEL32!SetLastError` at `0x18000d7ce`
- `KERNEL32!SetLastError` at `0x18000d83d`
- `KERNEL32!SetLastError` at `0x18000d8ac`

## pseudocode

```c
__int64 __fastcall FaxGetActivityLoggingConfigurationW(__int64 a1, LPVOID *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  CLIENT_CALL_RETURN v7; // rax
  unsigned __int64 v8; // rcx
  unsigned int v9; // r8d
  _WORD *v10; // rcx
  unsigned int v11; // eax
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF
  LPVOID *v14; // [rsp+68h] [rbp+10h]
  CLIENT_CALL_RETURN v15; // [rsp+70h] [rbp+18h]

  v14 = a2;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v5 = 177;
LABEL_34:
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
    v5 = 178;
    goto LABEL_34;
  }
  *a2 = 0;
  v6 = *(_QWORD **)(a1 + 32);
  v15.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Bu, 0, *v6, a2, &v13).Pointer;
  v15.Pointer = v7.Pointer;
  if ( LODWORD(v7.Pointer) )
  {
    SetLastError((DWORD)v7.Pointer);
  }
  else
  {
    if ( !(unsigned int)MarshallUpStructure(a2, &v13, &fax_activity_logging_config_fields, 24, 1, 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      SetLastError(0x54Fu);
      pMemFree(*a2);
      *a2 = 0;
      return 0;
    }
    v8 = *((_QWORD *)*a2 + 2);
    v9 = v13;
    if ( v8 <= v13 )
    {
      if ( v8 )
      {
        *((_QWORD *)*a2 + 2) = (char *)*a2 + v8;
        v9 = v13;
      }
      v10 = (_WORD *)*((_QWORD *)*a2 + 2);
      if ( v10 )
      {
        v11 = (v9 + (unsigned int)*a2 - (_DWORD)v10) >> 1;
        if ( !v11 )
          return 0;
        while ( *v10 )
        {
          ++v10;
          if ( !--v11 )
            return 0;
        }
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d680  mov     [rsp+arg_18], rbx
0x18000d685  mov     [rsp+arg_8], rdx
0x18000d68a  push    rsi
0x18000d68b  push    rdi
0x18000d68c  push    r15
0x18000d68e  sub     rsp, 40h
0x18000d692  mov     rsi, rdx
0x18000d695  mov     rbx, rcx
0x18000d698  xor     edi, edi
0x18000d69a  mov     [rsp+58h+arg_0], edi
0x18000d69e  lea     r15, WPP_GLOBAL_Control
0x18000d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6ac  cmp     rcx, r15
0x18000d6af  jz      short loc_18000D6D5
0x18000d6b1  test    dword ptr [rcx+1Ch], 1000h
0x18000d6b8  jz      short loc_18000D6D5
0x18000d6ba  cmp     byte ptr [rcx+19h], 5
0x18000d6be  jb      short loc_18000D6D5
0x18000d6c0  mov     edx, 0B0h
0x18000d6c5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d6cc  mov     rcx, [rcx+10h]
0x18000d6d0  call    WPP_SF_
0x18000d6d5  test    rbx, rbx
0x18000d6d8  jz      loc_18000D8A7
0x18000d6de  cmp     [rbx], edi
0x18000d6e0  jz      loc_18000D8A7
0x18000d6e6  cmp     [rbx+10h], edi
0x18000d6e9  jnz     loc_18000D8A7
0x18000d6ef  test    rsi, rsi
0x18000d6f2  jnz     short loc_18000D734
0x18000d6f4  lea     ecx, [rsi+57h]; dwErrCode
0x18000d6f7  call    cs:__imp_SetLastError
0x18000d6fe  nop     dword ptr [rax+rax+00h]
0x18000d703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d70a  cmp     rcx, r15
0x18000d70d  jz      loc_18000D8E8
0x18000d713  test    dword ptr [rcx+1Ch], 1000h
0x18000d71a  jz      loc_18000D8E8
0x18000d720  cmp     byte ptr [rcx+19h], 2
0x18000d724  jb      loc_18000D8E8
0x18000d72a  mov     edx, 0B2h
0x18000d72f  jmp     loc_18000D8D8
0x18000d734  mov     [rsi], rdi
0x18000d737  mov     rax, [rbx+20h]
0x18000d73b  mov     [rsp+58h+arg_10], rdi
0x18000d740  lea     rcx, [rsp+58h+arg_0]
0x18000d745  mov     [rsp+58h+var_30], rcx
0x18000d74a  mov     [rsp+58h+var_38], rsi
0x18000d74f  mov     r9, [rax]
0x18000d752  xor     r8d, r8d; pReturnValue
0x18000d755  lea     edx, [r8+2Bh]; nProcNum
0x18000d759  lea     rcx, pProxyInfo; pProxyInfo
0x18000d760  call    cs:__imp_NdrClientCall3
0x18000d767  nop     dword ptr [rax+rax+00h]
0x18000d76c  mov     rbx, rax
0x18000d76f  mov     [rsp+58h+arg_10], rax
0x18000d774  mov     [rsp+58h+var_28], eax
0x18000d778  jmp     short loc_18000D7C8
0x18000d77a  mov     ebx, eax
0x18000d77c  mov     [rsp+58h+var_28], eax
0x18000d780  lea     rdx, WPP_GLOBAL_Control
0x18000d787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d78e  cmp     rcx, rdx
0x18000d791  jz      short loc_18000D7BA
0x18000d793  test    dword ptr [rcx+1Ch], 1000h
0x18000d79a  jz      short loc_18000D7BA
0x18000d79c  cmp     byte ptr [rcx+19h], 2
0x18000d7a0  jb      short loc_18000D7BA
0x18000d7a2  mov     edx, 0B3h
0x18000d7a7  mov     r9d, eax
0x18000d7aa  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d7b1  mov     rcx, [rcx+10h]
0x18000d7b5  call    WPP_SF_d
0x18000d7ba  xor     edi, edi
0x18000d7bc  lea     r15, WPP_GLOBAL_Control
0x18000d7c3  mov     rsi, [rsp+58h+arg_8]
0x18000d7c8  test    ebx, ebx
0x18000d7ca  jz      short loc_18000D7DF
0x18000d7cc  mov     ecx, ebx; dwErrCode
0x18000d7ce  call    cs:__imp_SetLastError
0x18000d7d5  nop     dword ptr [rax+rax+00h]
0x18000d7da  jmp     loc_18000D8E8
0x18000d7df  mov     ebx, 1
0x18000d7e4  mov     dword ptr [rsp+58h+var_30], ebx
0x18000d7e8  mov     dword ptr [rsp+58h+var_38], ebx
0x18000d7ec  lea     r9d, [rbx+17h]
0x18000d7f0  lea     r8, ?fax_activity_logging_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_activity_logging_config_fields
0x18000d7f7  lea     rdx, [rsp+58h+arg_0]
0x18000d7fc  mov     rcx, rsi
0x18000d7ff  call    MarshallUpStructure
0x18000d804  test    eax, eax
0x18000d806  jnz     short loc_18000D859
0x18000d808  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d80f  cmp     rcx, r15
0x18000d812  jz      short loc_18000D838
0x18000d814  test    dword ptr [rcx+1Ch], 1000h
0x18000d81b  jz      short loc_18000D838
0x18000d81d  cmp     byte ptr [rcx+19h], 2
0x18000d821  jb      short loc_18000D838
0x18000d823  mov     edx, 0B4h
0x18000d828  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d82f  mov     rcx, [rcx+10h]
0x18000d833  call    WPP_SF_
0x18000d838  mov     ecx, 54Fh; dwErrCode
0x18000d83d  call    cs:__imp_SetLastError
0x18000d844  nop     dword ptr [rax+rax+00h]
0x18000d849  mov     rcx, [rsi]; lpMem
0x18000d84c  call    pMemFree
0x18000d851  mov     [rsi], rdi
0x18000d854  jmp     loc_18000D8E8
0x18000d859  mov     rdx, [rsi]
0x18000d85c  mov     rcx, [rdx+10h]
0x18000d860  mov     r8d, [rsp+58h+arg_0]
0x18000d865  cmp     rcx, r8
0x18000d868  ja      short loc_18000D8E8
0x18000d86a  test    rcx, rcx
0x18000d86d  jz      short loc_18000D87C
0x18000d86f  lea     rax, [rcx+rdx]
0x18000d873  mov     [rdx+10h], rax
0x18000d877  mov     r8d, [rsp+58h+arg_0]
0x18000d87c  mov     rdx, [rsi]
0x18000d87f  mov     rcx, [rdx+10h]
0x18000d883  test    rcx, rcx
0x18000d886  jz      short loc_18000D8A3
0x18000d888  mov     eax, edx
0x18000d88a  sub     eax, ecx
0x18000d88c  add     eax, r8d
0x18000d88f  shr     eax, 1
0x18000d891  jz      short loc_18000D8E8
0x18000d893  cmp     di, [rcx]
0x18000d896  jz      short loc_18000D8A3
0x18000d898  add     rcx, 2
0x18000d89c  add     eax, 0FFFFFFFFh
0x18000d89f  jnz     short loc_18000D893
0x18000d8a1  jmp     short loc_18000D8E8
0x18000d8a3  mov     eax, ebx
0x18000d8a5  jmp     short loc_18000D8EA
0x18000d8a7  mov     ecx, 6; dwErrCode
0x18000d8ac  call    cs:__imp_SetLastError
0x18000d8b3  nop     dword ptr [rax+rax+00h]
0x18000d8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8bf  cmp     rcx, r15
0x18000d8c2  jz      short loc_18000D8E8
0x18000d8c4  test    dword ptr [rcx+1Ch], 1000h
0x18000d8cb  jz      short loc_18000D8E8
0x18000d8cd  cmp     byte ptr [rcx+19h], 2
0x18000d8d1  jb      short loc_18000D8E8
0x18000d8d3  mov     edx, 0B1h
0x18000d8d8  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d8df  mov     rcx, [rcx+10h]
0x18000d8e3  call    WPP_SF_
0x18000d8e8  xor     eax, eax
0x18000d8ea  mov     rbx, [rsp+58h+arg_18]
0x18000d8ef  add     rsp, 40h
0x18000d8f3  pop     r15
0x18000d8f5  pop     rdi
0x18000d8f6  pop     rsi
0x18000d8f7  retn
```
