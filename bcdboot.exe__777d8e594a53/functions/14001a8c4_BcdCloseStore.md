# BcdCloseStore

- ea: `0x14001a8c4`
- end: `0x14001a95b`
- name: `BcdCloseStore`
- size: `151`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x140003d30`
- `0x140004080`
- `0x140004f9c`
- `0x140005e18`
- `0x140009658`
- `0x14001a964`
- `0x14001b764`

## callees

- `0x1400133e4`
- `0x14001a8c4`
- `0x14001ae94`
- `0x14001b4bc`
- `0x14001b64c`
- `0x14001c014`
- `0x140020298`

## pseudocode

```c
__int64 __fastcall BcdCloseStore(__int64 a1)
{
  __int64 v1; // r14
  char v2; // si
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // rcx

  v1 = a1;
  v2 = a1 & 1;
  LOBYTE(a1) = a1 & 1;
  v3 = BiAcquireBcdSyncMutant(a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( (unsigned __int8)BiIsSystemStore(v1) )
    {
      v5 = ~(2 * (_BYTE)v1) & 4 | 2;
      if ( !(unsigned __int8)BiIsWinPEBoot() )
        v5 = ~(2 * (_BYTE)v1) & 4;
    }
    else
    {
      v5 = 2;
    }
    BiLogMessage(2, L"Closing store. Flags: 0x%x", v5);
    v6 = BiCloseStore(v1, v5);
    LOBYTE(v7) = v2;
    v4 = v6;
    BiReleaseBcdSyncMutant(v7);
  }
  else
  {
    BiLogMessage(4, L"BcdCloseStore: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v3);
  }
  return v4;
}

```

## disassembly

```asm
0x14001a8c4  push    rbx
0x14001a8c6  push    rsi
0x14001a8c7  push    rdi
0x14001a8c8  push    r14
0x14001a8ca  sub     rsp, 28h
0x14001a8ce  mov     sil, cl
0x14001a8d1  mov     r14, rcx
0x14001a8d4  and     sil, 1
0x14001a8d8  mov     cl, sil
0x14001a8db  call    BiAcquireBcdSyncMutant
0x14001a8e0  mov     ebx, eax
0x14001a8e2  test    eax, eax
0x14001a8e4  jns     short loc_14001A8FC
0x14001a8e6  mov     r8d, eax
0x14001a8e9  lea     rdx, aBcdclosestoreF; "BcdCloseStore: Failed to acquire BCD sy"...
0x14001a8f0  mov     ecx, 4
0x14001a8f5  call    BiLogMessage
0x14001a8fa  jmp     short loc_14001A94F
0x14001a8fc  mov     rcx, r14
0x14001a8ff  call    BiIsSystemStore
0x14001a904  test    al, al
0x14001a906  jz      short loc_14001A922
0x14001a908  lea     rbx, [r14+r14]
0x14001a90c  not     ebx
0x14001a90e  and     ebx, 4
0x14001a911  call    BiIsWinPEBoot
0x14001a916  mov     edi, ebx
0x14001a918  or      edi, 2
0x14001a91b  test    al, al
0x14001a91d  cmovz   edi, ebx
0x14001a920  jmp     short loc_14001A927
0x14001a922  mov     edi, 2
0x14001a927  mov     r8d, edi
0x14001a92a  lea     rdx, aClosingStoreFl; "Closing store. Flags: 0x%x"
0x14001a931  mov     ecx, 2
0x14001a936  call    BiLogMessage
0x14001a93b  mov     edx, edi
0x14001a93d  mov     rcx, r14
0x14001a940  call    BiCloseStore
0x14001a945  mov     cl, sil
0x14001a948  mov     ebx, eax
0x14001a94a  call    BiReleaseBcdSyncMutant
0x14001a94f  mov     eax, ebx
0x14001a951  add     rsp, 28h
0x14001a955  pop     r14
0x14001a957  pop     rdi
0x14001a958  pop     rsi
0x14001a959  pop     rbx
0x14001a95a  retn
```
