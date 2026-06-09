# CommonUtil::CRefObjectFor<CommonUtil::IEnumFiles>::AddRef(void)

- ea: `0x140011e10`
- end: `0x140011e2d`
- name: `?AddRef@?$CRefObjectFor@UIEnumFiles@CommonUtil@@@CommonUtil@@UEBAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011e10`

## pseudocode

```c
__int64 __fastcall CommonUtil::CRefObjectFor<CommonUtil::IEnumFiles>::AddRef(__int64 a1)
{
  __int64 result; // rax

  result = 1;
  if ( *(_DWORD *)(a1 + 8) )
    return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  *(_DWORD *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x140011e10  mov     eax, [rcx+8]
0x140011e13  mov     rdx, rcx
0x140011e16  test    eax, eax
0x140011e18  mov     eax, 1
0x140011e1d  jnz     short loc_140011E23
0x140011e1f  mov     [rcx+8], eax
0x140011e22  retn
0x140011e23  mov     ecx, eax
0x140011e25  lock xadd [rdx+8], ecx
0x140011e2a  add     eax, ecx
0x140011e2c  retn
```
