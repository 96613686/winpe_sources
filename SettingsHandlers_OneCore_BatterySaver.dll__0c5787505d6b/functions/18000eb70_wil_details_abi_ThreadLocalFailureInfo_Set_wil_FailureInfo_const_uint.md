# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000eb70`
- end: `0x18000eca6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000eff4`

## callees

- `0x180009cf0`
- `0x18000ad54`
- `0x18000adcc`
- `0x18000db6c`
- `0x18000e9e8`
- `0x18000ea08`
- `0x18000eb70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec1f`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18000eb70  push    rbx
0x18000eb72  push    rbp
0x18000eb73  push    rsi
0x18000eb74  push    rdi
0x18000eb75  push    r12
0x18000eb77  push    r13
0x18000eb79  push    r14
0x18000eb7b  push    r15
0x18000eb7d  sub     rsp, 28h
0x18000eb81  mov     [rcx+4], r8d
0x18000eb85  lea     r14, [rcx+38h]
0x18000eb89  mov     eax, [rdx+8]
0x18000eb8c  mov     rsi, rcx
0x18000eb8f  mov     [rcx+8], eax
0x18000eb92  mov     r15, rdx
0x18000eb95  mov     qword ptr [rcx+10h], 0
0x18000eb9d  movzx   eax, word ptr [rdx+40h]
0x18000eba1  mov     [rcx+18h], ax
0x18000eba5  mov     al, [rdx]
0x18000eba7  mov     [rcx+1Ah], al
0x18000ebaa  mov     qword ptr [rcx+20h], 0
0x18000ebb2  mov     rax, [rdx+88h]
0x18000ebb9  mov     [rcx+28h], rax
0x18000ebbd  mov     rax, [rdx+90h]
0x18000ebc4  mov     [rcx+30h], rax
0x18000ebc8  mov     qword ptr [r14], 0
0x18000ebcf  mov     rcx, [rdx+18h]; this
0x18000ebd3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000ebd8  mov     rcx, [r15+38h]; this
0x18000ebdc  mov     rbp, rax
0x18000ebdf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ebe4  mov     rcx, [r15+80h]; this
0x18000ebeb  add     rbp, rax
0x18000ebee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ebf3  add     rbp, rax
0x18000ebf6  lea     rdi, [rsi+48h]
0x18000ebfa  cmp     qword ptr [rsi+40h], 0
0x18000ebff  jz      short loc_18000EC06
0x18000ec01  cmp     [rdi], rbp
0x18000ec04  jnb     short loc_18000EC3E
0x18000ec06  mov     rdx, rbp; dwBytes
0x18000ec09  mov     ecx, 8; dwFlags
0x18000ec0e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ec13  mov     r14, rax
0x18000ec16  test    rax, rax
0x18000ec19  jz      short loc_18000EC3A
0x18000ec1b  mov     rbx, [rsi+40h]
0x18000ec1f  call    cs:__imp_GetProcessHeap
0x18000ec25  mov     r8, rbx; lpMem
0x18000ec28  xor     edx, edx; dwFlags
0x18000ec2a  mov     rcx, rax; hHeap
0x18000ec2d  call    cs:__imp_HeapFree
0x18000ec33  mov     [rsi+40h], r14
0x18000ec37  mov     [rdi], rbp
0x18000ec3a  lea     r14, [rsi+38h]
0x18000ec3e  mov     rcx, [rsi+40h]; Destination
0x18000ec42  test    rcx, rcx
0x18000ec45  jz      short loc_18000EC95
0x18000ec47  mov     rbx, [rdi]
0x18000ec4a  lea     r9, [rsi+10h]
0x18000ec4e  mov     r8, [r15+38h]
0x18000ec52  add     rbx, rcx
0x18000ec55  mov     rdx, rbx
0x18000ec58  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ec5d  mov     r8, [r15+80h]
0x18000ec64  lea     r9, [rsi+20h]
0x18000ec68  mov     rdx, rbx
0x18000ec6b  mov     rcx, rax; Destination
0x18000ec6e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ec73  mov     r8, [r15+18h]
0x18000ec77  mov     r9, r14
0x18000ec7a  mov     rdx, rbx
0x18000ec7d  mov     rcx, rax; Destination
0x18000ec80  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000ec85  sub     rbx, rax
0x18000ec88  xor     edx, edx; Val
0x18000ec8a  mov     r8, rbx; Size
0x18000ec8d  mov     rcx, rax; void *
0x18000ec90  call    memset_0
0x18000ec95  add     rsp, 28h
0x18000ec99  pop     r15
0x18000ec9b  pop     r14
0x18000ec9d  pop     r13
0x18000ec9f  pop     r12
0x18000eca1  pop     rdi
0x18000eca2  pop     rsi
0x18000eca3  pop     rbp
0x18000eca4  pop     rbx
0x18000eca5  retn
```
