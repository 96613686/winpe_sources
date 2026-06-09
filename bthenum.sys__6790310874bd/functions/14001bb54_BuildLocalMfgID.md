# BuildLocalMfgID

- ea: `0x14001bb54`
- end: `0x14001bc46`
- name: `BuildLocalMfgID`
- size: `242`
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
- `0x14001bb54`

## pseudocode

```c
__int64 __fastcall BuildLocalMfgID(__int64 a1, wchar_t *a2, unsigned int a3)
{
  __int64 v3; // rax
  size_t v5; // rdx
  int v6; // r8d
  bool v7; // zf
  NTSTATUS v8; // eax
  __int64 v10; // rax
  int v11; // [rsp+30h] [rbp-58h]
  int v12; // [rsp+38h] [rbp-50h]
  _BYTE v13[22]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v14[22]; // [rsp+58h] [rbp-30h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  *(_OWORD *)v13 = *(_OWORD *)L"_LOCALMFG&";
  v5 = a3;
  v6 = *(unsigned __int16 *)(a1 + 1594);
  v7 = *(_DWORD *)(a1 + 2880) == 0;
  *(_QWORD *)&v13[14] = *(_QWORD *)L"FG&";
  *(_OWORD *)v14 = *(_OWORD *)L"_HCIBYPASS";
  *(_QWORD *)&v14[14] = *(_QWORD *)L"ASS";
  if ( v7 )
  {
    v11 = v6;
    v8 = RtlStringCchPrintfW(a2, v5, L"%s%s%s%04x", busId, v3, v13, v11);
  }
  else
  {
    v12 = v6;
    v8 = RtlStringCchPrintfW(a2, v5, L"%s%s%s%s%04x", busId, v3, v14, v13, v12);
  }
  if ( v8 < 0 )
    return 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  return (unsigned int)(v10 + 1);
}

```

## disassembly

```asm
0x14001bb54  mov     r11, rsp
0x14001bb57  mov     [r11+20h], rbx
0x14001bb5b  push    rdi
0x14001bb5c  sub     rsp, 80h
0x14001bb63  mov     rax, cs:__security_cookie
0x14001bb6a  xor     rax, rsp
0x14001bb6d  mov     [rsp+88h+var_18], rax
0x14001bb72  movups  xmm0, xmmword ptr cs:aLocalmfg; "_LOCALMFG&"
0x14001bb79  lea     r9, busId; "BTHENUM\\"
0x14001bb80  mov     rax, [rcx+38h]
0x14001bb84  movsd   xmm1, qword ptr cs:aLocalmfg+0Eh; "FG&"
0x14001bb8c  mov     rbx, rdx
0x14001bb8f  movups  [rsp+88h+var_48], xmm0
0x14001bb94  xor     edi, edi
0x14001bb96  mov     edx, r8d; cchDest
0x14001bb99  movups  xmm0, xmmword ptr cs:aHcibypass; "_HCIBYPASS"
0x14001bba0  movzx   r8d, word ptr [rcx+63Ah]
0x14001bba8  cmp     [rcx+0B40h], edi
0x14001bbae  lea     rcx, [r11-48h]
0x14001bbb2  movsd   qword ptr [rsp+88h+var_48+0Eh], xmm1
0x14001bbb8  movsd   xmm1, qword ptr cs:aHcibypass+0Eh; "ASS"
0x14001bbc0  movups  xmmword ptr [rsp+88h+var_30], xmm0
0x14001bbc5  movsd   qword ptr [rsp+88h+var_30+0Eh], xmm1
0x14001bbcb  jz      short loc_14001BBF2
0x14001bbcd  mov     [r11-50h], r8d
0x14001bbd1  lea     r8, aSSSS04x; "%s%s%s%s%04x"
0x14001bbd8  mov     [r11-58h], rcx
0x14001bbdc  lea     rcx, [r11-30h]
0x14001bbe0  mov     [r11-60h], rcx
0x14001bbe4  mov     rcx, rbx; pszDest
0x14001bbe7  mov     [r11-68h], rax
0x14001bbeb  call    RtlStringCchPrintfW
0x14001bbf0  jmp     short loc_14001BC10
0x14001bbf2  mov     [rsp+88h+var_58], r8d
0x14001bbf7  lea     r8, aSSS04x; "%s%s%s%04x"
0x14001bbfe  mov     [rsp+88h+var_60], rcx
0x14001bc03  mov     rcx, rbx; pszDest
0x14001bc06  mov     [rsp+88h+var_68], rax
0x14001bc0b  call    RtlStringCchPrintfW
0x14001bc10  test    eax, eax
0x14001bc12  jns     short loc_14001BC18
0x14001bc14  xor     eax, eax
0x14001bc16  jmp     short loc_14001BC27
0x14001bc18  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bc1c  inc     rax
0x14001bc1f  cmp     [rbx+rax*2], di
0x14001bc23  jnz     short loc_14001BC1C
0x14001bc25  inc     eax
0x14001bc27  mov     rcx, [rsp+88h+var_18]
0x14001bc2c  xor     rcx, rsp; StackCookie
0x14001bc2f  call    __security_check_cookie
0x14001bc34  mov     rbx, [rsp+88h+arg_18]
0x14001bc3c  add     rsp, 80h
0x14001bc43  pop     rdi
0x14001bc44  retn
```
