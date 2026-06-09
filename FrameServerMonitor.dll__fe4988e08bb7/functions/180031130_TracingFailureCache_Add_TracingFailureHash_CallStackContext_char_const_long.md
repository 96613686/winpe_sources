# TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x180031130`
- end: `0x180031225`
- name: `?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `245`
- prototype: `char __fastcall(TracingFailureCache *this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003180c`

## callees

- `0x18000232e`
- `0x180030e58`
- `0x180031130`
- `0x1800312e0`
- `0x180031540`
- `0x180031654`
- `0x1800317c4`
- `0x18004bf44`

## import_xrefs

- `MFPlat!MFGetSystemTime` at `0x18003117b`
- `MFPlat!MFGetSystemTime` at `0x18003117b`

## pseudocode

```c
char __fastcall TracingFailureCache::Add(
        TracingFailureCache *this,
        struct TracingFailureHash *a2,
        struct CallStackContext *a3,
        const char *a4,
        int a5)
{
  __int64 v8; // rdx
  __int64 v9; // rdi
  MFTIME v10; // rax
  _OWORD Buf1[3]; // [rsp+20h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 10) == 28 )
    TracingFailureCache::EvictOldest(this, (unsigned int)a2);
  if ( *((_DWORD *)this + 10) < 0x1Cu )
  {
    v8 = *((_QWORD *)this + 11);
    if ( v8 )
    {
      v9 = v8 + 2328LL * *((unsigned int *)this + 10);
      TracingFailureDetails::Reset((TracingFailureDetails *)v9);
      v10 = MFGetSystemTime();
      ++*(_DWORD *)(v9 + 2304);
      *(_QWORD *)(v9 + 2296) = v10;
      CallStackContext::CloneFrom((CallStackContext *)v9, a3);
      if ( a4 )
      {
        if ( !TracingFailureDetails::HashFunctionTemplate(a4, (char *)(v9 + 2032)) )
          o_strncpy_s_0(v9 + 2032, 256, a4, -1);
      }
      else
      {
        *(_BYTE *)(v9 + 2032) = 0;
      }
      *(_DWORD *)(v9 + 2288) = a5;
      TracingFailureDetails::GenerateHashCodeForContext(
        (struct CallStackContext *)v9,
        (struct TracingFailureHash *)(v9 + 2309));
      ++*((_DWORD *)this + 10);
      Buf1[0] = *((_OWORD *)a3 + 125);
      if ( !memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
        ++*((_DWORD *)this + 12);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180031130  push    rbx
0x180031132  push    rbp
0x180031133  push    rsi
0x180031134  push    rdi
0x180031135  push    r14
0x180031137  sub     rsp, 30h
0x18003113b  cmp     dword ptr [rcx+28h], 1Ch
0x18003113f  mov     rbp, r9
0x180031142  mov     r14, r8
0x180031145  mov     rbx, rcx
0x180031148  jnz     short loc_18003114F
0x18003114a  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x18003114f  cmp     dword ptr [rbx+28h], 1Ch
0x180031153  jnb     loc_180031218
0x180031159  mov     rdx, [rbx+58h]
0x18003115d  test    rdx, rdx
0x180031160  jz      loc_180031218
0x180031166  mov     eax, [rbx+28h]
0x180031169  imul    rdi, rax, 918h
0x180031170  add     rdi, rdx
0x180031173  mov     rcx, rdi; this
0x180031176  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18003117b  call    cs:__imp_MFGetSystemTime
0x180031181  inc     dword ptr [rdi+900h]
0x180031187  mov     rdx, r14; struct CallStackContext *
0x18003118a  mov     rcx, rdi; this
0x18003118d  mov     [rdi+8F8h], rax
0x180031194  call    ?CloneFrom@CallStackContext@@QEAAXAEBV1@@Z; CallStackContext::CloneFrom(CallStackContext const &)
0x180031199  lea     rsi, [rdi+7F0h]
0x1800311a0  test    rbp, rbp
0x1800311a3  jz      short loc_1800311CA
0x1800311a5  mov     rdx, rsi; char *
0x1800311a8  mov     rcx, rbp; char *
0x1800311ab  call    ?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z; TracingFailureDetails::HashFunctionTemplate(char const *,char *)
0x1800311b0  test    al, al
0x1800311b2  jnz     short loc_1800311CD
0x1800311b4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800311b8  mov     r8, rbp
0x1800311bb  mov     edx, 100h
0x1800311c0  mov     rcx, rsi
0x1800311c3  call    _o_strncpy_s_0
0x1800311c8  jmp     short loc_1800311CD
0x1800311ca  mov     byte ptr [rsi], 0
0x1800311cd  mov     eax, [rsp+58h+arg_20]
0x1800311d4  lea     rdx, [rdi+905h]; struct TracingFailureHash *
0x1800311db  mov     rcx, rdi; struct CallStackContext *
0x1800311de  mov     [rdi+8F0h], eax
0x1800311e4  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x1800311e9  inc     dword ptr [rbx+28h]
0x1800311ec  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800311f3  movups  xmm0, xmmword ptr [r14+7D0h]
0x1800311fb  mov     r8d, 10h; Size
0x180031201  lea     rcx, [rsp+58h+Buf1]; Buf1
0x180031206  movdqu  [rsp+58h+Buf1], xmm0
0x18003120c  call    memcmp_0
0x180031211  test    eax, eax
0x180031213  jnz     short loc_180031218
0x180031215  inc     dword ptr [rbx+30h]
0x180031218  mov     al, 1
0x18003121a  add     rsp, 30h
0x18003121e  pop     r14
0x180031220  pop     rdi
0x180031221  pop     rsi
0x180031222  pop     rbp
0x180031223  pop     rbx
0x180031224  retn
```
