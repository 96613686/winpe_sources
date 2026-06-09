# MSCryptDsaOpenProvider

- ea: `0x180052af0`
- end: `0x180052bbf`
- name: `MSCryptDsaOpenProvider`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800102a0`
- `0x180052af0`
- `0x18007f765`

## string_xrefs

- `0x180052b31`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180052b8e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaOpenProvider(__int64 *a1, const wchar_t *a2, int a3)
{
  __int64 v4; // rax
  unsigned int v5; // ebx

  if ( a1 && a2 && !a3 && !wcscmp_0(a2, L"DSA") )
  {
    v4 = SafeAllocaAllocateFromHeap(16);
    if ( v4 )
    {
      *(_QWORD *)(v4 + 8) = 196611;
      *(_DWORD *)v4 = 16;
      *(_DWORD *)(v4 + 4) = 1297301836;
      *a1 = v4;
      return 0;
    }
    else
    {
      v5 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 284);
    }
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        16);
  }
  return v5;
}

```

## disassembly

```asm
0x180052af0  push    rbx
0x180052af2  sub     rsp, 40h
0x180052af6  mov     rax, rdx
0x180052af9  mov     rbx, rcx
0x180052afc  test    rcx, rcx
0x180052aff  jz      short loc_180052B6C
0x180052b01  test    rax, rax
0x180052b04  jz      short loc_180052B6C
0x180052b06  test    r8d, r8d
0x180052b09  jnz     short loc_180052B6C
0x180052b0b  lea     rdx, aDsa; "DSA"
0x180052b12  mov     rcx, rax; String1
0x180052b15  call    wcscmp_0
0x180052b1a  test    eax, eax
0x180052b1c  jnz     short loc_180052B6C
0x180052b1e  lea     ecx, [rax+10h]
0x180052b21  call    SafeAllocaAllocateFromHeap
0x180052b26  test    rax, rax
0x180052b29  jnz     short loc_180052B50
0x180052b2b  mov     r9d, 11Ch
0x180052b31  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052b38  lea     rdx, aStatus; "Status"
0x180052b3f  mov     ecx, 0C0000017h
0x180052b44  mov     ebx, 0C0000017h
0x180052b49  call    DebugTraceError
0x180052b4e  jmp     short loc_180052BB6
0x180052b50  mov     qword ptr [rax+8], 30003h
0x180052b58  mov     dword ptr [rax], 10h
0x180052b5e  mov     dword ptr [rax+4], 4D53414Ch
0x180052b65  mov     [rbx], rax
0x180052b68  xor     ebx, ebx
0x180052b6a  jmp     short loc_180052BB6
0x180052b6c  mov     ebx, 0C000000Dh
0x180052b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b78  lea     rax, WPP_GLOBAL_Control
0x180052b7f  cmp     rcx, rax
0x180052b82  jz      short loc_180052BB6
0x180052b84  test    byte ptr [rcx+1Ch], 1
0x180052b88  jz      short loc_180052BB6
0x180052b8a  mov     rcx, [rcx+10h]
0x180052b8e  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052b95  mov     [rsp+48h+var_18], 110h
0x180052b9d  lea     r9, aStatus; "Status"
0x180052ba4  mov     [rsp+48h+var_20], rax
0x180052ba9  mov     [rsp+48h+var_28], 0C000000Dh
0x180052bb1  call    WPP_SF_sDsd
0x180052bb6  mov     eax, ebx
0x180052bb8  add     rsp, 40h
0x180052bbc  pop     rbx
0x180052bbd  retn
```
