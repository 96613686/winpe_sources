# MSCryptCloseDHProvider

- ea: `0x180068050`
- end: `0x1800680db`
- name: `MSCryptCloseDHProvider`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x180050ab8`
- `0x180068050`

## string_xrefs

- `0x1800680bf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseDHProvider(_DWORD *a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  unsigned int *v6; // rcx
  _BYTE *v7; // rdx
  __int64 v8; // rax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int *v11; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  if ( !a1 || a2 )
  {
    v3 = -1073741811;
    v4 = 1048;
    v5 = 3221225485LL;
    goto LABEL_9;
  }
  v2 = ValidateDHAlgorithm(a1, 0, &v10, &v11);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1055;
    v5 = (unsigned int)v2;
LABEL_9:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v4);
    return v3;
  }
  v6 = v11;
  v7 = v11;
  v8 = *v11;
  if ( *v11 )
  {
    do
    {
      *v7++ = 0;
      --v8;
    }
    while ( v8 );
  }
  MSCryptFree(v6);
  return v3;
}

```

## disassembly

```asm
0x180068050  mov     rax, rsp
0x180068053  push    rbx
0x180068054  sub     rsp, 20h
0x180068058  mov     dword ptr [rax+8], 0
0x18006805f  mov     qword ptr [rax+18h], 0
0x180068067  test    rcx, rcx
0x18006806a  jz      short loc_1800680AF
0x18006806c  test    edx, edx
0x18006806e  jnz     short loc_1800680AF
0x180068070  lea     r9, [rax+18h]
0x180068074  lea     r8, [rax+8]
0x180068078  call    ValidateDHAlgorithm
0x18006807d  mov     ebx, eax
0x18006807f  test    eax, eax
0x180068081  jns     short loc_18006808D
0x180068083  mov     r9d, 41Fh
0x180068089  mov     ecx, eax
0x18006808b  jmp     short loc_1800680BF
0x18006808d  mov     rcx, [rsp+28h+arg_10]
0x180068092  mov     rdx, rcx
0x180068095  mov     eax, [rcx]
0x180068097  test    rax, rax
0x18006809a  jz      short loc_1800680A8
0x18006809c  mov     byte ptr [rdx], 0
0x18006809f  inc     rdx
0x1800680a2  sub     rax, 1
0x1800680a6  jnz     short loc_18006809C
0x1800680a8  call    MSCryptFree
0x1800680ad  jmp     short loc_1800680D2
0x1800680af  mov     ebx, 0C000000Dh
0x1800680b4  mov     r9d, 418h
0x1800680ba  mov     ecx, 0C000000Dh
0x1800680bf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800680c6  lea     rdx, aStatus; "Status"
0x1800680cd  call    DebugTraceError
0x1800680d2  mov     eax, ebx
0x1800680d4  add     rsp, 20h
0x1800680d8  pop     rbx
0x1800680d9  retn
```
