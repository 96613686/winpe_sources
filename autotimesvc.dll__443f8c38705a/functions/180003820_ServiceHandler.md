# ServiceHandler

- ea: `0x180003820`
- end: `0x180003857`
- name: `ServiceHandler`
- size: `55`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800037ec`
- `0x180003820`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  __int64 result; // rax
  DWORD v5; // ecx
  DWORD v6; // ecx

  result = 120;
  v5 = dwControl - 1;
  if ( !v5 )
  {
    InitiateStop();
    return 0;
  }
  v6 = v5 - 3;
  if ( !v6 )
    return 0;
  if ( v6 == 28 )
  {
    result = 0;
    if ( (_DWORD)xmmword_18001C30C == 3 )
      return 1115;
  }
  return result;
}

```

## disassembly

```asm
0x180003820  sub     rsp, 28h
0x180003824  mov     eax, 78h ; 'x'
0x180003829  sub     ecx, 1
0x18000382c  jz      short loc_18000384B
0x18000382e  sub     ecx, 3
0x180003831  jz      short loc_180003850
0x180003833  cmp     ecx, 1Ch
0x180003836  jnz     short loc_180003852
0x180003838  xor     eax, eax
0x18000383a  mov     ecx, 45Bh
0x18000383f  cmp     dword ptr cs:xmmword_18001C30C, 3
0x180003846  cmovz   eax, ecx
0x180003849  jmp     short loc_180003852
0x18000384b  call    ?InitiateStop@@YAXXZ; InitiateStop(void)
0x180003850  xor     eax, eax
0x180003852  add     rsp, 28h
0x180003856  retn
```
