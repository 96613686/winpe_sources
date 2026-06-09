# SrppPluginAccessCheck

- ea: `0x14002fc50`
- end: `0x14002fe15`
- name: `SrppPluginAccessCheck`
- size: `453`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002023c`
- `0x14002f560`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x14002fc50`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fce8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002fce8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fde2`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fde2`
- `ntoskrnl!SeSrpAccessCheck` at `0x14002fdad`
- `ntoskrnl!SeSrpAccessCheck` at `0x14002fdad`

## pseudocode

```c
__int64 __fastcall SrppPluginAccessCheck(HANDLE Handle, __int64 a2, unsigned int *a3)
{
  NTSTATUS v6; // eax
  PVOID v7; // rdi
  __int64 result; // rax
  unsigned int v9; // ecx
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+34h] [rbp-CCh] BYREF
  PVOID Object; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int128 v18; // [rsp+78h] [rbp-88h] BYREF
  __int128 v19; // [rsp+88h] [rbp-78h]
  _BYTE v20[24]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v21; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v22; // [rsp+C0h] [rbp-40h]
  _DWORD v23[32]; // [rsp+D0h] [rbp-30h] BYREF

  memset(v23, 0, sizeof(v23));
  v17 = 0;
  v12 = 0;
  v21 = 0;
  Object = 0;
  v22 = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  memset(v20, 0, 20);
  v15 = 0;
  v16 = 0;
  v6 = ObReferenceObjectByHandle(Handle, 0, 0, 0, &Object, 0);
  v7 = Object;
  v11 = v6;
  if ( v6 >= 0 )
  {
    LOBYTE(HandleInformation) = 1;
    *((_QWORD *)&v14 + 1) = a2 + *(unsigned int *)(a2 + 16);
    v21 = 0u;
    *(_QWORD *)v20 = qword_14000C000;
    *((_QWORD *)&v18 + 1) = &v14;
    *((_QWORD *)&v15 + 1) = &v12;
    v22 = (unsigned __int64)Object;
    *(_QWORD *)&v16 = &v11;
    *((_QWORD *)&v16 + 1) = v23;
    *(_QWORD *)&v14 = 0x300000010LL;
    *(_QWORD *)&v18 = 56;
    *(_OWORD *)&v20[8] = 0;
    v19 = 0x20u;
    *(_QWORD *)&v15 = 0x100000028LL;
    v17 = 0;
    if ( !(unsigned __int8)SeSrpAccessCheck(&v21, 0, &v18, &v15, 0, HandleInformation) && v11 == -1073741790 )
      v11 = (*(_BYTE *)(a2 + 24) & 1) != 0 ? 0xC0000364 : 0;
  }
  if ( v7 )
    ObfDereferenceObject(v7);
  result = v11;
  v9 = v23[5];
  *a3 = v11;
  a3[1] = v9;
  return result;
}

```

## disassembly

```asm
0x14002fc50  push    rbp
0x14002fc52  push    rbx
0x14002fc53  push    rsi
0x14002fc54  push    rdi
0x14002fc55  push    r14
0x14002fc57  lea     rbp, [rsp-60h]
0x14002fc5c  sub     rsp, 160h
0x14002fc63  mov     rax, cs:__security_cookie
0x14002fc6a  xor     rax, rsp
0x14002fc6d  mov     [rbp+80h+var_30], rax
0x14002fc71  mov     rbx, r8
0x14002fc74  mov     rsi, rdx
0x14002fc77  mov     rdi, rcx
0x14002fc7a  xor     edx, edx; Val
0x14002fc7c  mov     r8d, 80h; Size
0x14002fc82  lea     rcx, [rbp+80h+var_B0]; void *
0x14002fc86  call    memset
0x14002fc8b  xorps   xmm0, xmm0
0x14002fc8e  xor     eax, eax
0x14002fc90  xor     r14d, r14d
0x14002fc93  mov     [rbp+80h+var_D8], eax
0x14002fc96  mov     [rsp+180h+var_110], rax
0x14002fc9b  xor     r9d, r9d; AccessMode
0x14002fc9e  lea     rax, [rsp+180h+var_148]
0x14002fca3  mov     [rsp+180h+HandleInformation], r14; HandleInformation
0x14002fca8  xor     r8d, r8d; ObjectType
0x14002fcab  mov     [rsp+180h+Object], rax; Object
0x14002fcb0  xor     edx, edx; DesiredAccess
0x14002fcb2  mov     [rsp+180h+var_150], r14d
0x14002fcb7  mov     rcx, rdi; Handle
0x14002fcba  mov     [rsp+180h+var_14C], r14d
0x14002fcbf  movups  [rbp+80h+var_D0], xmm0
0x14002fcc3  mov     [rsp+180h+var_148], r14
0x14002fcc8  movups  [rbp+80h+var_C0], xmm0
0x14002fccc  movups  [rsp+180h+var_140], xmm0
0x14002fcd1  movups  [rsp+180h+var_108], xmm0
0x14002fcd6  movups  [rbp+80h+var_F8], xmm0
0x14002fcda  movups  [rbp+80h+var_E8], xmm0
0x14002fcde  movups  [rsp+180h+var_130], xmm0
0x14002fce3  movups  [rsp+180h+var_120], xmm0
0x14002fce8  call    cs:__imp_ObReferenceObjectByHandle
0x14002fcef  nop     dword ptr [rax+rax+00h]
0x14002fcf4  mov     rdi, [rsp+180h+var_148]
0x14002fcf9  mov     [rsp+180h+var_150], eax
0x14002fcfd  test    eax, eax
0x14002fcff  js      loc_14002FDDA
0x14002fd05  mov     eax, [rsi+10h]
0x14002fd08  lea     r9, [rsp+180h+var_130]
0x14002fd0d  add     rax, rsi
0x14002fd10  mov     byte ptr [rsp+180h+HandleInformation], 1
0x14002fd15  mov     qword ptr [rsp+180h+var_140+8], rax
0x14002fd1a  lea     r8, [rsp+180h+var_108]
0x14002fd1f  lea     rax, qword_14000C000
0x14002fd26  mov     qword ptr [rbp+80h+var_D0], r14
0x14002fd2a  mov     qword ptr [rbp+80h+var_E8], rax
0x14002fd2e  lea     rcx, [rbp+80h+var_D0]
0x14002fd32  lea     rax, [rsp+180h+var_140]
0x14002fd37  mov     qword ptr [rbp+80h+var_D0+8], r14
0x14002fd3b  mov     qword ptr [rbp+80h+var_108+8], rax
0x14002fd3f  xorps   xmm0, xmm0
0x14002fd42  lea     rax, [rsp+180h+var_14C]
0x14002fd47  mov     qword ptr [rbp+80h+var_C0+8], r14
0x14002fd4b  mov     qword ptr [rsp+180h+var_130+8], rax
0x14002fd50  xor     edx, edx
0x14002fd52  lea     rax, [rsp+180h+var_150]
0x14002fd57  mov     qword ptr [rbp+80h+var_C0], rdi
0x14002fd5b  mov     qword ptr [rsp+180h+var_120], rax
0x14002fd60  lea     rax, [rbp+80h+var_B0]
0x14002fd64  mov     qword ptr [rsp+180h+var_120+8], rax
0x14002fd69  mov     dword ptr [rsp+180h+var_140], 10h
0x14002fd71  mov     dword ptr [rsp+180h+var_140+4], 3
0x14002fd79  mov     qword ptr [rsp+180h+var_108], 38h ; '8'
0x14002fd82  mov     qword ptr [rbp+80h+var_F8+8], r14
0x14002fd86  movdqu  [rbp+80h+var_E8+8], xmm0
0x14002fd8b  mov     qword ptr [rbp+80h+var_F8], 20h ; ' '
0x14002fd93  mov     dword ptr [rsp+180h+var_130], 28h ; '('
0x14002fd9b  mov     dword ptr [rsp+180h+var_130+4], 1
0x14002fda3  mov     [rsp+180h+var_110], r14
0x14002fda8  mov     [rsp+180h+Object], r14
0x14002fdad  call    cs:__imp_SeSrpAccessCheck
0x14002fdb4  nop     dword ptr [rax+rax+00h]
0x14002fdb9  test    al, al
0x14002fdbb  jnz     short loc_14002FDDA
0x14002fdbd  cmp     [rsp+180h+var_150], 0C0000022h
0x14002fdc5  jnz     short loc_14002FDDA
0x14002fdc7  movzx   eax, byte ptr [rsi+18h]
0x14002fdcb  and     al, 1
0x14002fdcd  neg     al
0x14002fdcf  sbb     eax, eax
0x14002fdd1  and     eax, 0C0000364h
0x14002fdd6  mov     [rsp+180h+var_150], eax
0x14002fdda  test    rdi, rdi
0x14002fddd  jz      short loc_14002FDEE
0x14002fddf  mov     rcx, rdi; Object
0x14002fde2  call    cs:__imp_ObfDereferenceObject
0x14002fde9  nop     dword ptr [rax+rax+00h]
0x14002fdee  mov     eax, [rsp+180h+var_150]
0x14002fdf2  mov     ecx, [rbp+80h+var_9C]
0x14002fdf5  mov     [rbx], eax
0x14002fdf7  mov     [rbx+4], ecx
0x14002fdfa  mov     rcx, [rbp+80h+var_30]
0x14002fdfe  xor     rcx, rsp; StackCookie
0x14002fe01  call    __security_check_cookie
0x14002fe06  add     rsp, 160h
0x14002fe0d  pop     r14
0x14002fe0f  pop     rdi
0x14002fe10  pop     rsi
0x14002fe11  pop     rbx
0x14002fe12  pop     rbp
0x14002fe13  retn
```
