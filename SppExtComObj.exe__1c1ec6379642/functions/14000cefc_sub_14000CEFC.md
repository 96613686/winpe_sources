# sub_14000CEFC

- ea: `0x14000cefc`
- end: `0x14000cf70`
- name: `sub_14000CEFC`
- size: `116`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000cf78`
- `0x14000d194`
- `0x14000d8e0`
- `0x1400102b8`
- `0x1400104a8`
- `0x140010918`

## callees

- `0x14000b95c`
- `0x14000c5a0`
- `0x14000c930`
- `0x14000cefc`
- `0x14000eb74`

## pseudocode

```c
__int64 __fastcall sub_14000CEFC(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v4 = sub_14000C930(a1, &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a3 = v7;
    v7 = 0;
  }
  else
  {
    sub_14000C5A0(v4);
  }
  sub_14000EB74(v5);
  sub_14000B95C(&v7);
  if ( (v5 & 0x80000000) != 0 )
    sub_14000C5A0(v5);
  sub_14000EB74(v5);
  return v5;
}

```

## disassembly

```asm
0x14000cefc  mov     rax, rsp
0x14000ceff  mov     [rax+8], rbx
0x14000cf03  mov     [rax+10h], rdx
0x14000cf07  push    rdi
0x14000cf08  sub     rsp, 20h
0x14000cf0c  lea     rdx, [rax+10h]
0x14000cf10  mov     qword ptr [rax+10h], 0
0x14000cf18  mov     rdi, r8
0x14000cf1b  call    sub_14000C930
0x14000cf20  mov     ebx, eax
0x14000cf22  test    eax, eax
0x14000cf24  jns     short loc_14000CF2F
0x14000cf26  mov     ecx, eax
0x14000cf28  call    sub_14000C5A0
0x14000cf2d  jmp     short loc_14000CF40
0x14000cf2f  mov     rax, [rsp+28h+arg_8]
0x14000cf34  mov     [rdi], rax
0x14000cf37  mov     [rsp+28h+arg_8], 0
0x14000cf40  mov     ecx, ebx
0x14000cf42  call    sub_14000EB74
0x14000cf47  lea     rcx, [rsp+28h+arg_8]
0x14000cf4c  call    sub_14000B95C
0x14000cf51  test    ebx, ebx
0x14000cf53  jns     short loc_14000CF5C
0x14000cf55  mov     ecx, ebx
0x14000cf57  call    sub_14000C5A0
0x14000cf5c  mov     ecx, ebx
0x14000cf5e  call    sub_14000EB74
0x14000cf63  mov     eax, ebx
0x14000cf65  mov     rbx, [rsp+28h+arg_0]
0x14000cf6a  add     rsp, 20h
0x14000cf6e  pop     rdi
0x14000cf6f  retn
```
