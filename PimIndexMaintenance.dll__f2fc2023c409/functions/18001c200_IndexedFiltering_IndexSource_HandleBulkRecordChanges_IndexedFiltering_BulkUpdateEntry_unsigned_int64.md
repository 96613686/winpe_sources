# IndexedFiltering::IndexSource::HandleBulkRecordChanges(IndexedFiltering::BulkUpdateEntry *,unsigned __int64)

- ea: `0x18001c200`
- end: `0x18001c328`
- name: `?HandleBulkRecordChanges@IndexSource@IndexedFiltering@@UEAAJPEAUBulkUpdateEntry@2@_K@Z`
- size: `296`
- prototype: `__int64 __fastcall(__int64 this, struct IndexedFiltering::BulkUpdateEntry *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x1800086a0`
- `0x18000d63c`
- `0x18001c200`
- `0x18001cb30`
- `0x180022010`

## string_xrefs

- `0x18001c228`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`
- `0x18001c273`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexSource::HandleBulkRecordChanges(
        __int64 this,
        struct IndexedFiltering::BulkUpdateEntry *a2,
        unsigned __int64 a3)
{
  IndexedFiltering::IndexSource *v5; // r12
  unsigned __int64 i; // rbx
  int v7; // edi
  int *v8; // rsi
  int v9; // ebp
  __int64 j; // rdi
  int v11; // eax
  unsigned int v12; // ebp
  __int64 v13; // r9

  v5 = (IndexedFiltering::IndexSource *)this;
  if ( !a2 || !a3 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
      384);
  for ( i = 0; i < a3; ++i )
  {
    v7 = FailOnServiceShutdown(this, (__int64)a2, a3);
    if ( v7 < 0 )
    {
      v13 = 391;
      goto LABEL_24;
    }
    v8 = (int *)((char *)a2 + 40 * i);
    this = (unsigned int)v8[3];
    if ( !(_DWORD)this )
      goto LABEL_17;
    this = (unsigned int)(this - 1);
    if ( (_DWORD)this )
    {
      if ( (_DWORD)this != 1 )
      {
        if ( v8[3] >= 3 )
          Log_AssertionEvent(
            this,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
            411);
        continue;
      }
      v9 = 1;
    }
    else
    {
      v9 = 0;
    }
    v7 = (*(__int64 (__fastcall **)(IndexedFiltering::IndexSource *, char *))(*(_QWORD *)v5 + 152LL))(
           v5,
           (char *)a2 + 40 * i);
    if ( v7 < 0 )
    {
      v13 = 418;
LABEL_24:
      Log_HREvent_7((unsigned int)v7, 1, a3, v13);
      return (unsigned int)v7;
    }
    if ( v9 )
    {
LABEL_17:
      for ( j = 0; (unsigned __int64)(unsigned int)j < *((_QWORD *)v8 + 3); j = (unsigned int)(j + 1) )
      {
        v11 = (*(__int64 (__fastcall **)(IndexedFiltering::IndexSource *, char *, __int64))(*(_QWORD *)v5 + 160LL))(
                v5,
                (char *)a2 + 40 * i,
                *((_QWORD *)v8 + 2) + 24 * j);
        v12 = v11;
        if ( v11 < 0 )
        {
          Log_HREvent_7((unsigned int)v11, 1, a3, 429);
          return v12;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c200  push    rbx
0x18001c202  push    rbp
0x18001c203  push    rsi
0x18001c204  push    rdi
0x18001c205  push    r12
0x18001c207  push    r14
0x18001c209  push    r15
0x18001c20b  sub     rsp, 30h
0x18001c20f  mov     r14, r8
0x18001c212  mov     r15, rdx
0x18001c215  mov     r12, rcx
0x18001c218  test    rdx, rdx
0x18001c21b  jz      short loc_18001C222
0x18001c21d  test    r8, r8
0x18001c220  jnz     short loc_18001C234
0x18001c222  mov     r8d, 180h
0x18001c228  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001c22f  call    Log_AssertionEvent
0x18001c234  xor     ebx, ebx
0x18001c236  cmp     rbx, r14
0x18001c239  jnb     loc_18001C317
0x18001c23f  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x18001c244  mov     edi, eax
0x18001c246  test    eax, eax
0x18001c248  js      loc_18001C301
0x18001c24e  lea     rax, [rbx+rbx*4]
0x18001c252  lea     rsi, [r15+rax*8]
0x18001c256  mov     ecx, [rsi+0Ch]
0x18001c259  test    ecx, ecx
0x18001c25b  jz      short loc_18001C2AD
0x18001c25d  sub     ecx, 1
0x18001c260  jz      short loc_18001C28B
0x18001c262  cmp     ecx, 1
0x18001c265  jz      short loc_18001C284
0x18001c267  cmp     dword ptr [rsi+0Ch], 3
0x18001c26b  jl      short loc_18001C27F
0x18001c26d  mov     r8d, 19Bh
0x18001c273  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001c27a  call    Log_AssertionEvent
0x18001c27f  inc     rbx
0x18001c282  jmp     short loc_18001C236
0x18001c284  mov     ebp, 1
0x18001c289  jmp     short loc_18001C28D
0x18001c28b  xor     ebp, ebp
0x18001c28d  mov     rax, [r12]
0x18001c291  mov     rdx, rsi
0x18001c294  mov     rcx, r12
0x18001c297  mov     rax, [rax+98h]
0x18001c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2a3  mov     edi, eax
0x18001c2a5  test    eax, eax
0x18001c2a7  js      short loc_18001C2E3
0x18001c2a9  test    ebp, ebp
0x18001c2ab  jz      short loc_18001C27F
0x18001c2ad  xor     edi, edi
0x18001c2af  mov     eax, edi
0x18001c2b1  cmp     rax, [rsi+18h]
0x18001c2b5  jnb     short loc_18001C27F
0x18001c2b7  mov     rax, [rsi+10h]
0x18001c2bb  lea     rcx, [rdi+rdi*2]
0x18001c2bf  mov     rdx, [r12]
0x18001c2c3  lea     r8, [rax+rcx*8]
0x18001c2c7  mov     rcx, r12
0x18001c2ca  mov     rax, [rdx+0A0h]
0x18001c2d1  mov     rdx, rsi
0x18001c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d9  mov     ebp, eax
0x18001c2db  test    eax, eax
0x18001c2dd  js      short loc_18001C2EB
0x18001c2df  inc     edi
0x18001c2e1  jmp     short loc_18001C2AF
0x18001c2e3  mov     r9d, 1A2h
0x18001c2e9  jmp     short loc_18001C307
0x18001c2eb  mov     edx, 1
0x18001c2f0  mov     r9d, 1ADh
0x18001c2f6  mov     ecx, ebp
0x18001c2f8  call    Log_HREvent_7
0x18001c2fd  mov     eax, ebp
0x18001c2ff  jmp     short loc_18001C319
0x18001c301  mov     r9d, 187h
0x18001c307  mov     edx, 1
0x18001c30c  mov     ecx, edi
0x18001c30e  call    Log_HREvent_7
0x18001c313  mov     eax, edi
0x18001c315  jmp     short loc_18001C319
0x18001c317  xor     eax, eax
0x18001c319  add     rsp, 30h
0x18001c31d  pop     r15
0x18001c31f  pop     r14
0x18001c321  pop     r12
0x18001c323  pop     rdi
0x18001c324  pop     rsi
0x18001c325  pop     rbp
0x18001c326  pop     rbx
0x18001c327  retn
```
