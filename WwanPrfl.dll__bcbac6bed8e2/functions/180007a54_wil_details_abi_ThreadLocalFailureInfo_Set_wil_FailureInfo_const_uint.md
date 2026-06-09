# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007a54`
- end: `0x180007c6d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d10`

## callees

- `0x180002034`
- `0x180005f68`
- `0x180007a54`
- `0x18000e674`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3c`

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
                memcpy_s_0(v20, v22 - v20, v29, 2 * v3 + 2);
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
          memcpy_s_0(v20, v22 - v20, v26, v27 + 1);
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
      memcpy_s_0(*((void *const *)this + 8), v21, v23, v24 + 1);
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
0x180007a54  push    rbx
0x180007a56  push    rbp
0x180007a57  push    rsi
0x180007a58  push    rdi
0x180007a59  push    r12
0x180007a5b  push    r13
0x180007a5d  push    r14
0x180007a5f  push    r15
0x180007a61  sub     rsp, 28h
0x180007a65  mov     [rcx+4], r8d
0x180007a69  xor     r13d, r13d
0x180007a6c  mov     eax, [rdx+8]
0x180007a6f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007a73  mov     [rcx+8], eax
0x180007a76  mov     rdi, rcx
0x180007a79  mov     [rcx+10h], r13
0x180007a7d  mov     r12, rdx
0x180007a80  movzx   eax, word ptr [rdx+40h]
0x180007a84  mov     [rcx+18h], ax
0x180007a88  mov     al, [rdx]
0x180007a8a  mov     [rcx+1Ah], al
0x180007a8d  mov     [rcx+20h], r13
0x180007a91  mov     rax, [rdx+88h]
0x180007a98  mov     [rcx+28h], rax
0x180007a9c  mov     rax, [rdx+90h]
0x180007aa3  mov     [rcx+30h], rax
0x180007aa7  mov     [rcx+38h], r13
0x180007aab  mov     rcx, [rdx+38h]
0x180007aaf  lea     edx, [rbp+2]
0x180007ab2  test    rcx, rcx
0x180007ab5  jnz     short loc_180007ABC
0x180007ab7  mov     r8d, edx
0x180007aba  jmp     short loc_180007ACC
0x180007abc  mov     rax, rbp
0x180007abf  inc     rax
0x180007ac2  cmp     [rcx+rax], r13b
0x180007ac6  jnz     short loc_180007ABF
0x180007ac8  lea     r8, [rax+1]; unsigned __int64
0x180007acc  mov     rcx, [r12+80h]
0x180007ad4  test    rcx, rcx
0x180007ad7  jz      short loc_180007AE9
0x180007ad9  mov     rax, rbp
0x180007adc  inc     rax
0x180007adf  cmp     [rcx+rax], r13b
0x180007ae3  jnz     short loc_180007ADC
0x180007ae5  lea     rdx, [rax+1]
0x180007ae9  mov     rcx, [r12+18h]
0x180007aee  test    rcx, rcx
0x180007af1  jnz     short loc_180007AF8
0x180007af3  lea     eax, [rcx+2]
0x180007af6  jmp     short loc_180007B0D
0x180007af8  mov     rax, rbp
0x180007afb  inc     rax
0x180007afe  cmp     [rcx+rax*2], r13w
0x180007b03  jnz     short loc_180007AFB
0x180007b05  lea     rax, ds:2[rax*2]
0x180007b0d  lea     r14, [rdx+rax]
0x180007b11  add     r14, r8
0x180007b14  lea     rsi, [rdi+48h]
0x180007b18  cmp     [rdi+40h], r13
0x180007b1c  jz      short loc_180007B23
0x180007b1e  cmp     [rsi], r14
0x180007b21  jnb     short loc_180007B57
0x180007b23  mov     rdx, r14; dwBytes
0x180007b26  mov     ecx, 8; dwFlags
0x180007b2b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007b30  mov     r15, rax
0x180007b33  test    rax, rax
0x180007b36  jz      short loc_180007B57
0x180007b38  mov     rbx, [rdi+40h]
0x180007b3c  call    cs:__imp_GetProcessHeap
0x180007b42  mov     r8, rbx; lpMem
0x180007b45  xor     edx, edx; dwFlags
0x180007b47  mov     rcx, rax; hHeap
0x180007b4a  call    cs:__imp_HeapFree
0x180007b50  mov     [rdi+40h], r15
0x180007b54  mov     [rsi], r14
0x180007b57  mov     rbx, [rdi+40h]
0x180007b5b  test    rbx, rbx
0x180007b5e  jz      loc_180007C5C
0x180007b64  mov     rdx, [rsi]; DestinationSize
0x180007b67  lea     rsi, [rdx+rbx]
0x180007b6b  cmp     rbx, rsi
0x180007b6e  jz      short loc_180007BAE
0x180007b70  mov     r8, [r12+38h]; Source
0x180007b75  test    r8, r8
0x180007b78  jz      short loc_180007BAE
0x180007b7a  cmp     [r8], r13b
0x180007b7d  jz      short loc_180007BAE
0x180007b7f  mov     rax, rbp
0x180007b82  inc     rax
0x180007b85  cmp     [r8+rax], r13b
0x180007b89  jnz     short loc_180007B82
0x180007b8b  lea     r14, [rax+1]
0x180007b8f  cmp     rdx, r14
0x180007b92  jnb     short loc_180007B9A
0x180007b94  mov     [rdi+10h], r13
0x180007b98  jmp     short loc_180007BB7
0x180007b9a  mov     r9, r14; SourceSize
0x180007b9d  mov     rcx, rbx; Destination
0x180007ba0  call    memcpy_s_0
0x180007ba5  mov     [rdi+10h], rbx
0x180007ba9  add     rbx, r14
0x180007bac  jmp     short loc_180007BB2
0x180007bae  mov     [rdi+10h], r13
0x180007bb2  cmp     rbx, rsi
0x180007bb5  jz      short loc_180007BFE
0x180007bb7  mov     r8, [r12+80h]; Source
0x180007bbf  test    r8, r8
0x180007bc2  jz      short loc_180007BFE
0x180007bc4  cmp     [r8], r13b
0x180007bc7  jz      short loc_180007BFE
0x180007bc9  mov     rax, rbp
0x180007bcc  inc     rax
0x180007bcf  cmp     [r8+rax], r13b
0x180007bd3  jnz     short loc_180007BCC
0x180007bd5  mov     rdx, rsi
0x180007bd8  lea     r14, [rax+1]
0x180007bdc  sub     rdx, rbx; DestinationSize
0x180007bdf  cmp     rdx, r14
0x180007be2  jnb     short loc_180007BEA
0x180007be4  mov     [rdi+20h], r13
0x180007be8  jmp     short loc_180007C07
0x180007bea  mov     r9, r14; SourceSize
0x180007bed  mov     rcx, rbx; Destination
0x180007bf0  call    memcpy_s_0
0x180007bf5  mov     [rdi+20h], rbx
0x180007bf9  add     rbx, r14
0x180007bfc  jmp     short loc_180007C02
0x180007bfe  mov     [rdi+20h], r13
0x180007c02  cmp     rbx, rsi
0x180007c05  jz      short loc_180007C48
0x180007c07  mov     r8, [r12+18h]; Source
0x180007c0c  test    r8, r8
0x180007c0f  jz      short loc_180007C48
0x180007c11  cmp     [r8], r13w
0x180007c15  jz      short loc_180007C48
0x180007c17  inc     rbp
0x180007c1a  cmp     [r8+rbp*2], r13w
0x180007c1f  jnz     short loc_180007C17
0x180007c21  mov     rdx, rsi
0x180007c24  lea     r14, ds:2[rbp*2]
0x180007c2c  sub     rdx, rbx; DestinationSize
0x180007c2f  cmp     rdx, r14
0x180007c32  jb      short loc_180007C48
0x180007c34  mov     r9, r14; SourceSize
0x180007c37  mov     rcx, rbx; Destination
0x180007c3a  call    memcpy_s_0
0x180007c3f  mov     [rdi+38h], rbx
0x180007c43  add     rbx, r14
0x180007c46  jmp     short loc_180007C4C
0x180007c48  mov     [rdi+38h], r13
0x180007c4c  sub     rsi, rbx
0x180007c4f  xor     edx, edx; Val
0x180007c51  mov     r8, rsi; Size
0x180007c54  mov     rcx, rbx; void *
0x180007c57  call    memset_0
0x180007c5c  add     rsp, 28h
0x180007c60  pop     r15
0x180007c62  pop     r14
0x180007c64  pop     r13
0x180007c66  pop     r12
0x180007c68  pop     rdi
0x180007c69  pop     rsi
0x180007c6a  pop     rbp
0x180007c6b  pop     rbx
0x180007c6c  retn
```
