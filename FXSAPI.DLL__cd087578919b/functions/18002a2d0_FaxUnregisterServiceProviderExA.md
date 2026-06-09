# FaxUnregisterServiceProviderExA

- ea: `0x18002a2d0`
- end: `0x18002a38f`
- name: `FaxUnregisterServiceProviderExA`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002a2d0`
- `0x18002a3a0`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a32c`
- `KERNEL32!GetLastError` at `0x18002a32c`

## pseudocode

```c
__int64 __fastcall FaxUnregisterServiceProviderExA(__int64 a1, const CHAR *a2)
{
  WCHAR *v4; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  if ( !a2 || (v4 = AnsiStringToUnicodeString(a2)) != 0 )
  {
    v7 = FaxUnregisterServiceProviderExW(a1, v4);
    pMemFree(v4);
    return v7;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, LastError);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002a2d0  push    rbx
0x18002a2d2  push    rsi
0x18002a2d3  push    rdi
0x18002a2d4  push    r14
0x18002a2d6  sub     rsp, 28h
0x18002a2da  mov     rbx, rdx
0x18002a2dd  mov     rsi, rcx
0x18002a2e0  xor     edi, edi
0x18002a2e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2e9  lea     r14, WPP_GLOBAL_Control
0x18002a2f0  cmp     rcx, r14
0x18002a2f3  jz      short loc_18002A317
0x18002a2f5  test    dword ptr [rcx+1Ch], 1000h
0x18002a2fc  jz      short loc_18002A317
0x18002a2fe  cmp     byte ptr [rcx+19h], 5
0x18002a302  jb      short loc_18002A317
0x18002a304  mov     rcx, [rcx+10h]
0x18002a308  lea     edx, [rdi+3Dh]
0x18002a30b  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a312  call    WPP_SF_
0x18002a317  test    rbx, rbx
0x18002a31a  jz      short loc_18002A36D
0x18002a31c  mov     rcx, rbx; lpMultiByteStr
0x18002a31f  call    AnsiStringToUnicodeString
0x18002a324  mov     rdi, rax
0x18002a327  test    rax, rax
0x18002a32a  jnz     short loc_18002A36D
0x18002a32c  call    cs:__imp_GetLastError
0x18002a333  nop     dword ptr [rax+rax+00h]
0x18002a338  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a33f  cmp     rcx, r14
0x18002a342  jz      short loc_18002A369
0x18002a344  test    dword ptr [rcx+1Ch], 1000h
0x18002a34b  jz      short loc_18002A369
0x18002a34d  cmp     byte ptr [rcx+19h], 2
0x18002a351  jb      short loc_18002A369
0x18002a353  mov     rcx, [rcx+10h]
0x18002a357  lea     edx, [rdi+3Eh]
0x18002a35a  mov     r9d, eax
0x18002a35d  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x18002a364  call    WPP_SF_d
0x18002a369  xor     eax, eax
0x18002a36b  jmp     short loc_18002A384
0x18002a36d  mov     rdx, rdi
0x18002a370  mov     rcx, rsi
0x18002a373  call    FaxUnregisterServiceProviderExW
0x18002a378  mov     rcx, rdi; lpMem
0x18002a37b  mov     ebx, eax
0x18002a37d  call    pMemFree
0x18002a382  mov     eax, ebx
0x18002a384  add     rsp, 28h
0x18002a388  pop     r14
0x18002a38a  pop     rdi
0x18002a38b  pop     rsi
0x18002a38c  pop     rbx
0x18002a38d  retn
```
