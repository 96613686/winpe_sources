# CMetaData::~CMetaData(void)

- ea: `0x1800026a0`
- end: `0x1800027b7`
- name: `??1CMetaData@@QEAA@XZ`
- size: `279`
- prototype: `void __fastcall(CMetaData *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005798`
- `0x18001aaa0`
- `0x18001fcdc`
- `0x18002e703`

## callees

- `0x180001dd8`
- `0x1800026a0`
- `0x180004b30`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800026b4`
- `ole32!CoTaskMemFree` at `0x1800026be`
- `ole32!CoTaskMemFree` at `0x1800026c8`
- `ole32!CoTaskMemFree` at `0x1800026b4`
- `ole32!CoTaskMemFree` at `0x1800026be`
- `ole32!CoTaskMemFree` at `0x1800026c8`

## pseudocode

```c
void __fastcall CMetaData::~CMetaData(CMetaData *this)
{
  unsigned __int8 **v1; // rdi
  CMetaData *v3; // rcx
  unsigned __int16 i; // bp
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rcx
  unsigned __int8 *v8; // rcx
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rcx

  v1 = (unsigned __int8 **)*((_QWORD *)this + 6);
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 3));
  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *(_WORD *)this; ++i )
    {
      v5 = *((_QWORD *)this + 4) + 9648LL * i;
      if ( *((_BYTE *)this + 56) )
      {
        CMetaData::mdReleaseByRefData(v3, (struct tagCOLRSDATA *)(*((_QWORD *)this + 4) + 9648LL * i));
      }
      else
      {
        if ( !*(_DWORD *)(v5 + 9608) )
        {
          v3 = *(CMetaData **)(v5 + 9600);
          if ( v3 )
            MMMFree((unsigned __int8 *)v3);
        }
        if ( !*(_DWORD *)(v5 + 9632) )
        {
          v3 = *(CMetaData **)(v5 + 9624);
          if ( v3 )
            MMMFree((unsigned __int8 *)v3);
        }
      }
    }
    v6 = (unsigned __int8 *)*((_QWORD *)this + 4);
    if ( v6 )
      MMMFree(v6);
  }
  while ( v1 )
  {
    *((_QWORD *)this + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 48LL);
    if ( *v1 )
      MMMFree(*v1);
    v7 = v1[1];
    if ( v7 )
      MMMFree(v7);
    v8 = v1[2];
    if ( v8 )
      MMMFree(v8);
    v9 = v1[4];
    if ( v9 )
      MMMFree(v9);
    MMMFree((unsigned __int8 *)v1);
    v1 = (unsigned __int8 **)*((_QWORD *)this + 6);
  }
  v10 = (unsigned __int8 *)*((_QWORD *)this + 5);
  if ( v10 )
    MMMFree(v10);
}

```

## disassembly

```asm
0x1800026a0  push    rbx
0x1800026a2  push    rbp
0x1800026a3  push    rsi
0x1800026a4  push    rdi
0x1800026a5  sub     rsp, 28h
0x1800026a9  mov     rdi, [rcx+30h]
0x1800026ad  mov     rbx, rcx
0x1800026b0  mov     rcx, [rcx+8]; pv
0x1800026b4  call    cs:__imp_CoTaskMemFree
0x1800026ba  mov     rcx, [rbx+10h]; pv
0x1800026be  call    cs:__imp_CoTaskMemFree
0x1800026c4  mov     rcx, [rbx+18h]; pv
0x1800026c8  call    cs:__imp_CoTaskMemFree
0x1800026ce  cmp     qword ptr [rbx+20h], 0
0x1800026d3  jz      loc_18000279B
0x1800026d9  xor     ebp, ebp
0x1800026db  xor     eax, eax
0x1800026dd  cmp     ax, [rbx]
0x1800026e0  jnb     short loc_18000273C
0x1800026e2  movzx   eax, bp
0x1800026e5  imul    rsi, rax, 25B0h
0x1800026ec  add     rsi, [rbx+20h]
0x1800026f0  cmp     byte ptr [rbx+38h], 0
0x1800026f4  jz      short loc_180002700
0x1800026f6  mov     rdx, rsi; struct tagCOLRSDATA *
0x1800026f9  call    ?mdReleaseByRefData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@@Z; CMetaData::mdReleaseByRefData(tagCOLRSDATA *)
0x1800026fe  jmp     short loc_180002734
0x180002700  cmp     dword ptr [rsi+2588h], 0
0x180002707  jnz     short loc_18000271A
0x180002709  mov     rcx, [rsi+2580h]; unsigned __int8 *
0x180002710  test    rcx, rcx
0x180002713  jz      short loc_18000271A
0x180002715  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000271a  cmp     dword ptr [rsi+25A0h], 0
0x180002721  jnz     short loc_180002734
0x180002723  mov     rcx, [rsi+2598h]; unsigned __int8 *
0x18000272a  test    rcx, rcx
0x18000272d  jz      short loc_180002734
0x18000272f  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002734  inc     bp
0x180002737  cmp     bp, [rbx]
0x18000273a  jb      short loc_1800026E2
0x18000273c  mov     rcx, [rbx+20h]; unsigned __int8 *
0x180002740  test    rcx, rcx
0x180002743  jz      short loc_18000279B
0x180002745  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000274a  jmp     short loc_18000279B
0x18000274c  mov     rax, [rbx+30h]
0x180002750  mov     rcx, [rax+30h]
0x180002754  mov     [rbx+30h], rcx
0x180002758  mov     rcx, [rdi]; unsigned __int8 *
0x18000275b  test    rcx, rcx
0x18000275e  jz      short loc_180002765
0x180002760  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002765  mov     rcx, [rdi+8]; unsigned __int8 *
0x180002769  test    rcx, rcx
0x18000276c  jz      short loc_180002773
0x18000276e  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002773  mov     rcx, [rdi+10h]; unsigned __int8 *
0x180002777  test    rcx, rcx
0x18000277a  jz      short loc_180002781
0x18000277c  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002781  mov     rcx, [rdi+20h]; unsigned __int8 *
0x180002785  test    rcx, rcx
0x180002788  jz      short loc_18000278F
0x18000278a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000278f  mov     rcx, rdi; unsigned __int8 *
0x180002792  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002797  mov     rdi, [rbx+30h]
0x18000279b  test    rdi, rdi
0x18000279e  jnz     short loc_18000274C
0x1800027a0  mov     rcx, [rbx+28h]; unsigned __int8 *
0x1800027a4  test    rcx, rcx
0x1800027a7  jz      short loc_1800027AE
0x1800027a9  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x1800027ae  add     rsp, 28h
0x1800027b2  pop     rdi
0x1800027b3  pop     rsi
0x1800027b4  pop     rbp
0x1800027b5  pop     rbx
0x1800027b6  retn
```
