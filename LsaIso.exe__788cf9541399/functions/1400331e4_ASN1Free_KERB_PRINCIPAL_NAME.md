# ASN1Free_KERB_PRINCIPAL_NAME

- ea: `0x1400331e4`
- end: `0x14003322d`
- name: `ASN1Free_KERB_PRINCIPAL_NAME`
- size: `73`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x140032600`
- `0x140032670`
- `0x140032790`
- `0x140032834`
- `0x140032a40`
- `0x140032b40`
- `0x140032bc0`
- `0x140032cb8`
- `0x140032dac`
- `0x140032ef0`
- `0x1400330f0`
- `0x1400331b0`
- `0x1400333e0`
- `0x140033430`
- `0x140033470`
- `0x1400334f0`
- `0x140033540`
- `0x1400335e0`
- `0x140033850`

## callees

- `0x1400331e4`

## import_xrefs

- `MSASN1!ASN1Free` at `0x140033214`
- `MSASN1!ASN1Free` at `0x140033214`
- `MSASN1!ASN1ztcharstring_free` at `0x140033208`
- `MSASN1!ASN1ztcharstring_free` at `0x140033208`

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
0x1400331e4  test    rcx, rcx
0x1400331e7  jz      short locret_14003322C
0x1400331e9  mov     [rsp+arg_0], rbx
0x1400331ee  push    rdi
0x1400331ef  sub     rsp, 20h
0x1400331f3  lea     rdi, [rcx+8]
0x1400331f7  test    rdi, rdi
0x1400331fa  jz      short loc_140033222
0x1400331fc  mov     rdi, [rdi]
0x1400331ff  test    rdi, rdi
0x140033202  jz      short loc_140033222
0x140033204  mov     rcx, [rdi+8]
0x140033208  call    cs:__imp_ASN1ztcharstring_free
0x14003320e  mov     rbx, [rdi]
0x140033211  mov     rcx, rdi
0x140033214  call    cs:__imp_ASN1Free
0x14003321a  mov     rdi, rbx
0x14003321d  test    rbx, rbx
0x140033220  jnz     short loc_140033204
0x140033222  mov     rbx, [rsp+28h+arg_0]
0x140033227  add     rsp, 20h
0x14003322b  pop     rdi
0x14003322c  retn
```
