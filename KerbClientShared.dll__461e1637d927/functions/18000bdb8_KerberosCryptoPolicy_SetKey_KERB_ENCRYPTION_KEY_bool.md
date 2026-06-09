# KerberosCryptoPolicy::SetKey(_KERB_ENCRYPTION_KEY *,bool)

- ea: `0x18000bdb8`
- end: `0x18000bdef`
- name: `?SetKey@KerberosCryptoPolicy@@QEAAXPEAU_KERB_ENCRYPTION_KEY@@_N@Z`
- size: `55`
- prototype: `void __fastcall(KerberosCryptoPolicy *__hidden this, struct _KERB_ENCRYPTION_KEY *, bool)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009c50`
- `0x180009d60`
- `0x180009fa0`
- `0x18000a1b0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000b790`
- `0x18000bcf4`
- `0x18000c498`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180016190`

## callees

- `0x180007960`
- `0x18000bdb8`

## pseudocode

```c
void __fastcall KerberosCryptoPolicy::SetKey(KerberosCryptoPolicy *this, struct _KERB_ENCRYPTION_KEY *a2, char a3)
{
  __int64 v5; // rcx

  v5 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = a2;
  if ( v5 && *((_BYTE *)this + 104) )
    KerbFreeKey(v5);
  *((_BYTE *)this + 104) = a3;
}

```

## disassembly

```asm
0x18000bdb8  mov     [rsp+arg_0], rbx
0x18000bdbd  push    rdi
0x18000bdbe  sub     rsp, 20h
0x18000bdc2  mov     rbx, rcx
0x18000bdc5  mov     dil, r8b
0x18000bdc8  mov     rcx, [rcx+70h]
0x18000bdcc  mov     [rbx+70h], rdx
0x18000bdd0  test    rcx, rcx
0x18000bdd3  jz      short loc_18000BDE0
0x18000bdd5  cmp     byte ptr [rbx+68h], 0
0x18000bdd9  jz      short loc_18000BDE0
0x18000bddb  call    KerbFreeKey
0x18000bde0  mov     [rbx+68h], dil
0x18000bde4  mov     rbx, [rsp+28h+arg_0]
0x18000bde9  add     rsp, 20h
0x18000bded  pop     rdi
0x18000bdee  retn
```
