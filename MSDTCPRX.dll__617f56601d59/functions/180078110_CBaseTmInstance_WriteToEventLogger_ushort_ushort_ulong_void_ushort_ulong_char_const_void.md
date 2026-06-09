# CBaseTmInstance::WriteToEventLogger(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *)

- ea: `0x180078110`
- end: `0x180078366`
- name: `?WriteToEventLogger@CBaseTmInstance@@UEAAJGGKPEAXGKPEAPEBD0@Z`
- size: `598`
- prototype: `__int64 __fastcall(CBaseTmInstance *__hidden this, unsigned __int16, unsigned __int16, unsigned int, void *, unsigned __int16, size_t Size, const char **, void *Src)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18001156c`
- `0x18001d178`
- `0x18001d184`
- `0x18001de26`
- `0x180075cb8`
- `0x18007652c`
- `0x180078110`
- `0x18008179c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007834c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007834c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078213`

## string_xrefs

- `0x1800782f5`: `com\complus\dtc\shared\util\basetminstance.cpp`
- `0x1800782fc`: `WriteToEventLogger failed`

## pseudocode

```c
__int64 __fastcall CBaseTmInstance::WriteToEventLogger(
        CBaseTmInstance *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        void *a5,
        unsigned __int16 a6,
        size_t Size,
        char **a8,
        void *Src)
{
  void **v10; // rsi
  char *v11; // r14
  signed int v12; // ebx
  __int64 v13; // rdi
  unsigned __int16 **v14; // rax
  CBaseTmInstance *v15; // rcx
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  char *v18; // rax
  char *v19; // r14
  int v20; // eax
  unsigned __int16 i; // di
  char *v23; // [rsp+60h] [rbp-58h]
  LPVOID pv; // [rsp+68h] [rbp-50h] BYREF
  void *v25; // [rsp+70h] [rbp-48h]

  v10 = 0;
  pv = 0;
  v11 = 0;
  v12 = CBaseTmInstance::EnsureEventLogHandle(this);
  if ( v12 < 0 )
    goto LABEL_23;
  v13 = -1;
  v14 = (unsigned __int16 **)operator new[](saturated_mul(a6, 8u));
  v10 = (void **)v14;
  if ( !v14 )
  {
    v12 = -2147024882;
LABEL_23:
    TraceFileW(v12, L"WriteToEventLogger failed", L"com\\complus\\dtc\\shared\\util\\basetminstance.cpp", 0x7D3u);
    goto LABEL_24;
  }
  v12 = CBaseTmInstance::AsciiToWideStringArray(v15, (const char **)a8, a6, v14);
  if ( v12 < 0 )
    goto LABEL_23;
  v12 = (*(__int64 (__fastcall **)(CBaseTmInstance *, LPVOID *))(*(_QWORD *)this + 56LL))(this, &pv);
  if ( v12 >= 0 )
  {
    v25 = pv;
    if ( pv )
    {
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      v16 = 2 * v13;
      if ( Src )
        v17 = v16 + Size + 4;
      else
        v17 = 2 * v13;
      v18 = (char *)CoTaskMemAlloc(v17);
      v19 = v18;
      if ( v18 )
      {
        v23 = v18;
        if ( Src )
        {
          memcpy_0(v18, Src, (unsigned int)Size);
          *(_DWORD *)&v19[(unsigned int)Size] = 0;
          v19 += (unsigned int)Size + 4;
        }
        memcpy_0(v19, v25, v16);
        v11 = v23;
        v12 = 0;
      }
      else
      {
        v11 = 0;
        v12 = -2147024882;
      }
    }
    else
    {
      v12 = -2147467259;
    }
  }
  v20 = NetpEventlogWriteEx3(*((_QWORD *)this + 1), a2, a3, a4);
  if ( v20 && v20 != 183 )
  {
    if ( v20 > 0 )
      v12 = (unsigned __int16)v20 | 0x80070000;
    else
      v12 = v20;
  }
  if ( v12 < 0 )
    goto LABEL_23;
LABEL_24:
  if ( v10 )
  {
    for ( i = 0; i < a6; ++i )
      operator delete(v10[i]);
    operator delete(v10);
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180078110  mov     rax, rsp
0x180078113  mov     [rax+20h], r9d
0x180078117  mov     [rax+18h], r8w
0x18007811c  mov     [rax+10h], dx
0x180078120  mov     [rax+8], rcx
0x180078124  push    rbx
0x180078125  push    rbp
0x180078126  push    rsi
0x180078127  push    rdi
0x180078128  push    r12
0x18007812a  push    r13
0x18007812c  push    r14
0x18007812e  sub     rsp, 80h
0x180078135  xor     r12d, r12d
0x180078138  mov     rbp, rcx
0x18007813b  mov     esi, r12d
0x18007813e  mov     [rax-50h], r12
0x180078142  mov     r14d, r12d
0x180078145  call    ?EnsureEventLogHandle@CBaseTmInstance@@AEAAJXZ; CBaseTmInstance::EnsureEventLogHandle(void)
0x18007814a  mov     ebx, eax
0x18007814c  test    eax, eax
0x18007814e  js      loc_1800782EF
0x180078154  movzx   r8d, [rsp+0B8h+arg_28]
0x18007815d  lea     eax, [r12+8]
0x180078162  mul     r8
0x180078165  lea     rdi, [r12-1]
0x18007816a  cmovb   rax, rdi
0x18007816e  mov     rcx, rax; unsigned __int64
0x180078171  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180078176  mov     rsi, rax
0x180078179  test    rax, rax
0x18007817c  jnz     short loc_180078188
0x18007817e  mov     ebx, 8007000Eh
0x180078183  jmp     loc_1800782EF
0x180078188  movzx   r8d, [rsp+0B8h+arg_28]; unsigned __int16
0x180078191  mov     r9, rsi; unsigned __int16 **
0x180078194  mov     rdx, [rsp+0B8h+arg_38]; char **
0x18007819c  call    ?AsciiToWideStringArray@CBaseTmInstance@@AEAAJPEAPEBDGPEAPEAG@Z; CBaseTmInstance::AsciiToWideStringArray(char const * *,ushort,ushort * *)
0x1800781a1  mov     ebx, eax
0x1800781a3  test    eax, eax
0x1800781a5  js      loc_1800782EF
0x1800781ab  mov     rax, [rbp+0]
0x1800781af  lea     rdx, [rsp+0B8h+pv]
0x1800781b4  mov     rcx, rbp
0x1800781b7  mov     rax, [rax+38h]
0x1800781bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781c0  mov     ebx, eax
0x1800781c2  test    eax, eax
0x1800781c4  js      loc_18007827C
0x1800781ca  mov     rax, [rsp+0B8h+pv]
0x1800781cf  mov     [rsp+0B8h+var_48], rax
0x1800781d4  mov     [rsp+0B8h+var_58], r12
0x1800781d9  test    rax, rax
0x1800781dc  jz      loc_180078277
0x1800781e2  inc     rdi
0x1800781e5  cmp     [rax+rdi*2], r12w
0x1800781ea  jnz     short loc_1800781E2
0x1800781ec  mov     ebp, dword ptr [rsp+0B8h+Size]
0x1800781f3  lea     r13d, [rdi+rdi]
0x1800781f7  mov     rdi, [rsp+0B8h+Src]
0x1800781ff  test    rdi, rdi
0x180078202  jz      short loc_18007820D
0x180078204  lea     r12d, [rbp+4]
0x180078208  add     r12d, r13d
0x18007820b  jmp     short loc_180078210
0x18007820d  mov     r12d, r13d
0x180078210  mov     ecx, r12d; cb
0x180078213  call    cs:__imp_CoTaskMemAlloc
0x180078219  mov     r14, rax
0x18007821c  test    rax, rax
0x18007821f  jnz     short loc_180078230
0x180078221  mov     r14, [rsp+0B8h+var_58]
0x180078226  mov     ebx, 8007000Eh
0x18007822b  xor     r12d, r12d
0x18007822e  jmp     short loc_18007828B
0x180078230  mov     [rsp+0B8h+var_58], r14
0x180078235  test    rdi, rdi
0x180078238  jz      short loc_180078254
0x18007823a  mov     r8, rbp; Size
0x18007823d  mov     rdx, rdi; Src
0x180078240  mov     rcx, r14; void *
0x180078243  call    memcpy_0
0x180078248  lea     rax, [r14+rbp]
0x18007824c  xor     ecx, ecx
0x18007824e  mov     [rax], ecx
0x180078250  lea     r14, [rax+4]
0x180078254  mov     rdx, [rsp+0B8h+var_48]; Src
0x180078259  mov     rcx, r14; void *
0x18007825c  mov     r8d, r13d; Size
0x18007825f  call    memcpy_0
0x180078264  mov     r14, [rsp+0B8h+var_58]
0x180078269  mov     ebp, r12d
0x18007826c  xor     r12d, r12d
0x18007826f  mov     rdi, r14
0x180078272  mov     ebx, r12d
0x180078275  jmp     short loc_18007828B
0x180078277  mov     ebx, 80004005h
0x18007827c  mov     ebp, dword ptr [rsp+0B8h+Size]
0x180078283  mov     rdi, [rsp+0B8h+Src]
0x18007828b  movzx   eax, [rsp+0B8h+arg_28]
0x180078293  mov     rcx, [rsp+0B8h+arg_0]
0x18007829b  movzx   r8d, [rsp+0B8h+arg_10]
0x1800782a4  movzx   edx, [rsp+0B8h+arg_8]
0x1800782ac  mov     r9d, [rsp+0B8h+arg_18]
0x1800782b4  mov     rcx, [rcx+8]
0x1800782b8  mov     [rsp+0B8h+var_68], ebp
0x1800782bc  mov     [rsp+0B8h+var_70], rdi
0x1800782c1  mov     [rsp+0B8h+var_78], eax
0x1800782c5  mov     [rsp+0B8h+var_80], rsi
0x1800782ca  call    NetpEventlogWriteEx3
0x1800782cf  test    eax, eax
0x1800782d1  jz      short loc_1800782EB
0x1800782d3  cmp     eax, 0B7h
0x1800782d8  jz      short loc_1800782EB
0x1800782da  test    eax, eax
0x1800782dc  jg      short loc_1800782E2
0x1800782de  mov     ebx, eax
0x1800782e0  jmp     short loc_1800782EB
0x1800782e2  movzx   ebx, ax
0x1800782e5  or      ebx, 80070000h
0x1800782eb  test    ebx, ebx
0x1800782ed  jns     short loc_18007830A
0x1800782ef  mov     r9d, 7D3h; unsigned int
0x1800782f5  lea     r8, aComComplusDtcS_3; "com\\complus\\dtc\\shared\\util\\basetm"...
0x1800782fc  lea     rdx, aWritetoeventlo; "WriteToEventLogger failed"
0x180078303  mov     ecx, ebx; int
0x180078305  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18007830a  test    rsi, rsi
0x18007830d  jz      short loc_18007833E
0x18007830f  mov     edi, r12d
0x180078312  cmp     r12w, [rsp+0B8h+arg_28]
0x18007831b  jnb     short loc_180078336
0x18007831d  movzx   ecx, di
0x180078320  mov     rcx, [rsi+rcx*8]; Block
0x180078324  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078329  inc     di
0x18007832c  cmp     di, [rsp+0B8h+arg_28]
0x180078334  jb      short loc_18007831D
0x180078336  mov     rcx, rsi; Block
0x180078339  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007833e  mov     rcx, [rsp+0B8h+pv]; pv
0x180078343  call    cs:__imp_CoTaskMemFree
0x180078349  mov     rcx, r14; pv
0x18007834c  call    cs:__imp_CoTaskMemFree
0x180078352  mov     eax, ebx
0x180078354  add     rsp, 80h
0x18007835b  pop     r14
0x18007835d  pop     r13
0x18007835f  pop     r12
0x180078361  pop     rdi
0x180078362  pop     rsi
0x180078363  pop     rbp
0x180078364  pop     rbx
0x180078365  retn
```
