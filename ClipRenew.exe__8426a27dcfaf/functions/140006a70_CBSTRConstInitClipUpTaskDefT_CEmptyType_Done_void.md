# CBSTRConstInitClipUpTaskDefT<CEmptyType>::Done(void)

- ea: `0x140006a70`
- end: `0x140006ab0`
- name: `?Done@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@CAJXZ`
- size: `64`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140006a70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140006a8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140006a8c`

## pseudocode

```c
__int64 CBSTRConstInitClipUpTaskDefT<CEmptyType>::Done()
{
  __int64 i; // rbx
  OLECHAR *v1; // rcx

  for ( i = 0; i != 9; ++i )
  {
    v1 = (OLECHAR *)CBSTRConstInitClipUpTaskDefT<CEmptyType>::m_consts[i];
    if ( v1 )
    {
      SysFreeString(v1);
      CBSTRConstInitClipUpTaskDefT<CEmptyType>::m_consts[i] = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140006a70  mov     [rsp+arg_0], rbx
0x140006a75  push    rdi
0x140006a76  sub     rsp, 20h
0x140006a7a  xor     ebx, ebx
0x140006a7c  lea     rdi, ?m_consts@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@0PAPEAGA; ushort * near * CBSTRConstInitClipUpTaskDefT<CEmptyType>::m_consts
0x140006a83  mov     rcx, [rdi+rbx*8]; bstrString
0x140006a87  test    rcx, rcx
0x140006a8a  jz      short loc_140006A9A
0x140006a8c  call    cs:__imp_SysFreeString
0x140006a92  mov     qword ptr [rdi+rbx*8], 0
0x140006a9a  inc     rbx
0x140006a9d  cmp     rbx, 9
0x140006aa1  jnz     short loc_140006A7C
0x140006aa3  mov     rbx, [rsp+28h+arg_0]
0x140006aa8  xor     eax, eax
0x140006aaa  add     rsp, 20h
0x140006aae  pop     rdi
0x140006aaf  retn
```
