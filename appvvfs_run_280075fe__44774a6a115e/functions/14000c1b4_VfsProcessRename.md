# VfsProcessRename

- ea: `0x14000c1b4`
- end: `0x14000c403`
- name: `VfsProcessRename`
- size: `591`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x140001690`

## callees

- `0x14000c1b4`
- `0x14000c574`
- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`
- `0x14000f058`
- `0x14000f124`
- `0x1400111ec`
- `0x140013b00`
- `0x140013be0`
- `0x140014000`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000c242`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000c242`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000c251`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000c251`
- `AppvVemgr!VeMgrLookupProcess` at `0x14000c26b`
- `AppvVemgr!VeMgrLookupProcess` at `0x14000c26b`

## pseudocode

```c
__int64 __fastcall VfsProcessRename(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v5; // r14
  __int64 v6; // rsi
  __int64 v7; // rcx
  HANDLE CurrentThreadId; // rbx
  HANDLE CurrentProcessId; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // rbx
  __int64 v18; // [rsp+30h] [rbp-79h] BYREF
  __int64 v19; // [rsp+38h] [rbp-71h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD Buf2[2]; // [rsp+50h] [rbp-59h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp-39h] BYREF
  __int128 v24; // [rsp+80h] [rbp-29h]
  _BYTE v25[80]; // [rsp+90h] [rbp-19h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v20 = 0;
  v5 = *(_QWORD *)(v2 + 56);
  v6 = *(_QWORD *)(v2 + 40);
  Buf1 = 0;
  v24 = 0;
  memset(v25, 0, 0x44u);
  v7 = *(_QWORD *)(a2 + 32);
  v18 = 0;
  v19 = 0;
  if ( !(unsigned __int8)VfsDecodeFileObject(v7, v21, &v18) )
  {
    if ( !v6 )
      return 1;
    CurrentThreadId = PsGetCurrentThreadId();
    CurrentProcessId = PsGetCurrentProcessId();
    v10 = VeMgrLookupProcess(CurrentProcessId, CurrentThreadId, &Buf1, v25);
    if ( v10 == -1073741772 )
    {
      LODWORD(v18) = 0;
      Buf1 = 0;
      v24 = 0;
    }
    else
    {
      LODWORD(v18) = v10;
      if ( v10 < 0 )
        goto LABEL_11;
    }
    memset(Buf2, 0, sizeof(Buf2));
    if ( !memcmp(&Buf1, Buf2, 0x20u) )
    {
      if ( (unsigned __int8)VfsDecodeFileObject(v6, 0, 0)
        || (v12 = *(_QWORD *)(v5 + 8)) != 0
        && (LOBYTE(v11) = *(_BYTE *)(a1 + 80), (unsigned __int8)VfsDecodeFileHandle(v12, v11, &v18, &v20)) )
      {
        *(_DWORD *)(a1 + 24) = -1073741823;
LABEL_12:
        *(_QWORD *)(a1 + 32) = 0;
        return 4;
      }
      return 1;
    }
    if ( (unsigned __int8)VfsDecodeFileObject(v6, 0, &v19) )
      return VfsRenameNativeFileToVirtualTarget(a1);
    v15 = *(_QWORD *)(a1 + 16);
    LODWORD(v18) = 0;
    v19 = 0;
    v16 = *(_QWORD *)(v15 + 56);
    v17 = *(_QWORD *)(v16 + 8);
    if ( !v17 )
      return 1;
    LOBYTE(v14) = *(_BYTE *)(a1 + 80);
    if ( !(unsigned __int8)VfsDecodeFileHandle(*(_QWORD *)(v16 + 8), v14, &v18, &v19) )
      return 1;
    v10 = v18;
    if ( (int)v18 >= 0 )
    {
      *(_QWORD *)(v16 + 8) = v19;
      v10 = VfsSetRenameInformation(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL),
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
              v6,
              v16,
              *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL));
      *(_QWORD *)(v16 + 8) = v17;
    }
LABEL_11:
    *(_DWORD *)(a1 + 24) = v10;
    goto LABEL_12;
  }
  if ( !v6 )
    return VfsRenameVirtualFileSimple(a1, v18);
  if ( (unsigned __int8)VfsDecodeFileObject(v6, 0, &v19) )
    return VfsRenameVirtualFileToVirtualTarget(a1);
  return VfsRenameVirtualFileToNativeTarget(a1, v18, v6);
}

```

## disassembly

```asm
0x14000c1b4  mov     [rsp-8+arg_10], rbx
0x14000c1b9  mov     [rsp-8+arg_18], rsi
0x14000c1be  push    rbp
0x14000c1bf  push    rdi
0x14000c1c0  push    r14
0x14000c1c2  lea     rbp, [rsp-47h]
0x14000c1c7  sub     rsp, 0F0h
0x14000c1ce  mov     rax, cs:__security_cookie
0x14000c1d5  xor     rax, rsp
0x14000c1d8  mov     [rbp+57h+var_20], rax
0x14000c1dc  mov     rax, [rcx+10h]
0x14000c1e0  xorps   xmm0, xmm0
0x14000c1e3  mov     rbx, rdx
0x14000c1e6  mov     [rbp+57h+var_C0], 0
0x14000c1ee  xor     edx, edx; Val
0x14000c1f0  mov     rdi, rcx
0x14000c1f3  lea     rcx, [rbp+57h+var_70]; void *
0x14000c1f7  mov     r14, [rax+38h]
0x14000c1fb  mov     rsi, [rax+28h]
0x14000c1ff  lea     r8d, [rdx+44h]; Size
0x14000c203  movups  [rbp+57h+Buf1], xmm0
0x14000c207  movups  [rbp+57h+var_80], xmm0
0x14000c20b  call    memset
0x14000c210  mov     rcx, [rbx+20h]
0x14000c214  lea     r8, [rbp+57h+var_D0]
0x14000c218  lea     rdx, [rbp+57h+var_B8]
0x14000c21c  mov     [rbp+57h+var_D0], 0
0x14000c224  mov     [rbp+57h+var_C8], 0
0x14000c22c  call    VfsDecodeFileObject
0x14000c231  test    al, al
0x14000c233  jnz     loc_14000C39F
0x14000c239  test    rsi, rsi
0x14000c23c  jz      loc_14000C398
0x14000c242  call    cs:__imp_PsGetCurrentThreadId
0x14000c249  nop     dword ptr [rax+rax+00h]
0x14000c24e  mov     rbx, rax
0x14000c251  call    cs:__imp_PsGetCurrentProcessId
0x14000c258  nop     dword ptr [rax+rax+00h]
0x14000c25d  lea     r9, [rbp+57h+var_70]
0x14000c261  mov     rdx, rbx
0x14000c264  mov     rcx, rax
0x14000c267  lea     r8, [rbp+57h+Buf1]
0x14000c26b  call    cs:__imp_VeMgrLookupProcess
0x14000c272  nop     dword ptr [rax+rax+00h]
0x14000c277  cmp     eax, 0C0000034h
0x14000c27c  jnz     short loc_14000C2F1
0x14000c27e  xorps   xmm0, xmm0
0x14000c281  mov     dword ptr [rbp+57h+var_D0], 0
0x14000c288  movups  [rbp+57h+Buf1], xmm0
0x14000c28c  movups  [rbp+57h+var_80], xmm0
0x14000c290  xorps   xmm0, xmm0
0x14000c293  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14000c297  mov     r8d, 20h ; ' '; Size
0x14000c29d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14000c2a1  movups  [rbp+57h+Buf2], xmm0
0x14000c2a5  movups  [rbp+57h+var_A0], xmm0
0x14000c2a9  call    memcmp
0x14000c2ae  xor     edx, edx
0x14000c2b0  mov     rcx, rsi
0x14000c2b3  test    eax, eax
0x14000c2b5  jnz     short loc_14000C30D
0x14000c2b7  xor     r8d, r8d
0x14000c2ba  call    VfsDecodeFileObject
0x14000c2bf  test    al, al
0x14000c2c1  jnz     short loc_14000C2E8
0x14000c2c3  mov     rcx, [r14+8]
0x14000c2c7  test    rcx, rcx
0x14000c2ca  jz      loc_14000C398
0x14000c2d0  mov     dl, [rdi+50h]
0x14000c2d3  lea     r9, [rbp+57h+var_C0]
0x14000c2d7  lea     r8, [rbp+57h+var_D0]
0x14000c2db  call    VfsDecodeFileHandle
0x14000c2e0  test    al, al
0x14000c2e2  jz      loc_14000C398
0x14000c2e8  mov     dword ptr [rdi+18h], 0C0000001h
0x14000c2ef  jmp     short loc_14000C2FB
0x14000c2f1  mov     dword ptr [rbp+57h+var_D0], eax
0x14000c2f4  test    eax, eax
0x14000c2f6  jns     short loc_14000C290
0x14000c2f8  mov     [rdi+18h], eax
0x14000c2fb  mov     qword ptr [rdi+20h], 0
0x14000c303  mov     eax, 4
0x14000c308  jmp     loc_14000C3DE
0x14000c30d  lea     r8, [rbp+57h+var_C8]
0x14000c311  call    VfsDecodeFileObject
0x14000c316  test    al, al
0x14000c318  jnz     short loc_14000C387
0x14000c31a  mov     rax, [rdi+10h]
0x14000c31e  mov     dword ptr [rbp+57h+var_D0], 0
0x14000c325  mov     [rbp+57h+var_C8], 0
0x14000c32d  mov     r14, [rax+38h]
0x14000c331  mov     rbx, [r14+8]
0x14000c335  test    rbx, rbx
0x14000c338  jz      short loc_14000C398
0x14000c33a  mov     dl, [rdi+50h]
0x14000c33d  lea     r9, [rbp+57h+var_C8]
0x14000c341  lea     r8, [rbp+57h+var_D0]
0x14000c345  mov     rcx, rbx
0x14000c348  call    VfsDecodeFileHandle
0x14000c34d  test    al, al
0x14000c34f  jz      short loc_14000C398
0x14000c351  mov     eax, dword ptr [rbp+57h+var_D0]
0x14000c354  test    eax, eax
0x14000c356  js      short loc_14000C2F8
0x14000c358  mov     rax, [rbp+57h+var_C8]
0x14000c35c  mov     r9, r14
0x14000c35f  mov     [r14+8], rax
0x14000c363  mov     r8, rsi
0x14000c366  mov     rcx, [rdi+10h]
0x14000c36a  mov     eax, [rcx+18h]
0x14000c36d  mov     rdx, [rcx+8]
0x14000c371  mov     rcx, [rcx+10h]
0x14000c375  mov     [rsp+100h+var_E0], eax
0x14000c379  call    VfsSetRenameInformation
0x14000c37e  mov     [r14+8], rbx
0x14000c382  jmp     loc_14000C2F8
0x14000c387  mov     r8, [rbp+57h+var_C8]
0x14000c38b  mov     rdx, rsi
0x14000c38e  mov     rcx, rdi; int
0x14000c391  call    VfsRenameNativeFileToVirtualTarget
0x14000c396  jmp     short loc_14000C3DE
0x14000c398  mov     eax, 1
0x14000c39d  jmp     short loc_14000C3DE
0x14000c39f  test    rsi, rsi
0x14000c3a2  jnz     short loc_14000C3B2
0x14000c3a4  mov     rdx, [rbp+57h+var_D0]
0x14000c3a8  mov     rcx, rdi
0x14000c3ab  call    VfsRenameVirtualFileSimple
0x14000c3b0  jmp     short loc_14000C3DE
0x14000c3b2  lea     r8, [rbp+57h+var_C8]
0x14000c3b6  xor     edx, edx
0x14000c3b8  mov     rcx, rsi
0x14000c3bb  call    VfsDecodeFileObject
0x14000c3c0  mov     rdx, [rbp+57h+var_D0]
0x14000c3c4  mov     r8, rsi
0x14000c3c7  mov     rcx, rdi; int
0x14000c3ca  test    al, al
0x14000c3cc  jnz     short loc_14000C3D5
0x14000c3ce  call    VfsRenameVirtualFileToNativeTarget
0x14000c3d3  jmp     short loc_14000C3DE
0x14000c3d5  mov     r9, [rbp+57h+var_C8]
0x14000c3d9  call    VfsRenameVirtualFileToVirtualTarget
0x14000c3de  mov     rcx, [rbp+57h+var_20]
0x14000c3e2  xor     rcx, rsp; StackCookie
0x14000c3e5  call    __security_check_cookie
0x14000c3ea  lea     r11, [rsp+100h+var_10]
0x14000c3f2  mov     rbx, [r11+30h]
0x14000c3f6  mov     rsi, [r11+38h]
0x14000c3fa  mov     rsp, r11
0x14000c3fd  pop     r14
0x14000c3ff  pop     rdi
0x14000c400  pop     rbp
0x14000c401  retn
```
