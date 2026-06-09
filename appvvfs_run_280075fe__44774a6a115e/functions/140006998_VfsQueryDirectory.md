# VfsQueryDirectory

- ea: `0x140006998`
- end: `0x140006a57`
- name: `VfsQueryDirectory`
- size: `191`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001530`

## callees

- `0x14000652c`
- `0x140006710`
- `0x140006998`
- `0x14000b11c`

## pseudocode

```c
__int64 VfsQueryDirectory(PFLT_CALLBACK_DATA Data, __int64 a2, _WORD *a3, ...)
{
  NTSTATUS v5; // eax
  __int64 v7; // [rsp+30h] [rbp-10h] BYREF
  signed __int64 v8; // [rsp+38h] [rbp-8h] BYREF
  int v9; // [rsp+58h] [rbp+18h] BYREF
  int v10; // [rsp+5Ch] [rbp+1Ch]
  __int64 v11; // [rsp+68h] [rbp+28h] BYREF
  va_list va; // [rsp+68h] [rbp+28h]
  va_list va1; // [rsp+70h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  v10 = HIDWORD(a2);
  v8 = 0;
  v7 = 0;
  v9 = 0;
  LOBYTE(v11) = 0;
  v5 = VfsPrepareMergeDirectory(Data, (__int64)a3, &v8, &v7, (ULONG *)&v9, (__int64 *)va);
  if ( v5 < 0 )
    goto LABEL_7;
  if ( (_BYTE)v11 )
  {
    if ( *a3 != 5767 )
      return 1;
    v5 = VfsRedirectIo(Data);
    if ( v5 >= 0 )
      return 1;
    goto LABEL_7;
  }
  v5 = VfsMergeDirectory((__int64)Data, v8, v7, v9);
  if ( v5 < 0 )
  {
LABEL_7:
    Data->IoStatus.Information = 0;
    Data->IoStatus.Status = v5;
  }
  return 4;
}

```

## disassembly

```asm
0x140006998  mov     r11, rsp
0x14000699b  mov     [r11+8], rbx
0x14000699f  mov     [r11+18h], rdi
0x1400069a3  mov     [r11+20h], r9
0x1400069a7  mov     [r11+10h], rdx
0x1400069ab  push    rbp
0x1400069ac  mov     rbp, rsp
0x1400069af  sub     rsp, 40h
0x1400069b3  mov     rdi, r8
0x1400069b6  mov     [rbp+var_8], 0
0x1400069be  lea     rax, [rbp+arg_18]
0x1400069c2  mov     [rbp+var_10], 0
0x1400069ca  mov     [r11-20h], rax
0x1400069ce  lea     r9, [rbp+var_10]
0x1400069d2  lea     rax, [rbp+arg_8]
0x1400069d6  mov     [rbp+arg_8], 0
0x1400069dd  lea     r8, [rbp+var_8]
0x1400069e1  mov     [r11-28h], rax
0x1400069e5  mov     rdx, rdi
0x1400069e8  mov     byte ptr [rbp+arg_18], 0
0x1400069ec  mov     rbx, rcx
0x1400069ef  call    VfsPrepareMergeDirectory
0x1400069f4  test    eax, eax
0x1400069f6  js      short loc_140006A36
0x1400069f8  cmp     byte ptr [rbp+arg_18], 0
0x1400069fc  jz      short loc_140006A1E
0x1400069fe  mov     eax, 1687h
0x140006a03  cmp     [rdi], ax
0x140006a06  jnz     short loc_140006A17
0x140006a08  mov     rdx, rdi
0x140006a0b  mov     rcx, rbx; Data
0x140006a0e  call    VfsRedirectIo
0x140006a13  test    eax, eax
0x140006a15  js      short loc_140006A36
0x140006a17  mov     eax, 1
0x140006a1c  jmp     short loc_140006A46
0x140006a1e  mov     r9d, [rbp+arg_8]
0x140006a22  mov     rcx, rbx
0x140006a25  mov     r8, [rbp+var_10]
0x140006a29  mov     rdx, [rbp+var_8]
0x140006a2d  call    VfsMergeDirectory
0x140006a32  test    eax, eax
0x140006a34  jns     short loc_140006A41
0x140006a36  mov     qword ptr [rbx+20h], 0
0x140006a3e  mov     [rbx+18h], eax
0x140006a41  mov     eax, 4
0x140006a46  mov     rbx, [rsp+40h+arg_0]
0x140006a4b  mov     rdi, [rsp+40h+arg_10]
0x140006a50  add     rsp, 40h
0x140006a54  pop     rbp
0x140006a55  retn
```
