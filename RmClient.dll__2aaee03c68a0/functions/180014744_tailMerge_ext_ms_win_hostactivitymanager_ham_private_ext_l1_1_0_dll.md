# __tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll

- ea: `0x180014744`
- end: `0x1800147bd`
- name: `__tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800147c3`
- `0x1800147d5`
- `0x1800147e7`
- `0x1800147f9`
- `0x18001480b`
- `0x18001481d`
- `0x18001482f`
- `0x180014841`
- `0x180014853`
- `0x180014865`
- `0x180014877`
- `0x180014889`
- `0x18001489b`
- `0x1800148ad`

## callees

- `0x18000f260`
- `0x180014744`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014744  mov     [rsp+arg_0], rcx
0x180014749  mov     [rsp+arg_8], rdx
0x18001474e  mov     [rsp+arg_10], r8
0x180014753  mov     [rsp+arg_18], r9
0x180014758  sub     rsp, 68h
0x18001475c  movdqa  [rsp+68h+var_48], xmm0
0x180014762  movdqa  [rsp+68h+var_38], xmm1
0x180014768  movdqa  [rsp+68h+var_28], xmm2
0x18001476e  movdqa  [rsp+68h+var_18], xmm3
0x180014774  mov     rdx, rax
0x180014777  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll
0x18001477e  call    __delayLoadHelper2
0x180014783  movdqa  xmm0, [rsp+68h+var_48]
0x180014789  movdqa  xmm1, [rsp+68h+var_38]
0x18001478f  movdqa  xmm2, [rsp+68h+var_28]
0x180014795  movdqa  xmm3, [rsp+68h+var_18]
0x18001479b  mov     rcx, [rsp+68h+arg_0]
0x1800147a0  mov     rdx, [rsp+68h+arg_8]
0x1800147a5  mov     r8, [rsp+68h+arg_10]
0x1800147ad  mov     r9, [rsp+68h+arg_18]
0x1800147b5  add     rsp, 68h
0x1800147b9  jmp     short $+2
0x1800147bb  jmp     rax
```
