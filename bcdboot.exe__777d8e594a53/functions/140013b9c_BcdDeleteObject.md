# BcdDeleteObject

- ea: `0x140013b9c`
- end: `0x140013c15`
- name: `BcdDeleteObject`
- size: `121`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x140004828`
- `0x140007e20`
- `0x140008104`
- `0x140008400`
- `0x14001474c`
- `0x140021c10`
- `0x140021f58`

## callees

- `0x1400133e4`
- `0x140013b9c`
- `0x14001ae94`
- `0x14001c014`
- `0x14001c088`
- `0x14001c6e4`
- `0x14001ec14`

## string_xrefs

- `0x140013bc6`: `BcdDeleteObject: Failed to acquire BCD sync mutant. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdDeleteObject(__int64 a1)
{
  __int64 v1; // rbx
  char v2; // si
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx

  v1 = a1;
  v2 = a1 & 1;
  LOBYTE(a1) = a1 & 1;
  v3 = BiAcquireBcdSyncMutant(a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(v1, 0) )
      BiSetFirmwareModifiedFromObject(v1);
    v6 = BiDeleteKey(v1);
    LOBYTE(v7) = v2;
    v8 = v6;
    BiReleaseBcdSyncMutant(v7);
    return v8;
  }
  else
  {
    BiLogMessage(4, L"BcdDeleteObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v3);
    return v4;
  }
}

```

## disassembly

```asm
0x140013b9c  mov     [rsp+arg_0], rbx
0x140013ba1  mov     [rsp+arg_8], rsi
0x140013ba6  push    rdi
0x140013ba7  sub     rsp, 20h
0x140013bab  mov     sil, cl
0x140013bae  mov     rbx, rcx
0x140013bb1  and     sil, 1
0x140013bb5  mov     cl, sil
0x140013bb8  call    BiAcquireBcdSyncMutant
0x140013bbd  mov     edi, eax
0x140013bbf  test    eax, eax
0x140013bc1  jns     short loc_140013BDB
0x140013bc3  mov     r8d, eax
0x140013bc6  lea     rdx, aBcddeleteobjec; "BcdDeleteObject: Failed to acquire BCD "...
0x140013bcd  mov     ecx, 4
0x140013bd2  call    BiLogMessage
0x140013bd7  mov     eax, edi
0x140013bd9  jmp     short loc_140013C05
0x140013bdb  xor     edx, edx
0x140013bdd  mov     rcx, rbx
0x140013be0  call    BiIsLinkedToFirmwareVariable
0x140013be5  test    al, al
0x140013be7  jz      short loc_140013BF1
0x140013be9  mov     rcx, rbx
0x140013bec  call    BiSetFirmwareModifiedFromObject
0x140013bf1  mov     rcx, rbx
0x140013bf4  call    BiDeleteKey
0x140013bf9  mov     cl, sil
0x140013bfc  mov     ebx, eax
0x140013bfe  call    BiReleaseBcdSyncMutant
0x140013c03  mov     eax, ebx
0x140013c05  mov     rbx, [rsp+28h+arg_0]
0x140013c0a  mov     rsi, [rsp+28h+arg_8]
0x140013c0f  add     rsp, 20h
0x140013c13  pop     rdi
0x140013c14  retn
```
