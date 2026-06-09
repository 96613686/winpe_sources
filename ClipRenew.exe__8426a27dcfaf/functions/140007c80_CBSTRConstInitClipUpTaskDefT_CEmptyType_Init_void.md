# CBSTRConstInitClipUpTaskDefT<CEmptyType>::Init(void)

- ea: `0x140007c80`
- end: `0x140007cdc`
- name: `?Init@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@CAJXZ`
- size: `92`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140007c80`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140007ca9`
- `OLEAUT32!__imp_SysAllocString` at `0x140007ca9`

## pseudocode

```c
__int64 CBSTRConstInitClipUpTaskDefT<CEmptyType>::Init()
{
  int v0; // edi
  BSTR v1; // rax

  v0 = 0;
  while ( 1 )
  {
    v1 = SysAllocString((&off_140015068)[2 * v0]);
    CBSTRConstInitClipUpTaskDefT<CEmptyType>::m_consts[v0] = (__int64)v1;
    if ( !v1 )
      break;
    if ( (unsigned int)++v0 >= 9 )
      return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140007c80  mov     [rsp+arg_0], rbx
0x140007c85  mov     [rsp+arg_8], rsi
0x140007c8a  push    rdi
0x140007c8b  sub     rsp, 20h
0x140007c8f  xor     edi, edi
0x140007c91  lea     rsi, __ImageBase
0x140007c98  movsxd  rbx, edi
0x140007c9b  mov     rcx, rbx
0x140007c9e  add     rcx, rcx
0x140007ca1  mov     rcx, ds:rva off_140015068[rsi+rcx*8]; psz
0x140007ca9  call    cs:__imp_SysAllocString
0x140007caf  mov     rva ?m_consts@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@0PAPEAGA[rsi+rbx*8], rax; ushort * near * CBSTRConstInitClipUpTaskDefT<CEmptyType>::m_consts ...
0x140007cb7  test    rax, rax
0x140007cba  jz      short loc_140007CC7
0x140007cbc  inc     edi
0x140007cbe  cmp     edi, 9
0x140007cc1  jb      short loc_140007C98
0x140007cc3  xor     eax, eax
0x140007cc5  jmp     short loc_140007CCC
0x140007cc7  mov     eax, 80070057h
0x140007ccc  mov     rbx, [rsp+28h+arg_0]
0x140007cd1  mov     rsi, [rsp+28h+arg_8]
0x140007cd6  add     rsp, 20h
0x140007cda  pop     rdi
0x140007cdb  retn
```
