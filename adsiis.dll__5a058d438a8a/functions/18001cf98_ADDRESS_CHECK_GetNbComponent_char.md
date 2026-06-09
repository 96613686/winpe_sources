# ADDRESS_CHECK::GetNbComponent(char *)

- ea: `0x18001cf98`
- end: `0x18001cfc6`
- name: `?GetNbComponent@ADDRESS_CHECK@@QEAAIPEAD@Z`
- size: `46`
- prototype: `unsigned int __fastcall(ADDRESS_CHECK *__hidden this, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c8b0`

## callees

- `0x18001cf98`

## import_xrefs

- `msvcrt!strchr` at `0x18001cfb3`
- `msvcrt!strchr` at `0x18001cfb3`

## pseudocode

```c
__int64 __fastcall ADDRESS_CHECK::GetNbComponent(ADDRESS_CHECK *this, char *a2)
{
  unsigned int i; // ebx
  char *v4; // rax

  for ( i = 1; ; ++i )
  {
    v4 = strchr(a2, 46);
    if ( !v4 )
      break;
    a2 = v4 + 1;
  }
  return i;
}

```

## disassembly

```asm
0x18001cf98  push    rbx
0x18001cf9a  sub     rsp, 20h
0x18001cf9e  mov     rcx, rdx
0x18001cfa1  mov     ebx, 1
0x18001cfa6  jmp     short loc_18001CFAE
0x18001cfa8  inc     ebx
0x18001cfaa  lea     rcx, [rax+1]; Str
0x18001cfae  mov     edx, 2Eh ; '.'; Val
0x18001cfb3  call    cs:__imp_strchr
0x18001cfb9  test    rax, rax
0x18001cfbc  jnz     short loc_18001CFA8
0x18001cfbe  mov     eax, ebx
0x18001cfc0  add     rsp, 20h
0x18001cfc4  pop     rbx
0x18001cfc5  retn
```
