# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x180001d30`
- end: `0x180001d8c`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043b8`

## callees

- `0x180001d30`
- `0x180006010`

## pseudocode

```c
_BOOL8 __fastcall WWWServerTraceProvider::CheckTracingEnabled(
        int (__fastcall ***a1)(_QWORD, GUID **),
        __int64 a2,
        unsigned int a3)
{
  int (__fastcall **v3)(_QWORD, GUID **); // rax
  GUID *v6; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+28h] [rbp-20h]

  v6 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v3 = *a1;
  v7 = 0;
  return (*v3)(a1, &v6) >= 0 && DWORD2(v7) && DWORD1(v7) >= a3 && ((_DWORD)v7 == 2 || (v7 & 2) != 0);
}

```

## disassembly

```asm
0x180001d30  push    rbx
0x180001d32  sub     rsp, 40h
0x180001d36  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001d3d  xorps   xmm0, xmm0
0x180001d40  mov     [rsp+48h+var_28], rax
0x180001d45  lea     rdx, [rsp+48h+var_28]
0x180001d4a  mov     rax, [rcx]
0x180001d4d  mov     ebx, r8d
0x180001d50  movdqu  [rsp+48h+var_20], xmm0
0x180001d56  mov     rax, [rax]
0x180001d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5e  test    eax, eax
0x180001d60  js      short loc_180001D69
0x180001d62  cmp     dword ptr [rsp+48h+var_20+8], 0
0x180001d67  jnz     short loc_180001D71
0x180001d69  xor     eax, eax
0x180001d6b  add     rsp, 40h
0x180001d6f  pop     rbx
0x180001d70  retn
0x180001d71  cmp     dword ptr [rsp+48h+var_20+4], ebx
0x180001d75  jb      short loc_180001D69
0x180001d77  mov     rax, qword ptr [rsp+48h+var_20]
0x180001d7c  cmp     eax, 2
0x180001d7f  jz      short loc_180001D85
0x180001d81  test    al, 2
0x180001d83  jz      short loc_180001D69
0x180001d85  mov     eax, 1
0x180001d8a  jmp     short loc_180001D6B
```
