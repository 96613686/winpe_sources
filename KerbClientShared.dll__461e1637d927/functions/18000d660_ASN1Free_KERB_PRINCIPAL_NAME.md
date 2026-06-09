# ASN1Free_KERB_PRINCIPAL_NAME

- ea: `0x18000d660`
- end: `0x18000d6a9`
- name: `ASN1Free_KERB_PRINCIPAL_NAME`
- size: `73`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d564`
- `0x18000d5f0`
- `0x18000d6b0`
- `0x180026e70`
- `0x180026ee0`
- `0x180027000`
- `0x1800270a4`
- `0x1800271f8`
- `0x180027300`
- `0x180027474`
- `0x180027560`
- `0x180027760`
- `0x180027820`
- `0x180027a00`
- `0x180027a50`
- `0x180027a90`
- `0x180027ae0`
- `0x180027b80`
- `0x180027df0`

## callees

- `0x18000d660`

## import_xrefs

- `MSASN1!ASN1ztcharstring_free` at `0x18000d684`
- `MSASN1!ASN1ztcharstring_free` at `0x18000d684`
- `MSASN1!ASN1Free` at `0x18000d690`
- `MSASN1!ASN1Free` at `0x18000d690`

## pseudocode

```c
__int64 __fastcall ASN1Free_KERB_PRINCIPAL_NAME(__int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    if ( a1 != -8 )
    {
      v1 = *(_QWORD **)(a1 + 8);
      if ( v1 )
      {
        do
        {
          ASN1ztcharstring_free(v1[1]);
          v2 = (_QWORD *)*v1;
          result = ASN1Free(v1);
          v1 = v2;
        }
        while ( v2 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d660  test    rcx, rcx
0x18000d663  jz      short locret_18000D6A8
0x18000d665  mov     [rsp+arg_0], rbx
0x18000d66a  push    rdi
0x18000d66b  sub     rsp, 20h
0x18000d66f  lea     rdi, [rcx+8]
0x18000d673  test    rdi, rdi
0x18000d676  jz      short loc_18000D69E
0x18000d678  mov     rdi, [rdi]
0x18000d67b  test    rdi, rdi
0x18000d67e  jz      short loc_18000D69E
0x18000d680  mov     rcx, [rdi+8]
0x18000d684  call    cs:__imp_ASN1ztcharstring_free
0x18000d68a  mov     rbx, [rdi]
0x18000d68d  mov     rcx, rdi
0x18000d690  call    cs:__imp_ASN1Free
0x18000d696  mov     rdi, rbx
0x18000d699  test    rbx, rbx
0x18000d69c  jnz     short loc_18000D680
0x18000d69e  mov     rbx, [rsp+28h+arg_0]
0x18000d6a3  add     rsp, 20h
0x18000d6a7  pop     rdi
0x18000d6a8  retn
```
