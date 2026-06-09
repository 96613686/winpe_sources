# FaxDeleteAccount

- ea: `0x18002b3d0`
- end: `0x18002b514`
- name: `FaxDeleteAccount`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002b3d0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002b45e`
- `RPCRT4!NdrClientCall3` at `0x18002b45e`
- `KERNEL32!SetLastError` at `0x18002b4ee`
- `KERNEL32!SetLastError` at `0x18002b4ee`

## pseudocode

```c
__int64 __fastcall FaxDeleteAccount(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  DWORD Pointer; // ebx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x5Eu,
                              0,
                              **(_QWORD **)(a1 + 32),
                              a2).Pointer;
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 19, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
    Pointer = 6;
  }
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18002b3d0  mov     [rsp+arg_8], rbx
0x18002b3d5  mov     [rsp+arg_10], rsi
0x18002b3da  push    rdi
0x18002b3db  sub     rsp, 40h
0x18002b3df  mov     rdi, rdx
0x18002b3e2  mov     rbx, rcx
0x18002b3e5  lea     rsi, WPP_GLOBAL_Control
0x18002b3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3f3  cmp     rcx, rsi
0x18002b3f6  jz      short loc_18002B423
0x18002b3f8  test    dword ptr [rcx+1Ch], 1000h
0x18002b3ff  jz      short loc_18002B423
0x18002b401  cmp     byte ptr [rcx+19h], 5
0x18002b405  jb      short loc_18002B423
0x18002b407  mov     edx, 12h
0x18002b40c  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b413  mov     rcx, [rcx+10h]
0x18002b417  call    WPP_SF_
0x18002b41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b423  test    rbx, rbx
0x18002b426  jz      loc_18002B4BA
0x18002b42c  cmp     dword ptr [rbx], 0
0x18002b42f  jz      loc_18002B4BA
0x18002b435  cmp     dword ptr [rbx+10h], 0
0x18002b439  jnz     short loc_18002B4BA
0x18002b43b  mov     rax, [rbx+20h]
0x18002b43f  mov     [rsp+48h+arg_0], 0
0x18002b448  mov     [rsp+48h+var_28], rdi
0x18002b44d  mov     r9, [rax]
0x18002b450  xor     r8d, r8d; pReturnValue
0x18002b453  lea     edx, [r8+5Eh]; nProcNum
0x18002b457  lea     rcx, pProxyInfo; pProxyInfo
0x18002b45e  call    cs:__imp_NdrClientCall3
0x18002b465  nop     dword ptr [rax+rax+00h]
0x18002b46a  mov     rbx, rax
0x18002b46d  mov     [rsp+48h+arg_0], rax
0x18002b472  mov     [rsp+48h+var_18], eax
0x18002b476  jmp     short loc_18002B4E8
0x18002b478  mov     ebx, eax
0x18002b47a  mov     [rsp+48h+var_18], eax
0x18002b47e  lea     rdx, WPP_GLOBAL_Control
0x18002b485  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b48c  cmp     rcx, rdx
0x18002b48f  jz      short loc_18002B4B8
0x18002b491  test    dword ptr [rcx+1Ch], 1000h
0x18002b498  jz      short loc_18002B4B8
0x18002b49a  cmp     byte ptr [rcx+19h], 2
0x18002b49e  jb      short loc_18002B4B8
0x18002b4a0  mov     edx, 14h
0x18002b4a5  mov     r9d, eax
0x18002b4a8  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b4af  mov     rcx, [rcx+10h]
0x18002b4b3  call    WPP_SF_d
0x18002b4b8  jmp     short loc_18002B4E8
0x18002b4ba  cmp     rcx, rsi
0x18002b4bd  jz      short loc_18002B4E3
0x18002b4bf  test    dword ptr [rcx+1Ch], 1000h
0x18002b4c6  jz      short loc_18002B4E3
0x18002b4c8  cmp     byte ptr [rcx+19h], 2
0x18002b4cc  jb      short loc_18002B4E3
0x18002b4ce  mov     edx, 13h
0x18002b4d3  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b4da  mov     rcx, [rcx+10h]
0x18002b4de  call    WPP_SF_
0x18002b4e3  mov     ebx, 6
0x18002b4e8  test    ebx, ebx
0x18002b4ea  jz      short loc_18002B4FE
0x18002b4ec  mov     ecx, ebx; dwErrCode
0x18002b4ee  call    cs:__imp_SetLastError
0x18002b4f5  nop     dword ptr [rax+rax+00h]
0x18002b4fa  xor     eax, eax
0x18002b4fc  jmp     short loc_18002B503
0x18002b4fe  mov     eax, 1
0x18002b503  mov     rbx, [rsp+48h+arg_8]
0x18002b508  mov     rsi, [rsp+48h+arg_10]
0x18002b50d  add     rsp, 40h
0x18002b511  pop     rdi
0x18002b512  retn
```
