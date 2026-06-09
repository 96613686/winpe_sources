# CRdpIdAdapter::SetVirtualDesktopInfo(tagRECT const &)

- ea: `0x18001d5f0`
- end: `0x18001d7b4`
- name: `?SetVirtualDesktopInfo@CRdpIdAdapter@@AEAAXAEBUtagRECT@@@Z`
- size: `452`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001de94`

## callees

- `0x18000ead8`
- `0x180017888`
- `0x180017914`
- `0x18001d5f0`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x18001d69e`: `Failed to open property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdAdapter::SetVirtualDesktopInfo(CRdpIdAdapter *this, const struct tagRECT *a2)
{
  unsigned int left; // esi
  unsigned int top; // ebp
  unsigned int v5; // ebx
  unsigned int v6; // edi
  int v7; // ecx
  int v8; // eax
  __int64 *v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // eax
  int v12; // r9d
  unsigned int v13; // eax
  int v14; // r9d
  unsigned int v15; // eax
  unsigned int v16; // r9d
  unsigned int v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // eax
  const char *v20; // [rsp+28h] [rbp-20h]
  const char *v21; // [rsp+28h] [rbp-20h]
  const char *v22; // [rsp+28h] [rbp-20h]
  const char *v23; // [rsp+28h] [rbp-20h]
  const char *v24; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Rdp::Utils::Props *v26; // [rsp+50h] [rbp+8h] BYREF

  left = a2->left;
  top = a2->top;
  v5 = a2->right - a2->left;
  v6 = a2->bottom - top;
  v7 = 1;
  while ( _InterlockedExchange((volatile __int32 *)this + 142, 1) )
  {
    while ( *((_DWORD *)this + 142) )
    {
      v8 = v7;
      if ( !v7 )
        goto LABEL_6;
      do
      {
        _mm_pause();
        --v8;
      }
      while ( v8 );
      if ( v7 >= 64 )
        v7 = 64;
      else
LABEL_6:
        v7 *= 2;
    }
  }
  *((_DWORD *)this + 143) = left;
  *((_DWORD *)this + 144) = top;
  *((_DWORD *)this + 145) = v5;
  *((_DWORD *)this + 146) = v6;
  *((_DWORD *)this + 142) = 0;
  v26 = 0;
  v9 = (__int64 *)*((_QWORD *)this + 70);
  v10 = *v9;
  v26 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v10 + 24))(v9, &v26);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x521,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v11,
    (int)"Failed to open property store",
    v20);
  v13 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v26,
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
          (const struct _tagpropertykey *)left,
          v12);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x528,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v13,
    (int)"Failed to set PKEY_VirtualDesktop_Origin_X",
    v21);
  v15 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v26,
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
          (const struct _tagpropertykey *)top,
          v14);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x52F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v15,
    (int)"Failed to set PKEY_VirtualDesktop_Origin_Y",
    v22);
  v17 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v26,
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
          (const struct _tagpropertykey *)v5,
          v16);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x536,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v17,
    (int)"Failed to set PKEY_VirtualDesktop_Width",
    v23);
  v19 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v26,
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
          (const struct _tagpropertykey *)v6,
          v18);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x53D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v19,
    (int)"Failed to set PKEY_VirtualDesktop_Height",
    v24);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>((__int64 *)&v26);
}

```

## disassembly

```asm
0x18001d5f0  mov     [rsp+arg_8], rbx
0x18001d5f5  mov     [rsp+arg_10], rbp
0x18001d5fa  push    rsi
0x18001d5fb  push    rdi
0x18001d5fc  push    r14
0x18001d5fe  sub     rsp, 30h
0x18001d602  mov     r8, rcx
0x18001d605  mov     esi, [rdx]
0x18001d607  mov     ebp, [rdx+4]
0x18001d60a  mov     ebx, [rdx+8]
0x18001d60d  sub     ebx, esi
0x18001d60f  mov     edi, [rdx+0Ch]
0x18001d612  sub     edi, ebp
0x18001d614  mov     r9d, 1
0x18001d61a  mov     ecx, r9d
0x18001d61d  xor     edx, edx
0x18001d61f  jmp     short loc_18001D645
0x18001d621  mov     eax, ecx
0x18001d623  test    ecx, ecx
0x18001d625  jz      short loc_18001D638
0x18001d627  pause
0x18001d629  sub     eax, r9d
0x18001d62c  jnz     short loc_18001D627
0x18001d62e  cmp     ecx, 40h ; '@'
0x18001d631  jl      short loc_18001D638
0x18001d633  lea     ecx, [rax+40h]
0x18001d636  jmp     short loc_18001D63A
0x18001d638  add     ecx, ecx
0x18001d63a  mov     eax, [r8+238h]
0x18001d641  test    eax, eax
0x18001d643  jnz     short loc_18001D621
0x18001d645  mov     eax, r9d
0x18001d648  xchg    eax, [r8+238h]
0x18001d64f  test    eax, eax
0x18001d651  jnz     short loc_18001D63A
0x18001d653  mov     [r8+23Ch], esi
0x18001d65a  mov     [r8+240h], ebp
0x18001d661  mov     [r8+244h], ebx
0x18001d668  mov     [r8+248h], edi
0x18001d66f  nop
0x18001d670  mov     [r8+238h], edx
0x18001d677  mov     [rsp+48h+arg_0], rdx
0x18001d67c  mov     rcx, [r8+230h]
0x18001d683  mov     rax, [rcx]
0x18001d686  mov     [rsp+48h+arg_0], rdx
0x18001d68b  lea     rdx, [rsp+48h+arg_0]
0x18001d690  mov     rax, [rax+18h]
0x18001d694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d699  mov     rcx, [rsp+48h]; this
0x18001d69e  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001d6a5  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18001d6aa  mov     r9d, eax; char *
0x18001d6ad  lea     r14, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001d6b4  mov     r8, r14; unsigned int
0x18001d6b7  mov     edx, 521h; void *
0x18001d6bc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d6c1  mov     r8d, esi; struct _tagpropertykey *
0x18001d6c4  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x18001d6cb  mov     rcx, [rsp+48h+arg_0]; this
0x18001d6d0  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x18001d6d5  mov     rcx, [rsp+48h]; this
0x18001d6da  lea     rdx, aFailedToSetPke_23; "Failed to set PKEY_VirtualDesktop_Origi"...
0x18001d6e1  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18001d6e6  mov     r9d, eax; char *
0x18001d6e9  mov     r8, r14; unsigned int
0x18001d6ec  mov     edx, 528h; void *
0x18001d6f1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d6f6  mov     r8d, ebp; struct _tagpropertykey *
0x18001d6f9  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x18001d700  mov     rcx, [rsp+48h+arg_0]; this
0x18001d705  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x18001d70a  mov     rcx, [rsp+48h]; this
0x18001d70f  lea     rdx, aFailedToSetPke_9; "Failed to set PKEY_VirtualDesktop_Origi"...
0x18001d716  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18001d71b  mov     r9d, eax; char *
0x18001d71e  mov     r8, r14; unsigned int
0x18001d721  mov     edx, 52Fh; void *
0x18001d726  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d72b  mov     r8d, ebx; struct _tagpropertykey *
0x18001d72e  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x18001d735  mov     rcx, [rsp+48h+arg_0]; this
0x18001d73a  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001d73f  mov     rcx, [rsp+48h]; this
0x18001d744  lea     rdx, aFailedToSetPke_32; "Failed to set PKEY_VirtualDesktop_Width"
0x18001d74b  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18001d750  mov     r9d, eax; char *
0x18001d753  mov     r8, r14; unsigned int
0x18001d756  mov     edx, 536h; void *
0x18001d75b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d760  mov     r8d, edi; struct _tagpropertykey *
0x18001d763  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x18001d76a  mov     rcx, [rsp+48h+arg_0]; this
0x18001d76f  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001d774  mov     rcx, [rsp+48h]; this
0x18001d779  lea     rdx, aFailedToSetPke_36; "Failed to set PKEY_VirtualDesktop_Heigh"...
0x18001d780  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18001d785  mov     r9d, eax; char *
0x18001d788  mov     r8, r14; unsigned int
0x18001d78b  mov     edx, 53Dh; void *
0x18001d790  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d795  nop
0x18001d796  lea     rcx, [rsp+48h+arg_0]
0x18001d79b  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001d7a0  mov     rbx, [rsp+48h+arg_8]
0x18001d7a5  mov     rbp, [rsp+48h+arg_10]
0x18001d7aa  add     rsp, 30h
0x18001d7ae  pop     r14
0x18001d7b0  pop     rdi
0x18001d7b1  pop     rsi
0x18001d7b2  retn
```
