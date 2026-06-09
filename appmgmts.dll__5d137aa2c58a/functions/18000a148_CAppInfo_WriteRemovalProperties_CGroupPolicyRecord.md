# CAppInfo::WriteRemovalProperties(CGroupPolicyRecord *)

- ea: `0x18000a148`
- end: `0x18000a2a0`
- name: `?WriteRemovalProperties@CAppInfo@@QEAAJPEAVCGroupPolicyRecord@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(CAppInfo *this, struct CGroupPolicyRecord *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009584`
- `0x18000a7c0`

## callees

- `0x18000a148`
- `0x18001b1a0`
- `0x180029cc0`
- `0x180029eb4`
- `0x180029fd0`

## pseudocode

```c
__int64 __fastcall CAppInfo::WriteRemovalProperties(CAppInfo *this, struct CGroupPolicyRecord *a2)
{
  int v2; // r8d
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // r8
  int v12; // eax

  v2 = *((_DWORD *)this + 96);
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 440LL) != 4 )
  {
    if ( v2 == 2 )
    {
      v5 = 3 - (*((_DWORD *)this + 57) != 4);
      goto LABEL_9;
    }
    if ( v2 != 6 )
    {
      v6 = *((_DWORD *)this + 57);
      if ( v6 == 5 )
      {
        v5 = 4;
        goto LABEL_9;
      }
      if ( v6 != 4 )
        return 0;
    }
  }
  v5 = 3;
LABEL_9:
  v7 = CGroupPolicyRecord::SetValue(a2, L"RemovalCause", v2);
  if ( v7 < 0 && *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC29u, L"RemovalCause", (unsigned int)v7);
  v8 = CGroupPolicyRecord::SetValue(a2, L"RemovalType", v5);
  if ( v8 < 0 && *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC29u, L"RemovalType", (unsigned int)v8);
  v9 = CGroupPolicyRecord::ClearValue(a2, L"PrecedenceReason");
  v10 = v9;
  if ( v9 < 0 && *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC29u, L"PrecedenceReason", (unsigned int)v9);
  v11 = (const unsigned __int16 *)*((_QWORD *)this + 49);
  if ( v11 )
  {
    v12 = CGroupPolicyRecord::SetValue(a2, L"RemovingApplication", v11);
    v10 = v12;
    if ( v12 < 0 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"RemovingApplication", (unsigned int)v12);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000a148  push    rbx
0x18000a14a  push    rsi
0x18000a14b  push    rdi
0x18000a14c  push    r14
0x18000a14e  sub     rsp, 28h
0x18000a152  mov     rax, [rcx+10h]
0x18000a156  mov     r14d, 4
0x18000a15c  mov     r8d, [rcx+180h]; int
0x18000a163  mov     rsi, rdx
0x18000a166  mov     rdi, rcx
0x18000a169  cmp     [rax+1B8h], r14d
0x18000a170  jz      short loc_18000A1AC
0x18000a172  cmp     r8d, 2
0x18000a176  jnz     short loc_18000A18D
0x18000a178  mov     eax, r14d
0x18000a17b  lea     ebx, [r8+1]
0x18000a17f  sub     eax, [rcx+0E4h]
0x18000a185  neg     eax
0x18000a187  sbb     eax, eax
0x18000a189  add     ebx, eax
0x18000a18b  jmp     short loc_18000A1B1
0x18000a18d  cmp     r8d, 6
0x18000a191  jz      short loc_18000A1AC
0x18000a193  mov     eax, [rcx+0E4h]
0x18000a199  cmp     eax, 5
0x18000a19c  jnz     short loc_18000A1A3
0x18000a19e  mov     ebx, r14d
0x18000a1a1  jmp     short loc_18000A1B1
0x18000a1a3  cmp     eax, r14d
0x18000a1a6  jnz     loc_18000A294
0x18000a1ac  mov     ebx, 3
0x18000a1b1  lea     rdx, aRemovalcause; "RemovalCause"
0x18000a1b8  mov     rcx, rsi; this
0x18000a1bb  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000a1c0  test    eax, eax
0x18000a1c2  jns     short loc_18000A1E4
0x18000a1c4  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000a1cb  jz      short loc_18000A1E4
0x18000a1cd  mov     r9d, eax
0x18000a1d0  lea     r8, aRemovalcause; "RemovalCause"
0x18000a1d7  mov     edx, 0C29h; unsigned int
0x18000a1dc  mov     ecx, r14d; unsigned int
0x18000a1df  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a1e4  mov     r8d, ebx; int
0x18000a1e7  lea     rdx, aRemovaltype; "RemovalType"
0x18000a1ee  mov     rcx, rsi; this
0x18000a1f1  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000a1f6  test    eax, eax
0x18000a1f8  jns     short loc_18000A21A
0x18000a1fa  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000a201  jz      short loc_18000A21A
0x18000a203  mov     r9d, eax
0x18000a206  lea     r8, aRemovaltype; "RemovalType"
0x18000a20d  mov     edx, 0C29h; unsigned int
0x18000a212  mov     ecx, r14d; unsigned int
0x18000a215  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a21a  lea     rdx, aPrecedencereas; "PrecedenceReason"
0x18000a221  mov     rcx, rsi; this
0x18000a224  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000a229  mov     ebx, eax
0x18000a22b  test    eax, eax
0x18000a22d  jns     short loc_18000A24F
0x18000a22f  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000a236  jz      short loc_18000A24F
0x18000a238  mov     r9d, eax
0x18000a23b  lea     r8, aPrecedencereas; "PrecedenceReason"
0x18000a242  mov     edx, 0C29h; unsigned int
0x18000a247  mov     ecx, r14d; unsigned int
0x18000a24a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a24f  mov     r8, [rdi+188h]; unsigned __int16 *
0x18000a256  test    r8, r8
0x18000a259  jz      short loc_18000A290
0x18000a25b  lea     rdx, aRemovingapplic; "RemovingApplication"
0x18000a262  mov     rcx, rsi; this
0x18000a265  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x18000a26a  mov     ebx, eax
0x18000a26c  test    eax, eax
0x18000a26e  jns     short loc_18000A290
0x18000a270  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000a277  jz      short loc_18000A290
0x18000a279  mov     r9d, eax
0x18000a27c  lea     r8, aRemovingapplic; "RemovingApplication"
0x18000a283  mov     edx, 0C29h; unsigned int
0x18000a288  mov     ecx, r14d; unsigned int
0x18000a28b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a290  mov     eax, ebx
0x18000a292  jmp     short loc_18000A296
0x18000a294  xor     eax, eax
0x18000a296  add     rsp, 28h
0x18000a29a  pop     r14
0x18000a29c  pop     rdi
0x18000a29d  pop     rsi
0x18000a29e  pop     rbx
0x18000a29f  retn
```
