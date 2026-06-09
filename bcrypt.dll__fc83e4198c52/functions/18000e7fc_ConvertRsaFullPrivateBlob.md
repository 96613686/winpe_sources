# ConvertRsaFullPrivateBlob

- ea: `0x18000e7fc`
- end: `0x18000e907`
- name: `ConvertRsaFullPrivateBlob`
- size: `267`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, _DWORD *, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180007a7c`
- `0x180009454`
- `0x18000e7fc`
- `0x18001b79d`
- `0x18001b7a9`

## string_xrefs

- `0x18000e857`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertRsaFullPrivateBlob(_DWORD *a1, unsigned int a2, _DWORD *a3, unsigned int a4, _DWORD *a5)
{
  int v8; // edx
  int v9; // ebx
  int v10; // r8d
  __int64 v11; // r12
  int v12; // ebx
  int v13; // edi
  int v14; // esi
  int v15; // ebp
  int v16; // r14d
  unsigned int v18[22]; // [rsp+40h] [rbp-58h] BYREF

  v18[0] = 0;
  v9 = VerifyRsaFullPrivateBlob(a1, a2, v18);
  if ( v9 >= 0 )
  {
    v11 = v18[0];
    *a5 = v18[0];
    if ( a3 )
    {
      if ( a4 < (unsigned int)v11 )
        return (unsigned int)-2146893784;
      v12 = a1[1];
      v13 = a1[2];
      v14 = a1[3];
      v15 = a1[4];
      v16 = a1[5];
      memset_0(a3, 0, a4);
      *a3 = 843141970;
      a3[1] = v12;
      a3[2] = v13;
      a3[3] = v14;
      a3[4] = v15;
      a3[5] = v16;
      memcpy_0(a3 + 6, a1 + 6, v11 - 24);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v10,
      (unsigned int)"Status",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      73);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e7fc  mov     dword ptr [rsp+Size], r9d
0x18000e801  push    rbx
0x18000e802  push    rbp
0x18000e803  push    rsi
0x18000e804  push    rdi
0x18000e805  push    r12
0x18000e807  push    r13
0x18000e809  push    r14
0x18000e80b  push    r15
0x18000e80d  sub     rsp, 58h
0x18000e811  mov     r15, r8
0x18000e814  mov     [rsp+98h+var_58], 0
0x18000e81c  lea     r8, [rsp+98h+var_58]
0x18000e821  mov     edi, r9d
0x18000e824  mov     r13, rcx
0x18000e827  call    VerifyRsaFullPrivateBlob
0x18000e82c  mov     ebx, eax
0x18000e82e  test    eax, eax
0x18000e830  jns     short loc_18000E87D
0x18000e832  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e839  lea     rax, WPP_GLOBAL_Control
0x18000e840  cmp     rcx, rax
0x18000e843  jz      loc_18000E8F3
0x18000e849  test    byte ptr [rcx+1Ch], 1
0x18000e84d  jz      loc_18000E8F3
0x18000e853  mov     rcx, [rcx+10h]
0x18000e857  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e85e  mov     [rsp+98h+var_68], 449h
0x18000e866  lea     r9, aStatus; "Status"
0x18000e86d  mov     [rsp+98h+var_70], rax
0x18000e872  mov     [rsp+98h+var_78], ebx
0x18000e876  call    WPP_SF_sDsd
0x18000e87b  jmp     short loc_18000E8F3
0x18000e87d  mov     rax, [rsp+98h+arg_20]
0x18000e885  mov     r12d, [rsp+98h+var_58]
0x18000e88a  mov     [rax], r12d
0x18000e88d  test    r15, r15
0x18000e890  jz      short loc_18000E8F1
0x18000e892  cmp     edi, r12d
0x18000e895  jnb     short loc_18000E89E
0x18000e897  mov     ebx, 80090028h
0x18000e89c  jmp     short loc_18000E8F3
0x18000e89e  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x18000e8a6  xor     edx, edx; Val
0x18000e8a8  mov     ebx, [r13+4]
0x18000e8ac  mov     rcx, r15; void *
0x18000e8af  mov     edi, [r13+8]
0x18000e8b3  mov     esi, [r13+0Ch]
0x18000e8b7  mov     ebp, [r13+10h]
0x18000e8bb  mov     r14d, [r13+14h]
0x18000e8bf  call    memset_0
0x18000e8c4  lea     r8, [r12-18h]; Size
0x18000e8c9  mov     dword ptr [r15], 32415352h
0x18000e8d0  lea     rdx, [r13+18h]; Src
0x18000e8d4  mov     [r15+4], ebx
0x18000e8d8  lea     rcx, [r15+18h]; void *
0x18000e8dc  mov     [r15+8], edi
0x18000e8e0  mov     [r15+0Ch], esi
0x18000e8e4  mov     [r15+10h], ebp
0x18000e8e8  mov     [r15+14h], r14d
0x18000e8ec  call    memcpy_0
0x18000e8f1  xor     ebx, ebx
0x18000e8f3  mov     eax, ebx
0x18000e8f5  add     rsp, 58h
0x18000e8f9  pop     r15
0x18000e8fb  pop     r14
0x18000e8fd  pop     r13
0x18000e8ff  pop     r12
0x18000e901  pop     rdi
0x18000e902  pop     rsi
0x18000e903  pop     rbp
0x18000e904  pop     rbx
0x18000e905  retn
```
