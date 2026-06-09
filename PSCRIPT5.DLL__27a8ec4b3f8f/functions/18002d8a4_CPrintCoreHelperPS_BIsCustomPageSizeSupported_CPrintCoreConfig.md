# CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)

- ea: `0x18002d8a4`
- end: `0x18002d91a`
- name: `?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(CPrintCoreHelperPS *this, struct CPrintCoreConfig *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002dcf0`
- `0x18002e0c0`
- `0x18002e640`

## callees

- `0x18002d8a4`
- `0x180034358`
- `0x180034384`

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
0x18002d8a4  mov     [rsp+arg_0], rbx
0x18002d8a9  push    rdi
0x18002d8aa  sub     rsp, 20h
0x18002d8ae  mov     rcx, rdx; this
0x18002d8b1  mov     rdi, rdx
0x18002d8b4  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002d8b9  test    byte ptr [rax+8Ch], 20h
0x18002d8c0  jz      short loc_18002D90C
0x18002d8c2  mov     rcx, rdi; this
0x18002d8c5  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002d8ca  cmp     dword ptr [rax+10h], 40003h
0x18002d8d1  jnb     short loc_18002D905
0x18002d8d3  mov     rcx, rdi; this
0x18002d8d6  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002d8db  cmp     dword ptr [rax+3Ch], 0
0x18002d8df  jz      short loc_18002D8F9
0x18002d8e1  mov     rcx, rdi; this
0x18002d8e4  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002d8e9  mov     rcx, rdi; this
0x18002d8ec  mov     ebx, [rax+3Ch]
0x18002d8ef  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x18002d8f4  add     rax, rbx
0x18002d8f7  jmp     short loc_18002D8FB
0x18002d8f9  xor     eax, eax
0x18002d8fb  mov     eax, [rax+2Ch]
0x18002d8fe  shr     eax, 1
0x18002d900  and     eax, 1
0x18002d903  jmp     short loc_18002D90E
0x18002d905  mov     eax, 1
0x18002d90a  jmp     short loc_18002D90E
0x18002d90c  xor     eax, eax
0x18002d90e  mov     rbx, [rsp+28h+arg_0]
0x18002d913  add     rsp, 20h
0x18002d917  pop     rdi
0x18002d918  retn
```
