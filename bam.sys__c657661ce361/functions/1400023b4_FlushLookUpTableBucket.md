# FlushLookUpTableBucket

- ea: `0x1400023b4`
- end: `0x1400024cb`
- name: `FlushLookUpTableBucket`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400132ac`
- `0x1400136dc`

## callees

- `0x1400023b4`
- `0x14000ee14`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400023e8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400023e8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002496`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002496`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140002485`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140002485`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002404`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002404`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v5; // r14
  KIRQL v6; // bp
  const EVENT_DESCRIPTOR *v7; // rsi
  unsigned int v8; // edi
  const EVENT_DESCRIPTOR **p_Keyword; // rcx
  const EVENT_DESCRIPTOR *v10; // rdx
  const EVENT_DESCRIPTOR *v11; // r8
  const EVENT_DESCRIPTOR *v12; // rdx
  const EVENT_DESCRIPTOR **v13; // rax
  const EVENT_DESCRIPTOR *v14; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = a1 + 272;
  v6 = 0;
  ExAcquirePushLockExclusiveEx(a1 + 272, 0);
  if ( !*(_BYTE *)(a1 + 373) )
    v6 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 280));
  v7 = *(const EVENT_DESCRIPTOR **)(a1 + 8 * v2);
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v8 = 0;
  v14 = v7;
  if ( v7 )
  {
    p_Keyword = &v14;
    v10 = v7;
    do
    {
      v11 = *(const EVENT_DESCRIPTOR **)&v10[2].Id;
      *(_QWORD *)&v10[2].Id = 0;
      p_Keyword = (const EVENT_DESCRIPTOR **)&(*p_Keyword)[1].Keyword;
      v12 = *p_Keyword;
      if ( *p_Keyword )
      {
        do
        {
          v13 = (const EVENT_DESCRIPTOR **)&v12[2];
          v12 = *(const EVENT_DESCRIPTOR **)&v12[2].Id;
        }
        while ( v12 );
      }
      else
      {
        v13 = p_Keyword;
      }
      *v13 = v11;
      ++v8;
      v10 = *p_Keyword;
    }
    while ( *p_Keyword );
  }
  *(_DWORD *)(a1 + 256) -= v8;
  if ( !*(_BYTE *)(a1 + 373) )
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 280), v6);
  ExReleasePushLockExclusiveEx(v5, 0);
  FlushEventEntryList(*(_QWORD *)(*(_QWORD *)(a1 + 344) + 32LL), v7);
  return v8;
}

```

## disassembly

```asm
0x1400023b4  mov     [rsp+arg_8], rbx
0x1400023b9  mov     [rsp+arg_10], rbp
0x1400023be  push    rsi
0x1400023bf  push    rdi
0x1400023c0  push    r14
0x1400023c2  sub     rsp, 20h
0x1400023c6  mov     edi, edx
0x1400023c8  mov     rbx, rcx
0x1400023cb  cmp     qword ptr [rcx+rdi*8], 0
0x1400023d0  jnz     short loc_1400023D9
0x1400023d2  xor     eax, eax
0x1400023d4  jmp     loc_1400024B7
0x1400023d9  lea     r14, [rcx+110h]
0x1400023e0  xor     edx, edx
0x1400023e2  mov     rcx, r14
0x1400023e5  xor     bpl, bpl
0x1400023e8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400023ef  nop     dword ptr [rax+rax+00h]
0x1400023f4  cmp     [rbx+175h], bpl
0x1400023fb  jnz     short loc_140002413
0x1400023fd  lea     rcx, [rbx+118h]; SpinLock
0x140002404  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000240b  nop     dword ptr [rax+rax+00h]
0x140002410  mov     bpl, al
0x140002413  mov     rsi, [rbx+rdi*8]
0x140002417  mov     qword ptr [rbx+rdi*8], 0
0x14000241f  xor     edi, edi
0x140002421  mov     [rsp+38h+arg_0], rsi
0x140002426  test    rsi, rsi
0x140002429  jz      short loc_14000246C
0x14000242b  lea     rcx, [rsp+38h+arg_0]
0x140002430  mov     rdx, rsi
0x140002433  mov     r8, [rdx+20h]
0x140002437  mov     qword ptr [rdx+20h], 0
0x14000243f  mov     rcx, [rcx]
0x140002442  add     rcx, 18h
0x140002446  mov     rdx, [rcx]
0x140002449  test    rdx, rdx
0x14000244c  jz      short loc_14000245C
0x14000244e  lea     rax, [rdx+20h]
0x140002452  mov     rdx, [rax]
0x140002455  test    rdx, rdx
0x140002458  jnz     short loc_14000244E
0x14000245a  jmp     short loc_14000245F
0x14000245c  mov     rax, rcx
0x14000245f  mov     [rax], r8
0x140002462  inc     edi
0x140002464  mov     rdx, [rcx]
0x140002467  test    rdx, rdx
0x14000246a  jnz     short loc_140002433
0x14000246c  sub     [rbx+100h], edi
0x140002472  cmp     byte ptr [rbx+175h], 0
0x140002479  jnz     short loc_140002491
0x14000247b  lea     rcx, [rbx+118h]; SpinLock
0x140002482  mov     dl, bpl; OldIrql
0x140002485  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000248c  nop     dword ptr [rax+rax+00h]
0x140002491  xor     edx, edx
0x140002493  mov     rcx, r14
0x140002496  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000249d  nop     dword ptr [rax+rax+00h]
0x1400024a2  mov     rcx, [rbx+158h]
0x1400024a9  mov     rdx, rsi; EventDescriptor
0x1400024ac  mov     rcx, [rcx+20h]; RegHandle
0x1400024b0  call    FlushEventEntryList
0x1400024b5  mov     eax, edi
0x1400024b7  mov     rbx, [rsp+38h+arg_8]
0x1400024bc  mov     rbp, [rsp+38h+arg_10]
0x1400024c1  add     rsp, 20h
0x1400024c5  pop     r14
0x1400024c7  pop     rdi
0x1400024c8  pop     rsi
0x1400024c9  retn
```
