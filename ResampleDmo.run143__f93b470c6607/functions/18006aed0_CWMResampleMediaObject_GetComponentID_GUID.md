# CWMResampleMediaObject::GetComponentID(_GUID *)

- ea: `0x18006aed0`
- end: `0x18006aee9`
- name: `?GetComponentID@CWMResampleMediaObject@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CWMResampleMediaObject *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18006aed0`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::GetComponentID(CWMResampleMediaObject *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = (struct _GUID)MFComponentID_ResampleMediaObject;
  return result;
}

```

## disassembly

```asm
0x18006aed0  test    rdx, rdx
0x18006aed3  jnz     short loc_18006AEDB
0x18006aed5  mov     eax, 80004003h
0x18006aeda  retn
0x18006aedb  movups  xmm0, cs:MFComponentID_ResampleMediaObject
0x18006aee2  xor     eax, eax
0x18006aee4  movdqu  xmmword ptr [rdx], xmm0
0x18006aee8  retn
```
