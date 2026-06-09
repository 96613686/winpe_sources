# BcdCloseObject

- ea: `0x140013b48`
- end: `0x140013b95`
- name: `BcdCloseObject`
- size: `77`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `34`
- callee_count: `5`
- tags: ``

## callers

- `0x140003d30`
- `0x140004828`
- `0x140004a60`
- `0x140004e20`
- `0x140004e98`
- `0x1400052bc`
- `0x1400058e4`
- `0x140005b98`
- `0x140005fc4`
- `0x140006b08`
- `0x1400078f4`
- `0x140007e20`
- `0x140008104`
- `0x140008400`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x140008e68`
- `0x140009094`
- `0x140009170`
- `0x140009528`
- `0x140009658`
- `0x14000efc8`
- `0x140014448`
- `0x14001474c`
- `0x140014ec8`
- `0x140021990`
- `0x140021c10`
- `0x140021f58`
- `0x140022258`
- `0x140022cb8`
- `0x140023824`
- `0x140024cf0`
- `0x14002515c`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x14001ae94`
- `0x14001c014`
- `0x14001e5e4`

## pseudocode

```c
__int64 __fastcall BcdCloseObject(HANDLE Handle)
{
  HANDLE v1; // rdi
  char v2; // bl
  int v3; // eax
  __int64 v5; // rcx

  v1 = Handle;
  v2 = (unsigned __int8)Handle & 1;
  LOBYTE(Handle) = (unsigned __int8)Handle & 1;
  v3 = BiAcquireBcdSyncMutant(Handle);
  if ( v3 < 0 )
    return BiLogMessage(4, L"BcdCloseObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v3);
  BiCloseKey(v1);
  LOBYTE(v5) = v2;
  return BiReleaseBcdSyncMutant(v5);
}

```

## disassembly

```asm
0x140013b48  mov     [rsp+arg_0], rbx
0x140013b4d  push    rdi
0x140013b4e  sub     rsp, 20h
0x140013b52  mov     bl, cl
0x140013b54  mov     rdi, rcx
0x140013b57  and     bl, 1
0x140013b5a  mov     cl, bl
0x140013b5c  call    BiAcquireBcdSyncMutant
0x140013b61  test    eax, eax
0x140013b63  jns     short loc_140013B7B
0x140013b65  mov     r8d, eax
0x140013b68  lea     rdx, aBcdcloseobject; "BcdCloseObject: Failed to acquire BCD s"...
0x140013b6f  mov     ecx, 4
0x140013b74  call    BiLogMessage
0x140013b79  jmp     short loc_140013B8A
0x140013b7b  mov     rcx, rdi; Handle
0x140013b7e  call    BiCloseKey
0x140013b83  mov     cl, bl
0x140013b85  call    BiReleaseBcdSyncMutant
0x140013b8a  mov     rbx, [rsp+28h+arg_0]
0x140013b8f  add     rsp, 20h
0x140013b93  pop     rdi
0x140013b94  retn
```
