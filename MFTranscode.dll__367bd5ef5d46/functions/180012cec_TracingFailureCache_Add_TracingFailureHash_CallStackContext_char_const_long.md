# TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x180012cec`
- end: `0x180012de1`
- name: `?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `245`
- prototype: `bool(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180059060`

## callees

- `0x180012cec`
- `0x180012de8`
- `0x180017e08`
- `0x18004f25c`
- `0x180058c10`
- `0x180058ea8`
- `0x180059018`
- `0x1800594b0`

## import_xrefs

- `MFPlat!MFGetSystemTime` at `0x180012d37`
- `MFPlat!MFGetSystemTime` at `0x180012d37`

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
0x180012cec  push    rbx
0x180012cee  push    rbp
0x180012cef  push    rsi
0x180012cf0  push    rdi
0x180012cf1  push    r14
0x180012cf3  sub     rsp, 30h
0x180012cf7  cmp     dword ptr [rcx+28h], 1Ch
0x180012cfb  mov     rbp, r9
0x180012cfe  mov     r14, r8
0x180012d01  mov     rbx, rcx
0x180012d04  jnz     short loc_180012D0B
0x180012d06  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x180012d0b  cmp     dword ptr [rbx+28h], 1Ch
0x180012d0f  jnb     loc_180012DD4
0x180012d15  mov     rdx, [rbx+58h]
0x180012d19  test    rdx, rdx
0x180012d1c  jz      loc_180012DD4
0x180012d22  mov     eax, [rbx+28h]
0x180012d25  imul    rdi, rax, 918h
0x180012d2c  add     rdi, rdx
0x180012d2f  mov     rcx, rdi; this
0x180012d32  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x180012d37  call    cs:__imp_MFGetSystemTime
0x180012d3d  inc     dword ptr [rdi+900h]
0x180012d43  mov     rdx, r14; struct CallStackContext *
0x180012d46  mov     rcx, rdi; this
0x180012d49  mov     [rdi+8F8h], rax
0x180012d50  call    ?CloneFrom@CallStackContext@@QEAAXAEBV1@@Z; CallStackContext::CloneFrom(CallStackContext const &)
0x180012d55  lea     rsi, [rdi+7F0h]
0x180012d5c  test    rbp, rbp
0x180012d5f  jz      short loc_180012D86
0x180012d61  mov     rdx, rsi; char *
0x180012d64  mov     rcx, rbp; char *
0x180012d67  call    ?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z; TracingFailureDetails::HashFunctionTemplate(char const *,char *)
0x180012d6c  test    al, al
0x180012d6e  jnz     short loc_180012D89
0x180012d70  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012d74  mov     r8, rbp
0x180012d77  mov     edx, 100h
0x180012d7c  mov     rcx, rsi
0x180012d7f  call    _o_strncpy_s_0
0x180012d84  jmp     short loc_180012D89
0x180012d86  mov     byte ptr [rsi], 0
0x180012d89  mov     eax, [rsp+58h+arg_20]
0x180012d90  lea     rdx, [rdi+905h]; struct TracingFailureHash *
0x180012d97  mov     rcx, rdi; struct CallStackContext *
0x180012d9a  mov     [rdi+8F0h], eax
0x180012da0  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x180012da5  inc     dword ptr [rbx+28h]
0x180012da8  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180012daf  movups  xmm0, xmmword ptr [r14+7D0h]
0x180012db7  mov     r8d, 10h; Size
0x180012dbd  lea     rcx, [rsp+58h+Buf1]; Buf1
0x180012dc2  movdqu  [rsp+58h+Buf1], xmm0
0x180012dc8  call    memcmp_0
0x180012dcd  test    eax, eax
0x180012dcf  jnz     short loc_180012DD4
0x180012dd1  inc     dword ptr [rbx+30h]
0x180012dd4  mov     al, 1
0x180012dd6  add     rsp, 30h
0x180012dda  pop     r14
0x180012ddc  pop     rdi
0x180012ddd  pop     rsi
0x180012dde  pop     rbp
0x180012ddf  pop     rbx
0x180012de0  retn
```
