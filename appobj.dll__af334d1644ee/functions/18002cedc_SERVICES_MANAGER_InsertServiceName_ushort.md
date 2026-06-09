# SERVICES_MANAGER::InsertServiceName(ushort *)

- ea: `0x18002cedc`
- end: `0x18002cfb2`
- name: `?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z`
- size: `214`
- prototype: `int(SERVICES_MANAGER *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002d750`
- `0x18002e468`

## callees

- `0x180001044`
- `0x18002ccd4`
- `0x18002cd18`
- `0x18002cedc`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002cf75`
- `msvcrt!wcscpy_s` at `0x18002cf75`
- `msvcrt!_wcsicmp` at `0x18002cf25`
- `msvcrt!_wcsicmp` at `0x18002cf25`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::InsertServiceName(SERVICES_MANAGER *this, unsigned __int16 *a2)
{
  LIST_ARRAY *v2; // rbx
  unsigned int i; // esi
  int Item; // edi
  __int64 v6; // rax
  rsize_t v7; // rdi
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  wchar_t *String2; // [rsp+40h] [rbp+8h] BYREF

  v2 = (SERVICES_MANAGER *)((char *)this + 8);
  String2 = 0;
  for ( i = 0; i < *(_DWORD *)v2; ++i )
  {
    Item = LIST_ARRAY::GetItem(v2, i, (void **)&String2);
    if ( Item < 0 || !_wcsicmp(a2, String2) )
      return (unsigned int)Item;
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v8 = (wchar_t *)operator new(saturated_mul(v6 + 1, 2u));
  v9 = v8;
  if ( v8 )
  {
    wcscpy_s(v8, v7, a2);
    Item = LIST_ARRAY::CheckRange(v2, *(_DWORD *)v2, 1);
    if ( Item >= 0 )
      *(_QWORD *)(*((_QWORD *)v2 + 5) + 8LL * (unsigned int)(*(_DWORD *)v2)++) = v9;
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x18002cedc  mov     [rsp+arg_8], rbx
0x18002cee1  mov     [rsp+arg_10], rbp
0x18002cee6  push    rsi
0x18002cee7  push    rdi
0x18002cee8  push    r14
0x18002ceea  sub     rsp, 20h
0x18002ceee  xor     r14d, r14d
0x18002cef1  lea     rbx, [rcx+8]
0x18002cef5  mov     [rsp+38h+String2], r14
0x18002cefa  mov     esi, r14d
0x18002cefd  mov     rbp, rdx
0x18002cf00  cmp     esi, [rbx]
0x18002cf02  jnb     short loc_18002CF33
0x18002cf04  lea     r8, [rsp+38h+String2]; void **
0x18002cf09  mov     edx, esi; unsigned int
0x18002cf0b  mov     rcx, rbx; this
0x18002cf0e  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002cf13  mov     edi, eax
0x18002cf15  test    eax, eax
0x18002cf17  js      loc_18002CF9D
0x18002cf1d  mov     rdx, [rsp+38h+String2]; String2
0x18002cf22  mov     rcx, rbp; String1
0x18002cf25  call    cs:__imp__wcsicmp
0x18002cf2b  test    eax, eax
0x18002cf2d  jz      short loc_18002CF9D
0x18002cf2f  inc     esi
0x18002cf31  jmp     short loc_18002CF00
0x18002cf33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002cf37  mov     rax, rcx
0x18002cf3a  inc     rax
0x18002cf3d  cmp     [rbp+rax*2+0], r14w
0x18002cf43  jnz     short loc_18002CF3A
0x18002cf45  lea     rdi, [rax+1]
0x18002cf49  mov     eax, 2
0x18002cf4e  mul     rdi
0x18002cf51  cmovb   rax, rcx
0x18002cf55  mov     rcx, rax; Size
0x18002cf58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cf5d  mov     rsi, rax
0x18002cf60  test    rax, rax
0x18002cf63  jnz     short loc_18002CF6C
0x18002cf65  mov     edi, 80070008h
0x18002cf6a  jmp     short loc_18002CF9D
0x18002cf6c  mov     r8, rbp; Source
0x18002cf6f  mov     rdx, rdi; SizeInWords
0x18002cf72  mov     rcx, rsi; Destination
0x18002cf75  call    cs:__imp_wcscpy_s
0x18002cf7b  mov     edx, [rbx]; unsigned int
0x18002cf7d  mov     r8d, 1; int
0x18002cf83  mov     rcx, rbx; this
0x18002cf86  call    ?CheckRange@LIST_ARRAY@@AEAAJKH@Z; LIST_ARRAY::CheckRange(ulong,int)
0x18002cf8b  mov     edi, eax
0x18002cf8d  test    eax, eax
0x18002cf8f  js      short loc_18002CF9D
0x18002cf91  mov     ecx, [rbx]
0x18002cf93  mov     rax, [rbx+28h]
0x18002cf97  mov     [rax+rcx*8], rsi
0x18002cf9b  inc     dword ptr [rbx]
0x18002cf9d  mov     rbx, [rsp+38h+arg_8]
0x18002cfa2  mov     eax, edi
0x18002cfa4  mov     rbp, [rsp+38h+arg_10]
0x18002cfa9  add     rsp, 20h
0x18002cfad  pop     r14
0x18002cfaf  pop     rdi
0x18002cfb0  pop     rsi
0x18002cfb1  retn
```
