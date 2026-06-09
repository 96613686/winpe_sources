# SmpSetEaFromOrigin

- ea: `0x1400076f0`
- end: `0x1400078e0`
- name: `SmpSetEaFromOrigin`
- size: `496`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, __int64, struct _FLT_CALLBACK_DATA *Src, size_t Size, struct _FLT_CALLBACK_DATA **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007030`

## callees

- `0x140001a40`
- `0x1400076f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400078b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400078b1`
- `ntoskrnl!ExAllocatePool2` at `0x1400077ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400077ac`
- `FLTMGR!FltFreeCallbackData` at `0x14000789d`
- `FLTMGR!FltFreeCallbackData` at `0x14000789d`
- `FLTMGR!FltAllocateCallbackData` at `0x140007819`
- `FLTMGR!FltAllocateCallbackData` at `0x140007819`
- `FLTMGR!FltPerformSynchronousIo` at `0x140007886`
- `FLTMGR!FltPerformSynchronousIo` at `0x140007886`

## pseudocode

```c
__int64 __fastcall SmpSetEaFromOrigin(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        __int64 a4,
        struct _FLT_CALLBACK_DATA *Src,
        size_t Size,
        struct _FLT_CALLBACK_DATA **a7)
{
  unsigned int v7; // ebp
  __int64 v8; // rsi
  __int64 *v11; // r10
  unsigned int v12; // edi
  __int64 v13; // r11
  struct _FLT_CALLBACK_DATA *v14; // rbx
  unsigned int Thread; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  ULONG v18; // ebp
  __int64 Pool2; // rax
  void *v20; // rsi
  NTSTATUS Status; // edi

  v7 = 0;
  v8 = 0;
  if ( a3 )
  {
    v11 = *(__int64 **)(*(_QWORD *)(a3 + 8) + 32LL);
    v12 = *((_DWORD *)v11 + 2);
    v13 = *v11;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  if ( a4 )
  {
    v8 = *(_QWORD *)(a4 + 32);
    v7 = *(_DWORD *)(a4 + 40);
  }
  v14 = Src;
  if ( Src )
  {
    Thread = (unsigned int)Src->Thread;
    if ( Thread <= 1 || Thread - 3 <= 1 )
      goto LABEL_16;
  }
  if ( v13 )
  {
    v16 = *(_DWORD *)(v13 + 8);
    if ( v16 <= 1 || v16 - 3 <= 1 )
    {
LABEL_18:
      v14 = (struct _FLT_CALLBACK_DATA *)v13;
      goto LABEL_21;
    }
  }
  if ( !v8 || (v17 = *(_DWORD *)(v8 + 8), v17 > 1) && v17 - 3 > 1 )
  {
    if ( Src )
    {
LABEL_16:
      v12 = Size;
      goto LABEL_21;
    }
    if ( a3 )
      goto LABEL_18;
    if ( !a4 )
      return 0;
  }
  v12 = v7;
  v14 = (struct _FLT_CALLBACK_DATA *)v8;
LABEL_21:
  v18 = v12 + 40;
  Pool2 = ExAllocatePool2(258, v12 + 40, 1165258099);
  v20 = (void *)Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *(_DWORD *)Pool2 = 0;
  *(_WORD *)(Pool2 + 4) = 7936;
  *(_WORD *)(Pool2 + 6) = v12;
  strcpy((char *)(Pool2 + 8), "$Kernel.Smartlocker.OriginClaim");
  memmove((void *)(Pool2 + 40), v14, v12);
  Src = 0;
  Status = FltAllocateCallbackData(Instance, FileObject, &Src);
  if ( Status >= 0 )
  {
    Src->Iopb->MajorFunction = 8;
    Src->Iopb->MinorFunction = 4;
    Src->Iopb->Parameters.Read.Length = v18;
    Src->Iopb->Parameters.QueryEa.EaList = v20;
    Src->Iopb->Parameters.Read.ByteOffset.QuadPart = 0;
    FltPerformSynchronousIo(Src);
    Status = Src->IoStatus.Status;
    FltFreeCallbackData(Src);
  }
  ExFreePoolWithTag(v20, 0x45746D73u);
  if ( Status >= 0 )
    *a7 = v14;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400076f0  push    rbx
0x1400076f2  push    rbp
0x1400076f3  push    rsi
0x1400076f4  push    rdi
0x1400076f5  push    r14
0x1400076f7  push    r15
0x1400076f9  sub     rsp, 28h
0x1400076fd  xor     ebp, ebp
0x1400076ff  xor     esi, esi
0x140007701  mov     r14, rdx
0x140007704  mov     r15, rcx
0x140007707  test    r8, r8
0x14000770a  jz      short loc_14000771D
0x14000770c  mov     rax, [r8+8]
0x140007710  mov     r10, [rax+20h]
0x140007714  mov     edi, [r10+8]
0x140007718  mov     r11, [r10]
0x14000771b  jmp     short loc_140007722
0x14000771d  xor     edi, edi
0x14000771f  xor     r11d, r11d
0x140007722  test    r9, r9
0x140007725  jz      short loc_14000772F
0x140007727  mov     rsi, [r9+20h]
0x14000772b  mov     ebp, [r9+28h]
0x14000772f  mov     rbx, [rsp+58h+Src]
0x140007737  mov     ecx, 1
0x14000773c  test    rbx, rbx
0x14000773f  jz      short loc_14000774F
0x140007741  mov     eax, [rbx+8]
0x140007744  cmp     eax, ecx
0x140007746  jbe     short loc_14000777B
0x140007748  add     eax, 0FFFFFFFDh
0x14000774b  cmp     eax, ecx
0x14000774d  jbe     short loc_14000777B
0x14000774f  test    r11, r11
0x140007752  jz      short loc_140007763
0x140007754  mov     eax, [r11+8]
0x140007758  cmp     eax, ecx
0x14000775a  jbe     short loc_140007789
0x14000775c  add     eax, 0FFFFFFFDh
0x14000775f  cmp     eax, ecx
0x140007761  jbe     short loc_140007789
0x140007763  test    rsi, rsi
0x140007766  jz      short loc_140007776
0x140007768  mov     eax, [rsi+8]
0x14000776b  cmp     eax, ecx
0x14000776d  jbe     short loc_140007797
0x14000776f  add     eax, 0FFFFFFFDh
0x140007772  cmp     eax, ecx
0x140007774  jbe     short loc_140007797
0x140007776  test    rbx, rbx
0x140007779  jz      short loc_140007784
0x14000777b  mov     edi, dword ptr [rsp+58h+Size]
0x140007782  jmp     short loc_14000779C
0x140007784  test    r8, r8
0x140007787  jz      short loc_14000778E
0x140007789  mov     rbx, r11
0x14000778c  jmp     short loc_14000779C
0x14000778e  test    r9, r9
0x140007791  jz      loc_1400078D0
0x140007797  mov     edi, ebp
0x140007799  mov     rbx, rsi
0x14000779c  lea     ebp, [rdi+28h]
0x14000779f  mov     ecx, 102h
0x1400077a4  mov     edx, ebp
0x1400077a6  mov     r8d, 45746D73h
0x1400077ac  call    cs:__imp_ExAllocatePool2
0x1400077b3  nop     dword ptr [rax+rax+00h]
0x1400077b8  mov     rsi, rax
0x1400077bb  test    rax, rax
0x1400077be  jnz     short loc_1400077CA
0x1400077c0  mov     eax, 0C0000017h
0x1400077c5  jmp     loc_1400078D2
0x1400077ca  mov     dword ptr [rax], 0
0x1400077d0  lea     rcx, [rax+28h]; void *
0x1400077d4  mov     word ptr [rax+4], 1F00h
0x1400077da  mov     rdx, rbx; Src
0x1400077dd  mov     [rax+6], di
0x1400077e1  movups  xmm0, cs:xmmword_1400035C8
0x1400077e8  mov     r8d, edi; Size
0x1400077eb  movups  xmmword ptr [rax+8], xmm0
0x1400077ef  movups  xmm1, cs:xmmword_1400035D8
0x1400077f6  movups  xmmword ptr [rax+18h], xmm1
0x1400077fa  call    memmove
0x1400077ff  lea     r8, [rsp+58h+Src]; RetNewCallbackData
0x140007807  mov     [rsp+58h+Src], 0
0x140007813  mov     rdx, r14; FileObject
0x140007816  mov     rcx, r15; Instance
0x140007819  call    cs:__imp_FltAllocateCallbackData
0x140007820  nop     dword ptr [rax+rax+00h]
0x140007825  mov     edi, eax
0x140007827  test    eax, eax
0x140007829  js      short loc_1400078A9
0x14000782b  mov     rax, [rsp+58h+Src]
0x140007833  mov     rcx, [rax+10h]
0x140007837  mov     byte ptr [rcx+4], 8
0x14000783b  mov     rax, [rsp+58h+Src]
0x140007843  mov     rcx, [rax+10h]
0x140007847  mov     byte ptr [rcx+5], 4
0x14000784b  mov     rax, [rsp+58h+Src]
0x140007853  mov     rcx, [rax+10h]
0x140007857  mov     [rcx+18h], ebp
0x14000785a  mov     rax, [rsp+58h+Src]
0x140007862  mov     rcx, [rax+10h]
0x140007866  mov     [rcx+20h], rsi
0x14000786a  mov     rax, [rsp+58h+Src]
0x140007872  mov     rcx, [rax+10h]
0x140007876  mov     qword ptr [rcx+28h], 0
0x14000787e  mov     rcx, [rsp+58h+Src]; CallbackData
0x140007886  call    cs:__imp_FltPerformSynchronousIo
0x14000788d  nop     dword ptr [rax+rax+00h]
0x140007892  mov     rcx, [rsp+58h+Src]; CallbackData
0x14000789a  mov     edi, [rcx+18h]
0x14000789d  call    cs:__imp_FltFreeCallbackData
0x1400078a4  nop     dword ptr [rax+rax+00h]
0x1400078a9  mov     edx, 45746D73h; Tag
0x1400078ae  mov     rcx, rsi; P
0x1400078b1  call    cs:__imp_ExFreePoolWithTag
0x1400078b8  nop     dword ptr [rax+rax+00h]
0x1400078bd  test    edi, edi
0x1400078bf  js      short loc_1400078CC
0x1400078c1  mov     rax, [rsp+58h+arg_30]
0x1400078c9  mov     [rax], rbx
0x1400078cc  mov     eax, edi
0x1400078ce  jmp     short loc_1400078D2
0x1400078d0  xor     eax, eax
0x1400078d2  add     rsp, 28h
0x1400078d6  pop     r15
0x1400078d8  pop     r14
0x1400078da  pop     rdi
0x1400078db  pop     rsi
0x1400078dc  pop     rbp
0x1400078dd  pop     rbx
0x1400078de  retn
```
