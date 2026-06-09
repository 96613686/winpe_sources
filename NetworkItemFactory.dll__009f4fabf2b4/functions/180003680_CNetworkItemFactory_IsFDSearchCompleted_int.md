# CNetworkItemFactory::IsFDSearchCompleted(int *)

- ea: `0x180003680`
- end: `0x180003699`
- name: `?IsFDSearchCompleted@CNetworkItemFactory@@UEAAJPEAH@Z`
- size: `25`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003680`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::IsFDSearchCompleted(CNetworkItemFactory *this, int *a2)
{
  __int64 result; // rax

  result = 2147500037LL;
  if ( *((_DWORD *)this + 14) )
  {
    if ( *((_DWORD *)this + 16) )
    {
      *a2 = *((_DWORD *)this + 15);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003680  cmp     dword ptr [rcx+38h], 0
0x180003684  mov     eax, 80004005h
0x180003689  jz      short locret_180003698
0x18000368b  cmp     dword ptr [rcx+40h], 0
0x18000368f  jz      short locret_180003698
0x180003691  mov     eax, [rcx+3Ch]
0x180003694  mov     [rdx], eax
0x180003696  xor     eax, eax
0x180003698  retn
```
