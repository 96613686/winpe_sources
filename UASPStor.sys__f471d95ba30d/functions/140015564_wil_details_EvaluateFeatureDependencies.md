# wil_details_EvaluateFeatureDependencies

- ea: `0x140015564`
- end: `0x140015673`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140015850`
- `0x140017078`

## callees

- `0x140015564`
- `0x1400156b8`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  ;
}

```

## disassembly

```asm
0x140015564  mov     [rsp+arg_8], rbx
0x140015569  push    rsi
0x14001556a  sub     rsp, 20h
0x14001556e  lea     rbx, wil_details_featureDescriptors_a
0x140015575  mov     [rsp+28h+arg_0], 0
0x14001557e  lea     rsi, wil_details_featureDescriptors_a
0x140015585  mov     rcx, rbx
0x140015588  cmp     rbx, rsi
0x14001558b  jnb     loc_140015667
0x140015591  cmp     qword ptr [rcx], 0
0x140015595  jnz     short loc_1400155A2
0x140015597  add     rcx, 8
0x14001559b  cmp     rcx, rsi
0x14001559e  jb      short loc_140015591
0x1400155a0  jmp     short loc_14001561F
0x1400155a2  test    rcx, rcx
0x1400155a5  jz      short loc_14001561F
0x1400155a7  mov     r9d, dword ptr [rsp+28h+arg_0]
0x1400155ac  mov     rax, [rcx]
0x1400155af  mov     edx, [rax]
0x1400155b1  bt      edx, 9
0x1400155b5  jnb     short loc_1400155F7
0x1400155b7  mov     r8d, edx
0x1400155ba  and     r8d, 180h
0x1400155c1  jnz     short loc_1400155CD
0x1400155c3  xor     eax, eax
0x1400155c5  cmp     [rcx+1Fh], al
0x1400155c8  setnz   al
0x1400155cb  jmp     short loc_1400155D9
0x1400155cd  xor     eax, eax
0x1400155cf  cmp     r8d, 100h
0x1400155d6  setz    al
0x1400155d9  shr     edx, 6
0x1400155dc  and     edx, 1
0x1400155df  xor     edx, eax
0x1400155e1  mov     eax, r9d
0x1400155e4  shl     edx, 6
0x1400155e7  and     eax, 0FFFFFFBFh
0x1400155ea  mov     r9d, edx
0x1400155ed  or      r9d, eax
0x1400155f0  mov     rax, [rcx]
0x1400155f3  lock xor [rax], r9d
0x1400155f7  add     rcx, 38h ; '8'
0x1400155fb  jmp     short loc_140015607
0x1400155fd  cmp     qword ptr [rcx], 0
0x140015601  jnz     short loc_14001560E
0x140015603  add     rcx, 8
0x140015607  cmp     rcx, rsi
0x14001560a  jb      short loc_1400155FD
0x14001560c  jmp     short loc_14001561F
0x14001560e  test    rcx, rcx
0x140015611  jnz     short loc_1400155AC
0x140015613  jmp     short loc_14001561F
0x140015615  cmp     qword ptr [rbx], 0
0x140015619  jnz     short loc_140015662
0x14001561b  add     rbx, 8
0x14001561f  cmp     rbx, rsi
0x140015622  jb      short loc_140015615
0x140015624  jmp     short loc_140015667
0x140015626  mov     rcx, [rbx]
0x140015629  mov     [rsp+28h+arg_0], 0
0x140015632  mov     eax, [rcx]
0x140015634  mov     dword ptr [rsp+28h+arg_0], eax
0x140015638  bt      eax, 9
0x14001563c  jnb     short loc_14001564B
0x14001563e  mov     rdx, [rsp+28h+arg_0]
0x140015643  mov     r8, rbx
0x140015646  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14001564b  add     rbx, 38h ; '8'
0x14001564f  jmp     short loc_14001565B
0x140015651  cmp     qword ptr [rbx], 0
0x140015655  jnz     short loc_140015662
0x140015657  add     rbx, 8
0x14001565b  cmp     rbx, rsi
0x14001565e  jb      short loc_140015651
0x140015660  jmp     short loc_140015667
0x140015662  test    rbx, rbx
0x140015665  jnz     short loc_140015626
0x140015667  mov     rbx, [rsp+28h+arg_8]
0x14001566c  add     rsp, 20h
0x140015670  pop     rsi
0x140015671  retn
```
