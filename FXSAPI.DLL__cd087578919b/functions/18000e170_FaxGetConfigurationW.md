# FaxGetConfigurationW

- ea: `0x18000e170`
- end: `0x18000e3eb`
- name: `FaxGetConfigurationW`
- size: `635`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, PFAX_CONFIGURATIONW *FaxConfig)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e040`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000e170`
- `0x18002bb58`
- `0x180034538`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e24c`
- `RPCRT4!NdrClientCall3` at `0x18000e24c`
- `KERNEL32!SetLastError` at `0x18000e1e5`
- `KERNEL32!SetLastError` at `0x18000e2ba`
- `KERNEL32!SetLastError` at `0x18000e327`
- `KERNEL32!SetLastError` at `0x18000e39e`
- `KERNEL32!SetLastError` at `0x18000e1e5`
- `KERNEL32!SetLastError` at `0x18000e2ba`
- `KERNEL32!SetLastError` at `0x18000e327`
- `KERNEL32!SetLastError` at `0x18000e39e`

## pseudocode

```c
BOOL __stdcall FaxGetConfigurationW(HANDLE FaxHandle, PFAX_CONFIGURATIONW *FaxConfig)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  CLIENT_CALL_RETURN v7; // rax
  LPCWSTR ArchiveDirectory; // rcx
  unsigned int v9; // r8d
  PFAX_CONFIGURATIONW v10; // rdx
  LPCWSTR v11; // rcx
  unsigned int v12; // eax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  PFAX_CONFIGURATIONW *v15; // [rsp+68h] [rbp+10h]
  CLIENT_CALL_RETURN v16; // [rsp+70h] [rbp+18h]

  v15 = FaxConfig;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 11;
LABEL_34:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !FaxConfig )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 12;
    goto LABEL_34;
  }
  *FaxConfig = 0;
  v6 = (_QWORD *)*((_QWORD *)FaxHandle + 4);
  v16.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0, *v6, FaxConfig, &v14).Pointer;
  v16.Pointer = v7.Pointer;
  if ( LODWORD(v7.Pointer) )
  {
    SetLastError((DWORD)v7.Pointer);
  }
  else
  {
    if ( !(unsigned int)MarshallUpStructure(FaxConfig, &v14, &fax_configuration_fields, 64, 1, 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      SetLastError(0x54Fu);
      pMemFree(*FaxConfig);
      *FaxConfig = 0;
      return 0;
    }
    ArchiveDirectory = (*FaxConfig)->ArchiveDirectory;
    v9 = v14;
    if ( (unsigned __int64)ArchiveDirectory <= v14 )
    {
      if ( ArchiveDirectory )
      {
        (*FaxConfig)->ArchiveDirectory = (LPCWSTR)((char *)*FaxConfig + (_QWORD)ArchiveDirectory);
        v9 = v14;
      }
      v10 = *FaxConfig;
      v11 = (*FaxConfig)->ArchiveDirectory;
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
      v10->Reserved = 0;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e170  mov     [rsp+arg_18], rbx
0x18000e175  mov     [rsp+arg_8], rdx
0x18000e17a  push    rsi
0x18000e17b  push    rdi
0x18000e17c  push    r15
0x18000e17e  sub     rsp, 40h
0x18000e182  mov     rsi, rdx
0x18000e185  mov     rbx, rcx
0x18000e188  xor     edi, edi
0x18000e18a  mov     [rsp+58h+arg_0], edi
0x18000e18e  lea     r15, WPP_GLOBAL_Control
0x18000e195  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e19c  cmp     rcx, r15
0x18000e19f  jz      short loc_18000E1C3
0x18000e1a1  test    dword ptr [rcx+1Ch], 1000h
0x18000e1a8  jz      short loc_18000E1C3
0x18000e1aa  cmp     byte ptr [rcx+19h], 5
0x18000e1ae  jb      short loc_18000E1C3
0x18000e1b0  lea     edx, [rdi+0Ah]
0x18000e1b3  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e1ba  mov     rcx, [rcx+10h]
0x18000e1be  call    WPP_SF_
0x18000e1c3  test    rbx, rbx
0x18000e1c6  jz      loc_18000E399
0x18000e1cc  cmp     [rbx], edi
0x18000e1ce  jz      loc_18000E399
0x18000e1d4  cmp     [rbx+10h], edi
0x18000e1d7  jnz     loc_18000E399
0x18000e1dd  test    rsi, rsi
0x18000e1e0  jnz     short loc_18000E220
0x18000e1e2  lea     ecx, [rsi+57h]; dwErrCode
0x18000e1e5  call    cs:__imp_SetLastError
0x18000e1ec  nop     dword ptr [rax+rax+00h]
0x18000e1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1f8  cmp     rcx, r15
0x18000e1fb  jz      loc_18000E3DA
0x18000e201  test    dword ptr [rcx+1Ch], 1000h
0x18000e208  jz      loc_18000E3DA
0x18000e20e  cmp     byte ptr [rcx+19h], 2
0x18000e212  jb      loc_18000E3DA
0x18000e218  lea     edx, [rsi+0Ch]
0x18000e21b  jmp     loc_18000E3CA
0x18000e220  mov     [rsi], rdi
0x18000e223  mov     rax, [rbx+20h]
0x18000e227  mov     [rsp+58h+arg_10], rdi
0x18000e22c  lea     rcx, [rsp+58h+arg_0]
0x18000e231  mov     [rsp+58h+var_30], rcx
0x18000e236  mov     [rsp+58h+var_38], rsi
0x18000e23b  mov     r9, [rax]
0x18000e23e  xor     r8d, r8d; pReturnValue
0x18000e241  lea     edx, [r8+13h]; nProcNum
0x18000e245  lea     rcx, pProxyInfo; pProxyInfo
0x18000e24c  call    cs:__imp_NdrClientCall3
0x18000e253  nop     dword ptr [rax+rax+00h]
0x18000e258  mov     rbx, rax
0x18000e25b  mov     [rsp+58h+arg_10], rax
0x18000e260  mov     [rsp+58h+var_28], eax
0x18000e264  jmp     short loc_18000E2B4
0x18000e266  mov     ebx, eax
0x18000e268  mov     [rsp+58h+var_28], eax
0x18000e26c  lea     rdx, WPP_GLOBAL_Control
0x18000e273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e27a  cmp     rcx, rdx
0x18000e27d  jz      short loc_18000E2A6
0x18000e27f  test    dword ptr [rcx+1Ch], 1000h
0x18000e286  jz      short loc_18000E2A6
0x18000e288  cmp     byte ptr [rcx+19h], 2
0x18000e28c  jb      short loc_18000E2A6
0x18000e28e  mov     edx, 0Dh
0x18000e293  mov     r9d, eax
0x18000e296  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e29d  mov     rcx, [rcx+10h]
0x18000e2a1  call    WPP_SF_d
0x18000e2a6  xor     edi, edi
0x18000e2a8  lea     r15, WPP_GLOBAL_Control
0x18000e2af  mov     rsi, [rsp+58h+arg_8]
0x18000e2b4  test    ebx, ebx
0x18000e2b6  jz      short loc_18000E2CB
0x18000e2b8  mov     ecx, ebx; dwErrCode
0x18000e2ba  call    cs:__imp_SetLastError
0x18000e2c1  nop     dword ptr [rax+rax+00h]
0x18000e2c6  jmp     loc_18000E3DA
0x18000e2cb  mov     ebx, 1
0x18000e2d0  mov     dword ptr [rsp+58h+var_30], ebx
0x18000e2d4  mov     dword ptr [rsp+58h+var_38], ebx
0x18000e2d8  lea     r9d, [rbx+3Fh]
0x18000e2dc  lea     r8, ?fax_configuration_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_configuration_fields
0x18000e2e3  lea     rdx, [rsp+58h+arg_0]
0x18000e2e8  mov     rcx, rsi
0x18000e2eb  call    MarshallUpStructure
0x18000e2f0  test    eax, eax
0x18000e2f2  jnz     short loc_18000E343
0x18000e2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2fb  cmp     rcx, r15
0x18000e2fe  jz      short loc_18000E322
0x18000e300  test    dword ptr [rcx+1Ch], 1000h
0x18000e307  jz      short loc_18000E322
0x18000e309  cmp     byte ptr [rcx+19h], 2
0x18000e30d  jb      short loc_18000E322
0x18000e30f  lea     edx, [rbx+0Dh]
0x18000e312  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e319  mov     rcx, [rcx+10h]
0x18000e31d  call    WPP_SF_
0x18000e322  mov     ecx, 54Fh; dwErrCode
0x18000e327  call    cs:__imp_SetLastError
0x18000e32e  nop     dword ptr [rax+rax+00h]
0x18000e333  mov     rcx, [rsi]; lpMem
0x18000e336  call    pMemFree
0x18000e33b  mov     [rsi], rdi
0x18000e33e  jmp     loc_18000E3DA
0x18000e343  mov     rdx, [rsi]
0x18000e346  mov     rcx, [rdx+30h]
0x18000e34a  mov     r8d, [rsp+58h+arg_0]
0x18000e34f  cmp     rcx, r8
0x18000e352  ja      loc_18000E3DA
0x18000e358  test    rcx, rcx
0x18000e35b  jz      short loc_18000E36A
0x18000e35d  lea     rax, [rcx+rdx]
0x18000e361  mov     [rdx+30h], rax
0x18000e365  mov     r8d, [rsp+58h+arg_0]
0x18000e36a  mov     rdx, [rsi]
0x18000e36d  mov     rcx, [rdx+30h]
0x18000e371  test    rcx, rcx
0x18000e374  jz      short loc_18000E391
0x18000e376  mov     eax, edx
0x18000e378  sub     eax, ecx
0x18000e37a  add     eax, r8d
0x18000e37d  shr     eax, 1
0x18000e37f  jz      short loc_18000E3DA
0x18000e381  cmp     di, [rcx]
0x18000e384  jz      short loc_18000E391
0x18000e386  add     rcx, 2
0x18000e38a  add     eax, 0FFFFFFFFh
0x18000e38d  jnz     short loc_18000E381
0x18000e38f  jmp     short loc_18000E3DA
0x18000e391  mov     [rdx+38h], rdi
0x18000e395  mov     eax, ebx
0x18000e397  jmp     short loc_18000E3DC
0x18000e399  mov     ecx, 6; dwErrCode
0x18000e39e  call    cs:__imp_SetLastError
0x18000e3a5  nop     dword ptr [rax+rax+00h]
0x18000e3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b1  cmp     rcx, r15
0x18000e3b4  jz      short loc_18000E3DA
0x18000e3b6  test    dword ptr [rcx+1Ch], 1000h
0x18000e3bd  jz      short loc_18000E3DA
0x18000e3bf  cmp     byte ptr [rcx+19h], 2
0x18000e3c3  jb      short loc_18000E3DA
0x18000e3c5  mov     edx, 0Bh
0x18000e3ca  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e3d1  mov     rcx, [rcx+10h]
0x18000e3d5  call    WPP_SF_
0x18000e3da  xor     eax, eax
0x18000e3dc  mov     rbx, [rsp+58h+arg_18]
0x18000e3e1  add     rsp, 40h
0x18000e3e5  pop     r15
0x18000e3e7  pop     rdi
0x18000e3e8  pop     rsi
0x18000e3e9  retn
```
