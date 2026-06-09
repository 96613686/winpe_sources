# __tailMerge_gdiplus_dll

- ea: `0x180009442`
- end: `0x1800094bb`
- name: `__tailMerge_gdiplus_dll`
- size: `121`
- prototype: ``
- caller_count: `42`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800094c1`
- `0x1800094d3`
- `0x1800094e5`
- `0x1800094f7`
- `0x180009509`
- `0x18000951b`
- `0x18000952d`
- `0x18000953f`
- `0x180009551`
- `0x180009563`
- `0x180009575`
- `0x180009587`
- `0x180009599`
- `0x1800095ab`
- `0x1800095bd`
- `0x1800095cf`
- `0x1800095e1`
- `0x1800095f3`
- `0x180009605`
- `0x180009617`
- `0x180009629`
- `0x18000963b`
- `0x18000964d`
- `0x18000965f`
- `0x180009671`
- `0x180009683`
- `0x180009695`
- `0x1800096a7`
- `0x1800096b9`
- `0x1800096cb`
- `0x1800096dd`
- `0x1800096ef`
- `0x180009701`
- `0x180009713`
- `0x180009725`
- `0x180009737`
- `0x180009749`
- `0x18000975b`
- `0x18000976d`
- `0x18000977f`
- `0x180009791`
- `0x1800097a3`

## callees

- `0x180009442`
- `0x180046dc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_gdiplus_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_gdiplus_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009442  mov     [rsp+arg_0], rcx
0x180009447  mov     [rsp+arg_8], rdx
0x18000944c  mov     [rsp+arg_10], r8
0x180009451  mov     [rsp+arg_18], r9
0x180009456  sub     rsp, 68h
0x18000945a  movdqa  [rsp+68h+var_48], xmm0
0x180009460  movdqa  [rsp+68h+var_38], xmm1
0x180009466  movdqa  [rsp+68h+var_28], xmm2
0x18000946c  movdqa  [rsp+68h+var_18], xmm3
0x180009472  mov     rdx, rax
0x180009475  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdiplus_dll
0x18000947c  call    __delayLoadHelper2
0x180009481  movdqa  xmm0, [rsp+68h+var_48]
0x180009487  movdqa  xmm1, [rsp+68h+var_38]
0x18000948d  movdqa  xmm2, [rsp+68h+var_28]
0x180009493  movdqa  xmm3, [rsp+68h+var_18]
0x180009499  mov     rcx, [rsp+68h+arg_0]
0x18000949e  mov     rdx, [rsp+68h+arg_8]
0x1800094a3  mov     r8, [rsp+68h+arg_10]
0x1800094ab  mov     r9, [rsp+68h+arg_18]
0x1800094b3  add     rsp, 68h
0x1800094b7  jmp     short $+2
0x1800094b9  jmp     rax
```
