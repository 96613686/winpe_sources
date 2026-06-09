# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006214`
- end: `0x180006232`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `103`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041d4`
- `0x1800045a8`
- `0x180005338`
- `0x180006cdc`
- `0x180007ad0`
- `0x180007e40`
- `0x180007f30`
- `0x180008674`
- `0x1800086ec`
- `0x180008784`
- `0x180008804`
- `0x180008874`
- `0x1800088ec`
- `0x18000895c`
- `0x1800089cc`
- `0x180008a44`
- `0x180008abc`
- `0x180008b2c`
- `0x180008b88`
- `0x180008c3c`
- `0x180008cb4`
- `0x1800094c0`
- `0x180009670`
- `0x1800096d0`
- `0x180009798`
- `0x180009ca0`
- `0x180009d10`
- `0x180009d70`
- `0x180009de0`
- `0x180009e40`
- `0x180009eb0`
- `0x180009f30`
- `0x18000a190`
- `0x18000a200`
- `0x18000a280`
- `0x18000a3f0`
- `0x18000a660`
- `0x18000a6e0`
- `0x18000a760`
- `0x18000a810`
- `0x18000a920`
- `0x18000a9d0`
- `0x18000aa50`
- `0x18000b8e8`
- `0x18000c864`
- `0x18000c8d4`
- `0x18000c954`
- `0x18000c9c4`
- `0x18000ca3c`
- `0x18000cab4`

## callees

- `0x1800034c4`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180006214  sub     rsp, 48h
0x180006218  mov     rax, [rsp+48h]
0x18000621d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006222  mov     [rsp+48h+var_20], rax; __int64
0x180006227  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000622c  nop
0x18000622d  add     rsp, 48h
0x180006231  retn
```
