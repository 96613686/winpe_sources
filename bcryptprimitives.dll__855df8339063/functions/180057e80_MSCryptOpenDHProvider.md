# MSCryptOpenDHProvider

- ea: `0x180057e80`
- end: `0x180057f65`
- name: `MSCryptOpenDHProvider`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800102a0`
- `0x180057e80`

## string_xrefs

- `0x180057ed7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180057f34`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenDHProvider(__int64 *a1, unsigned __int16 *a2, int a3)
{
  __int64 v4; // rax
  unsigned int v5; // ebx

  if ( !a1 || !a2 || a3 )
    goto LABEL_11;
  a3 = *a2 - 68;
  if ( *a2 == 68 )
  {
    a3 = a2[1] - 72;
    if ( a2[1] == 72 )
      a3 = a2[2];
  }
  if ( a3 )
  {
LABEL_11:
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
        2);
  }
  else
  {
    v4 = SafeAllocaAllocateFromHeap(16);
    if ( v4 )
    {
      *(_QWORD *)(v4 + 8) = 196610;
      *(_DWORD *)v4 = 16;
      *(_DWORD *)(v4 + 4) = 1297301836;
      *a1 = v4;
      return 0;
    }
    else
    {
      v5 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", 270);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180057e80  push    rbx
0x180057e82  sub     rsp, 40h
0x180057e86  mov     rbx, rcx
0x180057e89  test    rcx, rcx
0x180057e8c  jz      loc_180057F12
0x180057e92  test    rdx, rdx
0x180057e95  jz      short loc_180057F12
0x180057e97  test    r8d, r8d
0x180057e9a  jnz     short loc_180057F12
0x180057e9c  movzx   r8d, word ptr [rdx]
0x180057ea0  sub     r8d, 44h ; 'D'
0x180057ea4  jnz     short loc_180057EBE
0x180057ea6  movzx   r8d, word ptr [rdx+2]
0x180057eab  sub     r8d, 48h ; 'H'
0x180057eaf  jnz     short loc_180057EBE
0x180057eb1  movzx   r8d, word ptr [rdx+4]
0x180057eb6  xor     eax, eax
0x180057eb8  movzx   ecx, ax
0x180057ebb  sub     r8d, ecx
0x180057ebe  test    r8d, r8d
0x180057ec1  jnz     short loc_180057F12
0x180057ec3  lea     ecx, [r8+10h]
0x180057ec7  call    SafeAllocaAllocateFromHeap
0x180057ecc  test    rax, rax
0x180057ecf  jnz     short loc_180057EF6
0x180057ed1  mov     r9d, 10Eh
0x180057ed7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057ede  lea     rdx, aStatus; "Status"
0x180057ee5  mov     ecx, 0C0000017h
0x180057eea  mov     ebx, 0C0000017h
0x180057eef  call    DebugTraceError
0x180057ef4  jmp     short loc_180057F5C
0x180057ef6  mov     qword ptr [rax+8], 30002h
0x180057efe  mov     dword ptr [rax], 10h
0x180057f04  mov     dword ptr [rax+4], 4D53414Ch
0x180057f0b  mov     [rbx], rax
0x180057f0e  xor     ebx, ebx
0x180057f10  jmp     short loc_180057F5C
0x180057f12  mov     ebx, 0C000000Dh
0x180057f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f1e  lea     rax, WPP_GLOBAL_Control
0x180057f25  cmp     rcx, rax
0x180057f28  jz      short loc_180057F5C
0x180057f2a  test    byte ptr [rcx+1Ch], 1
0x180057f2e  jz      short loc_180057F5C
0x180057f30  mov     rcx, [rcx+10h]
0x180057f34  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057f3b  mov     [rsp+48h+var_18], 102h
0x180057f43  lea     r9, aStatus; "Status"
0x180057f4a  mov     [rsp+48h+var_20], rax
0x180057f4f  mov     [rsp+48h+var_28], 0C000000Dh
0x180057f57  call    WPP_SF_sDsd
0x180057f5c  mov     eax, ebx
0x180057f5e  add     rsp, 40h
0x180057f62  pop     rbx
0x180057f63  retn
```
