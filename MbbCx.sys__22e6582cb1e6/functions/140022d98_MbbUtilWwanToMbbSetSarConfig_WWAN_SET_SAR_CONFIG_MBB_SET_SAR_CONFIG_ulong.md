# MbbUtilWwanToMbbSetSarConfig(_WWAN_SET_SAR_CONFIG *,_MBB_SET_SAR_CONFIG * *,ulong *)

- ea: `0x140022d98`
- end: `0x140022e7a`
- name: `?MbbUtilWwanToMbbSetSarConfig@@YAHPEAU_WWAN_SET_SAR_CONFIG@@PEAPEAU_MBB_SET_SAR_CONFIG@@PEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct _WWAN_SET_SAR_CONFIG *, struct _MBB_SET_SAR_CONFIG **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140015fc0`

## callees

- `0x140020d40`
- `0x140022d98`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022dee`
- `ntoskrnl!ExAllocatePool2` at `0x140022dee`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbSetSarConfig(
        struct _WWAN_SET_SAR_CONFIG *a1,
        struct _MBB_SET_SAR_CONFIG **a2,
        unsigned int *a3)
{
  bool v3; // zf
  unsigned int *v4; // rsi
  __int64 result; // rax
  unsigned int v8; // r14d
  int v9; // r13d
  unsigned int v10; // ebp
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v12; // rbx
  __int64 v13; // r12
  unsigned int v14; // esi
  int v15; // eax
  size_t Size; // [rsp+28h] [rbp-50h]

  v3 = *((_DWORD *)a1 + 2) == 20;
  v4 = a3;
  *a3 = 0;
  if ( !v3 )
    return 3221225485LL;
  v8 = *((_DWORD *)a1 + 3);
  v9 = 8 * v8 + 12;
  v10 = 8 * v8 + v9;
  Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v10, 1683505741);
  v12 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v13 = 0;
  *(_DWORD *)Pool2 = *(_DWORD *)a1;
  *((_DWORD *)Pool2 + 1) = *((_DWORD *)a1 + 1);
  *((_DWORD *)Pool2 + 2) = v8;
  if ( v8 )
  {
    v14 = 16;
    do
    {
      LODWORD(Size) = 8;
      v15 = MbbUtilWriteStringToBuffer(
              v12,
              v10,
              v9,
              (struct _MBB_STRING *)&v12[8 * v13 + 12],
              (const unsigned __int8 *)a1 + v14,
              Size);
      v14 += 8;
      v13 = (unsigned int)(v13 + 1);
      v9 = v15;
    }
    while ( (unsigned int)v13 < v8 );
    v4 = a3;
  }
  *a2 = (struct _MBB_SET_SAR_CONFIG *)v12;
  result = 0;
  *v4 = v10;
  return result;
}

```

## disassembly

```asm
0x140022d98  mov     [rsp+arg_10], r8
0x140022d9d  push    rbx
0x140022d9e  push    rbp
0x140022d9f  push    rsi
0x140022da0  push    rdi
0x140022da1  push    r12
0x140022da3  push    r13
0x140022da5  push    r14
0x140022da7  push    r15
0x140022da9  sub     rsp, 38h
0x140022dad  cmp     dword ptr [rcx+8], 14h
0x140022db1  mov     rsi, r8
0x140022db4  mov     r15, rdx
0x140022db7  mov     dword ptr [r8], 0
0x140022dbe  mov     rdi, rcx
0x140022dc1  jz      short loc_140022DCD
0x140022dc3  mov     eax, 0C000000Dh
0x140022dc8  jmp     loc_140022E68
0x140022dcd  mov     r14d, [rcx+0Ch]
0x140022dd1  mov     r8d, 6458424Dh
0x140022dd7  mov     ecx, 40h ; '@'
0x140022ddc  lea     eax, ds:0[r14*8]
0x140022de4  lea     r13d, [rax+0Ch]
0x140022de8  lea     ebp, [rax+r13]
0x140022dec  mov     edx, ebp
0x140022dee  call    cs:__imp_ExAllocatePool2
0x140022df5  nop     dword ptr [rax+rax+00h]
0x140022dfa  mov     rbx, rax
0x140022dfd  test    rax, rax
0x140022e00  jnz     short loc_140022E09
0x140022e02  mov     eax, 0C000009Ah
0x140022e07  jmp     short loc_140022E68
0x140022e09  mov     eax, [rdi]
0x140022e0b  xor     r12d, r12d
0x140022e0e  mov     [rbx], eax
0x140022e10  mov     eax, [rdi+4]
0x140022e13  mov     [rbx+4], eax
0x140022e16  mov     [rbx+8], r14d
0x140022e1a  test    r14d, r14d
0x140022e1d  jz      short loc_140022E61
0x140022e1f  lea     esi, [r12+10h]
0x140022e24  mov     ecx, esi
0x140022e26  lea     r9, [rbx+0Ch]
0x140022e2a  add     rcx, rdi
0x140022e2d  mov     dword ptr [rsp+78h+Size], 8; Size
0x140022e35  mov     [rsp+78h+Src], rcx; Src
0x140022e3a  lea     r9, [r9+r12*8]; struct _MBB_STRING *
0x140022e3e  mov     rcx, rbx; unsigned __int8 *
0x140022e41  mov     r8d, r13d; unsigned int
0x140022e44  mov     edx, ebp; unsigned int
0x140022e46  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140022e4b  add     esi, 8
0x140022e4e  inc     r12d
0x140022e51  mov     r13d, eax
0x140022e54  cmp     r12d, r14d
0x140022e57  jb      short loc_140022E24
0x140022e59  mov     rsi, [rsp+78h+arg_10]
0x140022e61  mov     [r15], rbx
0x140022e64  xor     eax, eax
0x140022e66  mov     [rsi], ebp
0x140022e68  add     rsp, 38h
0x140022e6c  pop     r15
0x140022e6e  pop     r14
0x140022e70  pop     r13
0x140022e72  pop     r12
0x140022e74  pop     rdi
0x140022e75  pop     rsi
0x140022e76  pop     rbp
0x140022e77  pop     rbx
0x140022e78  retn
```
