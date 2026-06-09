# CBcdDeviceData::CreateNew(IWbemClassObject *,CBcdDeviceData * *)

- ea: `0x18000a1c0`
- end: `0x18000a332`
- name: `?CreateNew@CBcdDeviceData@@KAJPEAUIWbemClassObject@@PEAPEAV1@@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, struct CBcdDeviceData **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000aa50`
- `0x18000ab70`

## callees

- `0x1800015c4`
- `0x180009b84`
- `0x180009bac`
- `0x18000a1c0`
- `0x18000a338`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a1eb`
- `OLEAUT32!__imp_VariantInit` at `0x18000a1eb`
- `OLEAUT32!__imp_VariantClear` at `0x18000a308`
- `OLEAUT32!__imp_VariantClear` at `0x18000a308`

## pseudocode

```c
__int64 __fastcall CBcdDeviceData::CreateNew(struct IWbemClassObject *a1, struct CBcdDeviceData **a2)
{
  struct CBcdDeviceData *v4; // rbx
  int v5; // edi
  CBcdDeviceFileData *v6; // rax
  CBcdDeviceFileData *v7; // rax
  CBcdDevicePartitionData *v8; // rax
  VARIANTARG pvarg; // [rsp+50h] [rbp-48h] BYREF

  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"DeviceType",
         0,
         &pvarg,
         0,
         0);
  if ( v5 < 0 )
    goto LABEL_18;
  if ( pvarg.vt != 3 )
  {
    v5 = -1063256037;
    goto LABEL_18;
  }
  if ( pvarg.lVal == 2 )
  {
    v8 = (CBcdDevicePartitionData *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v7 = CBcdDevicePartitionData::CBcdDevicePartitionData(v8);
      goto LABEL_12;
    }
  }
  else
  {
    if ( (unsigned int)(pvarg.lVal - 3) >= 2 )
    {
      v4 = (struct CBcdDeviceData *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        *(_QWORD *)v4 = &CBcdDeviceData::`vftable';
        *((_DWORD *)v4 + 2) = 0;
        *((_QWORD *)v4 + 2) = 0;
        goto LABEL_14;
      }
      goto LABEL_13;
    }
    v6 = (CBcdDeviceFileData *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      v7 = CBcdDeviceFileData::CBcdDeviceFileData(v6);
LABEL_12:
      v4 = v7;
      goto LABEL_14;
    }
  }
LABEL_13:
  v4 = 0;
LABEL_14:
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(struct CBcdDeviceData *, struct IWbemClassObject *))(*(_QWORD *)v4 + 8LL))(v4, a1);
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
LABEL_18:
  VariantClear(&pvarg);
  if ( v4 )
    (**(void (__fastcall ***)(struct CBcdDeviceData *, __int64))v4)(v4, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a1c0  push    rbx
0x18000a1c2  push    rsi
0x18000a1c3  push    rdi
0x18000a1c4  push    r14
0x18000a1c6  sub     rsp, 78h
0x18000a1ca  mov     r14, rdx
0x18000a1cd  mov     rsi, rcx
0x18000a1d0  xor     ebx, ebx
0x18000a1d2  mov     [rsp+98h+var_50], rbx
0x18000a1d7  xorps   xmm0, xmm0
0x18000a1da  xor     eax, eax
0x18000a1dc  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000a1e1  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000a1e6  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000a1eb  call    cs:__imp_VariantInit
0x18000a1f1  mov     rax, [rsi]
0x18000a1f4  mov     [rsp+98h+var_70], rbx
0x18000a1f9  mov     [rsp+98h+var_78], rbx
0x18000a1fe  lea     r9, [rsp+98h+pvarg]
0x18000a203  xor     r8d, r8d
0x18000a206  lea     rdx, aDevicetype; "DeviceType"
0x18000a20d  mov     rcx, rsi
0x18000a210  mov     rax, [rax+20h]
0x18000a214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a219  mov     edi, eax
0x18000a21b  mov     [rsp+98h+var_58], eax
0x18000a21f  test    eax, eax
0x18000a221  js      loc_18000A303
0x18000a227  cmp     word ptr [rsp+98h+pvarg], 3
0x18000a22d  jz      short loc_18000A23D
0x18000a22f  mov     edi, 0C0A0001Bh
0x18000a234  mov     [rsp+98h+var_58], edi
0x18000a238  jmp     loc_18000A303
0x18000a23d  mov     ecx, dword ptr [rsp+98h+pvarg+8]
0x18000a241  sub     ecx, 2
0x18000a244  jz      short loc_18000A2A4
0x18000a246  sub     ecx, 1
0x18000a249  jz      short loc_18000A284
0x18000a24b  cmp     ecx, 1
0x18000a24e  jz      short loc_18000A284
0x18000a250  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a257  mov     ecx, 18h; unsigned __int64
0x18000a25c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a261  mov     rbx, rax
0x18000a264  test    rax, rax
0x18000a267  jz      short loc_18000A2C7
0x18000a269  lea     rax, ??_7CBcdDeviceData@@6B@; const CBcdDeviceData::`vftable'
0x18000a270  mov     [rbx], rax
0x18000a273  mov     dword ptr [rbx+8], 0
0x18000a27a  mov     qword ptr [rbx+10h], 0
0x18000a282  jmp     short loc_18000A2C9
0x18000a284  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a28b  mov     ecx, 28h ; '('; unsigned __int64
0x18000a290  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a295  test    rax, rax
0x18000a298  jz      short loc_18000A2C7
0x18000a29a  mov     rcx, rax; this
0x18000a29d  call    ??0CBcdDeviceFileData@@IEAA@XZ; CBcdDeviceFileData::CBcdDeviceFileData(void)
0x18000a2a2  jmp     short loc_18000A2C2
0x18000a2a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a2ab  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a2b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a2b5  test    rax, rax
0x18000a2b8  jz      short loc_18000A2C7
0x18000a2ba  mov     rcx, rax; this
0x18000a2bd  call    ??0CBcdDevicePartitionData@@IEAA@XZ; CBcdDevicePartitionData::CBcdDevicePartitionData(void)
0x18000a2c2  mov     rbx, rax
0x18000a2c5  jmp     short loc_18000A2C9
0x18000a2c7  xor     ebx, ebx
0x18000a2c9  mov     [rsp+98h+var_50], rbx
0x18000a2ce  test    rbx, rbx
0x18000a2d1  jnz     short loc_18000A2DD
0x18000a2d3  mov     edi, 8007000Eh
0x18000a2d8  jmp     loc_18000A234
0x18000a2dd  mov     rax, [rbx]
0x18000a2e0  mov     rdx, rsi
0x18000a2e3  mov     rcx, rbx
0x18000a2e6  mov     rax, [rax+8]
0x18000a2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ef  mov     edi, eax
0x18000a2f1  mov     [rsp+98h+var_58], eax
0x18000a2f5  test    eax, eax
0x18000a2f7  js      short loc_18000A303
0x18000a2f9  mov     [r14], rbx
0x18000a2fc  xor     ebx, ebx
0x18000a2fe  mov     [rsp+98h+var_50], rbx
0x18000a303  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000a308  call    cs:__imp_VariantClear
0x18000a30e  test    rbx, rbx
0x18000a311  jz      short loc_18000A326
0x18000a313  mov     rax, [rbx]
0x18000a316  mov     edx, 1
0x18000a31b  mov     rcx, rbx
0x18000a31e  mov     rax, [rax]
0x18000a321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a326  mov     eax, edi
0x18000a328  add     rsp, 78h
0x18000a32c  pop     r14
0x18000a32e  pop     rdi
0x18000a32f  pop     rsi
0x18000a330  pop     rbx
0x18000a331  retn
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
