# CSyncChangeBatch::CreateEmptyLearnedKnowledge(ISyncKnowledge * *)

- ea: `0x18004e2e4`
- end: `0x18004e4a6`
- name: `?CreateEmptyLearnedKnowledge@CSyncChangeBatch@@AEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CSyncChangeBatch *__hidden this, struct ISyncKnowledge **)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18004fa60`
- `0x18005022c`
- `0x180051480`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002070c`
- `0x18002d1c8`
- `0x18004e2e4`
- `0x180079388`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x18004e32e`: `CSyncChangeBatch::CreateEmptyLearnedKnowledge`
- `0x18004e468`: `CSyncChangeBatch::CreateEmptyLearnedKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::CreateEmptyLearnedKnowledge(CSyncChangeBatch *this, struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  bool v5; // zf
  int Parameters; // ebx
  int MadeWithKnowledge; // eax
  struct ISyncKnowledge *v8; // rdi
  IdParameters *v9; // rcx
  struct ISyncKnowledge *v11; // [rsp+30h] [rbp-40h] BYREF
  void *v12; // [rsp+38h] [rbp-38h] BYREF
  struct _ID_PARAMETERS v13; // [rsp+40h] [rbp-30h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::CreateEmptyLearnedKnowledge");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_DWORD *)this + 30) == 0;
  Parameters = -2147217380;
  v11 = 0;
  if ( !v5 )
  {
    MadeWithKnowledge = ChangeGroup::GetMadeWithKnowledge(**((ChangeGroup ***)this + 13), &v11);
    v8 = v11;
    Parameters = MadeWithKnowledge;
    if ( MadeWithKnowledge >= 0 )
    {
      v12 = 0;
      Parameters = CreateSyncService(&GUID_8ed97ec6_e77c_452e_9866_3747bc305db5, &v12);
      if ( Parameters >= 0 )
      {
        v9 = (IdParameters *)*((_QWORD *)this + 9);
        memset(&v13, 0, sizeof(v13));
        Parameters = IdParameters::GetParameters(v9, &v13);
        if ( Parameters >= 0 )
        {
          Parameters = (*(__int64 (__fastcall **)(void *, struct _ID_PARAMETERS *))(*(_QWORD *)v12 + 24LL))(v12, &v13);
          if ( Parameters >= 0 )
          {
            v11 = 0;
            Parameters = ((__int64 (__fastcall *)(struct ISyncKnowledge *, struct ISyncKnowledge **))v8->lpVtbl->GetReplicaKeyMap)(
                           v8,
                           &v11);
            if ( Parameters >= 0 )
            {
              Parameters = (*(__int64 (__fastcall **)(void *, _QWORD, struct ISyncKnowledge *, struct ISyncKnowledge **))(*(_QWORD *)v12 + 56LL))(
                             v12,
                             0,
                             v11,
                             a2);
              ((void (__fastcall *)(struct ISyncKnowledge *))v11->lpVtbl->Release)(v11);
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    if ( v8 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v8->lpVtbl->Release)(v8);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      113,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::CreateEmptyLearnedKnowledge",
      Parameters);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x18004e2e4  mov     [rsp-28h+arg_10], rbx
0x18004e2e9  push    rbp
0x18004e2ea  push    rsi
0x18004e2eb  push    rdi
0x18004e2ec  push    r12
0x18004e2ee  push    r14
0x18004e2f0  mov     rbp, rsp
0x18004e2f3  sub     rsp, 70h
0x18004e2f7  mov     rax, cs:__security_cookie
0x18004e2fe  xor     rax, rsp
0x18004e301  mov     [rbp+var_10], rax
0x18004e305  mov     r14, rdx
0x18004e308  mov     rsi, rcx
0x18004e30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e312  lea     r12, WPP_GLOBAL_Control
0x18004e319  cmp     rcx, r12
0x18004e31c  jz      short loc_18004E34D
0x18004e31e  test    byte ptr [rcx+1Ch], 10h
0x18004e322  jz      short loc_18004E34D
0x18004e324  cmp     byte ptr [rcx+19h], 5
0x18004e328  jb      short loc_18004E34D
0x18004e32a  mov     rcx, [rcx+10h]
0x18004e32e  lea     r9, aCsyncchangebat_59; "CSyncChangeBatch::CreateEmptyLearnedKno"...
0x18004e335  mov     edx, 70h ; 'p'
0x18004e33a  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18004e341  call    WPP_SF_s
0x18004e346  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e34d  cmp     dword ptr [rsi+78h], 0
0x18004e351  mov     ebx, 8004101Ch
0x18004e356  mov     [rbp+var_40], 0
0x18004e35e  jz      loc_18004E453
0x18004e364  mov     rcx, [rsi+68h]
0x18004e368  lea     rdx, [rbp+var_40]; struct ISyncKnowledge **
0x18004e36c  mov     rcx, [rcx]; this
0x18004e36f  call    ?GetMadeWithKnowledge@ChangeGroup@@QEAAJPEAPEAUISyncKnowledge@@@Z; ChangeGroup::GetMadeWithKnowledge(ISyncKnowledge * *)
0x18004e374  mov     rdi, [rbp+var_40]
0x18004e378  mov     ebx, eax
0x18004e37a  test    eax, eax
0x18004e37c  js      loc_18004E438
0x18004e382  lea     rdx, [rbp+var_38]; void **
0x18004e386  mov     [rbp+var_38], 0
0x18004e38e  lea     rcx, _GUID_8ed97ec6_e77c_452e_9866_3747bc305db5; struct _GUID *
0x18004e395  call    ?CreateSyncService@@YAJAEBU_GUID@@PEAPEAX@Z; CreateSyncService(_GUID const &,void * *)
0x18004e39a  mov     ebx, eax
0x18004e39c  test    eax, eax
0x18004e39e  js      loc_18004E438
0x18004e3a4  mov     rcx, [rsi+48h]; this
0x18004e3a8  lea     rdx, [rbp+var_30]; struct _ID_PARAMETERS *
0x18004e3ac  xorps   xmm0, xmm0
0x18004e3af  movups  xmmword ptr [rbp+var_30.dwSize], xmm0
0x18004e3b3  movups  xmmword ptr [rbp+var_30.itemId.fIsVariable], xmm0
0x18004e3b7  call    ?GetParameters@IdParameters@@QEAAJPEAU_ID_PARAMETERS@@@Z; IdParameters::GetParameters(_ID_PARAMETERS *)
0x18004e3bc  mov     ebx, eax
0x18004e3be  test    eax, eax
0x18004e3c0  js      short loc_18004E428
0x18004e3c2  mov     rcx, [rbp+var_38]
0x18004e3c6  lea     rdx, [rbp+var_30]
0x18004e3ca  mov     rax, [rcx]
0x18004e3cd  mov     rax, [rax+18h]
0x18004e3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3d6  mov     ebx, eax
0x18004e3d8  test    eax, eax
0x18004e3da  js      short loc_18004E428
0x18004e3dc  mov     [rbp+var_40], 0
0x18004e3e4  lea     rdx, [rbp+var_40]
0x18004e3e8  mov     rax, [rdi]
0x18004e3eb  mov     rcx, rdi
0x18004e3ee  mov     rax, [rax+48h]
0x18004e3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3f7  mov     ebx, eax
0x18004e3f9  test    eax, eax
0x18004e3fb  js      short loc_18004E428
0x18004e3fd  mov     rcx, [rbp+var_38]
0x18004e401  mov     r9, r14
0x18004e404  mov     r8, [rbp+var_40]
0x18004e408  xor     edx, edx
0x18004e40a  mov     rax, [rcx]
0x18004e40d  mov     rax, [rax+38h]
0x18004e411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e416  mov     rcx, [rbp+var_40]
0x18004e41a  mov     ebx, eax
0x18004e41c  mov     rax, [rcx]
0x18004e41f  mov     rax, [rax+10h]
0x18004e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e428  mov     rcx, [rbp+var_38]
0x18004e42c  mov     rax, [rcx]
0x18004e42f  mov     rax, [rax+10h]
0x18004e433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e438  test    rdi, rdi
0x18004e43b  jz      short loc_18004E44C
0x18004e43d  mov     rax, [rdi]
0x18004e440  mov     rcx, rdi
0x18004e443  mov     rax, [rax+10h]
0x18004e447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e44c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e453  cmp     rcx, r12
0x18004e456  jz      short loc_18004E484
0x18004e458  test    byte ptr [rcx+1Ch], 10h
0x18004e45c  jz      short loc_18004E484
0x18004e45e  cmp     byte ptr [rcx+19h], 5
0x18004e462  jb      short loc_18004E484
0x18004e464  mov     rcx, [rcx+10h]
0x18004e468  lea     r9, aCsyncchangebat_59; "CSyncChangeBatch::CreateEmptyLearnedKno"...
0x18004e46f  mov     edx, 71h ; 'q'
0x18004e474  mov     [rsp+70h+var_50], ebx
0x18004e478  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18004e47f  call    WPP_SF_sD
0x18004e484  mov     eax, ebx
0x18004e486  mov     rcx, [rbp+var_10]
0x18004e48a  xor     rcx, rsp; StackCookie
0x18004e48d  call    __security_check_cookie
0x18004e492  mov     rbx, [rsp+70h+arg_10]
0x18004e49a  add     rsp, 70h
0x18004e49e  pop     r14
0x18004e4a0  pop     r12
0x18004e4a2  pop     rdi
0x18004e4a3  pop     rsi
0x18004e4a4  pop     rbp
0x18004e4a5  retn
```
