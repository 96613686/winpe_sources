# CILogStorage::AddStream(char *,_STRMTBL * *,ulong *)

- ea: `0x1800042b4`
- end: `0x1800044c0`
- name: `?AddStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z`
- size: `524`
- prototype: `__int64 __fastcall(CILogStorage *__hidden this, char *, struct _STRMTBL **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180002370`
- `0x180002400`
- `0x1800047b0`

## callees

- `0x1800012c0`
- `0x1800042b4`
- `0x18000955c`
- `0x18000a1a8`
- `0x18000c918`
- `0x18000d998`
- `0x18000dc8c`
- `0x18001280a`
- `0x180015010`

## string_xrefs

- `0x1800044a0`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x1800044a7`: `failed in TracedStringCchCopyN`
- `0x1800044b3`: `failed in TracedStringCchCopyN`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CILogStorage::AddStream(CILogStorage *this, char *a2, struct _STRMTBL **a3, unsigned int *a4)
{
  char *v6; // rbx
  __int64 v8; // r10
  __int64 result; // rax
  CLogStream *v10; // rax
  CLogStream *v11; // rsi
  __int64 v12; // r9
  __int64 v13; // r8
  char *v14; // rdx
  char v15; // al
  char *v16; // rax
  __int64 v17; // [rsp+28h] [rbp-80h]
  _BYTE v18[96]; // [rsp+30h] [rbp-78h] BYREF
  CLogStream *v19; // [rsp+B8h] [rbp+10h] BYREF

  v6 = a2;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 400LL);
  if ( *(_WORD *)(v8 + 88) >= 0xB7u )
  {
    result = 2147942414LL;
LABEL_10:
    *a3 = 0;
    return result;
  }
  *a4 = *(unsigned __int16 *)(v8 + 88) + 1;
  v10 = (CLogStream *)operator new(0x260u);
  v19 = v10;
  if ( v10 )
    v11 = CLogStream::CLogStream(v10, *((struct CLogMgr **)this + 1), *a4);
  else
    v11 = 0;
  if ( !v11 )
  {
    result = 2147549183LL;
    goto LABEL_10;
  }
  (*(void (__fastcall **)(CLogStream *))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = *(_QWORD *)(*((_QWORD *)this + 1) + 296LL)
      + 44LL * *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 1) + 400LL) + 88LL);
  *(_OWORD *)v12 = 0;
  *(_OWORD *)(v12 + 16) = 0;
  *(_OWORD *)(v12 + 28) = 0;
  *(_WORD *)(v12 + 16) = 2;
  ++*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 400LL) + 88LL);
  v13 = 16;
  v14 = (char *)v12;
  do
  {
    v15 = *v6;
    if ( !*v6 )
      break;
    ++v6;
    *v14++ = v15;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
  {
    TraceFile(-2147024774, "failed in TracedStringCchCopyN", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0x104u);
    DtcInternalErrorW(L"failed in TracedStringCchCopyN");
  }
  *(_QWORD *)(v12 + 20) = v11;
  *a3 = *(struct _STRMTBL **)(*((_QWORD *)this + 1) + 296LL);
  memset_0(v18, 0, 0x54u);
  v17 = *((_QWORD *)this + 1) + 408LL;
  (**(void (__fastcall ***)(__int64))v17)(v17);
  CLogState::GetRestartArea(
    *(CLogState **)(*((_QWORD *)this + 1) + 400LL),
    (struct _RESTARTLOG *)v18,
    (unsigned int *)&v19,
    0);
  CLogStorage::ForceRestart(
    *(CLogStorage **)(*((_QWORD *)this + 1) + 392LL),
    (struct _RESTARTLOG *)v18,
    *(struct _STRMTBL **)(*((_QWORD *)this + 1) + 296LL));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  return 0;
}

```

## disassembly

```asm
0x1800042b4  mov     [rsp+arg_0], rbx
0x1800042b9  mov     [rsp+arg_10], rbp
0x1800042be  push    rsi
0x1800042bf  push    rdi
0x1800042c0  push    r14
0x1800042c2  sub     rsp, 90h
0x1800042c9  mov     rsi, r9
0x1800042cc  mov     r14, r8
0x1800042cf  mov     rbx, rdx
0x1800042d2  mov     rdi, rcx
0x1800042d5  test    rdx, rdx
0x1800042d8  jz      loc_18000447D
0x1800042de  test    r8, r8
0x1800042e1  jz      loc_18000447D
0x1800042e7  mov     rax, [rcx+8]
0x1800042eb  mov     r10, [rax+190h]
0x1800042f2  mov     eax, 0B7h
0x1800042f7  cmp     [r10+58h], ax
0x1800042fc  jb      short loc_180004305
0x1800042fe  mov     eax, 8007000Eh
0x180004303  jmp     short loc_18000434B
0x180004305  movzx   eax, word ptr [r10+58h]
0x18000430a  mov     ebp, 1
0x18000430f  add     eax, ebp
0x180004311  mov     [r9], eax
0x180004314  mov     ecx, 260h; Size
0x180004319  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000431e  mov     [rsp+0A8h+arg_8], rax
0x180004326  test    rax, rax
0x180004329  jz      short loc_18000433F
0x18000432b  mov     r8d, [rsi]; unsigned int
0x18000432e  mov     rdx, [rdi+8]; struct CLogMgr *
0x180004332  mov     rcx, rax; this
0x180004335  call    ??0CLogStream@@QEAA@PEAVCLogMgr@@K@Z; CLogStream::CLogStream(CLogMgr *,ulong)
0x18000433a  mov     rsi, rax
0x18000433d  jmp     short loc_180004341
0x18000433f  xor     esi, esi
0x180004341  test    rsi, rsi
0x180004344  jnz     short loc_180004357
0x180004346  mov     eax, 8000FFFFh
0x18000434b  mov     qword ptr [r14], 0
0x180004352  jmp     loc_180004482
0x180004357  mov     rax, [rsi]
0x18000435a  mov     rcx, rsi
0x18000435d  mov     rax, [rax+8]
0x180004361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004366  mov     r8, [rdi+8]
0x18000436a  mov     rax, [r8+190h]
0x180004371  movzx   ecx, word ptr [rax+58h]
0x180004375  imul    r9, rcx, 2Ch ; ','
0x180004379  add     r9, [r8+128h]
0x180004380  xorps   xmm0, xmm0
0x180004383  movups  xmmword ptr [r9], xmm0
0x180004387  movups  xmmword ptr [r9+10h], xmm0
0x18000438c  movups  xmmword ptr [r9+1Ch], xmm0
0x180004391  mov     word ptr [r9+10h], 2
0x180004398  mov     rax, [rdi+8]
0x18000439c  mov     rcx, [rax+190h]
0x1800043a3  add     [rcx+58h], bp
0x1800043a7  mov     r8d, 10h
0x1800043ad  mov     rdx, r9
0x1800043b0  mov     al, [rbx]
0x1800043b2  test    al, al
0x1800043b4  jz      short loc_1800043C3
0x1800043b6  add     rbx, rbp
0x1800043b9  mov     [rdx], al
0x1800043bb  add     rdx, rbp
0x1800043be  sub     r8, rbp
0x1800043c1  jnz     short loc_1800043B0
0x1800043c3  mov     rax, r8
0x1800043c6  neg     rax
0x1800043c9  sbb     ecx, ecx
0x1800043cb  not     ecx
0x1800043cd  and     ecx, 8007007Ah; int
0x1800043d3  lea     rax, [rdx-1]
0x1800043d7  test    r8, r8
0x1800043da  cmovnz  rax, rdx
0x1800043de  mov     byte ptr [rax], 0
0x1800043e1  jz      loc_18000449A
0x1800043e7  mov     [r9+14h], rsi
0x1800043eb  mov     rax, [rdi+8]
0x1800043ef  mov     rcx, [rax+128h]
0x1800043f6  mov     [r14], rcx
0x1800043f9  xor     edx, edx; Val
0x1800043fb  lea     r8d, [rdx+54h]; Size
0x1800043ff  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004404  call    memset_0
0x180004409  mov     rbx, [rdi+8]
0x18000440d  add     rbx, 198h
0x180004414  mov     [rsp+0A8h+var_88], ebp
0x180004418  mov     [rsp+0A8h+var_80], rbx
0x18000441d  mov     rax, [rbx]
0x180004420  mov     rcx, rbx
0x180004423  mov     rax, [rax]
0x180004426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000442b  nop
0x18000442c  mov     rcx, [rdi+8]
0x180004430  xor     r9d, r9d; int
0x180004433  lea     r8, [rsp+0A8h+arg_8]; unsigned int *
0x18000443b  lea     rdx, [rsp+0A8h+var_78]; struct _RESTARTLOG *
0x180004440  mov     rcx, [rcx+190h]; this
0x180004447  call    ?GetRestartArea@CLogState@@QEAAXPEAU_RESTARTLOG@@PEAKH@Z; CLogState::GetRestartArea(_RESTARTLOG *,ulong *,int)
0x18000444c  mov     rcx, [rdi+8]
0x180004450  mov     r8, [rcx+128h]; struct _STRMTBL *
0x180004457  lea     rdx, [rsp+0A8h+var_78]; struct _RESTARTLOG *
0x18000445c  mov     rcx, [rcx+188h]; this
0x180004463  call    ?ForceRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z; CLogStorage::ForceRestart(_RESTARTLOG *,_STRMTBL *)
0x180004468  nop
0x180004469  mov     rax, [rbx]
0x18000446c  mov     rcx, rbx
0x18000446f  mov     rax, [rax+8]
0x180004473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004478  nop
0x180004479  xor     eax, eax
0x18000447b  jmp     short loc_180004482
0x18000447d  mov     eax, 80070057h
0x180004482  lea     r11, [rsp+0A8h+var_18]
0x18000448a  mov     rbx, [r11+20h]
0x18000448e  mov     rbp, [r11+30h]
0x180004492  mov     rsp, r11
0x180004495  pop     r14
0x180004497  pop     rdi
0x180004498  pop     rsi
0x180004499  retn
0x18000449a  mov     r9d, 104h; unsigned int
0x1800044a0  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x1800044a7  lea     rdx, aFailedInTraced_10; "failed in TracedStringCchCopyN"
0x1800044ae  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800044b3  lea     rcx, aFailedInTraced_1; "failed in TracedStringCchCopyN"
0x1800044ba  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
