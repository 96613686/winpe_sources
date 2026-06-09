# Common::DirectoryTreeWalker::InitializePath(ushort const *)

- ea: `0x180018b90`
- end: `0x180018cbb`
- name: `?InitializePath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z`
- size: `299`
- prototype: `int(Common::DirectoryTreeWalker *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018ffc`

## callees

- `0x18000be00`
- `0x18000be3c`
- `0x180018b90`
- `0x180018cf0`
- `0x180018dd8`
- `0x180018e54`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::InitializePath(
        Common::DirectoryTreeWalker *this,
        const unsigned __int16 *a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v6; // rdi
  unsigned __int64 v7; // rdx
  const unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // rcx
  bool v10; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-8h] BYREF
  bool v12; // [rsp+70h] [rbp+30h] BYREF
  bool v13; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  v10 = 0;
  v13 = 0;
  result = Common::DirectoryTreeWalker::IsRootValidToWalk(a2, (unsigned __int64 *)&v11, &v12, &v10, &v13);
  if ( !(_DWORD)result )
  {
    v5 = v11;
    if ( !v12 )
    {
      if ( v13 )
        v5 = v11 + 3;
      else
        v5 = v11 + 2;
    }
    if ( (unsigned __int64)v5 <= 0x7FFF )
    {
      v11 = 0;
      Common::GlobalHeap::Alloc(0x10000u, (void **)&v11);
      v6 = v11;
      if ( v11 )
      {
        if ( v12 )
        {
          RtlStringCchCopyW(v11, 0x8000u, a2);
        }
        else
        {
          if ( v13 )
          {
            RtlStringCchCopyW(v11, 0x8000u, L"\\\\?\\UNC\\");
            v8 = a2 + 2;
          }
          else
          {
            RtlStringCchCopyW(v11, 0x8000u, L"\\\\?\\");
            v8 = a2;
          }
          RtlStringCchCatW(v6, v7, v8);
        }
        if ( v6[(_QWORD)v5 - 1] == 92 )
        {
          v6[(_QWORD)v5 - 1] = 0;
          v5 = (unsigned __int16 *)((char *)v5 - 1);
        }
        v9 = (unsigned __int16 *)*((_QWORD *)this + 1);
        if ( v9 != v6 )
        {
          Common::GlobalHeap::Free(v9);
          *((_QWORD *)this + 1) = v6;
        }
        *((_QWORD *)this + 2) = v5;
        result = 0;
        *((_QWORD *)this + 3) = v5;
      }
      else
      {
        return 14;
      }
    }
    else
    {
      return 206;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018b90  mov     [rsp-18h+arg_0], rbx
0x180018b95  mov     [rsp-18h+arg_8], rsi
0x180018b9a  push    rbp
0x180018b9b  push    rdi
0x180018b9c  push    r13
0x180018b9e  mov     rbp, rsp
0x180018ba1  sub     rsp, 40h
0x180018ba5  mov     r13, rdx
0x180018ba8  mov     [rbp+var_8], 0
0x180018bb0  mov     rsi, rcx
0x180018bb3  mov     [rbp+arg_10], 0
0x180018bb7  lea     rax, [rbp+arg_18]
0x180018bbb  mov     [rbp+var_10], 0
0x180018bbf  mov     rcx, r13; unsigned __int16 *
0x180018bc2  mov     [rbp+arg_18], 0
0x180018bc6  lea     r9, [rbp+var_10]; bool *
0x180018bca  mov     [rsp+40h+var_20], rax; bool *
0x180018bcf  lea     r8, [rbp+arg_10]; bool *
0x180018bd3  lea     rdx, [rbp+var_8]; unsigned __int64 *
0x180018bd7  call    ?IsRootValidToWalk@DirectoryTreeWalker@Common@@CAJPEBGPEA_KPEA_N22@Z; Common::DirectoryTreeWalker::IsRootValidToWalk(ushort const *,unsigned __int64 *,bool *,bool *,bool *)
0x180018bdc  test    eax, eax
0x180018bde  jnz     loc_180018CA8
0x180018be4  mov     rbx, [rbp+var_8]
0x180018be8  cmp     [rbp+arg_10], al
0x180018beb  jnz     short loc_180018BFC
0x180018bed  cmp     [rbp+arg_18], al
0x180018bf0  jz      short loc_180018BF8
0x180018bf2  add     rbx, 6
0x180018bf6  jmp     short loc_180018BFC
0x180018bf8  add     rbx, 4
0x180018bfc  cmp     rbx, 7FFFh
0x180018c03  jbe     short loc_180018C0F
0x180018c05  mov     eax, 0CEh
0x180018c0a  jmp     loc_180018CA8
0x180018c0f  lea     rdx, [rbp+var_8]; void **
0x180018c13  mov     [rbp+var_8], 0
0x180018c1b  mov     ecx, 10000h; unsigned __int64
0x180018c20  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180018c25  mov     rdi, [rbp+var_8]
0x180018c29  test    rdi, rdi
0x180018c2c  jnz     short loc_180018C33
0x180018c2e  lea     eax, [rdi+0Eh]
0x180018c31  jmp     short loc_180018CA8
0x180018c33  cmp     [rbp+arg_10], 0
0x180018c37  mov     edx, 8000h; unsigned __int64
0x180018c3c  mov     rcx, rdi; unsigned __int16 *
0x180018c3f  jz      short loc_180018C4B
0x180018c41  mov     r8, r13; unsigned __int16 *
0x180018c44  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018c49  jmp     short loc_180018C7A
0x180018c4b  cmp     [rbp+arg_18], 0
0x180018c4f  jz      short loc_180018C63
0x180018c51  lea     r8, aUnc; "\\\\?\\UNC\\"
0x180018c58  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018c5d  lea     r8, [r13+4]
0x180018c61  jmp     short loc_180018C72
0x180018c63  lea     r8, asc_18001FBB0; "\\\\?\\"
0x180018c6a  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018c6f  mov     r8, r13; unsigned __int16 *
0x180018c72  mov     rcx, rdi; unsigned __int16 *
0x180018c75  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018c7a  cmp     word ptr [rdi+rbx*2-2], 5Ch ; '\'
0x180018c80  jnz     short loc_180018C8C
0x180018c82  xor     eax, eax
0x180018c84  mov     [rdi+rbx*2-2], ax
0x180018c89  dec     rbx
0x180018c8c  mov     rcx, [rsi+8]; P
0x180018c90  cmp     rcx, rdi
0x180018c93  jz      short loc_180018C9E
0x180018c95  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180018c9a  mov     [rsi+8], rdi
0x180018c9e  mov     [rsi+10h], rbx
0x180018ca2  xor     eax, eax
0x180018ca4  mov     [rsi+18h], rbx
0x180018ca8  mov     rbx, [rsp+40h+arg_0]
0x180018cad  mov     rsi, [rsp+40h+arg_8]
0x180018cb2  add     rsp, 40h
0x180018cb6  pop     r13
0x180018cb8  pop     rdi
0x180018cb9  pop     rbp
0x180018cba  retn
```
