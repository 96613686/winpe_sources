# appv::shared::kernel::command_line_processor::get_argument_value_from_command_line(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING &)

- ea: `0x18001a380`
- end: `0x18001a4cb`
- name: `?get_argument_value_from_command_line@command_line_processor@kernel@shared@appv@@SA_NPEBU_UNICODE_STRING@@0AEAU5@@Z`
- size: `331`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001872c`
- `0x180018ab0`

## callees

- `0x18001a380`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x18001a444`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001a444`

## pseudocode

```c
bool __fastcall appv::shared::kernel::command_line_processor::get_argument_value_from_command_line(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  unsigned __int16 v4; // di
  int v5; // ebx
  wchar_t *Buffer; // r15
  wchar_t *v7; // r13
  unsigned __int16 v8; // bp
  int v9; // r12d
  unsigned __int16 v10; // bx
  unsigned __int16 v11; // r8
  wchar_t v12; // cx
  unsigned __int16 v13; // r8
  bool result; // al
  UNICODE_STRING String2; // [rsp+20h] [rbp-68h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-58h] BYREF

  a3->Buffer = 0;
  *(_DWORD *)&a3->Length = 0;
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  if ( !a2->Length )
    return 0;
  if ( !a1->Length )
    return 0;
  v4 = a1->Length >> 1;
  v5 = a2->Length >> 1;
  if ( v4 < (unsigned int)(v5 + 1) )
    return 0;
  Buffer = a1->Buffer;
  v7 = a2->Buffer;
  v8 = 0;
  v9 = v4 - v5 - 1;
  if ( v9 < 0 )
    return 0;
  while ( 1 )
  {
    *(&String1.MaximumLength + 2) = 0;
    String1.Length = 2 * v5;
    *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * v5);
    *(&String2.MaximumLength + 2) = 0;
    String1.Buffer = &Buffer[v8];
    String2.Buffer = v7;
    String2.Length = 2 * v5;
    *(_DWORD *)&String2.MaximumLength = *(_DWORD *)&String1.MaximumLength;
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) == 1 )
      break;
    if ( ++v8 > v9 )
      return 0;
  }
  v10 = v8 + v5;
  if ( !v10 )
    return 0;
  v11 = v10;
  if ( v10 >= v4 )
    return 0;
  do
  {
    v12 = Buffer[v11];
    if ( v12 == 32 )
      break;
    if ( v12 == 9 )
      break;
    ++v11;
  }
  while ( v11 < v4 );
  if ( v11 == v10 )
    return 0;
  v13 = 2 * (v11 - v10);
  result = 1;
  a3->Length = v13;
  a3->MaximumLength = v13;
  a3->Buffer = &Buffer[v10];
  return result;
}

```

## disassembly

```asm
0x18001a380  push    rbx
0x18001a382  push    rbp
0x18001a383  push    rsi
0x18001a384  push    rdi
0x18001a385  push    r12
0x18001a387  push    r13
0x18001a389  push    r14
0x18001a38b  push    r15
0x18001a38d  sub     rsp, 48h
0x18001a391  xor     r9d, r9d
0x18001a394  mov     rsi, r8
0x18001a397  mov     [r8+8], r9
0x18001a39b  mov     [r8], r9d
0x18001a39e  test    rcx, rcx
0x18001a3a1  jz      loc_18001A4B7
0x18001a3a7  test    rdx, rdx
0x18001a3aa  jz      loc_18001A4B7
0x18001a3b0  movzx   eax, word ptr [rdx]
0x18001a3b3  test    ax, ax
0x18001a3b6  jz      loc_18001A4B7
0x18001a3bc  movzx   edi, word ptr [rcx]
0x18001a3bf  test    di, di
0x18001a3c2  jz      loc_18001A4B7
0x18001a3c8  shr     ax, 1
0x18001a3cb  shr     di, 1
0x18001a3ce  movzx   ebx, ax
0x18001a3d1  movzx   r8d, di
0x18001a3d5  lea     eax, [rbx+1]
0x18001a3d8  cmp     r8d, eax
0x18001a3db  jb      loc_18001A4B7
0x18001a3e1  mov     r15, [rcx+8]
0x18001a3e5  sub     r8d, ebx
0x18001a3e8  mov     r13, [rdx+8]
0x18001a3ec  mov     ebp, r9d
0x18001a3ef  lea     r12d, [r8-1]
0x18001a3f3  test    r12d, r12d
0x18001a3f6  js      loc_18001A4B7
0x18001a3fc  movzx   r14d, bx
0x18001a400  add     r14w, r14w
0x18001a404  movzx   eax, bp
0x18001a407  lea     rdx, [rsp+88h+String2]; String2
0x18001a40c  mov     r8b, 1; CaseInSensitive
0x18001a40f  mov     dword ptr [rsp+88h+String1+4], r9d
0x18001a414  mov     [rsp+88h+String1.Length], r14w
0x18001a41a  mov     [rsp+88h+String1.MaximumLength], r14w
0x18001a420  lea     rcx, [r15+rax*2]
0x18001a424  mov     dword ptr [rsp+88h+String2+4], r9d
0x18001a429  mov     [rsp+88h+String1.Buffer], rcx
0x18001a42e  lea     rcx, [rsp+88h+String1]; String1
0x18001a433  mov     [rsp+88h+String2.Buffer], r13
0x18001a438  mov     [rsp+88h+String2.Length], r14w
0x18001a43e  mov     [rsp+88h+String2.MaximumLength], r14w
0x18001a444  call    cs:__imp_RtlEqualUnicodeString
0x18001a44b  nop     dword ptr [rax+rax+00h]
0x18001a450  cmp     al, 1
0x18001a452  jz      short loc_18001A464
0x18001a454  inc     bp
0x18001a457  movzx   eax, bp
0x18001a45a  cmp     eax, r12d
0x18001a45d  jg      short loc_18001A4B7
0x18001a45f  xor     r9d, r9d
0x18001a462  jmp     short loc_18001A404
0x18001a464  add     bx, bp
0x18001a467  jz      short loc_18001A4B7
0x18001a469  movzx   r8d, bx
0x18001a46d  cmp     bx, di
0x18001a470  jnb     short loc_18001A4B7
0x18001a472  movzx   eax, r8w
0x18001a476  movzx   ecx, word ptr [r15+rax*2]
0x18001a47b  cmp     cx, 20h ; ' '
0x18001a47f  jz      short loc_18001A491
0x18001a481  cmp     cx, 9
0x18001a485  jz      short loc_18001A491
0x18001a487  inc     r8w
0x18001a48b  cmp     r8w, di
0x18001a48f  jb      short loc_18001A472
0x18001a491  cmp     r8w, bx
0x18001a495  jz      short loc_18001A4B7
0x18001a497  movzx   ecx, bx
0x18001a49a  sub     r8w, bx
0x18001a49e  add     r8w, r8w
0x18001a4a2  mov     al, 1
0x18001a4a4  mov     [rsi], r8w
0x18001a4a8  mov     [rsi+2], r8w
0x18001a4ad  lea     rdx, [r15+rcx*2]
0x18001a4b1  mov     [rsi+8], rdx
0x18001a4b5  jmp     short loc_18001A4B9
0x18001a4b7  xor     al, al
0x18001a4b9  add     rsp, 48h
0x18001a4bd  pop     r15
0x18001a4bf  pop     r14
0x18001a4c1  pop     r13
0x18001a4c3  pop     r12
0x18001a4c5  pop     rdi
0x18001a4c6  pop     rsi
0x18001a4c7  pop     rbp
0x18001a4c8  pop     rbx
0x18001a4c9  retn
```
