# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010f0c`
- end: `0x18001107c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011084`

## callees

- `0x18000a182`
- `0x18000a19a`
- `0x18000f994`
- `0x180010c88`
- `0x180010e80`
- `0x180010ea0`
- `0x180010f0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fc2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x180010f0c  push    rbx
0x180010f0e  push    rbp
0x180010f0f  push    rsi
0x180010f10  push    rdi
0x180010f11  push    r12
0x180010f13  push    r13
0x180010f15  push    r14
0x180010f17  push    r15
0x180010f19  sub     rsp, 28h
0x180010f1d  mov     [rcx+4], r8d
0x180010f21  lea     rbx, [rcx+20h]
0x180010f25  mov     eax, [rdx+8]
0x180010f28  lea     rsi, [rcx+38h]
0x180010f2c  mov     [rcx+8], eax
0x180010f2f  xor     r12d, r12d
0x180010f32  mov     [rcx+10h], r12
0x180010f36  mov     rbp, rcx
0x180010f39  movzx   eax, word ptr [rdx+40h]
0x180010f3d  mov     r14, rdx
0x180010f40  mov     [rcx+18h], ax
0x180010f44  mov     al, [rdx]
0x180010f46  mov     [rcx+1Ah], al
0x180010f49  mov     [rbx], r12
0x180010f4c  mov     rax, [rdx+88h]
0x180010f53  mov     [rcx+28h], rax
0x180010f57  mov     rax, [rdx+90h]
0x180010f5e  mov     [rcx+30h], rax
0x180010f62  mov     [rsi], r12
0x180010f65  mov     rcx, [rdx+18h]; this
0x180010f69  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010f6e  mov     rcx, [r14+38h]; this
0x180010f72  mov     r15, rax
0x180010f75  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010f7a  mov     rcx, [r14+80h]; this
0x180010f81  add     r15, rax
0x180010f84  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010f89  add     r15, rax
0x180010f8c  lea     rdi, [rbp+48h]
0x180010f90  cmp     [rbp+40h], r12
0x180010f94  jz      short loc_180010F9B
0x180010f96  cmp     [rdi], r15
0x180010f99  jnb     short loc_180010FD6
0x180010f9b  mov     rdx, r15; dwBytes
0x180010f9e  mov     ecx, 8; dwFlags
0x180010fa3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010fa8  mov     r12, rax
0x180010fab  test    rax, rax
0x180010fae  jz      short loc_180010FD3
0x180010fb0  mov     rbx, [rbp+40h]
0x180010fb4  call    cs:__imp_GetProcessHeap
0x180010fba  mov     r8, rbx; lpMem
0x180010fbd  xor     edx, edx; dwFlags
0x180010fbf  mov     rcx, rax; hHeap
0x180010fc2  call    cs:__imp_HeapFree
0x180010fc8  mov     [rbp+40h], r12
0x180010fcc  lea     rbx, [rbp+20h]
0x180010fd0  mov     [rdi], r15
0x180010fd3  xor     r12d, r12d
0x180010fd6  mov     rcx, [rbp+40h]; Destination
0x180010fda  test    rcx, rcx
0x180010fdd  jz      loc_18001106B
0x180010fe3  mov     rdi, [rdi]
0x180010fe6  lea     r9, [rbp+10h]
0x180010fea  mov     r8, [r14+38h]
0x180010fee  add     rdi, rcx
0x180010ff1  mov     rdx, rdi
0x180010ff4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010ff9  mov     r8, [r14+80h]
0x180011000  mov     r9, rbx
0x180011003  mov     rdx, rdi
0x180011006  mov     rcx, rax; Destination
0x180011009  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001100e  mov     rbx, rax
0x180011011  cmp     rax, rdi
0x180011014  jz      short loc_180011053
0x180011016  mov     rcx, [r14+18h]; this
0x18001101a  test    rcx, rcx
0x18001101d  jz      short loc_180011053
0x18001101f  cmp     [rcx], r12w
0x180011023  jz      short loc_180011053
0x180011025  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001102a  mov     rdx, rdi
0x18001102d  mov     r14, rax
0x180011030  sub     rdx, rbx; DestinationSize
0x180011033  cmp     rdx, rax
0x180011036  jb      short loc_180011053
0x180011038  mov     r8, rcx; Source
0x18001103b  mov     r9, rax; SourceSize
0x18001103e  mov     rcx, rbx; Destination
0x180011041  call    memcpy_s
0x180011046  test    rsi, rsi
0x180011049  jz      short loc_18001104E
0x18001104b  mov     [rsi], rbx
0x18001104e  add     rbx, r14
0x180011051  jmp     short loc_18001105B
0x180011053  test    rsi, rsi
0x180011056  jz      short loc_18001105B
0x180011058  mov     [rsi], r12
0x18001105b  sub     rdi, rbx
0x18001105e  xor     edx, edx; Val
0x180011060  mov     r8, rdi; Size
0x180011063  mov     rcx, rbx; void *
0x180011066  call    memset_0
0x18001106b  add     rsp, 28h
0x18001106f  pop     r15
0x180011071  pop     r14
0x180011073  pop     r13
0x180011075  pop     r12
0x180011077  pop     rdi
0x180011078  pop     rsi
0x180011079  pop     rbp
0x18001107a  pop     rbx
0x18001107b  retn
```
