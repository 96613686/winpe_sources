# UnicodeStringToCString(_UNICODE_STRING *,ushort * *,ulong *)

- ea: `0x18000caf0`
- end: `0x18000cbd5`
- name: `?UnicodeStringToCString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAK@Z`
- size: `229`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800183dc`

## callees

- `0x18000caf0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000cb82`
- `msvcrt!memcpy_s` at `0x18000cb82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cb58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cb58`

## pseudocode

```c
__int64 __fastcall UnicodeStringToCString(struct _UNICODE_STRING *a1, unsigned __int16 **a2, unsigned int *a3)
{
  int Length; // eax
  unsigned int v7; // ebp
  void *v8; // rsi
  unsigned int v9; // r15d
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  Length = a1->Length;
  if ( (unsigned __int16)Length > a1->MaximumLength )
    return 2147942487LL;
  v7 = Length + 2;
  if ( (((_BYTE)Length + 2) & 1) != 0 )
    return 2147942487LL;
  v8 = *a2;
  if ( !*a2 || (v9 = *a3, 2 * (unsigned __int64)*a3 < v7) )
  {
    v8 = CoTaskMemRealloc(v8, v7);
    if ( !v8 )
      return 2147942414LL;
    v9 = v7 >> 1;
  }
  if ( a1->Length )
    memcpy_s(v8, v7, a1->Buffer, a1->Length);
  result = 0;
  *((_WORD *)v8 + ((unsigned __int64)a1->Length >> 1)) = 0;
  *a2 = (unsigned __int16 *)v8;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18000caf0  push    rbx
0x18000caf2  push    rdi
0x18000caf3  push    r14
0x18000caf5  sub     rsp, 20h
0x18000caf9  mov     r14, r8
0x18000cafc  mov     rdi, rdx
0x18000caff  mov     rbx, rcx
0x18000cb02  test    rcx, rcx
0x18000cb05  jz      loc_18000CBC0
0x18000cb0b  movzx   eax, word ptr [rcx]
0x18000cb0e  cmp     ax, [rcx+2]
0x18000cb12  ja      loc_18000CBC0
0x18000cb18  mov     [rsp+38h+arg_0], rbp
0x18000cb1d  lea     ebp, [rax+2]
0x18000cb20  test    bpl, 1
0x18000cb24  jnz     loc_18000CBCE
0x18000cb2a  mov     [rsp+38h+arg_8], rsi
0x18000cb2f  mov     rsi, [rdx]
0x18000cb32  mov     [rsp+38h+arg_10], r12
0x18000cb37  mov     [rsp+38h+arg_18], r15
0x18000cb3c  mov     r12d, ebp
0x18000cb3f  test    rsi, rsi
0x18000cb42  jz      short loc_18000CB52
0x18000cb44  mov     r15d, [r8]
0x18000cb47  mov     eax, r15d
0x18000cb4a  add     rax, rax
0x18000cb4d  cmp     rax, r12
0x18000cb50  jnb     short loc_18000CB6B
0x18000cb52  mov     rdx, r12; cb
0x18000cb55  mov     rcx, rsi; pv
0x18000cb58  call    cs:__imp_CoTaskMemRealloc
0x18000cb5e  mov     rsi, rax
0x18000cb61  test    rax, rax
0x18000cb64  jz      short loc_18000CBB9
0x18000cb66  shr     ebp, 1
0x18000cb68  mov     r15d, ebp
0x18000cb6b  movzx   ecx, word ptr [rbx]
0x18000cb6e  xor     ebp, ebp
0x18000cb70  test    cx, cx
0x18000cb73  jz      short loc_18000CB88
0x18000cb75  mov     r8, [rbx+8]; Source
0x18000cb79  mov     r9d, ecx; SourceSize
0x18000cb7c  mov     rcx, rsi; Destination
0x18000cb7f  mov     rdx, r12; DestinationSize
0x18000cb82  call    cs:__imp_memcpy_s
0x18000cb88  movzx   edx, word ptr [rbx]
0x18000cb8b  mov     eax, ebp
0x18000cb8d  shr     rdx, 1
0x18000cb90  xor     ecx, ecx
0x18000cb92  mov     [rsi+rdx*2], cx
0x18000cb96  mov     [rdi], rsi
0x18000cb99  mov     [r14], r15d
0x18000cb9c  mov     r12, [rsp+38h+arg_10]
0x18000cba1  mov     rsi, [rsp+38h+arg_8]
0x18000cba6  mov     r15, [rsp+38h+arg_18]
0x18000cbab  mov     rbp, [rsp+38h+arg_0]
0x18000cbb0  add     rsp, 20h
0x18000cbb4  pop     r14
0x18000cbb6  pop     rdi
0x18000cbb7  pop     rbx
0x18000cbb8  retn
0x18000cbb9  mov     eax, 8007000Eh
0x18000cbbe  jmp     short loc_18000CB9C
0x18000cbc0  mov     eax, 80070057h
0x18000cbc5  add     rsp, 20h
0x18000cbc9  pop     r14
0x18000cbcb  pop     rdi
0x18000cbcc  pop     rbx
0x18000cbcd  retn
0x18000cbce  mov     eax, 80070057h
0x18000cbd3  jmp     short loc_18000CBAB
```
