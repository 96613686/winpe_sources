# Dossier::FreeKeyValuePairs(WOSCKeyValuePair *,ulong)

- ea: `0x18000d2a8`
- end: `0x18000d2f0`
- name: `?FreeKeyValuePairs@Dossier@@AEAAXPEAUWOSCKeyValuePair@@K@Z`
- size: `72`
- prototype: `void __fastcall(Dossier *__hidden this, struct WOSCKeyValuePair *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ccf0`

## callees

- `0x18000d2a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2e9`

## pseudocode

```c
void __fastcall Dossier::FreeKeyValuePairs(Dossier *this, LPVOID *a2, unsigned int a3)
{
  unsigned int i; // esi

  for ( i = 0; i < a3; ++i )
  {
    CoTaskMemFree(a2[2 * i]);
    CoTaskMemFree(a2[2 * i + 1]);
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x18000d2a8  push    rbx
0x18000d2aa  push    rbp
0x18000d2ab  push    rsi
0x18000d2ac  push    rdi
0x18000d2ad  sub     rsp, 28h
0x18000d2b1  xor     esi, esi
0x18000d2b3  mov     ebp, r8d
0x18000d2b6  mov     rdi, rdx
0x18000d2b9  test    r8d, r8d
0x18000d2bc  jz      short loc_18000D2DE
0x18000d2be  mov     ebx, esi
0x18000d2c0  add     rbx, rbx
0x18000d2c3  mov     rcx, [rdi+rbx*8]; pv
0x18000d2c7  call    cs:__imp_CoTaskMemFree
0x18000d2cd  mov     rcx, [rdi+rbx*8+8]; pv
0x18000d2d2  call    cs:__imp_CoTaskMemFree
0x18000d2d8  inc     esi
0x18000d2da  cmp     esi, ebp
0x18000d2dc  jb      short loc_18000D2BE
0x18000d2de  mov     rcx, rdi
0x18000d2e1  add     rsp, 28h
0x18000d2e5  pop     rdi
0x18000d2e6  pop     rsi
0x18000d2e7  pop     rbp
0x18000d2e8  pop     rbx
0x18000d2e9  jmp     cs:__imp_CoTaskMemFree
```
