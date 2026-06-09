# VerifyRsaFullPrivateBlob

- ea: `0x180009454`
- end: `0x180009562`
- name: `VerifyRsaFullPrivateBlob`
- size: `270`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008890`
- `0x18000e7fc`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x180009454`

## string_xrefs

- `0x180009500`: `onecore\ds\security\cryptoapi\ncrypt\common\translate.c`
- `0x180009530`: `onecore\ds\security\cryptoapi\ncrypt\common\translate.c`

## pseudocode

```c
__int64 __fastcall VerifyRsaFullPrivateBlob(_DWORD *a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v5; // r9d
  unsigned int v6; // edx
  unsigned int v7; // r11d
  unsigned int v8; // r8d
  unsigned int v9; // r10d
  unsigned int v10; // ecx
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rcx

  if ( a1 && a2 >= 0x18 )
  {
    v5 = a1[1];
    if ( *a1 != 859919186
      || (v6 = a1[3], v5 >> 3 != v6)
      || (v7 = a1[2], v7 > v6)
      || (v8 = a1[4], v8 > v6)
      || (v9 = a1[5], v9 > v6) )
    {
      v11 = 309;
      goto LABEL_14;
    }
    v10 = v7 + v6 + v9 + v8 + 24;
    if ( a2 < v10 + v6 + v9 + 2 * v8 )
    {
      v11 = 330;
LABEL_14:
      v13 = 2148073477LL;
      v12 = -2146893819;
      goto LABEL_15;
    }
    if ( v5 - 256 > 0x3F00 )
    {
      v12 = -2146893783;
      v11 = 338;
      v13 = 2148073513LL;
LABEL_15:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\translate.c", v11);
      return v12;
    }
    *a3 = v10;
    return 0;
  }
  else
  {
    v12 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\translate.c",
        40);
  }
  return v12;
}

```

## disassembly

```asm
0x180009454  mov     [rsp+arg_0], rbx
0x180009459  push    rdi
0x18000945a  sub     rsp, 40h
0x18000945e  mov     rdi, r8
0x180009461  mov     ebx, edx
0x180009463  test    rcx, rcx
0x180009466  jz      loc_18000950E
0x18000946c  cmp     edx, 18h
0x18000946f  jb      loc_18000950E
0x180009475  cmp     dword ptr [rcx], 33415352h
0x18000947b  mov     r9d, [rcx+4]
0x18000947f  jnz     short loc_1800094EC
0x180009481  mov     edx, [rcx+0Ch]
0x180009484  mov     eax, r9d
0x180009487  shr     eax, 3
0x18000948a  cmp     eax, edx
0x18000948c  jnz     short loc_1800094EC
0x18000948e  mov     r11d, [rcx+8]
0x180009492  cmp     r11d, edx
0x180009495  ja      short loc_1800094EC
0x180009497  mov     r8d, [rcx+10h]
0x18000949b  cmp     r8d, edx
0x18000949e  ja      short loc_1800094EC
0x1800094a0  mov     r10d, [rcx+14h]
0x1800094a4  cmp     r10d, edx
0x1800094a7  ja      short loc_1800094EC
0x1800094a9  lea     ecx, [r8+18h]
0x1800094ad  add     ecx, r10d
0x1800094b0  lea     eax, [r10+r8*2]
0x1800094b4  add     ecx, edx
0x1800094b6  add     eax, edx
0x1800094b8  add     ecx, r11d
0x1800094bb  add     eax, ecx
0x1800094bd  cmp     ebx, eax
0x1800094bf  jnb     short loc_1800094C9
0x1800094c1  mov     r9d, 14Ah
0x1800094c7  jmp     short loc_1800094F2
0x1800094c9  lea     eax, [r9-100h]
0x1800094d0  cmp     eax, 3F00h
0x1800094d5  ja      short loc_1800094DD
0x1800094d7  mov     [rdi], ecx
0x1800094d9  xor     ebx, ebx
0x1800094db  jmp     short loc_180009554
0x1800094dd  mov     ebx, 80090029h
0x1800094e2  mov     r9d, 152h
0x1800094e8  mov     ecx, ebx
0x1800094ea  jmp     short loc_1800094F9
0x1800094ec  mov     r9d, 135h
0x1800094f2  mov     ecx, 80090005h
0x1800094f7  mov     ebx, ecx
0x1800094f9  lea     rdx, aStatus; "Status"
0x180009500  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009507  call    DebugTraceError
0x18000950c  jmp     short loc_180009554
0x18000950e  mov     ebx, 80090027h
0x180009513  mov     rcx, cs:WPP_GLOBAL_Control
0x18000951a  lea     rax, WPP_GLOBAL_Control
0x180009521  cmp     rcx, rax
0x180009524  jz      short loc_180009554
0x180009526  test    byte ptr [rcx+1Ch], 1
0x18000952a  jz      short loc_180009554
0x18000952c  mov     rcx, [rcx+10h]
0x180009530  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009537  mov     [rsp+48h+var_18], 128h
0x18000953f  lea     r9, aStatus; "Status"
0x180009546  mov     [rsp+48h+var_20], rax
0x18000954b  mov     [rsp+48h+var_28], ebx
0x18000954f  call    WPP_SF_sDsd
0x180009554  mov     eax, ebx
0x180009556  mov     rbx, [rsp+48h+arg_0]
0x18000955b  add     rsp, 40h
0x18000955f  pop     rdi
0x180009560  retn
```
