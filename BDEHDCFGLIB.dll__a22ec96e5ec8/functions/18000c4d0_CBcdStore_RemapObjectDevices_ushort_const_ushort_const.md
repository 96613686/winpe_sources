# CBcdStore::RemapObjectDevices(ushort const *,ushort const *)

- ea: `0x18000c4d0`
- end: `0x18000c818`
- name: `?RemapObjectDevices@CBcdStore@@QEAAJPEBG0@Z`
- size: `840`
- prototype: `__int64 __fastcall(struct IWbemServices **this, OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007bd0`

## callees

- `0x18000a0f0`
- `0x18000a4f0`
- `0x18000a5b0`
- `0x18000c144`
- `0x18000c4d0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c53b`
- `OLEAUT32!__imp_VariantInit` at `0x18000c5df`
- `OLEAUT32!__imp_VariantInit` at `0x18000c53b`
- `OLEAUT32!__imp_VariantInit` at `0x18000c5df`
- `OLEAUT32!__imp_VariantClear` at `0x18000c77f`
- `OLEAUT32!__imp_VariantClear` at `0x18000c78d`
- `OLEAUT32!__imp_VariantClear` at `0x180013fde`
- `OLEAUT32!__imp_VariantClear` at `0x180013feb`
- `OLEAUT32!__imp_VariantClear` at `0x18000c77f`
- `OLEAUT32!__imp_VariantClear` at `0x18000c78d`
- `OLEAUT32!__imp_VariantClear` at `0x180013fde`
- `OLEAUT32!__imp_VariantClear` at `0x180013feb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000c665`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000c665`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000c648`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000c648`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000c67d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000c67d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c75f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c771`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013fd0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c75f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c771`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013fd0`

## pseudocode

```c
__int64 __fastcall CBcdStore::RemapObjectDevices(struct IWbemServices **this, OLECHAR *psz, OLECHAR *a3)
{
  SAFEARRAY *parray; // rsi
  int LBound; // ebx
  int v8; // eax
  LONG i; // edi
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct IWbemClassObject **); // rcx
  struct CBcdObject *v11; // r14
  struct IWbemClassObject *v13; // [rsp+40h] [rbp-98h] BYREF
  struct IWbemClassObject *v14; // [rsp+48h] [rbp-90h] BYREF
  LONG plUbound; // [rsp+50h] [rbp-88h] BYREF
  void *ppvData; // [rsp+58h] [rbp-80h] BYREF
  struct CBcdObject *v17; // [rsp+60h] [rbp-78h] BYREF
  struct IWbemClassObject *v18; // [rsp+68h] [rbp-70h] BYREF
  LONG v19; // [rsp+70h] [rbp-68h]
  LONGLONG llVal; // [rsp+78h] [rbp-60h]
  VARIANTARG v21; // [rsp+80h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-40h] BYREF
  LONG plLbound; // [rsp+F8h] [rbp+20h] BYREF

  v14 = 0;
  v18 = 0;
  v13 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v21, 0, sizeof(v21));
  parray = 0;
  llVal = 0;
  ppvData = 0;
  plLbound = 0;
  plUbound = 0;
  VariantInit(&v21);
  v21.vt = 3;
  v21.lVal = 0;
  LBound = CBcdWmiWrapper::CreateInParams((CBcdWmiWrapper *)this, L"EnumerateObjects", &v14);
  if ( LBound >= 0 )
  {
    LBound = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v14->lpVtbl->Put)(
               v14,
               L"Type",
               0,
               &v21,
               0);
    if ( LBound >= 0 )
    {
      v8 = CBcdWmiWrapper::ExecuteMethod((CBcdWmiWrapper *)this, L"EnumerateObjects", v14, &v18);
      LBound = v8;
      if ( v8 >= 0 )
      {
        if ( v8 == 1 )
        {
LABEL_5:
          LBound = -1063256037;
          goto LABEL_25;
        }
        VariantInit(&pvarg);
        LBound = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v18->lpVtbl->Get)(
                   v18,
                   L"Objects",
                   0,
                   &pvarg,
                   0,
                   0);
        if ( LBound >= 0 )
        {
          if ( pvarg.vt != 8205 )
            goto LABEL_5;
          parray = pvarg.parray;
          llVal = pvarg.llVal;
          LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
          if ( LBound >= 0 )
          {
            LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
            if ( LBound >= 0 )
            {
              LBound = SafeArrayAccessData(parray, &ppvData);
              if ( LBound >= 0 )
              {
                for ( i = plLbound; ; ++i )
                {
                  v19 = i;
                  if ( i > plUbound )
                    break;
                  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IWbemClassObject **))*((_QWORD *)ppvData + i);
                  if ( !v10 )
                  {
                    LBound = -2147467261;
                    goto LABEL_25;
                  }
                  LBound = (**v10)(v10, &IID_IWbemClassObject, &v13);
                  if ( LBound < 0 )
                    goto LABEL_25;
                  LBound = CBcdObject::CreateNew(this[2], v13, &v17);
                  if ( LBound < 0 )
                    goto LABEL_25;
                  v11 = v17;
                  LBound = CBcdObject::RemapElementDevices((const wchar_t **)v17, psz, a3);
                  if ( LBound < 0 )
                    goto LABEL_25;
                  if ( v11 )
                    (**(void (__fastcall ***)(struct CBcdObject *, __int64))v11)(v11, 1);
                  v17 = 0;
                  if ( v13 )
                  {
                    ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                    v13 = 0;
                  }
                }
                ppvData = 0;
                LBound = SafeArrayUnaccessData(parray);
              }
            }
          }
        }
      }
    }
  }
LABEL_25:
  if ( ppvData )
    SafeArrayUnaccessData(parray);
  VariantClear(&v21);
  VariantClear(&pvarg);
  if ( v14 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v18 )
    ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
  if ( v13 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v17 )
    (**(void (__fastcall ***)(struct CBcdObject *, __int64))v17)(v17, 1);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18000c4d0  mov     r11, rsp
0x18000c4d3  mov     [r11+8], rbx
0x18000c4d7  mov     [r11+10h], rsi
0x18000c4db  push    rdi
0x18000c4dc  push    r12
0x18000c4de  push    r13
0x18000c4e0  push    r14
0x18000c4e2  push    r15
0x18000c4e4  sub     rsp, 0B0h
0x18000c4eb  mov     r12, r8
0x18000c4ee  mov     r13, rdx
0x18000c4f1  mov     r15, rcx
0x18000c4f4  xor     r14d, r14d
0x18000c4f7  mov     [rsp+0D8h+var_90], r14
0x18000c4fc  mov     [r11-70h], r14
0x18000c500  mov     [rsp+0D8h+var_98], r14
0x18000c505  mov     [r11-78h], r14
0x18000c509  xorps   xmm0, xmm0
0x18000c50c  xor     eax, eax
0x18000c50e  movups  xmmword ptr [r11-40h], xmm0
0x18000c513  mov     [r11-30h], rax
0x18000c517  xorps   xmm1, xmm1
0x18000c51a  movups  xmmword ptr [r11-58h], xmm1
0x18000c51f  mov     [r11-48h], rax
0x18000c523  mov     esi, r14d
0x18000c526  mov     [r11-60h], r14
0x18000c52a  mov     [r11-80h], r14
0x18000c52e  mov     [r11+20h], r14d
0x18000c532  mov     [rsp+0D8h+plUbound], r14d
0x18000c537  lea     rcx, [r11-58h]; pvarg
0x18000c53b  call    cs:__imp_VariantInit
0x18000c541  lea     eax, [r14+3]
0x18000c545  mov     word ptr [rsp+0D8h+var_58], ax
0x18000c54d  mov     dword ptr [rsp+0D8h+var_58+8], r14d
0x18000c555  lea     r8, [rsp+0D8h+var_90]; struct IWbemClassObject **
0x18000c55a  lea     rdx, aEnumerateobjec; "EnumerateObjects"
0x18000c561  mov     rcx, r15; this
0x18000c564  call    ?CreateInParams@CBcdWmiWrapper@@IEAAJPEBGPEAPEAUIWbemClassObject@@@Z; CBcdWmiWrapper::CreateInParams(ushort const *,IWbemClassObject * *)
0x18000c569  mov     ebx, eax
0x18000c56b  test    eax, eax
0x18000c56d  js      loc_18000C767
0x18000c573  mov     rcx, [rsp+0D8h+var_90]
0x18000c578  mov     rax, [rcx]
0x18000c57b  mov     dword ptr [rsp+0D8h+var_B8], r14d
0x18000c580  lea     r9, [rsp+0D8h+var_58]
0x18000c588  xor     r8d, r8d
0x18000c58b  lea     rdx, aType; "Type"
0x18000c592  mov     rax, [rax+28h]
0x18000c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c59b  mov     ebx, eax
0x18000c59d  test    eax, eax
0x18000c59f  js      loc_18000C767
0x18000c5a5  lea     r9, [rsp+0D8h+var_70]; struct IWbemClassObject **
0x18000c5aa  mov     r8, [rsp+0D8h+var_90]; struct IWbemClassObject *
0x18000c5af  lea     rdx, aEnumerateobjec; "EnumerateObjects"
0x18000c5b6  mov     rcx, r15; this
0x18000c5b9  call    ?ExecuteMethod@CBcdWmiWrapper@@IEAAJPEBGPEAUIWbemClassObject@@PEAPEAU2@@Z; CBcdWmiWrapper::ExecuteMethod(ushort const *,IWbemClassObject *,IWbemClassObject * *)
0x18000c5be  mov     ebx, eax
0x18000c5c0  test    eax, eax
0x18000c5c2  js      loc_18000C767
0x18000c5c8  cmp     eax, 1
0x18000c5cb  jnz     short loc_18000C5D7
0x18000c5cd  mov     ebx, 0C0A0001Bh
0x18000c5d2  jmp     loc_18000C767
0x18000c5d7  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18000c5df  call    cs:__imp_VariantInit
0x18000c5e5  mov     rcx, [rsp+0D8h+var_70]
0x18000c5ea  mov     rax, [rcx]
0x18000c5ed  mov     [rsp+0D8h+var_B0], r14
0x18000c5f2  mov     [rsp+0D8h+var_B8], r14
0x18000c5f7  lea     r9, [rsp+0D8h+pvarg]
0x18000c5ff  xor     r8d, r8d
0x18000c602  lea     rdx, aObjects; "Objects"
0x18000c609  mov     rax, [rax+20h]
0x18000c60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c612  mov     ebx, eax
0x18000c614  test    eax, eax
0x18000c616  js      loc_18000C767
0x18000c61c  mov     eax, 200Dh
0x18000c621  cmp     word ptr [rsp+0D8h+pvarg], ax
0x18000c629  jnz     short loc_18000C5CD
0x18000c62b  mov     rsi, qword ptr [rsp+0D8h+pvarg+8]
0x18000c633  mov     [rsp+0D8h+var_60], rsi
0x18000c638  lea     r8, [rsp+0D8h+plLbound]; plLbound
0x18000c640  mov     edx, 1; nDim
0x18000c645  mov     rcx, rsi; psa
0x18000c648  call    cs:__imp_SafeArrayGetLBound
0x18000c64e  mov     ebx, eax
0x18000c650  test    eax, eax
0x18000c652  js      loc_18000C767
0x18000c658  lea     r8, [rsp+0D8h+plUbound]; plUbound
0x18000c65d  mov     edx, 1; nDim
0x18000c662  mov     rcx, rsi; psa
0x18000c665  call    cs:__imp_SafeArrayGetUBound
0x18000c66b  mov     ebx, eax
0x18000c66d  test    eax, eax
0x18000c66f  js      loc_18000C767
0x18000c675  lea     rdx, [rsp+0D8h+ppvData]; ppvData
0x18000c67a  mov     rcx, rsi; psa
0x18000c67d  call    cs:__imp_SafeArrayAccessData
0x18000c683  mov     ebx, eax
0x18000c685  test    eax, eax
0x18000c687  js      loc_18000C767
0x18000c68d  mov     edi, [rsp+0D8h+plLbound]
0x18000c694  mov     [rsp+0D8h+var_68], edi
0x18000c698  cmp     edi, [rsp+0D8h+plUbound]
0x18000c69c  jg      loc_18000C757
0x18000c6a2  movsxd  rcx, edi
0x18000c6a5  mov     rax, [rsp+0D8h+ppvData]
0x18000c6aa  mov     rcx, [rax+rcx*8]
0x18000c6ae  test    rcx, rcx
0x18000c6b1  jnz     short loc_18000C6BD
0x18000c6b3  mov     ebx, 80004003h
0x18000c6b8  jmp     loc_18000C767
0x18000c6bd  mov     rax, [rcx]
0x18000c6c0  lea     r8, [rsp+0D8h+var_98]
0x18000c6c5  lea     rdx, IID_IWbemClassObject
0x18000c6cc  mov     rax, [rax]
0x18000c6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d4  mov     ebx, eax
0x18000c6d6  test    eax, eax
0x18000c6d8  js      loc_18000C767
0x18000c6de  lea     r8, [rsp+0D8h+var_78]; struct CBcdObject **
0x18000c6e3  mov     rdx, [rsp+0D8h+var_98]; struct IWbemClassObject *
0x18000c6e8  mov     rcx, [r15+10h]; struct IWbemServices *
0x18000c6ec  call    ?CreateNew@CBcdObject@@KAJPEAUIWbemServices@@PEAUIWbemClassObject@@PEAPEAV1@@Z; CBcdObject::CreateNew(IWbemServices *,IWbemClassObject *,CBcdObject * *)
0x18000c6f1  mov     ebx, eax
0x18000c6f3  test    eax, eax
0x18000c6f5  js      short loc_18000C767
0x18000c6f7  mov     r8, r12; OLECHAR *
0x18000c6fa  mov     rdx, r13; psz
0x18000c6fd  mov     r14, [rsp+0D8h+var_78]
0x18000c702  mov     rcx, r14; this
0x18000c705  call    ?RemapElementDevices@CBcdObject@@IEAAJPEBG0@Z; CBcdObject::RemapElementDevices(ushort const *,ushort const *)
0x18000c70a  mov     ebx, eax
0x18000c70c  test    eax, eax
0x18000c70e  js      short loc_18000C752
0x18000c710  test    r14, r14
0x18000c713  jz      short loc_18000C728
0x18000c715  mov     rax, [r14]
0x18000c718  mov     edx, 1
0x18000c71d  mov     rcx, r14
0x18000c720  mov     rax, [rax]
0x18000c723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c728  xor     r14d, r14d
0x18000c72b  mov     [rsp+0D8h+var_78], r14
0x18000c730  mov     rcx, [rsp+0D8h+var_98]
0x18000c735  test    rcx, rcx
0x18000c738  jz      short loc_18000C74B
0x18000c73a  mov     rax, [rcx]
0x18000c73d  mov     rax, [rax+10h]
0x18000c741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c746  mov     [rsp+0D8h+var_98], r14
0x18000c74b  inc     edi
0x18000c74d  jmp     loc_18000C694
0x18000c752  xor     r14d, r14d
0x18000c755  jmp     short loc_18000C767
0x18000c757  mov     [rsp+0D8h+ppvData], r14
0x18000c75c  mov     rcx, rsi; psa
0x18000c75f  call    cs:__imp_SafeArrayUnaccessData
0x18000c765  mov     ebx, eax
0x18000c767  cmp     [rsp+0D8h+ppvData], r14
0x18000c76c  jz      short loc_18000C777
0x18000c76e  mov     rcx, rsi; psa
0x18000c771  call    cs:__imp_SafeArrayUnaccessData
0x18000c777  lea     rcx, [rsp+0D8h+var_58]; pvarg
0x18000c77f  call    cs:__imp_VariantClear
0x18000c785  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18000c78d  call    cs:__imp_VariantClear
0x18000c793  mov     rcx, [rsp+0D8h+var_90]
0x18000c798  test    rcx, rcx
0x18000c79b  jz      short loc_18000C7AE
0x18000c79d  mov     rax, [rcx]
0x18000c7a0  mov     rax, [rax+10h]
0x18000c7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a9  mov     [rsp+0D8h+var_90], r14
0x18000c7ae  mov     rcx, [rsp+0D8h+var_70]
0x18000c7b3  test    rcx, rcx
0x18000c7b6  jz      short loc_18000C7C4
0x18000c7b8  mov     rax, [rcx]
0x18000c7bb  mov     rax, [rax+10h]
0x18000c7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7c4  mov     rcx, [rsp+0D8h+var_98]
0x18000c7c9  test    rcx, rcx
0x18000c7cc  jz      short loc_18000C7DF
0x18000c7ce  mov     rax, [rcx]
0x18000c7d1  mov     rax, [rax+10h]
0x18000c7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7da  mov     [rsp+0D8h+var_98], r14
0x18000c7df  mov     rcx, [rsp+0D8h+var_78]
0x18000c7e4  test    rcx, rcx
0x18000c7e7  jz      short loc_18000C7F9
0x18000c7e9  mov     rax, [rcx]
0x18000c7ec  mov     edx, 1
0x18000c7f1  mov     rax, [rax]
0x18000c7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f9  mov     eax, ebx
0x18000c7fb  lea     r11, [rsp+0D8h+var_28]
0x18000c803  mov     rbx, [r11+30h]
0x18000c807  mov     rsi, [r11+38h]
0x18000c80b  mov     rsp, r11
0x18000c80e  pop     r15
0x18000c810  pop     r14
0x18000c812  pop     r13
0x18000c814  pop     r12
0x18000c816  pop     rdi
0x18000c817  retn
0x180013fbc  push    rbp
0x180013fbe  sub     rsp, 40h
0x180013fc2  mov     rbp, rdx
0x180013fc5  cmp     qword ptr [rbp+58h], 0
0x180013fca  jz      short loc_180013FD7
0x180013fcc  mov     rcx, [rbp+78h]; psa
0x180013fd0  call    cs:__imp_SafeArrayUnaccessData
0x180013fd6  nop
0x180013fd7  lea     rcx, [rbp+80h]; pvarg
0x180013fde  call    cs:__imp_VariantClear
0x180013fe4  lea     rcx, [rbp+98h]; pvarg
0x180013feb  call    cs:__imp_VariantClear
0x180013ff1  mov     rcx, [rbp+48h]
0x180013ff5  test    rcx, rcx
0x180013ff8  jz      short loc_18001400E
0x180013ffa  mov     rax, [rcx]
0x180013ffd  mov     rax, [rax+10h]
0x180014001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014006  mov     qword ptr [rbp+48h], 0
0x18001400e  mov     rcx, [rbp+68h]
0x180014012  test    rcx, rcx
0x180014015  jz      short loc_180014024
0x180014017  mov     rax, [rcx]
0x18001401a  mov     rax, [rax+10h]
0x18001401e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014023  nop
0x180014024  mov     rcx, [rbp+40h]
0x180014028  test    rcx, rcx
0x18001402b  jz      short loc_180014041
0x18001402d  mov     rax, [rcx]
0x180014030  mov     rax, [rax+10h]
0x180014034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014039  mov     qword ptr [rbp+40h], 0
0x180014041  mov     rcx, [rbp+60h]
0x180014045  test    rcx, rcx
0x180014048  jz      short loc_18001405B
0x18001404a  mov     rax, [rcx]
0x18001404d  mov     edx, 1
0x180014052  mov     rax, [rax]
0x180014055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001405a  nop
0x18001405b  add     rsp, 40h
0x18001405f  pop     rbp
0x180014060  retn
```
