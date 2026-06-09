# ModuleUtil::Details::AddThreadListEntry(ulong)

- ea: `0x18000c2dc`
- end: `0x18000c438`
- name: `?AddThreadListEntry@Details@ModuleUtil@@YA_NK@Z`
- size: `348`
- prototype: `bool __fastcall(ModuleUtil::Details *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c568`

## callees

- `0x180001008`
- `0x18000c2dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c370`
- `ntdll!RtlAllocateHeap` at `0x18000c370`

## string_xrefs

- `0x18000c343`: `Duplicate thread list entry found`
- `0x18000c3f6`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`
- `0x18000c3dd`: `Failed to allocate thread list entry`

## pseudocode

```c
char __fastcall ModuleUtil::Details::AddThreadListEntry(ModuleUtil::Details *this, __int64 a2, int a3, int a4)
{
  int v4; // edi
  __int64 *v5; // rbx
  __int64 i; // rax
  int v7; // ecx
  const char *v8; // rax
  __int16 *v9; // rdx
  _QWORD *Heap; // rax
  __int64 v11; // rcx
  int v13; // [rsp+60h] [rbp+20h] BYREF
  int v14; // [rsp+68h] [rbp+28h] BYREF
  const char *v15; // [rsp+70h] [rbp+30h] BYREF
  const char *v16; // [rsp+78h] [rbp+38h] BYREF

  v4 = (int)this;
  v5 = &qword_180069920[3 * ((unsigned __int8)this & 7)];
  for ( i = *v5; (__int64 *)i != v5; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 16) == (_DWORD)this )
    {
      if ( (unsigned int)dword_180069000 > 3 )
      {
        v7 = qword_180069018;
        if ( (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
        {
          v8 = "Duplicate thread list entry found";
          v14 = 49;
          v9 = (__int16 *)qword_180059FE0;
          goto LABEL_17;
        }
      }
      return 0;
    }
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
  if ( !Heap )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v7 = qword_180069018;
      if ( (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
      {
        v8 = "Failed to allocate thread list entry";
        v14 = 64;
        v9 = &word_180059E56;
LABEL_17:
        v15 = v8;
        v16 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
        v13 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (_DWORD)v9,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v14,
          (__int64)&v15,
          (__int64)&v13);
      }
    }
    return 0;
  }
  *(_OWORD *)Heap = 0;
  Heap[2] = 0;
  *((_DWORD *)Heap + 4) = v4;
  v11 = *v5;
  if ( *(__int64 **)(*v5 + 8) != v5 )
    __fastfail(3u);
  *Heap = v11;
  Heap[1] = v5;
  *(_QWORD *)(v11 + 8) = Heap;
  ++*((_DWORD *)v5 + 4);
  *v5 = (__int64)Heap;
  return 1;
}

```

## disassembly

```asm
0x18000c2dc  push    rbp
0x18000c2de  push    rbx
0x18000c2df  push    rdi
0x18000c2e0  mov     rbp, rsp
0x18000c2e3  sub     rsp, 40h
0x18000c2e7  mov     eax, ecx
0x18000c2e9  mov     edi, ecx
0x18000c2eb  and     eax, 7
0x18000c2ee  lea     rcx, qword_180069920
0x18000c2f5  lea     rax, [rax+rax*2]
0x18000c2f9  lea     rbx, [rcx+rax*8]
0x18000c2fd  mov     rax, [rbx]
0x18000c300  cmp     rax, rbx
0x18000c303  jz      short loc_18000C35D
0x18000c305  cmp     [rax+10h], edi
0x18000c308  jz      short loc_18000C30F
0x18000c30a  mov     rax, [rax]
0x18000c30d  jmp     short loc_18000C300
0x18000c30f  mov     eax, cs:dword_180069000
0x18000c315  cmp     eax, 3
0x18000c318  jbe     loc_18000C42D
0x18000c31e  mov     rcx, cs:qword_180069018
0x18000c325  mov     rax, cs:qword_180069010
0x18000c32c  test    al, 2
0x18000c32e  jz      loc_18000C42D
0x18000c334  mov     rax, rcx
0x18000c337  and     eax, 2
0x18000c33a  cmp     rax, rcx
0x18000c33d  jnz     loc_18000C42D
0x18000c343  lea     rax, aDuplicateThrea; "Duplicate thread list entry found"
0x18000c34a  mov     [rbp+arg_8], 31h ; '1'
0x18000c351  lea     rdx, qword_180059FE0
0x18000c358  jmp     loc_18000C3F2
0x18000c35d  mov     rcx, gs:60h
0x18000c366  xor     edx, edx; Flags
0x18000c368  mov     rcx, [rcx+30h]; HeapHandle
0x18000c36c  lea     r8d, [rdx+18h]; Size
0x18000c370  call    cs:__imp_RtlAllocateHeap
0x18000c377  nop     dword ptr [rax+rax+00h]
0x18000c37c  test    rax, rax
0x18000c37f  jz      short loc_18000C3B5
0x18000c381  xor     ecx, ecx
0x18000c383  xorps   xmm0, xmm0
0x18000c386  movups  xmmword ptr [rax], xmm0
0x18000c389  mov     [rax+10h], rcx
0x18000c38d  mov     [rax+10h], edi
0x18000c390  mov     rcx, [rbx]
0x18000c393  cmp     [rcx+8], rbx
0x18000c397  jz      short loc_18000C3A0
0x18000c399  mov     ecx, 3
0x18000c39e  int     29h; Win8: RtlFailFast(ecx)
0x18000c3a0  mov     [rax], rcx
0x18000c3a3  mov     [rax+8], rbx
0x18000c3a7  mov     [rcx+8], rax
0x18000c3ab  inc     dword ptr [rbx+10h]
0x18000c3ae  mov     [rbx], rax
0x18000c3b1  mov     al, 1
0x18000c3b3  jmp     short loc_18000C42F
0x18000c3b5  mov     eax, cs:dword_180069000
0x18000c3bb  cmp     eax, 2
0x18000c3be  jbe     short loc_18000C42D
0x18000c3c0  mov     rcx, cs:qword_180069018
0x18000c3c7  mov     rax, cs:qword_180069010
0x18000c3ce  test    al, 2
0x18000c3d0  jz      short loc_18000C42D
0x18000c3d2  mov     rax, rcx
0x18000c3d5  and     eax, 2
0x18000c3d8  cmp     rax, rcx
0x18000c3db  jnz     short loc_18000C42D
0x18000c3dd  lea     rax, aFailedToAlloca; "Failed to allocate thread list entry"
0x18000c3e4  mov     [rbp+arg_8], 40h ; '@'
0x18000c3eb  lea     rdx, word_180059E56
0x18000c3f2  mov     [rbp+arg_10], rax
0x18000c3f6  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000c3fd  mov     [rbp+arg_18], rax
0x18000c401  lea     rax, [rbp+arg_0]
0x18000c405  mov     [rsp+40h+var_8], rax
0x18000c40a  lea     rax, [rbp+arg_10]
0x18000c40e  mov     [rsp+40h+var_10], rax
0x18000c413  lea     rax, [rbp+arg_8]
0x18000c417  mov     [rsp+40h+var_18], rax
0x18000c41c  lea     rax, [rbp+arg_18]
0x18000c420  mov     [rsp+40h+var_20], rax
0x18000c425  mov     [rbp+arg_0], edi
0x18000c428  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c42d  xor     al, al
0x18000c42f  add     rsp, 40h
0x18000c433  pop     rdi
0x18000c434  pop     rbx
0x18000c435  pop     rbp
0x18000c436  retn
```
