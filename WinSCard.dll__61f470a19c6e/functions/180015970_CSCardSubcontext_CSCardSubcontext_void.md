# CSCardSubcontext::~CSCardSubcontext(void)

- ea: `0x180015970`
- end: `0x180015a1e`
- name: `??1CSCardSubcontext@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(CSCardSubcontext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015930`

## callees

- `0x180015970`
- `0x18001685c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800159cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800159cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159f1`
- `RPCRT4!RpcBindingFree` at `0x180015a0c`
- `RPCRT4!RpcBindingFree` at `0x180015a0c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800159e9`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800159e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSCardSubcontext::~CSCardSubcontext(CSCardSubcontext *this)
{
  CSCardSubcontext *v1; // rdi
  CHandleObject *v2; // rbx
  char *v3; // rcx
  CHandleObject *v6; // [rsp+38h] [rbp+10h]

  v1 = this;
  *(_QWORD *)this = &CSCardSubcontext::`vftable';
  v2 = (CSCardSubcontext *)((char *)this + 24);
  v6 = (CSCardSubcontext *)((char *)this + 24);
  v3 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *(_QWORD *)v2 = 0;
  }
  try
  {
    if ( *((_QWORD *)v1 + 14) )
      RpcSsDestroyClientContext((void **)v1 + 14);
  }
  catch ( ... )
  {
    v1 = this;
    v2 = v6;
  }
  if ( *((_QWORD *)v1 + 13) )
    RpcBindingFree((RPC_BINDING_HANDLE *)v1 + 13);
  *((_QWORD *)v1 + 6) = &CCriticalSectionObject::`vftable';
  if ( !*((_DWORD *)v1 + 24) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 56));
  if ( (unsigned __int64)(*(_QWORD *)v2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close(v2);
}

```

## disassembly

```asm
0x180015970  mov     [rsp+arg_10], rbx
0x180015975  mov     [rsp+arg_0], rcx
0x18001597a  push    rdi
0x18001597b  sub     rsp, 20h
0x18001597f  mov     rdi, rcx
0x180015982  lea     rax, ??_7CSCardSubcontext@@6B@; const CSCardSubcontext::`vftable'
0x180015989  mov     [rcx], rax
0x18001598c  lea     rbx, [rcx+18h]
0x180015990  mov     [rsp+28h+arg_8], rbx
0x180015995  mov     rcx, [rbx]; hObject
0x180015998  lea     rax, [rcx-1]
0x18001599c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800159a0  jbe     short loc_1800159F1
0x1800159a2  lea     rcx, [rdi+70h]; ContextHandle
0x1800159a6  cmp     qword ptr [rcx], 0
0x1800159aa  jnz     short loc_1800159E9
0x1800159ac  lea     rcx, [rdi+68h]; Binding
0x1800159b0  cmp     qword ptr [rcx], 0
0x1800159b4  jnz     short loc_180015A0C
0x1800159b6  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x1800159bd  mov     [rdi+30h], rax
0x1800159c1  cmp     dword ptr [rdi+60h], 0
0x1800159c5  jnz     short loc_1800159D2
0x1800159c7  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800159cb  call    cs:__imp_DeleteCriticalSection
0x1800159d1  nop
0x1800159d2  mov     rax, [rbx]
0x1800159d5  dec     rax
0x1800159d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800159dc  jbe     short loc_180015A14
0x1800159de  mov     rbx, [rsp+28h+arg_10]
0x1800159e3  add     rsp, 20h
0x1800159e7  pop     rdi
0x1800159e8  retn
0x1800159e9  call    cs:__imp_RpcSsDestroyClientContext
0x1800159ef  jmp     short loc_1800159AC
0x1800159f1  call    cs:__imp_CloseHandle
0x1800159f7  mov     qword ptr [rbx], 0
0x1800159fe  jmp     short loc_1800159A2
0x180015a00  mov     rdi, [rsp+28h+arg_0]
0x180015a05  mov     rbx, [rsp+28h+arg_8]
0x180015a0a  jmp     short loc_1800159AC
0x180015a0c  call    cs:__imp_RpcBindingFree
0x180015a12  jmp     short loc_1800159B6
0x180015a14  mov     rcx, rbx; this
0x180015a17  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x180015a1c  jmp     short loc_1800159DE
```
