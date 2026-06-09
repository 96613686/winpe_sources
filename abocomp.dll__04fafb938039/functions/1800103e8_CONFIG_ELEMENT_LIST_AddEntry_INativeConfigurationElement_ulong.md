# CONFIG_ELEMENT_LIST::AddEntry(INativeConfigurationElement *,ulong)

- ea: `0x1800103e8`
- end: `0x180010438`
- name: `?AddEntry@CONFIG_ELEMENT_LIST@@QEAAJPEAVINativeConfigurationElement@@K@Z`
- size: `80`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT_LIST *__hidden this, struct INativeConfigurationElement *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010f40`
- `0x180023cf0`
- `0x180024a10`

## callees

- `0x1800103e8`
- `0x180010504`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010418`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010418`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT_LIST::AddEntry(CONFIG_ELEMENT_LIST *this, struct INativeConfigurationElement *a2)
{
  int Storage; // ebx

  if ( a2 )
  {
    Storage = CONFIG_ELEMENT_LIST::AllocateStorage(this);
    if ( Storage >= 0 )
    {
      *((_QWORD *)BUFFER::QueryPtr((CONFIG_ELEMENT_LIST *)((char *)this + 8)) + *(unsigned int *)this) = a2;
      ++*(_DWORD *)this;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x1800103e8  mov     [rsp+arg_0], rbx
0x1800103ed  mov     [rsp+arg_8], rsi
0x1800103f2  push    rdi
0x1800103f3  sub     rsp, 20h
0x1800103f7  mov     rsi, rdx
0x1800103fa  mov     rdi, rcx
0x1800103fd  test    rdx, rdx
0x180010400  jnz     short loc_180010409
0x180010402  mov     ebx, 80070057h
0x180010407  jmp     short loc_180010426
0x180010409  call    ?AllocateStorage@CONFIG_ELEMENT_LIST@@AEAAJXZ; CONFIG_ELEMENT_LIST::AllocateStorage(void)
0x18001040e  mov     ebx, eax
0x180010410  test    eax, eax
0x180010412  js      short loc_180010426
0x180010414  lea     rcx, [rdi+8]
0x180010418  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001041e  mov     ecx, [rdi]
0x180010420  mov     [rax+rcx*8], rsi
0x180010424  inc     dword ptr [rdi]
0x180010426  mov     rsi, [rsp+28h+arg_8]
0x18001042b  mov     eax, ebx
0x18001042d  mov     rbx, [rsp+28h+arg_0]
0x180010432  add     rsp, 20h
0x180010436  pop     rdi
0x180010437  retn
```
