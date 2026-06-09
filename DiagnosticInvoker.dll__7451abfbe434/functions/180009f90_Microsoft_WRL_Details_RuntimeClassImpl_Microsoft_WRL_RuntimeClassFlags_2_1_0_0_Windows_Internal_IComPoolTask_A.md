# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::AddRef(void)

- ea: `0x180009f90`
- end: `0x180009fb9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009f90`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::AddRef(
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
0x180009f90  mov     r9d, 7FFFFFFFh
0x180009f96  jmp     short loc_180009FA6
0x180009f98  lea     edx, [r8+1]
0x180009f9c  mov     eax, r8d
0x180009f9f  lock cmpxchg [rcx+0Ch], edx
0x180009fa4  jz      short loc_180009FB1
0x180009fa6  mov     r8d, [rcx+0Ch]
0x180009faa  cmp     r8d, r9d
0x180009fad  jnz     short loc_180009F98
0x180009faf  jmp     short loc_180009FB5
0x180009fb1  lea     r9d, [r8+1]
0x180009fb5  mov     eax, r9d
0x180009fb8  retn
```
