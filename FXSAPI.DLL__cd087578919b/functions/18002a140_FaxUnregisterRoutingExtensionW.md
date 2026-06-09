# FaxUnregisterRoutingExtensionW

- ea: `0x18002a140`
- end: `0x18002a2c6`
- name: `FaxUnregisterRoutingExtensionW`
- size: `390`
- prototype: `BOOL __stdcall(HANDLE hFaxHandle, LPCWSTR lpctstrExtensionName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002a070`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002a140`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002a206`
- `RPCRT4!NdrClientCall3` at `0x18002a206`
- `KERNEL32!SetLastError` at `0x18002a1ac`
- `KERNEL32!SetLastError` at `0x18002a267`
- `KERNEL32!SetLastError` at `0x18002a281`
- `KERNEL32!SetLastError` at `0x18002a1ac`
- `KERNEL32!SetLastError` at `0x18002a267`
- `KERNEL32!SetLastError` at `0x18002a281`

## pseudocode

```c
BOOL __stdcall FaxUnregisterRoutingExtensionW(HANDLE hFaxHandle, LPCWSTR lpctstrExtensionName)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  if ( !hFaxHandle || !*(_DWORD *)hFaxHandle || *((_DWORD *)hFaxHandle + 4) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 48;
LABEL_20:
    WPP_SF_(v4[2], v5, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    return 0;
  }
  if ( !lpctstrExtensionName )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 49;
    goto LABEL_20;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x3Eu,
                            0,
                            **((_QWORD **)hFaxHandle + 4),
                            lpctstrExtensionName).Pointer;
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18002a140  push    rbx
0x18002a142  push    rsi
0x18002a143  push    rdi
0x18002a144  push    r14
0x18002a146  sub     rsp, 48h
0x18002a14a  mov     rsi, rdx
0x18002a14d  mov     rdi, rcx
0x18002a150  lea     r14, WPP_GLOBAL_Control
0x18002a157  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a15e  mov     ebx, 1000h
0x18002a163  cmp     rcx, r14
0x18002a166  jz      short loc_18002A188
0x18002a168  test    [rcx+1Ch], ebx
0x18002a16b  jz      short loc_18002A188
0x18002a16d  cmp     byte ptr [rcx+19h], 5
0x18002a171  jb      short loc_18002A188
0x18002a173  mov     edx, 2Fh ; '/'
0x18002a178  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a17f  mov     rcx, [rcx+10h]
0x18002a183  call    WPP_SF_
0x18002a188  test    rdi, rdi
0x18002a18b  jz      loc_18002A27C
0x18002a191  cmp     dword ptr [rdi], 0
0x18002a194  jz      loc_18002A27C
0x18002a19a  cmp     dword ptr [rdi+10h], 0
0x18002a19e  jnz     loc_18002A27C
0x18002a1a4  test    rsi, rsi
0x18002a1a7  jnz     short loc_18002A1E3
0x18002a1a9  lea     ecx, [rsi+57h]; dwErrCode
0x18002a1ac  call    cs:__imp_SetLastError
0x18002a1b3  nop     dword ptr [rax+rax+00h]
0x18002a1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1bf  cmp     rcx, r14
0x18002a1c2  jz      loc_18002A2B9
0x18002a1c8  test    [rcx+1Ch], ebx
0x18002a1cb  jz      loc_18002A2B9
0x18002a1d1  cmp     byte ptr [rcx+19h], 2
0x18002a1d5  jb      loc_18002A2B9
0x18002a1db  lea     edx, [rsi+31h]
0x18002a1de  jmp     loc_18002A2A9
0x18002a1e3  mov     rax, [rdi+20h]
0x18002a1e7  mov     [rsp+68h+arg_0], 0
0x18002a1f0  mov     [rsp+68h+var_48], rsi
0x18002a1f5  mov     r9, [rax]
0x18002a1f8  xor     r8d, r8d; pReturnValue
0x18002a1fb  lea     edx, [r8+3Eh]; nProcNum
0x18002a1ff  lea     rcx, pProxyInfo; pProxyInfo
0x18002a206  call    cs:__imp_NdrClientCall3
0x18002a20d  nop     dword ptr [rax+rax+00h]
0x18002a212  mov     rbx, rax
0x18002a215  mov     [rsp+68h+arg_0], rax
0x18002a21a  mov     [rsp+68h+var_38], eax
0x18002a21e  jmp     short loc_18002A261
0x18002a220  mov     ebx, eax
0x18002a222  mov     [rsp+68h+var_38], eax
0x18002a226  lea     rdx, WPP_GLOBAL_Control
0x18002a22d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a234  cmp     rcx, rdx
0x18002a237  jz      short loc_18002A261
0x18002a239  test    dword ptr [rcx+1Ch], 1000h
0x18002a240  jz      short loc_18002A261
0x18002a242  cmp     byte ptr [rcx+19h], 2
0x18002a246  jb      short loc_18002A261
0x18002a248  mov     edx, 32h ; '2'
0x18002a24d  mov     r9d, eax
0x18002a250  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a257  mov     rcx, [rcx+10h]
0x18002a25b  call    WPP_SF_d
0x18002a260  nop
0x18002a261  test    ebx, ebx
0x18002a263  jz      short loc_18002A275
0x18002a265  mov     ecx, ebx; dwErrCode
0x18002a267  call    cs:__imp_SetLastError
0x18002a26e  nop     dword ptr [rax+rax+00h]
0x18002a273  jmp     short loc_18002A2B9
0x18002a275  mov     eax, 1
0x18002a27a  jmp     short loc_18002A2BB
0x18002a27c  mov     ecx, 6; dwErrCode
0x18002a281  call    cs:__imp_SetLastError
0x18002a288  nop     dword ptr [rax+rax+00h]
0x18002a28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a294  cmp     rcx, r14
0x18002a297  jz      short loc_18002A2B9
0x18002a299  test    [rcx+1Ch], ebx
0x18002a29c  jz      short loc_18002A2B9
0x18002a29e  cmp     byte ptr [rcx+19h], 2
0x18002a2a2  jb      short loc_18002A2B9
0x18002a2a4  mov     edx, 30h ; '0'
0x18002a2a9  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a2b0  mov     rcx, [rcx+10h]
0x18002a2b4  call    WPP_SF_
0x18002a2b9  xor     eax, eax
0x18002a2bb  add     rsp, 48h
0x18002a2bf  pop     r14
0x18002a2c1  pop     rdi
0x18002a2c2  pop     rsi
0x18002a2c3  pop     rbx
0x18002a2c4  retn
```
