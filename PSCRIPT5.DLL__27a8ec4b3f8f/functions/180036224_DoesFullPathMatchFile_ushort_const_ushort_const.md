# DoesFullPathMatchFile(ushort const *,ushort const *)

- ea: `0x180036224`
- end: `0x180036279`
- name: `?DoesFullPathMatchFile@@YA_NPEBG0@Z`
- size: `85`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034bc`
- `0x180029d7c`
- `0x180034774`
- `0x180036280`
- `0x1800362e0`
- `0x180036d30`
- `0x18003791c`
- `0x180038118`

## callees

- `0x18000289c`
- `0x180036224`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180036239`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180036239`

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
0x180036224  mov     [rsp+arg_0], rbx
0x180036229  push    rdi
0x18003622a  sub     rsp, 20h
0x18003622e  mov     rdi, rdx
0x180036231  mov     rbx, rcx
0x180036234  mov     edx, 5Ch ; '\'; Ch
0x180036239  call    cs:__imp_wcsrchr
0x180036240  nop     dword ptr [rax+rax+00h]
0x180036245  test    rax, rax
0x180036248  jz      short loc_180036250
0x18003624a  add     rax, 2
0x18003624e  jmp     short loc_180036253
0x180036250  mov     rax, rbx
0x180036253  test    rax, rax
0x180036256  jz      short loc_18003626B
0x180036258  mov     rdx, rdi; String2
0x18003625b  mov     rcx, rax; String1
0x18003625e  call    _wcsicmp
0x180036263  test    eax, eax
0x180036265  jnz     short loc_18003626B
0x180036267  mov     al, 1
0x180036269  jmp     short loc_18003626D
0x18003626b  xor     al, al
0x18003626d  mov     rbx, [rsp+28h+arg_0]
0x180036272  add     rsp, 20h
0x180036276  pop     rdi
0x180036277  retn
```
