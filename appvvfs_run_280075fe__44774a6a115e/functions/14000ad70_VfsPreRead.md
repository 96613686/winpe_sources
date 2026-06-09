# VfsPreRead

- ea: `0x14000ad70`
- end: `0x14000adda`
- name: `VfsPreRead`
- size: `106`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000ad70`
- `0x14000b11c`
- `0x14000f124`

## pseudocode

```c
__int64 __fastcall VfsPreRead(PFLT_CALLBACK_DATA Data, __int64 a2, PFILE_OBJECT *a3)
{
  unsigned int v5; // edi
  NTSTATUS v6; // eax

  v5 = 1;
  if ( (unsigned __int8)VfsDecodeFileObject(*(_QWORD *)(a2 + 32), 0, 0) )
  {
    v6 = VfsRedirectIo(Data);
    if ( v6 >= 0 )
    {
      v5 = 0;
      *a3 = Data->Iopb->TargetFileObject;
    }
    else
    {
      Data->IoStatus.Status = v6;
      v5 = 4;
      Data->IoStatus.Information = 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000ad70  push    rbx
0x14000ad72  push    rsi
0x14000ad73  push    rdi
0x14000ad74  push    r14
0x14000ad76  sub     rsp, 28h
0x14000ad7a  mov     rsi, rdx
0x14000ad7d  mov     r14, r8
0x14000ad80  mov     rbx, rcx
0x14000ad83  xor     r8d, r8d
0x14000ad86  xor     edx, edx
0x14000ad88  mov     edi, 1
0x14000ad8d  mov     rcx, [rsi+20h]
0x14000ad91  call    VfsDecodeFileObject
0x14000ad96  test    al, al
0x14000ad98  jz      short loc_14000ADCD
0x14000ad9a  mov     rdx, [rsi+20h]
0x14000ad9e  mov     rcx, rbx; Data
0x14000ada1  mov     rdx, [rdx+20h]
0x14000ada5  call    VfsRedirectIo
0x14000adaa  test    eax, eax
0x14000adac  jns     short loc_14000ADC0
0x14000adae  mov     [rbx+18h], eax
0x14000adb1  mov     edi, 4
0x14000adb6  mov     qword ptr [rbx+20h], 0
0x14000adbe  jmp     short loc_14000ADCD
0x14000adc0  mov     rax, [rbx+10h]
0x14000adc4  xor     edi, edi
0x14000adc6  mov     rcx, [rax+8]
0x14000adca  mov     [r14], rcx
0x14000adcd  mov     eax, edi
0x14000adcf  add     rsp, 28h
0x14000add3  pop     r14
0x14000add5  pop     rdi
0x14000add6  pop     rsi
0x14000add7  pop     rbx
0x14000add8  retn
```
