# PasskeysCapabilityHandler::GetConsentNameFromConsentId(ushort const *,ushort const *,ushort * *)

- ea: `0x1800114e0`
- end: `0x18001156a`
- name: `?GetConsentNameFromConsentId@PasskeysCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z`
- size: `138`
- prototype: `__int64 __fastcall(PasskeysCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011570`

## callees

- `0x1800114e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011552`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011533`

## pseudocode

```c
__int64 __fastcall PasskeysCapabilityHandler::GetConsentNameFromConsentId(
        PasskeysCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const wchar_t *v5; // rbx
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax

  v5 = a3;
  if ( !a2 || !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( !a3 || !*a3 || *a3 == 42 && !a3[1] )
    v5 = L"All Passkeys";
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6 + 2);
  *a4 = v7;
  if ( !v7 )
    return 2147942414LL;
  _o_wcscpy_s(v7, v6 + 1, v5);
  return 0;
}

```

## disassembly

```asm
0x1800114e0  push    rbx
0x1800114e2  push    rbp
0x1800114e3  push    rsi
0x1800114e4  push    rdi
0x1800114e5  sub     rsp, 28h
0x1800114e9  xor     ebp, ebp
0x1800114eb  mov     rsi, r9
0x1800114ee  mov     rbx, r8
0x1800114f1  test    rdx, rdx
0x1800114f4  jz      short loc_18001155C
0x1800114f6  test    r9, r9
0x1800114f9  jz      short loc_18001155C
0x1800114fb  mov     [r9], rbp
0x1800114fe  test    rbx, rbx
0x180011501  jz      short loc_180011517
0x180011503  cmp     [r8], bp
0x180011507  jz      short loc_180011517
0x180011509  cmp     word ptr [r8], 2Ah ; '*'
0x18001150e  jnz     short loc_18001151E
0x180011510  cmp     [r8+2], bp
0x180011515  jnz     short loc_18001151E
0x180011517  lea     rbx, aAllPasskeys; "All Passkeys"
0x18001151e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011522  inc     rdi
0x180011525  cmp     [rbx+rdi*2], bp
0x180011529  jnz     short loc_180011522
0x18001152b  lea     rcx, ds:2[rdi*2]; cb
0x180011533  call    cs:__imp_CoTaskMemAlloc
0x180011539  mov     [rsi], rax
0x18001153c  test    rax, rax
0x18001153f  jnz     short loc_180011548
0x180011541  mov     eax, 8007000Eh
0x180011546  jmp     short loc_180011561
0x180011548  lea     rdx, [rdi+1]
0x18001154c  mov     r8, rbx
0x18001154f  mov     rcx, rax
0x180011552  call    cs:__imp__o_wcscpy_s
0x180011558  xor     eax, eax
0x18001155a  jmp     short loc_180011561
0x18001155c  mov     eax, 80070057h
0x180011561  add     rsp, 28h
0x180011565  pop     rdi
0x180011566  pop     rsi
0x180011567  pop     rbp
0x180011568  pop     rbx
0x180011569  retn
```
