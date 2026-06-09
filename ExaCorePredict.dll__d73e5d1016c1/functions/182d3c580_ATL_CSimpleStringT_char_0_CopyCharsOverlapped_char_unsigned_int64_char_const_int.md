# ATL::CSimpleStringT<char,0>::CopyCharsOverlapped(char *,unsigned __int64,char const *,int)

- ea: `0x182d3c580`
- end: `0x182d3c5df`
- name: `?CopyCharsOverlapped@?$CSimpleStringT@D$0A@@ATL@@SAXPEAD_KPEBDH@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x182d3d3a0`

## callees

- `0x182d3c580`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182d3c5d3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x182d3c5a4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x182d3c5c5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182d3c594`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182d3c5b5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182d3c594`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182d3c5b5`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<char,0>::CopyCharsOverlapped(void *a1, unsigned __int64 a2, const void *a3, int a4)
{
  if ( a4 )
  {
    if ( !a1 || !a3 )
    {
      *_errno() = 22;
LABEL_4:
      _invalid_parameter_noinfo();
      return;
    }
    if ( a2 < a4 )
    {
      *_errno() = 34;
      goto LABEL_4;
    }
    memmove(a1, a3, a4);
  }
}

```

## disassembly

```asm
0x182d3c580  sub     rsp, 28h
0x182d3c584  mov     rax, r8
0x182d3c587  movsxd  r8, r9d
0x182d3c58a  test    r9d, r9d
0x182d3c58d  jz      short loc_182D3C5DA
0x182d3c58f  test    rcx, rcx
0x182d3c592  jnz     short loc_182D3C5AB
0x182d3c594  call    cs:__imp__errno
0x182d3c59a  mov     dword ptr [rax], 16h
0x182d3c5a0  add     rsp, 28h
0x182d3c5a4  jmp     cs:__imp__invalid_parameter_noinfo
0x182d3c5ab  test    rax, rax
0x182d3c5ae  jz      short loc_182D3C594
0x182d3c5b0  cmp     rdx, r8
0x182d3c5b3  jnb     short loc_182D3C5CC
0x182d3c5b5  call    cs:__imp__errno
0x182d3c5bb  mov     dword ptr [rax], 22h ; '"'
0x182d3c5c1  add     rsp, 28h
0x182d3c5c5  jmp     cs:__imp__invalid_parameter_noinfo
0x182d3c5cc  mov     rdx, rax
0x182d3c5cf  add     rsp, 28h
0x182d3c5d3  jmp     cs:__imp_memmove
0x182d3c5da  add     rsp, 28h
0x182d3c5de  retn
```
