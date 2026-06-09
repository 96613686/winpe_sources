# FaxGetOutboxConfiguration

- ea: `0x18000f060`
- end: `0x18000f20b`
- name: `FaxGetOutboxConfiguration`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000f060`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000f146`
- `RPCRT4!NdrClientCall3` at `0x18000f146`
- `KERNEL32!SetLastError` at `0x18000f0d9`
- `KERNEL32!SetLastError` at `0x18000f1a7`
- `KERNEL32!SetLastError` at `0x18000f1c1`
- `KERNEL32!SetLastError` at `0x18000f0d9`
- `KERNEL32!SetLastError` at `0x18000f1a7`
- `KERNEL32!SetLastError` at `0x18000f1c1`

## pseudocode

```c
__int64 __fastcall FaxGetOutboxConfiguration(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  CLIENT_CALL_RETURN v7; // rax
  int v9; // [rsp+60h] [rbp+8h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+70h] [rbp+18h]

  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v5 = 141;
LABEL_20:
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
    v5 = 142;
    goto LABEL_20;
  }
  *a2 = 0;
  v6 = *(_QWORD **)(a1 + 32);
  v10.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x26u, 0, *v6, a2, &v9).Pointer;
  v10.Pointer = v7.Pointer;
  if ( !LODWORD(v7.Pointer) )
    return 1;
  SetLastError((DWORD)v7.Pointer);
  return 0;
}

```

## disassembly

```asm
0x18000f060  mov     [rsp+arg_8], rbx
0x18000f065  push    rsi
0x18000f066  push    r14
0x18000f068  push    r15
0x18000f06a  sub     rsp, 40h
0x18000f06e  mov     r14, rdx
0x18000f071  mov     rsi, rcx
0x18000f074  mov     [rsp+58h+arg_0], 0
0x18000f07c  lea     r15, WPP_GLOBAL_Control
0x18000f083  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f08a  mov     ebx, 1000h
0x18000f08f  cmp     rcx, r15
0x18000f092  jz      short loc_18000F0B4
0x18000f094  test    [rcx+1Ch], ebx
0x18000f097  jz      short loc_18000F0B4
0x18000f099  cmp     byte ptr [rcx+19h], 5
0x18000f09d  jb      short loc_18000F0B4
0x18000f09f  mov     edx, 8Ch
0x18000f0a4  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f0ab  mov     rcx, [rcx+10h]
0x18000f0af  call    WPP_SF_
0x18000f0b4  test    rsi, rsi
0x18000f0b7  jz      loc_18000F1BC
0x18000f0bd  cmp     dword ptr [rsi], 0
0x18000f0c0  jz      loc_18000F1BC
0x18000f0c6  cmp     dword ptr [rsi+10h], 0
0x18000f0ca  jnz     loc_18000F1BC
0x18000f0d0  test    r14, r14
0x18000f0d3  jnz     short loc_18000F112
0x18000f0d5  lea     ecx, [r14+57h]; dwErrCode
0x18000f0d9  call    cs:__imp_SetLastError
0x18000f0e0  nop     dword ptr [rax+rax+00h]
0x18000f0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0ec  cmp     rcx, r15
0x18000f0ef  jz      loc_18000F1F9
0x18000f0f5  test    [rcx+1Ch], ebx
0x18000f0f8  jz      loc_18000F1F9
0x18000f0fe  cmp     byte ptr [rcx+19h], 2
0x18000f102  jb      loc_18000F1F9
0x18000f108  mov     edx, 8Eh
0x18000f10d  jmp     loc_18000F1E9
0x18000f112  mov     qword ptr [r14], 0
0x18000f119  mov     rax, [rsi+20h]
0x18000f11d  mov     [rsp+58h+arg_10], 0
0x18000f126  lea     rcx, [rsp+58h+arg_0]
0x18000f12b  mov     [rsp+58h+var_30], rcx
0x18000f130  mov     [rsp+58h+var_38], r14
0x18000f135  mov     r9, [rax]
0x18000f138  xor     r8d, r8d; pReturnValue
0x18000f13b  lea     edx, [r8+26h]; nProcNum
0x18000f13f  lea     rcx, pProxyInfo; pProxyInfo
0x18000f146  call    cs:__imp_NdrClientCall3
0x18000f14d  nop     dword ptr [rax+rax+00h]
0x18000f152  mov     rbx, rax
0x18000f155  mov     [rsp+58h+arg_10], rax
0x18000f15a  mov     [rsp+58h+var_28], eax
0x18000f15e  jmp     short loc_18000F1A1
0x18000f160  mov     ebx, eax
0x18000f162  mov     [rsp+58h+var_28], eax
0x18000f166  lea     rdx, WPP_GLOBAL_Control
0x18000f16d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f174  cmp     rcx, rdx
0x18000f177  jz      short loc_18000F1A1
0x18000f179  test    dword ptr [rcx+1Ch], 1000h
0x18000f180  jz      short loc_18000F1A1
0x18000f182  cmp     byte ptr [rcx+19h], 2
0x18000f186  jb      short loc_18000F1A1
0x18000f188  mov     edx, 8Fh
0x18000f18d  mov     r9d, eax
0x18000f190  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f197  mov     rcx, [rcx+10h]
0x18000f19b  call    WPP_SF_d
0x18000f1a0  nop
0x18000f1a1  test    ebx, ebx
0x18000f1a3  jz      short loc_18000F1B5
0x18000f1a5  mov     ecx, ebx; dwErrCode
0x18000f1a7  call    cs:__imp_SetLastError
0x18000f1ae  nop     dword ptr [rax+rax+00h]
0x18000f1b3  jmp     short loc_18000F1F9
0x18000f1b5  mov     eax, 1
0x18000f1ba  jmp     short loc_18000F1FB
0x18000f1bc  mov     ecx, 6; dwErrCode
0x18000f1c1  call    cs:__imp_SetLastError
0x18000f1c8  nop     dword ptr [rax+rax+00h]
0x18000f1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d4  cmp     rcx, r15
0x18000f1d7  jz      short loc_18000F1F9
0x18000f1d9  test    [rcx+1Ch], ebx
0x18000f1dc  jz      short loc_18000F1F9
0x18000f1de  cmp     byte ptr [rcx+19h], 2
0x18000f1e2  jb      short loc_18000F1F9
0x18000f1e4  mov     edx, 8Dh
0x18000f1e9  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f1f0  mov     rcx, [rcx+10h]
0x18000f1f4  call    WPP_SF_
0x18000f1f9  xor     eax, eax
0x18000f1fb  mov     rbx, [rsp+58h+arg_8]
0x18000f200  add     rsp, 40h
0x18000f204  pop     r15
0x18000f206  pop     r14
0x18000f208  pop     rsi
0x18000f209  retn
```
