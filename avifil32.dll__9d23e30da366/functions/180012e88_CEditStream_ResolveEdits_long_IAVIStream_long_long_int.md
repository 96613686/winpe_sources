# CEditStream::ResolveEdits(long,IAVIStream * *,long *,long *,int)

- ea: `0x180012e88`
- end: `0x180012f5c`
- name: `?ResolveEdits@CEditStream@@AEAAJJPEAPEAUIAVIStream@@PEAJ1H@Z`
- size: `212`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, int, struct IAVIStream **, int *, int *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180011594`
- `0x180011a64`
- `0x180011e54`
- `0x180012224`
- `0x180012a44`
- `0x180012c74`

## callees

- `0x180012e88`

## pseudocode

```c
__int64 __fastcall CEditStream::ResolveEdits(
        CEditStream *this,
        int a2,
        struct IAVIStream **a3,
        int *a4,
        int *a5,
        int a6)
{
  int v7; // edx
  int v8; // r10d
  int v9; // edi
  __int64 v10; // r8
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v16; // ecx

  if ( a2 >= *((_DWORD *)this + 10) )
  {
    v7 = a2 - *((_DWORD *)this + 10);
    v8 = 0;
    v9 = *((_DWORD *)this + 54);
    if ( v9 > 0 )
    {
      v10 = *((_QWORD *)this + 29);
      while ( 1 )
      {
        v11 = 56LL * (unsigned int)v8;
        v12 = *(_DWORD *)(v11 + v10 + 12);
        if ( v7 < v12 )
          break;
        v7 -= v12;
        if ( ++v8 >= v9 )
          goto LABEL_6;
      }
      v16 = v7 + *(_DWORD *)(v11 + v10 + 8);
      *a3 = *(struct IAVIStream **)(v11 + v10);
      *a4 = v16;
      if ( a5 )
        *a5 = v8;
      return 0;
    }
LABEL_6:
    if ( !v7 && a6 )
    {
      v13 = *((_QWORD *)this + 29);
      v14 = 56LL * v8;
      *a3 = *(struct IAVIStream **)(v14 + v13 - 56);
      *a4 = *(_DWORD *)(v14 + v13 - 48) + *(_DWORD *)(v14 + v13 - 44);
      if ( a5 )
        *a5 = v8 - 1;
      return 0;
    }
    *a3 = 0;
    *a4 = 0;
    if ( a5 )
      *a5 = 0;
  }
  return 2147762282LL;
}

```

## disassembly

```asm
0x180012e88  mov     [rsp+arg_0], rbx
0x180012e8d  mov     [rsp+arg_8], rdi
0x180012e92  mov     r11, r8
0x180012e95  cmp     edx, [rcx+28h]
0x180012e98  jl      loc_180012F4C
0x180012e9e  sub     edx, [rcx+28h]
0x180012ea1  xor     r10d, r10d
0x180012ea4  mov     edi, [rcx+0D8h]
0x180012eaa  test    edi, edi
0x180012eac  jle     short loc_180012ECF
0x180012eae  mov     r8, [rcx+0E8h]
0x180012eb5  mov     eax, r10d
0x180012eb8  imul    rbx, rax, 38h ; '8'
0x180012ebc  mov     eax, [rbx+r8+0Ch]
0x180012ec1  cmp     edx, eax
0x180012ec3  jl      short loc_180012F0E
0x180012ec5  sub     edx, eax
0x180012ec7  inc     r10d
0x180012eca  cmp     r10d, edi
0x180012ecd  jl      short loc_180012EB5
0x180012ecf  test    edx, edx
0x180012ed1  jnz     short loc_180012F2E
0x180012ed3  cmp     [rsp+arg_28], edx
0x180012ed7  jz      short loc_180012F2E
0x180012ed9  mov     rcx, [rcx+0E8h]
0x180012ee0  movsxd  rax, r10d
0x180012ee3  imul    rdx, rax, 38h ; '8'
0x180012ee7  mov     rax, [rdx+rcx-38h]
0x180012eec  mov     [r11], rax
0x180012eef  mov     eax, [rdx+rcx-2Ch]
0x180012ef3  add     eax, [rdx+rcx-30h]
0x180012ef7  mov     rcx, [rsp+arg_20]
0x180012efc  mov     [r9], eax
0x180012eff  test    rcx, rcx
0x180012f02  jz      short loc_180012F0A
0x180012f04  lea     eax, [r10-1]
0x180012f08  mov     [rcx], eax
0x180012f0a  xor     eax, eax
0x180012f0c  jmp     short loc_180012F51
0x180012f0e  mov     rax, [rbx+r8]
0x180012f12  mov     ecx, [rbx+r8+8]
0x180012f17  add     ecx, edx
0x180012f19  mov     [r11], rax
0x180012f1c  mov     rax, [rsp+arg_20]
0x180012f21  mov     [r9], ecx
0x180012f24  test    rax, rax
0x180012f27  jz      short loc_180012F0A
0x180012f29  mov     [rax], r10d
0x180012f2c  jmp     short loc_180012F0A
0x180012f2e  mov     rax, [rsp+arg_20]
0x180012f33  mov     qword ptr [r11], 0
0x180012f3a  mov     dword ptr [r9], 0
0x180012f41  test    rax, rax
0x180012f44  jz      short loc_180012F4C
0x180012f46  mov     dword ptr [rax], 0
0x180012f4c  mov     eax, 8004406Ah
0x180012f51  mov     rbx, [rsp+arg_0]
0x180012f56  mov     rdi, [rsp+arg_8]
0x180012f5b  retn
```
