# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::AddRef(void)

- ea: `0x140008ba0`
- end: `0x140008bc9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008bd0`

## callees

- `0x140008ba0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 20);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140008ba0  mov     r9d, 7FFFFFFFh
0x140008ba6  jmp     short loc_140008BB6
0x140008ba8  lea     edx, [r8+1]
0x140008bac  mov     eax, r8d
0x140008baf  lock cmpxchg [rcx+14h], edx
0x140008bb4  jz      short loc_140008BC1
0x140008bb6  mov     r8d, [rcx+14h]
0x140008bba  cmp     r8d, r9d
0x140008bbd  jnz     short loc_140008BA8
0x140008bbf  jmp     short loc_140008BC5
0x140008bc1  lea     r9d, [r8+1]
0x140008bc5  mov     eax, r9d
0x140008bc8  retn
```
