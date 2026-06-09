# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::AddRef(void)

- ea: `0x140008b70`
- end: `0x140008b99`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008b70`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 12);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140008b70  mov     r9d, 7FFFFFFFh
0x140008b76  jmp     short loc_140008B86
0x140008b78  lea     edx, [r8+1]
0x140008b7c  mov     eax, r8d
0x140008b7f  lock cmpxchg [rcx+0Ch], edx
0x140008b84  jz      short loc_140008B91
0x140008b86  mov     r8d, [rcx+0Ch]
0x140008b8a  cmp     r8d, r9d
0x140008b8d  jnz     short loc_140008B78
0x140008b8f  jmp     short loc_140008B95
0x140008b91  lea     r9d, [r8+1]
0x140008b95  mov     eax, r9d
0x140008b98  retn
```
