# __acrt_lowio_create_handle_array

- ea: `0x1400082c8`
- end: `0x14000836d`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400083c0`

## callees

- `0x1400068c0`
- `0x140006940`
- `0x1400082c8`
- `0x1400096ec`

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
0x1400082c8  mov     [rsp+arg_0], rbx
0x1400082cd  mov     [rsp+arg_8], rbp
0x1400082d2  mov     [rsp+arg_10], rsi
0x1400082d7  push    rdi
0x1400082d8  sub     rsp, 20h
0x1400082dc  mov     edx, 48h ; 'H'; Size
0x1400082e1  lea     ecx, [rdx-8]; Count
0x1400082e4  call    _calloc_base
0x1400082e9  xor     esi, esi
0x1400082eb  mov     rbx, rax
0x1400082ee  test    rax, rax
0x1400082f1  jz      short loc_14000834E
0x1400082f3  lea     rbp, [rax+1200h]
0x1400082fa  cmp     rax, rbp
0x1400082fd  jz      short loc_14000834B
0x1400082ff  lea     rdi, [rax+30h]
0x140008303  lea     rcx, [rdi-30h]; lpCriticalSection
0x140008307  xor     r8d, r8d; Flags
0x14000830a  mov     edx, 0FA0h; dwSpinCount
0x14000830f  call    InitializeCriticalSectionEx
0x140008314  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x140008319  lea     rcx, [rdi+0Eh]
0x14000831d  and     byte ptr [rdi+0Dh], 0F8h
0x140008321  mov     eax, esi
0x140008323  mov     [rdi], rsi
0x140008326  mov     dword ptr [rdi+8], 0A0A0000h
0x14000832d  mov     byte ptr [rdi+0Ch], 0Ah
0x140008331  mov     [rcx], sil
0x140008334  inc     eax
0x140008336  inc     rcx
0x140008339  cmp     eax, 5
0x14000833c  jb      short loc_140008331
0x14000833e  add     rdi, 48h ; 'H'
0x140008342  lea     rax, [rdi-30h]
0x140008346  cmp     rax, rbp
0x140008349  jnz     short loc_140008303
0x14000834b  mov     rsi, rbx
0x14000834e  xor     ecx, ecx; Block
0x140008350  call    _free_base
0x140008355  mov     rbx, [rsp+28h+arg_0]
0x14000835a  mov     rax, rsi
0x14000835d  mov     rsi, [rsp+28h+arg_10]
0x140008362  mov     rbp, [rsp+28h+arg_8]
0x140008367  add     rsp, 20h
0x14000836b  pop     rdi
0x14000836c  retn
```
