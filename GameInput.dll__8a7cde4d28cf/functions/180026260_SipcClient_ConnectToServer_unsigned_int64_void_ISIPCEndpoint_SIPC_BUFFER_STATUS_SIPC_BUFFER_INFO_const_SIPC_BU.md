# SipcClient::ConnectToServer(unsigned __int64,void (*)(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *),void (*)(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *),void *,uint *,ISIPCEndpoint * *)

- ea: `0x180026260`
- end: `0x180026442`
- name: `?ConnectToServer@SipcClient@@UEAAJ_KP6AXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@3PEAX@ZP6AX1W4SIPC_ENDPOINT_STATUS@@4@Z4PEAIPEAPEAU2@@Z`
- size: `482`
- prototype: `__int64 __usercall@<rax>(SipcClient *__hidden this@<rcx>, unsigned __int64@<rdx>, void (__high *)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *)@<r8>, void (__high *)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *)@<r9>, void *, unsigned int *, struct ISIPCEndpoint **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x18000c11c`
- `0x180024e3c`
- `0x180025b80`
- `0x180026260`
- `0x180026d6c`
- `0x1800299bc`
- `0x18002ad20`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800262f0`
- `ntdll!RtlAllocateHeap` at `0x1800262f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800262c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800262c4`

## pseudocode

```c
__int64 __fastcall SipcClient::ConnectToServer(
        SipcClient *this,
        unsigned __int64 a2,
        void (__high *a3)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *),
        void (__high *a4)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *),
        void *a5,
        unsigned int *a6,
        struct ISIPCEndpoint **a7)
{
  unsigned int *v7; // r12
  struct ISIPCEndpoint **v8; // r13
  _DWORD *v11; // rsi
  _QWORD *i; // rbx
  int v13; // edi
  char *Heap; // rax
  void **v15; // rdi
  SipcEndpoint **v16; // r14
  int ClientEndpoint; // ebx
  const struct std::nothrow_t *v18; // rdx
  __int64 result; // rax
  _QWORD *v20; // rax

  v7 = a6;
  v8 = a7;
  *a6 = 0;
  *v8 = 0;
  if ( !a3 || !a4 )
    return 2147942487LL;
  v11 = (_DWORD *)((char *)this + 104);
  for ( i = (_QWORD *)*((_QWORD *)this + 13); i != (_QWORD *)v11; i = (_QWORD *)*i )
  {
    v13 = *(_DWORD *)(i[2] + 56LL);
    if ( v13 == GetCurrentThreadId() )
      return 2147942487LL;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
  v15 = (void **)Heap;
  if ( !Heap )
    return 2147942414LL;
  *((_QWORD *)Heap + 2) = 0;
  *((_QWORD *)Heap + 3) = 0;
  *((_QWORD *)Heap + 4) = 0;
  *((_QWORD *)Heap + 5) = 0;
  *((_QWORD *)Heap + 6) = 0;
  LODWORD(a6) = 0;
  v16 = (SipcEndpoint **)(Heap + 16);
  ClientEndpoint = SipcEndpoint::CreateClientEndpoint(
                     this,
                     a2,
                     a3,
                     a4,
                     a5,
                     (unsigned int *)&a6,
                     (struct SipcEndpoint **)Heap + 2);
  if ( ClientEndpoint < 0 )
  {
LABEL_9:
    SipcClient::EndpointListEntry::~EndpointListEntry((SipcClient::EndpointListEntry *)v15);
    operator delete(v15, v18);
    return (unsigned int)ClientEndpoint;
  }
  v15[3] = this;
  SipcEndpoint::GetWaitHandles(*v16, v15 + 4, v15 + 5, v15 + 6);
  ClientEndpoint = AggregateWaitHandle::AddHandle((AggregateWaitHandle *)((char *)v15[3] + 56), v15[4]);
  if ( ClientEndpoint < 0
    || (ClientEndpoint = AggregateWaitHandle::AddHandle((AggregateWaitHandle *)((char *)v15[3] + 56), v15[5]),
        ClientEndpoint < 0)
    || (ClientEndpoint = AggregateWaitHandle::AddHandle((AggregateWaitHandle *)((char *)v15[3] + 56), v15[6]),
        ClientEndpoint < 0) )
  {
    SipcObjectBase<ISIPCEndpoint>::Release(*v16);
    goto LABEL_9;
  }
  *v7 = (unsigned int)a6;
  *v8 = *v16;
  v20 = *(_QWORD **)v11;
  if ( *(_DWORD **)(*(_QWORD *)v11 + 8LL) != v11 )
    __fastfail(3u);
  *v15 = v20;
  v15[1] = v11;
  v20[1] = v15;
  ++v11[4];
  result = 0;
  *(_QWORD *)v11 = v15;
  return result;
}

```

## disassembly

```asm
0x180026260  mov     [rsp+arg_0], rbx
0x180026265  mov     [rsp+arg_10], r8
0x18002626a  mov     [rsp+arg_8], rdx
0x18002626f  push    rbp
0x180026270  push    rsi
0x180026271  push    rdi
0x180026272  push    r12
0x180026274  push    r13
0x180026276  push    r14
0x180026278  push    r15
0x18002627a  sub     rsp, 40h
0x18002627e  mov     r12, [rsp+78h+arg_28]
0x180026286  xor     r14d, r14d
0x180026289  mov     r13, [rsp+78h+arg_30]
0x180026291  mov     r15, r9
0x180026294  mov     rbp, rcx
0x180026297  mov     [r12], r14d
0x18002629b  mov     [r13+0], r14
0x18002629f  test    r8, r8
0x1800262a2  jz      loc_180026424
0x1800262a8  test    r9, r9
0x1800262ab  jz      loc_180026424
0x1800262b1  lea     rsi, [rcx+68h]
0x1800262b5  mov     rbx, [rsi]
0x1800262b8  cmp     rbx, rsi
0x1800262bb  jz      short loc_1800262DD
0x1800262bd  mov     rax, [rbx+10h]
0x1800262c1  mov     edi, [rax+38h]
0x1800262c4  call    cs:__imp_GetCurrentThreadId
0x1800262cb  nop     dword ptr [rax+rax+00h]
0x1800262d0  cmp     edi, eax
0x1800262d2  jz      loc_180026424
0x1800262d8  mov     rbx, [rbx]
0x1800262db  jmp     short loc_1800262B8
0x1800262dd  mov     rcx, gs:60h
0x1800262e6  xor     edx, edx; Flags
0x1800262e8  mov     rcx, [rcx+30h]; HeapHandle
0x1800262ec  lea     r8d, [rdx+38h]; Size
0x1800262f0  call    cs:__imp_RtlAllocateHeap
0x1800262f7  nop     dword ptr [rax+rax+00h]
0x1800262fc  mov     rdi, rax
0x1800262ff  test    rax, rax
0x180026302  jz      loc_18002641D
0x180026308  mov     r8, [rsp+78h+arg_10]; void (__high *)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *)
0x180026310  mov     r9, r15; void (__high *)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *)
0x180026313  mov     rdx, [rsp+78h+arg_8]; unsigned __int64
0x18002631b  mov     rcx, rbp; struct SipcClient *
0x18002631e  mov     [rax+10h], r14
0x180026322  mov     [rax+18h], r14
0x180026326  mov     [rax+20h], r14
0x18002632a  mov     [rax+28h], r14
0x18002632e  mov     [rax+30h], r14
0x180026332  mov     dword ptr [rsp+78h+arg_28], r14d
0x18002633a  lea     r14, [rax+10h]
0x18002633e  lea     rax, [rsp+78h+arg_28]
0x180026346  mov     [rsp+78h+var_48], r14; struct SipcEndpoint **
0x18002634b  mov     [rsp+78h+var_50], rax; unsigned int *
0x180026350  mov     rax, [rsp+78h+arg_20]
0x180026358  mov     [rsp+78h+var_58], rax; void *
0x18002635d  call    ?CreateClientEndpoint@SipcEndpoint@@SAJPEAVSipcClient@@_KP6AXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@4PEAX@ZP6AX2W4SIPC_ENDPOINT_STATUS@@5@Z5PEAIPEAPEAV1@@Z; SipcEndpoint::CreateClientEndpoint(SipcClient *,unsigned __int64,void (*)(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *),void (*)(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *),void *,uint *,SipcEndpoint * *)
0x180026362  mov     ebx, eax
0x180026364  test    eax, eax
0x180026366  jns     short loc_18002637F
0x180026368  mov     rcx, rdi; this
0x18002636b  call    ??1EndpointListEntry@SipcClient@@QEAA@XZ; SipcClient::EndpointListEntry::~EndpointListEntry(void)
0x180026370  mov     rcx, rdi; P
0x180026373  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026378  mov     eax, ebx
0x18002637a  jmp     loc_180026429
0x18002637f  mov     [rdi+18h], rbp
0x180026383  lea     r9, [rdi+30h]; void **
0x180026387  mov     rcx, [r14]; this
0x18002638a  lea     r8, [rdi+28h]; void **
0x18002638e  lea     rdx, [rdi+20h]; void **
0x180026392  call    ?GetWaitHandles@SipcEndpoint@@QEBAXAEAPEAX00@Z; SipcEndpoint::GetWaitHandles(void * &,void * &,void * &)
0x180026397  mov     rcx, [rdi+18h]
0x18002639b  mov     rdx, [rdi+20h]; void *
0x18002639f  add     rcx, 38h ; '8'; this
0x1800263a3  call    ?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z; AggregateWaitHandle::AddHandle(void *)
0x1800263a8  mov     ebx, eax
0x1800263aa  test    eax, eax
0x1800263ac  js      short loc_1800263DC
0x1800263ae  mov     rcx, [rdi+18h]
0x1800263b2  mov     rdx, [rdi+28h]; void *
0x1800263b6  add     rcx, 38h ; '8'; this
0x1800263ba  call    ?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z; AggregateWaitHandle::AddHandle(void *)
0x1800263bf  mov     ebx, eax
0x1800263c1  test    eax, eax
0x1800263c3  js      short loc_1800263DC
0x1800263c5  mov     rcx, [rdi+18h]
0x1800263c9  mov     rdx, [rdi+30h]; void *
0x1800263cd  add     rcx, 38h ; '8'; this
0x1800263d1  call    ?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z; AggregateWaitHandle::AddHandle(void *)
0x1800263d6  mov     ebx, eax
0x1800263d8  test    eax, eax
0x1800263da  jns     short loc_1800263E6
0x1800263dc  mov     rcx, [r14]
0x1800263df  call    ?Release@?$SipcObjectBase@UISIPCEndpoint@@@@UEAAKXZ; SipcObjectBase<ISIPCEndpoint>::Release(void)
0x1800263e4  jmp     short loc_180026368
0x1800263e6  mov     eax, dword ptr [rsp+78h+arg_28]
0x1800263ed  mov     [r12], eax
0x1800263f1  mov     rax, [r14]
0x1800263f4  mov     [r13+0], rax
0x1800263f8  mov     rax, [rsi]
0x1800263fb  cmp     [rax+8], rsi
0x1800263ff  jz      short loc_180026408
0x180026401  mov     ecx, 3
0x180026406  int     29h; Win8: RtlFailFast(ecx)
0x180026408  mov     [rdi], rax
0x18002640b  mov     [rdi+8], rsi
0x18002640f  mov     [rax+8], rdi
0x180026413  inc     dword ptr [rsi+10h]
0x180026416  xor     eax, eax
0x180026418  mov     [rsi], rdi
0x18002641b  jmp     short loc_180026429
0x18002641d  mov     eax, 8007000Eh
0x180026422  jmp     short loc_180026429
0x180026424  mov     eax, 80070057h
0x180026429  mov     rbx, [rsp+78h+arg_0]
0x180026431  add     rsp, 40h
0x180026435  pop     r15
0x180026437  pop     r14
0x180026439  pop     r13
0x18002643b  pop     r12
0x18002643d  pop     rdi
0x18002643e  pop     rsi
0x18002643f  pop     rbp
0x180026440  retn
```
