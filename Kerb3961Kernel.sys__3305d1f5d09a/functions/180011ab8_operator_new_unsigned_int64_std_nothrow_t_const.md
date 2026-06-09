# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180011ab8`
- end: `0x180011b36`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `126`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180001170`
- `0x180001818`
- `0x18000186c`
- `0x1800060f0`
- `0x180006a20`
- `0x180009890`
- `0x180009964`
- `0x18000aac8`
- `0x18000af4c`
- `0x18000b300`
- `0x18000f5e0`
- `0x180010460`
- `0x180010b40`
- `0x180011d64`

## callees

- `0x180011ab8`
- `0x180012600`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x180011ae5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180011ae5`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  size_t v2; // rsi
  void *result; // rax
  _DWORD *PoolWithTag; // rbx

  v2 = a1 + 16;
  if ( a1 + 16 < a1 )
    return 0;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, a1 + 16, 0x4362724Bu);
  result = 0;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return result;
  }
  else
  {
    if ( !PoolWithTag )
      return result;
    memset(PoolWithTag, 0, v2);
  }
  *(_QWORD *)PoolWithTag = a1;
  result = PoolWithTag + 4;
  PoolWithTag[2] = 512;
  return result;
}

```

## disassembly

```asm
0x180011ab8  mov     [rsp+arg_0], rbx
0x180011abd  mov     [rsp+arg_8], rsi
0x180011ac2  push    rdi
0x180011ac3  sub     rsp, 20h
0x180011ac7  lea     rsi, [rcx+10h]
0x180011acb  mov     rdi, rcx
0x180011ace  cmp     rsi, rcx
0x180011ad1  jnb     short loc_180011AD7
0x180011ad3  xor     eax, eax
0x180011ad5  jmp     short loc_180011B25
0x180011ad7  mov     r8d, 4362724Bh; Tag
0x180011add  mov     rdx, rsi; NumberOfBytes
0x180011ae0  mov     ecx, 600h; PoolType
0x180011ae5  call    cs:__imp_ExAllocatePoolWithTag
0x180011aec  nop     dword ptr [rax+rax+00h]
0x180011af1  mov     rbx, rax
0x180011af4  xor     eax, eax
0x180011af6  cmp     cs:ExPoolZeroingNativelySupported, al
0x180011afc  jnz     short loc_180011B12
0x180011afe  test    rbx, rbx
0x180011b01  jz      short loc_180011B25
0x180011b03  mov     r8, rsi; Size
0x180011b06  xor     edx, edx; Val
0x180011b08  mov     rcx, rbx; void *
0x180011b0b  call    memset
0x180011b10  jmp     short loc_180011B17
0x180011b12  test    rbx, rbx
0x180011b15  jz      short loc_180011B25
0x180011b17  mov     [rbx], rdi
0x180011b1a  lea     rax, [rbx+10h]
0x180011b1e  mov     dword ptr [rbx+8], 200h
0x180011b25  mov     rbx, [rsp+28h+arg_0]
0x180011b2a  mov     rsi, [rsp+28h+arg_8]
0x180011b2f  add     rsp, 20h
0x180011b33  pop     rdi
0x180011b34  retn
```
