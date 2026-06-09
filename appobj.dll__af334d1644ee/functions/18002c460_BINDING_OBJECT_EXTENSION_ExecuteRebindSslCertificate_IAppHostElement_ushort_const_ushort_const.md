# BINDING_OBJECT_EXTENSION::ExecuteRebindSslCertificate(IAppHostElement *,ushort const *,ushort const *)

- ea: `0x18002c460`
- end: `0x18002c539`
- name: `?ExecuteRebindSslCertificate@BINDING_OBJECT_EXTENSION@@AEAAJPEAUIAppHostElement@@PEBG1@Z`
- size: `217`
- prototype: `__int64 __fastcall(BINDING_OBJECT_EXTENSION *this, struct IAppHostElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c0a8`

## callees

- `0x18002c460`
- `0x18002ca34`
- `0x18002cbd8`
- `0x180036010`

## string_xrefs

- `0x18002c4d5`: `certificateStoreName`

## pseudocode

```c
__int64 __fastcall BINDING_OBJECT_EXTENSION::ExecuteRebindSslCertificate(
        BINDING_OBJECT_EXTENSION *this,
        struct IAppHostElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int MethodInstance; // eax
  struct IAppHostMethodInstance *v7; // rdi
  int v8; // ebx
  struct IAppHostMethodInstance *v10; // [rsp+20h] [rbp-38h] BYREF
  struct IAppHostElement *v11; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  v11 = 0;
  MethodInstance = GetMethodInstance(a2, (const unsigned __int16 *)a2, &v10);
  v7 = v10;
  v8 = MethodInstance;
  if ( MethodInstance >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IAppHostMethodInstance *, struct IAppHostElement **))v10->lpVtbl->get_Input)(
           v10,
           &v11);
    if ( v8 >= 0 )
    {
      v8 = SetElementStringProperty(v11, L"certificateHash", a3);
      if ( v8 >= 0 )
      {
        v8 = SetElementStringProperty(v11, L"certificateStoreName", a4);
        if ( v8 >= 0 )
          v8 = ((__int64 (__fastcall *)(struct IAppHostMethodInstance *))v7->lpVtbl->Execute)(v7);
      }
    }
  }
  if ( v11 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v11->lpVtbl->Release)(v11);
    v11 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IAppHostMethodInstance *))v7->lpVtbl->Release)(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c460  mov     rax, rsp
0x18002c463  mov     [rax+8], rcx
0x18002c467  push    rbx
0x18002c468  push    rbp
0x18002c469  push    rsi
0x18002c46a  push    rdi
0x18002c46b  sub     rsp, 38h
0x18002c46f  mov     rsi, r8
0x18002c472  mov     qword ptr [rax-38h], 0
0x18002c47a  lea     r8, [rax-38h]; struct IAppHostMethodInstance **
0x18002c47e  mov     qword ptr [rax+8], 0
0x18002c486  mov     rcx, rdx; struct IAppHostElement *
0x18002c489  mov     rbp, r9
0x18002c48c  call    ?GetMethodInstance@@YAJPEAUIAppHostElement@@PEBGPEAPEAUIAppHostMethodInstance@@@Z; GetMethodInstance(IAppHostElement *,ushort const *,IAppHostMethodInstance * *)
0x18002c491  mov     rdi, [rsp+58h+var_38]
0x18002c496  mov     ebx, eax
0x18002c498  test    eax, eax
0x18002c49a  js      short loc_18002C4FB
0x18002c49c  mov     rax, [rdi]
0x18002c49f  lea     rdx, [rsp+58h+arg_0]
0x18002c4a4  mov     rcx, rdi
0x18002c4a7  mov     rax, [rax+18h]
0x18002c4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4b0  mov     ebx, eax
0x18002c4b2  test    eax, eax
0x18002c4b4  js      short loc_18002C4FB
0x18002c4b6  mov     rcx, [rsp+58h+arg_0]; struct IAppHostElement *
0x18002c4bb  lea     rdx, aCertificatehas; "certificateHash"
0x18002c4c2  mov     r8, rsi; unsigned __int16 *
0x18002c4c5  call    ?SetElementStringProperty@@YAJPEAUIAppHostElement@@PEBG1@Z; SetElementStringProperty(IAppHostElement *,ushort const *,ushort const *)
0x18002c4ca  mov     ebx, eax
0x18002c4cc  test    eax, eax
0x18002c4ce  js      short loc_18002C4FB
0x18002c4d0  mov     rcx, [rsp+58h+arg_0]; struct IAppHostElement *
0x18002c4d5  lea     rdx, aCertificatesto; "certificateStoreName"
0x18002c4dc  mov     r8, rbp; unsigned __int16 *
0x18002c4df  call    ?SetElementStringProperty@@YAJPEAUIAppHostElement@@PEBG1@Z; SetElementStringProperty(IAppHostElement *,ushort const *,ushort const *)
0x18002c4e4  mov     ebx, eax
0x18002c4e6  test    eax, eax
0x18002c4e8  js      short loc_18002C4FB
0x18002c4ea  mov     rax, [rdi]
0x18002c4ed  mov     rcx, rdi
0x18002c4f0  mov     rax, [rax+28h]
0x18002c4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4f9  mov     ebx, eax
0x18002c4fb  mov     rcx, [rsp+58h+arg_0]
0x18002c500  test    rcx, rcx
0x18002c503  jz      short loc_18002C51A
0x18002c505  mov     rax, [rcx]
0x18002c508  mov     rax, [rax+10h]
0x18002c50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c511  mov     [rsp+58h+arg_0], 0
0x18002c51a  test    rdi, rdi
0x18002c51d  jz      short loc_18002C52E
0x18002c51f  mov     rax, [rdi]
0x18002c522  mov     rcx, rdi
0x18002c525  mov     rax, [rax+10h]
0x18002c529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c52e  mov     eax, ebx
0x18002c530  add     rsp, 38h
0x18002c534  pop     rdi
0x18002c535  pop     rsi
0x18002c536  pop     rbp
0x18002c537  pop     rbx
0x18002c538  retn
```
