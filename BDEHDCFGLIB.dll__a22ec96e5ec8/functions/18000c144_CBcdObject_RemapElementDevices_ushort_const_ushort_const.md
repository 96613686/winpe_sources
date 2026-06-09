# CBcdObject::RemapElementDevices(ushort const *,ushort const *)

- ea: `0x18000c144`
- end: `0x18000c4c7`
- name: `?RemapElementDevices@CBcdObject@@IEAAJPEBG0@Z`
- size: `899`
- prototype: `__int64 __fastcall(const wchar_t **this, OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c4d0`

## callees

- `0x18000a338`
- `0x18000a5b0`
- `0x18000b69c`
- `0x18000b92c`
- `0x18000c144`
- `0x18000c820`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c1f7`
- `msvcrt!_wcsnicmp` at `0x18000c1f7`
- `msvcrt!_wcsicmp` at `0x18000c1a6`
- `msvcrt!_wcsicmp` at `0x18000c228`
- `msvcrt!_wcsicmp` at `0x18000c1a6`
- `msvcrt!_wcsicmp` at `0x18000c228`
- `OLEAUT32!__imp_VariantInit` at `0x18000c278`
- `OLEAUT32!__imp_VariantInit` at `0x18000c278`
- `OLEAUT32!__imp_VariantClear` at `0x18000c42f`
- `OLEAUT32!__imp_VariantClear` at `0x180013f28`
- `OLEAUT32!__imp_VariantClear` at `0x18000c42f`
- `OLEAUT32!__imp_VariantClear` at `0x180013f28`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000c301`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000c301`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000c2e4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000c2e4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000c319`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000c319`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c40f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c421`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013f1a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c40f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c421`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013f1a`

## pseudocode

```c
__int64 __fastcall CBcdObject::RemapElementDevices(const wchar_t **this, OLECHAR *psz, OLECHAR *a3)
{
  SAFEARRAY *parray; // r14
  int v7; // eax
  unsigned int v8; // edx
  CBcdObject *v9; // rcx
  HRESULT LBound; // ebx
  unsigned int v11; // edx
  __int64 v12; // rcx
  int v14; // eax
  LONG i; // edi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct IWbemClassObject **); // rcx
  struct IWbemClassObject *v18; // [rsp+40h] [rbp-98h] BYREF
  struct CBcdElement *v19; // [rsp+48h] [rbp-90h] BYREF
  LONG plUbound; // [rsp+50h] [rbp-88h] BYREF
  void *ppvData; // [rsp+58h] [rbp-80h] BYREF
  struct IWbemClassObject *v22; // [rsp+60h] [rbp-78h] BYREF
  struct CBcdDeviceElement *v23; // [rsp+68h] [rbp-70h] BYREF
  struct CBcdStringElement *v24; // [rsp+70h] [rbp-68h] BYREF
  LONG v25; // [rsp+78h] [rbp-60h]
  LONGLONG llVal; // [rsp+80h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-50h] BYREF
  LONG plLbound; // [rsp+F8h] [rbp+20h] BYREF

  v24 = 0;
  v23 = 0;
  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  parray = 0;
  llVal = 0;
  v22 = 0;
  v18 = 0;
  ppvData = 0;
  plLbound = 0;
  plUbound = 0;
  v7 = _wcsicmp(this[6], L"{9dea862c-5cdd-4e70-acc1-f32b344d4795}");
  v9 = (CBcdObject *)this;
  if ( !v7 )
  {
LABEL_2:
    LBound = CBcdObject::SetPartitionDeviceElement(v9, psz, 0x11000001u);
    if ( LBound >= 0 )
      LBound = 0;
    goto LABEL_35;
  }
  if ( (int)CBcdObject::GetElement((CBcdObject *)this, v8, &v24) >= 0
    && !_wcsnicmp(*((const wchar_t **)v24 + 4), L"\\Boot", 5u)
    && (int)CBcdObject::GetElement((CBcdObject *)this, v11, &v23) >= 0 )
  {
    v12 = *((_QWORD *)v23 + 4);
    if ( *(_DWORD *)(v12 + 8) == 2 ? _wcsicmp(*(const wchar_t **)(v12 + 24), a3) == 0 : *(_DWORD *)(v12 + 8) == 1 )
    {
      v9 = (CBcdObject *)this;
      goto LABEL_2;
    }
  }
  v14 = CBcdWmiWrapper::ExecuteMethod((CBcdWmiWrapper *)this, L"EnumerateElements", 0, &v22);
  LBound = v14;
  if ( v14 < 0 )
    goto LABEL_35;
  if ( v14 == 1 )
    goto LABEL_14;
  VariantInit(&pvarg);
  LBound = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v22->lpVtbl->Get)(
             v22,
             L"Elements",
             0,
             &pvarg,
             0,
             0);
  if ( LBound < 0 )
    goto LABEL_35;
  if ( pvarg.vt != 8205 )
  {
LABEL_14:
    LBound = -1063256037;
    goto LABEL_35;
  }
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
          v25 = i;
          if ( i > plUbound )
            break;
          v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IWbemClassObject **))*((_QWORD *)ppvData + i);
          if ( !v16 )
          {
            LBound = -2147467261;
            goto LABEL_35;
          }
          LBound = (**v16)(v16, &IID_IWbemClassObject, &v18);
          if ( LBound < 0 )
            goto LABEL_35;
          LBound = CBcdElement::CreateNew(v18, &v19);
          if ( LBound < 0 )
            goto LABEL_35;
          if ( (*((_DWORD *)v19 + 6) & 0xF000000) == 0x1000000 && *(_DWORD *)(*((_QWORD *)v19 + 4) + 8LL) == 1 )
          {
            LBound = CBcdObject::SetPartitionDeviceElement((CBcdObject *)this, a3, *((_DWORD *)v19 + 6));
            if ( LBound < 0 )
              goto LABEL_35;
          }
          if ( v19 )
            (**(void (__fastcall ***)(struct CBcdElement *, __int64))v19)(v19, 1);
          v19 = 0;
          if ( v18 )
          {
            ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
            v18 = 0;
          }
        }
        ppvData = 0;
        LBound = SafeArrayUnaccessData(parray);
      }
    }
  }
LABEL_35:
  if ( ppvData )
    SafeArrayUnaccessData(parray);
  VariantClear(&pvarg);
  if ( v22 )
    ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
  if ( v18 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v23 )
    (**(void (__fastcall ***)(struct CBcdDeviceElement *, __int64))v23)(v23, 1);
  if ( v24 )
    (**(void (__fastcall ***)(struct CBcdStringElement *, __int64))v24)(v24, 1);
  if ( v19 )
    (**(void (__fastcall ***)(struct CBcdElement *, __int64))v19)(v19, 1);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18000c144  mov     r11, rsp
0x18000c147  push    rbx
0x18000c148  push    rsi
0x18000c149  push    rdi
0x18000c14a  push    r12
0x18000c14c  push    r14
0x18000c14e  push    r15
0x18000c150  sub     rsp, 0A8h
0x18000c157  mov     r15, r8
0x18000c15a  mov     rbx, rdx
0x18000c15d  mov     rsi, rcx
0x18000c160  xor     r12d, r12d
0x18000c163  mov     [r11-68h], r12
0x18000c167  mov     [r11-70h], r12
0x18000c16b  mov     [rsp+0D8h+var_90], r12
0x18000c170  xorps   xmm0, xmm0
0x18000c173  xor     eax, eax
0x18000c175  movups  xmmword ptr [r11-50h], xmm0
0x18000c17a  mov     [r11-40h], rax
0x18000c17e  mov     r14d, r12d
0x18000c181  mov     [r11-58h], r12
0x18000c185  mov     [r11-78h], r12
0x18000c189  mov     [rsp+0D8h+var_98], r12
0x18000c18e  mov     [r11-80h], r12
0x18000c192  mov     [r11+20h], r12d
0x18000c196  mov     [rsp+0D8h+plUbound], r12d
0x18000c19b  lea     rdx, a9dea862c5cdd4e; "{9dea862c-5cdd-4e70-acc1-f32b344d4795}"
0x18000c1a2  mov     rcx, [rcx+30h]; String1
0x18000c1a6  call    cs:__imp__wcsicmp
0x18000c1ac  mov     rcx, rsi; this
0x18000c1af  test    eax, eax
0x18000c1b1  jnz     short loc_18000C1D3
0x18000c1b3  mov     rdx, rbx; psz
0x18000c1b6  mov     r8d, 11000001h; unsigned int
0x18000c1bc  call    ?SetPartitionDeviceElement@CBcdObject@@QEAAJPEBGI@Z; CBcdObject::SetPartitionDeviceElement(ushort const *,uint)
0x18000c1c1  mov     ebx, eax
0x18000c1c3  test    eax, eax
0x18000c1c5  js      loc_18000C417
0x18000c1cb  mov     ebx, r12d
0x18000c1ce  jmp     loc_18000C417
0x18000c1d3  lea     r8, [rsp+0D8h+var_68]; struct CBcdStringElement **
0x18000c1d8  call    ?GetElement@CBcdObject@@QEAAJIPEAPEAVCBcdStringElement@@@Z; CBcdObject::GetElement(uint,CBcdStringElement * *)
0x18000c1dd  test    eax, eax
0x18000c1df  js      short loc_18000C240
0x18000c1e1  mov     r8d, 5; MaxCount
0x18000c1e7  lea     rdx, aBoot; "\\Boot"
0x18000c1ee  mov     rcx, [rsp+0D8h+var_68]
0x18000c1f3  mov     rcx, [rcx+20h]; String1
0x18000c1f7  call    cs:__imp__wcsnicmp
0x18000c1fd  test    eax, eax
0x18000c1ff  jnz     short loc_18000C240
0x18000c201  lea     r8, [rsp+0D8h+var_70]; struct CBcdDeviceElement **
0x18000c206  mov     rcx, rsi; this
0x18000c209  call    ?GetElement@CBcdObject@@QEAAJIPEAPEAVCBcdDeviceElement@@@Z; CBcdObject::GetElement(uint,CBcdDeviceElement * *)
0x18000c20e  test    eax, eax
0x18000c210  js      short loc_18000C240
0x18000c212  mov     rax, [rsp+0D8h+var_70]
0x18000c217  mov     rcx, [rax+20h]
0x18000c21b  cmp     dword ptr [rcx+8], 2
0x18000c21f  jnz     short loc_18000C23A
0x18000c221  mov     rdx, r15; String2
0x18000c224  mov     rcx, [rcx+18h]; String1
0x18000c228  call    cs:__imp__wcsicmp
0x18000c22e  test    eax, eax
0x18000c230  jnz     short loc_18000C240
0x18000c232  mov     rcx, rsi
0x18000c235  jmp     loc_18000C1B3
0x18000c23a  cmp     dword ptr [rcx+8], 1
0x18000c23e  jmp     short loc_18000C230
0x18000c240  lea     r9, [rsp+0D8h+var_78]; struct IWbemClassObject **
0x18000c245  xor     r8d, r8d; struct IWbemClassObject *
0x18000c248  lea     rdx, aEnumerateeleme; "EnumerateElements"
0x18000c24f  mov     rcx, rsi; this
0x18000c252  call    ?ExecuteMethod@CBcdWmiWrapper@@IEAAJPEBGPEAUIWbemClassObject@@PEAPEAU2@@Z; CBcdWmiWrapper::ExecuteMethod(ushort const *,IWbemClassObject *,IWbemClassObject * *)
0x18000c257  mov     ebx, eax
0x18000c259  test    eax, eax
0x18000c25b  js      loc_18000C417
0x18000c261  cmp     eax, 1
0x18000c264  jnz     short loc_18000C270
0x18000c266  mov     ebx, 0C0A0001Bh
0x18000c26b  jmp     loc_18000C417
0x18000c270  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18000c278  call    cs:__imp_VariantInit
0x18000c27e  mov     rcx, [rsp+0D8h+var_78]
0x18000c283  mov     rax, [rcx]
0x18000c286  mov     [rsp+0D8h+var_B0], r12
0x18000c28b  mov     [rsp+0D8h+var_B8], r12
0x18000c290  lea     r9, [rsp+0D8h+pvarg]
0x18000c298  xor     r8d, r8d
0x18000c29b  lea     rdx, aElements; "Elements"
0x18000c2a2  mov     rax, [rax+20h]
0x18000c2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ab  mov     ebx, eax
0x18000c2ad  test    eax, eax
0x18000c2af  js      loc_18000C417
0x18000c2b5  mov     eax, 200Dh
0x18000c2ba  cmp     word ptr [rsp+0D8h+pvarg], ax
0x18000c2c2  jnz     short loc_18000C266
0x18000c2c4  mov     r14, qword ptr [rsp+0D8h+pvarg+8]
0x18000c2cc  mov     [rsp+0D8h+var_58], r14
0x18000c2d4  lea     r8, [rsp+0D8h+plLbound]; plLbound
0x18000c2dc  mov     edx, 1; nDim
0x18000c2e1  mov     rcx, r14; psa
0x18000c2e4  call    cs:__imp_SafeArrayGetLBound
0x18000c2ea  mov     ebx, eax
0x18000c2ec  test    eax, eax
0x18000c2ee  js      loc_18000C417
0x18000c2f4  lea     r8, [rsp+0D8h+plUbound]; plUbound
0x18000c2f9  mov     edx, 1; nDim
0x18000c2fe  mov     rcx, r14; psa
0x18000c301  call    cs:__imp_SafeArrayGetUBound
0x18000c307  mov     ebx, eax
0x18000c309  test    eax, eax
0x18000c30b  js      loc_18000C417
0x18000c311  lea     rdx, [rsp+0D8h+ppvData]; ppvData
0x18000c316  mov     rcx, r14; psa
0x18000c319  call    cs:__imp_SafeArrayAccessData
0x18000c31f  mov     ebx, eax
0x18000c321  test    eax, eax
0x18000c323  js      loc_18000C417
0x18000c329  mov     edi, [rsp+0D8h+plLbound]
0x18000c330  mov     [rsp+0D8h+var_60], edi
0x18000c334  cmp     edi, [rsp+0D8h+plUbound]
0x18000c338  jg      loc_18000C407
0x18000c33e  movsxd  rcx, edi
0x18000c341  mov     rax, [rsp+0D8h+ppvData]
0x18000c346  mov     rcx, [rax+rcx*8]
0x18000c34a  test    rcx, rcx
0x18000c34d  jnz     short loc_18000C359
0x18000c34f  mov     ebx, 80004003h
0x18000c354  jmp     loc_18000C417
0x18000c359  mov     rax, [rcx]
0x18000c35c  lea     r8, [rsp+0D8h+var_98]
0x18000c361  lea     rdx, IID_IWbemClassObject
0x18000c368  mov     rax, [rax]
0x18000c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c370  mov     ebx, eax
0x18000c372  test    eax, eax
0x18000c374  js      loc_18000C417
0x18000c37a  lea     rdx, [rsp+0D8h+var_90]; struct CBcdElement **
0x18000c37f  mov     rcx, [rsp+0D8h+var_98]; struct IWbemClassObject *
0x18000c384  call    ?CreateNew@CBcdElement@@KAJPEAUIWbemClassObject@@PEAPEAV1@@Z; CBcdElement::CreateNew(IWbemClassObject *,CBcdElement * *)
0x18000c389  mov     ebx, eax
0x18000c38b  test    eax, eax
0x18000c38d  js      loc_18000C417
0x18000c393  mov     rcx, [rsp+0D8h+var_90]
0x18000c398  mov     r8d, [rcx+18h]; unsigned int
0x18000c39c  mov     eax, r8d
0x18000c39f  and     eax, 0F000000h
0x18000c3a4  cmp     eax, 1000000h
0x18000c3a9  jnz     short loc_18000C3C6
0x18000c3ab  mov     rax, [rcx+20h]
0x18000c3af  cmp     dword ptr [rax+8], 1
0x18000c3b3  jnz     short loc_18000C3C6
0x18000c3b5  mov     rdx, r15; psz
0x18000c3b8  mov     rcx, rsi; this
0x18000c3bb  call    ?SetPartitionDeviceElement@CBcdObject@@QEAAJPEBGI@Z; CBcdObject::SetPartitionDeviceElement(ushort const *,uint)
0x18000c3c0  mov     ebx, eax
0x18000c3c2  test    eax, eax
0x18000c3c4  js      short loc_18000C417
0x18000c3c6  mov     rcx, [rsp+0D8h+var_90]
0x18000c3cb  test    rcx, rcx
0x18000c3ce  jz      short loc_18000C3E0
0x18000c3d0  mov     rax, [rcx]
0x18000c3d3  mov     edx, 1
0x18000c3d8  mov     rax, [rax]
0x18000c3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e0  mov     [rsp+0D8h+var_90], r12
0x18000c3e5  mov     rcx, [rsp+0D8h+var_98]
0x18000c3ea  test    rcx, rcx
0x18000c3ed  jz      short loc_18000C400
0x18000c3ef  mov     rax, [rcx]
0x18000c3f2  mov     rax, [rax+10h]
0x18000c3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fb  mov     [rsp+0D8h+var_98], r12
0x18000c400  inc     edi
0x18000c402  jmp     loc_18000C330
0x18000c407  mov     [rsp+0D8h+ppvData], r12
0x18000c40c  mov     rcx, r14; psa
0x18000c40f  call    cs:__imp_SafeArrayUnaccessData
0x18000c415  mov     ebx, eax
0x18000c417  cmp     [rsp+0D8h+ppvData], r12
0x18000c41c  jz      short loc_18000C427
0x18000c41e  mov     rcx, r14; psa
0x18000c421  call    cs:__imp_SafeArrayUnaccessData
0x18000c427  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18000c42f  call    cs:__imp_VariantClear
0x18000c435  mov     rcx, [rsp+0D8h+var_78]
0x18000c43a  test    rcx, rcx
0x18000c43d  jz      short loc_18000C44B
0x18000c43f  mov     rax, [rcx]
0x18000c442  mov     rax, [rax+10h]
0x18000c446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44b  mov     rcx, [rsp+0D8h+var_98]
0x18000c450  test    rcx, rcx
0x18000c453  jz      short loc_18000C466
0x18000c455  mov     rax, [rcx]
0x18000c458  mov     rax, [rax+10h]
0x18000c45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c461  mov     [rsp+0D8h+var_98], r12
0x18000c466  mov     rcx, [rsp+0D8h+var_70]
0x18000c46b  test    rcx, rcx
0x18000c46e  jz      short loc_18000C480
0x18000c470  mov     rax, [rcx]
0x18000c473  mov     edx, 1
0x18000c478  mov     rax, [rax]
0x18000c47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c480  mov     rcx, [rsp+0D8h+var_68]
0x18000c485  test    rcx, rcx
0x18000c488  jz      short loc_18000C49A
0x18000c48a  mov     rax, [rcx]
0x18000c48d  mov     edx, 1
0x18000c492  mov     rax, [rax]
0x18000c495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c49a  mov     rcx, [rsp+0D8h+var_90]
0x18000c49f  test    rcx, rcx
0x18000c4a2  jz      short loc_18000C4B4
0x18000c4a4  mov     rax, [rcx]
0x18000c4a7  mov     edx, 1
0x18000c4ac  mov     rax, [rax]
0x18000c4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4b4  mov     eax, ebx
0x18000c4b6  add     rsp, 0A8h
0x18000c4bd  pop     r15
0x18000c4bf  pop     r14
0x18000c4c1  pop     r12
0x18000c4c3  pop     rdi
0x18000c4c4  pop     rsi
0x18000c4c5  pop     rbx
0x18000c4c6  retn
0x180013f03  push    rbp
0x180013f05  sub     rsp, 40h
0x180013f09  mov     rbp, rdx
0x180013f0c  cmp     qword ptr [rbp+58h], 0
0x180013f11  jz      short loc_180013F21
0x180013f13  mov     rcx, [rbp+80h]; psa
0x180013f1a  call    cs:__imp_SafeArrayUnaccessData
0x180013f20  nop
0x180013f21  lea     rcx, [rbp+88h]; pvarg
0x180013f28  call    cs:__imp_VariantClear
0x180013f2e  mov     rcx, [rbp+60h]
0x180013f32  test    rcx, rcx
0x180013f35  jz      short loc_180013F44
0x180013f37  mov     rax, [rcx]
0x180013f3a  mov     rax, [rax+10h]
0x180013f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f43  nop
0x180013f44  mov     rcx, [rbp+40h]
0x180013f48  test    rcx, rcx
0x180013f4b  jz      short loc_180013F61
0x180013f4d  mov     rax, [rcx]
0x180013f50  mov     rax, [rax+10h]
0x180013f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f59  mov     qword ptr [rbp+40h], 0
0x180013f61  mov     rcx, [rbp+68h]
0x180013f65  test    rcx, rcx
0x180013f68  jz      short loc_180013F7B
0x180013f6a  mov     rax, [rcx]
0x180013f6d  mov     edx, 1
0x180013f72  mov     rax, [rax]
0x180013f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f7a  nop
0x180013f7b  mov     rcx, [rbp+70h]
0x180013f7f  test    rcx, rcx
0x180013f82  jz      short loc_180013F95
0x180013f84  mov     rax, [rcx]
0x180013f87  mov     edx, 1
0x180013f8c  mov     rax, [rax]
0x180013f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f94  nop
0x180013f95  mov     rcx, [rbp+48h]
0x180013f99  test    rcx, rcx
0x180013f9c  jz      short loc_180013FAF
0x180013f9e  mov     rax, [rcx]
0x180013fa1  mov     edx, 1
0x180013fa6  mov     rax, [rax]
0x180013fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fae  nop
0x180013faf  add     rsp, 40h
0x180013fb3  pop     rbp
0x180013fb4  retn
```
