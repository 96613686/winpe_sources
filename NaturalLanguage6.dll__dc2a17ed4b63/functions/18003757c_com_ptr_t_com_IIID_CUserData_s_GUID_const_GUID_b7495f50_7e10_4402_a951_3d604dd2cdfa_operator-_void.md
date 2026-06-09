# _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)

- ea: `0x18003757c`
- end: `0x180037598`
- name: `??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ`
- size: `28`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031a20`
- `0x180034a60`
- `0x180038660`
- `0x18003a2a0`
- `0x18003b510`
- `0x18003b808`
- `0x18003b8d0`
- `0x18003d1f4`
- `0x18004ccd0`
- `0x18004cde0`
- `0x18004ce50`
- `0x18004d020`
- `0x18004d4b4`
- `0x18004ea14`
- `0x180051df4`
- `0x180051f1c`
- `0x180054e30`
- `0x180057ec0`
- `0x180058510`
- `0x180059860`
- `0x180059f80`
- `0x18006b1d4`
- `0x18006b38c`
- `0x18006b554`

## callees

- `0x180003894`
- `0x18003757c`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( !*a1 )
    _com_issue_error(-2147467261);
  return result;
}

```

## disassembly

```asm
0x18003757c  sub     rsp, 28h
0x180037580  mov     rax, [rcx]
0x180037583  test    rax, rax
0x180037586  jnz     short loc_180037593
0x180037588  mov     ecx, 80004003h; int
0x18003758d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180037593  add     rsp, 28h
0x180037597  retn
```
