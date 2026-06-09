# CLogMgr::Get64BitTickCount(void)

- ea: `0x18000651c`
- end: `0x18000655e`
- name: `?Get64BitTickCount@CLogMgr@@SA_KXZ`
- size: `66`
- prototype: `unsigned __int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000699c`
- `0x1800073b4`
- `0x180007b40`
- `0x180008248`

## callees

- `0x18000651c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000652c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000652c`

## pseudocode

```c
unsigned __int64 CLogMgr::Get64BitTickCount(void)
{
  DWORD TickCount; // eax
  unsigned int v1; // ecx

  dword_18001FA90 = dword_18001FA8C;
  TickCount = GetTickCount();
  v1 = dword_18001FA88;
  dword_18001FA8C = TickCount;
  if ( TickCount < dword_18001FA90 )
    v1 = ++dword_18001FA88;
  return TickCount | ((unsigned __int64)v1 << 32);
}

```

## disassembly

```asm
0x18000651c  sub     rsp, 28h
0x180006520  mov     eax, cs:dword_18001FA8C
0x180006526  mov     cs:dword_18001FA90, eax
0x18000652c  call    cs:__imp_GetTickCount
0x180006532  cmp     eax, cs:dword_18001FA90
0x180006538  mov     ecx, cs:dword_18001FA88
0x18000653e  mov     edx, eax
0x180006540  mov     cs:dword_18001FA8C, edx
0x180006546  jnb     short loc_180006550
0x180006548  inc     ecx
0x18000654a  mov     cs:dword_18001FA88, ecx
0x180006550  mov     eax, ecx
0x180006552  shl     rax, 20h
0x180006556  or      rax, rdx
0x180006559  add     rsp, 28h
0x18000655d  retn
```
