# wil_details_EvaluateFeatureDependencies

- ea: `0x140007970`
- end: `0x140007a57`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007bc0`
- `0x140008560`

## callees

- `0x140007970`
- `0x140007a60`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  ;
}

```

## disassembly

```asm
0x140007970  push    rbx
0x140007972  sub     rsp, 20h
0x140007976  xor     r11d, r11d
0x140007979  lea     r9, wil_details_featureDescriptors_a
0x140007980  lea     rbx, wil_details_featureDescriptors_a
0x140007987  mov     [rsp+28h+arg_0], r11
0x14000798c  mov     rcx, r9
0x14000798f  cmp     r9, rbx
0x140007992  jnb     loc_140007A50
0x140007998  cmp     [rcx], r11
0x14000799b  jnz     short loc_1400079A8
0x14000799d  add     rcx, 8
0x1400079a1  cmp     rcx, rbx
0x1400079a4  jb      short loc_140007998
0x1400079a6  jmp     short loc_140007A23
0x1400079a8  test    rcx, rcx
0x1400079ab  jz      short loc_140007A23
0x1400079ad  mov     r10d, dword ptr [rsp+28h+arg_0]
0x1400079b2  mov     rax, [rcx]
0x1400079b5  mov     edx, [rax]
0x1400079b7  bt      edx, 9
0x1400079bb  jnb     short loc_1400079FD
0x1400079bd  mov     r8d, edx
0x1400079c0  mov     eax, r11d
0x1400079c3  and     r8d, 180h
0x1400079ca  jnz     short loc_1400079D5
0x1400079cc  cmp     [rcx+1Fh], r11b
0x1400079d0  setnz   al
0x1400079d3  jmp     short loc_1400079DF
0x1400079d5  cmp     r8d, 100h
0x1400079dc  setz    al
0x1400079df  shr     edx, 6
0x1400079e2  and     edx, 1
0x1400079e5  xor     edx, eax
0x1400079e7  mov     eax, r10d
0x1400079ea  shl     edx, 6
0x1400079ed  and     eax, 0FFFFFFBFh
0x1400079f0  mov     r10d, edx
0x1400079f3  or      r10d, eax
0x1400079f6  mov     rax, [rcx]
0x1400079f9  lock xor [rax], r10d
0x1400079fd  add     rcx, 38h ; '8'
0x140007a01  jmp     short loc_140007A0C
0x140007a03  cmp     [rcx], r11
0x140007a06  jnz     short loc_140007A13
0x140007a08  add     rcx, 8
0x140007a0c  cmp     rcx, rbx
0x140007a0f  jb      short loc_140007A03
0x140007a11  jmp     short loc_140007A23
0x140007a13  test    rcx, rcx
0x140007a16  jnz     short loc_1400079B2
0x140007a18  jmp     short loc_140007A23
0x140007a1a  cmp     [r9], r11
0x140007a1d  jnz     short loc_140007A4B
0x140007a1f  add     r9, 8
0x140007a23  cmp     r9, rbx
0x140007a26  jb      short loc_140007A1A
0x140007a28  jmp     short loc_140007A50
0x140007a2a  mov     rcx, [r9]
0x140007a2d  mov     rdx, r9
0x140007a30  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140007a35  add     r9, 38h ; '8'
0x140007a39  jmp     short loc_140007A44
0x140007a3b  cmp     [r9], r11
0x140007a3e  jnz     short loc_140007A4B
0x140007a40  add     r9, 8
0x140007a44  cmp     r9, rbx
0x140007a47  jb      short loc_140007A3B
0x140007a49  jmp     short loc_140007A50
0x140007a4b  test    r9, r9
0x140007a4e  jnz     short loc_140007A2A
0x140007a50  add     rsp, 20h
0x140007a54  pop     rbx
0x140007a55  retn
```
