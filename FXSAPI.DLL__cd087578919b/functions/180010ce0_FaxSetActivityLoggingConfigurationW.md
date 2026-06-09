# FaxSetActivityLoggingConfigurationW

- ea: `0x180010ce0`
- end: `0x180010f71`
- name: `FaxSetActivityLoggingConfigurationW`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010b20`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180010ce0`
- `0x180033d10`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010e7b`
- `RPCRT4!NdrClientCall3` at `0x180010e7b`
- `KERNEL32!SetLastError` at `0x180010d5e`
- `KERNEL32!SetLastError` at `0x180010da1`
- `KERNEL32!SetLastError` at `0x180010e3d`
- `KERNEL32!SetLastError` at `0x180010f22`
- `KERNEL32!SetLastError` at `0x180010d5e`
- `KERNEL32!SetLastError` at `0x180010da1`
- `KERNEL32!SetLastError` at `0x180010e3d`
- `KERNEL32!SetLastError` at `0x180010f22`

## pseudocode

```c
__int64 __fastcall FaxSetActivityLoggingConfigurationW(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // rax
  __int64 v8; // rdx
  DWORD v9; // ecx
  unsigned int Pointer; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 187;
LABEL_44:
    WPP_SF_(v5[2], v6, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 188;
    goto LABEL_44;
  }
  if ( *(_DWORD *)a2 != 24 )
  {
    SetLastError(0x57u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 189;
    goto LABEL_44;
  }
  if ( !*(_DWORD *)(a2 + 4) && !*(_DWORD *)(a2 + 8) )
    goto LABEL_32;
  v7 = *(_WORD **)(a2 + 16);
  if ( !v7 || !*v7 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 190, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v9 = 87;
    goto LABEL_31;
  }
  v8 = 249;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  if ( v8 )
  {
LABEL_32:
    *(_DWORD *)a2 = GetWin32StructSize(&fax_activity_logging_config_fields);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x2Cu,
                              0,
                              **(_QWORD **)(a1 + 32),
                              a2).Pointer;
    *(_DWORD *)a2 = 24;
    if ( !Pointer )
      return 1;
    v9 = Pointer;
    goto LABEL_31;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    WPP_SF_(v4[2], 191, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  v9 = 111;
LABEL_31:
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x180010ce0  mov     [rsp+arg_8], rbx
0x180010ce5  mov     [rsp+arg_10], rsi
0x180010cea  push    rdi
0x180010ceb  push    r14
0x180010ced  push    r15
0x180010cef  sub     rsp, 40h
0x180010cf3  mov     rsi, rdx
0x180010cf6  mov     r14, rcx
0x180010cf9  lea     r15, WPP_GLOBAL_Control
0x180010d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d07  mov     ebx, 1000h
0x180010d0c  cmp     rcx, r15
0x180010d0f  jz      short loc_180010D38
0x180010d11  test    [rcx+1Ch], ebx
0x180010d14  jz      short loc_180010D38
0x180010d16  cmp     byte ptr [rcx+19h], 5
0x180010d1a  jb      short loc_180010D38
0x180010d1c  mov     edx, 0BAh
0x180010d21  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010d28  mov     rcx, [rcx+10h]
0x180010d2c  call    WPP_SF_
0x180010d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d38  xor     edi, edi
0x180010d3a  test    r14, r14
0x180010d3d  jz      loc_180010F1D
0x180010d43  cmp     [r14], edi
0x180010d46  jz      loc_180010F1D
0x180010d4c  cmp     [r14+10h], edi
0x180010d50  jnz     loc_180010F1D
0x180010d56  test    rsi, rsi
0x180010d59  jnz     short loc_180010D97
0x180010d5b  lea     ecx, [rdi+57h]; dwErrCode
0x180010d5e  call    cs:__imp_SetLastError
0x180010d65  nop     dword ptr [rax+rax+00h]
0x180010d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d71  cmp     rcx, r15
0x180010d74  jz      loc_180010F5A
0x180010d7a  test    [rcx+1Ch], ebx
0x180010d7d  jz      loc_180010F5A
0x180010d83  cmp     byte ptr [rcx+19h], 2
0x180010d87  jb      loc_180010F5A
0x180010d8d  mov     edx, 0BCh
0x180010d92  jmp     loc_180010F4A
0x180010d97  cmp     dword ptr [rsi], 18h
0x180010d9a  jz      short loc_180010DDA
0x180010d9c  mov     ecx, 57h ; 'W'; dwErrCode
0x180010da1  call    cs:__imp_SetLastError
0x180010da8  nop     dword ptr [rax+rax+00h]
0x180010dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180010db4  cmp     rcx, r15
0x180010db7  jz      loc_180010F5A
0x180010dbd  test    [rcx+1Ch], ebx
0x180010dc0  jz      loc_180010F5A
0x180010dc6  cmp     byte ptr [rcx+19h], 2
0x180010dca  jb      loc_180010F5A
0x180010dd0  mov     edx, 0BDh
0x180010dd5  jmp     loc_180010F4A
0x180010dda  cmp     [rsi+4], edi
0x180010ddd  jnz     short loc_180010DE4
0x180010ddf  cmp     [rsi+8], edi
0x180010de2  jz      short loc_180010E4E
0x180010de4  mov     rax, [rsi+10h]
0x180010de8  test    rax, rax
0x180010deb  jz      loc_180010EEE
0x180010df1  cmp     di, [rax]
0x180010df4  jz      loc_180010EEE
0x180010dfa  mov     edx, 0F9h
0x180010dff  cmp     [rax], di
0x180010e02  jz      short loc_180010E0E
0x180010e04  add     rax, 2
0x180010e08  sub     rdx, 1
0x180010e0c  jnz     short loc_180010DFF
0x180010e0e  test    rdx, rdx
0x180010e11  jnz     short loc_180010E4E
0x180010e13  cmp     rcx, r15
0x180010e16  jz      short loc_180010E38
0x180010e18  test    [rcx+1Ch], ebx
0x180010e1b  jz      short loc_180010E38
0x180010e1d  cmp     byte ptr [rcx+19h], 2
0x180010e21  jb      short loc_180010E38
0x180010e23  mov     edx, 0BFh
0x180010e28  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010e2f  mov     rcx, [rcx+10h]
0x180010e33  call    WPP_SF_
0x180010e38  mov     ecx, 6Fh ; 'o'; dwErrCode
0x180010e3d  call    cs:__imp_SetLastError
0x180010e44  nop     dword ptr [rax+rax+00h]
0x180010e49  jmp     loc_180010F5A
0x180010e4e  lea     rcx, ?fax_activity_logging_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_activity_logging_config_fields
0x180010e55  call    GetWin32StructSize
0x180010e5a  mov     [rsi], eax
0x180010e5c  mov     rax, [r14+20h]
0x180010e60  mov     [rsp+58h+arg_0], rdi
0x180010e65  mov     [rsp+58h+var_38], rsi
0x180010e6a  mov     r9, [rax]
0x180010e6d  xor     r8d, r8d; pReturnValue
0x180010e70  lea     edx, [r8+2Ch]; nProcNum
0x180010e74  lea     rcx, pProxyInfo; pProxyInfo
0x180010e7b  call    cs:__imp_NdrClientCall3
0x180010e82  nop     dword ptr [rax+rax+00h]
0x180010e87  mov     rbx, rax
0x180010e8a  mov     [rsp+58h+arg_0], rax
0x180010e8f  mov     [rsp+58h+var_28], eax
0x180010e93  mov     dword ptr [rsi], 18h
0x180010e99  jmp     short loc_180010EDC
0x180010e9b  mov     ebx, eax
0x180010e9d  mov     [rsp+58h+var_28], eax
0x180010ea1  lea     rdx, WPP_GLOBAL_Control
0x180010ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010eaf  cmp     rcx, rdx
0x180010eb2  jz      short loc_180010EDC
0x180010eb4  test    dword ptr [rcx+1Ch], 1000h
0x180010ebb  jz      short loc_180010EDC
0x180010ebd  cmp     byte ptr [rcx+19h], 2
0x180010ec1  jb      short loc_180010EDC
0x180010ec3  mov     edx, 0C0h
0x180010ec8  mov     r9d, eax
0x180010ecb  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010ed2  mov     rcx, [rcx+10h]
0x180010ed6  call    WPP_SF_d
0x180010edb  nop
0x180010edc  test    ebx, ebx
0x180010ede  jz      short loc_180010EE7
0x180010ee0  mov     ecx, ebx
0x180010ee2  jmp     loc_180010E3D
0x180010ee7  mov     eax, 1
0x180010eec  jmp     short loc_180010F5C
0x180010eee  cmp     rcx, r15
0x180010ef1  jz      short loc_180010F13
0x180010ef3  test    [rcx+1Ch], ebx
0x180010ef6  jz      short loc_180010F13
0x180010ef8  cmp     byte ptr [rcx+19h], 2
0x180010efc  jb      short loc_180010F13
0x180010efe  mov     edx, 0BEh
0x180010f03  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010f0a  mov     rcx, [rcx+10h]
0x180010f0e  call    WPP_SF_
0x180010f13  mov     ecx, 57h ; 'W'
0x180010f18  jmp     loc_180010E3D
0x180010f1d  mov     ecx, 6; dwErrCode
0x180010f22  call    cs:__imp_SetLastError
0x180010f29  nop     dword ptr [rax+rax+00h]
0x180010f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f35  cmp     rcx, r15
0x180010f38  jz      short loc_180010F5A
0x180010f3a  test    [rcx+1Ch], ebx
0x180010f3d  jz      short loc_180010F5A
0x180010f3f  cmp     byte ptr [rcx+19h], 2
0x180010f43  jb      short loc_180010F5A
0x180010f45  mov     edx, 0BBh
0x180010f4a  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010f51  mov     rcx, [rcx+10h]
0x180010f55  call    WPP_SF_
0x180010f5a  xor     eax, eax
0x180010f5c  mov     rbx, [rsp+58h+arg_8]
0x180010f61  mov     rsi, [rsp+58h+arg_10]
0x180010f66  add     rsp, 40h
0x180010f6a  pop     r15
0x180010f6c  pop     r14
0x180010f6e  pop     rdi
0x180010f6f  retn
```
