# DoesFullPathMatchFile(ushort const *,ushort const *)

- ea: `0x180034afc`
- end: `0x180034b4a`
- name: `?DoesFullPathMatchFile@@YA_NPEBG0@Z`
- size: `78`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033f4`
- `0x180028c30`
- `0x1800330fc`
- `0x180034b50`
- `0x180034bb0`
- `0x1800355c0`
- `0x180036118`
- `0x1800368b8`

## callees

- `0x18000283c`
- `0x180034afc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180034b11`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180034b11`

## pseudocode

```c
bool __fastcall DoesFullPathMatchFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  wchar_t *v4; // rax
  const wchar_t *v5; // rax

  v4 = wcsrchr(a1, 0x5Cu);
  if ( v4 )
    v5 = v4 + 1;
  else
    v5 = a1;
  return v5 && !wcsicmp(v5, a2);
}

```

## disassembly

```asm
0x180034afc  mov     [rsp+arg_0], rbx
0x180034b01  push    rdi
0x180034b02  sub     rsp, 20h
0x180034b06  mov     rdi, rdx
0x180034b09  mov     rbx, rcx
0x180034b0c  mov     edx, 5Ch ; '\'; Ch
0x180034b11  call    cs:__imp_wcsrchr
0x180034b17  test    rax, rax
0x180034b1a  jz      short loc_180034B22
0x180034b1c  add     rax, 2
0x180034b20  jmp     short loc_180034B25
0x180034b22  mov     rax, rbx
0x180034b25  test    rax, rax
0x180034b28  jz      short loc_180034B3D
0x180034b2a  mov     rdx, rdi; String2
0x180034b2d  mov     rcx, rax; String1
0x180034b30  call    _wcsicmp
0x180034b35  test    eax, eax
0x180034b37  jnz     short loc_180034B3D
0x180034b39  mov     al, 1
0x180034b3b  jmp     short loc_180034B3F
0x180034b3d  xor     al, al
0x180034b3f  mov     rbx, [rsp+28h+arg_0]
0x180034b44  add     rsp, 20h
0x180034b48  pop     rdi
0x180034b49  retn
```
