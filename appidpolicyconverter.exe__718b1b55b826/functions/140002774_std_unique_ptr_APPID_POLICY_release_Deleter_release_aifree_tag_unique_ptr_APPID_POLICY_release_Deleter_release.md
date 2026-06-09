# std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>(void)

- ea: `0x140002774`
- end: `0x14000278b`
- name: `??1?$unique_ptr@U_APPID_POLICY@@U?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013c36`
- `0x140013c48`
- `0x140013d0d`
- `0x140013e7c`

## callees

- `0x140002774`
- `0x140008ef4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return AiFree(v1);
  return result;
}

```

## disassembly

```asm
0x140002774  sub     rsp, 28h
0x140002778  mov     rcx, [rcx]
0x14000277b  test    rcx, rcx
0x14000277e  jz      short loc_140002786
0x140002780  call    AiFree
0x140002785  nop
0x140002786  add     rsp, 28h
0x14000278a  retn
```
