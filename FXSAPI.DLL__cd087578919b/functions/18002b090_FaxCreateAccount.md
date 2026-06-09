# FaxCreateAccount

- ea: `0x18002b090`
- end: `0x18002b3bf`
- name: `FaxCreateAccount`
- size: `815`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x18002b090`
- `0x18002bab8`
- `0x18002bb58`
- `0x180033e20`
- `0x180034850`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002b2f4`
- `RPCRT4!NdrClientCall3` at `0x18002b2f4`
- `KERNEL32!SetLastError` at `0x18002b393`
- `KERNEL32!SetLastError` at `0x18002b393`

## pseudocode

```c
__int64 __fastcall FaxCreateAccount(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned __int8 *v6; // r14
  _QWORD *v7; // rcx
  DWORD Pointer; // ebx
  unsigned int v9; // r13d
  _QWORD *v10; // rax
  CLIENT_CALL_RETURN v11; // rax
  __int64 v13; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytes; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 *v15; // [rsp+98h] [rbp+20h]

  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
  {
    if ( a2 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        WPP_SF_d(v7[2], 12, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids, a2);
LABEL_13:
      Pointer = 87;
      goto LABEL_43;
    }
    if ( !a3 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        WPP_SF_(v7[2], 13, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
      goto LABEL_13;
    }
    if ( *a3 == 16 )
    {
      dwBytes = 16;
      SerializeAccountInfo(a3, 0, 0, 0, 0, &dwBytes);
      v9 = dwBytes;
      v6 = (unsigned __int8 *)pMemAlloc((unsigned int)dwBytes);
      v15 = v6;
      if ( v6 )
      {
        dwBytes = 16;
        SerializeAccountInfo(a3, 0, v6, v9, v6, &dwBytes);
        if ( (unsigned int)MarshallDownStructure(v6, (struct _FieldInfo *)&fax_account_info0_fields, 0x10u) )
        {
          v10 = *(_QWORD **)(a1 + 32);
          dwBytes = 0;
          LODWORD(v13) = 0;
          v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x5Du, 0, *v10, v13, v6, v9).Pointer;
          Pointer = (DWORD)v11.Pointer;
          dwBytes = v11.Simple;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids, 0);
          }
          Pointer = 1359;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids, v9);
        }
        Pointer = 8;
      }
    }
    else
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        WPP_SF_dd(v7[2], 14, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
      Pointer = 13;
    }
  }
  else
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_(v7[2], 11, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids);
    Pointer = 6;
  }
LABEL_43:
  pMemFree(v6);
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x18002b090  mov     [rsp+arg_8], rbx
0x18002b095  push    rsi
0x18002b096  push    r12
0x18002b098  push    r13
0x18002b09a  push    r14
0x18002b09c  push    r15
0x18002b09e  sub     rsp, 50h
0x18002b0a2  mov     r12, r8
0x18002b0a5  mov     esi, edx
0x18002b0a7  mov     r15, rcx
0x18002b0aa  xor     r14d, r14d
0x18002b0ad  lea     rdx, WPP_GLOBAL_Control
0x18002b0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0bb  mov     ebx, 1000h
0x18002b0c0  cmp     rcx, rdx
0x18002b0c3  jz      short loc_18002B0F2
0x18002b0c5  test    [rcx+1Ch], ebx
0x18002b0c8  jz      short loc_18002B0F2
0x18002b0ca  cmp     byte ptr [rcx+19h], 5
0x18002b0ce  jb      short loc_18002B0F2
0x18002b0d0  lea     edx, [r14+0Ah]
0x18002b0d4  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b0db  mov     rcx, [rcx+10h]
0x18002b0df  call    WPP_SF_
0x18002b0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0eb  lea     rdx, WPP_GLOBAL_Control
0x18002b0f2  test    r15, r15
0x18002b0f5  jz      loc_18002B35B
0x18002b0fb  cmp     [r15], r14d
0x18002b0fe  jz      loc_18002B35B
0x18002b104  cmp     [r15+10h], r14d
0x18002b108  jnz     loc_18002B35B
0x18002b10e  test    esi, esi
0x18002b110  jz      short loc_18002B144
0x18002b112  cmp     rcx, rdx
0x18002b115  jz      short loc_18002B13A
0x18002b117  test    [rcx+1Ch], ebx
0x18002b11a  jz      short loc_18002B13A
0x18002b11c  cmp     byte ptr [rcx+19h], 2
0x18002b120  jb      short loc_18002B13A
0x18002b122  mov     edx, 0Ch
0x18002b127  mov     r9d, esi
0x18002b12a  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b131  mov     rcx, [rcx+10h]
0x18002b135  call    WPP_SF_d
0x18002b13a  mov     ebx, 57h ; 'W'
0x18002b13f  jmp     loc_18002B385
0x18002b144  test    r12, r12
0x18002b147  jnz     short loc_18002B170
0x18002b149  cmp     rcx, rdx
0x18002b14c  jz      short loc_18002B13A
0x18002b14e  test    [rcx+1Ch], ebx
0x18002b151  jz      short loc_18002B13A
0x18002b153  cmp     byte ptr [rcx+19h], 2
0x18002b157  jb      short loc_18002B13A
0x18002b159  lea     edx, [r12+0Dh]
0x18002b15e  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b165  mov     rcx, [rcx+10h]
0x18002b169  call    WPP_SF_
0x18002b16e  jmp     short loc_18002B13A
0x18002b170  mov     eax, [r12]
0x18002b174  mov     r8d, 10h
0x18002b17a  cmp     eax, r8d
0x18002b17d  jz      short loc_18002B1B4
0x18002b17f  cmp     rcx, rdx
0x18002b182  jz      short loc_18002B1AA
0x18002b184  test    [rcx+1Ch], ebx
0x18002b187  jz      short loc_18002B1AA
0x18002b189  cmp     byte ptr [rcx+19h], 2
0x18002b18d  jb      short loc_18002B1AA
0x18002b18f  lea     edx, [r8-2]
0x18002b193  mov     dword ptr [rsp+78h+var_58], eax
0x18002b197  mov     r9d, r8d
0x18002b19a  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b1a1  mov     rcx, [rcx+10h]
0x18002b1a5  call    WPP_SF_dd
0x18002b1aa  mov     ebx, 0Dh
0x18002b1af  jmp     loc_18002B385
0x18002b1b4  mov     [rsp+78h+dwBytes], r8
0x18002b1bc  lea     rax, [rsp+78h+dwBytes]
0x18002b1c4  mov     [rsp+78h+var_50], rax
0x18002b1c9  mov     [rsp+78h+var_58], r14
0x18002b1ce  xor     r9d, r9d
0x18002b1d1  xor     r8d, r8d
0x18002b1d4  mov     edx, esi
0x18002b1d6  mov     rcx, r12
0x18002b1d9  call    SerializeAccountInfo
0x18002b1de  mov     r13, [rsp+78h+dwBytes]
0x18002b1e6  mov     ecx, r13d; dwBytes
0x18002b1e9  call    pMemAlloc
0x18002b1ee  mov     r14, rax
0x18002b1f1  mov     [rsp+78h+arg_18], rax
0x18002b1f9  test    rax, rax
0x18002b1fc  jnz     short loc_18002B23D
0x18002b1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b205  lea     rax, WPP_GLOBAL_Control
0x18002b20c  cmp     rcx, rax
0x18002b20f  jz      short loc_18002B233
0x18002b211  test    [rcx+1Ch], ebx
0x18002b214  jz      short loc_18002B233
0x18002b216  cmp     byte ptr [rcx+19h], 2
0x18002b21a  jb      short loc_18002B233
0x18002b21c  lea     edx, [r14+0Fh]
0x18002b220  mov     r9d, r13d
0x18002b223  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b22a  mov     rcx, [rcx+10h]
0x18002b22e  call    WPP_SF_d
0x18002b233  mov     ebx, 8
0x18002b238  jmp     loc_18002B385
0x18002b23d  mov     [rsp+78h+dwBytes], 10h
0x18002b249  lea     rax, [rsp+78h+dwBytes]
0x18002b251  mov     [rsp+78h+var_50], rax
0x18002b256  mov     [rsp+78h+var_58], r14
0x18002b25b  mov     r9d, r13d
0x18002b25e  mov     r8, r14
0x18002b261  mov     edx, esi
0x18002b263  mov     rcx, r12
0x18002b266  call    SerializeAccountInfo
0x18002b26b  mov     r12d, 10h
0x18002b271  mov     r8d, r12d; unsigned __int64
0x18002b274  lea     rdx, ?fax_account_info0_fields@@3PAU_FieldInfo@@A; struct _FieldInfo *
0x18002b27b  mov     rcx, r14; unsigned __int8 *
0x18002b27e  call    MarshallDownStructure
0x18002b283  test    eax, eax
0x18002b285  jnz     short loc_18002B2C5
0x18002b287  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b28e  lea     rax, WPP_GLOBAL_Control
0x18002b295  cmp     rcx, rax
0x18002b298  jz      short loc_18002B2BB
0x18002b29a  test    [rcx+1Ch], ebx
0x18002b29d  jz      short loc_18002B2BB
0x18002b29f  cmp     byte ptr [rcx+19h], 2
0x18002b2a3  jb      short loc_18002B2BB
0x18002b2a5  mov     edx, r12d
0x18002b2a8  mov     r9d, esi
0x18002b2ab  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b2b2  mov     rcx, [rcx+10h]
0x18002b2b6  call    WPP_SF_d
0x18002b2bb  mov     ebx, 54Fh
0x18002b2c0  jmp     loc_18002B385
0x18002b2c5  mov     rax, [r15+20h]
0x18002b2c9  mov     [rsp+78h+dwBytes], 0
0x18002b2d5  mov     [rsp+78h+var_48], r13d
0x18002b2da  mov     [rsp+78h+var_50], r14
0x18002b2df  mov     dword ptr [rsp+78h+var_58], esi
0x18002b2e3  mov     r9, [rax]
0x18002b2e6  xor     r8d, r8d; pReturnValue
0x18002b2e9  lea     edx, [r8+5Dh]; nProcNum
0x18002b2ed  lea     rcx, pProxyInfo; pProxyInfo
0x18002b2f4  call    cs:__imp_NdrClientCall3
0x18002b2fb  nop     dword ptr [rax+rax+00h]
0x18002b300  mov     rbx, rax
0x18002b303  mov     [rsp+78h+dwBytes], rax
0x18002b30b  mov     [rsp+78h+var_38], eax
0x18002b30f  jmp     short loc_18002B385
0x18002b311  mov     ebx, eax
0x18002b313  mov     [rsp+78h+var_38], eax
0x18002b317  lea     rdx, WPP_GLOBAL_Control
0x18002b31e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b325  cmp     rcx, rdx
0x18002b328  jz      short loc_18002B351
0x18002b32a  test    dword ptr [rcx+1Ch], 1000h
0x18002b331  jz      short loc_18002B351
0x18002b333  cmp     byte ptr [rcx+19h], 2
0x18002b337  jb      short loc_18002B351
0x18002b339  mov     edx, 11h
0x18002b33e  mov     r9d, eax
0x18002b341  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b348  mov     rcx, [rcx+10h]
0x18002b34c  call    WPP_SF_d
0x18002b351  mov     r14, [rsp+78h+arg_18]
0x18002b359  jmp     short loc_18002B385
0x18002b35b  cmp     rcx, rdx
0x18002b35e  jz      short loc_18002B380
0x18002b360  test    [rcx+1Ch], ebx
0x18002b363  jz      short loc_18002B380
0x18002b365  cmp     byte ptr [rcx+19h], 2
0x18002b369  jb      short loc_18002B380
0x18002b36b  mov     edx, 0Bh
0x18002b370  lea     r8, WPP_358fce5186633d20cf4d70a2185c7d2d_Traceguids
0x18002b377  mov     rcx, [rcx+10h]
0x18002b37b  call    WPP_SF_
0x18002b380  mov     ebx, 6
0x18002b385  mov     rcx, r14; lpMem
0x18002b388  call    pMemFree
0x18002b38d  test    ebx, ebx
0x18002b38f  jz      short loc_18002B3A3
0x18002b391  mov     ecx, ebx; dwErrCode
0x18002b393  call    cs:__imp_SetLastError
0x18002b39a  nop     dword ptr [rax+rax+00h]
0x18002b39f  xor     eax, eax
0x18002b3a1  jmp     short loc_18002B3A8
0x18002b3a3  mov     eax, 1
0x18002b3a8  mov     rbx, [rsp+78h+arg_8]
0x18002b3b0  add     rsp, 50h
0x18002b3b4  pop     r15
0x18002b3b6  pop     r14
0x18002b3b8  pop     r13
0x18002b3ba  pop     r12
0x18002b3bc  pop     rsi
0x18002b3bd  retn
```
