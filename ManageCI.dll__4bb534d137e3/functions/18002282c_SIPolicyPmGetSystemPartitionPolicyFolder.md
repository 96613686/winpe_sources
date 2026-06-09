# SIPolicyPmGetSystemPartitionPolicyFolder

- ea: `0x18002282c`
- end: `0x180022853`
- name: `SIPolicyPmGetSystemPartitionPolicyFolder`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020b44`
- `0x180021270`
- `0x1800220e0`
- `0x1800226d8`

## callees

- `0x18002282c`
- `0x18002285c`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetSystemPartitionPolicyFolder(__int64 a1)
{
  __int64 result; // rax

  result = SIPolicyPmGetSystemPartitionPolicyFolderCommon(MaxSystemInfoClass);
  if ( (int)result >= 0 )
    *(_BYTE *)(a1 + 17) = 0;
  return result;
}

```

## disassembly

```asm
0x18002282c  push    rbx
0x18002282e  sub     rsp, 20h
0x180022832  mov     r8, rdx
0x180022835  mov     rbx, rcx
0x180022838  mov     rdx, rcx
0x18002283b  mov     ecx, 62h ; 'b'; SystemInformationClass
0x180022840  call    SIPolicyPmGetSystemPartitionPolicyFolderCommon
0x180022845  test    eax, eax
0x180022847  js      short loc_18002284D
0x180022849  mov     byte ptr [rbx+11h], 0
0x18002284d  add     rsp, 20h
0x180022851  pop     rbx
0x180022852  retn
```
