# UpdateRebarBandColors

- ea: `0x18000cc00`
- end: `0x18000ccfc`
- name: `UpdateRebarBandColors`
- size: `252`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000cc00`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `USER32!GetSysColor` at `0x18000ccab`
- `USER32!GetSysColor` at `0x18000ccba`
- `USER32!GetSysColor` at `0x18000ccab`
- `USER32!GetSysColor` at `0x18000ccba`
- `USER32!SendMessageA` at `0x18000cc41`
- `USER32!SendMessageA` at `0x18000cc80`
- `USER32!SendMessageA` at `0x18000ccd4`
- `USER32!SendMessageA` at `0x18000cc41`
- `USER32!SendMessageA` at `0x18000cc80`
- `USER32!SendMessageA` at `0x18000ccd4`

## pseudocode

```c
__int64 __fastcall UpdateRebarBandColors(HWND hWnd)
{
  unsigned int v2; // ebp
  __int64 result; // rax
  unsigned int v4; // edi
  LPARAM lParam; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v6[4]; // [rsp+28h] [rbp-B0h] BYREF
  DWORD SysColor; // [rsp+2Ch] [rbp-ACh]
  DWORD v8; // [rsp+30h] [rbp-A8h]

  memset_0(&lParam, 0, 0x80u);
  v2 = SendMessageA(hWnd, 0x40Cu, 0, 0);
  result = (__int64)memset_0(v6, 0, 0x78u);
  v4 = 0;
  for ( lParam = 0x10000000080LL; v4 < v2; ++v4 )
  {
    SendMessageA(hWnd, 0x41Du, v4, (LPARAM)&lParam);
    memset_0(v6, 0, 0x78u);
    lParam = 0x200000080LL;
    SysColor = GetSysColor(18);
    v8 = GetSysColor(15);
    result = SendMessageA(hWnd, 0x406u, v4, (LPARAM)&lParam);
  }
  return result;
}

```

## disassembly

```asm
0x18000cc00  push    rbx
0x18000cc02  push    rbp
0x18000cc03  push    rsi
0x18000cc04  push    rdi
0x18000cc05  sub     rsp, 0B8h
0x18000cc0c  mov     rax, cs:__security_cookie
0x18000cc13  xor     rax, rsp
0x18000cc16  mov     [rsp+0D8h+var_38], rax
0x18000cc1e  mov     rsi, rcx
0x18000cc21  xor     edx, edx; Val
0x18000cc23  lea     rcx, [rsp+0D8h+lParam]; void *
0x18000cc28  mov     r8d, 80h; Size
0x18000cc2e  call    memset_0
0x18000cc33  xor     r9d, r9d; lParam
0x18000cc36  xor     r8d, r8d; wParam
0x18000cc39  mov     edx, 40Ch; Msg
0x18000cc3e  mov     rcx, rsi; hWnd
0x18000cc41  call    cs:__imp_SendMessageA
0x18000cc47  xor     edx, edx; Val
0x18000cc49  lea     rcx, [rsp+0D8h+var_B0]; void *
0x18000cc4e  mov     rbp, rax
0x18000cc51  lea     r8d, [rdx+78h]; Size
0x18000cc55  call    memset_0
0x18000cc5a  xor     edi, edi
0x18000cc5c  mov     dword ptr [rsp+0D8h+lParam], 80h
0x18000cc64  mov     dword ptr [rsp+0D8h+lParam+4], 100h
0x18000cc6c  test    ebp, ebp
0x18000cc6e  jz      short loc_18000CCE0
0x18000cc70  lea     r9, [rsp+0D8h+lParam]; lParam
0x18000cc75  mov     r8d, edi; wParam
0x18000cc78  mov     edx, 41Dh; Msg
0x18000cc7d  mov     rcx, rsi; hWnd
0x18000cc80  call    cs:__imp_SendMessageA
0x18000cc86  xor     edx, edx; Val
0x18000cc88  lea     rcx, [rsp+0D8h+var_B0]; void *
0x18000cc8d  lea     r8d, [rdx+78h]; Size
0x18000cc91  call    memset_0
0x18000cc96  mov     ecx, 12h; nIndex
0x18000cc9b  mov     dword ptr [rsp+0D8h+lParam], 80h
0x18000cca3  mov     dword ptr [rsp+0D8h+lParam+4], 2
0x18000ccab  call    cs:__imp_GetSysColor
0x18000ccb1  mov     ecx, 0Fh; nIndex
0x18000ccb6  mov     [rsp+0D8h+var_AC], eax
0x18000ccba  call    cs:__imp_GetSysColor
0x18000ccc0  lea     r9, [rsp+0D8h+lParam]; lParam
0x18000ccc5  mov     r8d, edi; wParam
0x18000ccc8  mov     edx, 406h; Msg
0x18000cccd  mov     [rsp+0D8h+var_A8], eax
0x18000ccd1  mov     rcx, rsi; hWnd
0x18000ccd4  call    cs:__imp_SendMessageA
0x18000ccda  inc     edi
0x18000ccdc  cmp     edi, ebp
0x18000ccde  jb      short loc_18000CC70
0x18000cce0  mov     rcx, [rsp+0D8h+var_38]
0x18000cce8  xor     rcx, rsp; StackCookie
0x18000cceb  call    __security_check_cookie
0x18000ccf0  add     rsp, 0B8h
0x18000ccf7  pop     rdi
0x18000ccf8  pop     rsi
0x18000ccf9  pop     rbp
0x18000ccfa  pop     rbx
0x18000ccfb  retn
```
