# MSCryptDsaCloseProvider

- ea: `0x180069710`
- end: `0x18006979b`
- name: `MSCryptDsaCloseProvider`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x180052794`
- `0x180069710`

## string_xrefs

- `0x18006977f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaCloseProvider(_DWORD *a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  unsigned int *v6; // rcx
  _BYTE *v7; // rdx
  __int64 v8; // rax
  int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int *v11; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  if ( !a1 || a2 )
  {
    v3 = -1073741811;
    v4 = 1128;
    v5 = 3221225485LL;
    goto LABEL_9;
  }
  v2 = ValidateDSAAlgorithm(a1, 0, &v10, &v11);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1135;
    v5 = (unsigned int)v2;
LABEL_9:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v4);
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
0x180069710  mov     rax, rsp
0x180069713  push    rbx
0x180069714  sub     rsp, 20h
0x180069718  mov     dword ptr [rax+8], 0
0x18006971f  mov     qword ptr [rax+18h], 0
0x180069727  test    rcx, rcx
0x18006972a  jz      short loc_18006976F
0x18006972c  test    edx, edx
0x18006972e  jnz     short loc_18006976F
0x180069730  lea     r9, [rax+18h]
0x180069734  lea     r8, [rax+8]
0x180069738  call    ValidateDSAAlgorithm
0x18006973d  mov     ebx, eax
0x18006973f  test    eax, eax
0x180069741  jns     short loc_18006974D
0x180069743  mov     r9d, 46Fh
0x180069749  mov     ecx, eax
0x18006974b  jmp     short loc_18006977F
0x18006974d  mov     rcx, [rsp+28h+arg_10]
0x180069752  mov     rdx, rcx
0x180069755  mov     eax, [rcx]
0x180069757  test    rax, rax
0x18006975a  jz      short loc_180069768
0x18006975c  mov     byte ptr [rdx], 0
0x18006975f  inc     rdx
0x180069762  sub     rax, 1
0x180069766  jnz     short loc_18006975C
0x180069768  call    MSCryptFree
0x18006976d  jmp     short loc_180069792
0x18006976f  mov     ebx, 0C000000Dh
0x180069774  mov     r9d, 468h
0x18006977a  mov     ecx, 0C000000Dh
0x18006977f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069786  lea     rdx, aStatus; "Status"
0x18006978d  call    DebugTraceError
0x180069792  mov     eax, ebx
0x180069794  add     rsp, 20h
0x180069798  pop     rbx
0x180069799  retn
```
