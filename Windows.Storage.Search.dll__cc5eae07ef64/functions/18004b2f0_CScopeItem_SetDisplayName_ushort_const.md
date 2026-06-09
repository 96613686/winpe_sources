# CScopeItem::SetDisplayName(ushort const *)

- ea: `0x18004b2f0`
- end: `0x18004b43a`
- name: `?SetDisplayName@CScopeItem@@UEAAJPEBG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CScopeItem *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004b2f0`
- `0x18007a4e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b30a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b30a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b3f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b3f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b351`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b351`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b314`

## pseudocode

```c
__int64 __fastcall CScopeItem::SetDisplayName(RTL_SRWLOCK *this, const unsigned __int16 *a2)
{
  RTL_SRWLOCK *v2; // r14
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rbx
  _WORD *v7; // rax
  _WORD *v8; // r8
  unsigned int v9; // edi
  const WCHAR *v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _WORD *v13; // r10
  __int64 v14; // r11
  _WORD *v15; // rcx
  __int64 v16; // r9
  __int64 v18; // rbx
  bool v19; // cf

  v2 = this + 9;
  AcquireSRWLockExclusive(this + 9);
  CoTaskMemFree(this[8].Ptr);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  this[8].Ptr = 0;
  if ( v5 + 1 < v5 || !is_mul_ok(v6, 2u) )
  {
    v9 = -2147024362;
    goto LABEL_17;
  }
  v7 = CoTaskMemAlloc(2 * v6);
  this[8].Ptr = v7;
  v8 = v7;
  v9 = v7 == 0 ? 0x8007000E : 0;
  if ( v7 )
  {
    if ( v6 <= 0x7FFFFFFF )
    {
      if ( v5 < 0x7FFFFFFF )
      {
        v10 = &pszFormat;
        v11 = v5 & -(__int64)(a2 != 0);
        if ( a2 )
          v10 = a2;
        v12 = v5 + 1;
        v13 = v8;
        v14 = 0;
        do
        {
          if ( !v11 )
            break;
          if ( !*v10 )
            break;
          *v13++ = *v10++;
          --v11;
          ++v14;
          --v12;
        }
        while ( v12 );
        v15 = v13 - 1;
        v16 = v14 - 1;
        if ( v12 )
        {
          v15 = v13;
          v16 = v14;
        }
        *v15 = 0;
        if ( v12 )
        {
          v19 = v6 == v16;
          v18 = v6 - v16;
          if ( !v19 && v18 != 1 )
            StringExHandleFillBehindNullW(&v8[v16], 2 * v18, 0x300u);
        }
        goto LABEL_17;
      }
      if ( v5 == -1 )
        goto LABEL_17;
    }
    *v7 = 0;
  }
LABEL_17:
  ReleaseSRWLockExclusive(v2);
  return v9;
}

```

## disassembly

```asm
0x18004b2f0  push    rbx
0x18004b2f2  push    rbp
0x18004b2f3  push    rsi
0x18004b2f4  push    rdi
0x18004b2f5  push    r14
0x18004b2f7  push    r15
0x18004b2f9  sub     rsp, 28h
0x18004b2fd  lea     r14, [rcx+48h]
0x18004b301  mov     rdi, rcx
0x18004b304  mov     rcx, r14; SRWLock
0x18004b307  mov     rbp, rdx
0x18004b30a  call    cs:__imp_AcquireSRWLockExclusive
0x18004b310  mov     rcx, [rdi+40h]; pv
0x18004b314  call    cs:__imp_CoTaskMemFree
0x18004b31a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004b31e  xor     r15d, r15d
0x18004b321  inc     rsi
0x18004b324  cmp     [rbp+rsi*2+0], r15w
0x18004b32a  jnz     short loc_18004B321
0x18004b32c  lea     rbx, [rsi+1]
0x18004b330  mov     [rdi+40h], r15
0x18004b334  cmp     rbx, rsi
0x18004b337  jb      loc_18004B40A
0x18004b33d  mov     eax, 2
0x18004b342  mul     rbx
0x18004b345  test    rdx, rdx
0x18004b348  jnz     loc_18004B40A
0x18004b34e  mov     rcx, rax; cb
0x18004b351  call    cs:__imp_CoTaskMemAlloc
0x18004b357  mov     [rdi+40h], rax
0x18004b35b  mov     rcx, rax
0x18004b35e  neg     rcx
0x18004b361  mov     r8, rax
0x18004b364  sbb     edi, edi
0x18004b366  not     edi
0x18004b368  and     edi, 8007000Eh
0x18004b36e  test    rax, rax
0x18004b371  jz      short loc_18004B3F2
0x18004b373  mov     eax, 7FFFFFFFh
0x18004b378  cmp     rbx, rax
0x18004b37b  ja      loc_18004B434
0x18004b381  cmp     rsi, rax
0x18004b384  jnb     loc_18004B42F
0x18004b38a  mov     rax, rbp
0x18004b38d  neg     rax
0x18004b390  lea     rax, pszFormat
0x18004b397  sbb     rcx, rcx
0x18004b39a  and     rcx, rsi
0x18004b39d  test    rbp, rbp
0x18004b3a0  cmovnz  rax, rbp
0x18004b3a4  test    rbx, rbx
0x18004b3a7  jz      short loc_18004B3F2
0x18004b3a9  mov     rdx, rbx
0x18004b3ac  mov     r10, r8
0x18004b3af  mov     r11, r15
0x18004b3b2  test    rcx, rcx
0x18004b3b5  jz      short loc_18004B3D9
0x18004b3b7  movzx   r9d, word ptr [rax]
0x18004b3bb  test    r9w, r9w
0x18004b3bf  jz      short loc_18004B3D9
0x18004b3c1  mov     [r10], r9w
0x18004b3c5  add     rax, 2
0x18004b3c9  add     r10, 2
0x18004b3cd  dec     rcx
0x18004b3d0  inc     r11
0x18004b3d3  sub     rdx, 1
0x18004b3d7  jnz     short loc_18004B3B2
0x18004b3d9  test    rdx, rdx
0x18004b3dc  lea     rcx, [r10-2]
0x18004b3e0  lea     r9, [r11-1]
0x18004b3e4  cmovnz  rcx, r10
0x18004b3e8  cmovnz  r9, r11
0x18004b3ec  mov     [rcx], r15w
0x18004b3f0  jnz     short loc_18004B411
0x18004b3f2  mov     rcx, r14; SRWLock
0x18004b3f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b3fb  mov     eax, edi
0x18004b3fd  add     rsp, 28h
0x18004b401  pop     r15
0x18004b403  pop     r14
0x18004b405  pop     rdi
0x18004b406  pop     rsi
0x18004b407  pop     rbp
0x18004b408  pop     rbx
0x18004b409  retn
0x18004b40a  mov     edi, 80070216h
0x18004b40f  jmp     short loc_18004B3F2
0x18004b411  sub     rbx, r9
0x18004b414  cmp     rbx, 1
0x18004b418  jbe     short loc_18004B3F2
0x18004b41a  lea     rcx, [r8+r9*2]; pszDestEnd
0x18004b41e  mov     r8d, 300h; dwFlags
0x18004b424  lea     rdx, [rbx+rbx]; cbRemaining
0x18004b428  call    StringExHandleFillBehindNullW
0x18004b42d  jmp     short loc_18004B3F2
0x18004b42f  test    rbx, rbx
0x18004b432  jz      short loc_18004B3F2
0x18004b434  mov     [r8], r15w
0x18004b438  jmp     short loc_18004B3F2
```
