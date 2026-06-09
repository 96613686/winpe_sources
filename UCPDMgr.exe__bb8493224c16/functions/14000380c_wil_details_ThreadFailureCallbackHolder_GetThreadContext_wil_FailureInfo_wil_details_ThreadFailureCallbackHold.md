# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000380c`
- end: `0x140003901`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000380c`
- `0x140003910`

## callees

- `0x14000380c`
- `0x14000f340`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // rbx
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // rcx
  rsize_t v17; // rbx

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v10;
        while ( v15[v10] );
        v16 = v10 + 1;
        v17 = v11 - v14;
        if ( v16 < v11 - v14 )
          v17 = v16;
        memcpy_s(v14, v11 - v14, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000380c  mov     [rsp+arg_0], rbx
0x140003811  mov     [rsp+arg_8], rbp
0x140003816  mov     [rsp+arg_10], rsi
0x14000381b  push    rdi
0x14000381c  sub     rsp, 20h
0x140003820  xor     al, al
0x140003822  mov     byte ptr [r8], 0
0x140003826  mov     rbp, r9
0x140003829  mov     rbx, r8
0x14000382c  mov     rsi, rdx
0x14000382f  mov     rdi, rcx
0x140003832  test    rdx, rdx
0x140003835  jz      loc_1400038EC
0x14000383b  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000383f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003844  mov     rdx, [rsi+20h]
0x140003848  test    rdx, rdx
0x14000384b  jz      loc_1400038EC
0x140003851  cmp     dword ptr [rdx], 0
0x140003854  jnz     short loc_140003867
0x140003856  mov     eax, 1
0x14000385b  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003863  inc     eax
0x140003865  mov     [rdx], eax
0x140003867  cmp     dword ptr [rdi+50h], 0
0x14000386b  jnz     short loc_14000387E
0x14000386d  movups  xmm0, xmmword ptr [rdx]
0x140003870  movups  xmmword ptr [rdi+50h], xmm0
0x140003874  movsd   xmm1, qword ptr [rdx+10h]
0x140003879  movsd   qword ptr [rdi+60h], xmm1
0x14000387e  movups  xmm0, xmmword ptr [rdx]
0x140003881  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140003885  lea     r10, [rbx+rbp]
0x140003889  mov     rax, rcx
0x14000388c  movups  xmmword ptr [rdi+68h], xmm0
0x140003890  movsd   xmm1, qword ptr [rdx+10h]
0x140003895  movsd   qword ptr [rdi+78h], xmm1
0x14000389a  inc     rax
0x14000389d  cmp     byte ptr [rbx+rax], 0
0x1400038a1  jnz     short loc_14000389A
0x1400038a3  add     rbx, rax
0x1400038a6  mov     rax, r10
0x1400038a9  sub     rax, rbx
0x1400038ac  cmp     rax, 2
0x1400038b0  jle     short loc_1400038EA
0x1400038b2  mov     byte ptr [rbx], 5Ch ; '\'
0x1400038b5  lea     rdi, [rbx+1]
0x1400038b9  mov     r8, [rdx+8]; Source
0x1400038bd  inc     rcx
0x1400038c0  cmp     byte ptr [r8+rcx], 0
0x1400038c5  jnz     short loc_1400038BD
0x1400038c7  inc     rcx
0x1400038ca  sub     r10, rdi
0x1400038cd  cmp     rcx, r10
0x1400038d0  mov     rbx, r10
0x1400038d3  mov     rdx, r10; DestinationSize
0x1400038d6  cmovb   rbx, rcx
0x1400038da  mov     rcx, rdi; Destination
0x1400038dd  mov     r9, rbx; SourceSize
0x1400038e0  call    memcpy_s
0x1400038e5  mov     byte ptr [rbx+rdi-1], 0
0x1400038ea  mov     al, 1
0x1400038ec  mov     rbx, [rsp+28h+arg_0]
0x1400038f1  mov     rbp, [rsp+28h+arg_8]
0x1400038f6  mov     rsi, [rsp+28h+arg_10]
0x1400038fb  add     rsp, 20h
0x1400038ff  pop     rdi
0x140003900  retn
```
