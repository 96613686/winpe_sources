# CMPEG2Demultiplexer::GetClassID(_GUID *)

- ea: `0x180014b90`
- end: `0x180014ba9`
- name: `?GetClassID@CMPEG2Demultiplexer@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014bb0`

## callees

- `0x180014b90`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::GetClassID(CMPEG2Demultiplexer *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = CLSID_MPEG2Demultiplexer;
  return result;
}

```

## disassembly

```asm
0x180014b90  test    rdx, rdx
0x180014b93  jnz     short loc_180014B9B
0x180014b95  mov     eax, 80004003h
0x180014b9a  retn
0x180014b9b  movups  xmm0, xmmword ptr cs:CLSID_MPEG2Demultiplexer.Data1
0x180014ba2  xor     eax, eax
0x180014ba4  movdqu  xmmword ptr [rdx], xmm0
0x180014ba8  retn
```
