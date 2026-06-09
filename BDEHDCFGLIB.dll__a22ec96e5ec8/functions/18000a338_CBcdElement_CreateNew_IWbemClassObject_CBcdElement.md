# CBcdElement::CreateNew(IWbemClassObject *,CBcdElement * *)

- ea: `0x18000a338`
- end: `0x18000a4e9`
- name: `?CreateNew@CBcdElement@@KAJPEAUIWbemClassObject@@PEAPEAV1@@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, struct CBcdElement **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b72c`
- `0x18000c144`

## callees

- `0x1800015c4`
- `0x180009b38`
- `0x180009b5c`
- `0x180009c00`
- `0x180009c28`
- `0x18000a338`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a363`
- `OLEAUT32!__imp_VariantInit` at `0x18000a363`
- `OLEAUT32!__imp_VariantClear` at `0x18000a4bf`
- `OLEAUT32!__imp_VariantClear` at `0x180013aa7`
- `OLEAUT32!__imp_VariantClear` at `0x18000a4bf`
- `OLEAUT32!__imp_VariantClear` at `0x180013aa7`

## pseudocode

```c
__int64 __fastcall CBcdElement::CreateNew(struct IWbemClassObject *a1, struct CBcdElement **a2)
{
  struct CBcdElement *v4; // rbx
  int v5; // edi
  CBcdBooleanElement *v6; // rax
  CBcdBooleanElement *v7; // rax
  CBcdObjectListElement *v8; // rax
  CBcdStringElement *v9; // rax
  CBcdDeviceElement *v10; // rax
  VARIANTARG pvarg; // [rsp+50h] [rbp-48h] BYREF

  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"Type",
         0,
         &pvarg,
         0,
         0);
  if ( v5 < 0 )
    goto LABEL_24;
  if ( pvarg.vt != 3 )
  {
    v5 = -1063256037;
    goto LABEL_24;
  }
  switch ( BYTE3(pvarg.decVal.Lo64) & 0xF )
  {
    case 1:
      v10 = (CBcdDeviceElement *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 )
      {
        v7 = CBcdDeviceElement::CBcdDeviceElement(v10);
        goto LABEL_18;
      }
      break;
    case 2:
      v9 = (CBcdStringElement *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 )
      {
        v7 = CBcdStringElement::CBcdStringElement(v9);
        goto LABEL_18;
      }
      break;
    case 4:
      v8 = (CBcdObjectListElement *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v8 )
      {
        v7 = CBcdObjectListElement::CBcdObjectListElement(v8);
        goto LABEL_18;
      }
      break;
    case 6:
      v6 = (CBcdBooleanElement *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
      {
        v7 = CBcdBooleanElement::CBcdBooleanElement(v6);
LABEL_18:
        v4 = v7;
        goto LABEL_20;
      }
      break;
    default:
      v4 = (struct CBcdElement *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        *(_QWORD *)v4 = &CBcdElement::`vftable';
        *((_QWORD *)v4 + 1) = 0;
        *((_QWORD *)v4 + 2) = 0;
        *((_DWORD *)v4 + 6) = 0;
        goto LABEL_20;
      }
      break;
  }
  v4 = 0;
LABEL_20:
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(struct CBcdElement *, struct IWbemClassObject *))(*(_QWORD *)v4 + 8LL))(v4, a1);
    if ( v5 >= 0 )
    {
      *a2 = v4;
      v4 = 0;
    }
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_24:
  VariantClear(&pvarg);
  if ( v4 )
    (**(void (__fastcall ***)(struct CBcdElement *, __int64))v4)(v4, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a338  push    rbx
0x18000a33a  push    rsi
0x18000a33b  push    rdi
0x18000a33c  push    r14
0x18000a33e  sub     rsp, 78h
0x18000a342  mov     r14, rdx
0x18000a345  mov     rsi, rcx
0x18000a348  xor     ebx, ebx
0x18000a34a  mov     [rsp+98h+var_50], rbx
0x18000a34f  xorps   xmm0, xmm0
0x18000a352  xor     eax, eax
0x18000a354  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000a359  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000a35e  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000a363  call    cs:__imp_VariantInit
0x18000a369  mov     rax, [rsi]
0x18000a36c  mov     [rsp+98h+var_70], rbx
0x18000a371  mov     [rsp+98h+var_78], rbx
0x18000a376  lea     r9, [rsp+98h+pvarg]
0x18000a37b  xor     r8d, r8d
0x18000a37e  lea     rdx, aType; "Type"
0x18000a385  mov     rcx, rsi
0x18000a388  mov     rax, [rax+20h]
0x18000a38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a391  mov     edi, eax
0x18000a393  mov     [rsp+98h+var_58], eax
0x18000a397  test    eax, eax
0x18000a399  js      loc_18000A4BA
0x18000a39f  cmp     word ptr [rsp+98h+pvarg], 3
0x18000a3a5  jz      short loc_18000A3B5
0x18000a3a7  mov     edi, 0C0A0001Bh
0x18000a3ac  mov     [rsp+98h+var_58], edi
0x18000a3b0  jmp     loc_18000A4BA
0x18000a3b5  mov     eax, dword ptr [rsp+98h+pvarg+8]
0x18000a3b9  shr     eax, 18h
0x18000a3bc  and     eax, 0Fh
0x18000a3bf  sub     eax, 1
0x18000a3c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a3c9  jz      loc_18000A462
0x18000a3cf  sub     eax, 1
0x18000a3d2  jz      short loc_18000A449
0x18000a3d4  sub     eax, 2
0x18000a3d7  jz      short loc_18000A430
0x18000a3d9  cmp     eax, 2
0x18000a3dc  jz      short loc_18000A417
0x18000a3de  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a3e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a3e8  mov     rbx, rax
0x18000a3eb  test    rax, rax
0x18000a3ee  jz      loc_18000A47E
0x18000a3f4  lea     rax, ??_7CBcdElement@@6B@; const CBcdElement::`vftable'
0x18000a3fb  mov     [rbx], rax
0x18000a3fe  mov     qword ptr [rbx+8], 0
0x18000a406  mov     qword ptr [rbx+10h], 0
0x18000a40e  mov     dword ptr [rbx+18h], 0
0x18000a415  jmp     short loc_18000A480
0x18000a417  mov     ecx, 28h ; '('; unsigned __int64
0x18000a41c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a421  test    rax, rax
0x18000a424  jz      short loc_18000A47E
0x18000a426  mov     rcx, rax; this
0x18000a429  call    ??0CBcdBooleanElement@@IEAA@XZ; CBcdBooleanElement::CBcdBooleanElement(void)
0x18000a42e  jmp     short loc_18000A479
0x18000a430  mov     ecx, 30h ; '0'; unsigned __int64
0x18000a435  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a43a  test    rax, rax
0x18000a43d  jz      short loc_18000A47E
0x18000a43f  mov     rcx, rax; this
0x18000a442  call    ??0CBcdObjectListElement@@IEAA@XZ; CBcdObjectListElement::CBcdObjectListElement(void)
0x18000a447  jmp     short loc_18000A479
0x18000a449  mov     ecx, 28h ; '('; unsigned __int64
0x18000a44e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a453  test    rax, rax
0x18000a456  jz      short loc_18000A47E
0x18000a458  mov     rcx, rax; this
0x18000a45b  call    ??0CBcdStringElement@@IEAA@XZ; CBcdStringElement::CBcdStringElement(void)
0x18000a460  jmp     short loc_18000A479
0x18000a462  mov     ecx, 28h ; '('; unsigned __int64
0x18000a467  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a46c  test    rax, rax
0x18000a46f  jz      short loc_18000A47E
0x18000a471  mov     rcx, rax; this
0x18000a474  call    ??0CBcdDeviceElement@@IEAA@XZ; CBcdDeviceElement::CBcdDeviceElement(void)
0x18000a479  mov     rbx, rax
0x18000a47c  jmp     short loc_18000A480
0x18000a47e  xor     ebx, ebx
0x18000a480  mov     [rsp+98h+var_50], rbx
0x18000a485  test    rbx, rbx
0x18000a488  jnz     short loc_18000A494
0x18000a48a  mov     edi, 8007000Eh
0x18000a48f  jmp     loc_18000A3AC
0x18000a494  mov     rax, [rbx]
0x18000a497  mov     rdx, rsi
0x18000a49a  mov     rcx, rbx
0x18000a49d  mov     rax, [rax+8]
0x18000a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4a6  mov     edi, eax
0x18000a4a8  mov     [rsp+98h+var_58], eax
0x18000a4ac  test    eax, eax
0x18000a4ae  js      short loc_18000A4BA
0x18000a4b0  mov     [r14], rbx
0x18000a4b3  xor     ebx, ebx
0x18000a4b5  mov     [rsp+98h+var_50], rbx
0x18000a4ba  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000a4bf  call    cs:__imp_VariantClear
0x18000a4c5  test    rbx, rbx
0x18000a4c8  jz      short loc_18000A4DD
0x18000a4ca  mov     rax, [rbx]
0x18000a4cd  mov     edx, 1
0x18000a4d2  mov     rcx, rbx
0x18000a4d5  mov     rax, [rax]
0x18000a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4dd  mov     eax, edi
0x18000a4df  add     rsp, 78h
0x18000a4e3  pop     r14
0x18000a4e5  pop     rdi
0x18000a4e6  pop     rsi
0x18000a4e7  pop     rbx
0x18000a4e8  retn
0x180013a9a  push    rbp
0x180013a9c  sub     rsp, 40h
0x180013aa0  mov     rbp, rdx
0x180013aa3  lea     rcx, [rbp+50h]; pvarg
0x180013aa7  call    cs:__imp_VariantClear
0x180013aad  mov     rcx, [rbp+48h]
0x180013ab1  test    rcx, rcx
0x180013ab4  jz      short loc_180013AC7
0x180013ab6  mov     rax, [rcx]
0x180013ab9  mov     edx, 1
0x180013abe  mov     rax, [rax]
0x180013ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac6  nop
0x180013ac7  add     rsp, 40h
0x180013acb  pop     rbp
0x180013acc  retn
```
