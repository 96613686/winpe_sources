# VidTriggerIoctlUpdateParameters

- ea: `0x14009949c`
- end: `0x14009962e`
- name: `VidTriggerIoctlUpdateParameters`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140035708`

## callees

- `0x140015004`
- `0x1400248f4`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x14009949c`
- `0x1400999b0`
- `0x1400f21a0`

## import_xrefs

- `winhvr!WinHvSetPortProperty` at `0x140099591`
- `winhvr!WinHvSetPortProperty` at `0x140099591`

## string_xrefs

- `0x1400994cc`: `VidTriggerIoctlUpdateParameters`
- `0x140099510`: `VidTriggerIoctlUpdateParameters`
- `0x14009953f`: `VidTriggerIoctlUpdateParameters`
- `0x1400995b0`: `VidTriggerIoctlUpdateParameters`
- `0x1400995d0`: `VidTriggerIoctlUpdateParameters`
- `0x140099613`: `VidTriggerIoctlUpdateParameters`

## pseudocode

```c
__int64 __fastcall VidTriggerIoctlUpdateParameters(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // eax

  v6 = VidTriggerpValidateParameters(a3);
  if ( v6 < 0 )
  {
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 356);
LABEL_17:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidTriggerIoctlUpdateParameters",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidtrigger.c",
      427,
      v6,
      a1 + 656);
    return (unsigned int)v6;
  }
  VidLockAcquireExclusive(a1 + 3368);
  v7 = VidHandleTableLookupEntry(a1 + 3336, a2);
  v8 = v7;
  if ( !v7 )
  {
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 365);
    v6 = -1073741275;
    goto LABEL_16;
  }
  v9 = *(_DWORD *)(v7 + 104);
  if ( v9 != *(_DWORD *)a3 )
  {
    v6 = -1073741811;
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 377);
    goto LABEL_16;
  }
  if ( v9 == 3 )
  {
    if ( *(_BYTE *)(v8 + 116) != *(_BYTE *)(a3 + 12)
      || *(_BYTE *)(v8 + 117) != *(_BYTE *)(a3 + 13)
      || ((*(_DWORD *)(v8 + 124) ^ *(_DWORD *)(a3 + 20)) & 0xFFFFFF) != 0
      || *(_WORD *)(v8 + 118) != *(_WORD *)(a3 + 14) )
    {
      v6 = -1073741637;
      VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 400);
      goto LABEL_16;
    }
    v6 = WinHvSetPortProperty(*(_QWORD *)v8, *(unsigned int *)(v8 + 124), 4, *(unsigned int *)(a3 + 8));
    if ( v6 < 0 )
    {
      VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 412);
      goto LABEL_16;
    }
  }
  VidTriggerpUpdateParameters(v8, a3);
  v6 = 0;
LABEL_16:
  VidLockRelease(a1 + 3368);
  if ( v6 < 0 )
    goto LABEL_17;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14009949c  push    rbx
0x14009949e  push    rsi
0x14009949f  push    rdi
0x1400994a0  push    r12
0x1400994a2  push    r15
0x1400994a4  sub     rsp, 30h
0x1400994a8  mov     r15, rcx
0x1400994ab  mov     rsi, r8
0x1400994ae  mov     rcx, r8
0x1400994b1  mov     rdi, rdx
0x1400994b4  call    VidTriggerpValidateParameters
0x1400994b9  mov     ebx, eax
0x1400994bb  test    eax, eax
0x1400994bd  jns     short loc_1400994DD
0x1400994bf  mov     r8d, 164h
0x1400994c5  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400994cc  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x1400994d3  call    VidTraceErrorInternal0
0x1400994d8  jmp     loc_1400995F7
0x1400994dd  lea     r12, [r15+0D28h]
0x1400994e4  mov     rcx, r12
0x1400994e7  call    VidLockAcquireExclusive
0x1400994ec  lea     rcx, [r15+0D08h]
0x1400994f3  mov     rdx, rdi
0x1400994f6  call    VidHandleTableLookupEntry
0x1400994fb  mov     rdi, rax
0x1400994fe  test    rax, rax
0x140099501  jnz     short loc_140099526
0x140099503  mov     r8d, 16Dh
0x140099509  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099510  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140099517  call    VidTraceErrorInternal0
0x14009951c  mov     ebx, 0C0000225h
0x140099521  jmp     loc_1400995EB
0x140099526  mov     eax, [rax+68h]
0x140099529  cmp     eax, [rsi]
0x14009952b  jz      short loc_140099550
0x14009952d  mov     ebx, 0C000000Dh
0x140099532  mov     r8d, 179h
0x140099538  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x14009953f  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140099546  call    VidTraceErrorInternal0
0x14009954b  jmp     loc_1400995EB
0x140099550  cmp     eax, 3
0x140099553  jnz     loc_1400995DE
0x140099559  mov     al, [rsi+0Ch]
0x14009955c  cmp     [rdi+74h], al
0x14009955f  jnz     short loc_1400995BE
0x140099561  mov     al, [rsi+0Dh]
0x140099564  cmp     [rdi+75h], al
0x140099567  jnz     short loc_1400995BE
0x140099569  mov     ecx, [rsi+14h]
0x14009956c  xor     ecx, [rdi+7Ch]
0x14009956f  test    ecx, 0FFFFFFh
0x140099575  jnz     short loc_1400995BE
0x140099577  movzx   eax, word ptr [rsi+0Eh]
0x14009957b  cmp     [rdi+76h], ax
0x14009957f  jnz     short loc_1400995BE
0x140099581  mov     r9d, [rsi+8]
0x140099585  mov     r8d, 4
0x14009958b  mov     edx, [rdi+7Ch]
0x14009958e  mov     rcx, [rdi]
0x140099591  call    cs:__imp_WinHvSetPortProperty
0x140099598  nop     dword ptr [rax+rax+00h]
0x14009959d  mov     ebx, eax
0x14009959f  test    eax, eax
0x1400995a1  jns     short loc_1400995DE
0x1400995a3  mov     r8d, 19Ch
0x1400995a9  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400995b0  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x1400995b7  call    VidTraceErrorInternal0
0x1400995bc  jmp     short loc_1400995EB
0x1400995be  mov     ebx, 0C00000BBh
0x1400995c3  mov     r8d, 190h
0x1400995c9  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400995d0  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x1400995d7  call    VidTraceErrorInternal0
0x1400995dc  jmp     short loc_1400995EB
0x1400995de  mov     rdx, rsi
0x1400995e1  mov     rcx, rdi
0x1400995e4  call    VidTriggerpUpdateParameters
0x1400995e9  xor     ebx, ebx
0x1400995eb  mov     rcx, r12
0x1400995ee  call    VidLockRelease
0x1400995f3  test    ebx, ebx
0x1400995f5  jns     short loc_14009961F
0x1400995f7  lea     rax, [r15+290h]
0x1400995fe  mov     r9d, ebx
0x140099601  mov     r8d, 1ABh
0x140099607  mov     [rsp+58h+var_38], rax
0x14009960c  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099613  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x14009961a  call    VidTraceErrorStatusPartitionInternal0
0x14009961f  mov     eax, ebx
0x140099621  add     rsp, 30h
0x140099625  pop     r15
0x140099627  pop     r12
0x140099629  pop     rdi
0x14009962a  pop     rsi
0x14009962b  pop     rbx
0x14009962c  retn
```
