# AddRootMetaDataToSortedList(__ROOT_KEY_METADATA *,_LIST_ENTRY *)

- ea: `0x180004568`
- end: `0x18000461c`
- name: `?AddRootMetaDataToSortedList@@YAJPEAU__ROOT_KEY_METADATA@@PEAU_LIST_ENTRY@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct __ROOT_KEY_METADATA *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800054e0`

## callees

- `0x180004568`
- `0x180010920`
- `0x18001a450`

## string_xrefs

- `0x180004592`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall AddRootMetaDataToSortedList(struct __ROOT_KEY_METADATA *a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rbx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  unsigned int v7; // esi
  struct _LIST_ENTRY *v8; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v10; // rax
  struct _LIST_ENTRY *v11; // rcx

  Flink = a2->Flink;
  v5 = SIDKeyProvAlloc(0x18u);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    *v5 = a1;
    v8 = 0;
    if ( Flink != a2 )
    {
      Blink = Flink[-1].Blink;
      do
      {
        if ( Blink[1].Flink <= (struct _LIST_ENTRY *)*((_QWORD *)a1 + 2) )
          break;
        v8 = Flink;
        Flink = Flink->Flink;
        Blink = Flink[-1].Blink;
      }
      while ( Flink != a2 );
    }
    v10 = (struct _LIST_ENTRY *)(v6 + 1);
    if ( v8 )
    {
      v8->Flink = v10;
      v6[2] = v8;
      v10->Flink = Flink;
      Flink->Blink = v10;
    }
    else
    {
      v11 = a2->Flink;
      if ( a2->Flink->Blink != a2 )
        __fastfail(3u);
      v10->Flink = v11;
      v6[2] = a2;
      v11->Blink = v10;
      a2->Flink = v10;
    }
  }
  else
  {
    v7 = -2147024882;
    SidKeyDebugTraceError(14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 192);
  }
  return v7;
}

```

## disassembly

```asm
0x180004568  push    rbx
0x18000456a  push    rbp
0x18000456b  push    rsi
0x18000456c  push    rdi
0x18000456d  sub     rsp, 28h
0x180004571  mov     rbx, [rdx]
0x180004574  mov     rbp, rcx
0x180004577  mov     ecx, 18h; unsigned __int64
0x18000457c  mov     rdi, rdx
0x18000457f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180004584  mov     rdx, rax
0x180004587  test    rax, rax
0x18000458a  jnz     short loc_1800045B1
0x18000458c  mov     r9d, 5C0h; unsigned int
0x180004592  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180004599  lea     rdx, aHr; "hr"
0x1800045a0  mov     ecx, 8007000Eh; unsigned int
0x1800045a5  mov     esi, 8007000Eh
0x1800045aa  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800045af  jmp     short loc_180004611
0x1800045b1  xor     esi, esi
0x1800045b3  mov     [rax], rbp
0x1800045b6  xor     ecx, ecx
0x1800045b8  cmp     rbx, rdi
0x1800045bb  jz      short loc_1800045DA
0x1800045bd  mov     rax, [rbx-8]
0x1800045c1  mov     r8, [rbp+10h]
0x1800045c5  cmp     [rax+10h], r8
0x1800045c9  jbe     short loc_1800045DA
0x1800045cb  mov     rcx, rbx
0x1800045ce  mov     rbx, [rbx]
0x1800045d1  mov     rax, [rbx-8]
0x1800045d5  cmp     rbx, rdi
0x1800045d8  jnz     short loc_1800045C5
0x1800045da  lea     rax, [rdx+8]
0x1800045de  test    rcx, rcx
0x1800045e1  jnz     short loc_180004603
0x1800045e3  mov     rcx, [rdi]
0x1800045e6  cmp     [rcx+8], rdi
0x1800045ea  jz      short loc_1800045F3
0x1800045ec  mov     ecx, 3
0x1800045f1  int     29h; Win8: RtlFailFast(ecx)
0x1800045f3  mov     [rax], rcx
0x1800045f6  mov     [rax+8], rdi
0x1800045fa  mov     [rcx+8], rax
0x1800045fe  mov     [rdi], rax
0x180004601  jmp     short loc_180004611
0x180004603  mov     [rcx], rax
0x180004606  mov     [rdx+10h], rcx
0x18000460a  mov     [rax], rbx
0x18000460d  mov     [rbx+8], rax
0x180004611  mov     eax, esi
0x180004613  add     rsp, 28h
0x180004617  pop     rdi
0x180004618  pop     rsi
0x180004619  pop     rbp
0x18000461a  pop     rbx
0x18000461b  retn
```
