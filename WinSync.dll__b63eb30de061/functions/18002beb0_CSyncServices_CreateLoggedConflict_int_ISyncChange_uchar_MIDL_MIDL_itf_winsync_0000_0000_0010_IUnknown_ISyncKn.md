# CSyncServices::CreateLoggedConflict(int,ISyncChange *,uchar *,__MIDL___MIDL_itf_winsync_0000_0000_0010,IUnknown *,ISyncKnowledge *,ISyncKnowledge *,int,ILoggedConflict * *)

- ea: `0x18002beb0`
- end: `0x18002c03c`
- name: `?CreateLoggedConflict@CSyncServices@@UEAAJHPEAUISyncChange@@PEAEW4__MIDL___MIDL_itf_winsync_0000_0000_0010@@PEAUIUnknown@@PEAUISyncKnowledge@@4HPEAPEAUILoggedConflict@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct IdParameters **this, int, struct ISyncChange *, unsigned __int8 *, enum __MIDL___MIDL_itf_winsync_0000_0000_0010, struct IUnknown *, struct ISyncKnowledge *, struct ISyncKnowledge *, int, struct ILoggedConflict **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002beb0`
- `0x18005cb98`
- `0x18005dd70`
- `0x180094010`

## string_xrefs

- `0x18002beef`: `CSyncServices::CreateLoggedConflict`
- `0x18002c00e`: `CSyncServices::CreateLoggedConflict`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateLoggedConflict(
        struct IdParameters **this,
        int a2,
        struct ISyncChange *a3,
        unsigned __int8 *a4,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0010 a5,
        struct IUnknown *a6,
        struct ISyncKnowledge *a7,
        struct ISyncKnowledge *a8,
        int a9,
        struct ILoggedConflict **a10)
{
  PVOID *v14; // rcx
  int v15; // ebx
  CInMemoryLoggedConflict *v16; // rax
  CInMemoryLoggedConflict *v17; // rax
  CInMemoryLoggedConflict *v18; // rdi

  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateLoggedConflict");
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = -2147217407;
  if ( this[5] )
  {
    v15 = -2147467261;
    if ( a3 )
    {
      if ( a7 && a10 )
      {
        v15 = -2147024882;
        v16 = (CInMemoryLoggedConflict *)SeAlloc(0x58u);
        if ( v16 )
        {
          v17 = CInMemoryLoggedConflict::CInMemoryLoggedConflict(v16, this[5]);
          v18 = v17;
          if ( v17 )
          {
            v15 = CInMemoryLoggedConflict::Init(v17, a2, a3, a4, a5, a6, a7, a8, a9);
            if ( v15 >= 0 )
              v15 = (**(__int64 (__fastcall ***)(CInMemoryLoggedConflict *, GUID *, struct ILoggedConflict **))v18)(
                      v18,
                      &GUID_8a2cbb44_bc42_43d1_af80_5d12db014ca2,
                      a10);
            (*(void (__fastcall **)(CInMemoryLoggedConflict *))(*(_QWORD *)v18 + 16LL))(v18);
          }
        }
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v14[2],
      57,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateLoggedConflict",
      v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002beb0  push    rbx
0x18002beb2  push    rbp
0x18002beb3  push    rdi
0x18002beb4  push    r12
0x18002beb6  push    r13
0x18002beb8  push    r14
0x18002beba  push    r15
0x18002bebc  sub     rsp, 50h
0x18002bec0  mov     r15, r9
0x18002bec3  mov     r14, r8
0x18002bec6  mov     r12d, edx
0x18002bec9  mov     rdi, rcx
0x18002becc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bed3  lea     r13, WPP_GLOBAL_Control
0x18002beda  cmp     rcx, r13
0x18002bedd  jz      short loc_18002BF0E
0x18002bedf  test    byte ptr [rcx+1Ch], 2
0x18002bee3  jz      short loc_18002BF0E
0x18002bee5  cmp     byte ptr [rcx+19h], 5
0x18002bee9  jb      short loc_18002BF0E
0x18002beeb  mov     rcx, [rcx+10h]
0x18002beef  lea     r9, aCsyncservicesC_17; "CSyncServices::CreateLoggedConflict"
0x18002bef6  mov     edx, 38h ; '8'
0x18002befb  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bf02  call    WPP_SF_s
0x18002bf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf0e  cmp     qword ptr [rdi+28h], 0
0x18002bf13  mov     ebx, 80041001h
0x18002bf18  jz      loc_18002BFF9
0x18002bf1e  mov     ebx, 80004003h
0x18002bf23  test    r14, r14
0x18002bf26  jz      loc_18002BFF9
0x18002bf2c  mov     rbp, [rsp+88h+arg_30]
0x18002bf34  test    rbp, rbp
0x18002bf37  jz      loc_18002BFF9
0x18002bf3d  cmp     [rsp+88h+arg_48], 0
0x18002bf46  jz      loc_18002BFF9
0x18002bf4c  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002bf51  mov     ebx, 8007000Eh
0x18002bf56  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002bf5b  test    rax, rax
0x18002bf5e  jz      loc_18002BFF2
0x18002bf64  mov     rdx, [rdi+28h]; struct IdParameters *
0x18002bf68  mov     rcx, rax; this
0x18002bf6b  call    ??0CInMemoryLoggedConflict@@QEAA@PEAVIdParameters@@@Z; CInMemoryLoggedConflict::CInMemoryLoggedConflict(IdParameters *)
0x18002bf70  mov     rdi, rax
0x18002bf73  test    rax, rax
0x18002bf76  jz      short loc_18002BFF2
0x18002bf78  mov     eax, [rsp+88h+arg_40]
0x18002bf7f  mov     r9, r15; unsigned __int8 *
0x18002bf82  mov     [rsp+88h+var_48], eax; int
0x18002bf86  mov     r8, r14; struct ISyncChange *
0x18002bf89  mov     rax, [rsp+88h+arg_38]
0x18002bf91  mov     edx, r12d; int
0x18002bf94  mov     [rsp+88h+var_50], rax; struct ISyncKnowledge *
0x18002bf99  mov     rcx, rdi; this
0x18002bf9c  mov     rax, [rsp+88h+arg_28]
0x18002bfa4  mov     [rsp+88h+var_58], rbp; struct ISyncKnowledge *
0x18002bfa9  mov     [rsp+88h+var_60], rax; struct IUnknown *
0x18002bfae  mov     eax, [rsp+88h+arg_20]
0x18002bfb5  mov     [rsp+88h+var_68], eax; enum __MIDL___MIDL_itf_winsync_0000_0000_0010
0x18002bfb9  call    ?Init@CInMemoryLoggedConflict@@QEAAJHPEAUISyncChange@@PEAEW4__MIDL___MIDL_itf_winsync_0000_0000_0010@@PEAUIUnknown@@PEAUISyncKnowledge@@4H@Z; CInMemoryLoggedConflict::Init(int,ISyncChange *,uchar *,__MIDL___MIDL_itf_winsync_0000_0000_0010,IUnknown *,ISyncKnowledge *,ISyncKnowledge *,int)
0x18002bfbe  mov     ebx, eax
0x18002bfc0  test    eax, eax
0x18002bfc2  js      short loc_18002BFE3
0x18002bfc4  mov     rax, [rdi]
0x18002bfc7  lea     rdx, _GUID_8a2cbb44_bc42_43d1_af80_5d12db014ca2
0x18002bfce  mov     r8, [rsp+88h+arg_48]
0x18002bfd6  mov     rcx, rdi
0x18002bfd9  mov     rax, [rax]
0x18002bfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfe1  mov     ebx, eax
0x18002bfe3  mov     rax, [rdi]
0x18002bfe6  mov     rcx, rdi
0x18002bfe9  mov     rax, [rax+10h]
0x18002bfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bff9  cmp     rcx, r13
0x18002bffc  jz      short loc_18002C02A
0x18002bffe  test    byte ptr [rcx+1Ch], 2
0x18002c002  jz      short loc_18002C02A
0x18002c004  cmp     byte ptr [rcx+19h], 5
0x18002c008  jb      short loc_18002C02A
0x18002c00a  mov     rcx, [rcx+10h]
0x18002c00e  lea     r9, aCsyncservicesC_17; "CSyncServices::CreateLoggedConflict"
0x18002c015  mov     edx, 39h ; '9'
0x18002c01a  mov     [rsp+88h+var_68], ebx
0x18002c01e  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c025  call    WPP_SF_sD
0x18002c02a  mov     eax, ebx
0x18002c02c  add     rsp, 50h
0x18002c030  pop     r15
0x18002c032  pop     r14
0x18002c034  pop     r13
0x18002c036  pop     r12
0x18002c038  pop     rdi
0x18002c039  pop     rbp
0x18002c03a  pop     rbx
0x18002c03b  retn
```
