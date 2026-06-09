# CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::~AutoRef<CommonUtil::ISecurityAttributes>(void)

- ea: `0x180006910`
- end: `0x18000694d`
- name: `??1?$AutoRef@UISecurityAttributes@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009ab4`

## callees

- `0x180006910`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::~AutoRef<CommonUtil::ISecurityAttributes>(
        __int64 *a1)
{
  __int64 v1; // rcx
  signed __int32 v2; // eax
  bool v3; // cc
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 8) == 1 )
    {
      *(_DWORD *)(v1 + 8) = 0;
    }
    else
    {
      v2 = _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 8), 0xFFFFFFFF);
      v3 = v2 <= 1;
      result = (unsigned int)(v2 - 1);
      if ( !v3 )
        return result;
    }
    return (**(__int64 (__fastcall ***)(__int64))v1)(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180006910  sub     rsp, 28h
0x180006914  mov     rcx, [rcx]
0x180006917  test    rcx, rcx
0x18000691a  jz      short loc_180006948
0x18000691c  mov     eax, [rcx+8]
0x18000691f  mov     edx, 1
0x180006924  cmp     eax, edx
0x180006926  jnz     short loc_180006931
0x180006928  mov     dword ptr [rcx+8], 0
0x18000692f  jmp     short loc_18000693D
0x180006931  or      eax, 0FFFFFFFFh
0x180006934  lock xadd [rcx+8], eax
0x180006939  sub     eax, edx
0x18000693b  jg      short loc_180006948
0x18000693d  mov     rax, [rcx]
0x180006940  mov     rax, [rax]
0x180006943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006948  add     rsp, 28h
0x18000694c  retn
```
