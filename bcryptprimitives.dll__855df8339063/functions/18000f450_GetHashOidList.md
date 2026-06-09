# GetHashOidList

- ea: `0x18000f450`
- end: `0x18000f800`
- name: `GetHashOidList`
- size: `944`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d000`
- `0x18003d300`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000ef70`
- `0x18000f450`
- `0x18000f810`
- `0x180010270`
- `0x1800102a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f5ef`
- `ntdll!RtlFreeHeap` at `0x18000f5ef`

## string_xrefs

- `0x18000f7e3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f655`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f67a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f6d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f72a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f76b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f793`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000f7bb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetHashOidList(_QWORD *a1, int a2, _QWORD *a3, unsigned int *a4)
{
  int HashProperty; // ebp
  __int64 result; // rax
  int v9; // eax
  unsigned int *v10; // r14
  int v11; // edx
  int v12; // edx
  unsigned int v13; // ebp
  _DWORD *v14; // rbx
  int v15; // edx
  __int64 v16; // rcx
  unsigned int *v17; // rax
  int v18; // [rsp+40h] [rbp-28h] BYREF
  PVOID P; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+8h] BYREF

  P = 0;
  v18 = 0;
  v20 = 0;
  if ( !a1 )
  {
    HashProperty = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        149);
    return (unsigned int)HashProperty;
  }
  if ( *a1 )
  {
    v9 = MSCryptOpenHashProvider(&P, *a1, 0);
    v10 = (unsigned int *)P;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          169);
      HashProperty = -1073741637;
      goto LABEL_15;
    }
    HashProperty = MSCryptGetHashProperty(P, L"HashDigestLength", &v18, 4, &v20, 0);
    if ( HashProperty < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          HashProperty,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          183);
      goto LABEL_15;
    }
    if ( v18 == a2 )
    {
      HashProperty = MSCryptGetHashProperty(v10, L"HashOIDList", 0, 0, &v20, 0);
      if ( HashProperty < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
            (unsigned int)"Status",
            HashProperty,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
            203);
        goto LABEL_15;
      }
      v13 = v20;
      v14 = (_DWORD *)SafeAllocaAllocateFromHeap(v20);
      if ( v14 )
      {
        HashProperty = MSCryptGetHashProperty(v10, L"HashOIDList", v14, v13, &v20, 0);
        if ( HashProperty >= 0 )
        {
          if ( *v14 )
          {
            HashProperty = 0;
            *a4 = v20;
            *a3 = v14;
            goto LABEL_15;
          }
          HashProperty = -1073741595;
          DebugTraceError(3221225701LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 234);
          goto LABEL_23;
        }
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_23:
          MSCryptFree(v14);
          goto LABEL_15;
        }
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          HashProperty,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          225);
        MSCryptFree(v14);
      }
      else
      {
        HashProperty = -1073741801;
        DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 212);
      }
    }
    else
    {
      HashProperty = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 190);
    }
LABEL_15:
    if ( v10 )
    {
      if ( v10[1] == 1297303617 )
      {
        v16 = *v10;
        v17 = v10;
        if ( *v10 )
        {
          do
          {
            *(_BYTE *)v17 = 0;
            v17 = (unsigned int *)((char *)v17 + 1);
            --v16;
          }
          while ( v16 );
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      }
      else
      {
        DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 900);
      }
    }
    return (unsigned int)HashProperty;
  }
  *a3 = 0;
  result = 0;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x18000f450  mov     [rsp+arg_10], rbx
0x18000f455  mov     [rsp+arg_18], rbp
0x18000f45a  push    rsi
0x18000f45b  push    rdi
0x18000f45c  push    r15
0x18000f45e  sub     rsp, 50h
0x18000f462  xor     r15d, r15d
0x18000f465  mov     rdi, r9
0x18000f468  mov     [rsp+68h+P], r15
0x18000f46d  mov     rsi, r8
0x18000f470  mov     [rsp+68h+var_28], r15d
0x18000f475  mov     ebx, edx
0x18000f477  mov     [rsp+68h+arg_0], r15d
0x18000f47c  test    rcx, rcx
0x18000f47f  jnz     short loc_18000F4BB
0x18000f481  mov     ebp, 0C000000Dh
0x18000f486  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f48d  lea     rax, WPP_GLOBAL_Control
0x18000f494  cmp     rcx, rax
0x18000f497  jz      short loc_18000F4A3
0x18000f499  test    byte ptr [rcx+1Ch], 1
0x18000f49d  jnz     loc_18000F726
0x18000f4a3  mov     eax, ebp
0x18000f4a5  lea     r11, [rsp+68h+var_18]
0x18000f4aa  mov     rbx, [r11+30h]
0x18000f4ae  mov     rbp, [r11+38h]
0x18000f4b2  mov     rsp, r11
0x18000f4b5  pop     r15
0x18000f4b7  pop     rdi
0x18000f4b8  pop     rsi
0x18000f4b9  retn
0x18000f4bb  mov     rdx, [rcx]
0x18000f4be  test    rdx, rdx
0x18000f4c1  jz      loc_18000F757
0x18000f4c7  xor     r8d, r8d
0x18000f4ca  mov     [rsp+68h+arg_8], r14
0x18000f4cf  lea     rcx, [rsp+68h+P]
0x18000f4d4  call    MSCryptOpenHashProvider
0x18000f4d9  mov     r14, [rsp+68h+P]
0x18000f4de  mov     edx, eax
0x18000f4e0  test    eax, eax
0x18000f4e2  js      loc_18000F6AB
0x18000f4e8  lea     rax, [rsp+68h+arg_0]
0x18000f4ed  mov     dword ptr [rsp+68h+var_40], r15d
0x18000f4f2  mov     r9d, 4
0x18000f4f8  mov     [rsp+68h+var_48], rax
0x18000f4fd  lea     r8, [rsp+68h+var_28]
0x18000f502  mov     rcx, r14
0x18000f505  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000f50c  call    MSCryptGetHashProperty
0x18000f511  mov     ebp, eax
0x18000f513  test    eax, eax
0x18000f515  js      loc_18000F6F8
0x18000f51b  cmp     [rsp+68h+var_28], ebx
0x18000f51f  jnz     loc_18000F765
0x18000f525  lea     rax, [rsp+68h+arg_0]
0x18000f52a  mov     dword ptr [rsp+68h+var_40], r15d
0x18000f52f  xor     r9d, r9d
0x18000f532  mov     [rsp+68h+var_48], rax
0x18000f537  xor     r8d, r8d
0x18000f53a  lea     rdx, aHashoidlist; "HashOIDList"
0x18000f541  mov     rcx, r14
0x18000f544  call    MSCryptGetHashProperty
0x18000f549  mov     ebp, eax
0x18000f54b  test    eax, eax
0x18000f54d  js      loc_18000F628
0x18000f553  mov     ebp, [rsp+68h+arg_0]
0x18000f557  mov     ecx, ebp
0x18000f559  call    SafeAllocaAllocateFromHeap
0x18000f55e  mov     rbx, rax
0x18000f561  test    rax, rax
0x18000f564  jz      loc_18000F78D
0x18000f56a  lea     rax, [rsp+68h+arg_0]
0x18000f56f  mov     dword ptr [rsp+68h+var_40], r15d
0x18000f574  mov     r9d, ebp
0x18000f577  mov     [rsp+68h+var_48], rax
0x18000f57c  mov     r8, rbx
0x18000f57f  lea     rdx, aHashoidlist; "HashOIDList"
0x18000f586  mov     rcx, r14
0x18000f589  call    MSCryptGetHashProperty
0x18000f58e  mov     ebp, eax
0x18000f590  test    eax, eax
0x18000f592  js      short loc_18000F605
0x18000f594  cmp     [rbx], r15d
0x18000f597  jz      loc_18000F7B5
0x18000f59d  mov     eax, [rsp+68h+arg_0]
0x18000f5a1  mov     ebp, r15d
0x18000f5a4  mov     [rdi], eax
0x18000f5a6  mov     [rsi], rbx
0x18000f5a9  test    r14, r14
0x18000f5ac  jz      short loc_18000F5FB
0x18000f5ae  cmp     dword ptr [r14+4], 4D534841h
0x18000f5b6  jnz     loc_18000F7DD
0x18000f5bc  mov     ecx, [r14]
0x18000f5bf  mov     rax, r14
0x18000f5c2  test    rcx, rcx
0x18000f5c5  jz      short loc_18000F5DD
0x18000f5c7  nop     word ptr [rax+rax+00000000h]
0x18000f5d0  mov     [rax], r15b
0x18000f5d3  lea     rax, [rax+1]
0x18000f5d7  sub     rcx, 1
0x18000f5db  jnz     short loc_18000F5D0
0x18000f5dd  mov     rcx, gs:60h
0x18000f5e6  mov     r8, r14; P
0x18000f5e9  xor     edx, edx; Flags
0x18000f5eb  mov     rcx, [rcx+30h]; HeapHandle
0x18000f5ef  call    cs:__imp_RtlFreeHeap
0x18000f5f6  nop     dword ptr [rax+rax+00h]
0x18000f5fb  mov     r14, [rsp+68h+arg_8]
0x18000f600  jmp     loc_18000F4A3
0x18000f605  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f60c  lea     rax, WPP_GLOBAL_Control
0x18000f613  cmp     rcx, rax
0x18000f616  jz      short loc_18000F61E
0x18000f618  test    byte ptr [rcx+1Ch], 1
0x18000f61c  jnz     short loc_18000F676
0x18000f61e  mov     rcx, rbx
0x18000f621  call    MSCryptFree
0x18000f626  jmp     short loc_18000F5A9
0x18000f628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f62f  lea     rax, WPP_GLOBAL_Control
0x18000f636  cmp     rcx, rax
0x18000f639  jz      loc_18000F5A9
0x18000f63f  test    byte ptr [rcx+1Ch], 1
0x18000f643  jz      loc_18000F5A9
0x18000f649  mov     [rsp+68h+var_38], 0CBh
0x18000f651  mov     rcx, [rcx+10h]
0x18000f655  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f65c  mov     [rsp+68h+var_40], r8
0x18000f661  lea     r9, aStatus; "Status"
0x18000f668  mov     dword ptr [rsp+68h+var_48], ebp
0x18000f66c  call    WPP_SF_sDsd
0x18000f671  jmp     loc_18000F5A9
0x18000f676  mov     rcx, [rcx+10h]
0x18000f67a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f681  mov     [rsp+68h+var_38], 0E1h
0x18000f689  lea     r9, aStatus; "Status"
0x18000f690  mov     [rsp+68h+var_40], r8
0x18000f695  mov     dword ptr [rsp+68h+var_48], ebp
0x18000f699  call    WPP_SF_sDsd
0x18000f69e  mov     rcx, rbx
0x18000f6a1  call    MSCryptFree
0x18000f6a6  jmp     loc_18000F5A9
0x18000f6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6b2  lea     rax, WPP_GLOBAL_Control
0x18000f6b9  cmp     rcx, rax
0x18000f6bc  jz      short loc_18000F6C4
0x18000f6be  test    byte ptr [rcx+1Ch], 1
0x18000f6c2  jnz     short loc_18000F6CE
0x18000f6c4  mov     ebp, 0C00000BBh
0x18000f6c9  jmp     loc_18000F5A9
0x18000f6ce  mov     rcx, [rcx+10h]
0x18000f6d2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f6d9  mov     [rsp+68h+var_38], 0A9h
0x18000f6e1  lea     r9, aStatus; "Status"
0x18000f6e8  mov     [rsp+68h+var_40], r8
0x18000f6ed  mov     dword ptr [rsp+68h+var_48], edx
0x18000f6f1  call    WPP_SF_sDsd
0x18000f6f6  jmp     short loc_18000F6C4
0x18000f6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6ff  lea     rax, WPP_GLOBAL_Control
0x18000f706  cmp     rcx, rax
0x18000f709  jz      loc_18000F5A9
0x18000f70f  test    byte ptr [rcx+1Ch], 1
0x18000f713  jz      loc_18000F5A9
0x18000f719  mov     [rsp+68h+var_38], 0B7h
0x18000f721  jmp     loc_18000F651
0x18000f726  mov     rcx, [rcx+10h]
0x18000f72a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f731  mov     [rsp+68h+var_38], 95h
0x18000f739  lea     r9, aStatus; "Status"
0x18000f740  mov     [rsp+68h+var_40], r8
0x18000f745  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000f74d  call    WPP_SF_sDsd
0x18000f752  jmp     loc_18000F4A3
0x18000f757  mov     [r8], r15
0x18000f75a  mov     eax, r15d
0x18000f75d  mov     [r9], r15d
0x18000f760  jmp     loc_18000F4A5
0x18000f765  mov     r9d, 0BEh
0x18000f76b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f772  lea     rdx, aStatus; "Status"
0x18000f779  mov     ecx, 0C000000Dh
0x18000f77e  mov     ebp, 0C000000Dh
0x18000f783  call    DebugTraceError
0x18000f788  jmp     loc_18000F5A9
0x18000f78d  mov     r9d, 0D4h
0x18000f793  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f79a  lea     rdx, aStatus; "Status"
0x18000f7a1  mov     ecx, 0C0000017h
0x18000f7a6  mov     ebp, 0C0000017h
0x18000f7ab  call    DebugTraceError
0x18000f7b0  jmp     loc_18000F5A9
0x18000f7b5  mov     r9d, 0EAh
0x18000f7bb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f7c2  lea     rdx, aStatus; "Status"
0x18000f7c9  mov     ecx, 0C00000E5h
0x18000f7ce  mov     ebp, 0C00000E5h
0x18000f7d3  call    DebugTraceError
0x18000f7d8  jmp     loc_18000F61E
0x18000f7dd  mov     r9d, 384h
0x18000f7e3  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f7ea  lea     rdx, aStatus; "Status"
0x18000f7f1  mov     ecx, 0C0000008h
0x18000f7f6  call    DebugTraceError
0x18000f7fb  jmp     loc_18000F5FB
```
