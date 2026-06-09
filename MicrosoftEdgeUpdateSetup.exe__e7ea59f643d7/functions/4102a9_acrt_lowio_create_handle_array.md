# ___acrt_lowio_create_handle_array

- ea: `0x4102a9`
- end: `0x410324`
- name: `___acrt_lowio_create_handle_array`
- size: `123`
- prototype: `char *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x410359`

## callees

- `0x40ecf6`
- `0x40ed53`
- `0x4102a9`
- `0x4114cc`

## pseudocode

```c
char *__acrt_lowio_create_handle_array()
{
  char *v0; // eax
  char *v1; // esi
  char *v2; // edi
  char *v3; // esi
  char *v5; // [esp+8h] [ebp-8h]

  v0 = (char *)_calloc_base(0x40u, 0x38u);
  v5 = v0;
  if ( v0 )
  {
    v2 = v0 + 32;
    v3 = v0 + 3584;
    do
    {
      __acrt_InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v2 - 32), 0xFA0u, 0);
      *((_DWORD *)v2 - 2) = -1;
      v2[13] &= 0xF8u;
      *(_DWORD *)v2 = 0;
      v2 += 56;
      *((_DWORD *)v2 - 13) = 0;
      *((_DWORD *)v2 - 12) = 168427520;
      *(v2 - 44) = 10;
      *(_DWORD *)(v2 - 42) = 0;
      *(v2 - 38) = 0;
    }
    while ( v2 - 32 != v3 );
    v1 = v5;
  }
  else
  {
    v1 = 0;
  }
  _free_base(0);
  return v1;
}

```

## disassembly

```asm
0x4102a9  mov     edi, edi
0x4102ab  push    ebp
0x4102ac  mov     ebp, esp
0x4102ae  push    ecx
0x4102af  push    ecx
0x4102b0  push    ebx
0x4102b1  push    esi
0x4102b2  push    38h ; '8'; Size
0x4102b4  push    40h ; '@'; Count
0x4102b6  call    __calloc_base
0x4102bb  mov     esi, eax
0x4102bd  xor     ebx, ebx
0x4102bf  mov     [ebp+var_8], esi
0x4102c2  pop     ecx
0x4102c3  pop     ecx
0x4102c4  test    esi, esi
0x4102c6  jnz     short loc_4102CC
0x4102c8  mov     esi, ebx
0x4102ca  jmp     short loc_410317
0x4102cc  lea     eax, [esi+0E00h]
0x4102d2  cmp     esi, eax
0x4102d4  jz      short loc_410317
0x4102d6  push    edi
0x4102d7  lea     edi, [esi+20h]
0x4102da  mov     esi, eax
0x4102dc  push    ebx; int
0x4102dd  push    0FA0h; dwSpinCount
0x4102e2  lea     eax, [edi-20h]
0x4102e5  push    eax; lpCriticalSection
0x4102e6  call    ___acrt_InitializeCriticalSectionEx@12
0x4102eb  or      dword ptr [edi-8], 0FFFFFFFFh
0x4102ef  and     byte ptr [edi+0Dh], 0F8h
0x4102f3  mov     [edi], ebx
0x4102f5  lea     edi, [edi+38h]
0x4102f8  mov     [edi-34h], ebx
0x4102fb  lea     eax, [edi-20h]
0x4102fe  mov     dword ptr [edi-30h], 0A0A0000h
0x410305  mov     byte ptr [edi-2Ch], 0Ah
0x410309  mov     [edi-2Ah], ebx
0x41030c  mov     [edi-26h], bl
0x41030f  cmp     eax, esi
0x410311  jnz     short loc_4102DC
0x410313  mov     esi, [ebp+var_8]
0x410316  pop     edi
0x410317  push    ebx; Block
0x410318  call    __free_base
0x41031d  pop     ecx
0x41031e  mov     eax, esi
0x410320  pop     esi
0x410321  pop     ebx
0x410322  leave
0x410323  retn
```
