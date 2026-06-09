# IsShouldLicenseManagerServiceAutoStopPresent

- ea: `0x1800042ac`
- end: `0x1800042fa`
- name: `IsShouldLicenseManagerServiceAutoStopPresent`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001b00`
- `0x1800060f4`

## callees

- `0x1800042ac`
- `0x18000430c`

## pseudocode

```c
char IsShouldLicenseManagerServiceAutoStopPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800216D8 == 1 )
    return 1;
  if ( dword_1800216D8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"JL", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800216D8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800042ac  sub     rsp, 28h
0x1800042b0  mov     ecx, cs:dword_1800216D8
0x1800042b6  sub     ecx, 1
0x1800042b9  jz      short loc_1800042F3
0x1800042bb  cmp     ecx, 1
0x1800042be  jz      short loc_1800042EF
0x1800042c0  lea     rdx, [rsp+28h+arg_0]
0x1800042c5  mov     [rsp+28h+arg_0], 0
0x1800042ca  lea     rcx, aJl; "JL"
0x1800042d1  call    ApiSetQueryApiSetPresence_0
0x1800042d6  test    eax, eax
0x1800042d8  js      short loc_1800042EF
0x1800042da  mov     al, [rsp+28h+arg_0]
0x1800042de  mov     cl, al
0x1800042e0  neg     cl
0x1800042e2  sbb     edx, edx
0x1800042e4  add     edx, 2
0x1800042e7  mov     cs:dword_1800216D8, edx
0x1800042ed  jmp     short loc_1800042F5
0x1800042ef  xor     al, al
0x1800042f1  jmp     short loc_1800042F5
0x1800042f3  mov     al, 1
0x1800042f5  add     rsp, 28h
0x1800042f9  retn
```
