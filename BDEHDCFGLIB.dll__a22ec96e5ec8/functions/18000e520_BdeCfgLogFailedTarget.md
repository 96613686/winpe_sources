# BdeCfgLogFailedTarget

- ea: `0x18000e520`
- end: `0x18000e740`
- name: `BdeCfgLogFailedTarget`
- size: `544`
- prototype: `__int64 __fastcall(DWORD dwMessageId, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006860`
- `0x180006eb8`

## callees

- `0x18000e520`
- `0x18000eb40`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000e6ec`
- `ADVAPI32!EventWrite` at `0x18000e6ec`
- `KERNEL32!FormatMessageW` at `0x18000e5c4`
- `KERNEL32!FormatMessageW` at `0x18000e5c4`
- `KERNEL32!LocalFree` at `0x18000e713`
- `KERNEL32!LocalFree` at `0x18000e713`

## pseudocode

```c
__int64 __fastcall BdeCfgLogFailedTarget(DWORD dwMessageId, __int64 a2)
{
  signed int v3; // ebx
  DWORD v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // rax
  signed int v7; // eax
  WCHAR Buffer[4]; // [rsp+48h] [rbp-90h] BYREF
  DWORD v10; // [rsp+50h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-78h] BYREF
  const OLECHAR *v12; // [rsp+70h] [rbp-68h]
  __int64 v13; // [rsp+78h] [rbp-60h]
  __int64 v14; // [rsp+80h] [rbp-58h]
  int v15; // [rsp+88h] [rbp-50h]
  int v16; // [rsp+8Ch] [rbp-4Ch]
  int *v17; // [rsp+90h] [rbp-48h]
  int v18; // [rsp+98h] [rbp-40h]
  int v19; // [rsp+9Ch] [rbp-3Ch]
  __int64 v20; // [rsp+A0h] [rbp-38h]
  __int64 v21; // [rsp+A8h] [rbp-30h]
  __int64 v22; // [rsp+B0h] [rbp-28h]
  __int64 v23; // [rsp+B8h] [rbp-20h]
  int v24; // [rsp+C0h] [rbp-18h] BYREF
  wchar_t v25; // [rsp+C4h] [rbp-14h]

  v10 = dwMessageId;
  *(_QWORD *)Buffer = 0;
  v24 = *(_DWORD *)L" :";
  v25 = asc_18001763C[2];
  v3 = 0;
  if ( !g_EventRegistrationHandle )
    v3 = -1063256042;
  if ( v3 >= 0 )
  {
    UserData.Ptr = (ULONGLONG)&v10;
    *(_QWORD *)&UserData.Size = 4;
    v4 = FormatMessageW(0xBFFu, g_hInstance, dwMessageId, 0, Buffer, 0, 0);
    if ( v4 )
    {
      v12 = *(const OLECHAR **)Buffer;
      v13 = 2 * v4 + 2;
    }
    else
    {
      v12 = &word_180017638;
      v13 = 2;
      v3 = 0;
    }
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a2 + 2 * v6) );
    v14 = a2;
    v15 = 2 * v6 + 2;
    v16 = 0;
    LOWORD(v24) = *(_WORD *)(a2 + 520);
    do
      ++v5;
    while ( *((_WORD *)&v24 + v5) );
    v17 = &v24;
    v18 = 2 * v5 + 2;
    v19 = 0;
    v20 = a2 + 524;
    v21 = 4;
    v22 = a2 + 528;
    v23 = 4;
    v7 = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_LOG_FAILED_CHECK_TARGET, 6u, &UserData);
    if ( v7 )
    {
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      else
        v3 = v7;
    }
  }
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e520  mov     r11, rsp
0x18000e523  mov     [r11+10h], rbx
0x18000e527  mov     [r11+18h], rsi
0x18000e52b  push    rdi
0x18000e52c  sub     rsp, 0D0h
0x18000e533  mov     rax, cs:__security_cookie
0x18000e53a  xor     rax, rsp
0x18000e53d  mov     [rsp+0D8h+var_10], rax
0x18000e545  mov     rdi, rdx
0x18000e548  mov     [rsp+0D8h+var_88], ecx
0x18000e54c  xor     esi, esi
0x18000e54e  mov     qword ptr [rsp+0D8h+Buffer], rsi
0x18000e553  mov     eax, dword ptr cs:asc_18001763C; " :"
0x18000e559  mov     [r11-18h], eax
0x18000e55d  movzx   eax, word ptr cs:asc_18001763C+4; ""
0x18000e564  mov     [r11-14h], ax
0x18000e569  mov     ebx, esi
0x18000e56b  mov     eax, 0C0A00016h
0x18000e570  cmp     cs:?g_EventRegistrationHandle@@3_KA, rsi; unsigned __int64 g_EventRegistrationHandle
0x18000e577  cmovz   ebx, eax
0x18000e57a  mov     [rsp+0D8h+var_94], ebx
0x18000e57e  test    ebx, ebx
0x18000e580  js      loc_18000E709
0x18000e586  mov     [rsp+0D8h+var_98], 1
0x18000e58e  lea     rax, [rsp+0D8h+var_88]
0x18000e593  mov     [r11-78h], rax
0x18000e597  mov     qword ptr [r11-70h], 4
0x18000e59f  mov     [rsp+0D8h+Arguments], rsi; Arguments
0x18000e5a4  mov     [rsp+0D8h+nSize], esi; nSize
0x18000e5a8  lea     rax, [rsp+0D8h+Buffer]
0x18000e5ad  mov     [rsp+0D8h+lpBuffer], rax; lpBuffer
0x18000e5b2  xor     r9d, r9d; dwLanguageId
0x18000e5b5  mov     r8d, ecx; dwMessageId
0x18000e5b8  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18000e5bf  mov     ecx, 0BFFh; dwFlags
0x18000e5c4  call    cs:__imp_FormatMessageW
0x18000e5ca  mov     ecx, eax
0x18000e5cc  mov     [rsp+0D8h+var_98], 2
0x18000e5d4  test    eax, eax
0x18000e5d6  jnz     short loc_18000E5F5
0x18000e5d8  lea     rax, word_180017638
0x18000e5df  mov     [rsp+0D8h+var_68], rax
0x18000e5e4  mov     [rsp+0D8h+var_60], 2
0x18000e5ed  mov     ebx, esi
0x18000e5ef  mov     [rsp+0D8h+var_94], ebx
0x18000e5f3  jmp     short loc_18000E60E
0x18000e5f5  mov     rax, qword ptr [rsp+0D8h+Buffer]
0x18000e5fa  mov     [rsp+0D8h+var_68], rax
0x18000e5ff  lea     eax, ds:2[rcx*2]
0x18000e606  mov     dword ptr [rsp+0D8h+var_60], eax
0x18000e60a  mov     dword ptr [rsp+0D8h+var_60+4], esi
0x18000e60e  mov     [rsp+0D8h+var_98], 3
0x18000e616  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e61a  mov     rax, rcx
0x18000e61d  inc     rax
0x18000e620  cmp     [rdi+rax*2], si
0x18000e624  jnz     short loc_18000E61D
0x18000e626  mov     [rsp+0D8h+var_58], rdi
0x18000e62e  lea     eax, ds:2[rax*2]
0x18000e635  mov     [rsp+0D8h+var_50], eax
0x18000e63c  mov     [rsp+0D8h+var_4C], esi
0x18000e643  movzx   eax, word ptr [rdi+208h]
0x18000e64a  mov     [rsp+0D8h+var_18], ax
0x18000e652  mov     [rsp+0D8h+var_98], 4
0x18000e65a  lea     rax, [rsp+0D8h+var_18]
0x18000e662  inc     rcx
0x18000e665  cmp     [rax+rcx*2], si
0x18000e669  jnz     short loc_18000E662
0x18000e66b  lea     rax, [rsp+0D8h+var_18]
0x18000e673  mov     [rsp+0D8h+var_48], rax
0x18000e67b  lea     eax, ds:2[rcx*2]
0x18000e682  mov     [rsp+0D8h+var_40], eax
0x18000e689  mov     [rsp+0D8h+var_3C], esi
0x18000e690  mov     [rsp+0D8h+var_98], 5
0x18000e698  lea     rax, [rdi+20Ch]
0x18000e69f  mov     [rsp+0D8h+var_38], rax
0x18000e6a7  mov     [rsp+0D8h+var_30], 4
0x18000e6b3  mov     r8d, 6; UserDataCount
0x18000e6b9  mov     [rsp+0D8h+var_98], r8d
0x18000e6be  lea     rax, [rdi+210h]
0x18000e6c5  mov     [rsp+0D8h+var_28], rax
0x18000e6cd  mov     [rsp+0D8h+var_20], 4
0x18000e6d9  lea     r9, [rsp+0D8h+UserData]; UserData
0x18000e6de  lea     rdx, BDECFG_EVT_LOG_FAILED_CHECK_TARGET; EventDescriptor
0x18000e6e5  mov     rcx, cs:?g_EventRegistrationHandle@@3_KA; RegHandle
0x18000e6ec  call    cs:__imp_EventWrite
0x18000e6f2  test    eax, eax
0x18000e6f4  jz      short loc_18000E709
0x18000e6f6  jg      short loc_18000E6FC
0x18000e6f8  mov     ebx, eax
0x18000e6fa  jmp     short loc_18000E705
0x18000e6fc  movzx   ebx, ax
0x18000e6ff  or      ebx, 80070000h
0x18000e705  mov     [rsp+0D8h+var_94], ebx
0x18000e709  mov     rcx, qword ptr [rsp+0D8h+Buffer]; hMem
0x18000e70e  test    rcx, rcx
0x18000e711  jz      short loc_18000E719
0x18000e713  call    cs:__imp_LocalFree
0x18000e719  mov     eax, ebx
0x18000e71b  mov     rcx, [rsp+0D8h+var_10]
0x18000e723  xor     rcx, rsp; StackCookie
0x18000e726  call    __security_check_cookie
0x18000e72b  lea     r11, [rsp+0D8h+var_8]
0x18000e733  mov     rbx, [r11+18h]
0x18000e737  mov     rsi, [r11+20h]
0x18000e73b  mov     rsp, r11
0x18000e73e  pop     rdi
0x18000e73f  retn
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
