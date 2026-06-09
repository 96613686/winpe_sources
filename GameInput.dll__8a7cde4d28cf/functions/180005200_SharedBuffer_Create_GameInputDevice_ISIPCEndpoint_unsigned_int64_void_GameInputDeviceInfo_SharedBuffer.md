# SharedBuffer::Create(GameInputDevice *,ISIPCEndpoint *,unsigned __int64,void *,GameInputDeviceInfo * *,SharedBuffer * *)

- ea: `0x180005200`
- end: `0x180005578`
- name: `?Create@SharedBuffer@@SAJPEAVGameInputDevice@@PEAUISIPCEndpoint@@_KPEAXPEAPEAUGameInputDeviceInfo@@PEAPEAV1@@Z`
- size: `888`
- prototype: `__int64 __fastcall(struct GameInputDevice *, struct ISIPCEndpoint *, unsigned __int64, void *, struct GameInputDeviceInfo **, struct SharedBuffer **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a91c`

## callees

- `0x180001304`
- `0x1800046f4`
- `0x180005200`
- `0x1800237b0`
- `0x180024aec`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005425`
- `ntdll!RtlAllocateHeap` at `0x180005425`

## pseudocode

```c
__int64 __fastcall SharedBuffer::Create(
        struct GameInputDevice *a1,
        struct ISIPCEndpoint *a2,
        unsigned __int64 a3,
        void *a4,
        struct GameInputDeviceInfo **a5,
        struct SharedBuffer **a6)
{
  struct SharedBuffer **v6; // r14
  char v8; // al
  int v9; // r8d
  __int64 v10; // r9
  unsigned int *v11; // rdx
  int v12; // ecx
  __int16 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // rbx
  __int64 v17; // r13
  unsigned int *v18; // rsi
  struct GameInputDeviceInfo *v19; // rcx
  __int64 result; // rax
  int v21; // edi
  int v22; // r8d
  int v23; // r9d
  _DWORD *Heap; // rdi
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v29; // rdx
  bool v30; // cf
  __int64 v31; // rcx
  __int64 v32; // r11
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  __int64 v35; // r10
  __int64 v36; // rax
  __int64 v37; // r9
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  unsigned int v40; // eax
  unsigned __int64 v41; // [rsp+20h] [rbp-30h]
  int v42; // [rsp+40h] [rbp-10h] BYREF
  const char *v43; // [rsp+48h] [rbp-8h] BYREF

  v6 = a6;
  a6 = 0;
  *v6 = 0;
  v8 = -LayoutBase::VerifyMemberBounds(a3, a4, a3, (unsigned __int64)a4, v41, (unsigned __int64 *)&a6);
  v11 = (unsigned int *)(v10 & -(__int64)(v8 != 0));
  if ( !v11 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return 2147942487LL;
    v12 = qword_180069018;
    if ( (qword_180069010 & 1) == 0 || (qword_180069018 & 1) != qword_180069018 )
      return 2147942487LL;
    v42 = 55;
    v13 = (__int16 *)byte_18005947B;
LABEL_14:
    v43 = "onecore\\xbox\\gameinput\\client\\SharedBuffer.cpp";
    LODWORD(a6) = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v13,
      v9,
      v10,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&a6);
    return 2147942487LL;
  }
  v14 = *(unsigned int *)((v10 & -(__int64)(v8 != 0)) + 4);
  v15 = ((unsigned __int64)v11 + v14) & -(__int64)(v14 != 0);
  v16 = ((unsigned __int64)v11 + v11[2]) & -(__int64)(v11[2] != 0);
  v17 = ((unsigned __int64)v11 + v11[3]) & -(__int64)(v11[3] != 0);
  v18 = (unsigned int *)(((unsigned __int64)v11 + v11[4]) & -(__int64)(v11[4] != 0));
  v19 = *a5;
  v43 = (const char *)(((unsigned __int64)v11 + v11[6]) & -(__int64)(v11[6] != 0));
  if ( v19 )
  {
    if ( *(_DWORD *)v16 != *(_DWORD *)v19 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return 2147942487LL;
      v12 = qword_180069018;
      if ( (qword_180069010 & 1) == 0 || (qword_180069018 & 1) != qword_180069018 )
        return 2147942487LL;
      v42 = 76;
      v13 = &word_18005943E;
      goto LABEL_14;
    }
    if ( *(_DWORD *)(v16 + 96) == 1 )
      *((_QWORD *)v19 + 2) = *(_QWORD *)(v16 + 16);
  }
  else
  {
    result = SharedBuffer::CopyAndRebaseDeviceInfo((const struct GameInputDeviceInfo *)v16, a5);
    if ( (int)result < 0 )
      return result;
  }
  a6 = 0;
  v21 = ReadingPool::Attach((const struct InputDataLayout *)v18, (struct ReadingPool **)&a6);
  if ( v21 >= 0 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    if ( Heap )
    {
      v27 = v18[9];
      v28 = v18[10];
      v29 = (unsigned __int64)v18 + v27;
      v30 = v27 != 0;
      v31 = v18[5];
      v32 = v29 & -(__int64)v30;
      v33 = (unsigned __int64)v18 + v31;
      v30 = v31 != 0;
      v34 = (unsigned __int64)v18 + v28;
      v35 = v33 & -(__int64)v30;
      v30 = v28 != 0;
      v36 = v18[1];
      v37 = v34 & -(__int64)v30;
      v38 = (unsigned __int64)v18 + v36;
      v30 = v36 != 0;
      v39 = v18[2];
      Heap[5] = *(_DWORD *)(v16 + 104);
      *((_QWORD *)Heap + 3) = a6;
      *((_QWORD *)Heap + 10) = v43;
      *((_QWORD *)Heap + 12) = a1;
      Heap[4] = 0;
      *((_QWORD *)Heap + 4) = v17;
      *((_QWORD *)Heap + 5) = ((unsigned __int64)v18 + v39) & -(__int64)(v39 != 0);
      *((_QWORD *)Heap + 6) = v38 & -(__int64)v30;
      *((_QWORD *)Heap + 7) = v37;
      *((_QWORD *)Heap + 8) = v35;
      *((_QWORD *)Heap + 9) = v32;
      *((_QWORD *)Heap + 11) = v15;
      *((_QWORD *)Heap + 13) = a2;
      *((_QWORD *)Heap + 14) = a4;
      (*(void (__fastcall **)(struct ISIPCEndpoint *))(*(_QWORD *)a2 + 8LL))(a2);
      result = 0;
      *v6 = (struct SharedBuffer *)Heap;
    }
    else
    {
      v40 = dword_180069000;
      *v6 = 0;
      if ( v40 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
      {
        LODWORD(a6) = -2147024882;
        v42 = 116;
        v43 = "onecore\\xbox\\gameinput\\client\\SharedBuffer.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&v43,
          (unsigned int)&byte_180059777,
          v25,
          v26,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&a6);
      }
      return 2147942414LL;
    }
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      LODWORD(a6) = v21;
      v43 = "onecore\\xbox\\gameinput\\client\\SharedBuffer.cpp";
      v42 = 98;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_180059B21,
        v22,
        v23,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&a6);
    }
    return (unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x180005200  mov     r11, rsp
0x180005203  mov     [r11+18h], rbx
0x180005207  mov     [r11+10h], rdx
0x18000520b  mov     [r11+8], rcx
0x18000520f  push    rbp
0x180005210  push    rsi
0x180005211  push    rdi
0x180005212  push    r12
0x180005214  push    r13
0x180005216  push    r14
0x180005218  push    r15
0x18000521a  mov     rbp, rsp
0x18000521d  sub     rsp, 50h
0x180005221  mov     r14, [rbp+arg_28]
0x180005225  lea     rax, [rbp+arg_28]
0x180005229  xor     edi, edi
0x18000522b  mov     [r11-60h], rax
0x18000522f  mov     rdx, r9; void *
0x180005232  mov     [rbp+arg_28], rdi
0x180005236  mov     rcx, r8; unsigned __int64
0x180005239  mov     r15, r9
0x18000523c  mov     [r14], rdi
0x18000523f  call    ?VerifyMemberBounds@LayoutBase@@KA_N_KPEBX000AEA_K@Z; LayoutBase::VerifyMemberBounds(unsigned __int64,void const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180005244  neg     al
0x180005246  sbb     rdx, rdx
0x180005249  and     rdx, r9
0x18000524c  jnz     short loc_180005295
0x18000524e  mov     eax, cs:dword_180069000
0x180005254  cmp     eax, 2
0x180005257  jbe     loc_180005378
0x18000525d  mov     rcx, cs:qword_180069018
0x180005264  mov     rax, cs:qword_180069010
0x18000526b  test    al, 1
0x18000526d  jz      loc_180005378
0x180005273  mov     rax, rcx
0x180005276  and     eax, 1
0x180005279  cmp     rax, rcx
0x18000527c  jnz     loc_180005378
0x180005282  mov     [rbp+var_10], 37h ; '7'
0x180005289  lea     rdx, byte_18005947B
0x180005290  jmp     loc_180005346
0x180005295  mov     eax, [rdx+4]
0x180005298  lea     rcx, [rdx+rax]
0x18000529c  neg     rax
0x18000529f  mov     eax, [rdx+8]
0x1800052a2  sbb     r12, r12
0x1800052a5  and     r12, rcx
0x1800052a8  lea     rcx, [rdx+rax]
0x1800052ac  neg     rax
0x1800052af  mov     eax, [rdx+0Ch]
0x1800052b2  sbb     rbx, rbx
0x1800052b5  and     rbx, rcx
0x1800052b8  lea     rcx, [rdx+rax]
0x1800052bc  neg     rax
0x1800052bf  mov     eax, [rdx+10h]
0x1800052c2  sbb     r13, r13
0x1800052c5  and     r13, rcx
0x1800052c8  lea     rcx, [rdx+rax]
0x1800052cc  neg     rax
0x1800052cf  mov     eax, [rdx+18h]
0x1800052d2  sbb     rsi, rsi
0x1800052d5  and     rsi, rcx
0x1800052d8  lea     rcx, [rdx+rax]
0x1800052dc  mov     rdx, [rbp+arg_20]; struct GameInputDeviceInfo **
0x1800052e0  neg     rax
0x1800052e3  sbb     rax, rax
0x1800052e6  and     rax, rcx
0x1800052e9  mov     rcx, [rdx]
0x1800052ec  mov     [rbp+var_8], rax
0x1800052f0  test    rcx, rcx
0x1800052f3  jnz     short loc_18000530A
0x1800052f5  mov     rcx, rbx; Src
0x1800052f8  call    ?CopyAndRebaseDeviceInfo@SharedBuffer@@CAJPEBUGameInputDeviceInfo@@PEAPEAU2@@Z; SharedBuffer::CopyAndRebaseDeviceInfo(GameInputDeviceInfo const *,GameInputDeviceInfo * *)
0x1800052fd  test    eax, eax
0x1800052ff  jns     loc_180005390
0x180005305  jmp     loc_18000555F
0x18000530a  mov     eax, [rcx]
0x18000530c  cmp     [rbx], eax
0x18000530e  jz      short loc_180005382
0x180005310  mov     eax, cs:dword_180069000
0x180005316  cmp     eax, 2
0x180005319  jbe     short loc_180005378
0x18000531b  mov     rcx, cs:qword_180069018
0x180005322  mov     rax, cs:qword_180069010
0x180005329  test    al, 1
0x18000532b  jz      short loc_180005378
0x18000532d  mov     rax, rcx
0x180005330  and     eax, 1
0x180005333  cmp     rax, rcx
0x180005336  jnz     short loc_180005378
0x180005338  mov     [rbp+var_10], 4Ch ; 'L'
0x18000533f  lea     rdx, word_18005943E
0x180005346  lea     rax, aOnecoreXboxGam_20; "onecore\\xbox\\gameinput\\client\\Share"...
0x18000534d  mov     [rbp+var_8], rax
0x180005351  lea     rax, [rbp+arg_28]
0x180005355  mov     [rsp+50h+var_20], rax
0x18000535a  lea     rax, [rbp+var_10]
0x18000535e  mov     [rsp+50h+var_28], rax
0x180005363  lea     rax, [rbp+var_8]
0x180005367  mov     [rsp+50h+var_30], rax
0x18000536c  mov     dword ptr [rbp+arg_28], 80070057h
0x180005373  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180005378  mov     eax, 80070057h
0x18000537d  jmp     loc_18000555F
0x180005382  cmp     dword ptr [rbx+60h], 1
0x180005386  jnz     short loc_180005390
0x180005388  mov     rax, [rbx+10h]
0x18000538c  mov     [rcx+10h], rax
0x180005390  lea     rdx, [rbp+arg_28]; struct ReadingPool **
0x180005394  mov     [rbp+arg_28], rdi
0x180005398  mov     rcx, rsi; struct InputDataLayout *
0x18000539b  call    ?Attach@ReadingPool@@SAJPEBVInputDataLayout@@PEAPEAV1@@Z; ReadingPool::Attach(InputDataLayout const *,ReadingPool * *)
0x1800053a0  mov     edi, eax
0x1800053a2  test    eax, eax
0x1800053a4  jns     short loc_180005412
0x1800053a6  mov     ecx, cs:dword_180069000
0x1800053ac  cmp     ecx, 2
0x1800053af  jbe     short loc_18000540B
0x1800053b1  mov     rdx, cs:qword_180069018
0x1800053b8  mov     rcx, cs:qword_180069010
0x1800053bf  test    cl, 1
0x1800053c2  jz      short loc_18000540B
0x1800053c4  mov     rax, rdx
0x1800053c7  and     eax, 1
0x1800053ca  cmp     rax, rdx
0x1800053cd  jnz     short loc_18000540B
0x1800053cf  lea     rax, aOnecoreXboxGam_20; "onecore\\xbox\\gameinput\\client\\Share"...
0x1800053d6  mov     dword ptr [rbp+arg_28], edi
0x1800053d9  mov     [rbp+var_8], rax
0x1800053dd  lea     rdx, byte_180059B21
0x1800053e4  lea     rax, [rbp+arg_28]
0x1800053e8  mov     [rbp+var_10], 62h ; 'b'
0x1800053ef  mov     [rsp+50h+var_20], rax
0x1800053f4  lea     rax, [rbp+var_10]
0x1800053f8  mov     [rsp+50h+var_28], rax
0x1800053fd  lea     rax, [rbp+var_8]
0x180005401  mov     [rsp+50h+var_30], rax
0x180005406  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000540b  mov     eax, edi
0x18000540d  jmp     loc_18000555F
0x180005412  mov     rcx, gs:60h
0x18000541b  xor     edx, edx; Flags
0x18000541d  mov     rcx, [rcx+30h]; HeapHandle
0x180005421  lea     r8d, [rdx+78h]; Size
0x180005425  call    cs:__imp_RtlAllocateHeap
0x18000542c  nop     dword ptr [rax+rax+00h]
0x180005431  mov     rdi, rax
0x180005434  test    rax, rax
0x180005437  jz      loc_1800054ED
0x18000543d  mov     ecx, [rsi+24h]
0x180005440  mov     eax, [rsi+28h]
0x180005443  lea     rdx, [rcx+rsi]
0x180005447  neg     rcx
0x18000544a  mov     ecx, [rsi+14h]
0x18000544d  sbb     r11, r11
0x180005450  and     r11, rdx
0x180005453  lea     rdx, [rcx+rsi]
0x180005457  neg     rcx
0x18000545a  lea     rcx, [rax+rsi]
0x18000545e  sbb     r10, r10
0x180005461  and     r10, rdx
0x180005464  neg     rax
0x180005467  mov     eax, [rsi+4]
0x18000546a  sbb     r9, r9
0x18000546d  and     r9, rcx
0x180005470  lea     rcx, [rax+rsi]
0x180005474  neg     rax
0x180005477  mov     eax, [rsi+8]
0x18000547a  sbb     r8, r8
0x18000547d  and     r8, rcx
0x180005480  lea     rcx, [rax+rsi]
0x180005484  neg     rax
0x180005487  mov     eax, [rbx+68h]
0x18000548a  mov     [rdi+14h], eax
0x18000548d  sbb     rdx, rdx
0x180005490  mov     rax, [rbp+arg_28]
0x180005494  and     rdx, rcx
0x180005497  mov     rcx, [rbp+arg_8]
0x18000549b  mov     [rdi+18h], rax
0x18000549f  mov     rax, [rbp+var_8]
0x1800054a3  mov     [rdi+50h], rax
0x1800054a7  mov     rax, [rbp+arg_0]
0x1800054ab  mov     [rdi+60h], rax
0x1800054af  mov     dword ptr [rdi+10h], 0
0x1800054b6  mov     [rdi+20h], r13
0x1800054ba  mov     [rdi+28h], rdx
0x1800054be  mov     [rdi+30h], r8
0x1800054c2  mov     [rdi+38h], r9
0x1800054c6  mov     [rdi+40h], r10
0x1800054ca  mov     [rdi+48h], r11
0x1800054ce  mov     [rdi+58h], r12
0x1800054d2  mov     [rdi+68h], rcx
0x1800054d6  mov     [rdi+70h], r15
0x1800054da  mov     rax, [rcx]
0x1800054dd  mov     rax, [rax+8]
0x1800054e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e6  xor     eax, eax
0x1800054e8  mov     [r14], rdi
0x1800054eb  jmp     short loc_18000555F
0x1800054ed  mov     eax, cs:dword_180069000
0x1800054f3  mov     ebx, 8007000Eh
0x1800054f8  mov     qword ptr [r14], 0
0x1800054ff  cmp     eax, 2
0x180005502  jbe     short loc_18000555D
0x180005504  mov     rcx, cs:qword_180069018
0x18000550b  mov     rax, cs:qword_180069010
0x180005512  test    al, 1
0x180005514  jz      short loc_18000555D
0x180005516  mov     rax, rcx
0x180005519  and     eax, 1
0x18000551c  cmp     rax, rcx
0x18000551f  jnz     short loc_18000555D
0x180005521  lea     rcx, [rbp+arg_28]
0x180005525  mov     dword ptr [rbp+arg_28], ebx
0x180005528  mov     [rsp+50h+var_20], rcx
0x18000552d  lea     rax, aOnecoreXboxGam_20; "onecore\\xbox\\gameinput\\client\\Share"...
0x180005534  lea     rcx, [rbp+var_10]
0x180005538  mov     [rbp+var_10], 74h ; 't'
0x18000553f  mov     [rsp+50h+var_28], rcx
0x180005544  lea     rdx, byte_180059777
0x18000554b  lea     rcx, [rbp+var_8]
0x18000554f  mov     [rbp+var_8], rax
0x180005553  mov     [rsp+50h+var_30], rcx
0x180005558  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000555d  mov     eax, ebx
0x18000555f  mov     rbx, [rsp+50h+arg_10]
0x180005567  add     rsp, 50h
0x18000556b  pop     r15
0x18000556d  pop     r14
0x18000556f  pop     r13
0x180005571  pop     r12
0x180005573  pop     rdi
0x180005574  pop     rsi
0x180005575  pop     rbp
0x180005576  retn
```
