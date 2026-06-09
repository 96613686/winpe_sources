# TiffCreate

- ea: `0x180038b68`
- end: `0x180038d3f`
- name: `TiffCreate`
- size: `471`
- prototype: `char *__fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180035d78`

## callees

- `0x18000abe4`
- `0x18002bab8`
- `0x18002bb58`
- `0x180038b68`
- `0x18003d4ca`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180038d18`
- `KERNEL32!DeleteFileW` at `0x180038d18`
- `KERNEL32!WriteFile` at `0x180038cf7`
- `KERNEL32!WriteFile` at `0x180038cf7`
- `KERNEL32!CloseHandle` at `0x180038d0a`
- `KERNEL32!CloseHandle` at `0x180038d0a`

## pseudocode

```c
char *__fastcall TiffCreate(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rsi
  char *v5; // rax
  char *v6; // rdi
  _OWORD *v8; // rcx
  __int64 *v9; // rax
  __int128 v10; // xmm1
  bool v11; // zf
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  v4 = 2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
  }
  v5 = (char *)pMemAlloc(0x6A0u);
  v6 = v5;
  if ( !v5 )
    return 0;
  memset_0(v5, 0, 0x6A0u);
  *((_DWORD *)v6 + 391) = a3;
  *(_QWORD *)v6 = -1;
  *((_DWORD *)v6 + 211) = 4;
  *((_DWORD *)v6 + 213) = 4;
  *((_WORD *)v6 + 282) = 18761;
  *((_WORD *)v6 + 283) = 42;
  *((_DWORD *)v6 + 6) = 0;
  *((_DWORD *)v6 + 395) = 0;
  *((_DWORD *)v6 + 396) = 32;
  *((_DWORD *)v6 + 407) = 1;
  *((_DWORD *)v6 + 421) = 196;
  memset_0(v6 + 860, 0, 0x288u);
  *((_QWORD *)v6 + 190) = v6 + 860;
  *((_QWORD *)v6 + 189) = v6 + 1076;
  v8 = v6 + 572;
  *((_QWORD *)v6 + 199) = v6 + 1076;
  v9 = gc_FaxIFDTemplate;
  do
  {
    *v8 = *(_OWORD *)v9;
    v8[1] = *((_OWORD *)v9 + 1);
    v8[2] = *((_OWORD *)v9 + 2);
    v8[3] = *((_OWORD *)v9 + 3);
    v8[4] = *((_OWORD *)v9 + 4);
    v8[5] = *((_OWORD *)v9 + 5);
    v8[6] = *((_OWORD *)v9 + 6);
    v10 = *((_OWORD *)v9 + 7);
    v9 += 16;
    v8[7] = v10;
    v8 += 8;
    --v4;
  }
  while ( v4 );
  v11 = *(_QWORD *)v6 == -1;
  *(_QWORD *)((char *)v8 - 2) = *(__int64 *)((char *)v9 - 2);
  if ( !v11 && !WriteFile(*(HANDLE *)v6, v6 + 564, 8u, &NumberOfBytesWritten, 0) )
  {
    CloseHandle(*(HANDLE *)v6);
    DeleteFileW(0);
    pMemFree(v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180038b68  mov     [rsp+NumberOfBytesWritten], r9d
0x180038b6d  push    rbx
0x180038b6e  push    rsi
0x180038b6f  push    rdi
0x180038b70  push    r14
0x180038b72  sub     rsp, 38h
0x180038b76  mov     ebx, r8d
0x180038b79  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180038b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b88  lea     rax, WPP_GLOBAL_Control
0x180038b8f  mov     esi, 2
0x180038b94  cmp     rcx, rax
0x180038b97  jz      short loc_180038BB8
0x180038b99  test    [rcx+1Ch], sil
0x180038b9d  jz      short loc_180038BB8
0x180038b9f  cmp     byte ptr [rcx+19h], 5
0x180038ba3  jb      short loc_180038BB8
0x180038ba5  mov     rcx, [rcx+10h]
0x180038ba9  lea     edx, [rsi+8]
0x180038bac  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180038bb3  call    WPP_SF_
0x180038bb8  mov     r14d, 6A0h
0x180038bbe  mov     ecx, r14d; dwBytes
0x180038bc1  call    pMemAlloc
0x180038bc6  mov     rdi, rax
0x180038bc9  test    rax, rax
0x180038bcc  jnz     short loc_180038BD5
0x180038bce  xor     eax, eax
0x180038bd0  jmp     loc_180038D34
0x180038bd5  mov     r8, r14; Size
0x180038bd8  xor     edx, edx; Val
0x180038bda  mov     rcx, rdi; void *
0x180038bdd  call    memset_0
0x180038be2  mov     [rdi+61Ch], ebx
0x180038be8  lea     r14, [rdi+234h]
0x180038bef  mov     eax, 4
0x180038bf4  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180038bfb  mov     [rdi+34Ch], eax
0x180038c01  lea     rbx, [rdi+35Ch]
0x180038c08  mov     [rdi+354h], eax
0x180038c0e  mov     rcx, rbx; void *
0x180038c11  mov     word ptr [r14], 4949h
0x180038c17  xor     edx, edx; Val
0x180038c19  mov     word ptr [rdi+236h], 2Ah ; '*'
0x180038c22  mov     r8d, 288h; Size
0x180038c28  mov     dword ptr [rdi+18h], 0
0x180038c2f  mov     dword ptr [rdi+62Ch], 0
0x180038c39  mov     dword ptr [rdi+630h], 20h ; ' '
0x180038c43  mov     dword ptr [rdi+65Ch], 1
0x180038c4d  mov     dword ptr [rdi+694h], 0C4h
0x180038c57  call    memset_0
0x180038c5c  lea     rax, [rbx+0D8h]
0x180038c63  mov     [rdi+5F0h], rbx
0x180038c6a  mov     [rdi+5E8h], rax
0x180038c71  lea     rcx, [rdi+23Ch]
0x180038c78  mov     [rdi+638h], rax
0x180038c7f  mov     edx, 80h
0x180038c84  lea     rax, gc_FaxIFDTemplate
0x180038c8b  movups  xmm0, xmmword ptr [rax]
0x180038c8e  movups  xmmword ptr [rcx], xmm0
0x180038c91  movups  xmm1, xmmword ptr [rax+10h]
0x180038c95  movups  xmmword ptr [rcx+10h], xmm1
0x180038c99  movups  xmm0, xmmword ptr [rax+20h]
0x180038c9d  movups  xmmword ptr [rcx+20h], xmm0
0x180038ca1  movups  xmm1, xmmword ptr [rax+30h]
0x180038ca5  movups  xmmword ptr [rcx+30h], xmm1
0x180038ca9  movups  xmm0, xmmword ptr [rax+40h]
0x180038cad  movups  xmmword ptr [rcx+40h], xmm0
0x180038cb1  movups  xmm1, xmmword ptr [rax+50h]
0x180038cb5  movups  xmmword ptr [rcx+50h], xmm1
0x180038cb9  movups  xmm0, xmmword ptr [rax+60h]
0x180038cbd  movups  xmmword ptr [rcx+60h], xmm0
0x180038cc1  movups  xmm1, xmmword ptr [rax+70h]
0x180038cc5  add     rax, rdx
0x180038cc8  movups  xmmword ptr [rcx+70h], xmm1
0x180038ccc  add     rcx, rdx
0x180038ccf  sub     rsi, 1
0x180038cd3  jnz     short loc_180038C8B
0x180038cd5  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180038cd9  mov     rax, [rax-2]
0x180038cdd  mov     [rcx-2], rax
0x180038ce1  jz      short loc_180038D31
0x180038ce3  mov     rcx, [rdi]; hFile
0x180038ce6  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180038ceb  lea     r8d, [rsi+8]; nNumberOfBytesToWrite
0x180038cef  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x180038cf4  mov     rdx, r14; lpBuffer
0x180038cf7  call    cs:__imp_WriteFile
0x180038cfe  nop     dword ptr [rax+rax+00h]
0x180038d03  test    eax, eax
0x180038d05  jnz     short loc_180038D31
0x180038d07  mov     rcx, [rdi]; hObject
0x180038d0a  call    cs:__imp_CloseHandle
0x180038d11  nop     dword ptr [rax+rax+00h]
0x180038d16  xor     ecx, ecx; lpFileName
0x180038d18  call    cs:__imp_DeleteFileW
0x180038d1f  nop     dword ptr [rax+rax+00h]
0x180038d24  mov     rcx, rdi; lpMem
0x180038d27  call    pMemFree
0x180038d2c  jmp     loc_180038BCE
0x180038d31  mov     rax, rdi
0x180038d34  add     rsp, 38h
0x180038d38  pop     r14
0x180038d3a  pop     rdi
0x180038d3b  pop     rsi
0x180038d3c  pop     rbx
0x180038d3d  retn
```
