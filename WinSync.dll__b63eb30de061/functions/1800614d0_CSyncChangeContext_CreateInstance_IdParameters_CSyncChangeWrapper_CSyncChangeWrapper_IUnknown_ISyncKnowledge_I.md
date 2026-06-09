# CSyncChangeContext_CreateInstance(IdParameters *,CSyncChangeWrapper *,CSyncChangeWrapper *,IUnknown *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,IForgottenKnowledge *,int,int,ulong,ISyncKnowledge * *,ISyncKnowledge * *,IEnumItemIds *,int,int,int,CSyncChangeContext * *)

- ea: `0x1800614d0`
- end: `0x18006169c`
- name: `?CSyncChangeContext_CreateInstance@@YAJPEAVIdParameters@@PEAVCSyncChangeWrapper@@1PEAUIUnknown@@PEAUISyncKnowledge@@3PEAUIForgottenKnowledge@@4HHKPEAPEAU4@5PEAUIEnumItemIds@@HHHPEAPEAVCSyncChangeContext@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct IdParameters *, struct CSyncChangeWrapper *, struct CSyncChangeWrapper *, struct IUnknown *, struct ISyncKnowledge *, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct IForgottenKnowledge *, int, int, unsigned int, struct ISyncKnowledge **, struct ISyncKnowledge **, struct IEnumItemIds *, int, int, int, struct CSyncChangeContext **)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180034f40`
- `0x180041720`
- `0x180041f28`
- `0x18005faac`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180061378`
- `0x1800614d0`
- `0x18006206c`
- `0x180094010`

## string_xrefs

- `0x18006150e`: `CSyncChangeContext_CreateInstance`
- `0x18006166f`: `CSyncChangeContext_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeContext_CreateInstance(
        struct IdParameters *a1,
        struct CSyncChangeWrapper *a2,
        struct CSyncChangeWrapper *a3,
        struct IUnknown *a4,
        struct ISyncKnowledge *a5,
        struct ISyncKnowledge *a6,
        struct IForgottenKnowledge *a7,
        struct IForgottenKnowledge *a8,
        int a9,
        int a10,
        unsigned int a11,
        struct ISyncKnowledge **a12,
        struct ISyncKnowledge **a13,
        struct IEnumItemIds *a14,
        int a15,
        int a16,
        int a17,
        struct CSyncChangeContext **a18)
{
  PVOID *v22; // rcx
  int v23; // edi
  CSyncChangeContext *v24; // rcx
  CSyncChangeContext *v25; // rax
  struct CSyncChangeContext *v26; // rbx

  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      "CSyncChangeContext_CreateInstance");
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = -2147467261;
  if ( a1 && a18 )
  {
    *a18 = 0;
    v23 = -2147024882;
    v24 = (CSyncChangeContext *)SeAlloc(0xC0u);
    if ( v24 )
    {
      v25 = CSyncChangeContext::CSyncChangeContext(v24, a1, a15, a16, a9, a10, a17);
      v26 = v25;
      if ( v25 )
      {
        v23 = CSyncChangeContext::Init(v25, a2, a3, a4, a5, a6, a7, a8, a11, a12, a13, a14);
        if ( v23 >= 0 )
        {
          v23 = 0;
          (*(void (__fastcall **)(struct CSyncChangeContext *))(*(_QWORD *)v26 + 8LL))(v26);
          *a18 = v26;
        }
        (*(void (__fastcall **)(struct CSyncChangeContext *))(*(_QWORD *)v26 + 16LL))(v26);
      }
    }
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 8) != 0 && *((_BYTE *)v22 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v22[2],
      57,
      (unsigned int)WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      (unsigned int)"CSyncChangeContext_CreateInstance",
      v23);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800614d0  push    rbx
0x1800614d2  push    rbp
0x1800614d3  push    rsi
0x1800614d4  push    rdi
0x1800614d5  push    r12
0x1800614d7  push    r14
0x1800614d9  push    r15
0x1800614db  sub     rsp, 60h
0x1800614df  mov     rbp, r9
0x1800614e2  mov     r14, r8
0x1800614e5  mov     r15, rdx
0x1800614e8  mov     rbx, rcx
0x1800614eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614f2  lea     r12, WPP_GLOBAL_Control
0x1800614f9  cmp     rcx, r12
0x1800614fc  jz      short loc_18006152D
0x1800614fe  test    byte ptr [rcx+1Ch], 8
0x180061502  jz      short loc_18006152D
0x180061504  cmp     byte ptr [rcx+19h], 5
0x180061508  jb      short loc_18006152D
0x18006150a  mov     rcx, [rcx+10h]
0x18006150e  lea     r9, aCsyncchangecon_15; "CSyncChangeContext_CreateInstance"
0x180061515  mov     edx, 38h ; '8'
0x18006151a  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x180061521  call    WPP_SF_s
0x180061526  mov     rcx, cs:WPP_GLOBAL_Control
0x18006152d  mov     edi, 80004003h
0x180061532  test    rbx, rbx
0x180061535  jz      loc_18006165A
0x18006153b  mov     rsi, [rsp+98h+arg_88]
0x180061543  test    rsi, rsi
0x180061546  jz      loc_18006165A
0x18006154c  mov     ecx, 0C0h; unsigned __int64
0x180061551  mov     qword ptr [rsi], 0
0x180061558  mov     edi, 8007000Eh
0x18006155d  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180061562  mov     rcx, rax; this
0x180061565  test    rax, rax
0x180061568  jz      loc_180061653
0x18006156e  mov     eax, [rsp+98h+arg_80]
0x180061575  mov     rdx, rbx; struct IdParameters *
0x180061578  mov     r9d, [rsp+98h+arg_78]; int
0x180061580  mov     r8d, [rsp+98h+arg_70]; int
0x180061588  mov     dword ptr [rsp+98h+var_68], eax; int
0x18006158c  mov     eax, [rsp+98h+arg_48]
0x180061593  mov     dword ptr [rsp+98h+var_70], eax; int
0x180061597  mov     eax, [rsp+98h+arg_40]
0x18006159e  mov     dword ptr [rsp+98h+var_78], eax; int
0x1800615a2  call    ??0CSyncChangeContext@@QEAA@PEAVIdParameters@@HHHHH@Z; CSyncChangeContext::CSyncChangeContext(IdParameters *,int,int,int,int,int)
0x1800615a7  mov     rbx, rax
0x1800615aa  test    rax, rax
0x1800615ad  jz      loc_180061653
0x1800615b3  mov     rax, [rsp+98h+arg_68]
0x1800615bb  mov     r9, rbp; struct IUnknown *
0x1800615be  mov     [rsp+98h+var_40], rax; struct IEnumItemIds *
0x1800615c3  mov     r8, r14; struct CSyncChangeWrapper *
0x1800615c6  mov     rax, [rsp+98h+arg_60]
0x1800615ce  mov     rdx, r15; struct CSyncChangeWrapper *
0x1800615d1  mov     [rsp+98h+var_48], rax; struct ISyncKnowledge **
0x1800615d6  mov     rcx, rbx; this
0x1800615d9  mov     rax, [rsp+98h+arg_58]
0x1800615e1  mov     [rsp+98h+var_50], rax; struct ISyncKnowledge **
0x1800615e6  mov     eax, [rsp+98h+arg_50]
0x1800615ed  mov     [rsp+98h+var_58], eax; unsigned int
0x1800615f1  mov     rax, [rsp+98h+arg_38]
0x1800615f9  mov     [rsp+98h+var_60], rax; struct IForgottenKnowledge *
0x1800615fe  mov     rax, [rsp+98h+arg_30]
0x180061606  mov     [rsp+98h+var_68], rax; struct IForgottenKnowledge *
0x18006160b  mov     rax, [rsp+98h+arg_28]
0x180061613  mov     [rsp+98h+var_70], rax; struct ISyncKnowledge *
0x180061618  mov     rax, [rsp+98h+arg_20]
0x180061620  mov     [rsp+98h+var_78], rax; struct ISyncKnowledge *
0x180061625  call    ?Init@CSyncChangeContext@@QEAAJPEAVCSyncChangeWrapper@@0PEAUIUnknown@@PEAUISyncKnowledge@@2PEAUIForgottenKnowledge@@3KPEAPEAU4@4PEAUIEnumItemIds@@@Z; CSyncChangeContext::Init(CSyncChangeWrapper *,CSyncChangeWrapper *,IUnknown *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,IForgottenKnowledge *,ulong,ISyncKnowledge * *,ISyncKnowledge * *,IEnumItemIds *)
0x18006162a  mov     edi, eax
0x18006162c  test    eax, eax
0x18006162e  js      short loc_180061644
0x180061630  mov     rax, [rbx]
0x180061633  xor     edi, edi
0x180061635  mov     rcx, rbx
0x180061638  mov     rax, [rax+8]
0x18006163c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061641  mov     [rsi], rbx
0x180061644  mov     rax, [rbx]
0x180061647  mov     rcx, rbx
0x18006164a  mov     rax, [rax+10h]
0x18006164e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061653  mov     rcx, cs:WPP_GLOBAL_Control
0x18006165a  cmp     rcx, r12
0x18006165d  jz      short loc_18006168B
0x18006165f  test    byte ptr [rcx+1Ch], 8
0x180061663  jz      short loc_18006168B
0x180061665  cmp     byte ptr [rcx+19h], 5
0x180061669  jb      short loc_18006168B
0x18006166b  mov     rcx, [rcx+10h]
0x18006166f  lea     r9, aCsyncchangecon_15; "CSyncChangeContext_CreateInstance"
0x180061676  mov     edx, 39h ; '9'
0x18006167b  mov     dword ptr [rsp+98h+var_78], edi
0x18006167f  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x180061686  call    WPP_SF_sD
0x18006168b  mov     eax, edi
0x18006168d  add     rsp, 60h
0x180061691  pop     r15
0x180061693  pop     r14
0x180061695  pop     r12
0x180061697  pop     rdi
0x180061698  pop     rsi
0x180061699  pop     rbp
0x18006169a  pop     rbx
0x18006169b  retn
```
