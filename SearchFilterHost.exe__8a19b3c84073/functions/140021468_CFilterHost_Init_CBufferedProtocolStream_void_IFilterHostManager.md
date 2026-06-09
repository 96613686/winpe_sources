# CFilterHost::Init(CBufferedProtocolStream *,void *,IFilterHostManager *)

- ea: `0x140021468`
- end: `0x140021561`
- name: `?Init@CFilterHost@@QEAAJPEAVCBufferedProtocolStream@@PEAXPEAUIFilterHostManager@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(CFilterHost *__hidden this, struct CBufferedProtocolStream *, void *, struct IFilterHostManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x140009f14`
- `0x140018260`
- `0x14001c26c`
- `0x140021468`
- `0x140021a14`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400214b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400214b6`

## pseudocode

```c
__int64 __fastcall CFilterHost::Init(
        CFilterHost *this,
        struct CBufferedProtocolStream *a2,
        void *a3,
        struct IFilterHostManager *a4)
{
  HRESULT Instance; // ebx
  __int64 v7; // rdx
  struct IFilterHostManager **v9; // rsi
  struct IFilterHostManager *v10; // rbx
  __int64 (__fastcall *v11)(struct IFilterHostManager *, char *); // rsi
  int ppv; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *((_QWORD *)this + 13) = a3;
  TComPointer<CBufferedProtocolStream>::operator=((CBufferedProtocolStream **)this + 12, (volatile signed __int32 *)a2);
  Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease((char *)this + 88);
  Instance = CoCreateInstance(
               &GUID_9e175b8d_f52a_11d8_b9a5_505054503030,
               0,
               1u,
               &GUID_40bdbd34_780b_48d3_9bb6_12ebd4ad2e75,
               (LPVOID *)this + 11);
  if ( Instance < 0 )
  {
    v7 = 1002;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchfilterhost\\fltrhost.cxx",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  *((_DWORD *)this + 20) = 1;
  v9 = (struct IFilterHostManager **)((char *)this + 216);
  v10 = (struct IFilterHostManager *)*((_QWORD *)this + 27);
  if ( v10 != a4 )
  {
    if ( v10 )
      winrt::com_ptr<ITextFilter>::unconditional_release_ref((char *)this + 216);
    *v9 = a4;
    if ( a4 )
    {
      (*(void (__fastcall **)(struct IFilterHostManager *))(*(_QWORD *)a4 + 8LL))(a4);
      v10 = *v9;
    }
    else
    {
      v10 = 0;
    }
  }
  v11 = *(__int64 (__fastcall **)(struct IFilterHostManager *, char *))(*(_QWORD *)v10 + 32LL);
  if ( *((_QWORD *)this + 28) )
    winrt::com_ptr<ITextFilter>::unconditional_release_ref((char *)this + 224);
  Instance = v11(v10, (char *)this + 224);
  if ( Instance < 0 )
  {
    v7 = 1008;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x140021468  push    rbx
0x14002146a  push    rbp
0x14002146b  push    rsi
0x14002146c  push    rdi
0x14002146d  sub     rsp, 48h
0x140021471  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x14002147a  mov     rdi, r9
0x14002147d  mov     rbp, rcx
0x140021480  mov     [rcx+68h], r8
0x140021484  add     rcx, 60h ; '`'
0x140021488  call    ??4?$TComPointer@VCBufferedProtocolStream@@@@QEAAPEAVCBufferedProtocolStream@@PEAV1@@Z; TComPointer<CBufferedProtocolStream>::operator=(CBufferedProtocolStream *)
0x14002148d  lea     rbx, [rbp+58h]
0x140021491  mov     rcx, rbx
0x140021494  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x140021499  mov     qword ptr [rsp+68h+ppv], rbx; int
0x14002149e  lea     r9, _GUID_40bdbd34_780b_48d3_9bb6_12ebd4ad2e75; riid
0x1400214a5  mov     esi, 1
0x1400214aa  mov     r8d, esi; dwClsContext
0x1400214ad  xor     edx, edx; pUnkOuter
0x1400214af  lea     rcx, _GUID_9e175b8d_f52a_11d8_b9a5_505054503030; rclsid
0x1400214b6  call    cs:__imp_CoCreateInstance
0x1400214bc  mov     ebx, eax
0x1400214be  test    eax, eax
0x1400214c0  jns     short loc_1400214DF
0x1400214c2  mov     edx, 3EAh; void *
0x1400214c7  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400214ce  mov     r9d, ebx; char *
0x1400214d1  mov     rcx, [rsp+68h]; this
0x1400214d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400214db  mov     eax, ebx
0x1400214dd  jmp     short loc_140021558
0x1400214df  mov     [rbp+50h], esi
0x1400214e2  lea     rsi, [rbp+0D8h]
0x1400214e9  mov     rbx, [rsi]
0x1400214ec  cmp     rbx, rdi
0x1400214ef  jz      short loc_14002151C
0x1400214f1  test    rbx, rbx
0x1400214f4  jz      short loc_1400214FE
0x1400214f6  mov     rcx, rsi
0x1400214f9  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x1400214fe  mov     [rsi], rdi
0x140021501  test    rdi, rdi
0x140021504  jz      short loc_14002151A
0x140021506  mov     rax, [rdi]
0x140021509  mov     rcx, rdi
0x14002150c  mov     rax, [rax+8]
0x140021510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021515  mov     rbx, [rsi]
0x140021518  jmp     short loc_14002151C
0x14002151a  xor     ebx, ebx
0x14002151c  mov     rax, [rbx]
0x14002151f  mov     rsi, [rax+20h]
0x140021523  lea     rdi, [rbp+0E0h]
0x14002152a  cmp     qword ptr [rdi], 0
0x14002152e  jz      short loc_140021538
0x140021530  mov     rcx, rdi
0x140021533  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x140021538  mov     rdx, rdi
0x14002153b  mov     rcx, rbx
0x14002153e  mov     rax, rsi
0x140021541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021546  mov     ebx, eax
0x140021548  test    eax, eax
0x14002154a  jns     short loc_140021556
0x14002154c  mov     edx, 3F0h
0x140021551  jmp     loc_1400214C7
0x140021556  xor     eax, eax
0x140021558  add     rsp, 48h
0x14002155c  pop     rdi
0x14002155d  pop     rsi
0x14002155e  pop     rbp
0x14002155f  pop     rbx
0x140021560  retn
```
