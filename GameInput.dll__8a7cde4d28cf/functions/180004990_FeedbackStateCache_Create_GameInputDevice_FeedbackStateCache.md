# FeedbackStateCache::Create(GameInputDevice *,FeedbackStateCache * *)

- ea: `0x180004990`
- end: `0x180004c27`
- name: `?Create@FeedbackStateCache@@SAJPEAVGameInputDevice@@PEAPEAV1@@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct GameInputDevice *, struct FeedbackStateCache **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004c30`

## callees

- `0x180001304`
- `0x180003940`
- `0x180004990`
- `0x1800069a4`
- `0x18000a7a0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004a5f`
- `ntdll!RtlAllocateHeap` at `0x180004a5f`

## string_xrefs

- `0x180004aac`: `onecore\xbox\gameinput\client\FeedbackStateCache.cpp`
- `0x180004bc9`: `onecore\xbox\gameinput\client\FeedbackStateCache.cpp`

## pseudocode

```c
__int64 __fastcall FeedbackStateCache::Create(struct GameInputDevice *a1, struct FeedbackStateCache **a2)
{
  SharedBuffer **CurrentBuffer; // rax
  int v4; // r8d
  int v5; // r9d
  SharedBuffer *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 v12; // r14
  unsigned int v13; // edx
  __int64 v14; // rdi
  SIZE_T v15; // r8
  __int64 v16; // rcx
  char *Heap; // rax
  int v18; // r8d
  int v19; // r9d
  char *v20; // rsi
  unsigned int v21; // edi
  char *v22; // r12
  unsigned int v23; // edx
  unsigned __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rcx
  struct FeedbackStateCache **v28; // rax
  __int64 v30; // [rsp+40h] [rbp-20h]
  SharedBuffer *v31; // [rsp+48h] [rbp-18h] BYREF
  SharedBuffer *v32; // [rsp+50h] [rbp-10h]
  struct FeedbackStateCache **v33; // [rsp+A8h] [rbp+48h] BYREF
  int v34; // [rsp+B0h] [rbp+50h] BYREF
  const char *i; // [rsp+B8h] [rbp+58h] BYREF

  v33 = a2;
  *a2 = 0;
  CurrentBuffer = (SharedBuffer **)GameInputDevice::GetCurrentBuffer(a1, &v31);
  v6 = *CurrentBuffer;
  *CurrentBuffer = 0;
  v32 = v6;
  if ( v31 )
    SharedBuffer::ReleaseReference(v31);
  if ( v6 )
  {
    v7 = *((_QWORD *)v6 + 10);
    if ( v7 )
    {
      v8 = *(unsigned int *)(v7 + 20);
      v9 = v8 + v7;
      v10 = -v8;
      v11 = v9 & -(__int64)(v10 != 0);
      if ( v11 )
      {
        v12 = *(unsigned int *)((v9 & -(__int64)(v10 != 0)) + 4);
        v13 = 0;
        v14 = 48;
        v15 = 8 * v12 + 48;
        for ( i = (const char *)v15; v13 < (unsigned int)v12; v15 += 280LL * *(unsigned __int16 *)(v16 + v11 + 12) + 112 )
          v16 = 28LL * v13++;
      }
      else
      {
        v14 = 0;
        i = 0;
        LODWORD(v12) = 0;
        v15 = 48;
      }
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      v20 = Heap;
      if ( Heap )
      {
        v22 = 0;
        if ( v11 )
        {
          v34 = 0;
          v22 = &Heap[v14];
          v23 = 0;
          if ( (_DWORD)v12 )
          {
            v24 = (unsigned __int64)i;
            v25 = 0;
            v30 = 0;
            do
            {
              v26 = 28 * v25;
              *(_QWORD *)&v22[8 * v25] = &v20[v24];
              ForceFeedbackMotorStateCache::ForceFeedbackMotorStateCache(
                (ForceFeedbackMotorStateCache *)&v20[v24],
                a1,
                v23,
                (const struct ForceFeedbackMotorResourceProfile *)(28 * v25 + v11 + 8));
              v27 = 280LL * *(unsigned __int16 *)(v26 + v11 + 12);
              v23 = v34 + 1;
              v34 = v23;
              v25 = v30 + 1;
              v24 = (v27 + v24 + 119) & 0xFFFFFFFFFFFFFFF8uLL;
              ++v30;
            }
            while ( v23 < (unsigned int)v12 );
            v6 = v32;
          }
        }
        v28 = v33;
        v21 = 0;
        *(_DWORD *)v20 = v12;
        *((_DWORD *)v20 + 1) = 0;
        *((_QWORD *)v20 + 1) = v22;
        *((_QWORD *)v20 + 2) = a1;
        *((_QWORD *)v20 + 3) = 0;
        *((_QWORD *)v20 + 4) = 0;
        *((_QWORD *)v20 + 5) = 0;
        *v28 = (struct FeedbackStateCache *)v20;
      }
      else
      {
        v21 = -2147024882;
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
        {
          LODWORD(v33) = -2147024882;
          i = "onecore\\xbox\\gameinput\\client\\FeedbackStateCache.cpp";
          v34 = 64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)&byte_1800597C7,
            v18,
            v19,
            (__int64)&i,
            (__int64)&v34,
            (__int64)&v33);
        }
      }
    }
    else
    {
      v21 = 1;
    }
    SharedBuffer::ReleaseReference(v6);
    return v21;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      LODWORD(v33) = -2147418113;
      i = "onecore\\xbox\\gameinput\\client\\FeedbackStateCache.cpp";
      v34 = 33;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&word_1800599B6,
        v4,
        v5,
        (__int64)&i,
        (__int64)&v34,
        (__int64)&v33);
    }
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180004990  mov     [rsp-38h+arg_0], rbx
0x180004995  mov     [rsp-38h+arg_8], rdx
0x18000499a  push    rbp
0x18000499b  push    rsi
0x18000499c  push    rdi
0x18000499d  push    r12
0x18000499f  push    r13
0x1800049a1  push    r14
0x1800049a3  push    r15
0x1800049a5  mov     rbp, rsp
0x1800049a8  sub     rsp, 60h
0x1800049ac  mov     qword ptr [rdx], 0
0x1800049b3  mov     r13, rcx
0x1800049b6  lea     rdx, [rbp+var_18]
0x1800049ba  call    ?GetCurrentBuffer@GameInputDevice@@QEBA?AVSharedBufferPtr@@XZ; GameInputDevice::GetCurrentBuffer(void)
0x1800049bf  mov     rbx, [rax]
0x1800049c2  mov     qword ptr [rax], 0
0x1800049c9  mov     rcx, [rbp+var_18]; this
0x1800049cd  mov     [rbp+var_10], rbx
0x1800049d1  test    rcx, rcx
0x1800049d4  jz      short loc_1800049DB
0x1800049d6  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x1800049db  test    rbx, rbx
0x1800049de  jz      loc_180004BA1
0x1800049e4  mov     rcx, [rbx+50h]
0x1800049e8  test    rcx, rcx
0x1800049eb  jz      loc_180004B90
0x1800049f1  mov     eax, [rcx+14h]
0x1800049f4  add     rcx, rax
0x1800049f7  neg     rax
0x1800049fa  sbb     r15, r15
0x1800049fd  and     r15, rcx
0x180004a00  jz      short loc_180004A41
0x180004a02  mov     r14d, [r15+4]
0x180004a06  xor     edx, edx
0x180004a08  mov     edi, 30h ; '0'
0x180004a0d  lea     r8, ds:30h[r14*8]
0x180004a15  mov     [rbp+arg_18], r8
0x180004a19  test    r14d, r14d
0x180004a1c  jz      short loc_180004A50
0x180004a1e  mov     eax, edx
0x180004a20  add     r8, 70h ; 'p'
0x180004a24  imul    rcx, rax, 1Ch
0x180004a28  inc     edx
0x180004a2a  movzx   eax, word ptr [rcx+r15+0Ch]
0x180004a30  imul    rcx, rax, 118h
0x180004a37  add     r8, rcx
0x180004a3a  cmp     edx, r14d
0x180004a3d  jb      short loc_180004A1E
0x180004a3f  jmp     short loc_180004A50
0x180004a41  xor     edi, edi
0x180004a43  xor     eax, eax
0x180004a45  mov     [rbp+arg_18], rax
0x180004a49  xor     r14d, r14d
0x180004a4c  lea     r8d, [rdi+30h]; Size
0x180004a50  mov     rcx, gs:60h
0x180004a59  xor     edx, edx; Flags
0x180004a5b  mov     rcx, [rcx+30h]; HeapHandle
0x180004a5f  call    cs:__imp_RtlAllocateHeap
0x180004a66  nop     dword ptr [rax+rax+00h]
0x180004a6b  mov     rsi, rax
0x180004a6e  test    rax, rax
0x180004a71  jnz     short loc_180004AED
0x180004a73  mov     eax, cs:dword_180069000
0x180004a79  mov     edi, 8007000Eh
0x180004a7e  cmp     eax, 2
0x180004a81  jbe     loc_180004B95
0x180004a87  mov     rcx, cs:qword_180069018
0x180004a8e  mov     rax, cs:qword_180069010
0x180004a95  test    al, 1
0x180004a97  jz      loc_180004B95
0x180004a9d  mov     rax, rcx
0x180004aa0  and     eax, 1
0x180004aa3  cmp     rax, rcx
0x180004aa6  jnz     loc_180004B95
0x180004aac  lea     rax, aOnecoreXboxGam_31; "onecore\\xbox\\gameinput\\client\\Feedb"...
0x180004ab3  mov     dword ptr [rbp+arg_8], edi
0x180004ab6  mov     [rbp+arg_18], rax
0x180004aba  lea     rdx, byte_1800597C7
0x180004ac1  lea     rax, [rbp+arg_8]
0x180004ac5  mov     [rbp+arg_10], 40h ; '@'
0x180004acc  mov     [rsp+60h+var_30], rax
0x180004ad1  lea     rax, [rbp+arg_10]
0x180004ad5  mov     [rsp+60h+var_38], rax
0x180004ada  lea     rax, [rbp+arg_18]
0x180004ade  mov     [rsp+60h+var_40], rax
0x180004ae3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180004ae8  jmp     loc_180004B95
0x180004aed  xor     r12d, r12d
0x180004af0  xor     ecx, ecx
0x180004af2  test    r15, r15
0x180004af5  jz      short loc_180004B63
0x180004af7  mov     [rbp+arg_10], ecx
0x180004afa  lea     r12, [rax+rdi]
0x180004afe  mov     edx, ecx
0x180004b00  test    r14d, r14d
0x180004b03  jz      short loc_180004B63
0x180004b05  mov     rbx, [rbp+arg_18]
0x180004b09  mov     eax, ecx
0x180004b0b  mov     [rbp+var_20], rcx
0x180004b0f  imul    rdi, rax, 1Ch
0x180004b13  lea     rcx, [rsi+rbx]; this
0x180004b17  mov     r8d, edx; unsigned int
0x180004b1a  lea     r9, [r15+8]
0x180004b1e  mov     [r12+rax*8], rcx
0x180004b22  add     r9, rdi; struct ForceFeedbackMotorResourceProfile *
0x180004b25  mov     rdx, r13; struct GameInputDevice *
0x180004b28  call    ??0ForceFeedbackMotorStateCache@@QEAA@PEAVGameInputDevice@@IAEBUForceFeedbackMotorResourceProfile@@@Z; ForceFeedbackMotorStateCache::ForceFeedbackMotorStateCache(GameInputDevice *,uint,ForceFeedbackMotorResourceProfile const &)
0x180004b2d  movzx   eax, word ptr [rdi+r15+0Ch]
0x180004b33  add     rbx, 77h ; 'w'
0x180004b37  mov     edx, [rbp+arg_10]
0x180004b3a  imul    rcx, rax, 118h
0x180004b41  mov     rax, [rbp+var_20]
0x180004b45  inc     edx
0x180004b47  add     rbx, rcx
0x180004b4a  mov     [rbp+arg_10], edx
0x180004b4d  inc     rax
0x180004b50  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180004b54  mov     [rbp+var_20], rax
0x180004b58  cmp     edx, r14d
0x180004b5b  jb      short loc_180004B0F
0x180004b5d  mov     rbx, [rbp+var_10]
0x180004b61  xor     ecx, ecx
0x180004b63  mov     rax, [rbp+arg_8]
0x180004b67  mov     edi, ecx
0x180004b69  mov     [rsi], r14d
0x180004b6c  mov     [rsi+4], ecx
0x180004b6f  mov     [rsi+8], r12
0x180004b73  mov     [rsi+10h], r13
0x180004b77  mov     [rsi+18h], rcx
0x180004b7b  mov     qword ptr [rsi+20h], 0
0x180004b83  mov     qword ptr [rsi+28h], 0
0x180004b8b  mov     [rax], rsi
0x180004b8e  jmp     short loc_180004B95
0x180004b90  mov     edi, 1
0x180004b95  mov     rcx, rbx; this
0x180004b98  call    ?ReleaseReference@SharedBuffer@@QEAAXXZ; SharedBuffer::ReleaseReference(void)
0x180004b9d  mov     eax, edi
0x180004b9f  jmp     short loc_180004C0E
0x180004ba1  mov     eax, cs:dword_180069000
0x180004ba7  cmp     eax, 2
0x180004baa  jbe     short loc_180004C09
0x180004bac  mov     rcx, cs:qword_180069018
0x180004bb3  mov     rax, cs:qword_180069010
0x180004bba  test    al, 1
0x180004bbc  jz      short loc_180004C09
0x180004bbe  mov     rax, rcx
0x180004bc1  and     eax, 1
0x180004bc4  cmp     rax, rcx
0x180004bc7  jnz     short loc_180004C09
0x180004bc9  lea     rax, aOnecoreXboxGam_31; "onecore\\xbox\\gameinput\\client\\Feedb"...
0x180004bd0  mov     dword ptr [rbp+arg_8], 8000FFFFh
0x180004bd7  mov     [rbp+arg_18], rax
0x180004bdb  lea     rdx, word_1800599B6
0x180004be2  lea     rax, [rbp+arg_8]
0x180004be6  mov     [rbp+arg_10], 21h ; '!'
0x180004bed  mov     [rsp+60h+var_30], rax
0x180004bf2  lea     rax, [rbp+arg_10]
0x180004bf6  mov     [rsp+60h+var_38], rax
0x180004bfb  lea     rax, [rbp+arg_18]
0x180004bff  mov     [rsp+60h+var_40], rax
0x180004c04  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180004c09  mov     eax, 8000FFFFh
0x180004c0e  mov     rbx, [rsp+60h+arg_0]
0x180004c16  add     rsp, 60h
0x180004c1a  pop     r15
0x180004c1c  pop     r14
0x180004c1e  pop     r13
0x180004c20  pop     r12
0x180004c22  pop     rdi
0x180004c23  pop     rsi
0x180004c24  pop     rbp
0x180004c25  retn
```
