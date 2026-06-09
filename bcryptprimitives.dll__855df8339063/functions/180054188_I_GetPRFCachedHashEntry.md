# I_GetPRFCachedHashEntry

- ea: `0x180054188`
- end: `0x18005427a`
- name: `I_GetPRFCachedHashEntry`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007ecd4`

## callees

- `0x18000ecb0`
- `0x180013a50`
- `0x180054188`
- `0x18007ebb4`

## string_xrefs

- `0x1800541de`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_GetPRFCachedHashEntry(unsigned int a1, __int64 a2)
{
  __int64 v3; // rdi
  wchar_t *v4; // rcx
  int PRFHashProvider; // eax
  unsigned int v6; // ebx
  PVOID v7; // rcx
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+30h] [rbp-38h]

  v3 = 3LL * a1;
  if ( *((_QWORD *)&xmmword_1800A53F0 + 3 * a1) )
  {
LABEL_6:
    v6 = 0;
    *(_OWORD *)a2 = *(__int128 *)((char *)&xmmword_1800A53F0 + 8 * v3);
    *(_QWORD *)(a2 + 16) = qword_1800A5400[v3];
    return v6;
  }
  v4 = off_180087F00[a1];
  *(_OWORD *)P = 0;
  v10 = 0;
  PRFHashProvider = I_LoadPRFHashProvider(v4, P);
  v6 = PRFHashProvider;
  if ( PRFHashProvider >= 0 )
  {
    v7 = P[0];
    *((PVOID *)&xmmword_1800A53F0 + v3 + 1) = P[1];
    LODWORD(qword_1800A5400[v3]) = v10;
    HIDWORD(qword_1800A5400[v3]) = 1;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1800A53F0 + v3, (signed __int64)v7, 0) )
      MSCryptCloseHashProvider((unsigned int *)P[0], 0);
    goto LABEL_6;
  }
  DebugTraceError((unsigned int)PRFHashProvider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", 198);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  return v6;
}

```

## disassembly

```asm
0x180054188  push    rbx
0x18005418a  push    rsi
0x18005418b  push    rdi
0x18005418c  push    r14
0x18005418e  sub     rsp, 48h
0x180054192  mov     ecx, ecx
0x180054194  lea     r14, cs:180000000h
0x18005419b  mov     rsi, rdx
0x18005419e  lea     rdi, [rcx+rcx*2]
0x1800541a2  cmp     qword ptr rva xmmword_1800A53F0[r14+rdi*8], 0
0x1800541ab  jnz     loc_180054250
0x1800541b1  mov     rcx, ds:rva off_180087F00[r14+rcx*8]; "SHA256" ...
0x1800541b9  lea     rdx, [rsp+68h+P]
0x1800541be  xorps   xmm0, xmm0
0x1800541c1  xor     eax, eax
0x1800541c3  movups  xmmword ptr [rsp+68h+P], xmm0
0x1800541c8  mov     [rsp+68h+var_38], rax
0x1800541cd  call    I_LoadPRFHashProvider
0x1800541d2  mov     ebx, eax
0x1800541d4  test    eax, eax
0x1800541d6  jns     short loc_180054201
0x1800541d8  mov     r9d, 0C6h
0x1800541de  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800541e5  lea     rdx, aStatus; "Status"
0x1800541ec  mov     ecx, eax
0x1800541ee  call    DebugTraceError
0x1800541f3  xorps   xmm0, xmm0
0x1800541f6  xor     eax, eax
0x1800541f8  movups  xmmword ptr [rsi], xmm0
0x1800541fb  mov     [rsi+10h], rax
0x1800541ff  jmp     short loc_18005426D
0x180054201  mov     eax, dword ptr [rsp+68h+P+8]
0x180054205  mov     rcx, [rsp+68h+P]
0x18005420a  mov     dword ptr (rva xmmword_1800A53F0+8)[r14+rdi*8], eax
0x180054212  mov     eax, dword ptr [rsp+68h+P+0Ch]
0x180054216  mov     dword ptr (rva xmmword_1800A53F0+0Ch)[r14+rdi*8], eax
0x18005421e  mov     eax, dword ptr [rsp+68h+var_38]
0x180054222  mov     dword ptr rva qword_1800A5400[r14+rdi*8], eax
0x18005422a  xor     eax, eax
0x18005422c  mov     dword ptr (rva qword_1800A5400+4)[r14+rdi*8], 1
0x180054238  lock cmpxchg qword ptr rva xmmword_1800A53F0[r14+rdi*8], rcx
0x180054242  jz      short loc_180054250
0x180054244  mov     rcx, [rsp+68h+P]; P
0x180054249  xor     edx, edx
0x18005424b  call    MSCryptCloseHashProvider
0x180054250  movups  xmm0, rva xmmword_1800A53F0[r14+rdi*8]
0x180054259  xor     ebx, ebx
0x18005425b  movups  xmmword ptr [rsi], xmm0
0x18005425e  movsd   xmm1, rva qword_1800A5400[r14+rdi*8]
0x180054268  movsd   qword ptr [rsi+10h], xmm1
0x18005426d  mov     eax, ebx
0x18005426f  add     rsp, 48h
0x180054273  pop     r14
0x180054275  pop     rdi
0x180054276  pop     rsi
0x180054277  pop     rbx
0x180054278  retn
```
