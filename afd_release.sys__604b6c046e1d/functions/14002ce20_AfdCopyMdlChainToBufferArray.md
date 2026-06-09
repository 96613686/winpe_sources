# AfdCopyMdlChainToBufferArray

- ea: `0x14002ce20`
- end: `0x14002d03c`
- name: `AfdCopyMdlChainToBufferArray`
- size: `540`
- prototype: `__int64 __fastcall(char *Src, unsigned int, int, __int64 *, __int64, SIZE_T Length, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a020`
- `0x14003b9e0`

## callees

- `0x14002ce20`
- `0x1400445b8`
- `0x1400726d0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14002ce48`
- `ntoskrnl!ExGetPreviousMode` at `0x14002ce48`
- `ntoskrnl!ProbeForWrite` at `0x14002cf06`
- `ntoskrnl!ProbeForWrite` at `0x14002cf06`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14002cfc6`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14002d000`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14002cfc6`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14002d000`

## pseudocode

```c
__int64 __fastcall AfdCopyMdlChainToBufferArray(
        char *Src,
        unsigned int a2,
        int a3,
        __int64 *a4,
        __int64 a5,
        SIZE_T Length,
        char a7)
{
  KPROCESSOR_MODE PreviousMode; // al
  unsigned int v12; // edi
  unsigned int v13; // esi
  int v14; // r13d
  char *v16; // rcx
  unsigned int v17; // ebp
  unsigned __int8 v18; // dl
  unsigned int v19; // r15d
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h] BYREF
  char *v22; // [rsp+40h] [rbp-48h]
  KPROCESSOR_MODE i; // [rsp+98h] [rbp+10h]
  __int64 v24; // [rsp+A8h] [rbp+20h] BYREF

  LODWORD(v22) = 0;
  v21 = 0;
  PreviousMode = ExGetPreviousMode();
  v12 = a5;
  v13 = Length;
  v14 = Length;
  for ( i = PreviousMode; v12 >= *((_DWORD *)a4 + 10); a4 = (__int64 *)*a4 )
    v12 -= *((_DWORD *)a4 + 10);
  if ( !a2 )
    goto LABEL_7;
  while ( 1 )
  {
    if ( !a3 )
      return 0;
    --a3;
    if ( a7 )
      RtlCopyFromUser(&v21, Src, 0x10u);
    else
      RtlCopyVolatileMemory(&v21, Src, 0x10u);
    Src += 16;
    if ( a2 < (unsigned int)v21 )
      break;
    a2 -= v21;
  }
  v16 = &v22[a2];
  v17 = v21 - a2;
  v22 = v16;
  LODWORD(v21) = v21 - a2;
  while ( 1 )
  {
    v18 = i;
    if ( v13 < v17 )
      v17 = v13;
    if ( i )
    {
      ProbeForWrite(v16, v17, 1u);
      v16 = v22;
      v18 = i;
    }
    v13 -= v17;
    if ( v17 )
    {
      while ( 1 )
      {
        v19 = *((_DWORD *)a4 + 10) - v12;
        if ( v17 < v19 )
          break;
        v24 = 0;
        RtlCopyMdlToBufferToMode(a4, v12, v16, v18, v19, &v24, v20);
        v18 = i;
        v16 = &v22[v19];
        v12 = 0;
        v22 = v16;
        a4 = (__int64 *)*a4;
        v17 -= v19;
        if ( !v17 )
          goto LABEL_7;
      }
      v20 = 0;
      ((void (__fastcall *)(__int64 *, _QWORD, char *, _QWORD, _QWORD, __int64 *))RtlCopyMdlToBufferToMode)(
        a4,
        v12,
        v16,
        v18,
        v17,
        &v20);
      v12 += v17;
    }
LABEL_7:
    if ( !v13 || !a3 )
      return v14 - v13;
    --a3;
    if ( a7 )
      RtlCopyFromUser(&v21, Src, 0x10u);
    else
      RtlCopyVolatileMemory(&v21, Src, 0x10u);
    v16 = v22;
    Src += 16;
    v17 = v21;
  }
}

```

## disassembly

```asm
0x14002ce20  push    rbx
0x14002ce22  push    rsi
0x14002ce23  push    rdi
0x14002ce24  push    r12
0x14002ce26  push    r13
0x14002ce28  push    r14
0x14002ce2a  push    r15
0x14002ce2c  sub     rsp, 50h
0x14002ce30  xor     eax, eax
0x14002ce32  mov     rbx, r9
0x14002ce35  mov     [rsp+88h+var_50+4], rax
0x14002ce3a  mov     r14d, r8d
0x14002ce3d  mov     [rsp+88h+var_50], rax
0x14002ce42  mov     r15d, edx
0x14002ce45  mov     r12, rcx
0x14002ce48  call    cs:__imp_ExGetPreviousMode
0x14002ce4f  nop     dword ptr [rax+rax+00h]
0x14002ce54  mov     edi, dword ptr [rsp+88h+arg_20]
0x14002ce5b  mov     esi, dword ptr [rsp+88h+Length]
0x14002ce62  mov     r13d, esi
0x14002ce65  mov     [rsp+88h+arg_8], al
0x14002ce6c  cmp     edi, [rbx+28h]
0x14002ce6f  jb      short loc_14002CE7C
0x14002ce71  sub     edi, [rbx+28h]
0x14002ce74  mov     rbx, [rbx]
0x14002ce77  cmp     edi, [rbx+28h]
0x14002ce7a  jnb     short loc_14002CE71
0x14002ce7c  mov     [rsp+88h+arg_0], rbp
0x14002ce84  test    r15d, r15d
0x14002ce87  jz      short loc_14002CEB7
0x14002ce89  test    r14d, r14d
0x14002ce8c  jnz     loc_14002CF33
0x14002ce92  xor     eax, eax
0x14002ce94  mov     rbp, [rsp+88h+arg_0]
0x14002ce9c  add     rsp, 50h
0x14002cea0  pop     r15
0x14002cea2  pop     r14
0x14002cea4  pop     r13
0x14002cea6  pop     r12
0x14002cea8  pop     rdi
0x14002cea9  pop     rsi
0x14002ceaa  pop     rbx
0x14002ceab  retn
0x14002cead  sub     esi, ebp
0x14002ceaf  test    ebp, ebp
0x14002ceb1  jnz     loc_14002CF90
0x14002ceb7  test    esi, esi
0x14002ceb9  jz      short loc_14002CF21
0x14002cebb  test    r14d, r14d
0x14002cebe  jz      short loc_14002CF21
0x14002cec0  dec     r14d
0x14002cec3  lea     rcx, [rsp+88h+var_50]; void *
0x14002cec8  cmp     byte ptr [rsp+88h+arg_30], 0
0x14002ced0  mov     r8d, 10h; Size
0x14002ced6  mov     rdx, r12; Src
0x14002ced9  jz      short loc_14002CF2C
0x14002cedb  call    RtlCopyFromUser
0x14002cee0  mov     rcx, [rsp+88h+var_48]; Address
0x14002cee5  add     r12, 10h
0x14002cee9  mov     ebp, dword ptr [rsp+88h+var_50]
0x14002ceed  movzx   edx, [rsp+88h+arg_8]
0x14002cef5  cmp     esi, ebp
0x14002cef7  cmovb   ebp, esi
0x14002cefa  test    dl, dl
0x14002cefc  jz      short loc_14002CEAD
0x14002cefe  mov     edx, ebp; Length
0x14002cf00  mov     r8d, 1; Alignment
0x14002cf06  call    cs:__imp_ProbeForWrite
0x14002cf0d  nop     dword ptr [rax+rax+00h]
0x14002cf12  mov     rcx, [rsp+88h+var_48]
0x14002cf17  movzx   edx, [rsp+88h+arg_8]
0x14002cf1f  jmp     short loc_14002CEAD
0x14002cf21  sub     r13d, esi
0x14002cf24  mov     eax, r13d
0x14002cf27  jmp     loc_14002CE94
0x14002cf2c  call    RtlCopyVolatileMemory
0x14002cf31  jmp     short loc_14002CEE0
0x14002cf33  dec     r14d
0x14002cf36  lea     rcx, [rsp+88h+var_50]; void *
0x14002cf3b  cmp     byte ptr [rsp+88h+arg_30], 0
0x14002cf43  mov     r8d, 10h; Size
0x14002cf49  mov     rdx, r12; Src
0x14002cf4c  jz      short loc_14002CF80
0x14002cf4e  call    RtlCopyFromUser
0x14002cf53  mov     ebp, dword ptr [rsp+88h+var_50]
0x14002cf57  add     r12, 10h
0x14002cf5b  cmp     r15d, ebp
0x14002cf5e  jnb     loc_14002D034
0x14002cf64  mov     rcx, [rsp+88h+var_48]
0x14002cf69  mov     eax, r15d
0x14002cf6c  add     rcx, rax
0x14002cf6f  sub     ebp, r15d
0x14002cf72  mov     [rsp+88h+var_48], rcx
0x14002cf77  mov     dword ptr [rsp+88h+var_50], ebp
0x14002cf7b  jmp     loc_14002CEED
0x14002cf80  call    RtlCopyVolatileMemory
0x14002cf85  jmp     short loc_14002CF53
0x14002cf90  mov     r15d, [rbx+28h]
0x14002cf94  movzx   r9d, dl
0x14002cf98  sub     r15d, edi
0x14002cf9b  mov     r10d, edi
0x14002cf9e  mov     edx, r10d
0x14002cfa1  cmp     ebp, r15d
0x14002cfa4  jnb     short loc_14002CFD9
0x14002cfa6  lea     r8, [rsp+88h+var_58]
0x14002cfab  mov     eax, ebp
0x14002cfad  mov     [rsp+88h+var_60], r8
0x14002cfb2  mov     r8, rcx
0x14002cfb5  mov     rcx, rbx
0x14002cfb8  mov     [rsp+88h+var_58], 0
0x14002cfc1  mov     [rsp+88h+var_68], rax
0x14002cfc6  call    cs:__imp_RtlCopyMdlToBufferToMode
0x14002cfcd  nop     dword ptr [rax+rax+00h]
0x14002cfd2  add     edi, ebp
0x14002cfd4  jmp     loc_14002CEB7
0x14002cfd9  lea     rax, [rsp+88h+arg_18]
0x14002cfe1  mov     edi, r15d
0x14002cfe4  mov     r8, rcx
0x14002cfe7  mov     [rsp+88h+var_60], rax
0x14002cfec  mov     rcx, rbx
0x14002cfef  mov     [rsp+88h+var_68], rdi
0x14002cff4  mov     [rsp+88h+arg_18], 0
0x14002d000  call    cs:__imp_RtlCopyMdlToBufferToMode
0x14002d007  nop     dword ptr [rax+rax+00h]
0x14002d00c  mov     rcx, [rsp+88h+var_48]
0x14002d011  movzx   edx, [rsp+88h+arg_8]
0x14002d019  add     rcx, rdi
0x14002d01c  xor     edi, edi
0x14002d01e  mov     [rsp+88h+var_48], rcx
0x14002d023  mov     rbx, [rbx]
0x14002d026  sub     ebp, r15d
0x14002d029  jz      loc_14002CEB7
0x14002d02f  jmp     loc_14002CF90
0x14002d034  sub     r15d, ebp
0x14002d037  jmp     loc_14002CE89
```
