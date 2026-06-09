# FaxRegisterServiceProviderExW

- ea: `0x180029e10`
- end: `0x18002a05d`
- name: `FaxRegisterServiceProviderExW`
- size: `589`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, LPCOLESTR lpsz@<rdx>, __int64, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180029bd0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180027b70`
- `0x180029e10`
- `0x18002a52c`
- `0x18002c31c`
- `0x18002f7b0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180029f5e`
- `RPCRT4!NdrClientCall3` at `0x180029f5e`
- `KERNEL32!SetLastError` at `0x180029ef5`
- `KERNEL32!SetLastError` at `0x18002a013`
- `KERNEL32!SetLastError` at `0x180029ef5`
- `KERNEL32!SetLastError` at `0x18002a013`

## pseudocode

```c
__int64 __fastcall FaxRegisterServiceProviderExW(
        _DWORD *a1,
        LPCOLESTR lpsz,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 *a5,
        int a6,
        int a7)
{
  _QWORD *v11; // rcx
  DWORD valid; // r14d
  DWORD v13; // ecx
  const unsigned __int16 *v14; // rcx
  unsigned int Pointer; // eax

  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    }
    return 0;
  }
  if ( a6 != 0x10000 || a7 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x1000) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_DD(v11[2]);
    return 87;
  }
  else
  {
    valid = IsValidGUID(lpsz);
    if ( valid )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, valid);
      }
      v13 = valid;
      goto LABEL_16;
    }
    v14 = a5;
    if ( !a5 )
      v14 = &qword_1800435E8;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x3Cu,
                              0,
                              **((_QWORD **)a1 + 4),
                              lpsz,
                              a3,
                              a4,
                              v14,
                              0x10000,
                              0).Pointer;
    if ( Pointer )
    {
      v13 = Pointer;
LABEL_16:
      SetLastError(v13);
      return 0;
    }
    if ( (unsigned int)IsLocalFaxConnection(a1) )
      AddOrVerifyLocalFaxPrinter();
    return 1;
  }
}

```

## disassembly

```asm
0x180029e10  mov     [rsp+arg_0], rcx
0x180029e15  push    rbx
0x180029e16  push    rsi
0x180029e17  push    r12
0x180029e19  push    r13
0x180029e1b  push    r14
0x180029e1d  push    r15
0x180029e1f  sub     rsp, 68h
0x180029e23  mov     r12, r9
0x180029e26  mov     r13, r8
0x180029e29  mov     r15, rdx
0x180029e2c  mov     rsi, rcx
0x180029e2f  lea     r14, WPP_GLOBAL_Control
0x180029e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e3d  mov     ebx, 1000h
0x180029e42  cmp     rcx, r14
0x180029e45  jz      short loc_180029E6E
0x180029e47  test    [rcx+1Ch], ebx
0x180029e4a  jz      short loc_180029E6E
0x180029e4c  cmp     byte ptr [rcx+19h], 5
0x180029e50  jb      short loc_180029E6E
0x180029e52  mov     edx, 38h ; '8'
0x180029e57  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180029e5e  mov     rcx, [rcx+10h]
0x180029e62  call    WPP_SF_
0x180029e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e6e  test    rsi, rsi
0x180029e71  jz      loc_18002A00E
0x180029e77  cmp     dword ptr [rsi], 0
0x180029e7a  jz      loc_18002A00E
0x180029e80  cmp     dword ptr [rsi+10h], 0
0x180029e84  jnz     loc_18002A00E
0x180029e8a  mov     r9d, [rsp+98h+arg_28]
0x180029e92  cmp     r9d, 10000h
0x180029e99  jnz     loc_180029FE3
0x180029e9f  cmp     [rsp+98h+arg_30], 0
0x180029ea7  jnz     loc_180029FE3
0x180029ead  mov     rcx, r15; lpsz
0x180029eb0  call    IsValidGUID
0x180029eb5  mov     r14d, eax
0x180029eb8  test    eax, eax
0x180029eba  jz      short loc_180029F06
0x180029ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ec3  lea     rax, WPP_GLOBAL_Control
0x180029eca  cmp     rcx, rax
0x180029ecd  jz      short loc_180029EF2
0x180029ecf  test    [rcx+1Ch], ebx
0x180029ed2  jz      short loc_180029EF2
0x180029ed4  cmp     byte ptr [rcx+19h], 2
0x180029ed8  jb      short loc_180029EF2
0x180029eda  mov     edx, 3Bh ; ';'
0x180029edf  mov     r9d, r14d
0x180029ee2  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180029ee9  mov     rcx, [rcx+10h]
0x180029eed  call    WPP_SF_d
0x180029ef2  mov     ecx, r14d; dwErrCode
0x180029ef5  call    cs:__imp_SetLastError
0x180029efc  nop     dword ptr [rax+rax+00h]
0x180029f01  jmp     loc_18002A04B
0x180029f06  mov     rcx, [rsp+98h+arg_20]
0x180029f0e  lea     rax, qword_1800435E8
0x180029f15  test    rcx, rcx
0x180029f18  cmovz   rcx, rax
0x180029f1c  mov     rax, [rsi+20h]
0x180029f20  mov     [rsp+98h+var_40], 0
0x180029f29  mov     [rsp+98h+var_50], 0
0x180029f31  mov     [rsp+98h+var_58], 10000h
0x180029f39  mov     [rsp+98h+var_60], rcx
0x180029f3e  mov     [rsp+98h+var_68], r12
0x180029f43  mov     [rsp+98h+var_70], r13
0x180029f48  mov     [rsp+98h+var_78], r15
0x180029f4d  mov     r9, [rax]
0x180029f50  xor     r8d, r8d; pReturnValue
0x180029f53  lea     edx, [r8+3Ch]; nProcNum
0x180029f57  lea     rcx, pProxyInfo; pProxyInfo
0x180029f5e  call    cs:__imp_NdrClientCall3
0x180029f65  nop     dword ptr [rax+rax+00h]
0x180029f6a  mov     rbx, rax
0x180029f6d  mov     [rsp+98h+var_40], rax
0x180029f72  mov     [rsp+98h+var_48], eax
0x180029f76  jmp     short loc_180029FC0
0x180029f78  mov     ebx, eax
0x180029f7a  mov     [rsp+98h+var_48], eax
0x180029f7e  lea     rdx, WPP_GLOBAL_Control
0x180029f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f8c  cmp     rcx, rdx
0x180029f8f  jz      short loc_180029FB8
0x180029f91  test    dword ptr [rcx+1Ch], 1000h
0x180029f98  jz      short loc_180029FB8
0x180029f9a  cmp     byte ptr [rcx+19h], 2
0x180029f9e  jb      short loc_180029FB8
0x180029fa0  mov     edx, 3Ch ; '<'
0x180029fa5  mov     r9d, eax
0x180029fa8  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180029faf  mov     rcx, [rcx+10h]
0x180029fb3  call    WPP_SF_d
0x180029fb8  mov     rsi, [rsp+98h+arg_0]
0x180029fc0  test    ebx, ebx
0x180029fc2  jz      short loc_180029FCB
0x180029fc4  mov     ecx, ebx
0x180029fc6  jmp     loc_180029EF5
0x180029fcb  mov     rcx, rsi; void *
0x180029fce  call    ?IsLocalFaxConnection@@YAHPEAX@Z; IsLocalFaxConnection(void *)
0x180029fd3  test    eax, eax
0x180029fd5  jz      short loc_180029FDC
0x180029fd7  call    AddOrVerifyLocalFaxPrinter
0x180029fdc  mov     eax, 1
0x180029fe1  jmp     short loc_18002A04D
0x180029fe3  cmp     rcx, r14
0x180029fe6  jz      short loc_18002A007
0x180029fe8  test    [rcx+1Ch], ebx
0x180029feb  jz      short loc_18002A007
0x180029fed  cmp     byte ptr [rcx+19h], 2
0x180029ff1  jb      short loc_18002A007
0x180029ff3  mov     eax, [rsp+98h+arg_30]
0x180029ffa  mov     dword ptr [rsp+98h+var_78], eax
0x180029ffe  mov     rcx, [rcx+10h]
0x18002a002  call    WPP_SF_DD
0x18002a007  mov     eax, 57h ; 'W'
0x18002a00c  jmp     short loc_18002A04D
0x18002a00e  mov     ecx, 6; dwErrCode
0x18002a013  call    cs:__imp_SetLastError
0x18002a01a  nop     dword ptr [rax+rax+00h]
0x18002a01f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a026  cmp     rcx, r14
0x18002a029  jz      short loc_18002A04B
0x18002a02b  test    [rcx+1Ch], ebx
0x18002a02e  jz      short loc_18002A04B
0x18002a030  cmp     byte ptr [rcx+19h], 2
0x18002a034  jb      short loc_18002A04B
0x18002a036  mov     edx, 39h ; '9'
0x18002a03b  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a042  mov     rcx, [rcx+10h]
0x18002a046  call    WPP_SF_
0x18002a04b  xor     eax, eax
0x18002a04d  add     rsp, 68h
0x18002a051  pop     r15
0x18002a053  pop     r14
0x18002a055  pop     r13
0x18002a057  pop     r12
0x18002a059  pop     rsi
0x18002a05a  pop     rbx
0x18002a05b  retn
```
