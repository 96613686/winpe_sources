# ReadPifProps(_WIZDATA *)

- ea: `0x18001cd5c`
- end: `0x18001cdd9`
- name: `?ReadPifProps@@YAHPEAU_WIZDATA@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(struct _WIZDATA *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c310`
- `0x18001c5cc`

## callees

- `0x18001cd5c`

## import_xrefs

- `SHELL32!__imp_PifMgr_OpenProperties` at `0x18001cd8e`
- `SHELL32!__imp_PifMgr_OpenProperties` at `0x18001cd8e`
- `SHELL32!__imp_PifMgr_GetProperties` at `0x18001cdbb`
- `SHELL32!__imp_PifMgr_GetProperties` at `0x18001cdbb`
- `SHELL32!__imp_PifMgr_CloseProperties` at `0x18001cdc6`
- `SHELL32!__imp_PifMgr_CloseProperties` at `0x18001cdc6`

## pseudocode

```c
__int64 __fastcall ReadPifProps(struct _WIZDATA *a1)
{
  __int64 result; // rax
  void *v3; // rbx

  result = (__int64)PifMgr_OpenProperties(
                      (PCWSTR)((char *)a1 + ((*((_DWORD *)a1 + 2) & 0x10000000) != 0 ? 532LL : 12LL)),
                      0,
                      0,
                      0x8000u);
  v3 = (void *)result;
  if ( result )
  {
    PifMgr_GetProperties((HANDLE)result, (PCSTR)1, (char *)a1 + 2632, 658, 0);
    PifMgr_CloseProperties(v3, 1u);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001cd5c  mov     [rsp+arg_0], rbx
0x18001cd61  push    rdi
0x18001cd62  sub     rsp, 30h
0x18001cd66  mov     eax, [rcx+8]
0x18001cd69  mov     rdi, rcx
0x18001cd6c  and     eax, 10000000h
0x18001cd71  mov     r9d, 8000h; flOpt
0x18001cd77  neg     eax
0x18001cd79  sbb     rcx, rcx
0x18001cd7c  xor     r8d, r8d; hInf
0x18001cd7f  and     ecx, 208h
0x18001cd85  xor     edx, edx; pszPIF
0x18001cd87  add     rcx, 0Ch
0x18001cd8b  add     rcx, rdi; pszApp
0x18001cd8e  call    cs:__imp_PifMgr_OpenProperties
0x18001cd94  mov     rbx, rax
0x18001cd97  test    rax, rax
0x18001cd9a  jz      short loc_18001CDCE
0x18001cd9c  lea     r8, [rdi+0A48h]; lpProps
0x18001cda3  mov     [rsp+38h+flOpt], 0; flOpt
0x18001cdab  mov     edi, 1
0x18001cdb0  mov     r9d, 292h; cbProps
0x18001cdb6  mov     edx, edi; pszGroup
0x18001cdb8  mov     rcx, rbx; hProps
0x18001cdbb  call    cs:__imp_PifMgr_GetProperties
0x18001cdc1  mov     edx, edi; flOpt
0x18001cdc3  mov     rcx, rbx; hProps
0x18001cdc6  call    cs:__imp_PifMgr_CloseProperties
0x18001cdcc  mov     eax, edi
0x18001cdce  mov     rbx, [rsp+38h+arg_0]
0x18001cdd3  add     rsp, 30h
0x18001cdd7  pop     rdi
0x18001cdd8  retn
```
