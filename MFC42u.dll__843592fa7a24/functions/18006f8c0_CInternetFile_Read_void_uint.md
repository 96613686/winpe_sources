# CInternetFile::Read(void *,uint)

- ea: `0x18006f8c0`
- end: `0x18006fa4e`
- name: `?Read@CInternetFile@@UEAAIPEAXI@Z`
- size: `398`
- prototype: `unsigned int(CInternetFile *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18006dd90`
- `0x18006f8c0`
- `0x1800d1f7a`

## import_xrefs

- `WININET!InternetReadFile` at `0x18006f909`
- `WININET!InternetReadFile` at `0x18006f97b`
- `WININET!InternetReadFile` at `0x18006f9de`
- `WININET!InternetReadFile` at `0x18006f909`
- `WININET!InternetReadFile` at `0x18006f97b`
- `WININET!InternetReadFile` at `0x18006f9de`

## pseudocode

```c
__int64 __fastcall CInternetFile::Read(CInternetFile *this, char *a2, DWORD a3)
{
  bool v3; // zf
  DWORD v5; // esi
  void *v7; // rcx
  __int64 v8; // r9
  __int64 v10; // r14
  void *v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // ebp
  __int64 v14; // rbp
  DWORD v15; // r8d
  void *v16; // rdx
  void *v17; // rcx
  DWORD v18; // eax
  const void *v19; // rdx
  DWORD v20; // esi
  bool v21; // cf
  DWORD v22; // ebx
  DWORD dwNumberOfBytesRead; // [rsp+50h] [rbp+8h] BYREF
  DWORD v24; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 12) == 0;
  v5 = a3;
  dwNumberOfBytesRead = 0;
  if ( v3 || (v7 = (void *)*((_QWORD *)this + 5)) == 0 )
    AfxThrowInternetException(*((_QWORD *)this + 7), 6u);
  v8 = *((_QWORD *)this + 13);
  if ( v8 )
  {
    if ( a3 >= *((_DWORD *)this + 24) )
    {
      v10 = (unsigned int)(*((_DWORD *)this + 28) - *((_DWORD *)this + 25));
      if ( (int)v10 < 0 )
      {
        v10 = 0;
LABEL_11:
        memcpy_0(a2, (const void *)(v8 + *((unsigned int *)this + 25)), (unsigned int)v10);
        v11 = (void *)*((_QWORD *)this + 5);
        *((_DWORD *)this + 25) = *((_DWORD *)this + 24);
        if ( !InternetReadFile(v11, &a2[v10], v5 - v10, &dwNumberOfBytesRead) )
          AfxThrowInternetException(*((_QWORD *)this + 7), 0);
        return (unsigned int)v10 + dwNumberOfBytesRead;
      }
      if ( (unsigned int)v10 <= a3 )
        goto LABEL_11;
      return 0;
    }
    v12 = *((unsigned int *)this + 25);
    v13 = *((_DWORD *)this + 28);
    if ( (unsigned int)v12 + a3 < v13 )
    {
      memcpy_0(a2, (const void *)(v8 + v12), a3);
      *((_DWORD *)this + 25) += v5;
      return v5;
    }
    v14 = v13 - (unsigned int)v12;
    if ( (int)v14 >= 0 )
    {
      if ( (unsigned int)v14 > a3 )
        return 0;
    }
    else
    {
      v14 = 0;
    }
    memcpy_0(a2, (const void *)(v8 + v12), (unsigned int)v14);
    v15 = *((_DWORD *)this + 24);
    v16 = (void *)*((_QWORD *)this + 13);
    v17 = (void *)*((_QWORD *)this + 5);
    v24 = 0;
    if ( !InternetReadFile(v17, v16, v15, &v24) )
      AfxThrowInternetException(*((_QWORD *)this + 7), 0);
    v18 = v24;
    v19 = (const void *)*((_QWORD *)this + 13);
    v20 = v5 - v14;
    v21 = v20 < v24;
    *((_DWORD *)this + 28) = v24;
    if ( !v21 )
      v20 = v18;
    v22 = v20;
    v24 = v20;
    memcpy_0(&a2[v14], v19, v20);
    v5 = v14 + v20;
    *((_DWORD *)this + 25) = v22;
    return v5;
  }
  if ( !InternetReadFile(v7, a2, a3, &dwNumberOfBytesRead) )
    AfxThrowInternetException(*((_QWORD *)this + 7), 0);
  return dwNumberOfBytesRead;
}

```

## disassembly

```asm
0x18006f8c0  mov     [rsp+arg_8], rbx
0x18006f8c5  push    rbp
0x18006f8c6  push    rsi
0x18006f8c7  push    rdi
0x18006f8c8  push    r14
0x18006f8ca  push    r15
0x18006f8cc  sub     rsp, 20h
0x18006f8d0  cmp     dword ptr [rcx+30h], 0
0x18006f8d4  mov     r15, rdx
0x18006f8d7  mov     esi, r8d
0x18006f8da  mov     rdi, rcx
0x18006f8dd  mov     [rsp+48h+dwNumberOfBytesRead], 0
0x18006f8e5  jz      loc_18006FA3F
0x18006f8eb  mov     rcx, [rcx+28h]; hFile
0x18006f8ef  test    rcx, rcx
0x18006f8f2  jz      loc_18006FA3F
0x18006f8f8  mov     r9, [rdi+68h]
0x18006f8fc  test    r9, r9
0x18006f8ff  jnz     short loc_18006F934
0x18006f901  lea     r9, [rsp+48h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18006f906  mov     r8d, esi; dwNumberOfBytesToRead
0x18006f909  call    cs:__imp_InternetReadFile
0x18006f90f  test    eax, eax
0x18006f911  jnz     short loc_18006F91F
0x18006f913  mov     rcx, [rdi+38h]; unsigned __int64
0x18006f917  xor     edx, edx; unsigned int
0x18006f919  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x18006f91f  mov     eax, [rsp+48h+dwNumberOfBytesRead]
0x18006f923  mov     rbx, [rsp+48h+arg_8]
0x18006f928  add     rsp, 20h
0x18006f92c  pop     r15
0x18006f92e  pop     r14
0x18006f930  pop     rdi
0x18006f931  pop     rsi
0x18006f932  pop     rbp
0x18006f933  retn
0x18006f934  cmp     esi, [rdi+60h]
0x18006f937  jb      short loc_18006F99D
0x18006f939  mov     r14d, [rdi+70h]
0x18006f93d  sub     r14d, [rdi+64h]
0x18006f941  jns     short loc_18006F948
0x18006f943  xor     r14d, r14d
0x18006f946  jmp     short loc_18006F951
0x18006f948  cmp     r14d, esi
0x18006f94b  ja      loc_18006FA1F
0x18006f951  mov     edx, [rdi+64h]
0x18006f954  mov     rcx, r15; void *
0x18006f957  add     rdx, r9; Src
0x18006f95a  mov     r8d, r14d; Size
0x18006f95d  call    memcpy_0
0x18006f962  mov     eax, [rdi+60h]
0x18006f965  lea     rdx, [r14+r15]; lpBuffer
0x18006f969  mov     rcx, [rdi+28h]; hFile
0x18006f96d  lea     r9, [rsp+48h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18006f972  sub     esi, r14d
0x18006f975  mov     [rdi+64h], eax
0x18006f978  mov     r8d, esi; dwNumberOfBytesToRead
0x18006f97b  call    cs:__imp_InternetReadFile
0x18006f981  test    eax, eax
0x18006f983  jnz     short loc_18006F991
0x18006f985  mov     rcx, [rdi+38h]; unsigned __int64
0x18006f989  xor     edx, edx; unsigned int
0x18006f98b  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x18006f991  mov     esi, [rsp+48h+dwNumberOfBytesRead]
0x18006f995  add     esi, r14d
0x18006f998  jmp     loc_18006FA38
0x18006f99d  mov     ecx, [rdi+64h]
0x18006f9a0  mov     ebp, [rdi+70h]
0x18006f9a3  lea     eax, [rcx+rsi]
0x18006f9a6  cmp     eax, ebp
0x18006f9a8  jb      short loc_18006FA26
0x18006f9aa  sub     ebp, ecx
0x18006f9ac  jns     short loc_18006F9B2
0x18006f9ae  xor     ebp, ebp
0x18006f9b0  jmp     short loc_18006F9B6
0x18006f9b2  cmp     ebp, esi
0x18006f9b4  ja      short loc_18006FA1F
0x18006f9b6  lea     rdx, [r9+rcx]; Src
0x18006f9ba  mov     r8d, ebp; Size
0x18006f9bd  mov     rcx, r15; void *
0x18006f9c0  call    memcpy_0
0x18006f9c5  mov     r8d, [rdi+60h]; dwNumberOfBytesToRead
0x18006f9c9  lea     r9, [rsp+48h+arg_18]; lpdwNumberOfBytesRead
0x18006f9ce  mov     rdx, [rdi+68h]; lpBuffer
0x18006f9d2  mov     rcx, [rdi+28h]; hFile
0x18006f9d6  mov     [rsp+48h+arg_18], 0
0x18006f9de  call    cs:__imp_InternetReadFile
0x18006f9e4  test    eax, eax
0x18006f9e6  jnz     short loc_18006F9F4
0x18006f9e8  mov     rcx, [rdi+38h]; unsigned __int64
0x18006f9ec  xor     edx, edx; unsigned int
0x18006f9ee  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x18006f9f4  mov     eax, [rsp+48h+arg_18]
0x18006f9f8  lea     rcx, [r15+rbp]; void *
0x18006f9fc  mov     rdx, [rdi+68h]; Src
0x18006fa00  sub     esi, ebp
0x18006fa02  cmp     esi, eax
0x18006fa04  mov     [rdi+70h], eax
0x18006fa07  cmovnb  esi, eax
0x18006fa0a  mov     ebx, esi
0x18006fa0c  mov     r8d, esi; Size
0x18006fa0f  mov     [rsp+48h+arg_18], ebx
0x18006fa13  call    memcpy_0
0x18006fa18  add     esi, ebp
0x18006fa1a  mov     [rdi+64h], ebx
0x18006fa1d  jmp     short loc_18006FA38
0x18006fa1f  xor     eax, eax
0x18006fa21  jmp     loc_18006F923
0x18006fa26  lea     rdx, [r9+rcx]; Src
0x18006fa2a  mov     r8, rsi; Size
0x18006fa2d  mov     rcx, r15; void *
0x18006fa30  call    memcpy_0
0x18006fa35  add     [rdi+64h], esi
0x18006fa38  mov     eax, esi
0x18006fa3a  jmp     loc_18006F923
0x18006fa3f  mov     rcx, [rdi+38h]; unsigned __int64
0x18006fa43  mov     edx, 6; unsigned int
0x18006fa48  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
```
