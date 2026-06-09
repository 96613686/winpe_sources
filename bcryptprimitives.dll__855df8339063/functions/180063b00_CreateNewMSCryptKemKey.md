# CreateNewMSCryptKemKey

- ea: `0x180063b00`
- end: `0x180063bc4`
- name: `CreateNewMSCryptKemKey`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180064ef0`
- `0x180064ff0`

## callees

- `0x18000ecb0`
- `0x1800102a0`
- `0x180063180`
- `0x180063b00`
- `0x180064284`

## string_xrefs

- `0x180063b48`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall CreateNewMSCryptKemKey(_QWORD *a1, char a2, unsigned int a3)
{
  int MsCryptKemKeyLength; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rcx
  size_t v10; // rsi
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  size_t Size; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  MsCryptKemKeyLength = GetMsCryptKemKeyLength(a3, &Size);
  v7 = MsCryptKemKeyLength;
  if ( MsCryptKemKeyLength < 0 )
  {
    v8 = 362;
    v9 = (unsigned int)MsCryptKemKeyLength;
LABEL_3:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v8);
    return v7;
  }
  v10 = (unsigned int)Size;
  v11 = (_DWORD *)SafeAllocaAllocateFromHeap((unsigned int)Size);
  v12 = v11;
  if ( !v11 )
  {
    v7 = -1073741801;
    v8 = 370;
    v9 = 3221225495LL;
    goto LABEL_3;
  }
  memset_0(v11, 0, v10);
  v12[1] = 1297302859;
  *v12 = v10;
  v12[2] = a3;
  v12[4] = 0;
  if ( (a2 & 8) != 0 )
    v12[3] |= 0x100u;
  *a1 = v12;
  return v7;
}

```

## disassembly

```asm
0x180063b00  mov     rax, rsp
0x180063b03  mov     [rax+8], rbx
0x180063b07  mov     [rax+10h], rbp
0x180063b0b  push    rsi
0x180063b0c  push    rdi
0x180063b0d  push    r12
0x180063b0f  push    r14
0x180063b11  push    r15
0x180063b13  sub     rsp, 20h
0x180063b17  mov     r12d, edx
0x180063b1a  mov     dword ptr [rax+20h], 0
0x180063b21  mov     r14, rcx
0x180063b24  lea     rdx, [rax+20h]
0x180063b28  mov     ecx, r8d
0x180063b2b  mov     r15d, r8d
0x180063b2e  call    GetMsCryptKemKeyLength
0x180063b33  mov     edi, eax
0x180063b35  test    eax, eax
0x180063b37  jns     short loc_180063B56
0x180063b39  mov     r9d, 16Ah
0x180063b3f  mov     ecx, eax
0x180063b41  lea     rdx, aStatus; "Status"
0x180063b48  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063b4f  call    DebugTraceError
0x180063b54  jmp     short loc_180063BAA
0x180063b56  mov     esi, dword ptr [rsp+48h+Size]
0x180063b5a  mov     ecx, esi
0x180063b5c  call    SafeAllocaAllocateFromHeap
0x180063b61  mov     rbx, rax
0x180063b64  test    rax, rax
0x180063b67  jnz     short loc_180063B7B
0x180063b69  mov     edi, 0C0000017h
0x180063b6e  mov     r9d, 172h
0x180063b74  mov     ecx, 0C0000017h
0x180063b79  jmp     short loc_180063B41
0x180063b7b  mov     r8, rsi; Size
0x180063b7e  xor     edx, edx; Val
0x180063b80  mov     rcx, rbx; void *
0x180063b83  call    memset_0
0x180063b88  mov     dword ptr [rbx+4], 4D53454Bh
0x180063b8f  mov     [rbx], esi
0x180063b91  mov     [rbx+8], r15d
0x180063b95  mov     dword ptr [rbx+10h], 0
0x180063b9c  test    r12b, 8
0x180063ba0  jz      short loc_180063BA7
0x180063ba2  bts     dword ptr [rbx+0Ch], 8
0x180063ba7  mov     [r14], rbx
0x180063baa  mov     rbx, [rsp+48h+arg_0]
0x180063baf  mov     eax, edi
0x180063bb1  mov     rbp, [rsp+48h+arg_8]
0x180063bb6  add     rsp, 20h
0x180063bba  pop     r15
0x180063bbc  pop     r14
0x180063bbe  pop     r12
0x180063bc0  pop     rdi
0x180063bc1  pop     rsi
0x180063bc2  retn
```
