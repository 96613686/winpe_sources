# __acrt_lowio_create_handle_array

- ea: `0x14001e2b0`
- end: `0x14001e355`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: `char *()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e3a8`
- `0x14001e560`

## callees

- `0x140019930`
- `0x14001b910`
- `0x14001d074`
- `0x14001e2b0`

## pseudocode

```c
char *_acrt_lowio_create_handle_array()
{
  char *v0; // rax
  char *v1; // rsi
  char *v2; // rbx
  char *v3; // rbp
  char *v4; // rdi
  _BYTE *v5; // rcx
  unsigned int v6; // eax

  v0 = (char *)calloc_base(0x40u, 0x48u);
  v1 = 0;
  v2 = v0;
  if ( v0 )
  {
    v3 = v0 + 4608;
    v4 = v0 + 48;
    do
    {
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 - 48), 0xFA0u, 0);
      *((_QWORD *)v4 - 1) = -1;
      v5 = v4 + 14;
      v4[13] &= 0xF8u;
      v6 = 0;
      *(_QWORD *)v4 = 0;
      *((_DWORD *)v4 + 2) = 168427520;
      v4[12] = 10;
      do
      {
        *v5 = 0;
        ++v6;
        ++v5;
      }
      while ( v6 < 5 );
      v4 += 72;
    }
    while ( v4 - 48 != v3 );
    v1 = v2;
  }
  free_base(0);
  return v1;
}

```

## disassembly

```asm
0x14001e2b0  mov     [rsp+arg_0], rbx
0x14001e2b5  mov     [rsp+arg_8], rbp
0x14001e2ba  mov     [rsp+arg_10], rsi
0x14001e2bf  push    rdi
0x14001e2c0  sub     rsp, 20h
0x14001e2c4  mov     edx, 48h ; 'H'; Size
0x14001e2c9  lea     ecx, [rdx-8]; Count
0x14001e2cc  call    _calloc_base
0x14001e2d1  xor     esi, esi
0x14001e2d3  mov     rbx, rax
0x14001e2d6  test    rax, rax
0x14001e2d9  jz      short loc_14001E336
0x14001e2db  lea     rbp, [rax+1200h]
0x14001e2e2  cmp     rax, rbp
0x14001e2e5  jz      short loc_14001E333
0x14001e2e7  lea     rdi, [rax+30h]
0x14001e2eb  lea     rcx, [rdi-30h]; lpCriticalSection
0x14001e2ef  xor     r8d, r8d; Flags
0x14001e2f2  mov     edx, 0FA0h; dwSpinCount
0x14001e2f7  call    InitializeCriticalSectionEx
0x14001e2fc  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x14001e301  lea     rcx, [rdi+0Eh]
0x14001e305  and     byte ptr [rdi+0Dh], 0F8h
0x14001e309  mov     eax, esi
0x14001e30b  mov     [rdi], rsi
0x14001e30e  mov     dword ptr [rdi+8], 0A0A0000h
0x14001e315  mov     byte ptr [rdi+0Ch], 0Ah
0x14001e319  mov     [rcx], sil
0x14001e31c  inc     eax
0x14001e31e  inc     rcx
0x14001e321  cmp     eax, 5
0x14001e324  jb      short loc_14001E319
0x14001e326  add     rdi, 48h ; 'H'
0x14001e32a  lea     rax, [rdi-30h]
0x14001e32e  cmp     rax, rbp
0x14001e331  jnz     short loc_14001E2EB
0x14001e333  mov     rsi, rbx
0x14001e336  xor     ecx, ecx; Block
0x14001e338  call    _free_base
0x14001e33d  mov     rbx, [rsp+28h+arg_0]
0x14001e342  mov     rax, rsi
0x14001e345  mov     rsi, [rsp+28h+arg_10]
0x14001e34a  mov     rbp, [rsp+28h+arg_8]
0x14001e34f  add     rsp, 20h
0x14001e353  pop     rdi
0x14001e354  retn
```
