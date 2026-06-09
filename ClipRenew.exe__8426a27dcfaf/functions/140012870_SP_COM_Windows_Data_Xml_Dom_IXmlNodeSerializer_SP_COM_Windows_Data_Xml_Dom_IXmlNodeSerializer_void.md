# SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(void)

- ea: `0x140012870`
- end: `0x14001289a`
- name: `??1?$SP_COM@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012a38`

## callees

- `0x140012870`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140012870  push    rbx
0x140012872  sub     rsp, 20h
0x140012876  mov     rbx, rcx
0x140012879  mov     rcx, [rcx]
0x14001287c  test    rcx, rcx
0x14001287f  jz      short loc_140012894
0x140012881  mov     rax, [rcx]
0x140012884  mov     rax, [rax+10h]
0x140012888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001288d  mov     qword ptr [rbx], 0
0x140012894  add     rsp, 20h
0x140012898  pop     rbx
0x140012899  retn
```
