# CommonUtil::HrWinVerifyTrust

- ea: `0x140010458`
- end: `0x1400104de`
- name: `CommonUtil::HrWinVerifyTrust`
- size: `134`
- prototype: `LONG __fastcall(HWND, GUID *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400104e4`
- `0x1400108f8`
- `0x140010b20`

## callees

- `0x140003640`
- `0x140010458`
- `0x140010b20`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x140010465`
- `WINTRUST!WinVerifyTrust` at `0x140010465`

## pseudocode

```c
LONG __fastcall CommonUtil::HrWinVerifyTrust(HWND a1, GUID *a2, __int64 a3)
{
  LONG result; // eax
  unsigned int v5; // ebx

  result = WinVerifyTrust(a1, a2, (LPVOID)a3);
  v5 = result;
  if ( result )
  {
    if ( result >= 0 )
      v5 = (unsigned __int16)result | 0x80070000;
    if ( *(_DWORD *)(a3 + 48) == 1 )
    {
      CommonUtil::UtilCloseWinVerifyTrust(a3);
      *(_QWORD *)(a3 + 56) = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids, v5);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140010458  mov     [rsp+arg_0], rbx
0x14001045d  push    rdi
0x14001045e  sub     rsp, 20h
0x140010462  mov     rdi, r8
0x140010465  call    cs:__imp_WinVerifyTrust
0x14001046b  mov     ebx, eax
0x14001046d  test    eax, eax
0x14001046f  jz      short loc_1400104D3
0x140010471  js      short loc_14001048A
0x140010473  test    eax, eax
0x140010475  jle     short loc_140010480
0x140010477  movzx   ebx, ax
0x14001047a  or      ebx, 80070000h
0x140010480  test    ebx, ebx
0x140010482  mov     eax, 80004005h
0x140010487  cmovns  ebx, eax
0x14001048a  cmp     dword ptr [rdi+30h], 1
0x14001048e  jnz     short loc_1400104A0
0x140010490  mov     rcx, rdi
0x140010493  call    CommonUtil__UtilCloseWinVerifyTrust
0x140010498  mov     qword ptr [rdi+38h], 0
0x1400104a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104a7  lea     rax, WPP_GLOBAL_Control
0x1400104ae  cmp     rcx, rax
0x1400104b1  jz      short loc_1400104D1
0x1400104b3  test    byte ptr [rcx+1Ch], 4
0x1400104b7  jz      short loc_1400104D1
0x1400104b9  mov     rcx, [rcx+10h]
0x1400104bd  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x1400104c4  mov     edx, 0Ah
0x1400104c9  mov     r9d, ebx
0x1400104cc  call    WPP_SF_d
0x1400104d1  mov     eax, ebx
0x1400104d3  mov     rbx, [rsp+28h+arg_0]
0x1400104d8  add     rsp, 20h
0x1400104dc  pop     rdi
0x1400104dd  retn
```
