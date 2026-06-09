# FaxRemoveOutboundRule

- ea: `0x180010970`
- end: `0x180010b0e`
- name: `FaxRemoveOutboundRule`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180010970`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010a4d`
- `RPCRT4!NdrClientCall3` at `0x180010a4d`
- `KERNEL32!SetLastError` at `0x180010a15`
- `KERNEL32!SetLastError` at `0x180010abf`
- `KERNEL32!SetLastError` at `0x180010a15`
- `KERNEL32!SetLastError` at `0x180010abf`

## pseudocode

```c
__int64 __fastcall FaxRemoveOutboundRule(__int64 a1, int a2, int a3)
{
  _QWORD *v6; // rcx
  DWORD v7; // ecx
  unsigned int Pointer; // eax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
  {
    if ( a3 )
    {
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x39u,
                                0,
                                **(_QWORD **)(a1 + 32),
                                a2,
                                a3).Pointer;
      if ( !Pointer )
        return 1;
      v7 = Pointer;
    }
    else
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 259, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      v7 = 87;
    }
    SetLastError(v7);
  }
  else
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 258, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010970  mov     [rsp+arg_8], rbx
0x180010975  mov     [rsp+arg_10], rsi
0x18001097a  push    rdi
0x18001097b  push    r14
0x18001097d  push    r15
0x18001097f  sub     rsp, 40h
0x180010983  mov     esi, r8d
0x180010986  mov     r14d, edx
0x180010989  mov     rdi, rcx
0x18001098c  lea     r15, WPP_GLOBAL_Control
0x180010993  mov     rcx, cs:WPP_GLOBAL_Control
0x18001099a  mov     ebx, 1000h
0x18001099f  cmp     rcx, r15
0x1800109a2  jz      short loc_1800109CB
0x1800109a4  test    [rcx+1Ch], ebx
0x1800109a7  jz      short loc_1800109CB
0x1800109a9  cmp     byte ptr [rcx+19h], 5
0x1800109ad  jb      short loc_1800109CB
0x1800109af  mov     edx, 101h
0x1800109b4  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800109bb  mov     rcx, [rcx+10h]
0x1800109bf  call    WPP_SF_
0x1800109c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109cb  test    rdi, rdi
0x1800109ce  jz      loc_180010ABA
0x1800109d4  cmp     dword ptr [rdi], 0
0x1800109d7  jz      loc_180010ABA
0x1800109dd  cmp     dword ptr [rdi+10h], 0
0x1800109e1  jnz     loc_180010ABA
0x1800109e7  test    esi, esi
0x1800109e9  jnz     short loc_180010A26
0x1800109eb  cmp     rcx, r15
0x1800109ee  jz      short loc_180010A10
0x1800109f0  test    [rcx+1Ch], ebx
0x1800109f3  jz      short loc_180010A10
0x1800109f5  cmp     byte ptr [rcx+19h], 2
0x1800109f9  jb      short loc_180010A10
0x1800109fb  mov     edx, 103h
0x180010a00  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010a07  mov     rcx, [rcx+10h]
0x180010a0b  call    WPP_SF_
0x180010a10  mov     ecx, 57h ; 'W'; dwErrCode
0x180010a15  call    cs:__imp_SetLastError
0x180010a1c  nop     dword ptr [rax+rax+00h]
0x180010a21  jmp     loc_180010AF7
0x180010a26  mov     rax, [rdi+20h]
0x180010a2a  mov     [rsp+58h+arg_0], 0
0x180010a33  mov     [rsp+58h+var_30], esi
0x180010a37  mov     [rsp+58h+var_38], r14d
0x180010a3c  mov     r9, [rax]
0x180010a3f  xor     r8d, r8d; pReturnValue
0x180010a42  lea     edx, [r8+39h]; nProcNum
0x180010a46  lea     rcx, pProxyInfo; pProxyInfo
0x180010a4d  call    cs:__imp_NdrClientCall3
0x180010a54  nop     dword ptr [rax+rax+00h]
0x180010a59  mov     rbx, rax
0x180010a5c  mov     [rsp+58h+arg_0], rax
0x180010a61  mov     [rsp+58h+var_28], eax
0x180010a65  jmp     short loc_180010AA8
0x180010a67  mov     ebx, eax
0x180010a69  mov     [rsp+58h+var_28], eax
0x180010a6d  lea     rdx, WPP_GLOBAL_Control
0x180010a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a7b  cmp     rcx, rdx
0x180010a7e  jz      short loc_180010AA8
0x180010a80  test    dword ptr [rcx+1Ch], 1000h
0x180010a87  jz      short loc_180010AA8
0x180010a89  cmp     byte ptr [rcx+19h], 2
0x180010a8d  jb      short loc_180010AA8
0x180010a8f  mov     edx, 104h
0x180010a94  mov     r9d, eax
0x180010a97  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010a9e  mov     rcx, [rcx+10h]
0x180010aa2  call    WPP_SF_d
0x180010aa7  nop
0x180010aa8  test    ebx, ebx
0x180010aaa  jz      short loc_180010AB3
0x180010aac  mov     ecx, ebx
0x180010aae  jmp     loc_180010A15
0x180010ab3  mov     eax, 1
0x180010ab8  jmp     short loc_180010AF9
0x180010aba  mov     ecx, 6; dwErrCode
0x180010abf  call    cs:__imp_SetLastError
0x180010ac6  nop     dword ptr [rax+rax+00h]
0x180010acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ad2  cmp     rcx, r15
0x180010ad5  jz      short loc_180010AF7
0x180010ad7  test    [rcx+1Ch], ebx
0x180010ada  jz      short loc_180010AF7
0x180010adc  cmp     byte ptr [rcx+19h], 2
0x180010ae0  jb      short loc_180010AF7
0x180010ae2  mov     edx, 102h
0x180010ae7  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010aee  mov     rcx, [rcx+10h]
0x180010af2  call    WPP_SF_
0x180010af7  xor     eax, eax
0x180010af9  mov     rbx, [rsp+58h+arg_8]
0x180010afe  mov     rsi, [rsp+58h+arg_10]
0x180010b03  add     rsp, 40h
0x180010b07  pop     r15
0x180010b09  pop     r14
0x180010b0b  pop     rdi
0x180010b0c  retn
```
