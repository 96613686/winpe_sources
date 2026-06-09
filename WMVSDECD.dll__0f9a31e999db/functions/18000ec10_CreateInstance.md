# CreateInstance

- ea: `0x18000ec10`
- end: `0x18000eca9`
- name: `CreateInstance`
- size: `153`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e720`
- `0x18000e780`
- `0x18000ec10`
- `0x180039b24`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  int i; // ebx
  const void **v10; // rsi
  _BYTE v11[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  for ( i = 0; i < 1; ++i )
  {
    v10 = (const void **)((char *)&off_180042000 + 16 * i);
    if ( !memcmp(*v10, Buf2, 0x10u) )
    {
      sub_18000E720(v11, v10);
      result = sub_18000E780(v11, a2, a3, a4);
      _InterlockedDecrement(&dword_180048EC4);
      return result;
    }
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000ec10  push    rbx
0x18000ec12  push    rbp
0x18000ec13  push    rsi
0x18000ec14  push    rdi
0x18000ec15  push    r14
0x18000ec17  push    r15
0x18000ec19  sub     rsp, 48h
0x18000ec1d  mov     rdi, r9
0x18000ec20  mov     rbp, r8
0x18000ec23  mov     r14, rdx
0x18000ec26  mov     r15, rcx
0x18000ec29  test    r9, r9
0x18000ec2c  jnz     short loc_18000EC35
0x18000ec2e  mov     eax, 80004003h
0x18000ec33  jmp     short loc_18000EC9B
0x18000ec35  mov     qword ptr [r9], 0
0x18000ec3c  xor     ebx, ebx
0x18000ec3e  cmp     ebx, 1
0x18000ec41  jge     short loc_18000EC96
0x18000ec43  lea     rcx, off_180042000
0x18000ec4a  movsxd  rsi, ebx
0x18000ec4d  shl     rsi, 4
0x18000ec51  mov     r8d, 10h; Size
0x18000ec57  add     rsi, rcx
0x18000ec5a  mov     rdx, r15; Buf2
0x18000ec5d  mov     rcx, [rsi]; Buf1
0x18000ec60  call    memcmp
0x18000ec65  test    eax, eax
0x18000ec67  jz      short loc_18000EC6D
0x18000ec69  inc     ebx
0x18000ec6b  jmp     short loc_18000EC3E
0x18000ec6d  mov     rdx, rsi
0x18000ec70  lea     rcx, [rsp+78h+var_58]
0x18000ec75  call    sub_18000E720
0x18000ec7a  mov     r9, rdi
0x18000ec7d  lea     rcx, [rsp+78h+var_58]
0x18000ec82  mov     r8, rbp
0x18000ec85  mov     rdx, r14
0x18000ec88  call    sub_18000E780
0x18000ec8d  lock dec cs:dword_180048EC4
0x18000ec94  jmp     short loc_18000EC9B
0x18000ec96  mov     eax, 80040111h
0x18000ec9b  add     rsp, 48h
0x18000ec9f  pop     r15
0x18000eca1  pop     r14
0x18000eca3  pop     rdi
0x18000eca4  pop     rsi
0x18000eca5  pop     rbp
0x18000eca6  pop     rbx
0x18000eca7  retn
```
