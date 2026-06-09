# __acrt_lowio_create_handle_array

- ea: `0x140015f4c`
- end: `0x140015ff1`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: `char *()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140016044`
- `0x1400161fc`

## callees

- `0x14001074c`
- `0x1400107c4`
- `0x140013640`
- `0x140015f4c`

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
      _vcrt_InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 - 48), 0xFA0u);
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
0x140015f4c  mov     [rsp+arg_0], rbx
0x140015f51  mov     [rsp+arg_8], rbp
0x140015f56  mov     [rsp+arg_10], rsi
0x140015f5b  push    rdi
0x140015f5c  sub     rsp, 20h
0x140015f60  mov     edx, 48h ; 'H'; Size
0x140015f65  lea     ecx, [rdx-8]; Count
0x140015f68  call    _calloc_base
0x140015f6d  xor     esi, esi
0x140015f6f  mov     rbx, rax
0x140015f72  test    rax, rax
0x140015f75  jz      short loc_140015FD2
0x140015f77  lea     rbp, [rax+1200h]
0x140015f7e  cmp     rax, rbp
0x140015f81  jz      short loc_140015FCF
0x140015f83  lea     rdi, [rax+30h]
0x140015f87  lea     rcx, [rdi-30h]; lpCriticalSection
0x140015f8b  xor     r8d, r8d
0x140015f8e  mov     edx, 0FA0h; dwSpinCount
0x140015f93  call    __vcrt_InitializeCriticalSectionEx
0x140015f98  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x140015f9d  lea     rcx, [rdi+0Eh]
0x140015fa1  and     byte ptr [rdi+0Dh], 0F8h
0x140015fa5  mov     eax, esi
0x140015fa7  mov     [rdi], rsi
0x140015faa  mov     dword ptr [rdi+8], 0A0A0000h
0x140015fb1  mov     byte ptr [rdi+0Ch], 0Ah
0x140015fb5  mov     [rcx], sil
0x140015fb8  inc     eax
0x140015fba  inc     rcx
0x140015fbd  cmp     eax, 5
0x140015fc0  jb      short loc_140015FB5
0x140015fc2  add     rdi, 48h ; 'H'
0x140015fc6  lea     rax, [rdi-30h]
0x140015fca  cmp     rax, rbp
0x140015fcd  jnz     short loc_140015F87
0x140015fcf  mov     rsi, rbx
0x140015fd2  xor     ecx, ecx; Block
0x140015fd4  call    _free_base
0x140015fd9  mov     rbx, [rsp+28h+arg_0]
0x140015fde  mov     rax, rsi
0x140015fe1  mov     rsi, [rsp+28h+arg_10]
0x140015fe6  mov     rbp, [rsp+28h+arg_8]
0x140015feb  add     rsp, 20h
0x140015fef  pop     rdi
0x140015ff0  retn
```
