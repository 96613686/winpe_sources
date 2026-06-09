# ItemChangeWrapper::InitializeForgottenDelete(SharedRefPtr<ISyncKnowledge> const &,SharedRefPtr<IForgottenKnowledge> const &,SharedRefPtr<ISyncChange> const &)

- ea: `0x18007c190`
- end: `0x18007c325`
- name: `?InitializeForgottenDelete@ItemChangeWrapper@@QEAAJAEBV?$SharedRefPtr@UISyncKnowledge@@@@AEBV?$SharedRefPtr@UIForgottenKnowledge@@@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800752b4`
- `0x18007549c`

## callees

- `0x180005f20`
- `0x180011f60`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x18001dc70`
- `0x18007c190`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x18007c1d1`: `ItemChangeWrapper::InitializeForgottenDelete`
- `0x18007c2e6`: `ItemChangeWrapper::InitializeForgottenDelete`

## pseudocode

```c
__int64 __fastcall ItemChangeWrapper::InitializeForgottenDelete(__int64 a1, __int64 *a2, __int64 a3, __int64 *a4)
{
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v13[4]; // [rsp+38h] [rbp-28h] BYREF
  int v14; // [rsp+3Ch] [rbp-24h]
  __int64 v15; // [rsp+40h] [rbp-20h]
  _BYTE v16[4]; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+4Ch] [rbp-14h]
  __int64 v18; // [rsp+50h] [rbp-10h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      "ItemChangeWrapper::InitializeForgottenDelete");
  }
  v17 = 0;
  v18 = 0;
  v8 = SyncId::InitializeForRetrieval((SyncId *)v16, (const struct IdFormat *)(a1 + 60));
  if ( v8 >= 0 )
  {
    v9 = *a4;
    v12 = (unsigned __int16)v17;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v9 + 32LL))(v9, v18 + 4, &v12);
  }
  v14 = 0;
  v15 = 0;
  if ( v8 >= 0 )
  {
    v8 = SyncId::InitializeForRetrieval((SyncId *)v13, (const struct IdFormat *)(a1 + 52));
    if ( v8 >= 0 )
    {
      v10 = *a4;
      v12 = (unsigned __int16)v14;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v10 + 24LL))(v10, v15 + 4, &v12);
      if ( v8 >= 0 )
      {
        SharedRefPtr<IClockVector>::operator=((__int64 *)(a1 + 104), a2);
        SharedRefPtr<IForgottenKnowledge>::operator=(a1 + 120, a3);
        *(_DWORD *)(a1 + 200) = 1;
        *(_DWORD *)(a1 + 208) = 1;
        SyncId::operator=(a1 + 136, (__int64)v13);
        SyncId::operator=(a1 + 152, (__int64)v16);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      (unsigned int)"ItemChangeWrapper::InitializeForgottenDelete",
      v8);
  }
  SyncId::~SyncId((SyncId *)v13);
  SyncId::~SyncId((SyncId *)v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007c190  push    rbp
0x18007c192  push    rbx
0x18007c193  push    rsi
0x18007c194  push    rdi
0x18007c195  push    r13
0x18007c197  push    r14
0x18007c199  push    r15
0x18007c19b  mov     rbp, rsp
0x18007c19e  sub     rsp, 60h
0x18007c1a2  mov     rsi, r9
0x18007c1a5  mov     r14, r8
0x18007c1a8  mov     r15, rdx
0x18007c1ab  mov     rdi, rcx
0x18007c1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1b5  lea     r13, WPP_GLOBAL_Control
0x18007c1bc  cmp     rcx, r13
0x18007c1bf  jz      short loc_18007C1E9
0x18007c1c1  test    byte ptr [rcx+1Ch], 80h
0x18007c1c5  jz      short loc_18007C1E9
0x18007c1c7  cmp     byte ptr [rcx+19h], 5
0x18007c1cb  jb      short loc_18007C1E9
0x18007c1cd  mov     rcx, [rcx+10h]
0x18007c1d1  lea     r9, aItemchangewrap_25; "ItemChangeWrapper::InitializeForgottenD"...
0x18007c1d8  mov     edx, 12h
0x18007c1dd  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007c1e4  call    WPP_SF_s
0x18007c1e9  lea     rdx, [rdi+3Ch]; struct IdFormat *
0x18007c1ed  mov     [rbp+var_14], 0
0x18007c1f4  lea     rcx, [rbp+var_18]; this
0x18007c1f8  mov     [rbp+var_10], 0
0x18007c200  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18007c205  mov     ebx, eax
0x18007c207  test    eax, eax
0x18007c209  js      short loc_18007C22F
0x18007c20b  mov     rcx, [rsi]
0x18007c20e  lea     r8, [rbp+var_30]
0x18007c212  movzx   eax, word ptr [rbp+var_14]
0x18007c216  mov     rdx, [rbp+var_10]
0x18007c21a  mov     [rbp+var_30], eax
0x18007c21d  add     rdx, 4
0x18007c221  mov     rax, [rcx]
0x18007c224  mov     rax, [rax+20h]
0x18007c228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c22d  mov     ebx, eax
0x18007c22f  mov     [rbp+var_24], 0
0x18007c236  mov     [rbp+var_20], 0
0x18007c23e  test    ebx, ebx
0x18007c240  js      loc_18007C2CA
0x18007c246  lea     rdx, [rdi+34h]; struct IdFormat *
0x18007c24a  lea     rcx, [rbp+var_28]; this
0x18007c24e  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18007c253  mov     ebx, eax
0x18007c255  test    eax, eax
0x18007c257  js      short loc_18007C2CA
0x18007c259  mov     rcx, [rsi]
0x18007c25c  lea     r8, [rbp+var_30]
0x18007c260  movzx   eax, word ptr [rbp+var_24]
0x18007c264  mov     rdx, [rbp+var_20]
0x18007c268  mov     [rbp+var_30], eax
0x18007c26b  add     rdx, 4
0x18007c26f  mov     rax, [rcx]
0x18007c272  mov     rax, [rax+18h]
0x18007c276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c27b  mov     ebx, eax
0x18007c27d  test    eax, eax
0x18007c27f  js      short loc_18007C2CA
0x18007c281  lea     rcx, [rdi+68h]
0x18007c285  mov     rdx, r15
0x18007c288  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x18007c28d  lea     rcx, [rdi+78h]
0x18007c291  mov     rdx, r14
0x18007c294  call    ??4?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::operator=(SharedRefPtr<IForgottenKnowledge> const &)
0x18007c299  mov     eax, 1
0x18007c29e  lea     rcx, [rdi+88h]
0x18007c2a5  lea     rdx, [rbp+var_28]
0x18007c2a9  mov     [rdi+0C8h], eax
0x18007c2af  mov     [rdi+0D0h], eax
0x18007c2b5  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18007c2ba  lea     rcx, [rdi+98h]
0x18007c2c1  lea     rdx, [rbp+var_18]
0x18007c2c5  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18007c2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2d1  cmp     rcx, r13
0x18007c2d4  jz      short loc_18007C302
0x18007c2d6  test    byte ptr [rcx+1Ch], 80h
0x18007c2da  jz      short loc_18007C302
0x18007c2dc  cmp     byte ptr [rcx+19h], 5
0x18007c2e0  jb      short loc_18007C302
0x18007c2e2  mov     rcx, [rcx+10h]
0x18007c2e6  lea     r9, aItemchangewrap_25; "ItemChangeWrapper::InitializeForgottenD"...
0x18007c2ed  mov     edx, 13h
0x18007c2f2  mov     [rsp+60h+var_40], ebx
0x18007c2f6  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007c2fd  call    WPP_SF_sD
0x18007c302  lea     rcx, [rbp+var_28]; this
0x18007c306  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18007c30b  lea     rcx, [rbp+var_18]; this
0x18007c30f  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18007c314  mov     eax, ebx
0x18007c316  add     rsp, 60h
0x18007c31a  pop     r15
0x18007c31c  pop     r14
0x18007c31e  pop     r13
0x18007c320  pop     rdi
0x18007c321  pop     rsi
0x18007c322  pop     rbx
0x18007c323  pop     rbp
0x18007c324  retn
```
