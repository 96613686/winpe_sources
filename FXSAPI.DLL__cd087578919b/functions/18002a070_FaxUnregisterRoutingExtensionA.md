# FaxUnregisterRoutingExtensionA

- ea: `0x18002a070`
- end: `0x18002a12f`
- name: `FaxUnregisterRoutingExtensionA`
- size: `191`
- prototype: `BOOL __stdcall(HANDLE hFaxHandle, LPCSTR lpctstrExtensionName)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002a070`
- `0x18002a140`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a0cc`
- `KERNEL32!GetLastError` at `0x18002a0cc`

## pseudocode

```c
BOOL __stdcall FaxUnregisterRoutingExtensionA(HANDLE hFaxHandle, LPCSTR lpctstrExtensionName)
{
  WCHAR *v4; // rdi
  DWORD LastError; // eax
  BOOL v6; // ebx

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  if ( !lpctstrExtensionName || (v4 = AnsiStringToUnicodeString(lpctstrExtensionName)) != 0 )
  {
    v6 = FaxUnregisterRoutingExtensionW(hFaxHandle, v4);
    pMemFree(v4);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, LastError);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002a070  push    rbx
0x18002a072  push    rsi
0x18002a073  push    rdi
0x18002a074  push    r14
0x18002a076  sub     rsp, 28h
0x18002a07a  mov     rbx, rdx
0x18002a07d  mov     rsi, rcx
0x18002a080  xor     edi, edi
0x18002a082  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a089  lea     r14, WPP_GLOBAL_Control
0x18002a090  cmp     rcx, r14
0x18002a093  jz      short loc_18002A0B7
0x18002a095  test    dword ptr [rcx+1Ch], 1000h
0x18002a09c  jz      short loc_18002A0B7
0x18002a09e  cmp     byte ptr [rcx+19h], 5
0x18002a0a2  jb      short loc_18002A0B7
0x18002a0a4  mov     rcx, [rcx+10h]
0x18002a0a8  lea     edx, [rdi+2Dh]
0x18002a0ab  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a0b2  call    WPP_SF_
0x18002a0b7  test    rbx, rbx
0x18002a0ba  jz      short loc_18002A10D
0x18002a0bc  mov     rcx, rbx; lpMultiByteStr
0x18002a0bf  call    AnsiStringToUnicodeString
0x18002a0c4  mov     rdi, rax
0x18002a0c7  test    rax, rax
0x18002a0ca  jnz     short loc_18002A10D
0x18002a0cc  call    cs:__imp_GetLastError
0x18002a0d3  nop     dword ptr [rax+rax+00h]
0x18002a0d8  mov     ebx, eax
0x18002a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0e1  cmp     rcx, r14
0x18002a0e4  jz      short loc_18002A122
0x18002a0e6  test    dword ptr [rcx+1Ch], 1000h
0x18002a0ed  jz      short loc_18002A122
0x18002a0ef  cmp     byte ptr [rcx+19h], 2
0x18002a0f3  jb      short loc_18002A122
0x18002a0f5  mov     rcx, [rcx+10h]
0x18002a0f9  lea     edx, [rdi+2Eh]
0x18002a0fc  mov     r9d, eax
0x18002a0ff  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a106  call    WPP_SF_d
0x18002a10b  jmp     short loc_18002A122
0x18002a10d  mov     rdx, rdi; lpctstrExtensionName
0x18002a110  mov     rcx, rsi; hFaxHandle
0x18002a113  call    FaxUnregisterRoutingExtensionW
0x18002a118  mov     rcx, rdi; lpMem
0x18002a11b  mov     ebx, eax
0x18002a11d  call    pMemFree
0x18002a122  mov     eax, ebx
0x18002a124  add     rsp, 28h
0x18002a128  pop     r14
0x18002a12a  pop     rdi
0x18002a12b  pop     rsi
0x18002a12c  pop     rbx
0x18002a12d  retn
```
