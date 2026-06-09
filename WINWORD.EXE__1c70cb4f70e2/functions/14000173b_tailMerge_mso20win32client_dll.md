# __tailMerge_mso20win32client_dll

- ea: `0x14000173b`
- end: `0x1400017b5`
- name: `__tailMerge_mso20win32client_dll`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400017b5`
- `0x1400017c1`
- `0x1400017cd`
- `0x1400017d9`

## callees

- `0x14000173b`
- `0x140002d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_mso20win32client_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_mso20win32client_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000173b  mov     [rsp+arg_0], rcx
0x140001740  mov     [rsp+arg_8], rdx
0x140001745  mov     [rsp+arg_10], r8
0x14000174a  mov     [rsp+arg_18], r9
0x14000174f  sub     rsp, 68h
0x140001753  movdqa  [rsp+68h+var_48], xmm0
0x140001759  movdqa  [rsp+68h+var_38], xmm1
0x14000175f  movdqa  [rsp+68h+var_28], xmm2
0x140001765  movdqa  [rsp+68h+var_18], xmm3
0x14000176b  mov     rdx, rax
0x14000176e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mso20win32client_dll
0x140001775  call    __delayLoadHelper2
0x14000177a  movdqa  xmm0, [rsp+68h+var_48]
0x140001780  movdqa  xmm1, [rsp+68h+var_38]
0x140001786  movdqa  xmm2, [rsp+68h+var_28]
0x14000178c  movdqa  xmm3, [rsp+68h+var_18]
0x140001792  mov     rcx, [rsp+68h+arg_0]
0x140001797  mov     rdx, [rsp+68h+arg_8]
0x14000179c  mov     r8, [rsp+68h+arg_10]
0x1400017a4  mov     r9, [rsp+68h+arg_18]
0x1400017ac  add     rsp, 68h
0x1400017b0  jmp     short loc_1400017B3
0x1400017b3  jmp     rax
```
