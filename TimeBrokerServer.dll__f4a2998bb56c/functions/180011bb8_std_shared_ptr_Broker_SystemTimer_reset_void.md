# std::shared_ptr<Broker::SystemTimer>::reset(void)

- ea: `0x180011bb8`
- end: `0x180011be1`
- name: `?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ`
- size: `41`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ad8`
- `0x180013b40`

## callees

- `0x180005b30`
- `0x180011bb8`

## pseudocode

```c
void __fastcall std::shared_ptr<Broker::SystemTimer>::reset(_QWORD *a1)
{
  std::_Ref_count_base *v1; // rax

  *a1 = 0;
  v1 = (std::_Ref_count_base *)a1[1];
  a1[1] = 0;
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x180011bb8  sub     rsp, 28h
0x180011bbc  mov     qword ptr [rcx], 0
0x180011bc3  mov     rax, [rcx+8]
0x180011bc7  mov     qword ptr [rcx+8], 0
0x180011bcf  test    rax, rax
0x180011bd2  jz      short loc_180011BDC
0x180011bd4  mov     rcx, rax; this
0x180011bd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011bdc  add     rsp, 28h
0x180011be0  retn
```
