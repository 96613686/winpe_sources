# MSCryptOpenRsaProvider

- ea: `0x18004a200`
- end: `0x18004a35f`
- name: `MSCryptOpenRsaProvider`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a060`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800102a0`
- `0x18004a200`
- `0x18007f765`

## string_xrefs

- `0x18004a2be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004a2fd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004a33d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenRsaProvider(_QWORD *a1, const wchar_t *a2, int a3)
{
  _DWORD *v5; // rax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  char v11; // [rsp+30h] [rbp-18h]

  if ( !a1 )
  {
    v8 = -1073741811;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v11 = -102;
LABEL_15:
    WPP_SF_sDsd(
      v9[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      v11);
    return v8;
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v8 = -1073741811;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v11 = -95;
    goto LABEL_15;
  }
  if ( !wcscmp_0(a2, L"RSA") || !wcscmp_0(a2, L"RSA_SIGN") )
  {
    v5 = (_DWORD *)SafeAllocaAllocateFromHeap(16);
    if ( v5 )
    {
      *v5 = 16;
      v8 = 0;
      v5[1] = 1297306177;
      v5[2] = 196609;
      v5[3] = 40;
      *a1 = v5;
    }
    else
    {
      v8 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          v7,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          182);
    }
  }
  else
  {
    v8 = -1073741637;
    DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 429);
  }
  return v8;
}

```

## disassembly

```asm
0x18004a200  mov     [rsp+arg_0], rbx
0x18004a205  push    rdi
0x18004a206  sub     rsp, 40h
0x18004a20a  mov     rbx, rdx
0x18004a20d  mov     rdi, rcx
0x18004a210  test    rcx, rcx
0x18004a213  jz      short loc_18004A268
0x18004a215  test    r8d, 0FFFFFFFEh
0x18004a21c  jnz     loc_18004A2D7
0x18004a222  lea     rdx, aRsa; "RSA"
0x18004a229  mov     rcx, rbx; String1
0x18004a22c  call    wcscmp_0
0x18004a231  test    eax, eax
0x18004a233  jnz     loc_18004A320
0x18004a239  mov     ebx, 10h
0x18004a23e  mov     ecx, ebx
0x18004a240  call    SafeAllocaAllocateFromHeap
0x18004a245  test    rax, rax
0x18004a248  jz      short loc_18004A298
0x18004a24a  mov     [rax], ebx
0x18004a24c  xor     ebx, ebx
0x18004a24e  mov     dword ptr [rax+4], 4D535241h
0x18004a255  mov     dword ptr [rax+8], 30001h
0x18004a25c  mov     dword ptr [rax+0Ch], 28h ; '('
0x18004a263  mov     [rdi], rax
0x18004a266  jmp     short loc_18004A28A
0x18004a268  mov     ebx, 0C000000Dh
0x18004a26d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a274  lea     rax, WPP_GLOBAL_Control
0x18004a27b  cmp     rcx, rax
0x18004a27e  jz      short loc_18004A28A
0x18004a280  test    byte ptr [rcx+1Ch], 1
0x18004a284  jnz     loc_18004A316
0x18004a28a  mov     eax, ebx
0x18004a28c  mov     rbx, [rsp+48h+arg_0]
0x18004a291  add     rsp, 40h
0x18004a295  pop     rdi
0x18004a296  retn
0x18004a298  mov     ebx, 0C0000017h
0x18004a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2a4  lea     rax, WPP_GLOBAL_Control
0x18004a2ab  cmp     rcx, rax
0x18004a2ae  jz      short loc_18004A28A
0x18004a2b0  test    byte ptr [rcx+1Ch], 1
0x18004a2b4  jz      short loc_18004A28A
0x18004a2b6  mov     dword ptr [rsp+48h+var_18], 1B6h
0x18004a2be  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a2c5  mov     [rsp+48h+var_20], rax
0x18004a2ca  mov     [rsp+48h+var_28], 0C0000017h
0x18004a2d2  jmp     loc_180082856
0x18004a2d7  mov     ebx, 0C000000Dh
0x18004a2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2e3  lea     rax, WPP_GLOBAL_Control
0x18004a2ea  cmp     rcx, rax
0x18004a2ed  jz      short loc_18004A28A
0x18004a2ef  test    byte ptr [rcx+1Ch], 1
0x18004a2f3  jz      short loc_18004A28A
0x18004a2f5  mov     dword ptr [rsp+48h+var_18], 1A1h
0x18004a2fd  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a304  mov     [rsp+48h+var_20], rax
0x18004a309  mov     [rsp+48h+var_28], 0C000000Dh
0x18004a311  jmp     loc_180082856
0x18004a316  mov     dword ptr [rsp+48h+var_18], 19Ah
0x18004a31e  jmp     short loc_18004A2FD
0x18004a320  lea     rdx, aRsaSign; "RSA_SIGN"
0x18004a327  mov     rcx, rbx; String1
0x18004a32a  call    wcscmp_0
0x18004a32f  test    eax, eax
0x18004a331  jz      loc_18004A239
0x18004a337  mov     r9d, 1ADh
0x18004a33d  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a344  lea     rdx, aStatus; "Status"
0x18004a34b  mov     ecx, 0C00000BBh
0x18004a350  mov     ebx, 0C00000BBh
0x18004a355  call    DebugTraceError
0x18004a35a  jmp     loc_18004A28A
0x180082856  mov     rcx, [rcx+10h]
0x18008285a  lea     r9, aStatus; "Status"
0x180082861  call    WPP_SF_sDsd
0x180082866  nop
0x180082867  jmp     loc_18004A28A
```
