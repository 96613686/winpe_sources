# ___acrt_lowio_create_handle_array

- ea: `0x415d2a`
- end: `0x415da5`
- name: `___acrt_lowio_create_handle_array`
- size: `123`
- prototype: `char *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x415dda`

## callees

- `0x4136b2`
- `0x413e19`
- `0x415085`
- `0x415d2a`

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
0x415d2a  mov     edi, edi
0x415d2c  push    ebp
0x415d2d  mov     ebp, esp
0x415d2f  push    ecx
0x415d30  push    ecx
0x415d31  push    ebx
0x415d32  push    esi
0x415d33  push    38h ; '8'; Size
0x415d35  push    40h ; '@'; Count
0x415d37  call    __calloc_base
0x415d3c  mov     esi, eax
0x415d3e  xor     ebx, ebx
0x415d40  mov     [ebp+var_8], esi
0x415d43  pop     ecx
0x415d44  pop     ecx
0x415d45  test    esi, esi
0x415d47  jnz     short loc_415D4D
0x415d49  mov     esi, ebx
0x415d4b  jmp     short loc_415D98
0x415d4d  lea     eax, [esi+0E00h]
0x415d53  cmp     esi, eax
0x415d55  jz      short loc_415D98
0x415d57  push    edi
0x415d58  lea     edi, [esi+20h]
0x415d5b  mov     esi, eax
0x415d5d  push    ebx; int
0x415d5e  push    0FA0h; dwSpinCount
0x415d63  lea     eax, [edi-20h]
0x415d66  push    eax; lpCriticalSection
0x415d67  call    ___acrt_InitializeCriticalSectionEx@12
0x415d6c  or      dword ptr [edi-8], 0FFFFFFFFh
0x415d70  and     byte ptr [edi+0Dh], 0F8h
0x415d74  mov     [edi], ebx
0x415d76  lea     edi, [edi+38h]
0x415d79  mov     [edi-34h], ebx
0x415d7c  lea     eax, [edi-20h]
0x415d7f  mov     dword ptr [edi-30h], 0A0A0000h
0x415d86  mov     byte ptr [edi-2Ch], 0Ah
0x415d8a  mov     [edi-2Ah], ebx
0x415d8d  mov     [edi-26h], bl
0x415d90  cmp     eax, esi
0x415d92  jnz     short loc_415D5D
0x415d94  mov     esi, [ebp+var_8]
0x415d97  pop     edi
0x415d98  push    ebx; Block
0x415d99  call    __free_base
0x415d9e  pop     ecx
0x415d9f  mov     eax, esi
0x415da1  pop     esi
0x415da2  pop     ebx
0x415da3  leave
0x415da4  retn
```
