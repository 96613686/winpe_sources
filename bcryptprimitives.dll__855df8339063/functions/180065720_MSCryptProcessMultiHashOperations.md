# MSCryptProcessMultiHashOperations

- ea: `0x180065720`
- end: `0x1800657cb`
- name: `MSCryptProcessMultiHashOperations`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800185c0`
- `0x180065720`
- `0x180065a50`

## string_xrefs

- `0x1800657af`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptProcessMultiHashOperations(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  _DWORD *v5; // rax
  int v6; // edx
  unsigned int v7; // r9d
  unsigned int *v8; // r11
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx

  v5 = (_DWORD *)validateMSCryptHash(a1, a2);
  if ( !v5 || !v5[9] )
  {
    v11 = -1073741816;
    v12 = 4089;
    v13 = 3221225480LL;
    goto LABEL_11;
  }
  if ( v6 != 1 || (v9 = v7 / 0x18) == 0 || v7 != 24LL * v9 || a5 )
  {
    v11 = -1073741811;
    v12 = 4101;
    v13 = 3221225485LL;
    goto LABEL_11;
  }
  v10 = ProcessMultiHashOperations(v5, v8, v9);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 4108;
    v13 = (unsigned int)v10;
LABEL_11:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v12);
  }
  return v11;
}

```

## disassembly

```asm
0x180065720  push    rbx
0x180065722  sub     rsp, 20h
0x180065726  mov     r11, r8
0x180065729  call    validateMSCryptHash
0x18006572e  mov     r10, rax
0x180065731  test    rax, rax
0x180065734  jz      short loc_18006579F
0x180065736  cmp     dword ptr [rax+24h], 0
0x18006573a  jz      short loc_18006579F
0x18006573c  cmp     edx, 1
0x18006573f  jnz     short loc_18006578D
0x180065741  mov     r8d, r9d
0x180065744  mov     rax, 0AAAAAAAAAAAAAAABh
0x18006574e  mul     r8
0x180065751  shr     rdx, 4
0x180065755  test    edx, edx
0x180065757  jz      short loc_18006578D
0x180065759  mov     eax, edx
0x18006575b  lea     rcx, [rax+rax*2]
0x18006575f  shl     rcx, 3
0x180065763  cmp     r8, rcx
0x180065766  jnz     short loc_18006578D
0x180065768  cmp     [rsp+28h+arg_20], 0
0x18006576d  jnz     short loc_18006578D
0x18006576f  mov     r8d, edx
0x180065772  mov     rcx, r10
0x180065775  mov     rdx, r11
0x180065778  call    ProcessMultiHashOperations
0x18006577d  mov     ebx, eax
0x18006577f  test    eax, eax
0x180065781  jns     short loc_1800657C2
0x180065783  mov     r9d, 100Ch
0x180065789  mov     ecx, eax
0x18006578b  jmp     short loc_1800657AF
0x18006578d  mov     ebx, 0C000000Dh
0x180065792  mov     r9d, 1005h
0x180065798  mov     ecx, 0C000000Dh
0x18006579d  jmp     short loc_1800657AF
0x18006579f  mov     ebx, 0C0000008h
0x1800657a4  mov     r9d, 0FF9h
0x1800657aa  mov     ecx, 0C0000008h
0x1800657af  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800657b6  lea     rdx, aStatus; "Status"
0x1800657bd  call    DebugTraceError
0x1800657c2  mov     eax, ebx
0x1800657c4  add     rsp, 20h
0x1800657c8  pop     rbx
0x1800657c9  retn
```
