# StateItem::Create(int)

- ea: `0x140003b78`
- end: `0x140003bae`
- name: `?Create@StateItem@@SAPEAV1@H@Z`
- size: `54`
- prototype: `struct StateItem *__fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400017ac`

## callees

- `0x140001090`
- `0x140003b78`

## pseudocode

```c
struct StateItem *__fastcall StateItem::Create(int a1)
{
  struct StateItem *result; // rax
  SIZE_T v3; // rcx

  result = 0;
  if ( a1 >= 0 )
  {
    v3 = (unsigned int)(a1 + 8);
    if ( (unsigned int)v3 >= 8 )
    {
      result = (struct StateItem *)BlockMem::Alloc(v3);
      if ( result )
      {
        *(_DWORD *)result = 1;
        *((_DWORD *)result + 1) = a1;
        _InterlockedIncrement(&StateItem::s_cStateItems);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003b78  push    rbx
0x140003b7a  sub     rsp, 20h
0x140003b7e  xor     eax, eax
0x140003b80  mov     ebx, ecx
0x140003b82  test    ecx, ecx
0x140003b84  js      short loc_140003BA8
0x140003b86  add     ecx, 8; dwBytes
0x140003b89  cmp     ecx, 8
0x140003b8c  jb      short loc_140003BA8
0x140003b8e  call    ?Alloc@BlockMem@@SAPEAXI@Z; BlockMem::Alloc(uint)
0x140003b93  test    rax, rax
0x140003b96  jz      short loc_140003BA8
0x140003b98  mov     dword ptr [rax], 1
0x140003b9e  mov     [rax+4], ebx
0x140003ba1  lock inc cs:?s_cStateItems@StateItem@@0JA; long StateItem::s_cStateItems
0x140003ba8  add     rsp, 20h
0x140003bac  pop     rbx
0x140003bad  retn
```
