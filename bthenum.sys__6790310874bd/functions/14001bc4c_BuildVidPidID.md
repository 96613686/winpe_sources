# BuildVidPidID

- ea: `0x14001bc4c`
- end: `0x14001bd96`
- name: `BuildVidPidID`
- size: `330`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140018750`
- `0x140019058`

## callees

- `0x140001294`
- `0x140007d00`
- `0x14001bc4c`

## pseudocode

```c
__int64 __fastcall BuildVidPidID(__int64 a1, wchar_t *a2, unsigned int a3)
{
  int v4; // r9d
  int v5; // r10d
  bool v6; // zf
  __int64 v7; // rax
  size_t v8; // rdx
  int v9; // r8d
  NTSTATUS v10; // eax
  __int64 v12; // rax
  int v13; // [rsp+30h] [rbp-78h]
  int v14; // [rsp+38h] [rbp-70h]
  int v15; // [rsp+38h] [rbp-70h]
  int v16; // [rsp+40h] [rbp-68h]
  int v17; // [rsp+48h] [rbp-60h]
  int v18; // [rsp+50h] [rbp-58h]
  __int64 v19; // [rsp+60h] [rbp-48h] BYREF
  int v20; // [rsp+68h] [rbp-40h]
  __int64 v21; // [rsp+70h] [rbp-38h] BYREF
  int v22; // [rsp+78h] [rbp-30h]
  _BYTE v23[22]; // [rsp+80h] [rbp-28h] BYREF

  v4 = *(unsigned __int16 *)(a1 + 1588);
  v5 = *(unsigned __int16 *)(a1 + 1596);
  v6 = *(_DWORD *)(a1 + 2880) == 0;
  v21 = *(_QWORD *)L"_VID&";
  v22 = *(_DWORD *)L"&";
  v19 = *(_QWORD *)L"_PID&";
  v20 = *(_DWORD *)L"&";
  v7 = *(_QWORD *)(a1 + 56);
  v8 = a3;
  v9 = *(unsigned __int16 *)(a1 + 1590);
  *(_OWORD *)v23 = *(_OWORD *)L"_HCIBYPASS";
  *(_QWORD *)&v23[14] = *(_QWORD *)L"ASS";
  if ( v6 )
  {
    v17 = v9;
    v15 = v4;
    v13 = v5;
    v10 = RtlStringCchPrintfW(a2, v8, L"%s%s%s%04x%04x%s%04x", busId, v7, &v21, v13, v15, &v19, v17);
  }
  else
  {
    v18 = v9;
    v16 = v4;
    v14 = v5;
    v10 = RtlStringCchPrintfW(a2, v8, L"%s%s%s%s%04x%04x%s%04x", busId, v7, v23, &v21, v14, v16, &v19, v18);
  }
  if ( v10 < 0 )
    return 0;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  return (unsigned int)(v12 + 1);
}

```

## disassembly

```asm
0x14001bc4c  mov     r11, rsp
0x14001bc4f  mov     [r11+20h], rbx
0x14001bc53  push    rdi
0x14001bc54  sub     rsp, 0A0h
0x14001bc5b  mov     rax, cs:__security_cookie
0x14001bc62  xor     rax, rsp
0x14001bc65  mov     [rsp+0A8h+var_10], rax
0x14001bc6d  mov     eax, dword ptr cs:aVid+8; "&"
0x14001bc73  mov     rbx, rdx
0x14001bc76  movsd   xmm0, qword ptr cs:aVid; "_VID&"
0x14001bc7e  xor     edi, edi
0x14001bc80  movsd   xmm1, qword ptr cs:aHcibypass+0Eh; "ASS"
0x14001bc88  movzx   r9d, word ptr [rcx+634h]
0x14001bc90  movzx   r10d, word ptr [rcx+63Ch]
0x14001bc98  cmp     [rcx+0B40h], edi
0x14001bc9e  movsd   [rsp+0A8h+var_38], xmm0
0x14001bca4  movsd   xmm0, qword ptr cs:aPid; "_PID&"
0x14001bcac  mov     [rsp+0A8h+var_30], eax
0x14001bcb0  mov     eax, dword ptr cs:aPid+8; "&"
0x14001bcb6  movsd   [rsp+0A8h+var_48], xmm0
0x14001bcbc  movups  xmm0, xmmword ptr cs:aHcibypass; "_HCIBYPASS"
0x14001bcc3  mov     [rsp+0A8h+var_40], eax
0x14001bcc7  mov     rax, [rcx+38h]
0x14001bccb  mov     edx, r8d; cchDest
0x14001bcce  movzx   r8d, word ptr [rcx+636h]
0x14001bcd6  lea     rcx, [r11-48h]
0x14001bcda  movups  xmmword ptr [r11-28h], xmm0
0x14001bcdf  movsd   qword ptr [r11-1Ah], xmm1
0x14001bce5  jz      short loc_14001BD24
0x14001bce7  mov     [r11-58h], r8d
0x14001bceb  lea     r8, aSSSS04x04xS04x; "%s%s%s%s%04x%04x%s%04x"
0x14001bcf2  mov     [r11-60h], rcx
0x14001bcf6  lea     rcx, [r11-38h]
0x14001bcfa  mov     [r11-68h], r9d
0x14001bcfe  lea     r9, busId; "BTHENUM\\"
0x14001bd05  mov     [r11-70h], r10d
0x14001bd09  mov     [r11-78h], rcx
0x14001bd0d  lea     rcx, [r11-28h]
0x14001bd11  mov     [r11-80h], rcx
0x14001bd15  mov     rcx, rbx; pszDest
0x14001bd18  mov     [rsp+0A8h+var_88], rax
0x14001bd1d  call    RtlStringCchPrintfW
0x14001bd22  jmp     short loc_14001BD5D
0x14001bd24  mov     [rsp+0A8h+var_60], r8d
0x14001bd29  lea     r8, aSSS04x04xS04x; "%s%s%s%04x%04x%s%04x"
0x14001bd30  mov     [rsp+0A8h+var_68], rcx
0x14001bd35  lea     rcx, [rsp+0A8h+var_38]
0x14001bd3a  mov     [rsp+0A8h+var_70], r9d
0x14001bd3f  lea     r9, busId; "BTHENUM\\"
0x14001bd46  mov     [rsp+0A8h+var_78], r10d
0x14001bd4b  mov     [rsp+0A8h+var_80], rcx
0x14001bd50  mov     rcx, rbx; pszDest
0x14001bd53  mov     [rsp+0A8h+var_88], rax
0x14001bd58  call    RtlStringCchPrintfW
0x14001bd5d  test    eax, eax
0x14001bd5f  jns     short loc_14001BD65
0x14001bd61  xor     eax, eax
0x14001bd63  jmp     short loc_14001BD74
0x14001bd65  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bd69  inc     rax
0x14001bd6c  cmp     [rbx+rax*2], di
0x14001bd70  jnz     short loc_14001BD69
0x14001bd72  inc     eax
0x14001bd74  mov     rcx, [rsp+0A8h+var_10]
0x14001bd7c  xor     rcx, rsp; StackCookie
0x14001bd7f  call    __security_check_cookie
0x14001bd84  mov     rbx, [rsp+0A8h+arg_18]
0x14001bd8c  add     rsp, 0A0h
0x14001bd93  pop     rdi
0x14001bd94  retn
```
