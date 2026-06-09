# EdppIsAppxBroker

- ea: `0x140003dd8`
- end: `0x140003e24`
- name: `EdppIsAppxBroker`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002d5d4`

## callees

- `0x140003dd8`
- `0x140022b60`

## pseudocode

```c
__int64 __fastcall EdppIsAppxBroker(__int64 a1, bool *a2)
{
  __int64 v2; // rdi
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 56);
  result = *(unsigned int *)(v2 + 8);
  if ( (int)result >= 0
    || (result = AipGetPackageClaim(*(struct _KPROCESS **)v2, (_QWORD *)(v2 + 12)),
        *(_DWORD *)(v2 + 8) = result,
        (int)result >= 0) )
  {
    *a2 = (*(_DWORD *)(v2 + 12) & 0x40) != 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003dd8  mov     [rsp+arg_0], rbx
0x140003ddd  mov     [rsp+arg_8], rsi
0x140003de2  push    rdi
0x140003de3  sub     rsp, 20h
0x140003de7  mov     rdi, [rcx+38h]
0x140003deb  mov     rsi, rdx
0x140003dee  mov     eax, [rdi+8]
0x140003df1  test    eax, eax
0x140003df3  jns     short loc_140003E08
0x140003df5  mov     rcx, [rdi]
0x140003df8  lea     rdx, [rdi+0Ch]
0x140003dfc  call    AipGetPackageClaim
0x140003e01  mov     [rdi+8], eax
0x140003e04  test    eax, eax
0x140003e06  js      short loc_140003E13
0x140003e08  mov     ecx, [rdi+0Ch]
0x140003e0b  shr     ecx, 6
0x140003e0e  and     cl, 1
0x140003e11  mov     [rsi], cl
0x140003e13  mov     rbx, [rsp+28h+arg_0]
0x140003e18  mov     rsi, [rsp+28h+arg_8]
0x140003e1d  add     rsp, 20h
0x140003e21  pop     rdi
0x140003e22  retn
```
