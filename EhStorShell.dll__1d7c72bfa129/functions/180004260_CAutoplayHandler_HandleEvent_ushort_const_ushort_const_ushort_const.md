# CAutoplayHandler::HandleEvent(ushort const *,ushort const *,ushort const *)

- ea: `0x180004260`
- end: `0x18000449d`
- name: `?HandleEvent@CAutoplayHandler@@UEAAJPEBG00@Z`
- size: `573`
- prototype: `__int64 __fastcall(CAutoplayHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004260`
- `0x1800061ec`
- `0x1800064cc`
- `0x1800066c0`
- `0x18000684c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800042da`
- `KERNEL32!CompareStringW` at `0x1800042da`
- `ole32!CoCreateInstance` at `0x180004332`
- `ole32!CoCreateInstance` at `0x180004332`

## pseudocode

```c
__int64 __fastcall CAutoplayHandler::HandleEvent(
        CAutoplayHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // ebx
  HRESULT v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v12; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v13; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-8h] BYREF

  ppv = 0;
  v14 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, a4);
  if ( CompareStringW(0, 0, a4, -1, L"DeviceArrival", -1) != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, a4);
    v6 = -2147467263;
    goto LABEL_29;
  }
  v7 = CoCreateInstance(&CLSID_EnumEnhancedStorageACT, 0, 1u, &GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7, &ppv);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    v9 = 18;
    goto LABEL_13;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, a2, &v14);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    v9 = 19;
LABEL_13:
    WPP_SF_d(v8[2], v9, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, (unsigned int)v7);
    goto LABEL_29;
  }
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IUnknown **))v14)(
         v14,
         &GUID_022150a1_113d_11df_bb61_001aa01bbc58,
         &v13);
  if ( v6 >= 0 )
    goto LABEL_21;
  if ( v13 )
  {
    ATL::AtlComPtrAssign(&v13, 0);
LABEL_21:
    if ( v13 )
    {
      v12 = 1;
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v13->lpVtbl[4].AddRef)(v13, &v12);
      if ( v6 >= 0 && !v12 )
      {
        v6 = -2147467259;
        goto LABEL_29;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, v10);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 0, 0);
LABEL_29:
  if ( v13 )
    ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004260  push    rbp
0x180004262  push    rbx
0x180004263  push    rdi
0x180004264  push    r14
0x180004266  push    r15
0x180004268  mov     rbp, rsp
0x18000426b  sub     rsp, 50h
0x18000426f  mov     rbx, r9
0x180004272  mov     rdi, rdx
0x180004275  mov     [rbp+ppv], 0
0x18000427d  mov     [rbp+var_10], 0
0x180004285  mov     [rbp+var_18], 0
0x18000428d  lea     r14, WPP_GLOBAL_Control
0x180004294  lea     r15, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x18000429b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042a2  cmp     rcx, r14
0x1800042a5  jz      short loc_1800042BE
0x1800042a7  test    byte ptr [rcx+1Ch], 20h
0x1800042ab  jz      short loc_1800042BE
0x1800042ad  mov     edx, 10h
0x1800042b2  mov     r8, r15
0x1800042b5  mov     rcx, [rcx+10h]
0x1800042b9  call    WPP_SF_
0x1800042be  or      r9d, 0FFFFFFFFh; cchCount1
0x1800042c2  mov     [rsp+50h+cchCount2], r9d; cchCount2
0x1800042c7  lea     rax, aDevicearrival; "DeviceArrival"
0x1800042ce  mov     [rsp+50h+lpString2], rax; lpString2
0x1800042d3  mov     r8, rbx; lpString1
0x1800042d6  xor     edx, edx; dwCmpFlags
0x1800042d8  xor     ecx, ecx; Locale
0x1800042da  call    cs:__imp_CompareStringW
0x1800042e0  cmp     eax, 2
0x1800042e3  jz      short loc_180004315
0x1800042e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042ec  cmp     rcx, r14
0x1800042ef  jz      short loc_18000430B
0x1800042f1  test    byte ptr [rcx+1Ch], 2
0x1800042f5  jz      short loc_18000430B
0x1800042f7  mov     edx, 11h
0x1800042fc  mov     r9, rbx
0x1800042ff  mov     r8, r15
0x180004302  mov     rcx, [rcx+10h]
0x180004306  call    WPP_SF_S
0x18000430b  mov     ebx, 80004001h
0x180004310  jmp     loc_18000444D
0x180004315  lea     rax, [rbp+ppv]
0x180004319  mov     [rsp+50h+lpString2], rax; ppv
0x18000431e  lea     r9, _GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7; riid
0x180004325  xor     edx, edx; pUnkOuter
0x180004327  lea     r8d, [rdx+1]; dwClsContext
0x18000432b  lea     rcx, CLSID_EnumEnhancedStorageACT; rclsid
0x180004332  call    cs:__imp_CoCreateInstance
0x180004338  mov     ebx, eax
0x18000433a  test    eax, eax
0x18000433c  jns     short loc_180004371
0x18000433e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004345  cmp     rcx, r14
0x180004348  jz      loc_18000444D
0x18000434e  test    byte ptr [rcx+1Ch], 2
0x180004352  jz      loc_18000444D
0x180004358  mov     edx, 12h
0x18000435d  mov     r9d, eax
0x180004360  mov     r8, r15
0x180004363  mov     rcx, [rcx+10h]
0x180004367  call    WPP_SF_d
0x18000436c  jmp     loc_18000444D
0x180004371  mov     rcx, [rbp+ppv]
0x180004375  mov     rax, [rcx]
0x180004378  lea     r8, [rbp+var_10]
0x18000437c  mov     rdx, rdi
0x18000437f  mov     rax, [rax+20h]
0x180004383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004388  mov     ebx, eax
0x18000438a  test    eax, eax
0x18000438c  jns     short loc_1800043AF
0x18000438e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004395  cmp     rcx, r14
0x180004398  jz      loc_18000444D
0x18000439e  test    byte ptr [rcx+1Ch], 2
0x1800043a2  jz      loc_18000444D
0x1800043a8  mov     edx, 13h
0x1800043ad  jmp     short loc_18000435D
0x1800043af  mov     rcx, [rbp+var_10]
0x1800043b3  mov     rax, [rcx]
0x1800043b6  lea     r8, [rbp+var_18]
0x1800043ba  lea     rdx, _GUID_022150a1_113d_11df_bb61_001aa01bbc58
0x1800043c1  mov     rax, [rax]
0x1800043c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c9  mov     ebx, eax
0x1800043cb  test    eax, eax
0x1800043cd  jns     short loc_1800043E1
0x1800043cf  cmp     [rbp+var_18], 0
0x1800043d4  jz      short loc_180004414
0x1800043d6  xor     edx, edx; struct IUnknown *
0x1800043d8  lea     rcx, [rbp+var_18]; struct IUnknown **
0x1800043dc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800043e1  mov     rcx, [rbp+var_18]
0x1800043e5  test    rcx, rcx
0x1800043e8  jz      short loc_180004414
0x1800043ea  mov     [rbp+var_20], 1
0x1800043f1  mov     rax, [rcx]
0x1800043f4  lea     rdx, [rbp+var_20]
0x1800043f8  mov     rax, [rax+68h]
0x1800043fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004401  mov     ebx, eax
0x180004403  test    eax, eax
0x180004405  js      short loc_180004414
0x180004407  cmp     [rbp+var_20], 0
0x18000440b  jnz     short loc_180004414
0x18000440d  mov     ebx, 80004005h
0x180004412  jmp     short loc_18000444D
0x180004414  mov     rcx, cs:WPP_GLOBAL_Control
0x18000441b  cmp     rcx, r14
0x18000441e  jz      short loc_180004437
0x180004420  test    byte ptr [rcx+1Ch], 20h
0x180004424  jz      short loc_180004437
0x180004426  mov     edx, 14h
0x18000442b  mov     r8, r15
0x18000442e  mov     rcx, [rcx+10h]
0x180004432  call    WPP_SF_
0x180004437  mov     rcx, [rbp+var_10]
0x18000443b  mov     rax, [rcx]
0x18000443e  xor     r8d, r8d
0x180004441  xor     edx, edx
0x180004443  mov     rax, [rax+18h]
0x180004447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444c  nop
0x18000444d  mov     rcx, [rbp+var_18]
0x180004451  test    rcx, rcx
0x180004454  jz      short loc_180004463
0x180004456  mov     rax, [rcx]
0x180004459  mov     rax, [rax+10h]
0x18000445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004462  nop
0x180004463  mov     rcx, [rbp+var_10]
0x180004467  test    rcx, rcx
0x18000446a  jz      short loc_180004479
0x18000446c  mov     rax, [rcx]
0x18000446f  mov     rax, [rax+10h]
0x180004473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004478  nop
0x180004479  mov     rcx, [rbp+ppv]
0x18000447d  test    rcx, rcx
0x180004480  jz      short loc_18000448F
0x180004482  mov     rax, [rcx]
0x180004485  mov     rax, [rax+10h]
0x180004489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448e  nop
0x18000448f  mov     eax, ebx
0x180004491  add     rsp, 50h
0x180004495  pop     r15
0x180004497  pop     r14
0x180004499  pop     rdi
0x18000449a  pop     rbx
0x18000449b  pop     rbp
0x18000449c  retn
```
