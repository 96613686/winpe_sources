# FltpInsertVolumeInstance

- ea: `0x18006acb0`
- end: `0x18006ae63`
- name: `FltpInsertVolumeInstance`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180069c90`

## callees

- `0x18001f2b0`
- `0x180021e64`
- `0x18006acb0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x18006ad9c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18006ad9c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006acee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006acee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006ad31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006ad31`
- `ntoskrnl!ExReleaseFastResource` at `0x18006ad25`
- `ntoskrnl!ExReleaseFastResource` at `0x18006ad25`
- `ntoskrnl!RtlCompareAltitudes` at `0x18006adc3`
- `ntoskrnl!RtlCompareAltitudes` at `0x18006adc3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006ad09`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006ad09`

## pseudocode

```c
__int64 __fastcall FltpInsertVolumeInstance(__int64 a1, __int64 a2)
{
  __int64 v4; // rbp
  __int64 v5; // r8
  unsigned int v6; // ebx
  char v8; // r12
  __int64 *v9; // rsi
  __int64 *v10; // r13
  __int64 *i; // rbx
  LONG v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r9

  if ( (byte_180040A42 & 0x40) != 0 )
  {
    v15 = *(_QWORD *)(a2 + 72);
    McTemplateU0spwwpw_EtwWriteTransfer(
      a1,
      *(unsigned __int16 *)(v15 + 64) >> 1,
      *(unsigned __int16 *)(a1 + 112) >> 1,
      v15,
      *(_WORD *)(v15 + 64) >> 1,
      *(_QWORD *)(v15 + 72),
      *(_WORD *)(a2 + 88) >> 1,
      *(_QWORD *)(a2 + 96),
      a1,
      *(_WORD *)(a1 + 112) >> 1,
      *(_QWORD *)(a1 + 120));
  }
  KeEnterCriticalRegion();
  v4 = a1 + 192;
  LOBYTE(v5) = 1;
  ExAcquireFastResourceExclusive(a1 + 192, 0, v5);
  if ( (*(_DWORD *)a1 & 1) != 0 )
  {
    v6 = -1071906805;
  }
  else
  {
    v8 = 0;
    v9 = (__int64 *)(a1 + 296);
    v10 = v9;
    for ( i = (__int64 *)*v9; i != v9; i = (__int64 *)*i )
    {
      if ( (*(_DWORD *)(i - 2) & 2) == 0 )
      {
        if ( RtlEqualUnicodeString((PCUNICODE_STRING)(i + 11), (PCUNICODE_STRING)(a2 + 104), 1u) )
        {
          v6 = -1071906798;
          goto LABEL_5;
        }
        if ( !v8 )
        {
          v12 = RtlCompareAltitudes((PCUNICODE_STRING)(i + 9), (PCUNICODE_STRING)(a2 + 88));
          if ( v12 < 0 )
          {
            v10 = i;
            v8 = 1;
          }
          else if ( !v12 )
          {
            if ( (byte_180040A42 & 0x40) != 0 )
              McTemplateU0sppww_EtwWriteTransfer(
                *(unsigned __int16 *)(a2 + 88) >> 1,
                *(unsigned __int16 *)(i[7] + 64) >> 1,
                i[7],
                (_DWORD)i - 16,
                i[7],
                *(_WORD *)(i[7] + 64) >> 1,
                *(_QWORD *)(i[7] + 72),
                *(_WORD *)(a2 + 88) >> 1,
                *(_QWORD *)(a2 + 96));
            v6 = -1071906799;
            goto LABEL_5;
          }
        }
      }
    }
    v13 = (__int64 *)v10[1];
    v14 = *v13;
    if ( *(__int64 **)(*v13 + 8) != v13 )
      __fastfail(3u);
    v6 = 0;
    *(_QWORD *)(a2 + 16) = v14;
    *(_QWORD *)(a2 + 24) = v13;
    *(_QWORD *)(v14 + 8) = a2 + 16;
    *v13 = a2 + 16;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 120));
  }
LABEL_5:
  ExReleaseFastResource(v4, 0);
  KeLeaveCriticalRegion();
  return v6;
}

```

## disassembly

```asm
0x18006acb0  push    rbp
0x18006acb2  push    rsi
0x18006acb3  push    r14
0x18006acb5  sub     rsp, 70h
0x18006acb9  test    cs:byte_180040A42, 40h
0x18006acc0  mov     r14, rdx
0x18006acc3  mov     rsi, rcx
0x18006acc6  jnz     loc_18007A8BA
0x18006accc  mov     [rsp+88h+arg_0], rbx
0x18006acd4  mov     [rsp+88h+arg_8], rdi
0x18006acdc  mov     [rsp+88h+arg_10], r12
0x18006ace4  mov     [rsp+88h+var_20], r13
0x18006ace9  mov     [rsp+88h+var_28], r15
0x18006acee  call    cs:__imp_KeEnterCriticalRegion
0x18006acf5  nop     dword ptr [rax+rax+00h]
0x18006acfa  lea     rbp, [rsi+0C0h]
0x18006ad01  mov     r8b, 1
0x18006ad04  mov     rcx, rbp
0x18006ad07  xor     edx, edx
0x18006ad09  call    cs:__imp_ExAcquireFastResourceExclusive
0x18006ad10  nop     dword ptr [rax+rax+00h]
0x18006ad15  mov     eax, [rsi]
0x18006ad17  test    al, 1
0x18006ad19  jz      short loc_18006AD6B
0x18006ad1b  mov     ebx, 0C01C000Bh
0x18006ad20  xor     edx, edx
0x18006ad22  mov     rcx, rbp
0x18006ad25  call    cs:__imp_ExReleaseFastResource
0x18006ad2c  nop     dword ptr [rax+rax+00h]
0x18006ad31  call    cs:__imp_KeLeaveCriticalRegion
0x18006ad38  nop     dword ptr [rax+rax+00h]
0x18006ad3d  mov     r15, [rsp+88h+var_28]
0x18006ad42  mov     eax, ebx
0x18006ad44  mov     rbx, [rsp+88h+arg_0]
0x18006ad4c  mov     r13, [rsp+88h+var_20]
0x18006ad51  mov     r12, [rsp+88h+arg_10]
0x18006ad59  mov     rdi, [rsp+88h+arg_8]
0x18006ad61  add     rsp, 70h
0x18006ad65  pop     r14
0x18006ad67  pop     rsi
0x18006ad68  pop     rbp
0x18006ad69  retn
0x18006ad6b  xor     r12b, r12b
0x18006ad6e  add     rsi, 128h
0x18006ad75  mov     r13, rsi
0x18006ad78  mov     rbx, [rsi]
0x18006ad7b  nop     dword ptr [rax+rax+00h]
0x18006ad80  cmp     rbx, rsi
0x18006ad83  jz      short loc_18006ADE8
0x18006ad85  mov     eax, [rbx-10h]
0x18006ad88  test    al, 2
0x18006ad8a  jz      short loc_18006AD91
0x18006ad8c  mov     rbx, [rbx]
0x18006ad8f  jmp     short loc_18006AD80
0x18006ad91  lea     rdx, [r14+68h]; String2
0x18006ad95  mov     r8b, 1; CaseInSensitive
0x18006ad98  lea     rcx, [rbx+58h]; String1
0x18006ad9c  call    cs:__imp_RtlEqualUnicodeString
0x18006ada3  nop     dword ptr [rax+rax+00h]
0x18006ada8  test    al, al
0x18006adaa  jz      short loc_18006ADB6
0x18006adac  mov     ebx, 0C01C0012h
0x18006adb1  jmp     loc_18006AD20
0x18006adb6  test    r12b, r12b
0x18006adb9  jnz     short loc_18006AD8C
0x18006adbb  lea     rcx, [rbx+48h]; Altitude1
0x18006adbf  lea     rdx, [r14+58h]; Altitude2
0x18006adc3  call    cs:__imp_RtlCompareAltitudes
0x18006adca  nop     dword ptr [rax+rax+00h]
0x18006adcf  test    eax, eax
0x18006add1  js      short loc_18006AE19
0x18006add3  jnz     short loc_18006AD8C
0x18006add5  test    cs:byte_180040A42, 40h
0x18006addc  jnz     short loc_18006AE24
0x18006adde  mov     ebx, 0C01C0011h
0x18006ade3  jmp     loc_18006AD20
0x18006ade8  mov     rax, [r13+8]
0x18006adec  mov     rcx, [rax]
0x18006adef  cmp     [rcx+8], rax
0x18006adf3  jnz     short loc_18006AE12
0x18006adf5  lea     rdx, [r14+10h]
0x18006adf9  xor     ebx, ebx
0x18006adfb  mov     [rdx], rcx
0x18006adfe  mov     [rdx+8], rax
0x18006ae02  mov     [rcx+8], rdx
0x18006ae06  mov     [rax], rdx
0x18006ae09  lock inc dword ptr [rbp+78h]
0x18006ae0d  jmp     loc_18006AD20
0x18006ae12  mov     ecx, 3
0x18006ae17  int     29h; Win8: RtlFailFast(ecx)
0x18006ae19  mov     r13, rbx
0x18006ae1c  mov     r12b, 1
0x18006ae1f  jmp     loc_18006AD8C
0x18006ae24  mov     r8, [rbx+38h]
0x18006ae28  lea     r9, [rbx-10h]
0x18006ae2c  mov     rax, [r14+60h]
0x18006ae30  movzx   ecx, word ptr [r14+58h]
0x18006ae35  mov     [rsp+88h+var_48], rax
0x18006ae3a  movzx   edx, word ptr [r8+40h]
0x18006ae3f  mov     rax, [r8+48h]
0x18006ae43  shr     ecx, 1
0x18006ae45  mov     dword ptr [rsp+88h+var_50], ecx
0x18006ae49  mov     [rsp+88h+var_58], rax
0x18006ae4e  shr     edx, 1
0x18006ae50  mov     dword ptr [rsp+88h+var_60], edx
0x18006ae54  mov     [rsp+88h+var_68], r8
0x18006ae59  call    McTemplateU0sppww_EtwWriteTransfer
0x18006ae5e  jmp     loc_18006ADDE
0x18007a8ba  mov     r9, [rdx+48h]
0x18007a8be  movzx   r10d, word ptr [rdx+58h]
0x18007a8c3  mov     rax, [rcx+78h]
0x18007a8c7  movzx   r8d, word ptr [rcx+70h]
0x18007a8cc  movzx   edx, word ptr [r9+40h]
0x18007a8d1  mov     [rsp+88h+var_38], rax
0x18007a8d6  mov     rax, [r14+60h]
0x18007a8da  shr     r8d, 1
0x18007a8dd  mov     [rsp+88h+var_40], r8d
0x18007a8e2  mov     [rsp+88h+var_48], rsi
0x18007a8e7  mov     [rsp+88h+var_50], rax
0x18007a8ec  mov     rax, [r9+48h]
0x18007a8f0  shr     r10d, 1
0x18007a8f3  mov     dword ptr [rsp+88h+var_58], r10d
0x18007a8f8  shr     edx, 1
0x18007a8fa  mov     [rsp+88h+var_60], rax
0x18007a8ff  mov     dword ptr [rsp+88h+var_68], edx
0x18007a903  call    McTemplateU0spwwpw_EtwWriteTransfer
0x18007a908  nop
0x18007a909  jmp     loc_18006ACCC
```
