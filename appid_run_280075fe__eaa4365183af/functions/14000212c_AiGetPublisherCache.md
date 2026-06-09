# AiGetPublisherCache

- ea: `0x14000212c`
- end: `0x14000221d`
- name: `AiGetPublisherCache`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140026088`
- `0x140026140`

## callees

- `0x14000212c`
- `0x140006a20`
- `0x140036ee0`

## import_xrefs

- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x1400021b5`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x1400021b5`

## pseudocode

```c
__int64 __fastcall AiGetPublisherCache(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  int v7; // r8d
  unsigned int v8; // eax
  char v10; // [rsp+38h] [rbp-70h]
  unsigned int v11; // [rsp+50h] [rbp-58h] BYREF
  __int64 v12; // [rsp+58h] [rbp-50h]
  char v13[40]; // [rsp+60h] [rbp-48h] BYREF

  v11 = 0;
  v12 = 0;
  AiAddEaToQueryBuffer((void *)"$KERNEL.PURGE.APPID.SIGNERINFO");
  v10 = 0;
  v7 = FsRtlQueryKernelEaFile(a1, a3, 4096, 0, v13, 39, 0, v10, &v11);
  if ( v7 >= 0 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6) + *(unsigned __int8 *)(a3 + 5) + 9;
    if ( v8 < v11 || v8 < 0x30 || *(_DWORD *)(a3 + 40) != 860113217 || (*(_DWORD *)(a3 + 44) & 0xFFFFFFFE) != 0 )
      return (unsigned int)-1073739509;
    else
      *a4 = v11;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000212c  mov     r11, rsp
0x14000212f  push    rbx
0x140002130  push    rsi
0x140002131  push    rdi
0x140002132  sub     rsp, 90h
0x140002139  mov     rax, cs:__security_cookie
0x140002140  xor     rax, rsp
0x140002143  mov     [rsp+0A8h+var_20], rax
0x14000214b  mov     rsi, r9
0x14000214e  mov     [rsp+0A8h+var_58], 0
0x140002156  mov     rdi, r8
0x140002159  mov     qword ptr [r11-50h], 0
0x140002161  mov     rbx, rcx
0x140002164  lea     r9, [r11-50h]
0x140002168  lea     r8, [r11-48h]
0x14000216c  lea     rcx, aKernelPurgeApp_1; "$KERNEL.PURGE.APPID.SIGNERINFO"
0x140002173  lea     rdx, [r11-50h]
0x140002177  call    AiAddEaToQueryBuffer
0x14000217c  lea     rax, [rsp+0A8h+var_58]
0x140002181  xor     r9d, r9d
0x140002184  mov     [rsp+0A8h+var_68], rax
0x140002189  mov     r8d, 1000h
0x14000218f  mov     [rsp+0A8h+var_70], 0
0x140002194  lea     rax, [rsp+0A8h+var_48]
0x140002199  mov     [rsp+0A8h+var_78], 0
0x1400021a2  mov     rdx, rdi
0x1400021a5  mov     [rsp+0A8h+var_80], 27h ; '''
0x1400021ad  mov     rcx, rbx
0x1400021b0  mov     [rsp+0A8h+var_88], rax
0x1400021b5  call    cs:__imp_FsRtlQueryKernelEaFile
0x1400021bc  nop     dword ptr [rax+rax+00h]
0x1400021c1  mov     r8d, eax
0x1400021c4  test    eax, eax
0x1400021c6  js      short loc_1400021FE
0x1400021c8  movzx   eax, byte ptr [rdi+5]
0x1400021cc  movzx   edx, word ptr [rdi+6]
0x1400021d0  add     eax, 9
0x1400021d3  mov     ecx, [rsp+0A8h+var_58]
0x1400021d7  add     eax, edx
0x1400021d9  cmp     eax, ecx
0x1400021db  jb      short loc_1400021F8
0x1400021dd  cmp     eax, 30h ; '0'
0x1400021e0  jb      short loc_1400021F8
0x1400021e2  cmp     dword ptr [rdi+28h], 33444941h
0x1400021e9  jnz     short loc_1400021F8
0x1400021eb  test    dword ptr [rdi+2Ch], 0FFFFFFFEh
0x1400021f2  jnz     short loc_1400021F8
0x1400021f4  mov     [rsi], ecx
0x1400021f6  jmp     short loc_1400021FE
0x1400021f8  mov     r8d, 0C000090Bh
0x1400021fe  mov     eax, r8d
0x140002201  mov     rcx, [rsp+0A8h+var_20]
0x140002209  xor     rcx, rsp; StackCookie
0x14000220c  call    __security_check_cookie
0x140002211  add     rsp, 90h
0x140002218  pop     rdi
0x140002219  pop     rsi
0x14000221a  pop     rbx
0x14000221b  retn
```
