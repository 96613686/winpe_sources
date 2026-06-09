# BdeCfgLogWarning

- ea: `0x18000eb40`
- end: `0x18000ec6a`
- name: `BdeCfgLogWarning`
- size: `298`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800084a4`
- `0x18000d510`
- `0x1800101a0`

## callees

- `0x18000eb40`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000ec25`
- `ADVAPI32!EventWrite` at `0x18000ec25`
- `KERNEL32!FormatMessageW` at `0x18000ebc5`
- `KERNEL32!FormatMessageW` at `0x18000ebc5`
- `KERNEL32!LocalFree` at `0x18000ec4c`
- `KERNEL32!LocalFree` at `0x180014318`
- `KERNEL32!LocalFree` at `0x18000ec4c`
- `KERNEL32!LocalFree` at `0x180014318`

## pseudocode

```c
__int64 __fastcall BdeCfgLogWarning(DWORD dwMessageId)
{
  signed int v1; // ebx
  DWORD v2; // ecx
  signed int v3; // eax
  HLOCAL hMem; // [rsp+48h] [rbp-40h] BYREF
  DWORD v6; // [rsp+50h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-30h] BYREF
  const OLECHAR *v8; // [rsp+68h] [rbp-20h]
  __int64 v9; // [rsp+70h] [rbp-18h]

  v6 = dwMessageId;
  hMem = 0;
  v1 = 0;
  if ( !g_EventRegistrationHandle )
    v1 = -1063256042;
  if ( v1 >= 0 )
  {
    UserData.Ptr = (ULONGLONG)&v6;
    *(_QWORD *)&UserData.Size = 4;
    v2 = FormatMessageW(0xBFFu, g_hInstance, dwMessageId, 0, (LPWSTR)&hMem, 0, 0);
    if ( v2 )
    {
      v8 = (const OLECHAR *)hMem;
      v9 = 2 * v2 + 2;
    }
    else
    {
      v8 = &word_180017638;
      v9 = 2;
      v1 = 0;
    }
    v3 = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_WARNING, 2u, &UserData);
    if ( v3 )
    {
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      else
        v1 = v3;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000eb40  mov     r11, rsp
0x18000eb43  push    rbx
0x18000eb44  sub     rsp, 80h
0x18000eb4b  mov     rax, cs:__security_cookie
0x18000eb52  xor     rax, rsp
0x18000eb55  mov     [rsp+88h+var_10], rax
0x18000eb5a  mov     [rsp+88h+var_38], ecx
0x18000eb5e  mov     qword ptr [r11-40h], 0
0x18000eb66  xor     ebx, ebx
0x18000eb68  mov     eax, 0C0A00016h
0x18000eb6d  cmp     cs:?g_EventRegistrationHandle@@3_KA, rbx; unsigned __int64 g_EventRegistrationHandle
0x18000eb74  cmovz   ebx, eax
0x18000eb77  mov     [rsp+88h+var_44], ebx
0x18000eb7b  test    ebx, ebx
0x18000eb7d  js      loc_18000EC42
0x18000eb83  mov     [rsp+88h+var_48], 1
0x18000eb8b  lea     rax, [r11-38h]
0x18000eb8f  mov     [r11-30h], rax
0x18000eb93  mov     qword ptr [r11-28h], 4
0x18000eb9b  mov     qword ptr [r11-58h], 0
0x18000eba3  mov     [rsp+88h+nSize], 0; nSize
0x18000ebab  lea     rax, [r11-40h]
0x18000ebaf  mov     [r11-68h], rax
0x18000ebb3  xor     r9d, r9d; dwLanguageId
0x18000ebb6  mov     r8d, ecx; dwMessageId
0x18000ebb9  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18000ebc0  mov     ecx, 0BFFh; dwFlags
0x18000ebc5  call    cs:__imp_FormatMessageW
0x18000ebcb  mov     ecx, eax
0x18000ebcd  mov     r8d, 2; UserDataCount
0x18000ebd3  mov     [rsp+88h+var_48], r8d
0x18000ebd8  test    eax, eax
0x18000ebda  jnz     short loc_18000EBF5
0x18000ebdc  lea     rax, word_180017638
0x18000ebe3  mov     [rsp+88h+var_20], rax
0x18000ebe8  mov     [rsp+88h+var_18], r8
0x18000ebed  xor     ebx, ebx
0x18000ebef  mov     [rsp+88h+var_44], ebx
0x18000ebf3  jmp     short loc_18000EC12
0x18000ebf5  mov     rax, [rsp+88h+hMem]
0x18000ebfa  mov     [rsp+88h+var_20], rax
0x18000ebff  lea     eax, ds:2[rcx*2]
0x18000ec06  mov     dword ptr [rsp+88h+var_18], eax
0x18000ec0a  mov     dword ptr [rsp+88h+var_18+4], 0
0x18000ec12  lea     r9, [rsp+88h+UserData]; UserData
0x18000ec17  lea     rdx, BDECFG_EVT_WARNING; EventDescriptor
0x18000ec1e  mov     rcx, cs:?g_EventRegistrationHandle@@3_KA; RegHandle
0x18000ec25  call    cs:__imp_EventWrite
0x18000ec2b  test    eax, eax
0x18000ec2d  jz      short loc_18000EC42
0x18000ec2f  jg      short loc_18000EC35
0x18000ec31  mov     ebx, eax
0x18000ec33  jmp     short loc_18000EC3E
0x18000ec35  movzx   ebx, ax
0x18000ec38  or      ebx, 80070000h
0x18000ec3e  mov     [rsp+88h+var_44], ebx
0x18000ec42  mov     rcx, [rsp+88h+hMem]; hMem
0x18000ec47  test    rcx, rcx
0x18000ec4a  jz      short loc_18000EC52
0x18000ec4c  call    cs:__imp_LocalFree
0x18000ec52  mov     eax, ebx
0x18000ec54  mov     rcx, [rsp+88h+var_10]
0x18000ec59  xor     rcx, rsp; StackCookie
0x18000ec5c  call    __security_check_cookie
0x18000ec61  add     rsp, 80h
0x18000ec68  pop     rbx
0x18000ec69  retn
0x180014306  push    rbp
0x180014308  sub     rsp, 40h
0x18001430c  mov     rbp, rdx
0x18001430f  mov     rcx, [rbp+48h]; hMem
0x180014313  test    rcx, rcx
0x180014316  jz      short loc_18001431F
0x180014318  call    cs:__imp_LocalFree
0x18001431e  nop
0x18001431f  add     rsp, 40h
0x180014323  pop     rbp
0x180014324  retn
```
