# AiQueryTokenAttributes

- ea: `0x140032980`
- end: `0x140032a47`
- name: `AiQueryTokenAttributes`
- size: `199`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140030620`
- `0x140031d90`
- `0x140032420`

## callees

- `0x140032980`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400329ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032a23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400329ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032a23`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400329ee`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400329ee`

## pseudocode

```c
__int64 __fastcall AiQueryTokenAttributes(__int64 a1, _QWORD *a2)
{
  void *v2; // rbx
  unsigned int v3; // eax
  __int64 result; // rax
  unsigned int v7; // edi
  unsigned int i; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  for ( i = 0; ; v3 = i )
  {
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      v3 = i;
      v2 = 0;
    }
    if ( v3 )
    {
      v2 = (void *)AiAlloc(v3);
      if ( !v2 )
        return 3221225495LL;
      v3 = i;
    }
    result = ZwQuerySecurityAttributesToken(a1, 0, 0, v2, v3, &i);
    v7 = result;
    if ( (_DWORD)result != -1073741789 )
      break;
  }
  if ( (int)result < 0 )
  {
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      return v7;
    }
  }
  else
  {
    *a2 = v2;
  }
  return result;
}

```

## disassembly

```asm
0x140032980  mov     [rsp+arg_8], rbx
0x140032985  mov     [rsp+arg_18], rbp
0x14003298a  push    rsi
0x14003298b  sub     rsp, 30h
0x14003298f  xor     ebx, ebx
0x140032991  mov     [rsp+38h+arg_0], rdi
0x140032996  xor     eax, eax
0x140032998  mov     rsi, rdx
0x14003299b  mov     [rsp+38h+arg_10], eax
0x14003299f  mov     rbp, rcx
0x1400329a2  test    rbx, rbx
0x1400329a5  jz      short loc_1400329BE
0x1400329a7  xor     edx, edx; Tag
0x1400329a9  mov     rcx, rbx; P
0x1400329ac  call    cs:__imp_ExFreePoolWithTag
0x1400329b3  nop     dword ptr [rax+rax+00h]
0x1400329b8  mov     eax, [rsp+38h+arg_10]
0x1400329bc  xor     ebx, ebx
0x1400329be  test    eax, eax
0x1400329c0  jz      short loc_1400329D5
0x1400329c2  mov     ecx, eax
0x1400329c4  call    AiAlloc
0x1400329c9  mov     rbx, rax
0x1400329cc  test    rax, rax
0x1400329cf  jz      short loc_140032A09
0x1400329d1  mov     eax, [rsp+38h+arg_10]
0x1400329d5  lea     rcx, [rsp+38h+arg_10]
0x1400329da  mov     r9, rbx
0x1400329dd  mov     [rsp+38h+var_10], rcx
0x1400329e2  xor     r8d, r8d
0x1400329e5  mov     rcx, rbp
0x1400329e8  mov     [rsp+38h+var_18], eax
0x1400329ec  xor     edx, edx
0x1400329ee  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1400329f5  nop     dword ptr [rax+rax+00h]
0x1400329fa  mov     edi, eax
0x1400329fc  cmp     eax, 0C0000023h
0x140032a01  jnz     short loc_140032A10
0x140032a03  mov     eax, [rsp+38h+arg_10]
0x140032a07  jmp     short loc_1400329A2
0x140032a09  mov     eax, 0C0000017h
0x140032a0e  jmp     short loc_140032A31
0x140032a10  test    edi, edi
0x140032a12  js      short loc_140032A19
0x140032a14  mov     [rsi], rbx
0x140032a17  jmp     short loc_140032A31
0x140032a19  test    rbx, rbx
0x140032a1c  jz      short loc_140032A31
0x140032a1e  xor     edx, edx; Tag
0x140032a20  mov     rcx, rbx; P
0x140032a23  call    cs:__imp_ExFreePoolWithTag
0x140032a2a  nop     dword ptr [rax+rax+00h]
0x140032a2f  mov     eax, edi
0x140032a31  mov     rdi, [rsp+38h+arg_0]
0x140032a36  mov     rbx, [rsp+38h+arg_8]
0x140032a3b  mov     rbp, [rsp+38h+arg_18]
0x140032a40  add     rsp, 30h
0x140032a44  pop     rsi
0x140032a45  retn
```
