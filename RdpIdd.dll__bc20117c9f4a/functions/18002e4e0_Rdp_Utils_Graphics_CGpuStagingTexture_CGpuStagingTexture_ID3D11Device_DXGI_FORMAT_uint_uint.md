# Rdp::Utils::Graphics::CGpuStagingTexture::CGpuStagingTexture(ID3D11Device *,DXGI_FORMAT,uint,uint)

- ea: `0x18002e4e0`
- end: `0x18002e60d`
- name: `??0CGpuStagingTexture@Graphics@Utils@Rdp@@QEAA@PEAUID3D11Device@@W4DXGI_FORMAT@@II@Z`
- size: `301`
- prototype: `__int64 __fastcall(Rdp::Utils::Graphics::CGpuStagingTexture *__hidden this, struct ID3D11Device *, enum DXGI_FORMAT, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d998`

## callees

- `0x180006f60`
- `0x18000ead8`
- `0x18001ddf4`
- `0x18002e4e0`
- `0x18003f010`

## string_xrefs

- `0x18002e591`: `Failed to create staging texture`
- `0x18002e5a0`: `onecoreuap\termsrv\rdp_bin\win\common/inc/Texture.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Rdp::Utils::Graphics::CGpuStagingTexture *__fastcall Rdp::Utils::Graphics::CGpuStagingTexture::CGpuStagingTexture(
        Rdp::Utils::Graphics::CGpuStagingTexture *this,
        struct ID3D11Device *a2,
        enum DXGI_FORMAT a3,
        int a4,
        unsigned int a5)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  const char *v14; // [rsp+28h] [rbp-58h]
  _QWORD v15[2]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-3Ch]
  int v18; // [rsp+48h] [rbp-38h]
  int v19; // [rsp+4Ch] [rbp-34h]
  enum DXGI_FORMAT v20; // [rsp+50h] [rbp-30h]
  __int64 v21; // [rsp+54h] [rbp-2Ch]
  __int64 v22; // [rsp+5Ch] [rbp-24h]
  __int64 v23; // [rsp+64h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v15[1] = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct ID3D11Device *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  v21 = 1;
  v22 = 3;
  v23 = 0x20000;
  v16 = a4;
  v17 = a5;
  v20 = a3;
  v19 = 1;
  v18 = 1;
  v15[0] = 0;
  v8 = (__int64 *)*((_QWORD *)this + 2);
  v9 = *v8;
  v15[0] = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, int *, _QWORD, _QWORD *))(v9 + 40))(v8, &v16, 0, v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF1,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/Texture.h",
    (const char *)v10,
    (int)"Failed to create staging texture",
    v14);
  *((_DWORD *)this + 8) = v20;
  *((_DWORD *)this + 9) = v16;
  *((_DWORD *)this + 10) = v17;
  v11 = v15[0];
  v15[0] = 0;
  v12 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v11;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(v15);
  return this;
}

```

## disassembly

```asm
0x18002e4e0  push    rbp
0x18002e4e2  push    rbx
0x18002e4e3  push    rsi
0x18002e4e4  push    rdi
0x18002e4e5  push    r14
0x18002e4e7  mov     rbp, rsp
0x18002e4ea  sub     rsp, 80h
0x18002e4f1  mov     rax, cs:__security_cookie
0x18002e4f8  xor     rax, rsp
0x18002e4fb  mov     [rbp+var_10], rax
0x18002e4ff  mov     esi, r9d
0x18002e502  mov     edi, r8d
0x18002e505  mov     rbx, rcx
0x18002e508  mov     [rbp+var_48], rcx
0x18002e50c  xor     r14d, r14d
0x18002e50f  mov     [rcx], r14
0x18002e512  mov     [rcx+8], r14
0x18002e516  mov     [rcx+10h], rdx
0x18002e51a  test    rdx, rdx
0x18002e51d  jz      short loc_18002E52F
0x18002e51f  mov     rax, [rdx]
0x18002e522  mov     rcx, rdx
0x18002e525  mov     rax, [rax+8]
0x18002e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e52e  nop
0x18002e52f  mov     [rbx+18h], r14
0x18002e533  mov     [rbx+20h], r14
0x18002e537  mov     [rbx+28h], r14d
0x18002e53b  mov     [rbp+var_2C], 1
0x18002e543  mov     [rbp+var_24], 3
0x18002e54b  mov     [rbp+var_1C], 20000h
0x18002e553  mov     [rbp+var_40], esi
0x18002e556  mov     eax, [rbp+arg_20]
0x18002e559  mov     [rbp+var_3C], eax
0x18002e55c  mov     [rbp+var_30], edi
0x18002e55f  mov     eax, 1
0x18002e564  mov     [rbp+var_34], eax
0x18002e567  mov     [rbp+var_38], eax
0x18002e56a  mov     [rbp+var_50], r14
0x18002e56e  mov     rcx, [rbx+10h]
0x18002e572  mov     rax, [rcx]
0x18002e575  mov     [rbp+var_50], r14
0x18002e579  lea     r9, [rbp+var_50]
0x18002e57d  xor     r8d, r8d
0x18002e580  lea     rdx, [rbp+var_40]
0x18002e584  mov     rax, [rax+28h]
0x18002e588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e58d  mov     rcx, [rbp+28h]; this
0x18002e591  lea     rdx, aFailedToCreate_9; "Failed to create staging texture"
0x18002e598  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18002e59d  mov     r9d, eax; char *
0x18002e5a0  lea     r8, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002e5a7  mov     edx, 0F1h; void *
0x18002e5ac  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e5b1  mov     eax, [rbp+var_30]
0x18002e5b4  mov     [rbx+20h], eax
0x18002e5b7  mov     eax, [rbp+var_40]
0x18002e5ba  mov     [rbx+24h], eax
0x18002e5bd  mov     eax, [rbp+var_3C]
0x18002e5c0  mov     [rbx+28h], eax
0x18002e5c3  mov     rax, [rbp+var_50]
0x18002e5c7  mov     [rbp+var_50], r14
0x18002e5cb  mov     rcx, [rbx+18h]
0x18002e5cf  mov     [rbx+18h], rax
0x18002e5d3  test    rcx, rcx
0x18002e5d6  jz      short loc_18002E5E5
0x18002e5d8  mov     rdx, [rcx]
0x18002e5db  mov     rax, [rdx+10h]
0x18002e5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5e4  nop
0x18002e5e5  lea     rcx, [rbp+var_50]
0x18002e5e9  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002e5ee  nop
0x18002e5ef  mov     rax, rbx
0x18002e5f2  mov     rcx, [rbp+var_10]
0x18002e5f6  xor     rcx, rsp; StackCookie
0x18002e5f9  call    __security_check_cookie
0x18002e5fe  add     rsp, 80h
0x18002e605  pop     r14
0x18002e607  pop     rdi
0x18002e608  pop     rsi
0x18002e609  pop     rbx
0x18002e60a  pop     rbp
0x18002e60b  retn
```
