# CCorrAPOBase::GetRegistrationProperties(APO_REG_PROPERTIES * *)

- ea: `0x180012330`
- end: `0x1800123c8`
- name: `?GetRegistrationProperties@CCorrAPOBase@@UEAAJPEAPEAUAPO_REG_PROPERTIES@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this, struct APO_REG_PROPERTIES **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012330`
- `0x180016ac1`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012390`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::GetRegistrationProperties(CCorrAPOBase *this, struct APO_REG_PROPERTIES **a2)
{
  __int128 *v3; // rbx
  int v4; // eax
  unsigned __int64 v5; // rcx
  SIZE_T v6; // rcx
  __int64 result; // rax
  unsigned int v8; // ebp
  struct APO_REG_PROPERTIES *v9; // rax
  struct APO_REG_PROPERTIES *v10; // rdi

  if ( !a2 )
    return 2147500035LL;
  v3 = (__int128 *)&pProperties;
  if ( !*((_DWORD *)this + 8) )
    v3 = &xmmword_1801B7750;
  v4 = *((_DWORD *)v3 + 268);
  if ( !v4 )
    return 2147942487LL;
  v5 = 16LL * (unsigned int)(v4 - 1);
  if ( v5 > 0xFFFFFFFF )
    return 2147942934LL;
  v6 = (unsigned int)(v5 + 1092);
  if ( (unsigned int)v6 < 0x444 )
    return 2147942934LL;
  v8 = v6;
  v9 = (struct APO_REG_PROPERTIES *)CoTaskMemAlloc(v6);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  memcpy_0(v9, v3, v8);
  result = 0;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x180012330  push    rbx
0x180012332  push    rbp
0x180012333  push    rsi
0x180012334  push    rdi
0x180012335  sub     rsp, 28h
0x180012339  mov     rsi, rdx
0x18001233c  test    rdx, rdx
0x18001233f  jz      short loc_1800123B3
0x180012341  cmp     dword ptr [rcx+20h], 0
0x180012345  lea     rax, xmmword_1801B7750
0x18001234c  lea     rbx, pProperties
0x180012353  cmovz   rbx, rax
0x180012357  mov     eax, [rbx+430h]
0x18001235d  test    eax, eax
0x18001235f  jz      short loc_1800123C1
0x180012361  lea     ecx, [rax-1]
0x180012364  mov     eax, 0FFFFFFFFh
0x180012369  shl     rcx, 4
0x18001236d  cmp     rcx, rax
0x180012370  ja      short loc_180012380
0x180012372  add     ecx, 444h; cb
0x180012378  cmp     ecx, 444h
0x18001237e  jnb     short loc_18001238E
0x180012380  mov     eax, 80070216h
0x180012385  add     rsp, 28h
0x180012389  pop     rdi
0x18001238a  pop     rsi
0x18001238b  pop     rbp
0x18001238c  pop     rbx
0x18001238d  retn
0x18001238e  mov     ebp, ecx
0x180012390  call    cs:__imp_CoTaskMemAlloc
0x180012396  mov     rdi, rax
0x180012399  test    rax, rax
0x18001239c  jz      short loc_1800123BA
0x18001239e  mov     r8d, ebp; Size
0x1800123a1  mov     rdx, rbx; Src
0x1800123a4  mov     rcx, rax; void *
0x1800123a7  call    memcpy_0
0x1800123ac  xor     eax, eax
0x1800123ae  mov     [rsi], rdi
0x1800123b1  jmp     short loc_180012385
0x1800123b3  mov     eax, 80004003h
0x1800123b8  jmp     short loc_180012385
0x1800123ba  mov     eax, 8007000Eh
0x1800123bf  jmp     short loc_180012385
0x1800123c1  mov     eax, 80070057h
0x1800123c6  jmp     short loc_180012385
```
