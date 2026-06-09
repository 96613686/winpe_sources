# std::expected<Mso::LoadMso::LoadDllResult,Mso::LoadMso::LoadDllError>::error(void)

- ea: `0x1400056e8`
- end: `0x140005714`
- name: `?error@?$expected@ULoadDllResult@LoadMso@Mso@@ULoadDllError@23@@std@@QEGAAAEAULoadDllError@LoadMso@Mso@@XZ`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004fe0`

## callees

- `0x1400056e8`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140005705`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140005705`

## pseudocode

```c
__int64 __fastcall std::expected<Mso::LoadMso::LoadDllResult,Mso::LoadMso::LoadDllError>::error(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 48) )
    _invoke_watson(0, 0, 0, 0, 0);
  return a1;
}

```

## disassembly

```asm
0x1400056e8  sub     rsp, 38h
0x1400056ec  cmp     byte ptr [rcx+30h], 0
0x1400056f0  jz      short loc_14000570C
0x1400056f2  xor     r9d, r9d; LineNo
0x1400056f5  mov     [rsp+38h+Reserved], 0; Reserved
0x1400056fe  xor     r8d, r8d; FileName
0x140005701  xor     edx, edx; FunctionName
0x140005703  xor     ecx, ecx; Expression
0x140005705  call    cs:__imp__invoke_watson
0x14000570c  mov     rax, rcx
0x14000570f  add     rsp, 38h
0x140005713  retn
```
