# ___acrt_lowio_create_handle_array

- ea: `0x410f74`
- end: `0x410fef`
- name: `___acrt_lowio_create_handle_array`
- size: `123`
- prototype: `char *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x411024`

## callees

- `0x40ffbd`
- `0x41001a`
- `0x410f74`
- `0x411e67`

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
0x410f74  mov     edi, edi
0x410f76  push    ebp
0x410f77  mov     ebp, esp
0x410f79  push    ecx
0x410f7a  push    ecx
0x410f7b  push    ebx
0x410f7c  push    esi
0x410f7d  push    38h ; '8'; Size
0x410f7f  push    40h ; '@'; Count
0x410f81  call    __calloc_base
0x410f86  mov     esi, eax
0x410f88  xor     ebx, ebx
0x410f8a  mov     [ebp+var_8], esi
0x410f8d  pop     ecx
0x410f8e  pop     ecx
0x410f8f  test    esi, esi
0x410f91  jnz     short loc_410F97
0x410f93  mov     esi, ebx
0x410f95  jmp     short loc_410FE2
0x410f97  lea     eax, [esi+0E00h]
0x410f9d  cmp     esi, eax
0x410f9f  jz      short loc_410FE2
0x410fa1  push    edi
0x410fa2  lea     edi, [esi+20h]
0x410fa5  mov     esi, eax
0x410fa7  push    ebx; int
0x410fa8  push    0FA0h; dwSpinCount
0x410fad  lea     eax, [edi-20h]
0x410fb0  push    eax; lpCriticalSection
0x410fb1  call    ___acrt_InitializeCriticalSectionEx@12
0x410fb6  or      dword ptr [edi-8], 0FFFFFFFFh
0x410fba  and     byte ptr [edi+0Dh], 0F8h
0x410fbe  mov     [edi], ebx
0x410fc0  lea     edi, [edi+38h]
0x410fc3  mov     [edi-34h], ebx
0x410fc6  lea     eax, [edi-20h]
0x410fc9  mov     dword ptr [edi-30h], 0A0A0000h
0x410fd0  mov     byte ptr [edi-2Ch], 0Ah
0x410fd4  mov     [edi-2Ah], ebx
0x410fd7  mov     [edi-26h], bl
0x410fda  cmp     eax, esi
0x410fdc  jnz     short loc_410FA7
0x410fde  mov     esi, [ebp+var_8]
0x410fe1  pop     edi
0x410fe2  push    ebx; Block
0x410fe3  call    __free_base
0x410fe8  pop     ecx
0x410fe9  mov     eax, esi
0x410feb  pop     esi
0x410fec  pop     ebx
0x410fed  leave
0x410fee  retn
```
