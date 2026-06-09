# VfsUnMapName

- ea: `0x14000947c`
- end: `0x140009579`
- name: `VfsUnMapName`
- size: `253`
- prototype: `__int64 __fastcall(int, int, int, int, PUNICODE_STRING DestinationString)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140007da0`
- `0x140008e7c`
- `0x14000a7d0`

## callees

- `0x140008d50`
- `0x14000947c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000953d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009551`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000953d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009551`
- `ntoskrnl!ExAllocatePool2` at `0x1400094ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400094ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000951f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000951f`

## pseudocode

```c
__int64 __fastcall VfsUnMapName(__int64 a1, __int64 a2, __int64 a3, char a4, PUNICODE_STRING DestinationString)
{
  char v6; // bp
  __int64 result; // rax
  unsigned __int16 *v9; // rax
  unsigned int v10; // ecx
  unsigned __int16 v11; // si
  wchar_t *Pool2; // rax
  const UNICODE_STRING *v13; // rdx
  UNICODE_STRING Source; // [rsp+20h] [rbp-38h] BYREF

  v6 = a3;
  LOBYTE(a3) = 1;
  Source = 0;
  result = VfsGetRelativeNameByMapping(a1, a2, a3, &Source);
  if ( (int)result >= 0 )
  {
    if ( v6 )
      v9 = *(unsigned __int16 **)(a1 + 48);
    else
      v9 = *(unsigned __int16 **)(a1 + 40);
    v10 = Source.Length + *v9;
    if ( !a4 )
      v10 += *(unsigned __int16 *)(a1 + 8);
    if ( v10 > 0xFFFF )
    {
      return 3221225734LL;
    }
    else
    {
      v11 = v10;
      Pool2 = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v10, 1951614550);
      DestinationString->Buffer = Pool2;
      if ( Pool2 )
      {
        DestinationString->MaximumLength = v11;
        DestinationString->Length = 0;
        if ( !a4 )
          RtlCopyUnicodeString(DestinationString, (PCUNICODE_STRING)(a1 + 8));
        if ( v6 )
          v13 = *(const UNICODE_STRING **)(a1 + 48);
        else
          v13 = *(const UNICODE_STRING **)(a1 + 40);
        RtlAppendUnicodeStringToString(DestinationString, v13);
        RtlAppendUnicodeStringToString(DestinationString, &Source);
        return 0;
      }
      else
      {
        return 3221225626LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000947c  push    rbx
0x14000947e  push    rbp
0x14000947f  push    rsi
0x140009480  push    rdi
0x140009481  push    r14
0x140009483  sub     rsp, 30h
0x140009487  mov     r14b, r9b
0x14000948a  mov     bpl, r8b
0x14000948d  xorps   xmm0, xmm0
0x140009490  lea     r9, [rsp+58h+Source]
0x140009495  mov     r8b, 1
0x140009498  mov     rdi, rcx
0x14000949b  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1400094a0  call    VfsGetRelativeNameByMapping
0x1400094a5  test    eax, eax
0x1400094a7  js      loc_14000956D
0x1400094ad  test    bpl, bpl
0x1400094b0  jz      short loc_1400094B8
0x1400094b2  mov     rax, [rdi+30h]
0x1400094b6  jmp     short loc_1400094BC
0x1400094b8  mov     rax, [rdi+28h]
0x1400094bc  movzx   ecx, word ptr [rax]
0x1400094bf  movzx   eax, [rsp+58h+Source.Length]
0x1400094c4  add     ecx, eax
0x1400094c6  test    r14b, r14b
0x1400094c9  jnz     short loc_1400094D1
0x1400094cb  movzx   eax, word ptr [rdi+8]
0x1400094cf  add     ecx, eax
0x1400094d1  cmp     ecx, 0FFFFh
0x1400094d7  ja      loc_140009568
0x1400094dd  movzx   esi, cx
0x1400094e0  mov     r8d, 74534656h
0x1400094e6  mov     edx, esi
0x1400094e8  mov     ecx, 100h
0x1400094ed  call    cs:__imp_ExAllocatePool2
0x1400094f4  nop     dword ptr [rax+rax+00h]
0x1400094f9  mov     rbx, [rsp+58h+DestinationString]
0x140009501  mov     [rbx+8], rax
0x140009505  test    rax, rax
0x140009508  jz      short loc_140009561
0x14000950a  xor     eax, eax
0x14000950c  mov     [rbx+2], si
0x140009510  mov     [rbx], ax
0x140009513  test    r14b, r14b
0x140009516  jnz     short loc_14000952B
0x140009518  lea     rdx, [rdi+8]; SourceString
0x14000951c  mov     rcx, rbx; DestinationString
0x14000951f  call    cs:__imp_RtlCopyUnicodeString
0x140009526  nop     dword ptr [rax+rax+00h]
0x14000952b  mov     rcx, rbx; Destination
0x14000952e  test    bpl, bpl
0x140009531  jz      short loc_140009539
0x140009533  mov     rdx, [rdi+30h]
0x140009537  jmp     short loc_14000953D
0x140009539  mov     rdx, [rdi+28h]; Source
0x14000953d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140009544  nop     dword ptr [rax+rax+00h]
0x140009549  lea     rdx, [rsp+58h+Source]; Source
0x14000954e  mov     rcx, rbx; Destination
0x140009551  call    cs:__imp_RtlAppendUnicodeStringToString
0x140009558  nop     dword ptr [rax+rax+00h]
0x14000955d  xor     eax, eax
0x14000955f  jmp     short loc_14000956D
0x140009561  mov     eax, 0C000009Ah
0x140009566  jmp     short loc_14000956D
0x140009568  mov     eax, 0C0000106h
0x14000956d  add     rsp, 30h
0x140009571  pop     r14
0x140009573  pop     rdi
0x140009574  pop     rsi
0x140009575  pop     rbp
0x140009576  pop     rbx
0x140009577  retn
```
