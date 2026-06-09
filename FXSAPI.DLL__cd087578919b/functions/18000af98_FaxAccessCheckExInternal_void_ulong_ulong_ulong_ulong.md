# FaxAccessCheckExInternal(void *,ulong,ulong *,ulong,ulong)

- ea: `0x18000af98`
- end: `0x18000b240`
- name: `?FaxAccessCheckExInternal@@YAHPEAXKPEAKKK@Z`
- size: `680`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000b3f0`
- `0x18000b470`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000af98`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b121`
- `RPCRT4!NdrClientCall3` at `0x18000b16c`
- `RPCRT4!NdrClientCall3` at `0x18000b121`
- `RPCRT4!NdrClientCall3` at `0x18000b16c`
- `KERNEL32!SetLastError` at `0x18000b025`
- `KERNEL32!SetLastError` at `0x18000b067`
- `KERNEL32!SetLastError` at `0x18000b1cc`
- `KERNEL32!SetLastError` at `0x18000b1dc`
- `KERNEL32!SetLastError` at `0x18000b1f6`
- `KERNEL32!SetLastError` at `0x18000b025`
- `KERNEL32!SetLastError` at `0x18000b067`
- `KERNEL32!SetLastError` at `0x18000b1cc`
- `KERNEL32!SetLastError` at `0x18000b1dc`
- `KERNEL32!SetLastError` at `0x18000b1f6`

## pseudocode

```c
__int64 __fastcall FaxAccessCheckExInternal(_DWORD *a1, int a2, unsigned int *a3, unsigned int a4, unsigned int a5)
{
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD Pointer; // ebx
  unsigned int v14; // [rsp+A0h] [rbp+8h] BYREF

  v14 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 92;
LABEL_34:
    WPP_SF_(v10[2], v11, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( (a2 & a5) == 0 )
  {
    SetLastError(0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 93;
    goto LABEL_34;
  }
  if ( (~a5 & a2) != 0 )
  {
    SetLastError(0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 94;
    goto LABEL_34;
  }
  if ( a4 == 0x20000 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x19u,
                              0,
                              **((_QWORD **)a1 + 4),
                              a2,
                              &v14,
                              a3).Pointer;
  }
  else if ( a4 == 196608 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x65u,
                              0,
                              **((_QWORD **)a1 + 4),
                              a2,
                              &v14,
                              a3).Pointer;
  }
  else
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x1000) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(v9[2], 95, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, a4);
    Pointer = 668;
  }
  if ( !Pointer )
  {
    SetLastError(0);
    return v14;
  }
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18000af98  mov     rax, rsp
0x18000af9b  push    rbx
0x18000af9c  push    rsi
0x18000af9d  push    r12
0x18000af9f  push    r13
0x18000afa1  push    r14
0x18000afa3  push    r15
0x18000afa5  sub     rsp, 68h
0x18000afa9  mov     r14d, r9d
0x18000afac  mov     r12, r8
0x18000afaf  mov     r15d, edx
0x18000afb2  mov     rsi, rcx
0x18000afb5  mov     dword ptr [rax+8], 0
0x18000afbc  lea     r13, WPP_GLOBAL_Control
0x18000afc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afca  mov     ebx, 1000h
0x18000afcf  cmp     rcx, r13
0x18000afd2  jz      short loc_18000AFFB
0x18000afd4  test    [rcx+1Ch], ebx
0x18000afd7  jz      short loc_18000AFFB
0x18000afd9  cmp     byte ptr [rcx+19h], 5
0x18000afdd  jb      short loc_18000AFFB
0x18000afdf  mov     edx, 5Bh ; '['
0x18000afe4  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000afeb  mov     rcx, [rcx+10h]
0x18000afef  call    WPP_SF_
0x18000aff4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000affb  test    rsi, rsi
0x18000affe  jz      loc_18000B1F1
0x18000b004  cmp     dword ptr [rsi], 0
0x18000b007  jz      loc_18000B1F1
0x18000b00d  cmp     dword ptr [rsi+10h], 0
0x18000b011  jnz     loc_18000B1F1
0x18000b017  mov     eax, [rsp+98h+arg_20]
0x18000b01e  test    eax, r15d
0x18000b021  jnz     short loc_18000B05E
0x18000b023  xor     ecx, ecx; dwErrCode
0x18000b025  call    cs:__imp_SetLastError
0x18000b02c  nop     dword ptr [rax+rax+00h]
0x18000b031  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b038  cmp     rcx, r13
0x18000b03b  jz      loc_18000B22E
0x18000b041  test    [rcx+1Ch], ebx
0x18000b044  jz      loc_18000B22E
0x18000b04a  cmp     byte ptr [rcx+19h], 2
0x18000b04e  jb      loc_18000B22E
0x18000b054  mov     edx, 5Dh ; ']'
0x18000b059  jmp     loc_18000B21E
0x18000b05e  not     eax
0x18000b060  test    r15d, eax
0x18000b063  jz      short loc_18000B0A0
0x18000b065  xor     ecx, ecx; dwErrCode
0x18000b067  call    cs:__imp_SetLastError
0x18000b06e  nop     dword ptr [rax+rax+00h]
0x18000b073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b07a  cmp     rcx, r13
0x18000b07d  jz      loc_18000B22E
0x18000b083  test    [rcx+1Ch], ebx
0x18000b086  jz      loc_18000B22E
0x18000b08c  cmp     byte ptr [rcx+19h], 2
0x18000b090  jb      loc_18000B22E
0x18000b096  mov     edx, 5Eh ; '^'
0x18000b09b  jmp     loc_18000B21E
0x18000b0a0  cmp     r14d, 20000h
0x18000b0a7  jz      loc_18000B137
0x18000b0ad  cmp     r14d, 30000h
0x18000b0b4  jz      short loc_18000B0EC
0x18000b0b6  cmp     rcx, r13
0x18000b0b9  jz      short loc_18000B0DE
0x18000b0bb  test    [rcx+1Ch], ebx
0x18000b0be  jz      short loc_18000B0DE
0x18000b0c0  cmp     byte ptr [rcx+19h], 2
0x18000b0c4  jb      short loc_18000B0DE
0x18000b0c6  mov     edx, 5Fh ; '_'
0x18000b0cb  mov     r9d, r14d
0x18000b0ce  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b0d5  mov     rcx, [rcx+10h]
0x18000b0d9  call    WPP_SF_d
0x18000b0de  mov     ebx, 29Ch
0x18000b0e3  mov     [rsp+98h+var_58], ebx
0x18000b0e7  jmp     loc_18000B183
0x18000b0ec  mov     rax, [rsi+20h]
0x18000b0f0  mov     [rsp+98h+var_50], 0
0x18000b0f9  mov     [rsp+98h+var_68], r12
0x18000b0fe  lea     rcx, [rsp+98h+arg_0]
0x18000b106  mov     [rsp+98h+var_70], rcx
0x18000b10b  mov     [rsp+98h+var_78], r15d
0x18000b110  mov     r9, [rax]
0x18000b113  xor     r8d, r8d; pReturnValue
0x18000b116  lea     edx, [r8+65h]; nProcNum
0x18000b11a  lea     rcx, pProxyInfo; pProxyInfo
0x18000b121  call    cs:__imp_NdrClientCall3
0x18000b128  nop     dword ptr [rax+rax+00h]
0x18000b12d  mov     rbx, rax
0x18000b130  mov     [rsp+98h+var_50], rax
0x18000b135  jmp     short loc_18000B17F
0x18000b137  mov     rax, [rsi+20h]
0x18000b13b  mov     [rsp+98h+var_48], 0
0x18000b144  mov     [rsp+98h+var_68], r12
0x18000b149  lea     rcx, [rsp+98h+arg_0]
0x18000b151  mov     [rsp+98h+var_70], rcx
0x18000b156  mov     [rsp+98h+var_78], r15d
0x18000b15b  mov     r9, [rax]
0x18000b15e  xor     r8d, r8d; pReturnValue
0x18000b161  lea     edx, [r8+19h]; nProcNum
0x18000b165  lea     rcx, pProxyInfo; pProxyInfo
0x18000b16c  call    cs:__imp_NdrClientCall3
0x18000b173  nop     dword ptr [rax+rax+00h]
0x18000b178  mov     [rsp+98h+var_48], rax
0x18000b17d  mov     ebx, eax
0x18000b17f  mov     [rsp+98h+var_58], eax
0x18000b183  jmp     short loc_18000B1C6
0x18000b185  mov     ebx, eax
0x18000b187  mov     [rsp+98h+var_58], eax
0x18000b18b  lea     rdx, WPP_GLOBAL_Control
0x18000b192  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b199  cmp     rcx, rdx
0x18000b19c  jz      short loc_18000B1C6
0x18000b19e  test    dword ptr [rcx+1Ch], 1000h
0x18000b1a5  jz      short loc_18000B1C6
0x18000b1a7  cmp     byte ptr [rcx+19h], 2
0x18000b1ab  jb      short loc_18000B1C6
0x18000b1ad  mov     edx, 60h ; '`'
0x18000b1b2  mov     r9d, eax
0x18000b1b5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b1bc  mov     rcx, [rcx+10h]
0x18000b1c0  call    WPP_SF_d
0x18000b1c5  nop
0x18000b1c6  test    ebx, ebx
0x18000b1c8  jz      short loc_18000B1DA
0x18000b1ca  mov     ecx, ebx; dwErrCode
0x18000b1cc  call    cs:__imp_SetLastError
0x18000b1d3  nop     dword ptr [rax+rax+00h]
0x18000b1d8  jmp     short loc_18000B22E
0x18000b1da  xor     ecx, ecx; dwErrCode
0x18000b1dc  call    cs:__imp_SetLastError
0x18000b1e3  nop     dword ptr [rax+rax+00h]
0x18000b1e8  mov     eax, [rsp+98h+arg_0]
0x18000b1ef  jmp     short loc_18000B230
0x18000b1f1  mov     ecx, 6; dwErrCode
0x18000b1f6  call    cs:__imp_SetLastError
0x18000b1fd  nop     dword ptr [rax+rax+00h]
0x18000b202  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b209  cmp     rcx, r13
0x18000b20c  jz      short loc_18000B22E
0x18000b20e  test    [rcx+1Ch], ebx
0x18000b211  jz      short loc_18000B22E
0x18000b213  cmp     byte ptr [rcx+19h], 2
0x18000b217  jb      short loc_18000B22E
0x18000b219  mov     edx, 5Ch ; '\'
0x18000b21e  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b225  mov     rcx, [rcx+10h]
0x18000b229  call    WPP_SF_
0x18000b22e  xor     eax, eax
0x18000b230  add     rsp, 68h
0x18000b234  pop     r15
0x18000b236  pop     r14
0x18000b238  pop     r13
0x18000b23a  pop     r12
0x18000b23c  pop     rsi
0x18000b23d  pop     rbx
0x18000b23e  retn
```
