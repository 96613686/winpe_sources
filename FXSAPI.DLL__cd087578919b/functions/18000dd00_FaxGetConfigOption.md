# FaxGetConfigOption

- ea: `0x18000dd00`
- end: `0x18000dea1`
- name: `FaxGetConfigOption`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000dd00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ddd7`
- `RPCRT4!NdrClientCall3` at `0x18000ddd7`
- `KERNEL32!SetLastError` at `0x18000dd78`
- `KERNEL32!SetLastError` at `0x18000de38`
- `KERNEL32!SetLastError` at `0x18000de52`
- `KERNEL32!SetLastError` at `0x18000dd78`
- `KERNEL32!SetLastError` at `0x18000de38`
- `KERNEL32!SetLastError` at `0x18000de52`

## pseudocode

```c
__int64 __fastcall FaxGetConfigOption(__int64 a1, int a2, __int64 a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v7 = 108;
LABEL_20:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
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
    v7 = 109;
    goto LABEL_20;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x68u,
                            0,
                            **(_QWORD **)(a1 + 32),
                            a2,
                            a3).Pointer;
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18000dd00  mov     [rsp+arg_8], rbx
0x18000dd05  mov     [rsp+arg_10], rsi
0x18000dd0a  push    rdi
0x18000dd0b  push    r14
0x18000dd0d  push    r15
0x18000dd0f  sub     rsp, 40h
0x18000dd13  mov     rsi, r8
0x18000dd16  mov     r14d, edx
0x18000dd19  mov     rdi, rcx
0x18000dd1c  lea     r15, WPP_GLOBAL_Control
0x18000dd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd2a  mov     ebx, 1000h
0x18000dd2f  cmp     rcx, r15
0x18000dd32  jz      short loc_18000DD54
0x18000dd34  test    [rcx+1Ch], ebx
0x18000dd37  jz      short loc_18000DD54
0x18000dd39  cmp     byte ptr [rcx+19h], 5
0x18000dd3d  jb      short loc_18000DD54
0x18000dd3f  mov     edx, 6Bh ; 'k'
0x18000dd44  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000dd4b  mov     rcx, [rcx+10h]
0x18000dd4f  call    WPP_SF_
0x18000dd54  test    rdi, rdi
0x18000dd57  jz      loc_18000DE4D
0x18000dd5d  cmp     dword ptr [rdi], 0
0x18000dd60  jz      loc_18000DE4D
0x18000dd66  cmp     dword ptr [rdi+10h], 0
0x18000dd6a  jnz     loc_18000DE4D
0x18000dd70  test    rsi, rsi
0x18000dd73  jnz     short loc_18000DDAF
0x18000dd75  lea     ecx, [rsi+57h]; dwErrCode
0x18000dd78  call    cs:__imp_SetLastError
0x18000dd7f  nop     dword ptr [rax+rax+00h]
0x18000dd84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd8b  cmp     rcx, r15
0x18000dd8e  jz      loc_18000DE8A
0x18000dd94  test    [rcx+1Ch], ebx
0x18000dd97  jz      loc_18000DE8A
0x18000dd9d  cmp     byte ptr [rcx+19h], 2
0x18000dda1  jb      loc_18000DE8A
0x18000dda7  lea     edx, [rsi+6Dh]
0x18000ddaa  jmp     loc_18000DE7A
0x18000ddaf  mov     rax, [rdi+20h]
0x18000ddb3  mov     [rsp+58h+arg_0], 0
0x18000ddbc  mov     [rsp+58h+var_30], rsi
0x18000ddc1  mov     [rsp+58h+var_38], r14d
0x18000ddc6  mov     r9, [rax]
0x18000ddc9  xor     r8d, r8d; pReturnValue
0x18000ddcc  lea     edx, [r8+68h]; nProcNum
0x18000ddd0  lea     rcx, pProxyInfo; pProxyInfo
0x18000ddd7  call    cs:__imp_NdrClientCall3
0x18000ddde  nop     dword ptr [rax+rax+00h]
0x18000dde3  mov     rbx, rax
0x18000dde6  mov     [rsp+58h+arg_0], rax
0x18000ddeb  mov     [rsp+58h+var_28], eax
0x18000ddef  jmp     short loc_18000DE32
0x18000ddf1  mov     ebx, eax
0x18000ddf3  mov     [rsp+58h+var_28], eax
0x18000ddf7  lea     rdx, WPP_GLOBAL_Control
0x18000ddfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de05  cmp     rcx, rdx
0x18000de08  jz      short loc_18000DE32
0x18000de0a  test    dword ptr [rcx+1Ch], 1000h
0x18000de11  jz      short loc_18000DE32
0x18000de13  cmp     byte ptr [rcx+19h], 2
0x18000de17  jb      short loc_18000DE32
0x18000de19  mov     edx, 6Eh ; 'n'
0x18000de1e  mov     r9d, eax
0x18000de21  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000de28  mov     rcx, [rcx+10h]
0x18000de2c  call    WPP_SF_d
0x18000de31  nop
0x18000de32  test    ebx, ebx
0x18000de34  jz      short loc_18000DE46
0x18000de36  mov     ecx, ebx; dwErrCode
0x18000de38  call    cs:__imp_SetLastError
0x18000de3f  nop     dword ptr [rax+rax+00h]
0x18000de44  jmp     short loc_18000DE8A
0x18000de46  mov     eax, 1
0x18000de4b  jmp     short loc_18000DE8C
0x18000de4d  mov     ecx, 6; dwErrCode
0x18000de52  call    cs:__imp_SetLastError
0x18000de59  nop     dword ptr [rax+rax+00h]
0x18000de5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de65  cmp     rcx, r15
0x18000de68  jz      short loc_18000DE8A
0x18000de6a  test    [rcx+1Ch], ebx
0x18000de6d  jz      short loc_18000DE8A
0x18000de6f  cmp     byte ptr [rcx+19h], 2
0x18000de73  jb      short loc_18000DE8A
0x18000de75  mov     edx, 6Ch ; 'l'
0x18000de7a  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000de81  mov     rcx, [rcx+10h]
0x18000de85  call    WPP_SF_
0x18000de8a  xor     eax, eax
0x18000de8c  mov     rbx, [rsp+58h+arg_8]
0x18000de91  mov     rsi, [rsp+58h+arg_10]
0x18000de96  add     rsp, 40h
0x18000de9a  pop     r15
0x18000de9c  pop     r14
0x18000de9e  pop     rdi
0x18000de9f  retn
```
