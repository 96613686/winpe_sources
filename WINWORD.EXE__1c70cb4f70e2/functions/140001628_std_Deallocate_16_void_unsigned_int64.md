# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x140001628`
- end: `0x14000166e`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `70`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003220`
- `0x14000395c`
- `0x140003978`
- `0x140003a50`
- `0x1400040d0`
- `0x140004138`
- `0x1400041fc`
- `0x140004754`
- `0x140004c2c`

## callees

- `0x140001628`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140001667`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140001667`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14000164d`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      _invoke_watson(0, 0, 0, 0, 0);
    a1 = (_QWORD *)*(a1 - 1);
  }
  free(a1);
}

```

## disassembly

```asm
0x140001628  sub     rsp, 38h
0x14000162c  cmp     rdx, 1000h
0x140001633  jb      short loc_140001649
0x140001635  mov     rdx, [rcx-8]
0x140001639  sub     rcx, rdx
0x14000163c  lea     rax, [rcx-8]
0x140001640  cmp     rax, 1Fh
0x140001644  ja      short loc_140001654
0x140001646  mov     rcx, rdx
0x140001649  add     rsp, 38h
0x14000164d  jmp     cs:__imp_free
0x140001654  xor     r9d, r9d; LineNo
0x140001657  mov     [rsp+38h+Reserved], 0; Reserved
0x140001660  xor     r8d, r8d; FileName
0x140001663  xor     edx, edx; FunctionName
0x140001665  xor     ecx, ecx; Expression
0x140001667  call    cs:__imp__invoke_watson
```
