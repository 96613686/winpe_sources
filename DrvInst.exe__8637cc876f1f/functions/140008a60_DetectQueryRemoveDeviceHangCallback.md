# DetectQueryRemoveDeviceHangCallback

- ea: `0x140008a60`
- end: `0x140008b9d`
- name: `DetectQueryRemoveDeviceHangCallback`
- size: `317`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400070bc`
- `0x140008a60`
- `0x140009708`
- `0x140045f30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140008a95`
- `msvcrt!_wcsicmp` at `0x140008a95`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008ac7`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008b2d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008b6a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008ac7`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008b2d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140008b6a`

## pseudocode

```c
__int64 __fastcall DetectQueryRemoveDeviceHangCallback(unsigned __int16 *a1, int a2, int a3, __int64 a4)
{
  unsigned int v8; // edi
  unsigned int v9; // esi
  __int64 v10; // rcx
  wchar_t pszDest[64]; // [rsp+30h] [rbp-A8h] BYREF

  if ( !_wcsicmp(a1, *(const wchar_t **)a4) )
    *(_DWORD *)(a4 + 412) = a2;
  if ( !*(_DWORD *)(a4 + 408) )
    DevRtlWriteTextLog(*(_QWORD *)(a4 + 416), 1, 65540, "Detecting devices pending query-removal:");
  ++*(_DWORD *)(a4 + 408);
  v8 = 0;
  pszDest[0] = 0;
  v9 = a3 + 1;
  if ( v9 )
  {
    do
    {
      if ( StringCchCatW(pszDest, 0x40u, L"  ") < 0 )
        break;
      ++v8;
    }
    while ( v8 < v9 );
  }
  v10 = *(_QWORD *)(a4 + 416);
  if ( (a2 & 0x20000) != 0 )
  {
    DevRtlWriteTextLog(v10, 1, 2, "%ws%ws [QR]", pszDest, a1);
    if ( (int)StringCchCopyW((unsigned __int16 *)(a4 + 8), 0xC8u, (size_t *)a1) < 0 )
      *(_WORD *)(a4 + 8) = 0;
  }
  else
  {
    DevRtlWriteTextLog(v10, 1, 4, "%ws%ws", pszDest, a1);
  }
  return 1;
}

```

## disassembly

```asm
0x140008a60  mov     [rsp+arg_8], rbx
0x140008a65  mov     [rsp+arg_10], rbp
0x140008a6a  push    rsi
0x140008a6b  push    rdi
0x140008a6c  push    r14
0x140008a6e  sub     rsp, 0C0h
0x140008a75  mov     rax, cs:__security_cookie
0x140008a7c  xor     rax, rsp
0x140008a7f  mov     [rsp+0D8h+var_28], rax
0x140008a87  mov     ebp, edx
0x140008a89  mov     rbx, r9
0x140008a8c  mov     rdx, [r9]; String2
0x140008a8f  mov     esi, r8d
0x140008a92  mov     r14, rcx
0x140008a95  call    cs:__imp__wcsicmp
0x140008a9b  test    eax, eax
0x140008a9d  jnz     short loc_140008AA5
0x140008a9f  mov     [rbx+19Ch], ebp
0x140008aa5  cmp     dword ptr [rbx+198h], 0
0x140008aac  jnz     short loc_140008ACD
0x140008aae  mov     rcx, [rbx+1A0h]
0x140008ab5  lea     r9, aDetectingDevic; "Detecting devices pending query-removal"...
0x140008abc  mov     edx, 1
0x140008ac1  mov     r8d, 10004h
0x140008ac7  call    cs:__imp_DevRtlWriteTextLog
0x140008acd  inc     dword ptr [rbx+198h]
0x140008ad3  xor     eax, eax
0x140008ad5  xor     edi, edi
0x140008ad7  mov     [rsp+0D8h+pszDest], ax
0x140008adc  add     esi, 1
0x140008adf  jz      short loc_140008B01
0x140008ae1  lea     r8, pszSrc; "  "
0x140008ae8  mov     edx, 40h ; '@'; cchDest
0x140008aed  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x140008af2  call    StringCchCatW
0x140008af7  test    eax, eax
0x140008af9  js      short loc_140008B01
0x140008afb  inc     edi
0x140008afd  cmp     edi, esi
0x140008aff  jb      short loc_140008AE1
0x140008b01  mov     rcx, [rbx+1A0h]
0x140008b08  mov     [rsp+0D8h+var_B0], r14
0x140008b0d  bt      ebp, 11h
0x140008b11  jnb     short loc_140008B50
0x140008b13  mov     edx, 1
0x140008b18  lea     rax, [rsp+0D8h+pszDest]
0x140008b1d  lea     r9, aWsWsQr; "%ws%ws [QR]"
0x140008b24  mov     [rsp+0D8h+var_B8], rax
0x140008b29  lea     r8d, [rdx+1]
0x140008b2d  call    cs:__imp_DevRtlWriteTextLog
0x140008b33  mov     r8, r14; unsigned __int16 *
0x140008b36  lea     rcx, [rbx+8]; unsigned __int16 *
0x140008b3a  mov     edx, 0C8h; unsigned __int64
0x140008b3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008b44  test    eax, eax
0x140008b46  jns     short loc_140008B70
0x140008b48  xor     eax, eax
0x140008b4a  mov     [rbx+8], ax
0x140008b4e  jmp     short loc_140008B70
0x140008b50  lea     rdx, [rsp+0D8h+pszDest]
0x140008b55  mov     [rsp+0D8h+var_B8], rdx
0x140008b5a  lea     r9, aWsWs; "%ws%ws"
0x140008b61  mov     edx, 1
0x140008b66  lea     r8d, [rdx+3]
0x140008b6a  call    cs:__imp_DevRtlWriteTextLog
0x140008b70  mov     eax, 1
0x140008b75  mov     rcx, [rsp+0D8h+var_28]
0x140008b7d  xor     rcx, rsp; StackCookie
0x140008b80  call    __security_check_cookie
0x140008b85  lea     r11, [rsp+0D8h+var_18]
0x140008b8d  mov     rbx, [r11+28h]
0x140008b91  mov     rbp, [r11+30h]
0x140008b95  mov     rsp, r11
0x140008b98  pop     r14
0x140008b9a  pop     rdi
0x140008b9b  pop     rsi
0x140008b9c  retn
```
