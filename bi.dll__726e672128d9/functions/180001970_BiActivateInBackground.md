# BiActivateInBackground

- ea: `0x180001970`
- end: `0x1800019e6`
- name: `BiActivateInBackground`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800019f0`

## pseudocode

```c
__int64 __fastcall BiActivateInBackground(
        __int64 a1,
        unsigned __int16 *a2,
        void *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        int a10)
{
  return BiActivateInBackgroundEx(a1, 0, 0, a2, a3, a4, a5, 0, a6, a7, a8, a9, a10, 0);
}

```

## disassembly

```asm
0x180001970  mov     r11, rsp
0x180001973  sub     rsp, 78h
0x180001977  mov     eax, [rsp+78h+arg_48]
0x18000197e  mov     qword ptr [r11-10h], 0
0x180001986  mov     [rsp+78h+var_18], eax; int
0x18000198a  mov     rax, [rsp+78h+arg_40]
0x180001992  mov     [r11-20h], rax
0x180001996  mov     rax, [rsp+78h+arg_38]
0x18000199e  mov     [r11-28h], rax
0x1800019a2  mov     eax, [rsp+78h+arg_30]
0x1800019a9  mov     [rsp+78h+var_30], eax; int
0x1800019ad  mov     eax, [rsp+78h+arg_28]
0x1800019b4  mov     [rsp+78h+var_38], eax; int
0x1800019b8  mov     rax, [rsp+78h+arg_20]
0x1800019c0  mov     qword ptr [r11-40h], 0
0x1800019c8  mov     [r11-48h], rax
0x1800019cc  mov     [r11-50h], r9
0x1800019d0  mov     r9, rdx; int
0x1800019d3  mov     [r11-58h], r8
0x1800019d7  xor     edx, edx; int
0x1800019d9  xor     r8d, r8d; int
0x1800019dc  call    BiActivateInBackgroundEx
0x1800019e1  add     rsp, 78h
0x1800019e5  retn
```
