# CGpuFrameDumper::SetRenderDevice(ID3D11Device *)

- ea: `0x18002f4e0`
- end: `0x18002f682`
- name: `?SetRenderDevice@CGpuFrameDumper@@UEAAJPEAUID3D11Device@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(CGpuFrameDumper *__hidden this, struct ID3D11Device *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ead8`
- `0x18001dd50`
- `0x18001ddf4`
- `0x18002f4e0`
- `0x18003f010`

## string_xrefs

- `0x18002f66f`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x18002f5b1`: `Failed to create D2D1 device`
- `0x18002f610`: `Failed to create D2D1 device context`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGpuFrameDumper::SetRenderDevice(CGpuFrameDumper *this, struct ID3D11Device *a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // eax
  __int64 v7; // r14
  __int64 (__fastcall *v8)(__int64, __int64, char *); // r15
  char *v9; // rsi
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r14
  __int64 (__fastcall *v13)(__int64, _QWORD, char *); // r15
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-28h]
  const char *v20; // [rsp+28h] [rbp-20h]
  const char *v21; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v23; // [rsp+50h] [rbp+8h] BYREF

  try
  {
    v4 = *((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = a2;
    if ( a2 )
      ((void (__fastcall *)(struct ID3D11Device *))a2->lpVtbl->AddRef)(a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v23 = 0;
    v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
    if ( v5 )
    {
      v6 = (**v5)(v5, &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c, &v23);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
          (const char *)(unsigned int)v6,
          v19);
    }
    else
    {
      v23 = 0;
    }
    v7 = *((_QWORD *)this + 12);
    v8 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v7 + 136LL);
    v9 = (char *)this + 104;
    v10 = (_QWORD *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v10 + 16LL))(v10, *v10);
    v11 = v8(v7, v23, (char *)this + 104);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
      (const char *)v11,
      (int)"Failed to create D2D1 device",
      v20);
    v12 = *(_QWORD *)v9;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v9 + 32LL);
    v14 = *((_QWORD *)this + 14);
    *((_QWORD *)this + 14) = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = v13(v12, 0, (char *)this + 112);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
      (const char *)v15,
      (int)"Failed to create D2D1 device context",
      v21);
    v16 = (*(__int64 (__fastcall **)(_QWORD, struct ID3D11Device *))(**((_QWORD **)this + 4) + 48LL))(
            *((_QWORD *)this + 4),
            a2);
    wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v23);
    result = v16;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x116,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18002f4e0  mov     [rsp+arg_8], rbx
0x18002f4e5  mov     [rsp+arg_10], rsi
0x18002f4ea  push    rdi
0x18002f4eb  push    r14
0x18002f4ed  push    r15
0x18002f4ef  sub     rsp, 30h
0x18002f4f3  mov     rdi, rdx
0x18002f4f6  mov     rbx, rcx
0x18002f4f9  mov     rsi, [rcx+78h]
0x18002f4fd  mov     [rcx+78h], rdx
0x18002f501  test    rdx, rdx
0x18002f504  jz      short loc_18002F515
0x18002f506  mov     rax, [rdx]
0x18002f509  mov     rcx, rdx
0x18002f50c  mov     rax, [rax+8]
0x18002f510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f515  test    rsi, rsi
0x18002f518  jz      short loc_18002F52A
0x18002f51a  mov     rax, [rsi]
0x18002f51d  mov     rcx, rsi
0x18002f520  mov     rax, [rax+10h]
0x18002f524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f529  nop
0x18002f52a  mov     [rsp+48h+arg_0], 0
0x18002f533  mov     rcx, [rbx+78h]
0x18002f537  test    rcx, rcx
0x18002f53a  jz      short loc_18002F562
0x18002f53c  mov     rax, [rcx]
0x18002f53f  lea     r8, [rsp+48h+arg_0]
0x18002f544  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18002f54b  mov     rax, [rax]
0x18002f54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f553  mov     rcx, [rsp+48h]; this
0x18002f558  test    eax, eax
0x18002f55a  js      loc_18002F66C
0x18002f560  jmp     short loc_18002F56B
0x18002f562  mov     [rsp+48h+arg_0], 0
0x18002f56b  mov     r14, [rbx+60h]
0x18002f56f  mov     rax, [r14]
0x18002f572  mov     r15, [rax+88h]
0x18002f579  lea     rsi, [rbx+68h]
0x18002f57d  mov     rcx, [rsi]
0x18002f580  mov     qword ptr [rsi], 0
0x18002f587  test    rcx, rcx
0x18002f58a  jz      short loc_18002F599
0x18002f58c  mov     rdx, [rcx]
0x18002f58f  mov     rax, [rdx+10h]
0x18002f593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f598  nop
0x18002f599  mov     r8, rsi
0x18002f59c  mov     rdx, [rsp+48h+arg_0]
0x18002f5a1  mov     rcx, r14
0x18002f5a4  mov     rax, r15
0x18002f5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5ac  mov     rcx, [rsp+48h]; this
0x18002f5b1  lea     rdx, aFailedToCreate_1; "Failed to create D2D1 device"
0x18002f5b8  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18002f5bd  mov     r9d, eax; char *
0x18002f5c0  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002f5c7  mov     edx, 10Ch; void *
0x18002f5cc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002f5d1  mov     r14, [rsi]
0x18002f5d4  mov     rax, [r14]
0x18002f5d7  mov     r15, [rax+20h]
0x18002f5db  lea     rsi, [rbx+70h]
0x18002f5df  mov     rcx, [rsi]
0x18002f5e2  mov     qword ptr [rsi], 0
0x18002f5e9  test    rcx, rcx
0x18002f5ec  jz      short loc_18002F5FB
0x18002f5ee  mov     rdx, [rcx]
0x18002f5f1  mov     rax, [rdx+10h]
0x18002f5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5fa  nop
0x18002f5fb  mov     r8, rsi
0x18002f5fe  xor     edx, edx
0x18002f600  mov     rcx, r14
0x18002f603  mov     rax, r15
0x18002f606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f60b  mov     rcx, [rsp+48h]; this
0x18002f610  lea     rdx, aFailedToCreate_7; "Failed to create D2D1 device context"
0x18002f617  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18002f61c  mov     r9d, eax; char *
0x18002f61f  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002f626  mov     edx, 112h; void *
0x18002f62b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002f630  mov     rcx, [rbx+20h]
0x18002f634  mov     rax, [rcx]
0x18002f637  mov     rdx, rdi
0x18002f63a  mov     rax, [rax+30h]
0x18002f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f643  mov     ebx, eax
0x18002f645  lea     rcx, [rsp+48h+arg_0]
0x18002f64a  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f64f  mov     eax, ebx
0x18002f651  jmp     short loc_18002F657
0x18002f653  mov     eax, dword ptr [rsp+48h+arg_0]
0x18002f657  mov     rbx, [rsp+48h+arg_8]
0x18002f65c  mov     rsi, [rsp+48h+arg_10]
0x18002f661  add     rsp, 30h
0x18002f665  pop     r15
0x18002f667  pop     r14
0x18002f669  pop     rdi
0x18002f66a  retn
0x18002f66c  mov     r9d, eax; char *
0x18002f66f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f676  mov     edx, 1CBEh; void *
0x18002f67b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
