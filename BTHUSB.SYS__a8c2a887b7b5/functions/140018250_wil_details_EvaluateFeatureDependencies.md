# wil_details_EvaluateFeatureDependencies

- ea: `0x140018250`
- end: `0x14001835c`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140018560`
- `0x14001d5b4`

## callees

- `0x140018250`
- `0x1400183a0`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  ;
}

```

## disassembly

```asm
0x140018250  mov     [rsp+arg_8], rbx
0x140018255  push    rsi
0x140018256  sub     rsp, 20h
0x14001825a  lea     rbx, wil_details_featureDescriptors_a
0x140018261  mov     [rsp+28h+arg_0], 0
0x14001826a  lea     rsi, wil_details_featureDescriptors_a
0x140018271  mov     rcx, rbx
0x140018274  cmp     rbx, rsi
0x140018277  jnb     loc_140018350
0x14001827d  cmp     qword ptr [rcx], 0
0x140018281  jnz     short loc_14001828E
0x140018283  add     rcx, 8
0x140018287  cmp     rcx, rsi
0x14001828a  jb      short loc_14001827D
0x14001828c  jmp     short loc_140018308
0x14001828e  test    rcx, rcx
0x140018291  jz      short loc_140018308
0x140018293  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140018298  mov     rax, [rcx]
0x14001829b  mov     edx, [rax]
0x14001829d  bt      edx, 9
0x1400182a1  jnb     short loc_1400182E0
0x1400182a3  mov     r8d, edx
0x1400182a6  and     r8d, 180h
0x1400182ad  jnz     short loc_1400182B9
0x1400182af  xor     eax, eax
0x1400182b1  cmp     [rcx+1Fh], al
0x1400182b4  setnz   al
0x1400182b7  jmp     short loc_1400182C5
0x1400182b9  xor     eax, eax
0x1400182bb  cmp     r8d, 100h
0x1400182c2  setz    al
0x1400182c5  shl     eax, 6
0x1400182c8  and     edx, 40h
0x1400182cb  xor     edx, eax
0x1400182cd  mov     eax, r9d
0x1400182d0  and     eax, 0FFFFFFBFh
0x1400182d3  mov     r9d, edx
0x1400182d6  or      r9d, eax
0x1400182d9  mov     rax, [rcx]
0x1400182dc  lock xor [rax], r9d
0x1400182e0  add     rcx, 38h ; '8'
0x1400182e4  jmp     short loc_1400182F0
0x1400182e6  cmp     qword ptr [rcx], 0
0x1400182ea  jnz     short loc_1400182F7
0x1400182ec  add     rcx, 8
0x1400182f0  cmp     rcx, rsi
0x1400182f3  jb      short loc_1400182E6
0x1400182f5  jmp     short loc_140018308
0x1400182f7  test    rcx, rcx
0x1400182fa  jnz     short loc_140018298
0x1400182fc  jmp     short loc_140018308
0x1400182fe  cmp     qword ptr [rbx], 0
0x140018302  jnz     short loc_14001834B
0x140018304  add     rbx, 8
0x140018308  cmp     rbx, rsi
0x14001830b  jb      short loc_1400182FE
0x14001830d  jmp     short loc_140018350
0x14001830f  mov     rcx, [rbx]
0x140018312  mov     [rsp+28h+arg_0], 0
0x14001831b  mov     eax, [rcx]
0x14001831d  mov     dword ptr [rsp+28h+arg_0], eax
0x140018321  bt      eax, 9
0x140018325  jnb     short loc_140018334
0x140018327  mov     rdx, [rsp+28h+arg_0]
0x14001832c  mov     r8, rbx
0x14001832f  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140018334  add     rbx, 38h ; '8'
0x140018338  jmp     short loc_140018344
0x14001833a  cmp     qword ptr [rbx], 0
0x14001833e  jnz     short loc_14001834B
0x140018340  add     rbx, 8
0x140018344  cmp     rbx, rsi
0x140018347  jb      short loc_14001833A
0x140018349  jmp     short loc_140018350
0x14001834b  test    rbx, rbx
0x14001834e  jnz     short loc_14001830F
0x140018350  mov     rbx, [rsp+28h+arg_8]
0x140018355  add     rsp, 20h
0x140018359  pop     rsi
0x14001835a  retn
```
