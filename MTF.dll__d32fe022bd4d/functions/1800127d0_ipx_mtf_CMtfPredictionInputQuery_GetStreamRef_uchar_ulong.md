# ipx::mtf::CMtfPredictionInputQuery::GetStreamRef(uchar * *,ulong *)

- ea: `0x1800127d0`
- end: `0x180012973`
- name: `?GetStreamRef@CMtfPredictionInputQuery@mtf@ipx@@UEAAJPEAPEAEPEAK@Z`
- size: `419`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfPredictionInputQuery *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012980`

## callees

- `0x180002966`
- `0x180002d88`
- `0x180006074`
- `0x1800127d0`
- `0x180013a10`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180012948`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180012948`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012893`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012893`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012806`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012806`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800128b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800128b5`

## string_xrefs

- `0x180012875`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\MtfPrecompile.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ipx::mtf::CMtfPredictionInputQuery::GetStreamRef(RTL_SRWLOCK *this, PVOID *a2, unsigned int *a3)
{
  RTL_SRWLOCK *v6; // rsi
  PVOID Ptr; // rcx
  int v8; // eax
  const char *v9; // r9
  void *v10; // rdi
  unsigned __int64 v12; // rcx
  PVOID v13; // r14
  int v14; // [rsp+20h] [rbp-58h]
  void *Src[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v18; // [rsp+88h] [rbp+10h] BYREF
  RTL_SRWLOCK *v19; // [rsp+98h] [rbp+20h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = this + 16;
  AcquireSRWLockExclusive(this + 16);
  v19 = v6;
  if ( !this[17].Ptr )
  {
    Ptr = this[21].Ptr;
    if ( Ptr )
    {
      try
      {
        *(_OWORD *)Src = 0;
        v16 = 0;
        v18 = 0;
        v8 = (*(__int64 (__fastcall **)(PVOID, __int64 *, unsigned int *))(*(_QWORD *)Ptr + 32LL))(
               Ptr,
               qword_180034E38,
               &v18);
        if ( v8 != -2143288319 )
        {
          if ( v8 >= 0 )
          {
            std::vector<unsigned char>::resize(Src, v18);
            v10 = Src[0];
            if ( (*(int (__fastcall **)(PVOID, __int64 *, void *, _QWORD))(*(_QWORD *)this[21].Ptr + 40LL))(
                   this[21].Ptr,
                   qword_180034E38,
                   Src[0],
                   v18) >= 0 )
            {
              v12 = (unsigned int)(LODWORD(Src[1]) - (_DWORD)v10);
              LODWORD(this[18].Ptr) = v12;
              v13 = operator new[](v12);
              if ( v13 == this[17].Ptr )
              {
                v13 = this[17].Ptr;
              }
              else
              {
                operator delete[](this[17].Ptr);
                this[17].Ptr = v13;
              }
              memcpy_0(v13, v10, LODWORD(this[18].Ptr));
            }
            goto LABEL_10;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\MtfPrecompile.h",
            (const char *)(unsigned int)v8,
            v14);
        }
        v10 = Src[0];
LABEL_10:
        if ( v10 )
          operator delete(v10);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x142,
                               (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\inputquery.cpp",
                               v9);
      }
    }
  }
  *a2 = this[17].Ptr;
  *a3 = (unsigned int)this[18].Ptr;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  return 0;
}

```

## disassembly

```asm
0x1800127d0  mov     [rsp+arg_0], rbx
0x1800127d5  push    rsi
0x1800127d6  push    rdi
0x1800127d7  push    r12
0x1800127d9  push    r14
0x1800127db  push    r15
0x1800127dd  sub     rsp, 50h
0x1800127e1  mov     r15, r8
0x1800127e4  mov     r12, rdx
0x1800127e7  mov     rbx, rcx
0x1800127ea  test    rdx, rdx
0x1800127ed  jz      loc_1800128BF
0x1800127f3  test    r8, r8
0x1800127f6  jz      loc_1800128BF
0x1800127fc  lea     rsi, [rcx+80h]
0x180012803  mov     rcx, rsi; SRWLock
0x180012806  call    cs:__imp_AcquireSRWLockExclusive
0x18001280c  mov     [rsp+78h+arg_18], rsi
0x180012814  cmp     qword ptr [rbx+88h], 0
0x18001281c  jnz     short loc_180012899
0x18001281e  mov     rcx, [rbx+0A8h]
0x180012825  test    rcx, rcx
0x180012828  jz      short loc_180012899
0x18001282a  xorps   xmm0, xmm0
0x18001282d  movdqu  xmmword ptr [rsp+78h+Src], xmm0
0x180012833  mov     [rsp+78h+var_38], 0
0x18001283c  mov     [rsp+78h+arg_8], 0
0x180012847  mov     rax, [rcx]
0x18001284a  lea     r8, [rsp+78h+arg_8]
0x180012852  lea     rdx, qword_180034E38
0x180012859  mov     rax, [rax+20h]
0x18001285d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012862  cmp     eax, 80400401h
0x180012867  jz      short loc_180012886
0x180012869  test    eax, eax
0x18001286b  jns     short loc_1800128E2
0x18001286d  mov     rcx, [rsp+78h]; this
0x180012872  mov     r9d, eax; char *
0x180012875  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001287c  mov     edx, 0C0h; void *
0x180012881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012886  mov     rdi, [rsp+78h+Src]
0x18001288b  test    rdi, rdi
0x18001288e  jz      short loc_180012899
0x180012890  mov     rcx, rdi
0x180012893  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012899  mov     rax, [rbx+88h]
0x1800128a0  mov     [r12], rax
0x1800128a4  mov     eax, [rbx+90h]
0x1800128aa  mov     [r15], eax
0x1800128ad  test    rsi, rsi
0x1800128b0  jz      short loc_1800128BB
0x1800128b2  mov     rcx, rsi; SRWLock
0x1800128b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800128bb  xor     eax, eax
0x1800128bd  jmp     short loc_1800128CD
0x1800128bf  mov     eax, 80070057h
0x1800128c4  jmp     short loc_1800128CD
0x1800128c6  mov     eax, [rsp+78h+arg_8]
0x1800128cd  mov     rbx, [rsp+78h+arg_0]
0x1800128d5  add     rsp, 50h
0x1800128d9  pop     r15
0x1800128db  pop     r14
0x1800128dd  pop     r12
0x1800128df  pop     rdi
0x1800128e0  pop     rsi
0x1800128e1  retn
0x1800128e2  mov     edx, [rsp+78h+arg_8]
0x1800128e9  lea     rcx, [rsp+78h+Src]
0x1800128ee  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800128f3  mov     rcx, [rbx+0A8h]
0x1800128fa  mov     rax, [rcx]
0x1800128fd  mov     r9d, [rsp+78h+arg_8]
0x180012905  mov     rdi, [rsp+78h+Src]
0x18001290a  mov     r8, rdi
0x18001290d  lea     rdx, qword_180034E38
0x180012914  mov     rax, [rax+28h]
0x180012918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001291d  test    eax, eax
0x18001291f  js      loc_18001288B
0x180012925  mov     ecx, dword ptr [rsp+78h+Src+8]
0x180012929  sub     ecx, edi; unsigned __int64
0x18001292b  mov     [rbx+90h], ecx
0x180012931  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012936  mov     r14, rax
0x180012939  mov     rax, [rbx+88h]
0x180012940  cmp     r14, rax
0x180012943  jz      short loc_180012957
0x180012945  mov     rcx, rax
0x180012948  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001294e  mov     [rbx+88h], r14
0x180012955  jmp     short loc_18001295A
0x180012957  mov     r14, rax
0x18001295a  mov     r8d, [rbx+90h]; Size
0x180012961  mov     rdx, rdi; Src
0x180012964  mov     rcx, r14; void *
0x180012967  call    memcpy_0
0x18001296c  jmp     loc_18001288B
```
