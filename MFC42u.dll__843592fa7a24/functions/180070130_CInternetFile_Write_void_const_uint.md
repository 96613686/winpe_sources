# CInternetFile::Write(void const *,uint)

- ea: `0x180070130`
- end: `0x180070241`
- name: `?Write@CInternetFile@@UEAAXPEBXI@Z`
- size: `273`
- prototype: `void(CInternetFile *__hidden this, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18006dd90`
- `0x180070130`
- `0x1800d1f7a`

## import_xrefs

- `WININET!InternetWriteFile` at `0x18007017d`
- `WININET!InternetWriteFile` at `0x1800701bf`
- `WININET!InternetWriteFile` at `0x1800701f2`
- `WININET!InternetWriteFile` at `0x18007017d`
- `WININET!InternetWriteFile` at `0x1800701bf`
- `WININET!InternetWriteFile` at `0x1800701f2`

## pseudocode

```c
void __fastcall CInternetFile::Write(CInternetFile *this, const void *a2, DWORD a3)
{
  size_t v4; // rdi
  void *v6; // r10
  const void *v7; // rdx
  __int64 v8; // rcx
  DWORD dwNumberOfBytesWritten; // [rsp+30h] [rbp+8h] BYREF

  v4 = a3;
  if ( *((_DWORD *)this + 12) == 1 || (v6 = (void *)*((_QWORD *)this + 5)) == 0 )
    AfxThrowInternetException(*((_QWORD *)this + 7), 6u);
  v7 = (const void *)*((_QWORD *)this + 11);
  dwNumberOfBytesWritten = 0;
  if ( v7 )
  {
    v8 = *((unsigned int *)this + 21);
    if ( (unsigned int)v8 + a3 >= *((_DWORD *)this + 20) )
    {
      if ( !InternetWriteFile(v6, v7, v8, &dwNumberOfBytesWritten) )
        AfxThrowInternetException(*((_QWORD *)this + 7), 0);
      *((_DWORD *)this + 21) = 0;
      v8 = 0;
    }
    if ( (unsigned int)v4 < *((_DWORD *)this + 20) )
    {
      if ( (unsigned int)(v8 + v4) <= *((_DWORD *)this + 20) )
      {
        memcpy_0((void *)(*((_QWORD *)this + 11) + v8), a2, v4);
        *((_DWORD *)this + 21) += v4;
      }
    }
    else if ( !InternetWriteFile(*((HINTERNET *)this + 5), a2, v4, &dwNumberOfBytesWritten) )
    {
      AfxThrowInternetException(*((_QWORD *)this + 7), 0);
    }
  }
  else
  {
    if ( !InternetWriteFile(v6, a2, a3, &dwNumberOfBytesWritten) )
      AfxThrowInternetException(*((_QWORD *)this + 7), 0);
    if ( dwNumberOfBytesWritten != (_DWORD)v4 )
      AfxThrowInternetException(*((_QWORD *)this + 7), 0);
  }
}

```

## disassembly

```asm
0x180070130  mov     rax, rsp
0x180070133  mov     [rax+10h], rbx
0x180070137  mov     [rax+18h], rsi
0x18007013b  push    rdi
0x18007013c  sub     rsp, 20h
0x180070140  cmp     dword ptr [rcx+30h], 1
0x180070144  mov     rsi, rdx
0x180070147  mov     edi, r8d
0x18007014a  mov     rbx, rcx
0x18007014d  jz      loc_180070232
0x180070153  mov     r10, [rcx+28h]
0x180070157  test    r10, r10
0x18007015a  jz      loc_180070232
0x180070160  mov     rdx, [rcx+58h]; lpBuffer
0x180070164  mov     dword ptr [rax+8], 0
0x18007016b  test    rdx, rdx
0x18007016e  jnz     short loc_1800701A9
0x180070170  lea     r9, [rax+8]; lpdwNumberOfBytesWritten
0x180070174  mov     r8d, edi; dwNumberOfBytesToWrite
0x180070177  mov     rdx, rsi; lpBuffer
0x18007017a  mov     rcx, r10; hFile
0x18007017d  call    cs:__imp_InternetWriteFile
0x180070183  test    eax, eax
0x180070185  jnz     short loc_180070193
0x180070187  mov     rcx, [rbx+38h]; unsigned __int64
0x18007018b  xor     edx, edx; unsigned int
0x18007018d  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x180070193  cmp     [rsp+28h+dwNumberOfBytesWritten], edi
0x180070197  jz      loc_180070222
0x18007019d  mov     rcx, [rbx+38h]; unsigned __int64
0x1800701a1  xor     edx, edx; unsigned int
0x1800701a3  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x1800701a9  mov     ecx, [rcx+54h]
0x1800701ac  lea     eax, [rcx+rdi]
0x1800701af  cmp     eax, [rbx+50h]
0x1800701b2  jb      short loc_1800701DE
0x1800701b4  mov     r8d, ecx; dwNumberOfBytesToWrite
0x1800701b7  lea     r9, [rsp+28h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x1800701bc  mov     rcx, r10; hFile
0x1800701bf  call    cs:__imp_InternetWriteFile
0x1800701c5  test    eax, eax
0x1800701c7  jnz     short loc_1800701D5
0x1800701c9  mov     rcx, [rbx+38h]; unsigned __int64
0x1800701cd  xor     edx, edx; unsigned int
0x1800701cf  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x1800701d5  mov     dword ptr [rbx+54h], 0
0x1800701dc  xor     ecx, ecx
0x1800701de  cmp     edi, [rbx+50h]
0x1800701e1  jb      short loc_180070208
0x1800701e3  mov     rcx, [rbx+28h]; hFile
0x1800701e7  lea     r9, [rsp+28h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x1800701ec  mov     r8d, edi; dwNumberOfBytesToWrite
0x1800701ef  mov     rdx, rsi; lpBuffer
0x1800701f2  call    cs:__imp_InternetWriteFile
0x1800701f8  test    eax, eax
0x1800701fa  jnz     short loc_180070222
0x1800701fc  mov     rcx, [rbx+38h]; unsigned __int64
0x180070200  xor     edx, edx; unsigned int
0x180070202  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x180070208  lea     eax, [rcx+rdi]
0x18007020b  cmp     eax, [rbx+50h]
0x18007020e  ja      short loc_180070222
0x180070210  add     rcx, [rbx+58h]; void *
0x180070214  mov     r8, rdi; Size
0x180070217  mov     rdx, rsi; Src
0x18007021a  call    memcpy_0
0x18007021f  add     [rbx+54h], edi
0x180070222  mov     rbx, [rsp+28h+arg_8]
0x180070227  mov     rsi, [rsp+28h+arg_10]
0x18007022c  add     rsp, 20h
0x180070230  pop     rdi
0x180070231  retn
0x180070232  mov     rcx, [rcx+38h]; unsigned __int64
0x180070236  mov     edx, 6; unsigned int
0x18007023b  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
```
