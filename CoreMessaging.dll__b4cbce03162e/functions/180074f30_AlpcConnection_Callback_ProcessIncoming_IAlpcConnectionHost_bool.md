# AlpcConnection::Callback_ProcessIncoming(IAlpcConnectionHost *,bool *)

- ea: `0x180074f30`
- end: `0x1800752b4`
- name: `?Callback_ProcessIncoming@AlpcConnection@@IEAAXPEAUIAlpcConnectionHost@@PEA_N@Z`
- size: `900`
- prototype: `void __fastcall(AlpcConnection *__hidden this, struct IAlpcConnectionHost *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180074f20`

## callees

- `0x18000b0bc`
- `0x1800382d8`
- `0x1800389c4`
- `0x180038b04`
- `0x18003950c`
- `0x180074f30`
- `0x1800886ec`
- `0x1800a2108`
- `0x1800c7d64`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180075126`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180075126`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800750ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800750e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800751f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075203`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075241`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075250`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800750ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800750e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800751f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075203`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075241`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180075250`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18007509f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180075181`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18007509f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180075181`

## string_xrefs

- `0x180075299`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AlpcConnection::Callback_ProcessIncoming(
        AlpcConnection *this,
        struct IAlpcConnectionHost *a2,
        bool *a3)
{
  __m128i *v5; // r14
  __int64 (__fastcall *v6)(struct IAlpcConnectionHost *, char *, _QWORD, _QWORD); // r10
  char *v7; // rdx
  int v8; // eax
  __m128i v9; // xmm0
  __m128i v10; // xmm1
  int v11; // eax
  struct AlpcBuffer *v12; // rbx
  struct _ALPC_MESSAGE_ATTRIBUTES *v13; // rdi
  struct AlpcBuffer *v14; // rbp
  size_t v15; // rax
  struct _ALPC_MESSAGE_ATTRIBUTES *v16; // r15
  int v17; // ecx
  void *v18; // rcx
  void *v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rbx
  int v22; // ecx
  void *v23; // rcx
  void *v24; // rcx
  size_t v25; // [rsp+40h] [rbp-78h]
  struct _ALPC_MESSAGE_ATTRIBUTES *v26; // [rsp+48h] [rbp-70h] BYREF
  __int64 v27; // [rsp+50h] [rbp-68h]
  __m128i v28; // [rsp+58h] [rbp-60h] BYREF
  __m128i v29; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  bool v31; // [rsp+C0h] [rbp+8h] BYREF
  bool *v32; // [rsp+D0h] [rbp+18h]
  size_t Count; // [rsp+D8h] [rbp+20h] BYREF

  v32 = a3;
  *a3 = 1;
  v5 = (__m128i *)*((_QWORD *)this + 8);
  ++*((_DWORD *)this + 22);
  if ( v5 )
  {
    v6 = *(__int64 (__fastcall **)(struct IAlpcConnectionHost *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 8LL);
    v7 = (char *)this + 96;
    if ( (*((_BYTE *)this + 58) & 1) != 0 && !this )
      v7 = 0;
    v8 = v6(a2, v7, *(_QWORD *)(v5[1].m128i_i64[1] + 32), *(unsigned int *)(v5[1].m128i_i64[1] + 8));
    if ( v8 < 0 )
      CFlat::Abandonment::FailWithHR(v8, 0, 0);
    if ( v5->m128i_i64[1] )
    {
      v28 = *v5;
      v9 = v28;
      v29 = v5[1];
      v10 = v29;
      *((_QWORD *)this + 8) = &v28;
      v5->m128i_i64[1] = 0;
      v11 = AlpcConnection::Callback_DeliverBatchedBuffers(
              this,
              a2,
              (struct PortInfo *)_mm_srli_si128(v10, 8).m128i_i64[0],
              (struct AlpcBuffer *)_mm_srli_si128(v9, 8).m128i_i64[0]);
      if ( v11 == -2018375668 )
        v11 = (*(__int64 (__fastcall **)(struct IAlpcConnectionHost *, _QWORD, _QWORD))(*(_QWORD *)a2 + 16LL))(
                a2,
                *(_QWORD *)(v29.m128i_i64[1] + 32),
                *(unsigned int *)(v29.m128i_i64[1] + 8));
      *((_QWORD *)this + 8) = v5;
      if ( v11 < 0 )
        CFlat::Abandonment::FailWithHR(v11, 0, 0);
    }
  }
  v12 = 0;
  v27 = 0;
  v13 = 0;
  v26 = 0;
  v31 = 0;
  AlpcConnection::InitializeDefaultReceiveBuffers(
    *((unsigned __int16 *)this + 28),
    (char *)this + 32,
    (char *)this + 40);
  v14 = (struct AlpcBuffer *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  v15 = *((unsigned __int16 *)this + 28);
  Count = v15;
  v16 = (struct _ALPC_MESSAGE_ATTRIBUTES *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  *(_OWORD *)v14 = 0;
  *((_OWORD *)v14 + 1) = 0;
  *((_OWORD *)v14 + 2) = 0;
  *((_OWORD *)v14 + 3) = 0;
  *((_OWORD *)v14 + 4) = 0;
  v25 = v15;
  v17 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 3), 0, 0, 0);
  if ( v17 == -1073741789 && v25 > Count )
  {
    v18 = (void *)*((_QWORD *)this + 4);
    if ( v18 )
      free(v18);
    *((_QWORD *)this + 4) = v14;
    v19 = (void *)*((_QWORD *)this + 5);
    if ( v19 )
      free(v19);
    *((_QWORD *)this + 5) = v16;
    LODWORD(Count) = 0;
    v20 = ULongLongToUInt(v25, (unsigned int *)&Count);
    if ( v20 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
        (const char *)(unsigned int)v20,
        (int)v14);
    v21 = (unsigned int)Count;
    v14 = (struct AlpcBuffer *)calloc((unsigned int)Count, 1u);
    if ( !v14 )
      CFlat::Abandonment::OutOfMemory(v21);
    AlpcConnection::InitializeMessageAttributes(&v26);
    v12 = 0;
    v27 = 0;
    v16 = v26;
    v13 = 0;
    v26 = 0;
    LOBYTE(Count) = 0;
    v17 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 3), 0, 0, 0);
  }
  else
  {
    LOBYTE(Count) = 1;
    if ( v17 == -1073741823 )
    {
      *((_DWORD *)this + 19) = 0;
LABEL_24:
      v23 = (void *)*((_QWORD *)this + 4);
      if ( v23 )
        free(v23);
      *((_QWORD *)this + 4) = v14;
      v24 = (void *)*((_QWORD *)this + 5);
      if ( v24 )
        free(v24);
      *((_QWORD *)this + 5) = v16;
      goto LABEL_32;
    }
  }
  if ( v17 == -1073741769 || (unsigned int)(v17 + 1073740032) <= 1 )
    goto LABEL_23;
  v22 = v17 | 0x10000000;
  if ( v22 < 0 )
    CFlat::Abandonment::FailWithHR(v22, 0, 0);
  AlpcConnection::Callback_ProcessReceivedBuffer(this, a2, v14, v16, &v31, v32);
  if ( !v31 )
  {
LABEL_23:
    if ( !(_BYTE)Count )
    {
      v12 = v14;
      v13 = v16;
      goto LABEL_32;
    }
    goto LABEL_24;
  }
LABEL_32:
  --*((_DWORD *)this + 22);
  *((_QWORD *)this + 8) = v5;
  if ( v13 )
    free(v13);
  if ( v12 )
    free(v12);
}

```

## disassembly

```asm
0x180074f30  mov     [rsp+arg_8], rbx
0x180074f35  mov     [rsp+arg_10], r8
0x180074f3a  push    rbp
0x180074f3b  push    rsi
0x180074f3c  push    rdi
0x180074f3d  push    r12
0x180074f3f  push    r13
0x180074f41  push    r14
0x180074f43  push    r15
0x180074f45  sub     rsp, 80h
0x180074f4c  mov     r13, rdx
0x180074f4f  mov     rsi, rcx
0x180074f52  mov     byte ptr [r8], 1
0x180074f56  mov     r14, [rcx+40h]
0x180074f5a  inc     dword ptr [rcx+58h]
0x180074f5d  test    r14, r14
0x180074f60  jz      loc_180075019
0x180074f66  mov     r9, [r14+18h]
0x180074f6a  mov     rax, [rdx]
0x180074f6d  mov     r10, [rax+8]
0x180074f71  mov     r8, [r9+20h]
0x180074f75  lea     rdx, [rcx+60h]
0x180074f79  test    byte ptr [rcx+3Ah], 1
0x180074f7d  jz      short loc_180074F88
0x180074f7f  xor     eax, eax
0x180074f81  test    rcx, rcx
0x180074f84  cmovz   rdx, rax
0x180074f88  mov     r9d, [r9+8]
0x180074f8c  mov     rcx, r13
0x180074f8f  mov     rax, r10
0x180074f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f97  test    eax, eax
0x180074f99  js      loc_18007527C
0x180074f9f  cmp     qword ptr [r14+8], 0
0x180074fa4  jz      short loc_180075019
0x180074fa6  movups  xmm0, xmmword ptr [r14]
0x180074faa  movups  [rsp+0B8h+var_60], xmm0
0x180074faf  movups  xmm1, xmmword ptr [r14+10h]
0x180074fb4  movups  [rsp+0B8h+var_50], xmm1
0x180074fb9  lea     rax, [rsp+0B8h+var_60]
0x180074fbe  mov     [rsi+40h], rax
0x180074fc2  mov     qword ptr [r14+8], 0
0x180074fca  psrldq  xmm0, 8
0x180074fcf  movq    r9, xmm0; struct AlpcBuffer *
0x180074fd4  psrldq  xmm1, 8
0x180074fd9  movq    r8, xmm1; struct PortInfo *
0x180074fde  mov     rdx, r13; struct IAlpcConnectionHost *
0x180074fe1  mov     rcx, rsi; this
0x180074fe4  call    ?Callback_DeliverBatchedBuffers@AlpcConnection@@IEAAJPEAUIAlpcConnectionHost@@PEAUPortInfo@@PEAUAlpcBuffer@@@Z; AlpcConnection::Callback_DeliverBatchedBuffers(IAlpcConnectionHost *,PortInfo *,AlpcBuffer *)
0x180074fe9  cmp     eax, 87B2080Ch
0x180074fee  jnz     short loc_18007500D
0x180074ff0  mov     rax, [r13+0]
0x180074ff4  mov     rdx, qword ptr [rsp+0B8h+var_50+8]
0x180074ff9  mov     r8d, [rdx+8]
0x180074ffd  mov     rdx, [rdx+20h]
0x180075001  mov     rcx, r13
0x180075004  mov     rax, [rax+10h]
0x180075008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007500d  mov     [rsi+40h], r14
0x180075011  test    eax, eax
0x180075013  js      loc_180075289
0x180075019  xor     ebx, ebx
0x18007501b  mov     [rsp+0B8h+var_68], rbx
0x180075020  xor     edi, edi
0x180075022  mov     [rsp+0B8h+var_70], rdi
0x180075027  mov     [rsp+0B8h+arg_0], dil
0x18007502f  lea     r8, [rsi+28h]
0x180075033  lea     rdx, [rsi+20h]
0x180075037  movzx   ecx, word ptr [rsi+38h]
0x18007503b  call    ?InitializeDefaultReceiveBuffers@AlpcConnection@@KAXGPEAV?$HeapBuffer@UAlpcBuffer@@@@PEAV?$HeapBuffer@U_ALPC_MESSAGE_ATTRIBUTES@@@@@Z; AlpcConnection::InitializeDefaultReceiveBuffers(ushort,HeapBuffer<AlpcBuffer> *,HeapBuffer<_ALPC_MESSAGE_ATTRIBUTES> *)
0x180075040  mov     rbp, [rsi+20h]
0x180075044  xor     ecx, ecx
0x180075046  mov     [rsi+20h], rcx
0x18007504a  movzx   eax, word ptr [rsi+38h]
0x18007504e  mov     [rsp+0B8h+Count], rax
0x180075056  mov     r15, [rsi+28h]
0x18007505a  mov     [rsi+28h], rcx
0x18007505e  xorps   xmm0, xmm0
0x180075061  movups  xmmword ptr [rbp+0], xmm0
0x180075065  movups  xmmword ptr [rbp+10h], xmm0
0x180075069  movups  xmmword ptr [rbp+20h], xmm0
0x18007506d  movups  xmmword ptr [rbp+30h], xmm0
0x180075071  movups  xmmword ptr [rbp+40h], xmm0
0x180075075  mov     [rsp+0B8h+var_78], rax
0x18007507a  mov     [rsp+0B8h+var_80], rcx
0x18007507f  mov     [rsp+0B8h+var_88], r15
0x180075084  lea     rax, [rsp+0B8h+var_78]
0x180075089  mov     [rsp+0B8h+var_90], rax
0x18007508e  mov     [rsp+0B8h+var_98], rbp; int
0x180075093  xor     r9d, r9d
0x180075096  xor     r8d, r8d
0x180075099  xor     edx, edx
0x18007509b  mov     rcx, [rsi+18h]
0x18007509f  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800750a5  mov     ecx, eax
0x1800750a7  cmp     eax, 0C0000023h
0x1800750ac  jnz     loc_18007520F
0x1800750b2  mov     rax, [rsp+0B8h+Count]
0x1800750ba  cmp     [rsp+0B8h+var_78], rax
0x1800750bf  jbe     loc_18007520F
0x1800750c5  mov     rcx, [rsi+20h]; Block
0x1800750c9  test    rcx, rcx
0x1800750cc  jz      short loc_1800750D4
0x1800750ce  call    cs:__imp_free
0x1800750d4  mov     [rsi+20h], rbp
0x1800750d8  mov     rcx, [rsi+28h]; Block
0x1800750dc  test    rcx, rcx
0x1800750df  jz      short loc_1800750E7
0x1800750e1  call    cs:__imp_free
0x1800750e7  mov     [rsi+28h], r15
0x1800750eb  mov     dword ptr [rsp+0B8h+Count], 0
0x1800750f6  lea     rdx, [rsp+0B8h+Count]; unsigned int *
0x1800750fe  mov     rcx, [rsp+0B8h+var_78]; unsigned __int64
0x180075103  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180075108  mov     rcx, [rsp+0B8h]; this
0x180075110  test    eax, eax
0x180075112  js      loc_180075296
0x180075118  mov     ebx, dword ptr [rsp+0B8h+Count]
0x18007511f  mov     edx, 1; Size
0x180075124  mov     ecx, ebx; Count
0x180075126  call    cs:__imp_calloc
0x18007512c  mov     rbp, rax
0x18007512f  test    rax, rax
0x180075132  jz      loc_1800752AB
0x180075138  lea     rcx, [rsp+0B8h+var_70]
0x18007513d  call    ?InitializeMessageAttributes@AlpcConnection@@KAXPEAV?$HeapBuffer@U_ALPC_MESSAGE_ATTRIBUTES@@@@@Z; AlpcConnection::InitializeMessageAttributes(HeapBuffer<_ALPC_MESSAGE_ATTRIBUTES> *)
0x180075142  xor     ebx, ebx
0x180075144  mov     [rsp+0B8h+var_68], rbx
0x180075149  mov     r15, [rsp+0B8h+var_70]
0x18007514e  xor     edi, edi
0x180075150  mov     [rsp+0B8h+var_70], rdi
0x180075155  mov     byte ptr [rsp+0B8h+Count], bl
0x18007515c  mov     [rsp+0B8h+var_80], rbx
0x180075161  mov     [rsp+0B8h+var_88], r15
0x180075166  lea     rax, [rsp+0B8h+var_78]
0x18007516b  mov     [rsp+0B8h+var_90], rax
0x180075170  mov     [rsp+0B8h+var_98], rbp
0x180075175  xor     r9d, r9d
0x180075178  xor     r8d, r8d
0x18007517b  xor     edx, edx
0x18007517d  mov     rcx, [rsi+18h]
0x180075181  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180075187  mov     ecx, eax
0x180075189  cmp     ecx, 0C0000037h
0x18007518f  jz      short loc_1800751DD
0x180075191  lea     eax, [rcx+3FFFF900h]
0x180075197  cmp     eax, 1
0x18007519a  jbe     short loc_1800751DD
0x18007519c  or      ecx, 10000000h; int
0x1800751a2  jl      loc_180075271
0x1800751a8  mov     rax, [rsp+0B8h+arg_10]
0x1800751b0  mov     [rsp+0B8h+var_90], rax; bool *
0x1800751b5  lea     rax, [rsp+0B8h+arg_0]
0x1800751bd  mov     [rsp+0B8h+var_98], rax; bool *
0x1800751c2  mov     r9, r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800751c5  mov     r8, rbp; struct AlpcBuffer *
0x1800751c8  mov     rdx, r13; struct IAlpcConnectionHost *
0x1800751cb  mov     rcx, rsi; this
0x1800751ce  call    ?Callback_ProcessReceivedBuffer@AlpcConnection@@AEAAXPEAUIAlpcConnectionHost@@PEAUAlpcBuffer@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEA_N3@Z; AlpcConnection::Callback_ProcessReceivedBuffer(IAlpcConnectionHost *,AlpcBuffer *,_ALPC_MESSAGE_ATTRIBUTES *,bool *,bool *)
0x1800751d3  cmp     [rsp+0B8h+arg_0], 0
0x1800751db  jnz     short loc_180075232
0x1800751dd  cmp     byte ptr [rsp+0B8h+Count], 0
0x1800751e5  jz      short loc_18007522C
0x1800751e7  mov     rcx, [rsi+20h]; Block
0x1800751eb  test    rcx, rcx
0x1800751ee  jz      short loc_1800751F6
0x1800751f0  call    cs:__imp_free
0x1800751f6  mov     [rsi+20h], rbp
0x1800751fa  mov     rcx, [rsi+28h]; Block
0x1800751fe  test    rcx, rcx
0x180075201  jz      short loc_180075209
0x180075203  call    cs:__imp_free
0x180075209  mov     [rsi+28h], r15
0x18007520d  jmp     short loc_180075232
0x18007520f  mov     byte ptr [rsp+0B8h+Count], 1
0x180075217  cmp     ecx, 0C0000001h
0x18007521d  jnz     loc_180075189
0x180075223  mov     dword ptr [rsi+4Ch], 0
0x18007522a  jmp     short loc_1800751E7
0x18007522c  mov     rbx, rbp
0x18007522f  mov     rdi, r15
0x180075232  dec     dword ptr [rsi+58h]
0x180075235  mov     [rsi+40h], r14
0x180075239  test    rdi, rdi
0x18007523c  jz      short loc_180075248
0x18007523e  mov     rcx, rdi; Block
0x180075241  call    cs:__imp_free
0x180075247  nop
0x180075248  test    rbx, rbx
0x18007524b  jz      short loc_180075256
0x18007524d  mov     rcx, rbx; Block
0x180075250  call    cs:__imp_free
0x180075256  mov     rbx, [rsp+0B8h+arg_8]
0x18007525e  add     rsp, 80h
0x180075265  pop     r15
0x180075267  pop     r14
0x180075269  pop     r13
0x18007526b  pop     r12
0x18007526d  pop     rdi
0x18007526e  pop     rsi
0x18007526f  pop     rbp
0x180075270  retn
0x180075271  xor     r8d, r8d; int
0x180075274  xor     edx, edx; void *
0x180075276  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18007527c  xor     r8d, r8d; int
0x18007527f  xor     edx, edx; void *
0x180075281  mov     ecx, eax; int
0x180075283  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180075289  xor     r8d, r8d; int
0x18007528c  xor     edx, edx; void *
0x18007528e  mov     ecx, eax; int
0x180075290  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180075296  mov     r9d, eax; char *
0x180075299  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800752a0  mov     edx, 10Fh; void *
0x1800752a5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800752ab  mov     rcx, rbx; unsigned __int64
0x1800752ae  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
```
