# MSCryptDsaDestroyKeyPair

- ea: `0x18001c660`
- end: `0x18001c797`
- name: `MSCryptDsaDestroyKeyPair`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x18001c660`
- `0x18001c878`
- `0x1800581c0`

## string_xrefs

- `0x18001c70c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x18001c752`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaDestroyKeyPair(unsigned int *a1, int a2, int a3)
{
  unsigned int v4; // ecx
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // rcx

  if ( a1 )
  {
    if ( a1[1] == 1297304409 && a1[2] == 196611 && (v4 = a1[3], v4 - 64 <= 0x140) && (v4 & 7) == 0 )
    {
      v5 = 0;
      if ( *((_QWORD *)a1 + 5) )
      {
        SymCryptDlkeyFree();
        *((_QWORD *)a1 + 5) = 0;
      }
      v6 = *((_QWORD *)a1 + 4);
      if ( v6 )
      {
        SymCryptMlDsaTemporariesFree(v6);
        *((_QWORD *)a1 + 4) = 0;
      }
      v7 = *a1;
      v8 = a1;
      if ( *a1 )
      {
        do
        {
          *v8++ = 0;
          --v7;
        }
        while ( v7 );
      }
      MSCryptFree(a1);
    }
    else
    {
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 233);
      v5 = -1073741816;
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 2494);
    }
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        183);
  }
  return v5;
}

```

## disassembly

```asm
0x18001c660  mov     [rsp+arg_0], rbx
0x18001c665  push    rdi
0x18001c666  sub     rsp, 40h
0x18001c66a  mov     rbx, rcx
0x18001c66d  test    rcx, rcx
0x18001c670  jz      short loc_18001C6EA
0x18001c672  cmp     dword ptr [rcx+4], 4D534B59h
0x18001c679  jnz     loc_18001C752
0x18001c67f  cmp     dword ptr [rcx+8], 30003h
0x18001c686  jnz     loc_18001C752
0x18001c68c  mov     ecx, [rcx+0Ch]
0x18001c68f  lea     eax, [rcx-40h]
0x18001c692  cmp     eax, 140h
0x18001c697  ja      loc_18001C752
0x18001c69d  test    cl, 7
0x18001c6a0  jnz     loc_18001C752
0x18001c6a6  mov     rcx, [rbx+28h]
0x18001c6aa  xor     edi, edi
0x18001c6ac  test    rcx, rcx
0x18001c6af  jnz     loc_18001C744
0x18001c6b5  mov     rcx, [rbx+20h]
0x18001c6b9  test    rcx, rcx
0x18001c6bc  jnz     short loc_18001C736
0x18001c6be  mov     eax, [rbx]
0x18001c6c0  mov     rcx, rbx
0x18001c6c3  test    rax, rax
0x18001c6c6  jz      short loc_18001C6D4
0x18001c6c8  mov     [rcx], dil
0x18001c6cb  inc     rcx
0x18001c6ce  sub     rax, 1
0x18001c6d2  jnz     short loc_18001C6C8
0x18001c6d4  mov     rcx, rbx
0x18001c6d7  call    MSCryptFree
0x18001c6dc  mov     rbx, [rsp+48h+arg_0]
0x18001c6e1  mov     eax, edi
0x18001c6e3  add     rsp, 40h
0x18001c6e7  pop     rdi
0x18001c6e8  retn
0x18001c6ea  mov     edi, 0C000000Dh
0x18001c6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6f6  lea     rax, WPP_GLOBAL_Control
0x18001c6fd  cmp     rcx, rax
0x18001c700  jz      short loc_18001C6DC
0x18001c702  test    byte ptr [rcx+1Ch], 1
0x18001c706  jz      short loc_18001C6DC
0x18001c708  mov     rcx, [rcx+10h]
0x18001c70c  lea     rbx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c713  mov     [rsp+48h+var_18], 9B7h
0x18001c71b  lea     r9, aStatus; "Status"
0x18001c722  mov     [rsp+48h+var_20], rbx
0x18001c727  mov     [rsp+48h+var_28], 0C000000Dh
0x18001c72f  call    WPP_SF_sDsd
0x18001c734  jmp     short loc_18001C6DC
0x18001c736  call    SymCryptMlDsaTemporariesFree
0x18001c73b  mov     [rbx+20h], rdi
0x18001c73f  jmp     loc_18001C6BE
0x18001c744  call    SymCryptDlkeyFree
0x18001c749  mov     [rbx+28h], rdi
0x18001c74d  jmp     loc_18001C6B5
0x18001c752  lea     rbx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c759  mov     r9d, 0E9h
0x18001c75f  mov     r8, rbx
0x18001c762  lea     rdx, aStatus; "Status"
0x18001c769  mov     ecx, 0C0000008h
0x18001c76e  call    DebugTraceError
0x18001c773  mov     r9d, 9BEh
0x18001c779  lea     rdx, aStatus; "Status"
0x18001c780  mov     r8, rbx
0x18001c783  mov     ecx, 0C0000008h
0x18001c788  mov     edi, 0C0000008h
0x18001c78d  call    DebugTraceError
0x18001c792  jmp     loc_18001C6DC
```
