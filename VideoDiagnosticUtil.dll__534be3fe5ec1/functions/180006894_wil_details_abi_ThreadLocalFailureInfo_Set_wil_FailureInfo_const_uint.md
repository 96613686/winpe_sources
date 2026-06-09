# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006894`
- end: `0x180006acf`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `571`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041a0`

## callees

- `0x1800054f8`
- `0x180006894`
- `0x18000967e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800069ec`
- `msvcrt!memcpy_s` at `0x180006a43`
- `msvcrt!memcpy_s` at `0x180006a94`
- `msvcrt!memcpy_s` at `0x1800069ec`
- `msvcrt!memcpy_s` at `0x180006a43`
- `msvcrt!memcpy_s` at `0x180006a94`
- `KERNEL32!GetProcessHeap` at `0x18000697c`
- `KERNEL32!GetProcessHeap` at `0x18000697c`
- `KERNEL32!HeapFree` at `0x180006990`
- `KERNEL32!HeapFree` at `0x180006990`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x180006894  push    rbx
0x180006896  push    rbp
0x180006897  push    rsi
0x180006898  push    rdi
0x180006899  push    r12
0x18000689b  push    r13
0x18000689d  push    r14
0x18000689f  push    r15
0x1800068a1  sub     rsp, 28h
0x1800068a5  mov     [rcx+4], r8d
0x1800068a9  xor     r13d, r13d
0x1800068ac  mov     eax, [rdx+8]
0x1800068af  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800068b3  mov     [rcx+8], eax
0x1800068b6  mov     rdi, rcx
0x1800068b9  mov     [rcx+10h], r13
0x1800068bd  mov     r12, rdx
0x1800068c0  movzx   eax, word ptr [rdx+40h]
0x1800068c4  mov     [rcx+18h], ax
0x1800068c8  mov     al, [rdx]
0x1800068ca  mov     [rcx+1Ah], al
0x1800068cd  mov     [rcx+20h], r13
0x1800068d1  mov     rax, [rdx+88h]
0x1800068d8  mov     [rcx+28h], rax
0x1800068dc  mov     rax, [rdx+90h]
0x1800068e3  mov     [rcx+30h], rax
0x1800068e7  mov     [rcx+38h], r13
0x1800068eb  mov     rcx, [rdx+38h]
0x1800068ef  lea     edx, [rbp+2]
0x1800068f2  test    rcx, rcx
0x1800068f5  jnz     short loc_1800068FC
0x1800068f7  mov     r8d, edx
0x1800068fa  jmp     short loc_18000690C
0x1800068fc  mov     rax, rbp
0x1800068ff  inc     rax
0x180006902  cmp     [rcx+rax], r13b
0x180006906  jnz     short loc_1800068FF
0x180006908  lea     r8, [rax+1]; unsigned __int64
0x18000690c  mov     rcx, [r12+80h]
0x180006914  test    rcx, rcx
0x180006917  jz      short loc_180006929
0x180006919  mov     rax, rbp
0x18000691c  inc     rax
0x18000691f  cmp     [rcx+rax], r13b
0x180006923  jnz     short loc_18000691C
0x180006925  lea     rdx, [rax+1]
0x180006929  mov     rcx, [r12+18h]
0x18000692e  test    rcx, rcx
0x180006931  jnz     short loc_180006938
0x180006933  lea     eax, [rcx+2]
0x180006936  jmp     short loc_18000694D
0x180006938  mov     rax, rbp
0x18000693b  inc     rax
0x18000693e  cmp     [rcx+rax*2], r13w
0x180006943  jnz     short loc_18000693B
0x180006945  lea     rax, ds:2[rax*2]
0x18000694d  lea     r14, [rdx+rax]
0x180006951  add     r14, r8
0x180006954  lea     rsi, [rdi+48h]
0x180006958  cmp     [rdi+40h], r13
0x18000695c  jz      short loc_180006963
0x18000695e  cmp     [rsi], r14
0x180006961  jnb     short loc_1800069A3
0x180006963  mov     rdx, r14; dwBytes
0x180006966  mov     ecx, 8; dwFlags
0x18000696b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006970  mov     r15, rax
0x180006973  test    rax, rax
0x180006976  jz      short loc_1800069A3
0x180006978  mov     rbx, [rdi+40h]
0x18000697c  call    cs:__imp_GetProcessHeap
0x180006983  nop     dword ptr [rax+rax+00h]
0x180006988  mov     r8, rbx; lpMem
0x18000698b  xor     edx, edx; dwFlags
0x18000698d  mov     rcx, rax; hHeap
0x180006990  call    cs:__imp_HeapFree
0x180006997  nop     dword ptr [rax+rax+00h]
0x18000699c  mov     [rdi+40h], r15
0x1800069a0  mov     [rsi], r14
0x1800069a3  mov     rbx, [rdi+40h]
0x1800069a7  test    rbx, rbx
0x1800069aa  jz      loc_180006ABD
0x1800069b0  mov     rdx, [rsi]; DestinationSize
0x1800069b3  lea     rsi, [rdx+rbx]
0x1800069b7  cmp     rbx, rsi
0x1800069ba  jz      short loc_180006A01
0x1800069bc  mov     r8, [r12+38h]; Source
0x1800069c1  test    r8, r8
0x1800069c4  jz      short loc_180006A01
0x1800069c6  cmp     [r8], r13b
0x1800069c9  jz      short loc_180006A01
0x1800069cb  mov     rax, rbp
0x1800069ce  inc     rax
0x1800069d1  cmp     [r8+rax], r13b
0x1800069d5  jnz     short loc_1800069CE
0x1800069d7  lea     r14, [rax+1]
0x1800069db  cmp     rdx, r14
0x1800069de  jnb     short loc_1800069E6
0x1800069e0  mov     [rdi+10h], r13
0x1800069e4  jmp     short loc_180006A0A
0x1800069e6  mov     r9, r14; SourceSize
0x1800069e9  mov     rcx, rbx; Destination
0x1800069ec  call    cs:__imp_memcpy_s
0x1800069f3  nop     dword ptr [rax+rax+00h]
0x1800069f8  mov     [rdi+10h], rbx
0x1800069fc  add     rbx, r14
0x1800069ff  jmp     short loc_180006A05
0x180006a01  mov     [rdi+10h], r13
0x180006a05  cmp     rbx, rsi
0x180006a08  jz      short loc_180006A58
0x180006a0a  mov     r8, [r12+80h]; Source
0x180006a12  test    r8, r8
0x180006a15  jz      short loc_180006A58
0x180006a17  cmp     [r8], r13b
0x180006a1a  jz      short loc_180006A58
0x180006a1c  mov     rax, rbp
0x180006a1f  inc     rax
0x180006a22  cmp     [r8+rax], r13b
0x180006a26  jnz     short loc_180006A1F
0x180006a28  mov     rdx, rsi
0x180006a2b  lea     r14, [rax+1]
0x180006a2f  sub     rdx, rbx; DestinationSize
0x180006a32  cmp     rdx, r14
0x180006a35  jnb     short loc_180006A3D
0x180006a37  mov     [rdi+20h], r13
0x180006a3b  jmp     short loc_180006A61
0x180006a3d  mov     r9, r14; SourceSize
0x180006a40  mov     rcx, rbx; Destination
0x180006a43  call    cs:__imp_memcpy_s
0x180006a4a  nop     dword ptr [rax+rax+00h]
0x180006a4f  mov     [rdi+20h], rbx
0x180006a53  add     rbx, r14
0x180006a56  jmp     short loc_180006A5C
0x180006a58  mov     [rdi+20h], r13
0x180006a5c  cmp     rbx, rsi
0x180006a5f  jz      short loc_180006AA9
0x180006a61  mov     r8, [r12+18h]; Source
0x180006a66  test    r8, r8
0x180006a69  jz      short loc_180006AA9
0x180006a6b  cmp     [r8], r13w
0x180006a6f  jz      short loc_180006AA9
0x180006a71  inc     rbp
0x180006a74  cmp     [r8+rbp*2], r13w
0x180006a79  jnz     short loc_180006A71
0x180006a7b  mov     rdx, rsi
0x180006a7e  lea     r14, ds:2[rbp*2]
0x180006a86  sub     rdx, rbx; DestinationSize
0x180006a89  cmp     rdx, r14
0x180006a8c  jb      short loc_180006AA9
0x180006a8e  mov     r9, r14; SourceSize
0x180006a91  mov     rcx, rbx; Destination
0x180006a94  call    cs:__imp_memcpy_s
0x180006a9b  nop     dword ptr [rax+rax+00h]
0x180006aa0  mov     [rdi+38h], rbx
0x180006aa4  add     rbx, r14
0x180006aa7  jmp     short loc_180006AAD
0x180006aa9  mov     [rdi+38h], r13
0x180006aad  sub     rsi, rbx
0x180006ab0  xor     edx, edx; Val
0x180006ab2  mov     r8, rsi; Size
0x180006ab5  mov     rcx, rbx; void *
0x180006ab8  call    memset_0
0x180006abd  add     rsp, 28h
0x180006ac1  pop     r15
0x180006ac3  pop     r14
0x180006ac5  pop     r13
0x180006ac7  pop     r12
0x180006ac9  pop     rdi
0x180006aca  pop     rsi
0x180006acb  pop     rbp
0x180006acc  pop     rbx
0x180006acd  retn
```
