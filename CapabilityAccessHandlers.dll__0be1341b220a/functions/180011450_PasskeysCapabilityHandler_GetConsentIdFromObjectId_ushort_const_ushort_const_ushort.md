# PasskeysCapabilityHandler::GetConsentIdFromObjectId(ushort const *,ushort const *,ushort * *)

- ea: `0x180011450`
- end: `0x1800114ce`
- name: `?GetConsentIdFromObjectId@PasskeysCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(PasskeysCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011570`

## callees

- `0x180011450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800114b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800114b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011495`

## pseudocode

```c
__int64 __fastcall PasskeysCapabilityHandler::GetConsentIdFromObjectId(
        PasskeysCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const wchar_t *v5; // rbx
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  unsigned int v8; // esi

  v5 = a3;
  if ( !a2 || !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( !a3 || !*a3 )
    v5 = L"*";
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6 + 2);
  *a4 = v7;
  if ( v7 )
  {
    v8 = 0;
    _o_wcscpy_s(v7, v6 + 1, v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180011450  push    rbx
0x180011452  push    rbp
0x180011453  push    rsi
0x180011454  push    rdi
0x180011455  sub     rsp, 28h
0x180011459  xor     ebp, ebp
0x18001145b  mov     rsi, r9
0x18001145e  mov     rbx, r8
0x180011461  test    rdx, rdx
0x180011464  jz      short loc_1800114C0
0x180011466  test    r9, r9
0x180011469  jz      short loc_1800114C0
0x18001146b  mov     [r9], rbp
0x18001146e  test    rbx, rbx
0x180011471  jz      short loc_180011479
0x180011473  cmp     [r8], bp
0x180011477  jnz     short loc_180011480
0x180011479  lea     rbx, asc_1800175E8; "*"
0x180011480  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011484  inc     rdi
0x180011487  cmp     [rbx+rdi*2], bp
0x18001148b  jnz     short loc_180011484
0x18001148d  lea     rcx, ds:2[rdi*2]; cb
0x180011495  call    cs:__imp_CoTaskMemAlloc
0x18001149b  mov     [rsi], rax
0x18001149e  test    rax, rax
0x1800114a1  jnz     short loc_1800114AA
0x1800114a3  mov     esi, 8007000Eh
0x1800114a8  jmp     short loc_1800114BC
0x1800114aa  lea     rdx, [rdi+1]
0x1800114ae  mov     r8, rbx
0x1800114b1  mov     rcx, rax
0x1800114b4  mov     esi, ebp
0x1800114b6  call    cs:__imp__o_wcscpy_s
0x1800114bc  mov     eax, esi
0x1800114be  jmp     short loc_1800114C5
0x1800114c0  mov     eax, 80070057h
0x1800114c5  add     rsp, 28h
0x1800114c9  pop     rdi
0x1800114ca  pop     rsi
0x1800114cb  pop     rbp
0x1800114cc  pop     rbx
0x1800114cd  retn
```
