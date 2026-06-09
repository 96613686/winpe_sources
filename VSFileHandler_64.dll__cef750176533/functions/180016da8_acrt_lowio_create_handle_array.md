# __acrt_lowio_create_handle_array

- ea: `0x180016da8`
- end: `0x180016e4d`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: `char *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016ea0`

## callees

- `0x18000fe3c`
- `0x1800120b0`
- `0x180013de8`
- `0x180016da8`

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
      _acrt_InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 - 48), 0xFA0u);
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
0x180016da8  mov     [rsp+arg_0], rbx
0x180016dad  mov     [rsp+arg_8], rbp
0x180016db2  mov     [rsp+arg_10], rsi
0x180016db7  push    rdi
0x180016db8  sub     rsp, 20h
0x180016dbc  mov     edx, 48h ; 'H'; Size
0x180016dc1  lea     ecx, [rdx-8]; Count
0x180016dc4  call    _calloc_base
0x180016dc9  xor     esi, esi
0x180016dcb  mov     rbx, rax
0x180016dce  test    rax, rax
0x180016dd1  jz      short loc_180016E2E
0x180016dd3  lea     rbp, [rax+1200h]
0x180016dda  cmp     rax, rbp
0x180016ddd  jz      short loc_180016E2B
0x180016ddf  lea     rdi, [rax+30h]
0x180016de3  lea     rcx, [rdi-30h]; lpCriticalSection
0x180016de7  xor     r8d, r8d
0x180016dea  mov     edx, 0FA0h; dwSpinCount
0x180016def  call    __acrt_InitializeCriticalSectionEx
0x180016df4  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x180016df9  lea     rcx, [rdi+0Eh]
0x180016dfd  and     byte ptr [rdi+0Dh], 0F8h
0x180016e01  mov     eax, esi
0x180016e03  mov     [rdi], rsi
0x180016e06  mov     dword ptr [rdi+8], 0A0A0000h
0x180016e0d  mov     byte ptr [rdi+0Ch], 0Ah
0x180016e11  mov     [rcx], sil
0x180016e14  inc     eax
0x180016e16  inc     rcx
0x180016e19  cmp     eax, 5
0x180016e1c  jb      short loc_180016E11
0x180016e1e  add     rdi, 48h ; 'H'
0x180016e22  lea     rax, [rdi-30h]
0x180016e26  cmp     rax, rbp
0x180016e29  jnz     short loc_180016DE3
0x180016e2b  mov     rsi, rbx
0x180016e2e  xor     ecx, ecx; Block
0x180016e30  call    _free_base
0x180016e35  mov     rbx, [rsp+28h+arg_0]
0x180016e3a  mov     rax, rsi
0x180016e3d  mov     rsi, [rsp+28h+arg_10]
0x180016e42  mov     rbp, [rsp+28h+arg_8]
0x180016e47  add     rsp, 20h
0x180016e4b  pop     rdi
0x180016e4c  retn
```
