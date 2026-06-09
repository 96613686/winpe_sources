# CBcdStore::OpenStore(ushort const *,CBcdStore * *)

- ea: `0x18000be90`
- end: `0x18000c13d`
- name: `?OpenStore@CBcdStore@@QEAAJPEBGPEAPEAV1@@Z`
- size: `685`
- prototype: `__int64 __fastcall(struct IWbemServices **this, OLECHAR *psz, struct CBcdStore **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180007bd0`

## callees

- `0x1800015c4`
- `0x180001c80`
- `0x18000a0f0`
- `0x18000a5b0`
- `0x18000bb80`
- `0x18000be90`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000bef4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bef4`
- `OLEAUT32!__imp_VariantInit` at `0x18000bee3`
- `OLEAUT32!__imp_VariantInit` at `0x18000bfae`
- `OLEAUT32!__imp_VariantInit` at `0x18000bee3`
- `OLEAUT32!__imp_VariantInit` at `0x18000bfae`
- `OLEAUT32!__imp_VariantClear` at `0x18000c0db`
- `OLEAUT32!__imp_VariantClear` at `0x18000c121`
- `OLEAUT32!__imp_VariantClear` at `0x180013eac`
- `OLEAUT32!__imp_VariantClear` at `0x180013eef`
- `OLEAUT32!__imp_VariantClear` at `0x18000c0db`
- `OLEAUT32!__imp_VariantClear` at `0x18000c121`
- `OLEAUT32!__imp_VariantClear` at `0x180013eac`
- `OLEAUT32!__imp_VariantClear` at `0x180013eef`

## string_xrefs

- `0x18000bf1a`: `OpenStore`
- `0x18000bf7d`: `OpenStore`

## pseudocode

```c
__int64 __fastcall CBcdStore::OpenStore(struct IWbemServices **this, OLECHAR *psz, struct CBcdStore **a3)
{
  CBcdWmiWrapper *v6; // rdi
  int v7; // ebx
  int v8; // eax
  CBcdStore *v9; // rax
  struct IWbemClassObject *v11; // [rsp+48h] [rbp-60h] BYREF
  CBcdWmiWrapper *v12; // [rsp+50h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF
  VARIANTARG v14; // [rsp+70h] [rbp-38h] BYREF
  struct IWbemClassObject *v15; // [rsp+C0h] [rbp+18h] BYREF
  struct IWbemClassObject *v16; // [rsp+C8h] [rbp+20h] BYREF

  v15 = 0;
  v11 = 0;
  memset(&v14, 0, sizeof(v14));
  v16 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = 0;
  v12 = 0;
  *a3 = 0;
  VariantInit(&v14);
  v14.vt = 8;
  v14.llVal = (LONGLONG)SysAllocString(psz);
  if ( !v14.llVal )
  {
LABEL_2:
    v7 = -2147024882;
    goto LABEL_20;
  }
  v7 = CBcdWmiWrapper::CreateInParams((CBcdWmiWrapper *)this, L"OpenStore", &v15);
  if ( v7 >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v15->lpVtbl->Put)(
           v15,
           L"File",
           0,
           &v14,
           0);
    if ( v7 >= 0 )
    {
      v8 = CBcdWmiWrapper::ExecuteMethod((CBcdWmiWrapper *)this, L"OpenStore", v15, &v11);
      v7 = v8;
      if ( v8 >= 0 )
      {
        if ( v8 == 1 )
        {
          v7 = -1063256043;
        }
        else
        {
          VariantInit(&pvarg);
          v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v11->lpVtbl->Get)(
                 v11,
                 L"Store",
                 0,
                 &pvarg,
                 0,
                 0);
          if ( v7 >= 0 )
          {
            if ( pvarg.vt == 13 )
            {
              if ( pvarg.llVal )
              {
                v7 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IWbemClassObject **))pvarg.llVal)(
                       pvarg.llVal,
                       &IID_IWbemClassObject,
                       &v16);
                if ( v7 >= 0 )
                {
                  v9 = (CBcdStore *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v9 )
                    v6 = CBcdStore::CBcdStore(v9);
                  else
                    v6 = 0;
                  v12 = v6;
                  if ( !v6 )
                    goto LABEL_2;
                  v7 = CBcdWmiWrapper::InitializeInstance(v6, this[2], v16);
                  if ( v7 >= 0 )
                  {
                    *a3 = v6;
                    v6 = 0;
                    v12 = 0;
                  }
                }
              }
              else
              {
                v7 = -2147467261;
              }
            }
            else
            {
              v7 = -1063256037;
            }
          }
        }
      }
    }
  }
LABEL_20:
  if ( v6 )
    (**(void (__fastcall ***)(CBcdWmiWrapper *, __int64))v6)(v6, 1);
  if ( v16 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  VariantClear(&pvarg);
  if ( v11 )
    ((void (__fastcall *)(struct IWbemClassObject *))v11->lpVtbl->Release)(v11);
  if ( v15 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  VariantClear(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000be90  mov     r11, rsp
0x18000be93  mov     [r11+8], rbx
0x18000be97  push    rsi
0x18000be98  push    rdi
0x18000be99  push    r14
0x18000be9b  sub     rsp, 90h
0x18000bea2  mov     r14, r8
0x18000bea5  mov     rbx, rdx
0x18000bea8  mov     rsi, rcx
0x18000beab  mov     qword ptr [r11+18h], 0
0x18000beb3  mov     qword ptr [r11-60h], 0
0x18000bebb  xorps   xmm0, xmm0
0x18000bebe  xor     eax, eax
0x18000bec0  movups  xmmword ptr [rsp+0A8h+var_38], xmm0
0x18000bec5  mov     [r11-28h], rax
0x18000bec9  mov     [r11+20h], rax
0x18000becd  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x18000bed2  mov     [r11-40h], rax
0x18000bed6  xor     edi, edi
0x18000bed8  mov     [r11-58h], rdi
0x18000bedc  mov     [r8], rax
0x18000bedf  lea     rcx, [r11-38h]; pvarg
0x18000bee3  call    cs:__imp_VariantInit
0x18000bee9  lea     eax, [rdi+8]
0x18000beec  mov     word ptr [rsp+0A8h+var_38], ax
0x18000bef1  mov     rcx, rbx; psz
0x18000bef4  call    cs:__imp_SysAllocString
0x18000befa  mov     qword ptr [rsp+0A8h+var_38+8], rax
0x18000beff  test    rax, rax
0x18000bf02  jnz     short loc_18000BF12
0x18000bf04  mov     ebx, 8007000Eh
0x18000bf09  mov     [rsp+0A8h+var_68], ebx
0x18000bf0d  jmp     loc_18000C099
0x18000bf12  lea     r8, [rsp+0A8h+arg_10]; struct IWbemClassObject **
0x18000bf1a  lea     rdx, aOpenstore; "OpenStore"
0x18000bf21  mov     rcx, rsi; this
0x18000bf24  call    ?CreateInParams@CBcdWmiWrapper@@IEAAJPEBGPEAPEAUIWbemClassObject@@@Z; CBcdWmiWrapper::CreateInParams(ushort const *,IWbemClassObject * *)
0x18000bf29  mov     ebx, eax
0x18000bf2b  mov     [rsp+0A8h+var_68], eax
0x18000bf2f  test    eax, eax
0x18000bf31  js      loc_18000C099
0x18000bf37  mov     rcx, [rsp+0A8h+arg_10]
0x18000bf3f  mov     rax, [rcx]
0x18000bf42  mov     dword ptr [rsp+0A8h+var_88], 0
0x18000bf4a  lea     r9, [rsp+0A8h+var_38]
0x18000bf4f  xor     r8d, r8d
0x18000bf52  lea     rdx, aFile; "File"
0x18000bf59  mov     rax, [rax+28h]
0x18000bf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf62  mov     ebx, eax
0x18000bf64  mov     [rsp+0A8h+var_68], eax
0x18000bf68  test    eax, eax
0x18000bf6a  js      loc_18000C099
0x18000bf70  lea     r9, [rsp+0A8h+var_60]; struct IWbemClassObject **
0x18000bf75  mov     r8, [rsp+0A8h+arg_10]; struct IWbemClassObject *
0x18000bf7d  lea     rdx, aOpenstore; "OpenStore"
0x18000bf84  mov     rcx, rsi; this
0x18000bf87  call    ?ExecuteMethod@CBcdWmiWrapper@@IEAAJPEBGPEAUIWbemClassObject@@PEAPEAU2@@Z; CBcdWmiWrapper::ExecuteMethod(ushort const *,IWbemClassObject *,IWbemClassObject * *)
0x18000bf8c  mov     ebx, eax
0x18000bf8e  mov     [rsp+0A8h+var_68], eax
0x18000bf92  test    eax, eax
0x18000bf94  js      loc_18000C099
0x18000bf9a  cmp     eax, 1
0x18000bf9d  jnz     short loc_18000BFA9
0x18000bf9f  mov     ebx, 0C0A00015h
0x18000bfa4  jmp     loc_18000BF09
0x18000bfa9  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18000bfae  call    cs:__imp_VariantInit
0x18000bfb4  mov     rcx, [rsp+0A8h+var_60]
0x18000bfb9  mov     rax, [rcx]
0x18000bfbc  mov     [rsp+0A8h+var_80], 0
0x18000bfc5  mov     [rsp+0A8h+var_88], 0
0x18000bfce  lea     r9, [rsp+0A8h+pvarg]
0x18000bfd3  xor     r8d, r8d
0x18000bfd6  lea     rdx, aStore; "Store"
0x18000bfdd  mov     rax, [rax+20h]
0x18000bfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe6  mov     ebx, eax
0x18000bfe8  mov     [rsp+0A8h+var_68], eax
0x18000bfec  test    eax, eax
0x18000bfee  js      loc_18000C099
0x18000bff4  cmp     word ptr [rsp+0A8h+pvarg], 0Dh
0x18000bffa  jz      short loc_18000C006
0x18000bffc  mov     ebx, 0C0A0001Bh
0x18000c001  jmp     loc_18000BF09
0x18000c006  mov     rcx, qword ptr [rsp+0A8h+pvarg+8]
0x18000c00b  test    rcx, rcx
0x18000c00e  jnz     short loc_18000C01A
0x18000c010  mov     ebx, 80004003h
0x18000c015  jmp     loc_18000BF09
0x18000c01a  mov     rax, [rcx]
0x18000c01d  lea     r8, [rsp+0A8h+arg_18]
0x18000c025  lea     rdx, IID_IWbemClassObject
0x18000c02c  mov     rax, [rax]
0x18000c02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c034  mov     ebx, eax
0x18000c036  mov     [rsp+0A8h+var_68], eax
0x18000c03a  test    eax, eax
0x18000c03c  js      short loc_18000C099
0x18000c03e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c045  mov     ecx, 28h ; '('; unsigned __int64
0x18000c04a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c04f  test    rax, rax
0x18000c052  jz      short loc_18000C061
0x18000c054  mov     rcx, rax; this
0x18000c057  call    ??0CBcdStore@@IEAA@XZ; CBcdStore::CBcdStore(void)
0x18000c05c  mov     rdi, rax
0x18000c05f  jmp     short loc_18000C063
0x18000c061  xor     edi, edi
0x18000c063  mov     [rsp+0A8h+var_58], rdi
0x18000c068  test    rdi, rdi
0x18000c06b  jz      loc_18000BF04
0x18000c071  mov     r8, [rsp+0A8h+arg_18]; struct IWbemClassObject *
0x18000c079  mov     rdx, [rsi+10h]; struct IWbemServices *
0x18000c07d  mov     rcx, rdi; this
0x18000c080  call    ?InitializeInstance@CBcdWmiWrapper@@IEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CBcdWmiWrapper::InitializeInstance(IWbemServices *,IWbemClassObject *)
0x18000c085  mov     ebx, eax
0x18000c087  mov     [rsp+0A8h+var_68], eax
0x18000c08b  test    eax, eax
0x18000c08d  js      short loc_18000C099
0x18000c08f  mov     [r14], rdi
0x18000c092  xor     edi, edi
0x18000c094  mov     [rsp+0A8h+var_58], rdi
0x18000c099  test    rdi, rdi
0x18000c09c  jz      short loc_18000C0B1
0x18000c09e  mov     rax, [rdi]
0x18000c0a1  mov     edx, 1
0x18000c0a6  mov     rcx, rdi
0x18000c0a9  mov     rax, [rax]
0x18000c0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b1  mov     rcx, [rsp+0A8h+arg_18]
0x18000c0b9  test    rcx, rcx
0x18000c0bc  jz      short loc_18000C0D6
0x18000c0be  mov     rax, [rcx]
0x18000c0c1  mov     rax, [rax+10h]
0x18000c0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ca  mov     [rsp+0A8h+arg_18], 0
0x18000c0d6  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18000c0db  call    cs:__imp_VariantClear
0x18000c0e1  mov     rcx, [rsp+0A8h+var_60]
0x18000c0e6  test    rcx, rcx
0x18000c0e9  jz      short loc_18000C0F7
0x18000c0eb  mov     rax, [rcx]
0x18000c0ee  mov     rax, [rax+10h]
0x18000c0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f7  mov     rcx, [rsp+0A8h+arg_10]
0x18000c0ff  test    rcx, rcx
0x18000c102  jz      short loc_18000C11C
0x18000c104  mov     rax, [rcx]
0x18000c107  mov     rax, [rax+10h]
0x18000c10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c110  mov     [rsp+0A8h+arg_10], 0
0x18000c11c  lea     rcx, [rsp+0A8h+var_38]; pvarg
0x18000c121  call    cs:__imp_VariantClear
0x18000c127  mov     eax, ebx
0x18000c129  mov     rbx, [rsp+0A8h+arg_0]
0x18000c131  add     rsp, 90h
0x18000c138  pop     r14
0x18000c13a  pop     rdi
0x18000c13b  pop     rsi
0x18000c13c  retn
0x180013e62  push    rbp
0x180013e64  sub     rsp, 40h
0x180013e68  mov     rbp, rdx
0x180013e6b  mov     rcx, [rbp+50h]
0x180013e6f  test    rcx, rcx
0x180013e72  jz      short loc_180013E85
0x180013e74  mov     rax, [rcx]
0x180013e77  mov     edx, 1
0x180013e7c  mov     rax, [rax]
0x180013e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e84  nop
0x180013e85  mov     rcx, [rbp+0C8h]
0x180013e8c  test    rcx, rcx
0x180013e8f  jz      short loc_180013EA8
0x180013e91  mov     rax, [rcx]
0x180013e94  mov     rax, [rax+10h]
0x180013e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e9d  mov     qword ptr [rbp+0C8h], 0
0x180013ea8  lea     rcx, [rbp+58h]; pvarg
0x180013eac  call    cs:__imp_VariantClear
0x180013eb2  mov     rcx, [rbp+48h]
0x180013eb6  test    rcx, rcx
0x180013eb9  jz      short loc_180013EC8
0x180013ebb  mov     rax, [rcx]
0x180013ebe  mov     rax, [rax+10h]
0x180013ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec7  nop
0x180013ec8  mov     rcx, [rbp+0C0h]
0x180013ecf  test    rcx, rcx
0x180013ed2  jz      short loc_180013EEB
0x180013ed4  mov     rax, [rcx]
0x180013ed7  mov     rax, [rax+10h]
0x180013edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ee0  mov     qword ptr [rbp+0C0h], 0
0x180013eeb  lea     rcx, [rbp+70h]; pvarg
0x180013eef  call    cs:__imp_VariantClear
0x180013ef5  nop
0x180013ef6  add     rsp, 40h
0x180013efa  pop     rbp
0x180013efb  retn
```
