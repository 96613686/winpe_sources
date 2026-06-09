# _attribute_t::Clear(void)

- ea: `0x180003170`
- end: `0x1800031da`
- name: `?Clear@_attribute_t@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(_attribute_t *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800031e0`

## callees

- `0x180003170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000318b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000318b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031b0`

## pseudocode

```c
void __fastcall _attribute_t::Clear(_attribute_t *this)
{
  int v1; // eax
  __int64 v3; // rcx
  char *v4; // rax

  v1 = *((_DWORD *)this + 2);
  if ( v1 == 10 )
  {
    CoTaskMemFree(*((LPVOID *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  else if ( v1 == 14 )
  {
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) = 0;
  }
  CoTaskMemFree(*(LPVOID *)this);
  v3 = 128;
  *(_QWORD *)this = 0;
  v4 = (char *)this + 16;
  do
  {
    *v4++ = 0;
    --v3;
  }
  while ( v3 );
}

```

## disassembly

```asm
0x180003170  mov     [rsp+arg_0], rbx
0x180003175  push    rdi
0x180003176  sub     rsp, 20h
0x18000317a  mov     eax, [rcx+8]
0x18000317d  xor     edi, edi
0x18000317f  mov     rbx, rcx
0x180003182  cmp     eax, 0Ah
0x180003185  jnz     short loc_180003197
0x180003187  mov     rcx, [rcx+10h]; pv
0x18000318b  call    cs:__imp_CoTaskMemFree
0x180003191  mov     [rbx+10h], rdi
0x180003195  jmp     short loc_1800031AD
0x180003197  cmp     eax, 0Eh
0x18000319a  jnz     short loc_1800031AD
0x18000319c  mov     rcx, [rcx+18h]; pv
0x1800031a0  call    cs:__imp_CoTaskMemFree
0x1800031a6  mov     [rbx+18h], rdi
0x1800031aa  mov     [rbx+10h], edi
0x1800031ad  mov     rcx, [rbx]; pv
0x1800031b0  call    cs:__imp_CoTaskMemFree
0x1800031b6  mov     ecx, 80h
0x1800031bb  mov     [rbx], rdi
0x1800031be  lea     rax, [rbx+10h]
0x1800031c2  mov     [rax], dil
0x1800031c5  lea     rax, [rax+1]
0x1800031c9  sub     rcx, 1
0x1800031cd  jnz     short loc_1800031C2
0x1800031cf  mov     rbx, [rsp+28h+arg_0]
0x1800031d4  add     rsp, 20h
0x1800031d8  pop     rdi
0x1800031d9  retn
```
