# IsSelectStorageVolumeExPresent

- ea: `0x180002ab8`
- end: `0x180002b06`
- name: `IsSelectStorageVolumeExPresent`
- size: `78`
- prototype: `char()`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007000`
- `0x1800079d8`
- `0x180007ef8`
- `0x1800090a0`

## callees

- `0x180002ab8`
- `0x180002e15`

## pseudocode

```c
char IsSelectStorageVolumeExPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800182D0 == 1 )
    return 1;
  if ( dword_1800182D0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800182D0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180002ab8  sub     rsp, 28h
0x180002abc  mov     ecx, cs:dword_1800182D0
0x180002ac2  sub     ecx, 1
0x180002ac5  jz      short loc_180002AFF
0x180002ac7  cmp     ecx, 1
0x180002aca  jz      short loc_180002AFB
0x180002acc  lea     rdx, [rsp+28h+arg_0]
0x180002ad1  mov     [rsp+28h+arg_0], 0
0x180002ad6  lea     rcx, asc_180011058; ">@"
0x180002add  call    ApiSetQueryApiSetPresence_0
0x180002ae2  test    eax, eax
0x180002ae4  js      short loc_180002AFB
0x180002ae6  mov     al, [rsp+28h+arg_0]
0x180002aea  mov     cl, al
0x180002aec  neg     cl
0x180002aee  sbb     edx, edx
0x180002af0  add     edx, 2
0x180002af3  mov     cs:dword_1800182D0, edx
0x180002af9  jmp     short loc_180002B01
0x180002afb  xor     al, al
0x180002afd  jmp     short loc_180002B01
0x180002aff  mov     al, 1
0x180002b01  add     rsp, 28h
0x180002b05  retn
```
