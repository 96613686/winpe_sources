# FileProvCompressWorkItem

- ea: `0x14003acc0`
- end: `0x14003ae25`
- name: `FileProvCompressWorkItem`
- size: `357`
- prototype: `LONG __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003a6f8`

## callees

- `0x140006620`
- `0x14000c888`
- `0x14000c8a0`
- `0x1400116c0`
- `0x14003acc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14003ad46`
- `ntoskrnl!KeSetEvent` at `0x14003ad46`
- `ntoskrnl!RtlCompressBuffer` at `0x14003ad28`
- `ntoskrnl!RtlCompressBuffer` at `0x14003ad28`

## pseudocode

```c
LONG __fastcall FileProvCompressWorkItem(__int64 a1)
{
  int v1; // eax
  _DWORD *v3; // rdi
  NTSTATUS v4; // eax
  void *v6; // rcx
  int v7; // edi
  unsigned int v8; // ecx

  v1 = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 128) = 0;
  if ( (v1 & 0xFFFFFFFC) != 0 || v1 == 1 )
  {
    v6 = *(void **)(a1 + 72);
    if ( v1 == 1 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 17336LL) = v6;
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 17344LL) = 0;
      v7 = LZX_Encode(*(_QWORD *)(a1 + 120), *(_QWORD *)(a1 + 64), *(unsigned int *)(a1 + 88), a1 + 92);
      LZX_EncodeFlush(*(_QWORD *)(a1 + 120));
      LZX_EncodeNewGroup(*(_QWORD *)(a1 + 120));
      if ( v7 || (v8 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 17344LL), v8 >= *(_DWORD *)(a1 + 88)) )
      {
        memmove(*(void **)(a1 + 72), *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
        v8 = *(_DWORD *)(a1 + 88);
      }
      *(_DWORD *)(a1 + 92) = v8;
    }
    else
    {
      memmove(v6, *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
      *(_DWORD *)(a1 + 92) = *(_DWORD *)(a1 + 88);
    }
  }
  else
  {
    v3 = (_DWORD *)(a1 + 92);
    v4 = RtlCompressBuffer(
           FileProvXPressAlgorithm,
           *(PUCHAR *)(a1 + 64),
           *(_DWORD *)(a1 + 88),
           *(PUCHAR *)(a1 + 72),
           *(_DWORD *)(a1 + 88) - 1,
           **(_DWORD **)(a1 + 40),
           (PULONG)(a1 + 92),
           *(PVOID *)(a1 + 80));
    if ( v4 == 279 )
    {
      *v3 = 0;
    }
    else if ( v4 == -1073741789 )
    {
      memmove(*(void **)(a1 + 72), *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
      *v3 = *(_DWORD *)(a1 + 88);
    }
    else if ( v4 < 0 )
    {
      *(_DWORD *)(a1 + 128) = v4;
    }
  }
  return KeSetEvent((PRKEVENT)(a1 + 96), 0, 0);
}

```

## disassembly

```asm
0x14003acc0  mov     [rsp+arg_8], rbx
0x14003acc5  mov     [rsp+arg_10], rbp
0x14003acca  push    rdi
0x14003accb  sub     rsp, 40h
0x14003accf  mov     eax, [rcx+20h]
0x14003acd2  xor     ebp, ebp
0x14003acd4  mov     [rcx+80h], ebp
0x14003acda  mov     rbx, rcx
0x14003acdd  test    eax, 0FFFFFFFCh
0x14003ace2  jnz     loc_14003AD8E
0x14003ace8  cmp     eax, 1
0x14003aceb  jz      loc_14003AD8E
0x14003acf1  mov     rax, [rcx+28h]
0x14003acf5  lea     rdi, [rcx+5Ch]
0x14003acf9  mov     r8d, [rcx+58h]; UncompressedBufferSize
0x14003acfd  mov     r10, [rcx+50h]
0x14003ad01  mov     r9, [rbx+48h]; CompressedBuffer
0x14003ad05  mov     ecx, [rax]
0x14003ad07  mov     rdx, [rbx+40h]; UncompressedBuffer
0x14003ad0b  lea     eax, [r8-1]
0x14003ad0f  mov     [rsp+48h+WorkSpace], r10; WorkSpace
0x14003ad14  mov     [rsp+48h+FinalCompressedSize], rdi; FinalCompressedSize
0x14003ad19  mov     [rsp+48h+UncompressedChunkSize], ecx; UncompressedChunkSize
0x14003ad1d  movzx   ecx, cs:FileProvXPressAlgorithm; CompressionFormatAndEngine
0x14003ad24  mov     [rsp+48h+CompressedBufferSize], eax; CompressedBufferSize
0x14003ad28  call    cs:__imp_RtlCompressBuffer
0x14003ad2f  nop     dword ptr [rax+rax+00h]
0x14003ad34  cmp     eax, 117h
0x14003ad39  jnz     short loc_14003AD63
0x14003ad3b  mov     [rdi], ebp
0x14003ad3d  lea     rcx, [rbx+60h]; Event
0x14003ad41  xor     r8d, r8d; Wait
0x14003ad44  xor     edx, edx; Increment
0x14003ad46  call    cs:__imp_KeSetEvent
0x14003ad4d  nop     dword ptr [rax+rax+00h]
0x14003ad52  mov     rbx, [rsp+48h+arg_8]
0x14003ad57  mov     rbp, [rsp+48h+arg_10]
0x14003ad5c  add     rsp, 40h
0x14003ad60  pop     rdi
0x14003ad61  retn
0x14003ad63  cmp     eax, 0C0000023h
0x14003ad68  jz      short loc_14003AD76
0x14003ad6a  test    eax, eax
0x14003ad6c  jns     short loc_14003AD3D
0x14003ad6e  mov     [rbx+80h], eax
0x14003ad74  jmp     short loc_14003AD3D
0x14003ad76  mov     r8d, [rbx+58h]; Size
0x14003ad7a  mov     rdx, [rbx+40h]; Src
0x14003ad7e  mov     rcx, [rbx+48h]; void *
0x14003ad82  call    memmove
0x14003ad87  mov     eax, [rbx+58h]
0x14003ad8a  mov     [rdi], eax
0x14003ad8c  jmp     short loc_14003AD3D
0x14003ad8e  mov     rcx, [rcx+48h]; void *
0x14003ad92  mov     [rsp+48h+arg_0], rsi
0x14003ad97  cmp     eax, 1
0x14003ad9a  jnz     short loc_14003ADFF
0x14003ad9c  mov     rax, [rbx+78h]
0x14003ada0  lea     r9, [rbx+5Ch]
0x14003ada4  mov     [rax+43B8h], rcx
0x14003adab  mov     rax, [rbx+78h]
0x14003adaf  mov     [rax+43C0h], ebp
0x14003adb5  mov     r8d, [rbx+58h]
0x14003adb9  mov     rdx, [rbx+40h]
0x14003adbd  mov     rcx, [rbx+78h]
0x14003adc1  call    LZX_Encode
0x14003adc6  mov     rcx, [rbx+78h]
0x14003adca  mov     edi, eax
0x14003adcc  call    LZX_EncodeFlush
0x14003add1  mov     rcx, [rbx+78h]
0x14003add5  call    LZX_EncodeNewGroup
0x14003adda  test    edi, edi
0x14003addc  jz      short loc_14003AE14
0x14003adde  mov     r8d, [rbx+58h]; Size
0x14003ade2  mov     rdx, [rbx+40h]; Src
0x14003ade6  mov     rcx, [rbx+48h]; void *
0x14003adea  call    memmove
0x14003adef  mov     ecx, [rbx+58h]
0x14003adf2  mov     [rbx+5Ch], ecx
0x14003adf5  mov     rsi, [rsp+48h+arg_0]
0x14003adfa  jmp     loc_14003AD3D
0x14003adff  mov     r8d, [rbx+58h]; Size
0x14003ae03  mov     rdx, [rbx+40h]; Src
0x14003ae07  call    memmove
0x14003ae0c  mov     eax, [rbx+58h]
0x14003ae0f  mov     [rbx+5Ch], eax
0x14003ae12  jmp     short loc_14003ADF5
0x14003ae14  mov     rax, [rbx+78h]
0x14003ae18  mov     ecx, [rax+43C0h]
0x14003ae1e  cmp     ecx, [rbx+58h]
0x14003ae21  jb      short loc_14003ADF2
0x14003ae23  jmp     short loc_14003ADDE
```
