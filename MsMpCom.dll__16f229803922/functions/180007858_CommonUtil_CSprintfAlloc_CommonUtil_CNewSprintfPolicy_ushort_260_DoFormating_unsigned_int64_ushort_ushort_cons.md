# CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)

- ea: `0x180007858`
- end: `0x180007a3b`
- name: `?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007a74`

## callees

- `0x180001ce6`
- `0x1800021b0`
- `0x180007858`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800078ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800079a1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800078ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800079a1`
- `mpclient!MpUtilsExportFunctions` at `0x18000789e`
- `mpclient!MpUtilsExportFunctions` at `0x18000794c`
- `mpclient!MpUtilsExportFunctions` at `0x1800079d0`
- `mpclient!MpUtilsExportFunctions` at `0x18000789e`
- `mpclient!MpUtilsExportFunctions` at `0x18000794c`
- `mpclient!MpUtilsExportFunctions` at `0x1800079d0`

## pseudocode

```c
__int64 __fastcall CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<unsigned short>,260>::DoFormating(
        unsigned __int64 *a1,
        void **a2,
        __int64 a3,
        __int64 a4)
{
  void *v4; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  void *v15; // rax
  __int64 result; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  void *v19; // rax
  void *v20; // rbx
  __int64 v21; // rax
  int v22; // ecx
  _QWORD v23[2]; // [rsp+30h] [rbp-278h] BYREF
  _WORD Src[264]; // [rsp+40h] [rbp-268h] BYREF

  v4 = *a2;
  v23[0] = 0;
  if ( v4 )
  {
    v10 = *a1;
    v17 = MpUtilsExportFunctions();
    result = (*(__int64 (__fastcall **)(unsigned __int64, void *, _QWORD *, __int64, __int64))(v17 + 200))(
               v10,
               v4,
               v23,
               a3,
               a4);
    if ( (_DWORD)result == -2147024774 )
    {
      do
      {
LABEL_12:
        if ( v10 >= v23[0] )
          v10 = (3 * v10) >> 1;
        else
          v10 = v23[0];
        if ( v10 > 0x7FFFFFFF )
          return 2147942522LL;
        operator delete[](*a2);
        v18 = 2 * v10;
        if ( !is_mul_ok(v10, 2u) )
          v18 = -1;
        v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
        *a2 = v19;
        if ( !v19 )
        {
          *a1 = 0;
          return 2147942414LL;
        }
        *a1 = v10;
        v20 = *a2;
        v21 = MpUtilsExportFunctions();
        v22 = (*(__int64 (__fastcall **)(unsigned __int64, void *, _QWORD *, __int64, __int64))(v21 + 200))(
                v10,
                v20,
                v23,
                a3,
                a4);
      }
      while ( v22 == -2147024774 );
      result = 0;
      if ( v22 < 0 )
        return (unsigned int)v22;
    }
  }
  else
  {
    v9 = MpUtilsExportFunctions();
    v10 = 260;
    if ( (*(int (__fastcall **)(__int64, _WORD *, _QWORD *, __int64, __int64))(v9 + 200))(260, Src, v23, a3, a4) < 0 )
      goto LABEL_12;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
    v13 = v12 + 1;
    operator delete[](*a2);
    v14 = 2 * v13;
    if ( !is_mul_ok(v13, 2u) )
      v14 = -1;
    v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    *a2 = v15;
    if ( v15 )
    {
      memcpy_0(v15, Src, 2 * v13);
      do
        ++v11;
      while ( Src[v11] );
      *a1 = v11 + 1;
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007858  push    rbx
0x18000785a  push    rbp
0x18000785b  push    rsi
0x18000785c  push    rdi
0x18000785d  push    r12
0x18000785f  push    r13
0x180007861  push    r14
0x180007863  push    r15
0x180007865  sub     rsp, 268h
0x18000786c  mov     rax, cs:__security_cookie
0x180007873  xor     rax, rsp
0x180007876  mov     [rsp+2A8h+var_58], rax
0x18000787e  mov     rbx, [rdx]
0x180007881  xor     r13d, r13d
0x180007884  mov     [rsp+2A8h+var_278], r13
0x180007889  mov     r12, r9
0x18000788c  mov     rbp, r8
0x18000788f  mov     r15, rdx
0x180007892  mov     r14, rcx
0x180007895  test    rbx, rbx
0x180007898  jnz     loc_180007949
0x18000789e  call    cs:__imp_MpUtilsExportFunctions
0x1800078a4  mov     edi, 104h
0x1800078a9  mov     [rsp+2A8h+var_288], r12
0x1800078ae  mov     r9, rbp
0x1800078b1  lea     r8, [rsp+2A8h+var_278]
0x1800078b6  lea     rdx, [rsp+2A8h+Src]
0x1800078bb  mov     ecx, edi
0x1800078bd  mov     rax, [rax+0C8h]
0x1800078c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c9  test    eax, eax
0x1800078cb  js      loc_18000797C
0x1800078d1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800078d5  lea     rcx, [rsp+2A8h+Src]
0x1800078da  mov     rax, rsi
0x1800078dd  inc     rax
0x1800078e0  cmp     [rcx+rax*2], r13w
0x1800078e5  jnz     short loc_1800078DD
0x1800078e7  mov     rcx, [r15]
0x1800078ea  lea     rbx, [rax+1]
0x1800078ee  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800078f4  mov     eax, 2
0x1800078f9  mul     rbx
0x1800078fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007903  cmovb   rax, rsi
0x180007907  mov     rcx, rax; unsigned __int64
0x18000790a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000790f  mov     [r15], rax
0x180007912  test    rax, rax
0x180007915  jz      loc_180007A0B
0x18000791b  lea     r8, [rbx+rbx]; Size
0x18000791f  mov     rcx, rax; void *
0x180007922  lea     rdx, [rsp+2A8h+Src]; Src
0x180007927  call    memcpy_0
0x18000792c  lea     rax, [rsp+2A8h+Src]
0x180007931  inc     rsi
0x180007934  cmp     [rax+rsi*2], r13w
0x180007939  jnz     short loc_180007931
0x18000793b  lea     rax, [rsi+1]
0x18000793f  mov     [r14], rax
0x180007942  xor     eax, eax
0x180007944  jmp     loc_180007A17
0x180007949  mov     rdi, [rcx]
0x18000794c  call    cs:__imp_MpUtilsExportFunctions
0x180007952  mov     r9, rbp
0x180007955  mov     [rsp+2A8h+var_288], r12
0x18000795a  lea     r8, [rsp+2A8h+var_278]
0x18000795f  mov     rdx, rbx
0x180007962  mov     rcx, rdi
0x180007965  mov     rax, [rax+0C8h]
0x18000796c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007971  cmp     eax, 8007007Ah
0x180007976  jnz     loc_180007A17
0x18000797c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007980  cmp     rdi, [rsp+2A8h+var_278]
0x180007985  jnb     short loc_18000798E
0x180007987  mov     rdi, [rsp+2A8h+var_278]
0x18000798c  jmp     short loc_180007995
0x18000798e  lea     rdi, [rdi+rdi*2]
0x180007992  shr     rdi, 1
0x180007995  cmp     rdi, 7FFFFFFFh
0x18000799c  ja      short loc_180007A12
0x18000799e  mov     rcx, [r15]
0x1800079a1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800079a7  mov     eax, 2
0x1800079ac  mul     rdi
0x1800079af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079b6  cmovb   rax, rsi
0x1800079ba  mov     rcx, rax; unsigned __int64
0x1800079bd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800079c2  mov     [r15], rax
0x1800079c5  test    rax, rax
0x1800079c8  jz      short loc_180007A08
0x1800079ca  mov     [r14], rdi
0x1800079cd  mov     rbx, [r15]
0x1800079d0  call    cs:__imp_MpUtilsExportFunctions
0x1800079d6  mov     r9, rbp
0x1800079d9  mov     [rsp+2A8h+var_288], r12
0x1800079de  lea     r8, [rsp+2A8h+var_278]
0x1800079e3  mov     rdx, rbx
0x1800079e6  mov     rcx, rdi
0x1800079e9  mov     rax, [rax+0C8h]
0x1800079f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f5  mov     ecx, eax
0x1800079f7  cmp     eax, 8007007Ah
0x1800079fc  jz      short loc_180007980
0x1800079fe  test    ecx, ecx
0x180007a00  mov     eax, r13d
0x180007a03  cmovs   eax, ecx
0x180007a06  jmp     short loc_180007A17
0x180007a08  mov     [r14], r13
0x180007a0b  mov     eax, 8007000Eh
0x180007a10  jmp     short loc_180007A17
0x180007a12  mov     eax, 8007007Ah
0x180007a17  mov     rcx, [rsp+2A8h+var_58]
0x180007a1f  xor     rcx, rsp; StackCookie
0x180007a22  call    __security_check_cookie
0x180007a27  add     rsp, 268h
0x180007a2e  pop     r15
0x180007a30  pop     r14
0x180007a32  pop     r13
0x180007a34  pop     r12
0x180007a36  pop     rdi
0x180007a37  pop     rsi
0x180007a38  pop     rbp
0x180007a39  pop     rbx
0x180007a3a  retn
```
