# CRecoverableError_CreateInstance(__MIDL___MIDL_itf_winsync_0000_0000_0003,__MIDL___MIDL_itf_winsync_0000_0000_0001,CSyncChangeWrapper *,IRecoverableError * *)

- ea: `0x1800547d4`
- end: `0x18005493d`
- name: `?CRecoverableError_CreateInstance@@YAJW4__MIDL___MIDL_itf_winsync_0000_0000_0003@@W4__MIDL___MIDL_itf_winsync_0000_0000_0001@@PEAVCSyncChangeWrapper@@PEAPEAUIRecoverableError@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(enum __MIDL___MIDL_itf_winsync_0000_0000_0003, enum __MIDL___MIDL_itf_winsync_0000_0000_0001, struct CSyncChangeWrapper *, struct IRecoverableError **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180043ac0`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x1800547d4`
- `0x180054f2c`
- `0x180094010`

## string_xrefs

- `0x18005480d`: `CRecoverableError_CreateInstance`
- `0x180054912`: `CRecoverableError_CreateInstance`

## pseudocode

```c
__int64 __fastcall CRecoverableError_CreateInstance(
        enum __MIDL___MIDL_itf_winsync_0000_0000_0003 a1,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0001 a2,
        struct CSyncChangeWrapper *a3,
        struct IRecoverableError **a4)
{
  PVOID *v7; // rcx
  int v8; // edi
  CRecoverableError *v9; // rax
  enum __MIDL___MIDL_itf_winsync_0000_0000_0003 v10; // edx
  CRecoverableError *v11; // rbx

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids,
      "CRecoverableError_CreateInstance");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    v8 = -2147024882;
    v9 = (CRecoverableError *)SeAlloc(0x20u);
    v11 = v9;
    if ( v9 )
    {
      *((_DWORD *)v9 + 3) = 2;
      *((_DWORD *)v9 + 4) = 1;
      *(_QWORD *)v9 = &CRecoverableError::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      *((_QWORD *)v9 + 3) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids,
          "CRecoverableError::CRecoverableError");
      }
      _InterlockedAdd(&g_cRefThisDll, 1u);
      v8 = CRecoverableError::Init(v11, v10, a2, a3);
      if ( v8 >= 0 )
        v8 = (**(__int64 (__fastcall ***)(CRecoverableError *, GUID *, struct IRecoverableError **))v11)(
               v11,
               &GUID_0f5625e8_0a7b_45ee_9637_1ce13645909e,
               a4);
      (*(void (__fastcall **)(CRecoverableError *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v7[2],
      27,
      (unsigned int)WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids,
      (unsigned int)"CRecoverableError_CreateInstance",
      v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800547d4  push    rbx
0x1800547d6  push    rbp
0x1800547d7  push    rsi
0x1800547d8  push    rdi
0x1800547d9  push    r13
0x1800547db  push    r14
0x1800547dd  sub     rsp, 38h
0x1800547e1  mov     rsi, r9
0x1800547e4  mov     rbp, r8
0x1800547e7  mov     r14d, edx
0x1800547ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547f1  lea     r13, WPP_GLOBAL_Control
0x1800547f8  cmp     rcx, r13
0x1800547fb  jz      short loc_18005482C
0x1800547fd  test    byte ptr [rcx+1Ch], 8
0x180054801  jz      short loc_18005482C
0x180054803  cmp     byte ptr [rcx+19h], 5
0x180054807  jb      short loc_18005482C
0x180054809  mov     rcx, [rcx+10h]
0x18005480d  lea     r9, aCrecoverableer_8; "CRecoverableError_CreateInstance"
0x180054814  mov     edx, 1Ah
0x180054819  lea     r8, WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids
0x180054820  call    WPP_SF_s
0x180054825  mov     rcx, cs:WPP_GLOBAL_Control
0x18005482c  mov     edi, 80004003h
0x180054831  test    rsi, rsi
0x180054834  jz      loc_1800548FD
0x18005483a  mov     ecx, 20h ; ' '; unsigned __int64
0x18005483f  mov     qword ptr [rsi], 0
0x180054846  mov     edi, 8007000Eh
0x18005484b  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180054850  mov     rbx, rax
0x180054853  test    rax, rax
0x180054856  jz      loc_1800548F6
0x18005485c  mov     edi, 1
0x180054861  mov     dword ptr [rbx+0Ch], 2
0x180054868  lea     rax, ??_7CRecoverableError@@6B@; const CRecoverableError::`vftable'
0x18005486f  mov     [rbx+10h], edi
0x180054872  mov     [rbx], rax
0x180054875  mov     [rbx+8], edi
0x180054878  mov     qword ptr [rbx+18h], 0
0x180054880  mov     rcx, cs:WPP_GLOBAL_Control
0x180054887  cmp     rcx, r13
0x18005488a  jz      short loc_1800548B2
0x18005488c  test    byte ptr [rcx+1Ch], 8
0x180054890  jz      short loc_1800548B2
0x180054892  cmp     byte ptr [rcx+19h], 5
0x180054896  jb      short loc_1800548B2
0x180054898  mov     rcx, [rcx+10h]
0x18005489c  lea     edx, [rdi+9]
0x18005489f  lea     r9, aCrecoverableer_1; "CRecoverableError::CRecoverableError"
0x1800548a6  lea     r8, WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids
0x1800548ad  call    WPP_SF_s
0x1800548b2  lock add cs:?g_cRefThisDll@@3JC, edi; long volatile g_cRefThisDll
0x1800548b9  mov     r9, rbp; struct CSyncChangeWrapper *
0x1800548bc  mov     r8d, r14d; enum __MIDL___MIDL_itf_winsync_0000_0000_0001
0x1800548bf  mov     rcx, rbx; this
0x1800548c2  call    ?Init@CRecoverableError@@QEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0003@@W4__MIDL___MIDL_itf_winsync_0000_0000_0001@@PEAVCSyncChangeWrapper@@@Z; CRecoverableError::Init(__MIDL___MIDL_itf_winsync_0000_0000_0003,__MIDL___MIDL_itf_winsync_0000_0000_0001,CSyncChangeWrapper *)
0x1800548c7  mov     edi, eax
0x1800548c9  test    eax, eax
0x1800548cb  js      short loc_1800548E7
0x1800548cd  mov     rax, [rbx]
0x1800548d0  lea     rdx, _GUID_0f5625e8_0a7b_45ee_9637_1ce13645909e
0x1800548d7  mov     r8, rsi
0x1800548da  mov     rcx, rbx
0x1800548dd  mov     rax, [rax]
0x1800548e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548e5  mov     edi, eax
0x1800548e7  mov     rax, [rbx]
0x1800548ea  mov     rcx, rbx
0x1800548ed  mov     rax, [rax+10h]
0x1800548f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800548fd  cmp     rcx, r13
0x180054900  jz      short loc_18005492E
0x180054902  test    byte ptr [rcx+1Ch], 8
0x180054906  jz      short loc_18005492E
0x180054908  cmp     byte ptr [rcx+19h], 5
0x18005490c  jb      short loc_18005492E
0x18005490e  mov     rcx, [rcx+10h]
0x180054912  lea     r9, aCrecoverableer_8; "CRecoverableError_CreateInstance"
0x180054919  mov     edx, 1Bh
0x18005491e  mov     [rsp+68h+var_48], edi
0x180054922  lea     r8, WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids
0x180054929  call    WPP_SF_sD
0x18005492e  mov     eax, edi
0x180054930  add     rsp, 38h
0x180054934  pop     r14
0x180054936  pop     r13
0x180054938  pop     rdi
0x180054939  pop     rsi
0x18005493a  pop     rbp
0x18005493b  pop     rbx
0x18005493c  retn
```
