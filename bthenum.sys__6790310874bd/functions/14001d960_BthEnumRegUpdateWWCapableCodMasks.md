# BthEnumRegUpdateWWCapableCodMasks

- ea: `0x14001d960`
- end: `0x14001dafc`
- name: `BthEnumRegUpdateWWCapableCodMasks`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x140007d00`
- `0x140007e40`
- `0x140008140`
- `0x14001d960`
- `0x14001f5ec`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001da3b`
- `ntoskrnl!ExAllocatePool2` at `0x14001da3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d9c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d9c8`

## pseudocode

```c
__int64 __fastcall BthEnumRegUpdateWWCapableCodMasks(__int64 a1, void *a2)
{
  unsigned int v4; // ebx
  void *Pool2; // rax
  __int64 result; // rax
  __int64 i; // r8
  int v8; // ecx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD Src[80]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)(a1 + 128) = 0;
  LODWORD(v9) = 0;
  DestinationString = 0;
  memset(Src, 0, sizeof(Src));
  RtlInitUnicodeString(&DestinationString, L"WaitWake Capable COD Masks");
  if ( (int)BthQueryKeyValueEx(a2, &DestinationString, Src, (__int64)&v9) < 0 || (v4 = (unsigned int)v9 >> 3) == 0 )
  {
    v4 = 2;
    Src[0] = -65077248;
    Src[1] = 1074069504;
    Src[2] = -65077248;
    Src[3] = -2147155968;
  }
  Pool2 = (void *)ExAllocatePool2(64, 8LL * v4, 1330467906);
  *(_QWORD *)(a1 + 120) = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
  {
    v8 = HIBYTE(Src[2 * i]) | ((BYTE2(Src[2 * i]) | ((BYTE1(Src[2 * i]) | (LOBYTE(Src[2 * i]) << 8)) << 8)) << 8);
    Src[2 * i + 1] = HIBYTE(Src[2 * i + 1])
                   | ((BYTE2(Src[2 * i + 1]) | ((BYTE1(Src[2 * i + 1]) | (LOBYTE(Src[2 * i + 1]) << 8)) << 8)) << 8);
    Src[2 * i] = v8;
  }
  memmove(Pool2, Src, 8LL * v4);
  result = 0;
  *(_DWORD *)(a1 + 128) = v4;
  return result;
}

```

## disassembly

```asm
0x14001d960  mov     [rsp-8+arg_10], rbx
0x14001d965  push    rbp
0x14001d966  push    rsi
0x14001d967  push    rdi
0x14001d968  lea     rbp, [rsp-0A0h]
0x14001d970  sub     rsp, 1A0h
0x14001d977  mov     rax, cs:__security_cookie
0x14001d97e  xor     rax, rsp
0x14001d981  mov     [rbp+0B0h+var_20], rax
0x14001d988  mov     rbx, rdx
0x14001d98b  mov     dword ptr [rcx+80h], 0
0x14001d995  mov     rsi, rcx
0x14001d998  mov     dword ptr [rsp+1B0h+var_180], 0
0x14001d9a0  xorps   xmm0, xmm0
0x14001d9a3  lea     rcx, [rsp+1B0h+Src]; void *
0x14001d9a8  mov     edi, 140h
0x14001d9ad  xor     edx, edx; Val
0x14001d9af  mov     r8d, edi; Size
0x14001d9b2  movups  xmmword ptr [rsp+1B0h+DestinationString.Length], xmm0
0x14001d9b7  call    memset
0x14001d9bc  lea     rdx, aWaitwakeCapabl; "WaitWake Capable COD Masks"
0x14001d9c3  lea     rcx, [rsp+1B0h+DestinationString]; DestinationString
0x14001d9c8  call    cs:__imp_RtlInitUnicodeString
0x14001d9cf  nop     dword ptr [rax+rax+00h]
0x14001d9d4  lea     rax, [rsp+1B0h+var_180]
0x14001d9d9  mov     r9d, edi
0x14001d9dc  lea     r8, [rsp+1B0h+Src]; void *
0x14001d9e1  mov     [rsp+1B0h+var_190], rax; __int64
0x14001d9e6  lea     rdx, [rsp+1B0h+DestinationString]; ValueName
0x14001d9eb  mov     rcx, rbx; KeyHandle
0x14001d9ee  call    BthQueryKeyValueEx
0x14001d9f3  test    eax, eax
0x14001d9f5  js      short loc_14001DA02
0x14001d9f7  mov     ebx, dword ptr [rsp+1B0h+var_180]
0x14001d9fb  shr     ebx, 3
0x14001d9fe  test    ebx, ebx
0x14001da00  jnz     short loc_14001DA27
0x14001da02  mov     ebx, 2
0x14001da07  mov     [rsp+1B0h+Src], 0FC1F0000h
0x14001da0f  mov     [rsp+1B0h+var_15C], 40050000h
0x14001da17  mov     [rsp+1B0h+var_158], 0FC1F0000h
0x14001da1f  mov     [rsp+1B0h+var_154], 80050000h
0x14001da27  mov     edi, ebx
0x14001da29  mov     r8d, 4F4D5442h
0x14001da2f  shl     rdi, 3
0x14001da33  mov     ecx, 40h ; '@'
0x14001da38  mov     rdx, rdi
0x14001da3b  call    cs:__imp_ExAllocatePool2
0x14001da42  nop     dword ptr [rax+rax+00h]
0x14001da47  mov     [rsi+78h], rax
0x14001da4b  mov     r10, rax
0x14001da4e  test    rax, rax
0x14001da51  jnz     short loc_14001DA5A
0x14001da53  mov     eax, 0C000009Ah
0x14001da58  jmp     short loc_14001DAD9
0x14001da5a  xor     r8d, r8d
0x14001da5d  test    ebx, ebx
0x14001da5f  jz      short loc_14001DAC1
0x14001da61  movzx   eax, byte ptr [rsp+r8*8+1B0h+var_15C+1]
0x14001da67  movzx   edx, byte ptr [rsp+r8*8+1B0h+var_15C]
0x14001da6d  movzx   ecx, byte ptr [rsp+r8*8+1B0h+Src]
0x14001da73  shl     edx, 8
0x14001da76  or      edx, eax
0x14001da78  shl     ecx, 8
0x14001da7b  movzx   eax, byte ptr [rsp+r8*8+1B0h+var_15C+2]
0x14001da81  shl     edx, 8
0x14001da84  or      edx, eax
0x14001da86  movzx   eax, byte ptr [rsp+r8*8+1B0h+var_15C+3]
0x14001da8c  shl     edx, 8
0x14001da8f  or      edx, eax
0x14001da91  movzx   eax, byte ptr [rsp+r8*8+1B0h+Src+1]
0x14001da97  or      ecx, eax
0x14001da99  movzx   eax, byte ptr [rsp+r8*8+1B0h+Src+2]
0x14001da9f  shl     ecx, 8
0x14001daa2  or      ecx, eax
0x14001daa4  movzx   eax, byte ptr [rsp+r8*8+1B0h+Src+3]
0x14001daaa  shl     ecx, 8
0x14001daad  or      ecx, eax
0x14001daaf  mov     [rsp+r8*8+1B0h+var_15C], edx
0x14001dab4  mov     [rsp+r8*8+1B0h+Src], ecx
0x14001dab9  inc     r8d
0x14001dabc  cmp     r8d, ebx
0x14001dabf  jb      short loc_14001DA61
0x14001dac1  mov     r8, rdi; Size
0x14001dac4  lea     rdx, [rsp+1B0h+Src]; Src
0x14001dac9  mov     rcx, r10; void *
0x14001dacc  call    memmove
0x14001dad1  xor     eax, eax
0x14001dad3  mov     [rsi+80h], ebx
0x14001dad9  mov     rcx, [rbp+0B0h+var_20]
0x14001dae0  xor     rcx, rsp; StackCookie
0x14001dae3  call    __security_check_cookie
0x14001dae8  mov     rbx, [rsp+1B0h+arg_10]
0x14001daf0  add     rsp, 1A0h
0x14001daf7  pop     rdi
0x14001daf8  pop     rsi
0x14001daf9  pop     rbp
0x14001dafa  retn
```
