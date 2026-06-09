# CommonUtil::HrWinVerifyTrust

- ea: `0x14000ed88`
- end: `0x14000ee0e`
- name: `CommonUtil::HrWinVerifyTrust`
- size: `134`
- prototype: `LONG __fastcall(HWND, GUID *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ee14`
- `0x14000f1bc`
- `0x14000f3e4`

## callees

- `0x140003040`
- `0x14000ed88`
- `0x14000f3e4`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x14000ed95`
- `WINTRUST!WinVerifyTrust` at `0x14000ed95`

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
0x14000ed88  mov     [rsp+arg_0], rbx
0x14000ed8d  push    rdi
0x14000ed8e  sub     rsp, 20h
0x14000ed92  mov     rdi, r8
0x14000ed95  call    cs:__imp_WinVerifyTrust
0x14000ed9b  mov     ebx, eax
0x14000ed9d  test    eax, eax
0x14000ed9f  jz      short loc_14000EE03
0x14000eda1  js      short loc_14000EDBA
0x14000eda3  test    eax, eax
0x14000eda5  jle     short loc_14000EDB0
0x14000eda7  movzx   ebx, ax
0x14000edaa  or      ebx, 80070000h
0x14000edb0  test    ebx, ebx
0x14000edb2  mov     eax, 80004005h
0x14000edb7  cmovns  ebx, eax
0x14000edba  cmp     dword ptr [rdi+30h], 1
0x14000edbe  jnz     short loc_14000EDD0
0x14000edc0  mov     rcx, rdi
0x14000edc3  call    CommonUtil__UtilCloseWinVerifyTrust
0x14000edc8  mov     qword ptr [rdi+38h], 0
0x14000edd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edd7  lea     rax, WPP_GLOBAL_Control
0x14000edde  cmp     rcx, rax
0x14000ede1  jz      short loc_14000EE01
0x14000ede3  test    byte ptr [rcx+1Ch], 4
0x14000ede7  jz      short loc_14000EE01
0x14000ede9  mov     rcx, [rcx+10h]
0x14000eded  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000edf4  mov     edx, 0Ah
0x14000edf9  mov     r9d, ebx
0x14000edfc  call    WPP_SF_d
0x14000ee01  mov     eax, ebx
0x14000ee03  mov     rbx, [rsp+28h+arg_0]
0x14000ee08  add     rsp, 20h
0x14000ee0c  pop     rdi
0x14000ee0d  retn
```
