# CDriverVerifierController::Create(DeviceConfiguration *,_GUID const &,void * *)

- ea: `0x1800b38ac`
- end: `0x1800b395e`
- name: `?Create@CDriverVerifierController@@SAXPEAVDeviceConfiguration@@AEBU_GUID@@PEAPEAX@Z`
- size: `178`
- prototype: `static void(struct DeviceConfiguration *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800728bc`

## callees

- `0x18000b010`
- `0x18000b920`
- `0x180012220`
- `0x180017d60`
- `0x1800b38ac`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b38e7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b38e7`

## string_xrefs

- `0x1800b38e0`: `D3DDriverVerifier.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDriverVerifierController::Create(struct DeviceConfiguration *a1, const struct _GUID *a2, void **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  HMODULE LibraryW; // rax
  int Interface; // eax
  _QWORD *v10; // [rsp+60h] [rbp+18h] BYREF

  v6 = operator new(0x20u);
  v7 = v6;
  v10 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 0;
    v6[2] = a1;
    LibraryW = LoadLibraryW(L"D3DDriverVerifier.dll");
    v7[3] = LibraryW;
    if ( !LibraryW )
      ThrowFailure(-2005270483);
    *v7 = &MinComObject<CDriverVerifierController>::`vftable';
  }
  else
  {
    v7 = 0;
  }
  v10 = v7;
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
  if ( a3 )
  {
    Interface = ATL::AtlInternalQueryInterface(
                  v7,
                  (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDriverVerifierController::_GetEntries'::`2'::_entries,
                  a2,
                  a3);
    ThrowFailure(Interface);
  }
  ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v10);
}

```

## disassembly

```asm
0x1800b38ac  push    rbx
0x1800b38ae  push    rbp
0x1800b38af  push    rsi
0x1800b38b0  push    rdi
0x1800b38b1  sub     rsp, 28h
0x1800b38b5  mov     rdi, r8
0x1800b38b8  mov     rbp, rdx
0x1800b38bb  mov     rsi, rcx
0x1800b38be  mov     ecx, 20h ; ' '; dwBytes
0x1800b38c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b38c8  mov     rbx, rax
0x1800b38cb  mov     [rsp+48h+arg_10], rax
0x1800b38d0  test    rax, rax
0x1800b38d3  jz      short loc_1800B390D
0x1800b38d5  mov     dword ptr [rax+8], 0
0x1800b38dc  mov     [rax+10h], rsi
0x1800b38e0  lea     rcx, aD3ddriververif_0; "D3DDriverVerifier.dll"
0x1800b38e7  call    cs:__imp_LoadLibraryW
0x1800b38ed  mov     [rbx+18h], rax
0x1800b38f1  test    rax, rax
0x1800b38f4  jnz     short loc_1800B3901
0x1800b38f6  mov     ecx, 887A002Dh; int
0x1800b38fb  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b3900  nop
0x1800b3901  lea     rax, ??_7?$MinComObject@VCDriverVerifierController@@@@6B@; const MinComObject<CDriverVerifierController>::`vftable'
0x1800b3908  mov     [rbx], rax
0x1800b390b  jmp     short loc_1800B390F
0x1800b390d  xor     ebx, ebx
0x1800b390f  mov     [rsp+48h+arg_10], rbx
0x1800b3914  test    rbx, rbx
0x1800b3917  jz      short loc_1800B3929
0x1800b3919  mov     rax, [rbx]
0x1800b391c  mov     rcx, rbx
0x1800b391f  mov     rax, [rax+8]
0x1800b3923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3928  nop
0x1800b3929  test    rdi, rdi
0x1800b392c  jz      short loc_1800B394B
0x1800b392e  mov     r9, rdi; void **
0x1800b3931  mov     r8, rbp; struct _GUID *
0x1800b3934  lea     rdx, ?_entries@?1??_GetEntries@CDriverVerifierController@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800b393b  mov     rcx, rbx; void *
0x1800b393e  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800b3943  mov     ecx, eax; int
0x1800b3945  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b394a  nop
0x1800b394b  lea     rcx, [rsp+48h+arg_10]
0x1800b3950  call    ??1?$CComPtrBase@VCApplicationIdentity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(void)
0x1800b3955  add     rsp, 28h
0x1800b3959  pop     rdi
0x1800b395a  pop     rsi
0x1800b395b  pop     rbp
0x1800b395c  pop     rbx
0x1800b395d  retn
```
