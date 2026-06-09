# CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)

- ea: `0x18002c484`
- end: `0x18002c4f9`
- name: `?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z`
- size: `117`
- prototype: `int(CPrintCoreHelperPS *__hidden this, struct CPrintCoreConfig *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002c8d0`
- `0x18002cca0`
- `0x18002d220`

## callees

- `0x18002c484`
- `0x180032ce4`
- `0x180032d10`

## pseudocode

```c
__int64 __fastcall CPrintCoreHelperPS::BIsCustomPageSizeSupported(
        CPrintCoreHelperPS *this,
        struct CPrintCoreConfig *a2)
{
  __int64 v3; // rbx
  char *v4; // rax

  if ( (*((_BYTE *)CPrintCoreConfig::GetUIInfo(a2) + 140) & 0x20) == 0 )
    return 0;
  if ( *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 4) >= 0x40003u )
    return 1;
  if ( *((_DWORD *)CPrintCoreConfig::GetInfoHeader(a2) + 15) )
  {
    v3 = *((unsigned int *)CPrintCoreConfig::GetInfoHeader(a2) + 15);
    v4 = (char *)CPrintCoreConfig::GetInfoHeader(a2) + v3;
  }
  else
  {
    v4 = 0;
  }
  return (*((_DWORD *)v4 + 11) >> 1) & 1;
}

```

## disassembly

```asm
0x18002c484  mov     [rsp+arg_0], rbx
0x18002c489  push    rdi
0x18002c48a  sub     rsp, 20h
0x18002c48e  mov     rcx, rdx; this
0x18002c491  mov     rdi, rdx
0x18002c494  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002c499  test    byte ptr [rax+8Ch], 20h
0x18002c4a0  jz      short loc_18002C4EC
0x18002c4a2  mov     rcx, rdi; this
0x18002c4a5  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002c4aa  cmp     dword ptr [rax+10h], 40003h
0x18002c4b1  jnb     short loc_18002C4E5
0x18002c4b3  mov     rcx, rdi; this
0x18002c4b6  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002c4bb  cmp     dword ptr [rax+3Ch], 0
0x18002c4bf  jz      short loc_18002C4D9
0x18002c4c1  mov     rcx, rdi; this
0x18002c4c4  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002c4c9  mov     rcx, rdi; this
0x18002c4cc  mov     ebx, [rax+3Ch]
0x18002c4cf  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002c4d4  add     rax, rbx
0x18002c4d7  jmp     short loc_18002C4DB
0x18002c4d9  xor     eax, eax
0x18002c4db  mov     eax, [rax+2Ch]
0x18002c4de  shr     eax, 1
0x18002c4e0  and     eax, 1
0x18002c4e3  jmp     short loc_18002C4EE
0x18002c4e5  mov     eax, 1
0x18002c4ea  jmp     short loc_18002C4EE
0x18002c4ec  xor     eax, eax
0x18002c4ee  mov     rbx, [rsp+28h+arg_0]
0x18002c4f3  add     rsp, 20h
0x18002c4f7  pop     rdi
0x18002c4f8  retn
```
