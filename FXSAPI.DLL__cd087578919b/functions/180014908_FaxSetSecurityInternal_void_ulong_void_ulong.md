# FaxSetSecurityInternal(void *,ulong,void *,ulong)

- ea: `0x180014908`
- end: `0x180014d1b`
- name: `?FaxSetSecurityInternal@@YAHPEAXK0K@Z`
- size: `1043`
- prototype: `int(void *, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800160f0`
- `0x180016110`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014908`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014c1b`
- `RPCRT4!NdrClientCall3` at `0x180014c59`
- `RPCRT4!NdrClientCall3` at `0x180014c1b`
- `RPCRT4!NdrClientCall3` at `0x180014c59`
- `KERNEL32!SetLastError` at `0x180014989`
- `KERNEL32!SetLastError` at `0x1800149d3`
- `KERNEL32!SetLastError` at `0x180014a21`
- `KERNEL32!SetLastError` at `0x180014a79`
- `KERNEL32!SetLastError` at `0x180014b7a`
- `KERNEL32!SetLastError` at `0x180014cca`
- `KERNEL32!SetLastError` at `0x180014989`
- `KERNEL32!SetLastError` at `0x1800149d3`
- `KERNEL32!SetLastError` at `0x180014a21`
- `KERNEL32!SetLastError` at `0x180014a79`
- `KERNEL32!SetLastError` at `0x180014b7a`
- `KERNEL32!SetLastError` at `0x180014cca`
- `KERNEL32!GetLastError` at `0x180014b03`
- `KERNEL32!GetLastError` at `0x180014b03`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180014b8e`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180014b8e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180014ac9`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180014ac9`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180014a64`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180014a64`

## pseudocode

```c
__int64 __fastcall FaxSetSecurityInternal(_DWORD *a1, int a2, void *a3, unsigned int a4)
{
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  DWORD v11; // ecx
  DWORD SecurityDescriptorLength; // ecx
  int Pointer; // ebx
  _QWORD *v14; // rax
  CLIENT_CALL_RETURN v15; // rax
  _QWORD *v16; // rax
  DWORD dwRevision; // [rsp+44h] [rbp-54h] BYREF
  CLIENT_CALL_RETURN v19; // [rsp+48h] [rbp-50h]
  CLIENT_CALL_RETURN v20; // [rsp+50h] [rbp-48h]
  WORD pControl; // [rsp+A0h] [rbp+8h] BYREF

  dwRevision = 0;
  pControl = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 52;
LABEL_56:
    WPP_SF_(v8[2], v9, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
    return 0;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 53;
    goto LABEL_56;
  }
  if ( (a2 & 0xF) == 0 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 54;
    goto LABEL_56;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 55;
    goto LABEL_56;
  }
  if ( !IsValidSecurityDescriptor(a3) )
  {
    SetLastError(0x53Au);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 56;
    goto LABEL_56;
  }
  if ( GetSecurityDescriptorControl(a3, &pControl, &dwRevision) )
  {
    if ( (pControl & 0x8000u) != 0 )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(a3);
      if ( a4 == 0x20000 )
      {
        v16 = (_QWORD *)*((_QWORD *)a1 + 4);
        v20.Simple = 0;
        v20.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                        0x18u,
                        0,
                        *v16,
                        a2,
                        a3,
                        SecurityDescriptorLength).Pointer;
        Pointer = (int)v20.Pointer;
      }
      else if ( a4 == 196608 )
      {
        v14 = (_QWORD *)*((_QWORD *)a1 + 4);
        v19.Simple = 0;
        v15.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                        0x64u,
                        0,
                        *v14,
                        a2,
                        a3,
                        SecurityDescriptorLength).Pointer;
        Pointer = (int)v15.Pointer;
        v19.Pointer = v15.Pointer;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids, a4);
        }
        Pointer = 668;
      }
      if ( !Pointer )
        return 1;
      v11 = Pointer;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
      }
      v11 = 1338;
    }
    SetLastError(v11);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180014908  mov     rax, rsp
0x18001490b  push    rbx
0x18001490c  push    rsi
0x18001490d  push    r12
0x18001490f  push    r13
0x180014911  push    r14
0x180014913  push    r15
0x180014915  sub     rsp, 68h
0x180014919  mov     r12d, r9d
0x18001491c  mov     r14, r8
0x18001491f  mov     r13d, edx
0x180014922  mov     r15, rcx
0x180014925  xor     esi, esi
0x180014927  mov     [rax-54h], esi
0x18001492a  mov     [rax+8], si
0x18001492e  lea     rax, WPP_GLOBAL_Control
0x180014935  mov     rcx, cs:WPP_GLOBAL_Control
0x18001493c  mov     ebx, 1000h
0x180014941  cmp     rcx, rax
0x180014944  jz      short loc_180014964
0x180014946  test    [rcx+1Ch], ebx
0x180014949  jz      short loc_180014964
0x18001494b  cmp     byte ptr [rcx+19h], 5
0x18001494f  jb      short loc_180014964
0x180014951  lea     edx, [rsi+33h]
0x180014954  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x18001495b  mov     rcx, [rcx+10h]
0x18001495f  call    WPP_SF_
0x180014964  test    r15, r15
0x180014967  jz      loc_180014CC5
0x18001496d  cmp     [r15], esi
0x180014970  jz      loc_180014CC5
0x180014976  cmp     [r15+10h], esi
0x18001497a  jnz     loc_180014CC5
0x180014980  test    r14, r14
0x180014983  jnz     short loc_1800149C8
0x180014985  lea     ecx, [r14+57h]; dwErrCode
0x180014989  call    cs:__imp_SetLastError
0x180014990  nop     dword ptr [rax+rax+00h]
0x180014995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001499c  lea     rdx, WPP_GLOBAL_Control
0x1800149a3  cmp     rcx, rdx
0x1800149a6  jz      loc_180014D09
0x1800149ac  test    [rcx+1Ch], ebx
0x1800149af  jz      loc_180014D09
0x1800149b5  cmp     byte ptr [rcx+19h], 2
0x1800149b9  jb      loc_180014D09
0x1800149bf  lea     edx, [r14+35h]
0x1800149c3  jmp     loc_180014CF9
0x1800149c8  test    r13b, 0Fh
0x1800149cc  jnz     short loc_180014A13
0x1800149ce  mov     ecx, 57h ; 'W'; dwErrCode
0x1800149d3  call    cs:__imp_SetLastError
0x1800149da  nop     dword ptr [rax+rax+00h]
0x1800149df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149e6  lea     rdx, WPP_GLOBAL_Control
0x1800149ed  cmp     rcx, rdx
0x1800149f0  jz      loc_180014D09
0x1800149f6  test    [rcx+1Ch], ebx
0x1800149f9  jz      loc_180014D09
0x1800149ff  cmp     byte ptr [rcx+19h], 2
0x180014a03  jb      loc_180014D09
0x180014a09  mov     edx, 36h ; '6'
0x180014a0e  jmp     loc_180014CF9
0x180014a13  test    r13d, 0FFFFFFF0h
0x180014a1a  jz      short loc_180014A61
0x180014a1c  mov     ecx, 57h ; 'W'; dwErrCode
0x180014a21  call    cs:__imp_SetLastError
0x180014a28  nop     dword ptr [rax+rax+00h]
0x180014a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a34  lea     rdx, WPP_GLOBAL_Control
0x180014a3b  cmp     rcx, rdx
0x180014a3e  jz      loc_180014D09
0x180014a44  test    [rcx+1Ch], ebx
0x180014a47  jz      loc_180014D09
0x180014a4d  cmp     byte ptr [rcx+19h], 2
0x180014a51  jb      loc_180014D09
0x180014a57  mov     edx, 37h ; '7'
0x180014a5c  jmp     loc_180014CF9
0x180014a61  mov     rcx, r14; pSecurityDescriptor
0x180014a64  call    cs:__imp_IsValidSecurityDescriptor
0x180014a6b  nop     dword ptr [rax+rax+00h]
0x180014a70  test    eax, eax
0x180014a72  jnz     short loc_180014AB9
0x180014a74  mov     ecx, 53Ah; dwErrCode
0x180014a79  call    cs:__imp_SetLastError
0x180014a80  nop     dword ptr [rax+rax+00h]
0x180014a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a8c  lea     rdx, WPP_GLOBAL_Control
0x180014a93  cmp     rcx, rdx
0x180014a96  jz      loc_180014D09
0x180014a9c  test    [rcx+1Ch], ebx
0x180014a9f  jz      loc_180014D09
0x180014aa5  cmp     byte ptr [rcx+19h], 2
0x180014aa9  jb      loc_180014D09
0x180014aaf  mov     edx, 38h ; '8'
0x180014ab4  jmp     loc_180014CF9
0x180014ab9  lea     r8, [rsp+98h+dwRevision]; lpdwRevision
0x180014abe  lea     rdx, [rsp+98h+pControl]; pControl
0x180014ac6  mov     rcx, r14; pSecurityDescriptor
0x180014ac9  call    cs:__imp_GetSecurityDescriptorControl
0x180014ad0  nop     dword ptr [rax+rax+00h]
0x180014ad5  test    eax, eax
0x180014ad7  jnz     short loc_180014B33
0x180014ad9  mov     rax, cs:WPP_GLOBAL_Control
0x180014ae0  lea     rdx, WPP_GLOBAL_Control
0x180014ae7  cmp     rax, rdx
0x180014aea  jz      loc_180014D09
0x180014af0  test    [rax+1Ch], ebx
0x180014af3  jz      loc_180014D09
0x180014af9  cmp     byte ptr [rax+19h], 2
0x180014afd  jb      loc_180014D09
0x180014b03  call    cs:__imp_GetLastError
0x180014b0a  nop     dword ptr [rax+rax+00h]
0x180014b0f  mov     edx, 39h ; '9'
0x180014b14  mov     r9d, eax
0x180014b17  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b25  mov     rcx, [rcx+10h]
0x180014b29  call    WPP_SF_d
0x180014b2e  jmp     loc_180014D09
0x180014b33  mov     eax, 8000h
0x180014b38  test    [rsp+98h+pControl], ax
0x180014b40  jnz     short loc_180014B8B
0x180014b42  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b49  lea     rdx, WPP_GLOBAL_Control
0x180014b50  cmp     rcx, rdx
0x180014b53  jz      short loc_180014B75
0x180014b55  test    [rcx+1Ch], ebx
0x180014b58  jz      short loc_180014B75
0x180014b5a  cmp     byte ptr [rcx+19h], 2
0x180014b5e  jb      short loc_180014B75
0x180014b60  mov     edx, 3Ah ; ':'
0x180014b65  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014b6c  mov     rcx, [rcx+10h]
0x180014b70  call    WPP_SF_
0x180014b75  mov     ecx, 53Ah; dwErrCode
0x180014b7a  call    cs:__imp_SetLastError
0x180014b81  nop     dword ptr [rax+rax+00h]
0x180014b86  jmp     loc_180014D09
0x180014b8b  mov     rcx, r14; pSecurityDescriptor
0x180014b8e  call    cs:__imp_GetSecurityDescriptorLength
0x180014b95  nop     dword ptr [rax+rax+00h]
0x180014b9a  mov     ecx, eax
0x180014b9c  cmp     r12d, 20000h
0x180014ba3  jz      loc_180014C31
0x180014ba9  cmp     r12d, 30000h
0x180014bb0  jz      short loc_180014BF3
0x180014bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bb9  lea     rdx, WPP_GLOBAL_Control
0x180014bc0  cmp     rcx, rdx
0x180014bc3  jz      short loc_180014BE8
0x180014bc5  test    [rcx+1Ch], ebx
0x180014bc8  jz      short loc_180014BE8
0x180014bca  cmp     byte ptr [rcx+19h], 2
0x180014bce  jb      short loc_180014BE8
0x180014bd0  mov     edx, 3Bh ; ';'
0x180014bd5  mov     r9d, r12d
0x180014bd8  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014bdf  mov     rcx, [rcx+10h]
0x180014be3  call    WPP_SF_d
0x180014be8  mov     ebx, 29Ch
0x180014bed  mov     [rsp+98h+var_58], ebx
0x180014bf1  jmp     short loc_180014C70
0x180014bf3  mov     rax, [r15+20h]
0x180014bf7  mov     [rsp+98h+var_50], rsi
0x180014bfc  mov     [rsp+98h+var_68], ecx
0x180014c00  mov     [rsp+98h+var_70], r14
0x180014c05  mov     [rsp+98h+var_78], r13d
0x180014c0a  mov     r9, [rax]
0x180014c0d  xor     r8d, r8d; pReturnValue
0x180014c10  lea     edx, [r8+64h]; nProcNum
0x180014c14  lea     rcx, pProxyInfo; pProxyInfo
0x180014c1b  call    cs:__imp_NdrClientCall3
0x180014c22  nop     dword ptr [rax+rax+00h]
0x180014c27  mov     rbx, rax
0x180014c2a  mov     [rsp+98h+var_50], rax
0x180014c2f  jmp     short loc_180014C6C
0x180014c31  mov     rax, [r15+20h]
0x180014c35  mov     [rsp+98h+var_48], rsi
0x180014c3a  mov     [rsp+98h+var_68], ecx
0x180014c3e  mov     [rsp+98h+var_70], r14
0x180014c43  mov     [rsp+98h+var_78], r13d
0x180014c48  mov     r9, [rax]
0x180014c4b  xor     r8d, r8d; pReturnValue
0x180014c4e  lea     edx, [r8+18h]; nProcNum
0x180014c52  lea     rcx, pProxyInfo; pProxyInfo
0x180014c59  call    cs:__imp_NdrClientCall3
0x180014c60  nop     dword ptr [rax+rax+00h]
0x180014c65  mov     [rsp+98h+var_48], rax
0x180014c6a  mov     ebx, eax
0x180014c6c  mov     [rsp+98h+var_58], eax
0x180014c70  jmp     short loc_180014CB3
0x180014c72  mov     ebx, eax
0x180014c74  mov     [rsp+98h+var_58], eax
0x180014c78  lea     rdx, WPP_GLOBAL_Control
0x180014c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c86  cmp     rcx, rdx
0x180014c89  jz      short loc_180014CB3
0x180014c8b  test    dword ptr [rcx+1Ch], 1000h
0x180014c92  jz      short loc_180014CB3
0x180014c94  cmp     byte ptr [rcx+19h], 2
0x180014c98  jb      short loc_180014CB3
0x180014c9a  mov     edx, 3Ch ; '<'
0x180014c9f  mov     r9d, eax
0x180014ca2  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014ca9  mov     rcx, [rcx+10h]
0x180014cad  call    WPP_SF_d
0x180014cb2  nop
0x180014cb3  test    ebx, ebx
0x180014cb5  jz      short loc_180014CBE
0x180014cb7  mov     ecx, ebx
0x180014cb9  jmp     loc_180014B7A
0x180014cbe  mov     eax, 1
0x180014cc3  jmp     short loc_180014D0B
0x180014cc5  mov     ecx, 6; dwErrCode
0x180014cca  call    cs:__imp_SetLastError
0x180014cd1  nop     dword ptr [rax+rax+00h]
0x180014cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cdd  lea     rdx, WPP_GLOBAL_Control
0x180014ce4  cmp     rcx, rdx
0x180014ce7  jz      short loc_180014D09
0x180014ce9  test    [rcx+1Ch], ebx
0x180014cec  jz      short loc_180014D09
0x180014cee  cmp     byte ptr [rcx+19h], 2
0x180014cf2  jb      short loc_180014D09
0x180014cf4  mov     edx, 34h ; '4'
0x180014cf9  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014d00  mov     rcx, [rcx+10h]
0x180014d04  call    WPP_SF_
0x180014d09  xor     eax, eax
0x180014d0b  add     rsp, 68h
0x180014d0f  pop     r15
0x180014d11  pop     r14
0x180014d13  pop     r13
0x180014d15  pop     r12
0x180014d17  pop     rsi
0x180014d18  pop     rbx
0x180014d19  retn
```
