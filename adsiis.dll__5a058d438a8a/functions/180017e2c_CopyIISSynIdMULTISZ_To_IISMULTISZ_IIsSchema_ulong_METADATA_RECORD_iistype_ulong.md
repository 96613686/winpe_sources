# CopyIISSynIdMULTISZ_To_IISMULTISZ(IIsSchema *,ulong,_METADATA_RECORD *,_iistype *,ulong)

- ea: `0x180017e2c`
- end: `0x180017f64`
- name: `?CopyIISSynIdMULTISZ_To_IISMULTISZ@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KPEAU1@PEAU_iistype@@K@Z`
- size: `312`
- prototype: `struct _METADATA_RECORD *__fastcall(struct IIsSchema *, unsigned int, struct _METADATA_RECORD *, struct _iistype *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017f6c`

## callees

- `0x180017e2c`
- `0x18001b444`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180017f0e`
- `msvcrt!wcscat_s` at `0x180017f0e`
- `msvcrt!wcscpy_s` at `0x180017ee6`
- `msvcrt!wcscpy_s` at `0x180017ee6`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017ecb`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017ecb`

## pseudocode

```c
struct _METADATA_RECORD *__fastcall CopyIISSynIdMULTISZ_To_IISMULTISZ(
        struct IIsSchema *a1,
        unsigned int a2,
        struct _METADATA_RECORD *a3,
        struct _iistype *a4,
        unsigned int a5)
{
  DWORD v8; // edx
  unsigned int i; // r8d
  __int64 v10; // rax
  rsize_t v11; // rsi
  wchar_t *v12; // rax
  unsigned __int8 *v13; // rbx
  unsigned int v14; // ebp
  const wchar_t *v15; // r15
  __int64 v16; // rdx
  unsigned __int8 *v17; // rcx
  DWORD v19; // [rsp+58h] [rbp+10h] BYREF
  DWORD v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = 0;
  v20 = 0;
  IIsSchema::LookupMDFlags(a1, a2, &v19, &v20);
  a3->dwMDAttributes = v19;
  a3->dwMDUserType = v20;
  a3->dwMDIdentifier = a2;
  *(_QWORD *)&a3->dwMDDataType = 5;
  a3->pbMDData = 0;
  if ( a4 )
  {
    v8 = 0;
    if ( a5 )
    {
      for ( i = 0; i < a5; ++i )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(*((_QWORD *)a4 + 3 * i + 1) + 2 * v10) );
        v8 += 2 * v10 + 2;
        a3->dwMDDataLen = v8;
      }
    }
    v11 = (unsigned __int64)(v8 + 2) >> 1;
    v12 = (wchar_t *)AllocADsMem(2 * (int)v11);
    v13 = (unsigned __int8 *)v12;
    if ( v12 )
    {
      wcscpy_s(v12, v11, &psz);
      v14 = 0;
      for ( a3->pbMDData = v13; v14 < a5; ++v14 )
      {
        v15 = (const wchar_t *)*((_QWORD *)a4 + 3 * v14 + 1);
        wcscat_s((wchar_t *)v13, v11, v15);
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v17 = &v13[2 * v16];
        *(_WORD *)v17 = 0;
        v11 += -1 - v16;
        v13 = v17 + 2;
      }
      *(_WORD *)v13 = 0;
      a3->dwMDDataLen += 2;
    }
  }
  return a3;
}

```

## disassembly

```asm
0x180017e2c  mov     rax, rsp
0x180017e2f  mov     [rax+8], rbx
0x180017e33  mov     [rax+20h], rbp
0x180017e37  push    rsi
0x180017e38  push    rdi
0x180017e39  push    r12
0x180017e3b  push    r13
0x180017e3d  push    r15
0x180017e3f  sub     rsp, 20h
0x180017e43  mov     r12, r9
0x180017e46  mov     rdi, r8
0x180017e49  xor     r13d, r13d
0x180017e4c  lea     r9, [rax+18h]; unsigned int *
0x180017e50  lea     r8, [rax+10h]; unsigned int *
0x180017e54  mov     [rax+10h], r13d
0x180017e58  mov     [rax+18h], r13d
0x180017e5c  mov     ebx, edx
0x180017e5e  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180017e63  mov     eax, [rsp+48h+arg_8]
0x180017e67  mov     [rdi+4], eax
0x180017e6a  mov     eax, [rsp+48h+arg_10]
0x180017e6e  mov     [rdi+8], eax
0x180017e71  mov     [rdi], ebx
0x180017e73  mov     qword ptr [rdi+0Ch], 5
0x180017e7b  mov     [rdi+18h], r13
0x180017e7f  test    r12, r12
0x180017e82  jz      loc_180017F4A
0x180017e88  mov     edx, r13d
0x180017e8b  cmp     [rsp+48h+arg_20], r13d
0x180017e90  jbe     short loc_180017EC2
0x180017e92  mov     r8d, r13d
0x180017e95  mov     eax, r8d
0x180017e98  lea     rcx, [rax+rax*2]
0x180017e9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017ea0  mov     r9, [r12+rcx*8+8]
0x180017ea5  inc     rax
0x180017ea8  cmp     [r9+rax*2], r13w
0x180017ead  jnz     short loc_180017EA5
0x180017eaf  lea     edx, [rdx+rax*2]
0x180017eb2  inc     r8d
0x180017eb5  add     edx, 2
0x180017eb8  mov     [rdi+10h], edx
0x180017ebb  cmp     r8d, [rsp+48h+arg_20]
0x180017ec0  jb      short loc_180017E95
0x180017ec2  lea     esi, [rdx+2]
0x180017ec5  shr     rsi, 1
0x180017ec8  lea     ecx, [rsi+rsi]; cb
0x180017ecb  call    cs:__imp_AllocADsMem
0x180017ed1  mov     rbx, rax
0x180017ed4  test    rax, rax
0x180017ed7  jz      short loc_180017F4A
0x180017ed9  lea     r8, psz; Source
0x180017ee0  mov     rdx, rsi; SizeInWords
0x180017ee3  mov     rcx, rax; Destination
0x180017ee6  call    cs:__imp_wcscpy_s
0x180017eec  mov     ebp, r13d
0x180017eef  mov     [rdi+18h], rbx
0x180017ef3  cmp     [rsp+48h+arg_20], r13d
0x180017ef8  jbe     short loc_180017F42
0x180017efa  mov     eax, ebp
0x180017efc  mov     rdx, rsi; SizeInWords
0x180017eff  lea     rcx, [rax+rax*2]
0x180017f03  mov     r15, [r12+rcx*8+8]
0x180017f08  mov     rcx, rbx; Destination
0x180017f0b  mov     r8, r15; Source
0x180017f0e  call    cs:__imp_wcscat_s
0x180017f14  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017f18  mov     rdx, r8
0x180017f1b  inc     rdx
0x180017f1e  cmp     [r15+rdx*2], r13w
0x180017f23  jnz     short loc_180017F1B
0x180017f25  lea     rcx, [rbx+rdx*2]
0x180017f29  mov     rax, r8
0x180017f2c  sub     rax, rdx
0x180017f2f  mov     [rcx], r13w
0x180017f33  add     rsi, rax
0x180017f36  lea     rbx, [rcx+2]
0x180017f3a  inc     ebp
0x180017f3c  cmp     ebp, [rsp+48h+arg_20]
0x180017f40  jb      short loc_180017EFA
0x180017f42  mov     [rbx], r13w
0x180017f46  add     dword ptr [rdi+10h], 2
0x180017f4a  mov     rbx, [rsp+48h+arg_0]
0x180017f4f  mov     rax, rdi
0x180017f52  mov     rbp, [rsp+48h+arg_18]
0x180017f57  add     rsp, 20h
0x180017f5b  pop     r15
0x180017f5d  pop     r13
0x180017f5f  pop     r12
0x180017f61  pop     rdi
0x180017f62  pop     rsi
0x180017f63  retn
```
